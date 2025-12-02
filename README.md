# NBlogAutoTools Releases

**NBlogAutoTools** - 블로그 자동화 도구의 릴리즈 배포 전용 레포지토리입니다.

애플리케이션은 이 레포지토리를 통해 자동으로 업데이트를 확인하고 최신 버전을 다운로드합니다.

---

## 릴리즈 가이드라인

### 태그 형식

```
v{MAJOR}.{MINOR}.{PATCH}
```

**예시:**
- `v1.0.0`
- `v1.2.3`
- `v2.0.0-beta`

### 릴리즈명 형식

`v` 접두사 **없이** 시멘틱 버전만 사용:

```
{MAJOR}.{MINOR}.{PATCH}
```

**예시:**
- `1.0.0`
- `1.2.3`
- `2.0.0-beta`

### 릴리즈 파일명 규칙

| 플랫폼 | 형식 | 예시 |
|--------|------|------|
| Windows | `{파일명}_win.exe` | `{파일명}_win.exe` |
| macOS | `{파일명}_mac.zip` | `{파일명}_mac.zip` |

### macOS 빌드 참고사항

macOS 릴리즈는 `.app` 번들을 `.zip`으로 압축해야 합니다

### 릴리즈 체크리스트

- [ ] 태그가 `v{VERSION}` 형식인지 확인
- [ ] 릴리즈명이 `{VERSION}` (v 없음) 형식인지 확인
- [ ] Windows: `NBlogAutoTools_win.exe` 첨부
- [ ] macOS: `NBlogAutoTools_mac.zip` 첨부
- [ ] 릴리즈 노트에 변경사항 기술

---

## 자동 업데이트 메커니즘

애플리케이션은 GitHub Releases API를 통해 업데이트를 확인합니다:

```
GET https://api.github.com/repos/8around/nblog-auto-tools-releases/releases/latest
```

새 버전이 감지되면 사용자에게 업데이트 다운로드 및 설치를 안내합니다.

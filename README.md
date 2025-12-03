# NBlogAutoTools Releases

**NBlogAutoTools** - 블로그 자동화 도구의 릴리즈 배포 전용 레포지토리입니다.

---

## 포함된 애플리케이션

| 앱 | 식별자 (APP_ID) | 릴리즈 |
|----|--------------|-----------|
| 포스팅 | `uploader` | [Link](https://github.com/8around/nblog-auto-tools-releases/releases/tag/v0.1.0%2Buploader) |
| 이웃관리 | `neighbor` | [Link](https://github.com/8around/nblog-auto-tools-releases/releases/tag/v0.1.0%2Bneighbor) |

---

## 릴리즈 가이드라인

### 태그 형식 (PEP 440 Local Version)

```
v{VERSION}+{APP_ID}
```

| 앱 | 태그 예시 |
|----|----------|
| 포스팅 | `v1.0.0+uploader` |
| 이웃관리 | `v1.0.0+neighbor` |

### 릴리즈명 형식

```
{VERSION}+{APP_ID}
```

| 앱 | 릴리즈명 예시 |
|----|----------|
| 포스팅 | `1.0.0+uploader` |
| 이웃관리 | `1.0.0+neighbor` |

### 에셋 파일명 규칙

| 플랫폼 | 예시 |
|--------|------|
| Windows | `{파일명}_win.exe` | `{파일명}_win.exe` |
| macOS | `{파일명}_mac.zip` | `{파일명}_mac.zip` |

### macOS 빌드 참고사항

> macOS 릴리즈는 `.app` 번들을 `.zip`으로 압축해야 합니다

### 릴리즈 체크리스트

- [ ] 태그: `v{VERSION}+{APP_ID}` 형식
- [ ] 릴리즈명: `{VERSION}+{APP_ID}` 형식
- [ ] Windows/macOS 에셋 첨부
- [ ] 릴리즈 노트 작성

---

## 자동 업데이트 메커니즘

애플리케이션은 GitHub Releases API를 통해 업데이트를 확인합니다:

```
GET https://api.github.com/repos/8around/nblog-auto-tools-releases/releases
```

각 앱은 PEP 440 local version (`+uploader`, `+neighbor`)으로 자신의 릴리즈를 필터링합니다.

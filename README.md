# Assist Finder

**Mac과 Windows를 지원하는 S3 클라이언트.**
일반 Finder나 파일탐색기처럼 S3 버킷을 손쉽게 사용할 수 있습니다.

핵심 특징:
- 한국어 · 영어 · 일본어 네이티브 지원
- 영상 · 이미지 즉시 미리보기
- 객체 태그 지원

> 이 저장소는 Assist Finder의 **다운로드 배포 채널**입니다. 소스 코드는 별도 비공개 저장소에서 관리됩니다.

---

## 📥 다운로드 (Download)

가장 최신 빌드는 [Releases](../../releases) 페이지에서 받을 수 있습니다.

| 플랫폼 | 파일 |
|---|---|
| macOS (Apple Silicon · M1/M2/M3/M4) | `AssistFinder_*_aarch64.dmg` |
| macOS (Intel) | `AssistFinder_*_x64.dmg` |
| Windows 10/11 (64-bit) | `AssistFinder_*_x64_en-US.msi` |

> 어느 파일을 받아야 하는지 모르시면: macOS는 메뉴 →  → "이 Mac에 관하여"에서 칩 정보 확인. Apple M-시리즈면 `aarch64`, Intel이면 `x64`.

---

## 💻 시스템 요구사항 (Requirements)

- **macOS**: 12.0 Monterey 이상
- **Windows**: 10 이상 (64-bit)
- **메모리**: 권장 4 GB 이상
- **인터넷 연결**: AWS S3 통신용

---

## ⚠️ 첫 실행 시 보안 경고 안내

현재 베타 빌드는 **코드사이닝 전 단계**입니다 (정식 출시 시점에 해제 예정). 처음 실행할 때 OS의 보안 경고가 표시될 수 있습니다.

### macOS — "확인되지 않은 개발자" 경고

**방법 A (GUI, 권장)**
1. 다운받은 `.dmg`를 열고 앱을 `/Applications`로 드래그
2. Applications 폴더에서 앱을 처음 실행 시 경고가 나타나면 **취소**
3.  → 시스템 설정 → 개인 정보 보호 및 보안 → 하단의 **"확인 없이 열기"** 클릭

**방법 B (Terminal)**
```bash
xattr -cr /Applications/AssistFinder.app
```

### Windows — "Windows에서 PC를 보호했습니다" 경고

1. 다운받은 `.msi`를 더블클릭
2. SmartScreen 경고가 나타나면 **"추가 정보"** 클릭
3. **"실행"** 버튼이 나타나면 클릭

> 이 경고는 향후 정식 인증서 적용 후 사라집니다.

---

## 🚀 시작하기 (Getting Started)

설치 후 첫 실행 시:

1. 앱이 열리면 **"계정 추가"** 클릭
2. AWS Access Key ID + Secret Access Key + 리전 입력
3. **"연결 테스트"** 또는 **"저장"** — STS GetCallerIdentity로 자격증명을 검증합니다
4. 검증 성공 시 자동으로 활성 계정 전환, 버킷 목록이 표시됩니다

### 자격증명 안전성

- Secret Access Key는 OS 네이티브 키체인(macOS Keychain / Windows Credential Manager)에만 저장됩니다
- 앱 내부 어디에도 평문으로 보관되지 않습니다
- 외부 서버로 전송되지 않습니다 — 사용자의 AWS 계정에 직접 연결

---

## 🛠 주요 기능 (Features)

- 다중 AWS 계정 등록·전환 (OS 키체인 보안 저장)
- 버킷 탐색 (리스트/그리드 뷰, 폴더 네비게이션)
- 파일 업/다운로드 (멀티파트, 일시정지·재개·취소)
- 파일 관리 (복사·이동·이름변경·삭제·폴더 생성)
- prefix 기반 검색 + 확장자·크기·날짜 필터
- 이미지·동영상 즉시 미리보기 (썸네일 + 스트리밍)
- 파일 정보 패널 (메타데이터·태그·ACL·스토리지 클래스)
- 다크모드 (시스템 자동 연동 + 수동 전환)
- 전체 키보드 단축키

---

## 💬 지원 (Support)

- 버그 신고·기능 제안: [Issues](../../issues)
- 사용 중 발생한 오류는 가능하면 다음 정보와 함께 등록해주세요:
  - 앱 버전 (앱 → 정보)
  - OS와 버전
  - 재현 단계

---

## 📄 라이선스 (License)

- **앱 바이너리**: 무료 사용 (개인·상업 모두 허용)
- **소스 코드**: 비공개 (closed-source)

---

_Powered by Tauri + Rust + React_

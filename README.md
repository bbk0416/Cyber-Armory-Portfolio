# Cyber Armory

이 저장소는 비공개로 개발한 보안운영 플랫폼 프로토타입의 **공개 설명용 저장소**입니다. 소스코드는 공개하지 않고, 어떤 부분을 만들고 어떻게 검증했는지만 정리했습니다.

대표 포트폴리오는 [BBK Security Portfolio](https://bbk0416.github.io/bbk-security-portfolio/)입니다. Cyber Armory는 그중에서도 **보안 하드닝, 릴리스 점검, 배포 전 검증 경험을 보여주는 보조 자료**로 두고 있습니다.

실제 고객이 사용한 제품이나 운영 중인 상용 서비스로 소개하지 않습니다.

![Status](https://img.shields.io/badge/status-supporting--portfolio-blue)
![Source](https://img.shields.io/badge/source-private-lightgrey)
![Dependabot](https://img.shields.io/badge/Dependabot-0%20Open-brightgreen)
![Release Gate](https://img.shields.io/badge/Final%20Release%20Gate-PASS-brightgreen)
![Tests](https://img.shields.io/badge/pytest-189%20passed-brightgreen)

## 어떤 프로젝트였나

Flask 기반의 보안운영 플랫폼 프로토타입을 만들면서 다음 영역을 다뤘습니다.

- 로그인, 관리자 계정, 권한 관리
- 실행 대시보드와 파일 관리
- 보안 설정과 하드닝
- 취약 의존성 정리
- 릴리스 전 자동 점검
- Docker/Kubernetes 배포 전 확인
- 운영 절차와 점검 문서 정리

공개 저장소에는 내부 실행 로직, 실제 배포 설정, 비밀정보와 운영 데이터는 넣지 않았습니다.

## 마지막 비공개 기준선

| 항목 | 결과 |
|---|---|
| 비공개 구현 저장소 | `Cyber-Armory` |
| 공개 설명 저장소 | `Cyber-Armory-Portfolio` |
| 기준 버전 | `v0.34.0-hardened` |
| 이전 릴리스 기준 commit | `ca4ee2a` |
| Final Release Gate | PASS |
| 테스트 | 189 passed / 14 skipped / 1 warning |
| Dependabot | 0 Open |
| 기본 브랜치 | main |
| runtime artifact | 제외 |
| 소스코드 공개 | 하지 않음 |

`v0.34.0-hardened`에서는 release safety scan, Docker runtime preflight, Python compile validation까지 확인했습니다.

## 실제로 정리한 부분

- 실행 중 생기는 로그, 업로드 파일, DB, 백업, 가상환경을 릴리스 대상에서 제외
- Dependabot에서 확인된 취약 의존성 업데이트
- Gunicorn request smuggling 관련 advisory 반영
- 릴리스 전 자동 점검 추가
- 의존성 업데이트 뒤 테스트 재실행
- Docker/Kubernetes 배포 전 확인 절차 정리

## 구성

| 영역 | 내용 |
|---|---|
| 인증 | 로그인, 비밀번호 정책, 세션, 2FA 관련 설정 |
| 관리자 기능 | 사용자와 역할 관리 |
| 실행 화면 | 운영 작업을 위한 대시보드 |
| 파일 관리 | 업로드, 목록, 검증 흐름 |
| 보안 설정 | API key, 2FA, 비밀번호 정책 등 |
| 릴리스 점검 | 배포 전 자동 검사 |
| 배포 준비 | Docker/Kubernetes preflight |
| 문서 | 운영 절차, 체크리스트, 릴리스 기록 |

## 공개하지 않는 내용

이 저장소에는 아래 내용이 없습니다.

- 전체 소스코드
- 실제 배포 설정
- `.env`
- 계정정보, token, API key, 비밀번호
- 내부 실행 로직
- 실제 운영 인프라 정보
- exploit 구현 세부내용
- runtime 데이터, 로그, 업로드 파일, 백업

## 화면 예시

아래 이미지는 실제 내부정보를 넣지 않은 공개용 예시입니다.

| Validation | Dependency Security |
|---|---|
| ![Validation Summary](screenshots/01-validation-summary.svg) | ![Dependabot 0 Open](screenshots/02-dependabot-zero-open.svg) |

| Release Gate | Test Result |
|---|---|
| ![Final Release Gate PASS](screenshots/03-release-gate-pass.svg) | ![pytest result](screenshots/04-test-result.svg) |

| Architecture Overview |
|---|
| ![Architecture Overview](screenshots/05-architecture-overview.svg) |

추가 화면을 공개할 경우에는 사용자명, 이메일, 내부 IP, 개인 경로, token이나 세션값 같은 정보가 남지 않았는지 먼저 확인합니다.

## 사용 범위

보안 기능과 관련 코드는 허가된 환경의 방어·점검·학습 목적으로만 사용합니다. 권한이 없는 시스템을 대상으로 사용하지 않습니다.

## 왜 소스는 비공개인가

전체 구현을 공개할 필요가 없는 프로젝트라 소스는 비공개로 유지하고 있습니다. 이 저장소에서는 구현 자체보다 **어떤 보안 문제를 정리했고, 릴리스 전 어떤 검증을 했는지**만 보여줍니다.

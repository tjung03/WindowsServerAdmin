# Windows Server 관리 실습 기록

Windows Server 과정의 개인 학습 노트에서 **AD DS·DNS·DHCP·IIS·FTP의 구성 관계와 확인 절차**를 선별해 정리한 자료입니다. GUI 중심 실습도 서버 역할, 네트워크 전제, 작업 순서, 확인 지점을 문서로 남길 수 있습니다. 이 저장소는 실제 배포 자동화나 현재 운영 환경을 주장하지 않습니다.

## 실습 범위

| 주제 | 노트에 남은 구성 | 상세 |
|---|---|---|
| Active Directory | `hanbit.com` 포리스트, `second.hanbit.com` 자식 도메인, 읽기 전용 도메인 컨트롤러, 클라이언트 가입 | [AD 실습 구조](docs/ad-lab.md) |
| DNS·DHCP | DNS 서버 역할과 이름 조회, DHCP 범위 생성과 클라이언트 갱신 | [서비스 확인](docs/service-checks.md) |
| IIS·FTP | 서버 역할·서비스·방화벽 및 기본 문서·가상 디렉터리 실습 항목 | [서비스 확인](docs/service-checks.md) |

노트의 `[실습]` 표기는 실습 항목 또는 절차가 기록됐다는 뜻입니다. 이 자료만으로 각 단계의 성공 화면이나 현재 재현 결과까지 확인된 것은 아닙니다. `[실습x]`와 과제 요구사항은 완료 항목으로 포함하지 않았습니다.

## AD 실습 구성

| 노트의 이름 | 주소 | 노트상 역할 |
|---|---|---|
| FIRST | `192.168.10.10/24` | `hanbit.com` 첫 번째 DC·DNS |
| SECOND | `192.168.10.20/24` | `second.hanbit.com` 자식 도메인 DC |
| THIRD | `192.168.10.30/24` | `hanbit.com` 읽기 전용 DC(RODC) |
| WinClient | 노트에 주소 없음 | `hanbit.com` 도메인 멤버 |

이 주소와 이름은 **노트에 제시된 실습 구성값**입니다. 실제 환경에 그대로 적용하는 값이 아닙니다. 역할별 DNS 설정과 GUI 작업 순서는 [AD 실습 구조](docs/ad-lab.md)에 있습니다.

## 읽는 순서

1. [AD 실습 구조](docs/ad-lab.md)에서 도메인·DNS의 선행 관계와 노트의 설정 경로를 확인합니다.
2. [서비스 확인](docs/service-checks.md)에서 DNS·DHCP·IIS·FTP 실습 항목과 확인 기준을 확인합니다.
3. 새 환경에서 실습할 때는 OS 버전과 Microsoft 공식 문서를 먼저 대조하고, 완료 증거는 별도로 기록합니다.

## 버전 및 공개 범위

수업 노트에는 Windows Server 2012 R2 설치 매체와 `2022` 언급이 함께 있어 모든 절차를 하나의 버전에서 수행했다고 단정할 수 없습니다. **Windows Server 2012 R2의 연장 지원은 2023년 10월 10일 종료**되었습니다. 이 문서는 당시 학습 범위를 보존하며, 현재 재실습은 지원되는 Windows Server 버전의 [AD DS 설치 안내](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/deploy/install-active-directory-domain-services--level-100-)를 기준으로 화면과 절차를 다시 확인해야 합니다. [Microsoft 수명 주기](https://learn.microsoft.com/en-us/lifecycle/products/windows-server-2012-r2)

노트의 계정 비밀번호, 자동 로그인·보안 기능 해제, 로그인 화면에서의 암호 재설정 절차는 이 공개 문서에 싣지 않았습니다. 교재 PDF나 설치 이미지도 저장소에 포함하지 않습니다.

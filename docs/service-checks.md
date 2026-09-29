# DNS·DHCP·IIS·FTP 점검

[저장소 소개](../README.md)

다음 표는 각 서버 역할을 설치한 뒤 확인할 상태와 클라이언트 측 검증을 구분합니다. 실행 결과는 이 저장소에 포함되지 않습니다.

| 서비스 | 서버 측 확인 | 클라이언트 측 확인 |
|---|---|---|
| DNS | DNS 역할, 대상 존과 레코드 | 지정한 DNS 서버를 통한 이름 조회 결과 |
| DHCP | DHCP 역할, IPv4 범위와 활성 상태 | `ipconfig /release`·`ipconfig /renew` 후 주소·게이트웨이·DNS |
| IIS | 웹 사이트·바인딩·기본 문서와 서비스 상태 | 대상 URL의 HTTP 응답과 문서 내용 |
| FTP | IIS FTP 역할, 인증과 허용 경로 | 별도 실습 계정의 접속 및 파일 권한 |

AD DS 도메인과 별도의 DNS 존은 서로 다른 구성 대상으로 취급합니다. FTP 익명 업로드는 공개 환경의 권장 설정이 아닙니다.

## 점검 순서

1. 서버 관리자에서 대상 서버와 역할 설치 상태를 확인합니다.
2. 관리 도구에서 서비스 설정과 실행 상태를 확인합니다.
3. 다른 클라이언트에서 실제 DNS·DHCP·HTTP·FTP 요청 결과를 확인합니다.
4. 오류가 있다면 주소·라우팅·DNS, 서비스 상태·로그, 방화벽과 인증·파일 권한 순서로 범위를 좁힙니다.

GUI 명칭과 설정 항목은 설치한 Windows Server 버전에 맞춰 [Microsoft 공식 문서](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/deploy/install-active-directory-domain-services--level-100-)와 대조합니다.

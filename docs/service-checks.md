# DNS·DHCP·IIS·FTP 실습 항목과 확인

[저장소 소개](../README.md)

아래는 개인 학습 노트에 남아 있는 역할·관리 도구·확인 절차를 정리한 것입니다. 명령 실행 결과나 성공 화면은 첨부되어 있지 않습니다.

| 서비스 | 노트의 구성 항목 | 확인할 지점 |
|---|---|---|
| DNS | 서버 관리자에서 DNS 역할 설치, `brain.com` 존 실습 | DNS 관리 도구의 존·레코드와 클라이언트의 이름 조회 결과 |
| DHCP | DHCP 역할과 배포 후 구성, `dhcpmgmt.msc`에서 IPv4 범위 생성 | 범위 활성 상태, 클라이언트의 `ipconfig /release`·`ipconfig /renew` 후 주소·게이트웨이·DNS |
| IIS | 웹 서버 역할, 기본 문서·실제/가상 디렉터리 | 사이트 바인딩과 HTTP 응답, 기본 문서 접근 |
| FTP | IIS FTP 역할과 Microsoft FTP Service | 별도 실습 클라이언트의 접속·권한 확인 |

`brain.com` DNS 실습과 `hanbit.com` AD 실습은 노트의 **서로 다른 항목**입니다. 같은 DNS 존으로 합쳐 설명하지 않습니다. FTP의 익명 업로드와 디렉터리 검색은 노트에 실습 항목으로 적혀 있지만 공개 서비스의 권장 설정으로 제시하지 않습니다.

## 사용 시 확인

1. 서버 관리자에서 대상 서버·역할 설치 상태를 확인합니다.
2. 서비스 관리 도구(`services.msc`)에서 해당 서비스의 상태를 확인합니다.
3. DNS는 이름 조회, DHCP는 클라이언트 갱신 후 주소 설정, IIS는 HTTP 응답으로 각각 결과를 확인합니다.
4. 화면과 역할 옵션은 실제 설치 버전의 [Microsoft AD DS 안내](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/deploy/install-active-directory-domain-services--level-100-) 등 공식 문서와 대조합니다.

이 목록은 재실습 시 확인할 절차이며, 과거 실습의 성공 결과를 새로 주장하는 증거가 아닙니다.

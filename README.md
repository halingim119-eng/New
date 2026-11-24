# Search scriot — Netlify

## GitHub 및 Netlify 배포

1. 이 폴더의 파일 전체를 GitHub 저장소의 최상위에 올립니다. public, netlify 폴더와 netlify.toml을 포함해야 합니다.
2. Netlify에서 Add new project → Import an existing project → GitHub를 선택하고 저장소를 연결합니다.
3. 배포 설정은 netlify.toml에서 자동으로 읽습니다. Publish directory: `public`, Functions directory: `netlify/functions`. 별도 빌드 명령은 없습니다.
4. API 키는 요청에 따라 서버 코드에 기본값으로 들어 있습니다. 환경변수를 별도로 설정하지 않아도 됩니다. GitHub 저장소에 코드를 올리면 코드를 볼 수 있는 사람이 키도 볼 수 있습니다. 필요하면 Netlify 환경변수로 새 키를 지정할 수 있습니다.
5. Deploy project를 눌러 배포합니다.

영상 검색은 기존 외부 검색 서버를 사용합니다. 이 서버가 Netlify에서 접근 가능해야 검색이 가능합니다. 바이패스와 Pastebin은 해당 외부 서비스의 상태 및 제한에 따라 실패할 수 있습니다. 댓글과 영상 정보 조회에는 YouTube API 키 및 할당량이 필요합니다.

Netlify Functions는 실행 시간이 제한됩니다. 느린 외부 서버나 Linkvertise 요청은 시간 초과가 발생할 수 있습니다. 캐시는 실행 인스턴스 메모리에서만 유지되며 인스턴스 간 공유되지 않습니다.

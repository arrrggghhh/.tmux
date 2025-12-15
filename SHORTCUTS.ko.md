# tmux 단축키(Shortcuts)

tmux 설정에서 사용하는 주요 단축키를 한국어로 정리했습니다.

### 표기 규칙

- `<prefix>`: tmux prefix 키 조합을 의미합니다. 이 설정은 **기본 prefix `Ctrl-b`**를 유지하면서, **보조 prefix `Ctrl-a`**도 함께 제공합니다. 즉, 문서의 `<prefix>`는 `Ctrl-b` 또는 `Ctrl-a`로 눌러도 됩니다.
- `VISUAL` / `EDITOR`: 편집기를 결정하는 환경 변수입니다(둘 다 비어 있으면 기본값은 `vim`).

### 설정 / 화면

- `<prefix> e`: `.local` 커스터마이징 파일을 `VISUAL` 또는 `EDITOR`로 엽니다(비어 있으면 `vim`). 편집기를 종료하면 설정을 다시 로드합니다.
- `<prefix> r`: tmux 설정을 다시 로드합니다.
- `C-l`: 화면을 지우고(tmux 클리어), tmux 히스토리(스크롤백)도 함께 비웁니다.

### 세션(Session)

- `<prefix> C-c`: 새 세션을 만듭니다.
- `<prefix> C-f`: 세션 이름을 입력해서 다른 세션으로 전환합니다.

### 윈도우(Window) 이동

- `<prefix> C-h`, `<prefix> C-l`: 윈도우를 이전/다음으로 이동합니다.
  - 참고: 기본 `<prefix> n`은 unbind 되어 있고, `<prefix> p`는 다른 용도로 재사용됩니다.
- `<prefix> Tab`: 마지막으로 활성화됐던 윈도우로 이동합니다.

### 패널(Pane) 분할 / 이동 / 크기 조절

- `<prefix> -`: 현재 패널을 **세로로 분할**합니다.
- `<prefix> _`: 현재 패널을 **가로로 분할**합니다.
- `<prefix> h`, `<prefix> j`, `<prefix> k`, `<prefix> l`: Vim처럼 패널을 좌/하/상/우로 이동합니다.
- `<prefix> H`, `<prefix> J`, `<prefix> K`, `<prefix> L`: 패널 크기를 조절합니다.
- `<prefix> <`, `<prefix> >`: 패널을 서로 교환(swap)합니다.
- `<prefix> +`: 현재 패널을 새 윈도우로 **최대화(토글)**합니다.

### 유틸리티

- `<prefix> m`: 마우스 모드를 켜거나 끕니다.

### 복사 / 붙여넣기

- `<prefix> Enter`: copy-mode로 들어갑니다.
- `<prefix> b`: paste-buffer 목록을 봅니다.
- `<prefix> p`: 가장 위(최근)의 paste-buffer에서 붙여넣습니다.
- `<prefix> P`: 붙여넣을 paste-buffer를 선택합니다.
  - `P`로 버퍼 선택 화면을 띄운 뒤 `e`: 선택한 버퍼 내용을 편집기(`VISUAL`/`EDITOR`)로 열어 편집합니다.
  - 참고: `P` + `e`로 연 **select(선택) 기반 복사**에서, 줄 끝(EOL)까지 선택해 복사하면 buffer 내용 끝에 `\n`(개행)이 **같이 포함**될 수 있습니다.
    - 줄의 **마지막 문자까지만** 선택하면 `\n`이 **포함되지 않는** 경우가 많고, 줄 **끝까지(줄바꿈 포함)** 선택하면 `\n`이 **포함**될 수 있습니다.
    - 이미 `\n`이 포함된 상태라면, 열린 Vim에서 `:set binary noendofline`을 실행한 뒤 `:wq`로 저장하면 **버퍼 끝의 개행 없이** 저장할 수 있습니다.


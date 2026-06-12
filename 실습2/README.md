# kccenc-cowork-plugins

Claude Cowork / Claude Code 플러그인 마켓플레이스입니다. 플러그인을 모아 다른 사람이 설치할 수 있게 배포합니다.

## 구조

```
.
├── .claude-plugin/
│   └── marketplace.json        # 마켓플레이스 정의 (플러그인 목록)
└── plugins/
    └── text-tools/             # 개별 플러그인 (예시)
        ├── .claude-plugin/
        │   └── plugin.json     # 플러그인 매니페스트
        ├── skills/
        │   └── summarize/
        │       └── SKILL.md    # 스킬 정의
        └── README.md
```

## 설치해서 써보기

이 저장소를 GitHub에 올린 뒤, Claude Code/Cowork에서:

```shell
/plugin marketplace add <사용자명>/<저장소명>
/plugin install text-tools@kccenc-cowork-plugins
```

로컬에서 바로 테스트하려면 폴더 경로로 추가할 수도 있어요:

```shell
/plugin marketplace add ./
/plugin install text-tools@kccenc-cowork-plugins
```

## 플러그인 추가하기

1. `plugins/<플러그인이름>/` 폴더를 만들고 `.claude-plugin/plugin.json`을 작성합니다.
2. 그 안에 `skills/<스킬이름>/SKILL.md`로 기능을 추가합니다.
3. 루트 `.claude-plugin/marketplace.json`의 `plugins` 배열에 새 항목을 추가합니다.
4. 변경 사항을 커밋·푸시하면 사용자는 `/plugin marketplace update`로 갱신합니다.

> 이름(`kccenc-cowork-plugins`)은 공개로 노출됩니다. 바꾸려면 `marketplace.json`의 `name`을 수정하세요. (kebab-case·공백 없음)

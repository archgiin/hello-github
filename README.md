# hello-github

GitHub의 기본 흐름을 직접 손으로 익혀 보기 위한 연습용 저장소입니다.
커밋하고, 브랜치를 따고, Pull Request를 열어 보는 과정을 한 번씩 거쳐 보는 것이 목적입니다.

## 폴더 구성

| 경로 | 설명 |
| --- | --- |
| `README.md` | 저장소 소개와 연습 기록 (지금 보고 있는 파일) |
| `notes/` | 연습용 메모를 모아 두는 폴더 |
| `notes/first-note.md` | 첫 번째 연습 메모 |
| `notes/git-cheatsheet.md` | Git 기본 용어와 명령어 요약 (`practice/add-checklist` 브랜치에서 추가) |

## 연습 기록

1. **main 브랜치** — 저장소 소개 문구(이 문서)와 `notes/first-note.md`를 추가해 커밋·푸시
2. **practice/add-checklist 브랜치** — `notes/git-cheatsheet.md`를 추가하고 Pull Request 생성

## Git 기본 흐름 요약

```bash
git status                 # 무엇이 바뀌었는지 확인
git add <파일>             # 커밋할 변경 사항 고르기
git commit -m "메시지"     # 변경 사항 기록
git push                   # 원격 저장소로 올리기
```

브랜치를 따로 만들어 작업하면 main을 건드리지 않고 실험할 수 있고,
작업이 끝나면 Pull Request로 검토한 뒤 병합합니다.

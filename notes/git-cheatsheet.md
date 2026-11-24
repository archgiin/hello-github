# Git 치트시트

연습하면서 자주 쓰는 Git 명령어를 한 장으로 정리했습니다.

## 기본 용어

| 용어 | 뜻 |
| --- | --- |
| 저장소(repository) | 파일과 변경 이력을 함께 보관하는 공간 |
| 커밋(commit) | 변경 사항을 하나의 기록으로 묶어 저장한 것 |
| 브랜치(branch) | 원래 흐름에서 갈라져 나온 작업 갈래 |
| 원격(remote) | GitHub 같은 바깥에 있는 저장소 (`origin`이 기본 이름) |
| 스테이징(staging) | 커밋할 변경 사항을 골라 올려 두는 단계 |
| Pull Request | 브랜치의 변경을 main에 합쳐 달라고 요청하는 것 |
| Merge | Pull Request의 변경을 실제로 합치는 것 |

## 자주 쓰는 명령어

```bash
# 상태와 이력 보기
git status                  # 변경된 파일 확인
git log --oneline           # 커밋 이력을 한 줄씩 보기
git diff                    # 아직 스테이징하지 않은 변경 내용 보기

# 변경 사항 커밋하기
git add <파일>              # 특정 파일 스테이징
git add .                   # 현재 폴더의 변경 전부 스테이징
git commit -m "메시지"      # 커밋 만들기
git commit --amend          # 마지막 커밋 메시지나 내용 고치기

# 브랜치 다루기
git branch                  # 브랜치 목록
git switch -c <이름>        # 새 브랜치 만들고 이동
git switch <이름>           # 브랜치 이동
git switch main             # main으로 돌아오기
git branch -d <이름>        # 병합된 브랜치 삭제

# 원격 저장소와 주고받기
git clone <주소>            # 저장소 복제
git pull                    # 원격의 변경 내려받기
git push                    # 원격으로 올리기
git push -u origin <브랜치> # 새 브랜치를 원격에 올리고 연결

# 되돌리기
git restore <파일>          # 커밋하지 않은 변경 취소
git restore --staged <파일> # 스테이징만 취소
git revert <커밋>           # 이미 올린 커밋을 되돌리는 새 커밋 만들기
```

## 작업 순서 예시

```bash
git switch -c practice/my-branch   # 1. 브랜치 만들기
# 파일 수정
git add .                          # 2. 변경 스테이징
git commit -m "설명"               # 3. 커밋
git push -u origin practice/my-branch  # 4. 원격에 올리기
# 5. GitHub에서 Pull Request 생성
```

## Pull Request 열기 전 체크리스트

- [ ] 변경한 파일이 의도한 것만 들어 있는가 (`git status`)
- [ ] 커밋 메시지만 봐도 무엇을 바꿨는지 알 수 있는가
- [ ] README나 관련 문서에 빠진 내용이 없는가
- [ ] 최신 main 내용을 반영했는가 (`git pull origin main`)
- [ ] PR 제목과 설명에 변경 이유를 적었는가

## 참고

- 기본 브랜치는 `main`입니다.
- 커밋 메시지는 명령형으로 짧게 쓰는 것이 관례입니다. (예: `Add checklist`)

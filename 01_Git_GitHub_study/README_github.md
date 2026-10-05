# DataCenter_Space
> 20261005
> This place is the one where I collect all of my data for the space
> # 참고 사이트 :  나의 구글 독스   
https://docs.google.com/document/d/1obRG5PS62xQWqpNwDPsEOCrKuTshdXSNZVx93ZWdBbg/edit?tab=t.wk8wddcue7an

#### 브랜치는 main , dev , project 순으로 관리를 한다.
> main 브랜치는 배포용
> dev 는 개발용
> project는 테스트 용



#### local : 
> git config  
> git status   
> git add .  
> git commit -m "message"  
> git push or git push --set-upstream origin main or dev  
> git clone "git address"  
> git fetch origin main or dev  
> git pull --rebase origin main or dev  

#### github
##### GitHub(origin)에 있는 원격 브랜치 목록을 봅니다.
> git branch -r


### github에서 pull request 해서 merge

### 이곳에서 행하는 모든 데이타 행위는 local repository에서 fetch 가 되어서 git full 되어야 한다. 

질문    : 만일 gibhub 의 dev 에서 수정파일이 있고. 내 pc의 gib repository에서도 수정이 있다면 제가 어떤 것을 해야 하나요?
AI 답변 : 
        GitHub의 dev 브랜치와 내 PC의 저장소 양쪽에 수정사항이 있다면, 
        먼저 내 PC의 수정사항을 안전하게 보관한 뒤 원격 dev 변경사항을 가져와 합치고, 마지막에 push하면 됩니다.
        로컬 수정사항이 아직 커밋되지 않았다면 커밋하거나 임시 보관(stash)하세요. 커밋하는 방법은 다음과 같습니다.

git status
# 현재 브랜치와 수정 파일을 확인합니다.
git add .
# 수정한 파일을 커밋 대상으로 지정합니다.
git commit -m "로컬 변경사항 저장"
# 로컬 변경사항을 커밋으로 저장합니다.
그다음 dev 브랜치에서 원격 변경사항을 반영합니다.
git switch dev
# 로컬 dev 브랜치로 이동합니다.

git pull --rebase origin dev
# GitHub의 dev 변경사항을 가져와 로컬 커밋을 그 위에 다시 적용합니다.
충돌이 생기면 충돌 표시가 있는 파일을 수정하고 아래 명령을 실행하세요.
git add <충돌을 해결한 파일>
# 충돌을 해결한 파일을 표시합니다.

git rebase --continue
# rebase를 이어갑니다.
rebase가 끝나면 원격 저장소에 올립니다.
git push origin dev
# 로컬 dev의 변경사항을 GitHub dev에 올립니다.
로컬 수정사항이 아직 커밋되지 않았다면 git pull --rebase 전에 git stash push -m "작업 임시 보관"으로 보관하고, pull 후 git stash pop으로 다시 적용할 수도 있습니다. 다만 충돌이 나면 어느 쪽 변경을 남길지 직접 확인해야 합니다. git push --force는 원격 기록을 덮어쓸 수 있으니, 특별히 필요한 상황이 아니라면 사용하지 마세요.
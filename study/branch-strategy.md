# 브랜치 전략

## 목적

- 협업을 위해서는 git을 반 필수적으로 사용하게 됨
- 하지만 공통의 규칙이 없다면 git은 많은 충돌이 생기게 될 수밖에 없음
- 따라서 이렇게 해보는 것이 어떨까? 하는 일종의 방법론들이 등장
- 가장 대표적인 것은 git flow, github flow

## git flow

- master, develop, feature, release, hotfix 의 5개 브랜치를 사용
- 항시 유지되는 master, develop 브랜치와, 목적에 따라 임시로 생성되는 feature, release, hotfix로 구분
- 규칙이 비교적 복잡하지만, 그렇기 때문에 규모가 큰 프로젝트에는 적합함

## github flow

- 항상 배포 상태를 유지하는 master, 개발이 진행되는 feature 두 개의 브랜치로만 구분
- 따라서 자동 배포 환경을 구축해 놓는 것이 필요함
- 바로 배포가 되기 때문에 master로 merge되기 전 PR을 신중하게 검토해야함
- 잦은 수정과 배포가 이루어지는 가벼운 프로젝트에 적합함

## 기타

- 이 외에도 gitlab flow 도 존재
- 사실상 방법론이기 때문에 정답은 없고, 상황에 맞게 수정해서 사용하는 것이 중요함!

## Reference

- 우린 Git-flow를 사용하고 있어요(https://techblog.woowahan.com/2553/)
- git 브랜치 전략에 대해서(https://tecoble.techcourse.co.kr/post/2021-07-15-git-branch/)
- 깃 브랜치 전략(https://hyeon9mak.github.io/git-branch-strategy/)

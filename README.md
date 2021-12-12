git init && git add . && git commit -m "first commit" && git branch -M master && git remote add origin https://github.com/hwalanlee/asg-switch.git && git push -u origin master

git add . && git commit -m "first commit" && git push -u origin master


- 동일한 인프라에 여러 개의 cdk stack을 사용할 수 없다면, sdk로 변경해야
    - 동일한 cdk stack을 쓰려면 어떻게 해야 할까


- 실행 순서
    - packer-lc - 첫 번째 이미지 만들기
    - ckd-infra - 인프라 만들기, 첫 번째 asg 포함
    - packer-lc - 두 번째 이미지 만들기
    - cdk-lc - 두 번째 asg 만들기
    - ami-switch - 두 번째 asg로 lb 조정
- 남은 작업
    - jenkins pipeline
    - CodeDeploy로 코드만 배포하기 위한 set 만든 후
    - stack 통합하기
    - 표준화 작업 - 이미지 배포 세트, 코드 배포 세트
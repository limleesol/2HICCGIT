# 2HICCGIT

Git의 목적 : version, backup, collaborate 관리

local 저장소 : working directory(실제 파일), index(준비 영역), head(최종 확정본,commit)

1. VS code
    1) ctrl + ~ = terminal 이 열린다.

    2) git init : 새로운 git 저장소 만들어진다. 
        -> git의 관리 대상으로 설정된다. git에 변경사항이 저장된다. 

    3) git status : git의 관리 대상이 아닌 것(untracted files)이 표시 된다. 
        -해결법 
             (1) git add -a : 모든 것(all)을 git index에 추가
                    or git add __ : 해당 사항을 git index에 추가
             (2) git commit -m "확정본(commit)에 대한 설명" : index에 추가된 것들을 확정(commit)
    
    4) git log : commit 한 것들에 관한 정보를 보여준다. 

    5) Reset, Revert
        (1) git reset ______ --hard : 돌아가고자 하는 commit의 log 앞 6자리 입력 시 돌아가며,  해당 commit 이후 수정사항에 관한 내용은 삭제 된다. 
        (2) git revert _______ : 취소하고자 하는 commit의 log 앞 6자리 입력 시 그 직전으로 돌아가며, 해당 commit 부터의 내용도 보존된다. 

    6) Branch 생성과 삭제
        (1) git branch _____ : ___이라는 이름의 가지(branch)를 만든다.
                -> 기존 branch와 새로만든 ____이 존재
        (2) git checkout _____ : ____branch로 넘어간다.
        (3) git checkout -b _______ : ____branch를 만들고 동시에 넘어간다.
        (4) git branch -d _____ : ____branch를 삭제한다.
    
    7) Branch 활용
        (1) git merge _____ : ____branch의 내용을 가져온다.
        (2) git log --graph --all --decorate : 모든 branch의 정보를 확인할 수 있다.  
        *merge 하려는 branch의 파일과 사용하려는 branch의 파일의 같은 부분이 conflict 될 경우 오류 발생 -> 둘 중 하나 삭제해서 해결한다.
        (3) git rebase ____ : 여러 가지들을 한 갈래로 정리한다.
        
    8) 원격 저장소 추가 
        (1) git clone _____ : git의 repository clone URL을 입력시 해당 폴더에 URL의 원격저장소의 내용을 다운로드 받는다. 외부에서 원격 저장소에 접속한 것이기에 CD.\_불러온 폴더명_\을 입력해서 해당 폴더 안에 들어가야 한다.
        (2) git remote add _로컬저장소이름설정_ _원격저장소URL_ : 로컬저장소를 원격 저장소와 연결
        (3) git remote : 원격 repository로 설정 된 것이 무엇인지 나온다.
        (4) git push _원격 repository명_ _Brnach 명_ : 로컬 저장소 HEAD 안의 commit된 내용을 원격 repository로 보낸다.

    9)  로컬 저장소 갱신
        (1) git fetch : 다른 컴퓨터에서 commit이 변경되었는지 확인할 수 있다.
        (2) git pull _원격명_ _브랜치명_ : 변경된 사항을 다운받을 수 있다.

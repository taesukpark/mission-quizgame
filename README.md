# mission-quizgame
Python과 Git을 이용한 나만의 퀴즈게임 프로그림 만들기


## 1. 프로젝트 개요
```
Python 기본 문법과 역할별로 구조화한 클래스(객체 지향)로 프로그래밍하여 터미널 기반에서 동작되는 퀴즈 게임입니다.

사용자는 메뉴를 통해 퀴즈를 풀고, 새로운 퀴즈를 등록하고, 퀴즈 목록을 확인하고, 최근 점수와 최고 점수를 확인할 수 있습니다.

프로그램 종료 후에도 퀴즈 데이터와 점수 데이터가 유지되도록 `state.json` 파일에 데이터를 저장합니다.

```

## 2. 퀴즈 주제 선정 이유
```
누구라도 주제를 선택하여 가볍게 퀴즈풀거나 새로운 퀴즈를 등록할 수 있게 하여 부담없이 즐길 수 있도록 구성했습니다.
5가지 카테고리로 구성 : 과학, 수학, 역사, 지리. 파이썬)
```

## 3. 실행 방법
```
터미널 창에서 python quizgame.py 실행
PS C:\Users\lucidts1102\mission2> python quizgame.py

==============================
     파이썬 퀴즈 게임
==============================
1. 퀴즈 풀기
2. 퀴즈 등록
3. 퀴즈 목록
4. 점수 확인
5. 종료
==============================
메뉴 선택: 
```

## 4. 기능 목록
```
퀴즈 풀기
최고 기록 확인
새로운 퀴즈 등록
퀴즈 목록 확인
프로그램 종료
JSON 파일을 통한 데이터 저장 및 불러오기
프로그램 재실행 후에도 퀴즈와 점수 유지
```

## 5. 파일 구조
```
mission2
├── quizgame.py
├── state.json
├── README.md
└── .gitignore
```

## 6. 데이터 파일 설명(state.json 등)
```
state.json 파일은 프로그램 실행 중 생성되거나 수정되는 데이터 파일입니다.

quizzes: 퀴즈 데이터와 best_score: 최고 점수를 저장하는 기능이 구현되어 있습니다.(UTF-8 인코딩)

데이터 영속성 유지: 프로그램이 종료되어도 등록된 퀴즈와 최고 점수 기록이 사라지지 않도록 로컬에 저장합니다.

설정 및 상태 관리: class QuizDate 구조 정의를 통해 퀴즈data와 사용자의 퀴즈상황(최고 점수) state.jsond으로 통합 관리하는 중앙 저장소 역할을 합니다.

게임이 종료시 quizzes와 best_score를 state.json에 저장하여 다음 게임이용시 저장된 데이터를 이용할 수 있도록 합니다.
| index                  | Type    | Description 
| `quizzes`              | Array   | 퀴즈 객체들의 리스트 
| `quizzes[].category`   | String  | 퀴즈의 분류 
| `quizzes[].question`   | String  | 문제 내용   
| `quizzes[].options`    | Array   | 4개의 문자열로 구성된 선택지 리스트 
| `quizzes[].answer`     | Integer | 정답 번호 (1~4) 
| `high_scores`          | Object  | 카테고리별 최고 점수
```

## 7. 제출물

```
7-1. GitHub 저장소 URL : https://github.com/taesukpark/mission-quizgame.git
```
```
7-2. 개발 환경 설정 스크린샷(VSCode, Python버전, Git 설정)
* VSCode
PS C:\Users\lucidts1102> code --version
1.144.1
261c84cb1eddf11235f9e2c921425e9663fbe556
x64

* Python버전
PS C:\Users\lucidts1102> python --version
Python 3.14.9

*Git 설정
PS C:\Users\lucidts1102> git config --list
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=schannel
core.autocrlf=true
core.fscache=true
core.symlinks=false
pull.rebase=false
credential.helper=manager
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=master
```
```
7-3. 프로그램 실행 결과 스크린샷(퀴즈 추가, 목록, 풀기 및 점수)
```
```
PS C:\Users\lucidts1102\mission2> python quizgame.py
* quizgame.py프로그램실행중 ctrl+C로 빠져나올경우
==============================
     파이썬 퀴즈 게임
==============================
1. 퀴즈 풀기
2. 퀴즈 등록
3. 퀴즈 목록
4. 점수 확인
5. 종료
==============================
메뉴 선택:
```
```
*ctrl+C로 강제 중단후 메시지
⚠️ 사용자 중단(Ctrl+C/EOF)이 감지되었습니다.
현재까지의 데이터를 안전하게 저장하고 종료합니다...
PS C:\Users\lucidts1102\mission2> 
```
```
* 퀴즈 목록 조회
==============================
     파이썬 퀴즈 게임
==============================
1. 퀴즈 풀기
2. 퀴즈 등록
3. 퀴즈 목록
4. 점수 확인
5. 종료
==============================
메뉴 선택: 3

--- 📋 퀴즈 목록 ---

[1번 문제]
카테고리: 과학
질문: 물은 섭씨 몇 도에서 끓나요?
보기: 1)50도 2)80도 3)100도 4)120도
정답: 3번

[2번 문제]
카테고리: 수학
질문: 다음 중에 다각형이 아닌 것은?
보기: 1)사각형 2)원 3)삼각형 4)마름모
정답: 2번

[3번 문제]
카테고리: 역사
질문: 조선의 제1대 왕은 누구인가요?
보기: 1)세종대왕 2)태조 이성계 3)정조 4)광해군
정답: 2번

[4번 문제]
카테고리: 지리
질문: 대한민국의 수도는 어디인가요?
보기: 1)부산 2)인천 3)대구 4)서울
정답: 4번

[5번 문제]
카테고리: 파이썬
질문: 조건문 명령어가 아닌 것은?
보기: 1)if 2)else 3)elif 4)input
정답: 4번

✅ 총 5개의 퀴즈가 조회되었습니다.
```
```
* 퀴즈 추가
PS C:\Users\lucidts1102\mission2> python quizgame.py

==============================
     파이썬 퀴즈 게임
==============================
1. 퀴즈 풀기
2. 퀴즈 등록
3. 퀴즈 목록
4. 점수 확인
5. 종료
==============================
메뉴 선택: 2

--- ➕ 새 퀴즈 등록 ---
카테고리를 입력하세요 (예: 과학, 수학, 역사, 지리, 파이썬): 역사
질문을 입력하세요: 신라의 수도는?
보기 1번을 입력하세요: 서울
보기 2번을 입력하세요: 광주
보기 3번을 입력하세요: 경주
보기 4번을 입력하세요: 진주
정답 번호를 입력하세요 (1-4): 3

✅ 퀴즈가 성공적으로 등록되고 파일에 저장되었습니다!
```
```
* 퀴즈 풀기 및 점수 확인
==============================
     파이썬 퀴즈 게임
==============================
1. 퀴즈 풀기
2. 퀴즈 등록
3. 퀴즈 목록
4. 점수 확인
5. 종료
==============================
메뉴 선택: 1

=== 파이썬 퀴즈 게임 ===
1. 퀴즈 풀기
2. 최고 기록 확인
3. 새로운 퀴즈 등록
4. 퀴즈 목록 확인
5. 종료
메뉴를 선택하세요: 1

🚀 퀴즈 게임을 시작합니다!

[문제] 물은 섭씨 몇 도에서 끓나요?
1) 50도
2) 80도
3) 100도
4) 120도
정답 번호를 입력하세요: 3
✅ 정답입니다!

[문제] 다음 중에 다각형이 아닌 것은?
1) 사각형
2) 원
3) 삼각형
4) 마름모
정답 번호를 입력하세요: 2
✅ 정답입니다!

[문제] 조선의 제1대 왕은 누구인가요?
1) 세종대왕
2) 태조 이성계
3) 정조
4) 광해군
정답 번호를 입력하세요: 2
✅ 정답입니다!

[문제] 대한민국의 수도는 어디인가요?
1) 부산
2) 인천
3) 대구
4) 서울
정답 번호를 입력하세요: 4
✅ 정답입니다!

[문제] 조건문 명령어가 아닌 것은?
1) if
2) else
3) elif
4) input
정답 번호를 입력하세요: 4
✅ 정답입니다!

[문제] 신라시대의 여왕이 아닌 인물은?
1) 선덕여왕
2) 측천무후
3) 진덕여왕
4) 진성여왕
정답 번호를 입력하세요: 2
✅ 정답입니다!

[문제] 신라의 수도는?
1) 서울
2) 광주
3) 경주
4) 진주
정답 번호를 입력하세요: 3
✅ 정답입니다!

🎮 게임 종료! 당신의 점수는 70점입니다.
🎊 축하합니다! 최고 기록을 경신했습니다! (50 -> 70)
```

```
7-4. git log --oneline --graph 결과를 스크린샷

PS C:\Users\lucidts1102\mission2> git log
commit ef6acda0db02943839d37c9138b7058c1cbc2f38 (HEAD -> master)
Author: unknown <lucidts1102@gnia.kr>
Date:   Sun Nov 15 19:00:04 2026 +0900
```

```
7-5. git clon으로 Github에서 만든 포로젝트 내 컴퓨터로 가져오기 결과
PS C:\Users\lucidts1102\mission2> git clone https://github.com/taesukpark/mission-quizgame.git
Cloning into 'mission-quizgame'...
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (4/4), done.
```

## 8. git commit 10회 이상 하기(커밋 메시지에 변경 요약 포함)

```
8-1. 메뉴기능 완성 후 git commit 실행하기
PS C:\Users\lucidts1102\mission2> git commit -m "퀴즈 메뉴 구성 완성"
[master (root-commit) ef6acda] 퀴즈 메뉴 구성 완성
 Committer: unknown <lucidts1102@gnia.kr>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly. Run the
following command and follow the instructions in your editor to edit
your configuration file:

    git config --global --edit

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 1 file changed, 53 insertions(+)
 create mode 100644 quizgame.py
PS C:\Users\lucidts1102\mission2> git config --global user.name "taesukpark" 
PS C:\Users\lucidts1102\mission2> git config --global user.email "lucidts@hanmail.net"
PS C:\Users\lucidts1102\mission2> git log
commit ef6acda0db02943839d37c9138b7058c1cbc2f38 (HEAD -> master)
Author: unknown <lucidts1102@gnia.kr>
Date:   Sun Nov 15 19:00:04 2026 +0900

    퀴즈 메뉴 구성 완성
```
```
8-2. Quiz 클래스 작성후 커밋한다.
PS C:\Users\lucidts1102\mission2> git commit -m "Quiz 클래스 작성"    
[master 8c7ccc8] Quiz 클래스 작성
 2 files changed, 1 insertion(+)
 create mode 160000 mission-quizgame
 create mode 100644 "\354\212\244\355\201\254\353\246\260 \354\203\267/GitHub\355\231\224\353\251\264/new_repository.png"

PS C:\Users\lucidts1102\mission2> git commit -m "Quiz 클래스 재작성(인스턴 생성)"  
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   quizgame.py

no changes added to commit (use "git add" and/or "git commit -a")
```

```
8-3. 기본 퀴즈 데이터 작성 후 커밋한다.
PS C:\Users\lucidts1102\mission2> git commit -m "기본 퀴즈 데이터 작성"           
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   quizgame.py

no changes added to commit (use "git add" and/or "git commit -a")
```
```
8-4. main 브랜치 이외의 추가 브랜치를 생성하고 퀴즈풀기 코딩작업한다.
   git checkout -b 새브랜치명 : 새 브랜치 생성하면서 새브랜치로 이동
PS C:\Users\lucidts1102\mission2> git checkout -b feature/quiz-play
Switched to a new branch 'feature/quiz-play'
PS C:\Users\lucidts1102\mission2> git branch
* feature/quiz-play 현재 위치된 브랜치명에 *가 있음
  master
PS C:\Users\lucidts1102\mission2> git status
On branch feature/quiz-play
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   quizgame.py 빨간색

no changes added to commit (use "git add" and/or "git commit -a")
PS C:\Users\lucidts1102\mission2> git add .
PS C:\Users\lucidts1102\mission2> git status
On branch feature/quiz-play 
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   quizgame.py 초록색
PS C:\Users\lucidts1102\mission2> git commit -m "feature: 퀴즈 풀기 기능 구현 및 입력 예외 처리 추가"
[master 0836e52] feature: 퀴즈 풀기 기능 구현 및 입력 예외 처리 추가
 1 file changed, 107 insertions(+), 8 deletions(-)
```
```
8-5. 퀴즈풀기(브랜치 활용) 기능 완성후 커밋하고 master 브랜치로 병합
   git checkout main : 해당 브랜치에서 빠져나와 master으로 이동
PS C:\Users\lucidts1102\mission2> git checkout master
M       quizgame.py
Switched to branch 'master'

   git merge 새브랜치명 : master에 새브랜치의 내용을 합치는 실행
PS C:\Users\lucidts1102\mission2> git merge feature/quiz-play
Already up to date.
```
```
8-6. 퀴즈 추가 기능 완성후 commit한다. (예 Feat : 퀴즈 출제 기능 구현)
PS C:\Users\lucidts1102\mission2> git commit -m "퀴즈 추가 출제기능 반영"                                                 
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        "1. git commit 10\355\232\214 \354\235\264\354\203\201 \355\225\230\352\270\260(\354\273\244\353\260\213 \353\251\224\354\213\234\354\247\200\354\227\220 \353\263\200\352\262\275.txt"

nothing added to commit but untracked files present (use "git add" to track)
PS C:\Users\lucidts1102\mission2> git branch
  feature/quiz-play
* master
```
```
8-7. 퀴즈 목록 기능 완성 후 커밋한다.
PS C:\Users\lucidts1102\mission2> git commit -m "퀴즈 목록 확인 기능 추가"
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        "1. git commit 10\355\232\214 \354\235\264\354\203\201 \355\225\230\352\270\260(\354\273\244\353\260\213 \353\251\224\354\213\234\354\247\200\354\227\220 \353\263\200\352\262\275.txt"

nothing added to commit but untracked files present (use "git add" to track)
```
```
8-8. 점수확인 기능 완성 후 커밋한다.(예 Fix : 점수 계산 오류 수정)
PS C:\Users\lucidts1102\mission2> git commit -m "점수 확인 기능 추가"     
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        "1. git commit 10\355\232\214 \354\235\264\354\203\201 \355\225\230\352\270\260(\354\273\244\353\260\213 \353\251\224\354\213\234\354\247\200\354\227\220 \353\263\200\352\262\275.txt"

nothing added to commit but untracked files present (use "git add" to track)
```
```
8-9. QuizGame 클래스 작성후 git commit (예 Refacto : QuizGame 책임분리)
PS C:\Users\lucidts1102\mission2> git commit -m "클래스 구조 정리"   
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        "1. git commit 10\355\232\214 \354\235\264\354\203\201 \355\225\230\352\270\260(\354\273\244\353\260\213 \353\251\224\354\213\234\354\247\200\354\227\220 \353\263\200\352\262\275.txt"

nothing added to commit but untracked files present (use "git add" to track)
```
```
8-10. 파일 입출력 기능 완성 후 commit (퀴즈게임 프로젝트 코드가 GitHub에 업로드되어 있다.)
PS C:\Users\lucidts1102\mission2> git commit -m "Python Quiz Game 완성"                              
[master 2f80825] Python Quiz Game 완성
 3 files changed, 987 insertions(+), 19 deletions(-)
 create mode 100644 "1. git commit 10\355\232\214 \354\235\264\354\203\201 \355\225\230\352\270\260(\354\273\244\353\260\213 \353\251\224\354\213\234\354\247\200\354\227\220 \353\263\200\352\262\275.txt"
 create mode 100644 state.json
PS C:\Users\lucidts1102\mission2> git log
commit 2f80825bea33ab1ed6618562c2c06dcbbd5ac967 (HEAD -> master)
Author: taesukpark <lucidts@hanmail.net>
Date:   Mon Nov 16 04:38:36 2026 +0900

    Python Quiz Game 완성
```

## 9. Git 저장소 복제 실습

clone과 pull을 각각 1회 이상 사용한 기록이 있다.

```
9-1.git clone URL(GitHub 주소) 미션수행 저장소를 clone하여 별도의 로컬 디렉터리에 복제한다.

복제된 저장소에서 간단한 변경(예:README.md에 한 줄 추가)을 하고 commit하고 push한다.
PS C:\Users\lucidts1102\mission2> git push -u origin main
info: please complete authentication in your browser...
To https://github.com/taesukpark/mission-quizgame.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/taesukpark/mission-quizgame.git'
hint: Updates were rejected because the remote contains work that you do not
hint: have locally. This is usually caused by another repository pushing to
hint: the same ref. If you want to integrate the remote changes, use
hint: 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```

```
9-2. 기존 로컬 작업 디렉터리에서 pull로 변경사항을 가져온다.

```

```
9-3. git pull 받은 내용이 정상적으로 반영되었는지 확인한다.

```

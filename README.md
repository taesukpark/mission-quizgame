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

⚠️ 사용자 중단(Ctrl+C/EOF)이 감지되었습니다.
현재까지의 데이터를 안전하게 저장하고 종료합니다...
PS C:\Users\lucidts1102\mission2> 

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
메뉴 선택: 

⚠️ 사용자 중단(Ctrl+C/EOF)이 감지되었습니다.
현재까지의 데이터를 안전하게 저장하고 종료합니다...
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
4. git log --oneline --graph 결과를 스크린샷

```
```
프로젝트 개요
퀴즈 주제 선정이유
실행방법 (예 python main.py)
기능 목록(퀴즈 풀기/ 추가/ 목록/점수)
파일 구조
데이터 파일 설명(state.json 경로/역할/필드구조/스키마 등)
의 항목을 포함하여 작성후 Git 최종 push한다.
```
```
< git clon으로 Github에서 만든 포로젝트 내 컴퓨터로 가져오기 결과 >
PS C:\Users\lucidts1102\mission2> git clone https://github.com/taesukpark/mission-quizgame.git
Cloning into 'mission-quizgame'...
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (4/4), done.
```


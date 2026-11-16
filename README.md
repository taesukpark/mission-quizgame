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

import json
import os
import random
import sys


class Quiz:
    
    def __init__(self, category, question, choices, answer):
        """
        category : 퀴즈 주제
        question : 문제
        choices  : 선택지 4개 리스트
        answer   : 정답 번호 (1~4)
        """
        if not isinstance(choices, list) or len(choices) != 4:
            raise ValueError("선택지는 반드시 4개여야 합니다.")

        if not isinstance(answer, int) or answer not in [1, 2, 3, 4]:
            raise ValueError("정답 번호는 1~4 중 하나여야 합니다.")

        self.category = category
        self.question = question
        self.choices = choices
        self.answer = answer
    
    def print_quiz(self):
        """퀴즈 출력"""
        print(f"\n[퀴즈 주제: {self.category}]")
        print(f"문제: {self.question}")
        for i, choice in enumerate(self.choices, start=1):
            print(f"{i}. {choice}")

    def check_answer(self, input_answer):
        """정답 확인"""
        return input_answer == self.answer

    def to_dict(self):
        """객체 -> 딕셔너리 변환 (JSON 저장용)"""
        return {
            "category": self.category,
            "question": self.question,
            "choices": self.choices,
            "answer": self.answer
        }

    @classmethod
    def from_dict(cls, data):
        """딕셔너리 -> Quiz 객체 변환"""
        return cls(
            category=data["category"],
            question=data["question"],
            choices=data["choices"],
            answer=data["answer"]
        )

class QuizData:
    
    def __init__(self, file_path="state.json"):
        self.file_path = file_path
        # 기본 5가지 주제별 퀴즈 데이터 (선택지 4개 방식)
        self.default_data = {
            "quizzes": [
                {"category": "과학", "question": "물은 섭씨 몇 도에서 끓나요?", "choices": ["50도", "80도", "100도", "120도"], "answer": 3},
                {"category": "수학", "question": "다음 중에 다각형이 아닌 것은?", "choices": ["사각형", "원", "삼각형", "마름모"], "answer": 2},
                {"category": "역사", "question": "조선의 제1대 왕은 누구인가요?", "choices": ["세종대왕", "태조 이성계", "정조", "광해군"], "answer": 2},
                {"category": "지리", "question": "대한민국의 수도는 어디인가요?", "choices": ["부산", "인천", "대구", "서울"], "answer": 4},
                {"category": "파이썬", "question": "조건문 명령어가 아닌 것은?", "choices": ["if", "else", "elif", "input"], "answer": 4}
            ],
            "best_score": 0
        }
        # 데이터 로드 및 객체 변환
        raw_data = self.load_data()        
        try:
            self.quizzes = [Quiz.from_dict(q) for q in raw_data["quizzes"]]
            if not isinstance(raw_data["best_score"], int):
                raise ValueError("best_score는 정수여야 합니다.")
            self.best_score = raw_data["best_score"]
        except (KeyError, TypeError, ValueError):
            print("\n⚠️ 퀴즈 데이터 구조가 올바르지 않습니다. 기본 데이터로 복구합니다.")
            raw_data = self.default_data
            self.quizzes = [Quiz.from_dict(q) for q in raw_data["quizzes"]]
            self.best_score = raw_data["best_score"]

    def load_data(self):
        """JSON 파일 로드 및 손상시 복구 로직"""
        if not os.path.exists(self.file_path):
            return self.default_data
        
        try:
            with open(self.file_path, 'r', encoding='utf-8') as f:
                loaded_data = json.load(f)

            if not isinstance(loaded_data, dict):
                raise ValueError("데이터는 딕셔너리 형태여야 합니다.")

            if "quizzes" not in loaded_data or "best_score" not in loaded_data:
                raise ValueError("데이터 구조 불일치")

            return loaded_data

        except (json.JSONDecodeError, IOError, ValueError, TypeError):
            print("\n⚠️ 데이터 파일이 없거나 손상되었습니다. 기본 데이터로 시작합니다.")
            return self.default_data

    def save_data(self):
        """데이터를 JSON 파일로 저장"""
        try:
            # Quiz 객체들을 다시 딕셔너리로 변환하여 저장
            save_dict = {
                "quizzes": [q.to_dict() for q in self.quizzes],
                "best_score": self.best_score
            }
            with open(self.file_path, 'w', encoding='utf-8') as f:
                json.dump(save_dict, f, ensure_ascii=False, indent=4)
        except IOError as e:
            print(f"\n❌ 파일 저장 중 오류 발생: {e}")

class QuizGame:

    def __init__(self, manager):
        self.manager = manager

    def get_input(self, prompt, is_num=False, min_v=None, max_v=None, allow_cancel=False):
        """강화된 입력 검증 함수 (공백제거, 숫자변환, 범위체크, 빈입력체크, 취소기능)"""
        while True:
            user_input = input(prompt).strip()
            if not user_input:
                print("⚠️ 빈 입력은 허용되지 않습니다. 다시 입력해주세요.")
                continue

            if allow_cancel and user_input.lower() == "취소":
                return None

            if is_num:
                try:
                    user_input = int(user_input)
                    if min_v is not None and user_input < min_v:
                        print(f"⚠️ {min_v} 이상의 숫자를 입력해주세요.")
                        continue
                    if max_v is not None and user_input > max_v:
                        print(f"⚠️ {max_v} 이하의 숫자를 입력해주세요.")
                        continue
                    return user_input
                except ValueError:
                    print("⚠️ 숫자만 입력 가능합니다. 다시 입력해주세요.")
            else:
                return user_input

    def run(self):
        """메인 메뉴 루프"""
        
        while True:
            print("\n=== 파이썬 퀴즈 게임 ===")
            print("1. 퀴즈 풀기")
            print("2. 최고 기록 확인")
            print("3. 새로운 퀴즈 등록")
            print("4. 퀴즈 목록 확인")
            print("5. 종료")
            
            choice = self.get_input("메뉴를 선택하세요: ", is_num=True, min_v=1, max_v=5)
            
            if choice == 1:
                self.play_quiz()
            elif choice == 2:
                self.show_best_score()
            elif choice == 3:
                self.add_new_quiz()
            elif choice == 4:
                self.show_quiz_list()
            elif choice == 5:
                self.manager.save_data() # 종료 전 저장
                print("게임을 종료합니다. 안녕!")
                break
            else:
                print("잘못된 선택입니다. 다시 입력해주세요.")

    def play_quiz(self):
        """실제 퀴즈 진행 로직"""
        quizzes = self.manager.quizzes[:]
        if not quizzes:
            print("등록된 퀴즈가 없습니다. 퀴즈를 먼저 등록해 주세요.")
            return

        quizzes = self.manager.quizzes[:]
        random.shuffle(quizzes)  # 문제 순서 랜덤화

        print("\n🚀 퀴즈를 시작합니다!")
        score = 0

        for quiz in quizzes:
            quiz.print_quiz()
            while True:
                try:
                    user_input = int(input("정답 번호를 입력하세요 (1-4): "))
            
                    if user_input not in [1, 2, 3, 4]:
                        print("⚠️ 1번부터 4번 사이의 번호를 입력해주세요.")
                        continue  # while문의 처음으로 돌아가 다시 입력받음
            
                    # 정답 확인 로직
                    if quiz.check_answer(user_input):
                        print("✅ 정답입니다!")
                        score += 10
                    else:
                        print(f"❌ 틀렸습니다. 정답은 {quiz.answer}번입니다.")
            
                    break  # 정답이든 오답이든 유효한 입력이었으므로 while 루프 탈출 -> 다음 문제로!

                except ValueError:
                    # 숫자가 아닌 문자를 입력했을 때
                    print("⚠️ 숫자만 입력 가능합니다. 다시 입력해주세요.")
                    # 여기서 break를 안 썼기 때문에 다시 위로 올라가 input을 실행합니다.

        print(f"\n🎊 게임 종료! 당신의 점수는 {score}점입니다.")
        
        # 최고 기록 갱신 확인
        if score > self.manager.best_score:
            print("✨ 축하합니다! 최고 기록을 경신했습니다!")
            self.manager.best_score = score
            self.manager.save_data()

    def show_best_score(self):
        """2. 최고 점수를 확인하는 메서드"""
        print("\n=== 🏆 최고 기록 확인 ===")
        
        # 아직 퀴즈를 풀지 않은 경우 처리 (최고 점수가 0인 경우)
        if self.manager.best_score == 0:
            print("아직 퀴즈를 푼 기록이 없습니다. 첫 번째 도전에 나서보세요!")
        else:
            print(f"현재 최고 기록은 {self.manager.best_score}점입니다. 대단해요! 👍")

    def play_quiz(self):
        """1. 퀴즈를 풀고 점수를 갱신하는 메서드"""
        if not self.manager.quizzes:
            print("\n❌ 등록된 퀴즈가 없습니다. 퀴즈를 먼저 등록해주세요.")
            return

        print("\n🚀 퀴즈 게임을 시작합니다!")
        current_score = 0
        
        # 퀴즈 풀기 로직 (예시: 모든 퀴즈를 순회)
        for quiz in self.manager.quizzes:
            print(f"\n[문제] {quiz.question}")
            for i, choice in enumerate(quiz.choices, 1):
                print(f"{i}) {choice}")
            
            answer = input("정답 번호를 입력하세요: ").strip()
            if answer == str(quiz.answer):
                print("✅ 정답입니다!")
                current_score += 10  # 문제당 10점 가정
            else:
                print(f"❌ 틀렸습니다. 정답은 {quiz.answer}번입니다.")

        print(f"\n🎮 게임 종료! 당신의 점수는 {current_score}점입니다.")

        # --- 최고 점수 비교 및 갱신 로직 ---
        if current_score > self.manager.best_score:
            print(f"🎊 축하합니다! 최고 기록을 경신했습니다! ({self.manager.best_score} -> {current_score})")
            # 요청하신 대로 데이터 저장
            self.manager.best_score = current_score
            self.manager.save_data()
        else:
            print(f"아쉽네요! 최고 기록({self.manager.best_score}점) 경신에 실패했습니다.")

    def add_new_quiz(self):
        print("\n--- ➕ 새 퀴즈 등록 ---")
        
        # 1. 카테고리 입력 및 검증
        category = input("카테고리를 입력하세요 (예: 과학, 수학, 역사, 지리, 파이썬): ").strip()
        if not category:
            print("⚠️ 카테고리는 비어있을 수 없습니다.")
            return

        # 2. 질문 입력 및 검증
        question = input("질문을 입력하세요: ").strip()
        if not question:
            print("⚠️ 질문은 비어있을 수 없습니다.")
            return

        # 3. 보기 4개 입력 및 검증
        choices = []
        for i in range(1, 5):
            choice = input(f"보기 {i}번을 입력하세요: ").strip()
            if not choice:
                print(f"⚠️ 보기 {i}번이 입력되지 않았습니다.")
                return
            choices.append(choice)

        # 4. 정답 번호 입력 및 검증
        try:
            answer_input = input("정답 번호를 입력하세요 (1-4): ").strip()
            answer = int(answer_input)
            if answer not in [1, 2, 3, 4]:
                print("⚠️ 정답은 1번에서 4번 사이여야 합니다.")
                return
        except ValueError:
            print("⚠️ 정답은 숫자(1, 2, 3, 4)로 입력해야 합니다.")
            return

        # 5. Quiz 객체 생성 및 데이터 추가
        new_quiz = Quiz(category, question, choices, answer)
        
        # QuizData의 리스트에 추가
        self.manager.quizzes.append(new_quiz)
        
        # 6. 파일에 즉시 저장 (Persistence)
        self.manager.save_data()
        
        print("\n✅ 퀴즈가 성공적으로 등록되고 파일에 저장되었습니다!")

    def show_quiz_list(self):
        #저장된 퀴즈 목록을 확인하는 메서드
        print("\n--- 📋 퀴즈 목록 ---")
        
        # 1. 퀴즈가 없는 경우 처리 (요청하신 핵심 기능)
        if not self.manager.quizzes:
            print("❌ 등록된 퀴즈가 없습니다. 먼저 퀴즈를 등록해주세요.")
            return

        # 2. 퀴즈가 있는 경우 목록 출력
        for i, quiz in enumerate(self.manager.quizzes, 1):
            print(f"\n[{i}번 문제]")
            print(f"카테고리: {quiz.category}")
            print(f"질문: {quiz.question}")
            print(f"보기: 1){quiz.choices[0]} 2){quiz.choices[1]} 3){quiz.choices[2]} 4){quiz.choices[3]}")
            print(f"정답: {quiz.answer}번")
        
        print(f"\n✅ 총 {len(self.manager.quizzes)}개의 퀴즈가 조회되었습니다.")        

    def show_best_score(self):
        """2. 최고 점수를 확인하는 메서드"""
        print("\n=== 🏆 최고 기록 확인 ===")
        
        # 아직 퀴즈를 풀지 않은 경우 처리 (최고 점수가 0인 경우)
        if self.manager.best_score == 0:
            print("아직 퀴즈를 푼 기록이 없습니다. 첫 번째 도전에 나서보세요!")
        else:
            print(f"현재 최고 기록은 {self.manager.best_score}점입니다. 대단해요! 👍")

    def play_quiz(self):
        """1. 퀴즈를 풀고 점수를 갱신하는 메서드"""
        if not self.manager.quizzes:
            print("\n❌ 등록된 퀴즈가 없습니다. 퀴즈를 먼저 등록해주세요.")
            return

        print("\n🚀 퀴즈 게임을 시작합니다!")
        current_score = 0
        
        # 퀴즈 풀기 로직 (예시: 모든 퀴즈를 순회)
        for quiz in self.manager.quizzes:
            print(f"\n[문제] {quiz.question}")
            for i, choice in enumerate(quiz.choices, 1):
                print(f"{i}) {choice}")
            
            answer = input("정답 번호를 입력하세요: ").strip()
            if answer == str(quiz.answer):
                print("✅ 정답입니다!")
                current_score += 10  # 문제당 10점 가정
            else:
                print(f"❌ 틀렸습니다. 정답은 {quiz.answer}번입니다.")

        print(f"\n🎮 게임 종료! 당신의 점수는 {current_score}점입니다.")

        # --- 최고 점수 비교 및 갱신 로직 ---
        if current_score > self.manager.best_score:
            print(f"🎊 축하합니다! 최고 기록을 경신했습니다! ({self.manager.best_score} -> {current_score})")
            # 요청하신 대로 데이터 저장
            self.manager.best_score = current_score
            self.manager.save_data()
        else:
            print(f"아쉽네요! 최고 기록({self.manager.best_score}점) 경신에 실패했습니다.")

def main():
    manager = QuizData()
    engine = QuizGame(manager)

    try:
        while True:
            # 1. 메뉴 화면 출력
            print("\n" + "="*30)
            print("     파이썬 퀴즈 게임")
            print("="*30)
            print("1. 퀴즈 풀기")
            print("2. 퀴즈 등록")
            print("3. 퀴즈 목록")
            print("4. 점수 확인")
            print("5. 종료")
            print("="*30)

          
            # 2. 입력 검증 (공백제거, 숫자변환, 1~5 범위체크, 빈값체크 포함)
            # engine.get_input 내부에서 잘못된 입력 시 안내 메시지 후 재입력 루프가 동작함
            choice = engine.get_input("메뉴 선택: ", is_num=True, min_v=1, max_v=5)
            # 3. 메뉴 선택에 따른 기능 분기
            if choice == 1:
                engine.run()           
            elif choice == 2:
                engine.add_new_quiz()
            elif choice == 3:
                engine.show_quiz_list()
            elif choice == 4:
                engine.show_best_score()
            elif choice == 5:
                # 4. 정상 종료 처리
                print("\n데이터를 저장하고 프로그램을 종료합니다. 수고하셨습니다!")
                manager.save_data()
                break

    except (KeyboardInterrupt, EOFError):
        # 5. 강제 종료(Ctrl+C 등) 시 안전하게 저장 후 종료
        print("\n\n⚠️ 사용자 중단(Ctrl+C/EOF)이 감지되었습니다.")
        print("현재까지의 데이터를 안전하게 저장하고 종료합니다...")
        manager.save_data()
        sys.exit(0)


if __name__ == "__main__":
    main()

출처 : 한 권으로 그리는 컴퓨터 과학 로드맵 

<img width="555" alt="image" src="https://github.com/user-attachments/assets/f337f346-361e-4554-975e-6616d2089a0d">


# Computer Science (컴퓨터 과학)

컴퓨터과학이라는 학문이. 컴퓨터과학은 컴퓨터가 문제 해결에 어떻게 활용될 수 있는지 보여주었다. 결국 프로그램을 효과적으로 작성하려면 컴퓨터과학을 필수적으로 배워야 한다..

⇒  프로그래밍적 사고력을 요하는 개발자는 결국 코딩을 잘 해야하는데 이를 효과적으로 작성을 하려면 컴퓨터과학은 필수적으로 배워야 한다.

> 모든 사람은 프로그래밍을 배워야 한다. 프로그래밍은 생각하는 방법을 가르쳐주기 때문이다 - 스티브잡스
> 

## 문제 해결을 위한 기초 지식

1. 순서도와 의사코드를 이용해 생각을 나타내고 모델로 정리하기
2. 논리적으로 따져보고 옳고 그름 판단하기
3. 사물을 꼼꼼하게 세는 법
4. 확률을 안전하게 계산하기

### 1. 순서도

<img width="1211" alt="image" src="https://github.com/user-attachments/assets/0096472b-c9f2-4e78-afe1-250fc533a468">


<img width="764" alt="image" src="https://github.com/user-attachments/assets/2f02a087-2195-46ed-a78b-8490b8eebadf">


컴퓨터 프로그램도 결국 절차이기에  사람이 봐도 이해할 수 있도록 그릴수 있어야 한다. 

아래 대전제를 기억해보자 

1. 프로그램 절차의 개수는 정해져 있어야 한다.
2. 각 절차는 항상 같은 내용이어야 한다.
3. 모든 가능성을 고려해야 한다.
4. 예시는 절차를 검증하는 데 사용한다.

<img width="765" alt="image" src="https://github.com/user-attachments/assets/cda258b7-3f56-4a88-8cdc-dba258ef80ec">


vscode에서도 .excalidraw 파일로 업로드 가능하다. 

### 2. 논리적으로 따져 보기

수리논리학에서도 변수와 연산자를 이용해 사물의 타당성을 나타낸다고 한다.

eg)  “만약 수영장의 물이 따뜻하면, 나는 수영하겠다. “ 

이 명제가 타당하기 위해서는 다음 두 명제가 타당해야함.

A : 수영장의 물이 따듯하다.

B : 나는 수영한다. 

이러한 명제는 True 또는 False 둘 중하나만 될수 있다.  

참고 … fuzzy logic 이라는 개념에 의해 명확하게 정의될 수 없는 지식을 표현하는 방법이 있다고 한다. 

eg ) 참과 거짓이라는 2개의 값만을 가지는 고전적인 이진 논리에서 벗어나 참과 거짓으로 명확히 선을 그을 수 없는 예를들어 저는 키가 177~8정도 되는데 키가 큰 편일까요? 등 

이 처럼 이러한 한계점을 극복하기 위해 논리식의 값이 구간 [0, 1] 사이의 값을 가질 수 있도록 정의한다고 합니다.

위 예시의 명제에서 따듯한 물에서만 수영할 것을 뜻하는건 아닙니다. 이 명제는 차가운 수영장 물에 대해서는 아무것도 약속하지 않았다. 달리 말해 A→B는 B→A를 의미 하지 않는다. 

만약 두 명제가 서로 의존하다는 것을 나타내려면 ‘상호조건명제’를 사용하면 된다. 

A ←→ B : 만약 수영장의 물이 따뜻하다면, 그리고 오직 수영장의 물이 따뜻해야만 나는 수영하겠다.

어디까지나 상호조건명제에서만 그렇지 일반적으로 A→ B에서 B → A를 추론하지말자. 이렇게 추론하는 것을 ‘도치 (inverse)의 오류’ 리고 한다. 

이처럼 우리가 알고 있고 앞으로 학습할수 있는 여러 연산자(논리, boolean, 진리표등)을 통해 논리적인 사고력을 길러보자.

### 3. 꼼꼼하게 세는 법  & 4. 확률 계산하기

여,,,기에서는 다양한 문제에서 나올 수 있는 결과나 구성의 가짓수를 세는 수학적방법론과 확률 계산의 기본 원칙을 다루고 있어 pass 합니다. (아마 전공 과정에서는 이를 이산수학이라고 지칭하는거 같네요)

### 결론

어느 책에서 본 적이 있는데 사람이 집으로 갈 때는 무의식적으로 익숙한 주위를 보면서 가지만 컴퓨터는 도착지와 현재 위치 기반으로 어디를 어떻게 거리는 얼마나 등을 고려해야 한다 했습니다. 이처럼 컴퓨터에게 어떠한 명령을 하려면 논리를 기반으로 프로그래밍을 해야하는게 중요하며 위 4가지 속성아래 진행해야한 다는 것을 알수 있습니다. 이를 기반으로 cs study 할 때 접근하고자 합니다.

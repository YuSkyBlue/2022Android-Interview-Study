# <Coroutine 질문>

# 🍎코루틴을 왜 사용할까요?
- 하나의 쓰레드 버튼 클릭 이벤트 발생시키는 인터렉션 메인 스레드에서 작업하게 되는데 
- 메인 스레드의 부하를 막기 위해 작업을 전환하거나 생성 하게 되는데 작업 비용이 든다
- Thread 낭비가 되는 문제가 있다. 코루틴을 설정하게 되면 Thread 부하 없이 

Process -> Thread(Stack (공유 x)) -> Heap(공유가능)

# 🍎프로세스가 무엇인가요?
- 실행중에 있는 프로그램
- 하드디스크에 있는 프로그램을 실행하면 실행을 위해 메모리 할당 이루어지며. 그위에 바이너리 코드가 올라가 집니다. 이순간 부터 프로세스라 불린다.

# 🍎Thread 는 무엇인가요?
- 프로세스 내부의 작업의 흐름. 단위
- 프로세스 안에 하나 이상의 Thread가 존재한다

# 🍎코루틴을 왜 사용한다고 생각하시나요?
- 비동기적 프로그래밍을 하기 위해서 사용됩니다

# 🍎그러면 동기 / 비동기의 차이를 설명해 주실 수 있나요?
동기 
- 탑다운 순차적으로 출력 
- 현재 작업의 응답이  끝남과 동시에 다음 작업을 요청합니다
비동기
- 현재 작업의 응답이 끝나지 않은  상태에서 다음 작업을 요청 해서 진행 할 수 있습니다.
- 독립적으로 작업하는 작업 단위 

# 🍎백그라운 vs 포그라운드
포그라운드
- 사용자에 보이는 작업
백그라운
- 사용자의 눈에 보이지 않는 작업 이라고 생각합니다.

# 🍎비동기적 프로그래밍을 왜 채택했을까요?
- 결과과 주어지는 시간 동안 다른 일을 할 수 있어서 자원을 효율적으로 사용할 수 있기 때문입니다

# 🍎동시성 vs 병렬성
동시성 
- 두 개의 task 가 있을시에  잘개 쪼개어 번갈아 수행하여 수행자 입장에서 동시에 일어나는 것처럼 보임

병렬성
- 여러 작업을 한 번에 동시에 수행 

# 🍎Thread와 코루틴의  공통점 과 차이점에 대해서 설명하시오 
공통점
- 서로 ‘비동기’ 작업을 하기 위해서 사용된다는 점
- 동시성 프로그래밍을 위한 기술

차이점
- Thread는  각 태스크에 스택 메로리를 할당 받고 선점 스케줄링 방식으로 쓰레드를 수행한다
- Coroutine 은 Thread에 할당하는 것이 아닌 Object에 할당 해주며, Object를 자유롭게 스위칭함으로써  Context Switching 의 비용을 대폭 줄였다.(
- Coroutine은 콜백 기반 코드를 sequential code로 바꾸어주기 때문에 비동기 코드를 단순화할 수. 있습니다 (Suspend 내부 안에 콜백을 생성하기 때문에)
- Coroutine에는 CPS(Continuation Passing Style) 패러다임이 적용되어 있습니다. 
 
# 🍎Coroutine 은 왜 Main-Thread(Single-Thread)를 가지고 있을까요?
- 경쟁 상태/ 교착 상태를 예방 할 수 있습니다
- Context Switching 의 비용을 요구하지 않아서 애플리케이션 응답성 유지에 도움이 됩니다.


# 🍎Main-Safe 왜 해야하는지?
-  안드로이드의 Main-Thread는 많은 리소스를 작업하는 환경이여서 ~ 많은 부하를 받은 작업은 하지말아야하 한다 / 이런 작업은 백그라운드 스레드를 진행하여 작업을 이어나가야 합니다.
-  코루틴의 쓰레드의 차이 없이 필요할 메모리 Out Of Memoryf 피할 수 있습니다.


<참조문서><br>
https://tinyurl.com/2j3qx4qw<br>
https://tinyurl.com/2ncuxj7j<br>
https://tinyurl.com/2gx9wkv2<br>
https://tinyurl.com/2pv9e9pt (coroutine object )




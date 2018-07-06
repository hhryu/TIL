## Thread

- 명령어를 실행하기 위한 스케줄링 단위로 프로세스 내부에 생성할 수 있다.
- 멀티 스레딩을 지원하는 운영체제일 경우 하나의 프로세스에  여러 개의 스레드 자원을 가질 수 있다.
- 단일 스레드라는 것은 여러 작업을 동시에 할 수 없음을 의미, 이를 위해서 멀티 스레드가 필요.



#### 1. Foreground Thread 

```c#
static void Main(string[] args)
{
    var thread = new Thread(Func);
    thread.Start();
}

static void Func()
{
    //3초 후 프로그램 종료
    Thread.Sleep(3000);
}
```

- 위 코드와 같이 프로그램 실행 종료에 영향을 주는 스레드를 **Foreground Thread**라고 한다.



#### 2. Background Thread

```c#
static void Main(string[] args)
{
    var thread = new Thread(Func);
    thread.IsBackground = true;
    thread.Start();
    //thread.Join();
}

static void Func()
{
    //3초를 기다리지 않고 프로그램이 종료될 수 있음
    Thread.Sleep(3000);
}
```

- 위 코드와 같이 프로그램 실행 종료에 영향을 주지 않는 스레드를 **Background Thread**라고 한다.
- Background Thread이지만 작업이 종료될때까지 대기하게 하려면 **Join()**를 사용하면 된다.



#### 3. Thread Synchronization

- 여러 스레드가 하나의 자원을 공유할 때 충돌을 방지하기 위해 동기화가 필요하다.

```c#
// 방법1 : Monitor클래스 사용
class Test {
    public int Num { get; private set; }
    
    object lockObj = new object();
    
    public void Increment()
    { 
        Monitor.Enter(lockObj);
        try
        {
            //공유자원 사용
            this.Num++;
        }
        finally
        {
            Monitor.Exit(lockObj);
        }
    }
}

// 방법2 : lock 키워드 사용
public void Increment()
{
    lock(lockObj)
    {
        this.Num++;
    }
}
```

- 위 코드와 반대로 동기화 처리가 되지 않는 메서드를 **Not Thread-Safe** 메서드라고 한다.



#### 4. ThreadPool

- 재사용이 가능한 스레드 자원의 집합.
- 하나의 스레드를 생성/종료하는데 소비되는 CPU 사용량이 크므로 많은 스레드를 생성할 경우 ThreadPool을 사용하는 것이 성능에 좋다.

```c#
var obj = new object();
ThreadPool.QueueUserWorkItem(Func, obj);
```

- 위 코드의 QueueUserWorkItem()를 호출하면 먼저 스레드풀에서 유휴 스레드가 존재하는지 확인한다.
- 유휴 스레드가 있다면 그 스레드를 재사용하게 되고 없다면 새로운 스레드를 생성하여 실행한다.
- 작업이 종료되면 스레드는 바로 사라지지 않고 일정 시간 동안 스레드풀에 머물게 된다. (유휴 스레드)
- 스레드는 일정 시간 동안 새로운 작업이 할당되지 않으면 스레드풀에서 제거된다.


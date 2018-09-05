## P/Invoke (Platform Invoke)

- Native DLL(Unmanaged DLL)에 있는 함수를 호출할 때 사용하는 기술. (예: Win32 API)



#### 1. 구현 방법

- **System.Runtime.InteropServices** 네임스페이스 추가.
- **DllImport**를 통해 호출하고자 하는 함수의 dll을 지정.
- **static extern** 한정자를 사용하여 호출하고자 하는 함수의 시그니쳐를 지정.
  - Win32 API에 있는 메서드 시그니쳐는 **pinvoke.net** 에서 확인 가능.

```c#
using System;
using System.Runtime.InteropServices;

namespace Test
{
    class Program
    {
        static void Main(string[] args)
        {
            Beep(100, 1000);
        }
    }
    [DllImport("Kernel32.dll")]
    public static extern bool Beep(uint frequency, uint duration);
}
```



#### 2. Cross Platform에서 사용

- P/Invoke는 런타임시에 동적으로 함수를 호출하므로 컴파일 시 해당 함수를 가진 dll을 발견하지 못하여도 컴파일은 성공적으로 진행된다.

```c#
using System;
using System.Runtime.InteropServices;

namespace Test
{
    class Program
    {
        static void Main(string[] args)
        {
            OperatingSystem os = Environment.OSVersion;
            if(os.Platform == PlatformID.Win32Windows
               || os.Platform == PlatformID.Win32NT)
            {
                MessageBox(IntPtr.Zero, "Hello", "Windows", 0);
            }
            else
            {
                printf("Hello\n");
            }
        }
        
        [DllImport("user32", CharSet = charSet.Auto)]
        public static extern int MessageBox(IntPtr hwnd, string txt,
                                            string caption, int option);
        
        [DllImport("libc")]
        public static extern void printf(string txt);
    }
}
```

- if문은 Window에서 user32.dll의 MessageBox 메서드를 호출
- else문은 유닉스계열의 libc library의 print 메서드를 호출



#### 3. 호출하고자 하는 함수명을 바꾸고 싶은 경우

- EntryPoint에 기존의 함수명을 입력하면 된다.

```c#
[DllImport("Kernel32.dll"), EntryPoint = "Beep"]
    public static extern bool CustomBeep(uint frequency, uint duration);
```
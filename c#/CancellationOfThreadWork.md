## 실행중인 Task 작업 Cancel하기.

```c#
var cts = CancellationTokenSource();
var token = cts.Token;
    
var task = new Task(() => 
{
    while(true) 
    {
        if(token.IsCancellationRequested)
    	{
        	break;
	    }
    }
}, token);

task.Start();
cts.Cancel();
```


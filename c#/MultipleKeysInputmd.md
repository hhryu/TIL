## 다중 키 입력 받기

```c#
this.ctrl.KeyDown += (s, e) => 
{
	if(e.Control && e.KeyCode == Keys.C) 
	{
        //Ctrl+c 입력
	}
};
```


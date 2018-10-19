## Multi-Threading에서 UI Control에 접근 하는 방법.

```c#
delegate void SettingTextDelegate(string txt);	

void SetText(string txt)
{
    if(this.txtbox.InvokeRequired) 
    {
        var dele = new SettingTextDelegate(SetText);
        this.Invoke(dele, new object[] { txt });
    }
    else
    {
        this.txtbox.Text = txt;
    }
}

```


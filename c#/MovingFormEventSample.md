## 폼 이동 이벤트

```c#
public partial class Test : Form
{
	public const int WM_NCLBUTTONDOWN = 0xA1;
	public const int HT_CAPTION = 0x2;

	[DllImport("user32.dll")]
	public static extern int SendMessage(IntPtr hWnd, int Msg, int wParam, int lparam);

	[DllImport("user32.dll")]
	public static extern bool ReleaseCapture();

	public Test()
	{
		InitializeComponent();
		this.pn_left.MouseDown += MoveFrm;
		this.pn_main.MouseDown += MoveFrm;
    }

	private void MoveFrm(object sender, MouseEventArgs e)
	{
		if(e.Button == MouseButtons.Left)
		{
			ReleaseCapture();
			SendMessage(Handle, WM_NCLBUTTONDOWN, HT_CAPTION, 0);
		}
	}
}
```


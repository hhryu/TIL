```c#
using System;
using System.Drawing;
using System.Windows.Forms;

namespace MainProject.UserControls
{
    public partial class TabButton : UserControl
    {
        public TabButton()
        {
            InitializeComponent();
            this.MouseHover += MouseOverEvent;
            this.MouseLeave += MouseLeaveEvent;
            this.MouseDown += MouseDownEvent;
            this.MouseUp += MouseUpEvent;
            this.btn_close.MouseEnter += btn_close_MouseOver;
            this.btn_close.MouseLeave += btn_close_MouseLeave;
        }

        private void btn_close_MouseLeave(object sender, EventArgs e)
        {
            this.MouseLeaveEvent(sender, e);
        }

        private void btn_close_MouseOver(object sender, EventArgs e)
        {
            this.MouseOverEvent(sender, e);
            this.btn_close.FlatAppearance.MouseOverBackColor = Color.LightSlateGray;
        }

        private void MouseUpEvent(object sender, MouseEventArgs e)
        {
            Color color = Color.FromArgb(((int)(((byte)(7)))), ((int)(((byte)(38)))), ((int)(((byte)(59)))));
            this.BackColor = color;
            this.btn_close.BackColor = color;
            this.btn_close.FlatAppearance.BorderColor = color;
        }

        private void MouseDownEvent(object sender, MouseEventArgs e)
        {
            Color color = Color.LightSlateGray;
            this.BackColor = color;
            this.btn_close.BackColor = color;
            this.btn_close.FlatAppearance.BorderColor = color;
        }

        private void MouseLeaveEvent(object sender, EventArgs e)
        {
            Color color = Color.FromArgb(((int)(((byte)(33)))), ((int)(((byte)(133)))), ((int)(((byte)(143)))));
            this.BackColor = color;
            this.btn_close.BackColor = color;
            this.btn_close.FlatAppearance.BorderColor = color;
        }

        private void MouseOverEvent(object sender, EventArgs e)
        {
            Color color = Color.FromArgb(((int)(((byte)(7)))), ((int)(((byte)(38)))), ((int)(((byte)(59)))));
            this.BackColor = color;
            this.btn_close.BackColor = color;
            this.btn_close.FlatAppearance.BorderColor = color;
        }
    }
}

```


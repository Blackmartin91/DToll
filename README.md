# DToll
Gépi Látás: Digitális toll

Ez egy projeckt ahol bemutatom a digitális tollat.


<InkCanvas Name="myInkCanvas" MouseRightButtonUp="RightMouseUpHandler">
  private void RightMouseUpHandler(object sender, 
                                 System.Windows.Input.MouseButtonEventArgs e)
{
    Matrix m = new Matrix();
    m.Scale(1.1d, 1.1d);
    ((InkCanvas)sender).Strokes.Transform(m, true);
}
  
  using System;
using System.Windows;
using System.Windows.Controls;
class Program : Application
{
    Window win;
    InkCanvas ic;

    protected override void OnStartup(StartupEventArgs args)
    {
        base.OnStartup(args);
        win = new Window();
        ic = new InkCanvas();
        win.Content = ic;
        win.Show();
    }

    [STAThread]
    static void Main(string[] args)
    {
        new Program().Run();
    }
}

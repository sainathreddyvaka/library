# library
library code:
namespace Stackop
{
  public class opreations
    {
        static Stack<int> NumberStack = new Stack<int>();
        public void add(int stackitem)
        {
            NumberStack.Push(stackitem);
        }
        public int remove()
        {
            int j= NumberStack.Pop();
            return j ;
        }
        public int getdata()
        {
            int k = NumberStack.Count;
            return k;
        }
      }
    }    
    
    
    
    web site code(home page screen):
    
    <%@ Page Language="C#" AutoEventWireup="true" CodeFile="home.aspx.cs" Inherits="home" %>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title></title>
</head>
<body>
    <form id="form1" runat="server">
    <div>
    
        <asp:Button ID="Button1" runat="server" OnClick="Button1_Click" Text="push" />
        <asp:Button ID="Button2" runat="server" OnClick="Button2_Click" Text="pop" />
        <asp:Button ID="Button3" runat="server" OnClick="Button3_Click" Text="get data" />
    
    </div>
    </form>
</body>
</html>


webform1 code( push page code):
<%@ Page Language="C#" AutoEventWireup="true" CodeFile="push.aspx.cs" Inherits="push" %>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title></title>
</head>
<body>
    <form id="form1" runat="server">
    <div>
    
        <asp:Label ID="Label1" runat="server" Text="enter book number:"></asp:Label>
        <asp:TextBox ID="TextBox1" runat="server"></asp:TextBox>
        <asp:Button ID="Button1" runat="server" OnClick="Button1_Click" Text="push into stack" />
        <asp:Label ID="Label2" runat="server" Text="Label"></asp:Label>
    
    </div>
        <p>
            <asp:Button ID="Button2" runat="server" OnClick="Button2_Click" Text="click to go to home page" />
        </p>
    </form>
</body>
</html>
protected void Button1_Click(object sender, EventArgs e)
    {

        operations obj = new operations();
        if (TextBox1.Text == " ")
        {
            Label2.Text = "enter book number";
        }
        else
        {
            obj.add(Convert.ToInt32(TextBox1.Text));
            Label2.Text = TextBox1.Text + "added to stack";
        }
    }
    protected void Button2_Click(object sender, EventArgs e)
    {
        Server.Transfer("home.aspx");
    }
}
public partial class pop : System.Web.UI.Page



webform2 code(pop page code):

<%@ Page Language="C#" AutoEventWireup="true" CodeFile="pop.aspx.cs" Inherits="pop" %>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title></title>
</head>
<body>
    <form id="form1" runat="server">
    <div>
    
        <asp:Button ID="Button1" runat="server" OnClick="Button1_Click" Text="pop data" />
        <asp:Label ID="Label1" runat="server" Text="Label"></asp:Label>
    
    </div>
        <p>
            <asp:Button ID="Button2" runat="server" OnClick="Button2_Click" Text="click to go home page" />
        </p>
    </form>
</body>
</html>
{
    protected void Page_Load(object sender, EventArgs e)
    {

    }
    protected void Button1_Click(object sender, EventArgs e)
    {
        operations obj1 = new operations();

        Label1.Text = Convert.ToInt32(obj1.remove()) + "removed from stack";
    }
    protected void Button2_Click(object sender, EventArgs e)
    {
        Server.Transfer("home.aspx");
    }
}

 webform3 code(view data page code):
 
 <%@ Page Language="C#" AutoEventWireup="true" CodeFile="pop.aspx.cs" Inherits="pop" %>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title></title>
</head>
<body>
    <form id="form1" runat="server">
    <div>
    
        <asp:Button ID="Button1" runat="server" OnClick="Button1_Click" Text="pop data" />
        <asp:Label ID="Label1" runat="server" Text="Label"></asp:Label>
    
    </div>
        <p>
            <asp:Button ID="Button2" runat="server" OnClick="Button2_Click" Text="click to go home page" />
        </p>
    </form>
</body>
</html>

protected void Button1_Click(object sender, EventArgs e)
    {
        operations obj3 = new operations();
        obj3.remove();
        int l=obj3.getdata();
    
        for (int i=0; i<= l;i++ )
        {
           ListBox1.Text= obj3.remove().ToString();
        }
    }
    protected void Button2_Click(object sender, EventArgs e)
    {
        Server.Transfer("home.aspx");
    }



    

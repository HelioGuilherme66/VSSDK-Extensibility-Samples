
# Title: RGB Toolwindow Sample
**Abstract:** Provides a multi-instance toolwindow with a toolbar.

* Technologies: Visual Studio 2015 SDK
* Topics: Visual Studio Shell, VSX
* Last Updated: 05/15/2015

**Description**

This Visual Studio Package provides a multi-instance tool window called Red
Green Blue. The window contains a toolbar with three buttons that change the
background color and move the toolbar within the frame.

![image](C%23/Example.CommandTargetRGB.png)

**Requirements**

[ Visual Studio 2015 ](http://www.microsoft.com/visualstudio/en-us/try/default.mspx#download)

[ Visual Studio 2015 SDK ](https://www.visualstudio.com/en-us/downloads/visual-studio-2015-downloads-vs.aspx)



**Run the sample**

  1. To run the sample, hit **F5** or choose the **Debug &gt; Start Debugging** menu command. A new experimental instance of Visual Studio will launch. 
  2. Once loaded, choose the **View &gt; Other Windows &gt; RGB Toolwindow** menu command. 
  3. A new tool window called **Red Green Blue** will open containing a red background and a toolbar with three commands. This is a multi-instance tool window, meaining a new tool window will appear each time you select the **Red Green Blue** menu command. 
  4. The window contains a toolbar with three commands: **Red**, **Green**, and **Blue**. Each button changes the background color of the tool window and changes the position of the toolbar. **Red** aligns the toolbar with the top of the window, **Green** aligns the toolbar with the bottom, and **Blue** aligns the toolbar on the left edge of the screen. 



**Run the sample**

The source code in this sample demonstrates several techniques you can use to
write your own packages:

  * How to create a multi-instance tool window for your package 
  * How to style the content of a WPF control in a tool window 
  * How to handle commands from the tool window toolbar 
  * How to programmatically add a ToolBarTray to a WPF grid 



One of the most interesting aspects of the code for this sample is how the
toolbar is created. The _RGBToolWindow_ class uses the 
**IVsUIShell4.CreateToolbarTray** method to programmatically create a toolbar
tray, passing itself as the**IOleCommandTarget** for the toolbar. Since each
tool window is an independent instance of the _RGBToolWindow_ class, each tool
window can respond to its three toolbar commands independently without
affecting the other instances.



**Project Files**

* **CommandTargetRGB.vsct**

Defines the menu item, toolbar, and toolbar commands for the sample.

* **CommandTargetRGBPackage.cs**

Implements the Visual Studio Package, which creates and responds to the "Red
Green Blue" menu command.

* **RGBControl.xaml**

Defines the XAML layout for the WPF RGBControl.

* **RGBControl.xaml.cs**

Implements the code-behind for the RGBControl.

* **RGBToolWindow.cs**

Defines the tool window pane, creates the toolbar, and responds to
IOleCommandTarget commands.



**Functional Tests**

  * Verify the sample builds in all configurations
  * Verify that the sample was registered. The About box should list the product as installed
  * Verify that the toolwindow can be launched from **View &gt; Other Windows &gt; RGB Toolwindow**
  * Verify that the toolbar buttons change the background and reposition the toolbar as expected 



**Related topics**

  * [ Toolwindow Documentation ](https://msdn.microsoft.com/en-us/library/bb165390(v=vs.140).aspx)
  * [ Toolbar Documentation ](https://msdn.microsoft.com/en-us/library/dn949248(v=vs.140).aspx)
  * [ Visual Studio SDK Documentation ](https://msdn.microsoft.com/en-us/library/bb166441(v=vs.140).aspx)




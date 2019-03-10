# WinFormsCore
Example on how use the same Windows Forms in .net core 3 preview in Windows and run in Raspberry with Mono

In VS 2019 Preview you can't create direct a winforms in dotnetcore 3, so you net to use the cli.

mkdir WinFormCore
cd WinFormCore
dotnet new winfors -n WinFormCore
dotnet build

open the project in VS 2019. Save the project and Solution. The solution needs to be one level before the project

Add a new project to the Solution. Choose Windows Form Apps (.NET Framework) and name with the same name as the Core project, but add .Design to it
In this case it will be WinFormsCore.Design
The location folder should be the same as the Solution

In the property of the Classic Framework App renamte the default namespace to the core default namespace (remove the .Design)

Delete the Form1.cs in booth projects.

The steps below should be done every time you need to create a new Form

In the Classif Framework, add a new Windows Forms.

The Form would'nt contains the .resx file, so you need to do some change in form. Resize the window por example, change the text, etc.
When the .resx will be created, then save the form.

Select the Form in Classic Framework, cut (Ctrl + x), select the Core project and paste.

Select the Classic Framework, add -> Existing item...

In the selection box, change the "add" to "add as link" and select the 3 files from the form in Core folder.

Adjust both Program.cs to create the correct Form and build the solution.

Use the extension "File Nesting" to nest the files in Classic Framework project.

The core solution will run in Windows, and the bin from classic will run in Raspberry using mono

mono ./WinFormsCore.Design.exe


Based on: https://github.com/dotnet/winforms/blob/master/Documentation/winforms-designer.md


## scheenshot
### Raspberry: 
![alt text](https://github.com/TonhaoSemAcento/WinFormsCore/blob/master/screehshot/raspberry.PNG)

### Windows: 
![alt text](https://github.com/TonhaoSemAcento/WinFormsCore/blob/master/screehshot/windows.PNG)

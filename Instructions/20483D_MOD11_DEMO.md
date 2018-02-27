
# Module 11:   Integrating with Unmanaged Code

# Lesson 1:  Creating and using Dynamic Objects

### Demonstration: Interoperation with Microsoft Word

#### Preparation Steps

1. Ensure that you have cloned the 20483D directory from GitHub. It contains the code segments for this course's labs and demos. https://github.com/MicrosoftLearning/20483-Programming-in-C-Sharp/tree/master/Allfiles

#### Demonstration Steps

5.	Click **Visual Studio 2017**.
6.	In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.
7.	In the **Open Project** dialog box, browse to the **E:\Mod11\Democode\Starter\FourthCoffee.ExceptionLogger** folder, click **FourthCoffee.ExceptionLogger.sln**, and then click **Open**.
8.	In Solution Explorer, right-click the **FourthCoffee.ExceptionLogger** project, and then click **Add Reference**.
9.	In the **Reference Manager – FourthCoffee.ExceptionLogger** dialog box, perform the following steps, and then click **OK**:
    -	Expand **COM**, and then click **Type Libraries**.
    -	In the **Search** box, type **Word**.
    -	In the assembly list, select **Microsoft Word 14.0 Object Library**, and then select the **Microsoft Word 14.0 Object Library** check box.
10.	In Visual Studio, on the **View** menu, click **Task List**.
11.	In the **Task List** window, in the **Categories** list, click **Comments**.
12.	Double-click the **TODO: 01: Bring the Microsoft.Office.Interop.Word namespace into scope.** task.
13.	In the code editor, click in the blank line below the comment, and then type the following code:
    ```cs
    using Microsoft.Office.Interop.Word;
    ```
14.	Double-click the **TODO: 02: Declare a global object to encapsulate Microsoft Word**. task.
15.	In the code editor, click in the blank line below the comment, and then type the following code:
    ```cs
    dynamic _word;
    ```
16.	Double-click the **TODO: 03: Instantiate the _word object**. task.
17.	In the code editor, click in the blank line below the comment, and then type the following code:
    ```cs
    this._word = new Application();
    ```
18.	Double-click the **TODO: 04: Create a blank Word document**. task.
19.	In the code editor, click in the blank line below the comment, and then type the following code:
    ```cs
    this._word.Documents.Add().Activate();
    ```
20.	In the code editor, look at the following helper methods that wrap the Word COM API:
    -	The **GetEndOfDocument** method places the cursor at the end of the document. The **-1** converts the **End** property to a 0-based index value. Without the **-1**, the CLR will throw an IndexOutOfRange exception. 
    -	The **AppendText** method adds text to the end of the document, in the bold and/or italic style.
    -	The **InsertCarriageReturn** method inserts a carriage return at the end of the document.
    -	The **Save** method deletes any file with the same name and then saves the current Word document.
21.	On the **Build** menu, click **Build Solution**.
22.	On the **Debug** menu, click **Start Without Debugging**.
23.	In the **Exception Logger** application, click **Export**.
24.	In the **Export Successful** dialog box, click **OK**.
25.	Close the Exception Logger application.
26.	Open File Explorer, and browse to the **E:\Mod11\Democode\Data\Exceptions** folder.
27.	Double-click **Exceptions.docx**, and then view the combined exception report in the Word document.
28.	Close Microsoft Word.
29.	Close File Explorer.
30.	Close Visual Studio.





# Lesson 2:  Managing the Lifetime of Objects and Controlling Unmanaged Resoures

### Demonstration: Upgrading the Grades Report Lab

#### Preparation Steps

1. Ensure that you have cloned the 20483D directory from GitHub. It contains the code segments for this course's labs and demos. https://github.com/MicrosoftLearning/20483-Programming-in-C-Sharp/tree/master/Allfiles




©2017 Microsoft Corporation. All rights reserved.

The text in this document is available under the  [Creative Commons Attribution 3.0 License](https://creativecommons.org/licenses/by/3.0/legalcode), additional terms may apply. All other content contained in this document (including, without limitation, trademarks, logos, images, etc.) are  **not**  included within the Creative Commons license grant. This document does not provide you with any legal rights to any intellectual property in any Microsoft product. You may copy and use this document for your internal, reference purposes.

This document is provided &quot;as-is.&quot; Information and views expressed in this document, including URL and other Internet Web site references, may change without notice. You bear the risk of using it. Some examples are for illustration only and are fictitious. No real association is intended or inferred. Microsoft makes no warranties, express or implied, with respect to the information provided here.
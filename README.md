<div align="center">

## Disable the Windows Taskbar


</div>

### Description

Disable the Taskbar
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[StonePage](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/stonepage.md)
**Level**          |Unknown
**User Rating**    |5.0 (15 globes from 3 users)
**Compatibility**  |VB 4\.0 \(32\-bit\), VB 5\.0, VB 6\.0
**Category**       |[Windows System Services](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/windows-system-services__1-35.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/stonepage-disable-the-windows-taskbar__1-458/archive/master.zip)

### API Declarations

```
Dim hwnd1 As Long
Private Declare Function SetWindowPos Lib "user32" _
(ByVal hwnd As Long, ByVal hWndInsertAfter As Long, ByVal x As _
Long, ByVal y As Long, ByVal cx As Long, ByVal cy As Long, ByVal wFlags
_As Long) As Long
Private Declare Function FindWindow Lib "user32" _
Alias "FindWindowA" (ByVal lpClassName As String, ByVal lpWindowName _
As String) As Long
Const SWP_HIDEWINDOW &H80
Const SWP_SHOWWINDOW &H40
```


### Source Code

```
3. Add a Command Button control to Form1. Command1 is created by
default. Set its Caption property to "Hide".
4. Add the following code to the Click event for Command1.
Private Sub Command1_Click()
hwnd1 = FindWindow("Shell_traywnd", "")
Call SetWindowPos(hwnd1, 0, 0, 0, 0, 0, SWP_HIDEWINDOW)
End Sub
5. Add a second Command Button control to Form1. Command2 is created by
default. Set its Caption property to "Show".
6. Add the following code to the Click event for Command2.
Private Sub Command2_Click()
Call SetWindowPos(hwnd1, 0, 0, 0, 0, 0, SWP_SHOWWINDOW)
End Sub
```


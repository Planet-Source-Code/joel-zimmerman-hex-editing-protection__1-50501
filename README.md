<div align="center">

## Hex Editing Protection


</div>

### Description

Have you ever had one of your Programs, VIOLATED? By little punk kids that HEXED it? Well this Tutorial Shows you how to Protect against this!
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Joel Zimmerman](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/joel-zimmerman.md)
**Level**          |Intermediate
**User Rating**    |4.0 (16 globes from 4 users)
**Compatibility**  |VB 6\.0
**Category**       |[String Manipulation](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/string-manipulation__1-5.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/joel-zimmerman-hex-editing-protection__1-50501/archive/master.zip)





### Source Code

<br>Public Function HexEncrypt(ByVal sString As String) As String
<br>Dim sHex As String
<br>Dim i As Long
<br>Dim pos As Long
<br>Dim Encrypt As Boolean
<br>Dim sNew As String
<br>Dim sTmp As String
<br>Dim iDec As Long
<br>
<br>pos = 1
<br>For i = 1 To Len(sString) 'loop through the string however needed
<br>If Mid(sString, 1, 1) <> Chr(163) Then 'check if the string is already encrypted
<br>'Turn Char into hex
<br>sHex = sHex & Hex$(Asc(Mid(sString, i, 1)))
<br>'pad hex with zeros
<br>If Len(sHex) = 1 Then sHex = "0" & sHex
<br>Encrypt = True
<br>Else 'turn hex into text
<br>sTmp = Mid(sString, 2, Len(sString))
<br>sHex = Mid(sTmp, pos, 2)
<br>iDec = Val("&H" & sHex)
<br>If iDec > 0 Then
<br>sNew = sNew & Chr(iDec)
<br>End If
<br>pos = pos + 2
<br>Encrypt = False
<br>End If
<br>Next
<br>If Encrypt Then
<br>HexEncrypt = Chr(163) & sHex
<br>Else
<br>HexEncrypt = sNew
<br>End If
<br>End Function
<br>
<br>*************************** EXAMPLE: ***************************
<br>
<br>Dim Creator as string
<br>Creator = HexEncrypt("£42614444424C6F6F44")
<br>which actually means Creator = BaDDBLooD.
<br>
When people hex edit, They'll see the Hex of £42614444424C6F6F44, This will fake most inexperience users. Considering most people who hex programs are complete dumbdumb's ( Bad word Filter ) who can't make there own programs. Sometimes Experience users hex programs, to make them work under updated circumstances. If you want to Protect against this, just change the encryption to something more complex.
Tutorial Created by Joel Zimmerman, or Wu~En][g(v)a~uW@useast on Battle.net


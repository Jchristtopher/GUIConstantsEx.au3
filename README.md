# GUIConstantsEx.au3
#include &lt;GUIConstantsEx.au3>  _Example()  Func _Example()     Local $Form1, $iDummy, $iInput1, $iInput2, $iInput3, $iInput4, $nMsg     $Form1 = GUICreate("Input control with [Enter] key!", 320, 240, -1, -1)     $iInput1 = GUICtrlCreateInput("Input1", 14, 10, 290, 23)     $iInput2 = GUICtrlCreateInput("Input2", 14, 40, 290, 23)     $iInput3 = GUICtrlCreateInput("Input3", 14, 70, 290, 23)     $iInput4 = GUICtrlCreateInput("Input4", 14, 100, 290, 23)     $iDummy = GUICtrlCreateDummy()     Local $aAccelKeys[1][2] = [["{ENTER}", $iDummy]]     GUISetAccelerators($aAccelKeys)     GUISetState(@SW_SHOW)     While 1         $nMsg = GUIGetMsg()         Switch $nMsg             Case $GUI_EVENT_CLOSE                 Exit             Case $iDummy                 Switch ControlGetFocus($Form1)                     Case 'Edit1'                         MsgBox(4096, "Read!", GUICtrlRead($iInput1))                     Case 'Edit2', 'Edit3', 'Edit4'                         MsgBox(4096, "Read!", GUICtrlRead($iInput2) &amp; @CRLF &amp; GUICtrlRead($iInput3) &amp; @CRLF &amp; GUICtrlRead($iInput4))                         ; Case 'SysListView321'                         ; _Open()                         ; etc                 EndSwitch         EndSwitch     WEnd EndFunc

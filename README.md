# Alert-Found
$file = FileOpen("c:\hello.txt", 0) $read = FileRead($file)  func _CheckString()    If StringInStr($read, "Markus") Then       $position = StringInStr($read, "Markus")       MsgBox(0,"","Alert Found - Logs Line No "&amp;$position, 5)       FileClose($file)    Else       MsgBox(0,"","No Alert found", 5)       FileClose($file)    EndIf EndFunc  $Mins = 0.5 ; i change to fewer min for testing purpose $Timer = TimerInit()  While 1     If TimerDiff($Timer) > ($Mins * 60000) Then ; count per minute multiplied by 60sec.        _CheckString()        ConsoleWrite("30 Sec have passed!" &amp; @CRLF) ; console to see if its running.        $Timer = TimerInit()     EndIf  WEnd

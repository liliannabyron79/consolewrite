# consolewrite
 Global Const $ExpandCollapseState_Collapsed=0 ;~ Global Const $ExpandCollapseState_Expanded=1 ;~ Global Const $ExpandCollapseState_PartiallyExpanded=2 ;~ Global Const $ExpandCollapseState_LeafNode=3     $oExpandP.CurrentExpandCollapseState($state)     if $state=$ExpandCollapseState_Collapsed Then         _UIA_action("WMP.Firstlist","leftdoubleclick")     EndIf endif  ;~ _UIA_DEBUG("Action 4 Starting with the playbutton" &amp; @CRLF) ;~ $oPlayButton=_UIA_getObjectByFindAll($oWMP, _UIA_getVar("WMP.Playbutton"), $treescope_subtree) _UIA_action("WMP.Playbutton","left")  _UIA_DEBUG("Action 5 And finding the volume" &amp; @CRLF) $oVolumeButton=_UIA_getObjectByFindAll($oWMP, _UIA_getVar("WMP.Volumebutton"), $treescope_subtree) $oValueP=_UIA_getpattern($oVolumeButton,$UIA_ValuePatternId)  if isobj($oValueP) Then dim $volume     $oValuep.currentvalue($volume)     _UIA_Debug("Volume is " &amp; $volume &amp; @CRLF) EndIf  ; The End Func Terminate()     consolewrite("Exiting")     $running=false ;~  Exit 0 EndFunc   ;==>Terminate

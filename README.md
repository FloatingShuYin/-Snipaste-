;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;AHK代码，作者：zxh；QQ：105224583
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
Process, Priority, , High			;脚本高优先级
#NoTrayIcon 						;隐藏托盘图标
#NoEnv								;不检查空变量是否为环境变量
#Persistent						;让脚本持久运行(关闭或ExitApp)
#SingleInstance Force				;跳过对话框并自动替换旧实例
#WinActivateForce					;强制激活窗口
#MaxHotkeysPerInterval 200		;时间内按热键最大次数
#HotkeyModifierTimeout 100 		;按住modifier后（不用释放后再按一次）可隐藏多个当前激活窗口
SetBatchLines -1					;脚本全速执行
SetWinDelay 10						;设置在每次执行窗口命令(例如 WinActivate)后自动的延时
SetKeyDelay -1						;设置每次Send和ControlSend发送键击后自动的延时,使用-1表示无延时
SetControlDelay -1					;控件修改命令自动延时,-1无延时，0最小延时
CoordMode Menu Window				;坐标相对活动窗口
CoordMode Mouse Screen				;鼠标坐标相对于桌面(整个屏幕)
SendMode Input						;更速度和可靠方式发送键盘点击
SetTitleMatchMode 2				;窗口标题模糊匹配;RegEx正则匹配
DetectHiddenWindows On				;显示隐藏窗口
SetWorkingDir %A_ScriptDir%		;当前脚本的绝对路径.不包含最后的反斜线：D:\zxh\QuickZ\Apps，通用性不如A_workingdir
#InstallKeybdHook
#InstallMouseHook
#KeyHistory 100

#If (WinActive("ahk_class Qt5QWindowToolSaveBits") && IMECheckInputMode())		;Snapaste截图软件
$Esc::
	SentenceMode := IME_GetSentenceMode(_mhwnd())		;当前键盘布局
	if SentenceMode=8
		Send, {Esc 2}
	else		
		Send, {Esc}
	ifWinActive ahk_class Qt5QWindowToolSaveBits
		Send, {Space}
	return
#If (WinActive("ahk_class Qt5QWindowToolSaveBits") && !IMECheckInputMode())		;Snapaste截图软件
$Esc::
	ImageSearch, nowx, nowy, 0, 0, A_ScreenWidth, A_ScreenHeight, *10 D:\zxh\QuickZ\Apps\2system\icon\Snipaste\save.bmp
	if !ErrorLevel{
		Send, {Esc}
		return
	}else{
		Send, {Esc}
		ifWinActive ahk_class Qt5QWindowToolSaveBits
		Send, {Space}
	}
	return
+/::Run, D:\zxh\0常用软件\AutoHotkey110502\Snipaste.jpg
$c::
	ImageSearch, nowx, nowy, 0, 0, A_ScreenWidth, A_ScreenHeight, *10 D:\zxh\QuickZ\Apps\2system\icon\Snipaste\save.bmp
	if !ErrorLevel{
		Send, ^c
	}else{
		Send, c
	}
	return
$s::
	ImageSearch, nowx, nowy, 0, 0, A_ScreenWidth, A_ScreenHeight, *10 D:\zxh\QuickZ\Apps\2system\icon\Snipaste\save.bmp
	if !ErrorLevel{
		Send, ^s
	}else{
		Send, s
	}
	return
$z::
	ImageSearch, nowx, nowy, 0, 0, A_ScreenWidth, A_ScreenHeight, *10 D:\zxh\QuickZ\Apps\2system\icon\Snipaste\save.bmp
	if !ErrorLevel{
		Send, {Esc}
	}else{
		Send, z
	}
	return
b::
	ImageSearch, nowx, nowy, 0, 0, A_ScreenWidth, A_ScreenHeight, *10 D:\zxh\QuickZ\Apps\2system\icon\Snipaste\b.bmp
	if !ErrorLevel{
		nowx:=nowx+15
		nowy:=nowy+15
		MouseGetPos, MouseX, MouseY, MouseWin
		MouseMove, %nowx%, %nowy%, 0
		Click
		MouseMove, %MouseX%, %MouseY%, 0
	}
	return
e::
	ImageSearch, nowx, nowy, 0, 0, A_ScreenWidth, A_ScreenHeight, *10 D:\zxh\QuickZ\Apps\2system\icon\Snipaste\e.bmp
	if !ErrorLevel{
		nowx:=nowx+15
		nowy:=nowy+15
		MouseGetPos, MouseX, MouseY, MouseWin
		MouseMove, %nowx%, %nowy%, 0
		Click
		MouseMove, %MouseX%, %MouseY%, 0
	}
	return
j::
	ImageSearch, nowx, nowy, 0, 0, A_ScreenWidth, A_ScreenHeight, *10 D:\zxh\QuickZ\Apps\2system\icon\Snipaste\j.bmp
	if !ErrorLevel{
		nowx:=nowx+15
		nowy:=nowy+15
		MouseGetPos, MouseX, MouseY, MouseWin
		MouseMove, %nowx%, %nowy%, 0
		Click
		MouseMove, %MouseX%, %MouseY%, 0
	}
	return
m::
	ImageSearch, nowx, nowy, 0, 0, A_ScreenWidth, A_ScreenHeight, *10 D:\zxh\QuickZ\Apps\2system\icon\Snipaste\m.bmp
	if !ErrorLevel{
		nowx:=nowx+15
		nowy:=nowy+15
		MouseGetPos, MouseX, MouseY, MouseWin
		MouseMove, %nowx%, %nowy%, 0
		Click
		MouseMove, %MouseX%, %MouseY%, 0
	}
	return
q::
	ImageSearch, nowx, nowy, 0, 0, A_ScreenWidth, A_ScreenHeight, *10 D:\zxh\QuickZ\Apps\2system\icon\Snipaste\q.bmp
	if !ErrorLevel{
		nowx:=nowx+15
		nowy:=nowy+15
		MouseGetPos, MouseX, MouseY, MouseWin
		MouseMove, %nowx%, %nowy%, 0
		Click
		MouseMove, %MouseX%, %MouseY%, 0
	}
	return
t::
	ImageSearch, nowx, nowy, 0, 0, A_ScreenWidth, A_ScreenHeight, *10 D:\zxh\QuickZ\Apps\2system\icon\Snipaste\t.bmp
	if !ErrorLevel{
		nowx:=nowx+15
		nowy:=nowy+15
		MouseGetPos, MouseX, MouseY, MouseWin
		MouseMove, %nowx%, %nowy%, 0
		Click
		MouseMove, %MouseX%, %MouseY%, 0
	}
	return
v::
	ImageSearch, nowx, nowy, 0, 0, A_ScreenWidth, A_ScreenHeight, *10 D:\zxh\QuickZ\Apps\2system\icon\Snipaste\v.bmp
	if !ErrorLevel{
		nowx:=nowx+15
		nowy:=nowy+15
		MouseGetPos, MouseX, MouseY, MouseWin
		MouseMove, %nowx%, %nowy%, 0
		Click
		MouseMove, %MouseX%, %MouseY%, 0
	}
	return
x::
	ImageSearch, nowx, nowy, 0, 0, A_ScreenWidth, A_ScreenHeight, *10 D:\zxh\QuickZ\Apps\2system\icon\Snipaste\x.bmp
	if !ErrorLevel{
		nowx:=nowx+15
		nowy:=nowy+15
		MouseGetPos, MouseX, MouseY, MouseWin
		MouseMove, %nowx%, %nowy%, 0
		Click
		MouseMove, %MouseX%, %MouseY%, 0
	}
	return

#If 


`@echo off` 
`echo Set WshShell = CreateObject("WScript.Shell") > NumLockOn.vbs` 
`echo WshShell.SendKeys "{NUMLOCK}" >> NumLockOn.vbs` 
`cscript //nologo NumLockOn.vbs` 
`del NumLockOn.vbs`

Code im Editor / Notepad++ einfügen und als .bat speichern --> in einer Aufgabe bei der Aufgabenplanung konfigurieren

#informatik #informatik/Aufgabenplanung #informatik/Skripte #informatik/Windows 
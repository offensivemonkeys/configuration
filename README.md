# Configuration for Windows 10

First of all, i'm a big fun of `Scoop` on Windows! I think Scoop is a good choice from another available tools.
Most of the time i'm using terminal in code editor, but sometimes i need a full version of that.

We will use `PowerShell` next time.

```ps1
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser 
$env:SCOOP = "$env:USERPROFILE\Scoop" 
[Environment]::SetEnvironmentVariable('SCOOP', $env:SCOOP, 'User') 
iwr -useb get.scoop.sh | iex 
scoop install sudo git openssh 
[Environment]::SetEnvironmentVariable('GIT_SSH', Resolve-Path(scoop which ssh), 'User') 
scoop bucket add extras 
scoop install pshazz windows-terminal vscode-portable hosts-file-editor insomnia gitkraken 
scoop bucket add nerd-fonts 
sudo scoop install JetBrains-Mono 
```

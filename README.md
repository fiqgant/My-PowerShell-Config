# My PowerShell Config
- [Nerd Fonts](https://www.nerdfonts.com/) Iconic font aggregator, collection, and patcher
- [Scoop](https://scoop.sh/). A command-line installer for Windows


## Screenshot
![alt tag](https://github.com/fiqgant/My-PowerShell-Config/blob/main/Images/SS_1.png)

![alt tag](https://github.com/fiqgant/My-PowerShell-Config/blob/main/Images/SS_2.png)

![alt tag](https://github.com/fiqgant/My-PowerShell-Config/blob/main/Images/SS_3.png)


## Code

``` Powershell
# Prompt
clear
Import-Module posh-git
Import-Module PSReadLine
Import-Module -Name Terminal-Icons
oh-my-posh init pwsh --config C:\Users\fiq\AppData\Local\Programs\oh-my-posh\themes/cloud-native-azure.omp.json | Invoke-Expression

# PSReadline
Set-PSReadLineOption -EditMode Emacs
Set-PSReadLineOption -BellStyle None
Set-PSReadLineKeyHandler -Chord 'Ctrl+d' -Function DeleteChar
Set-PSReadLineOption -PredictionSource History

#Fzf
Import-Module PSFzf
Set-PsFzfOption -PSReadlineChordProvider 'Ctrl+f' -PSReadlineChordReverseHistory 'Ctrl+r'

# Alias
Set-Alias vim nvim
Set-Alias ll ls
Set-Alias g git
Set-Alias grep findstr
Set-Alias tig 'C:\Program Files\Git\usr\bin\tig.exe'
Set-Alias less 'C:\Program Files\Git\usr\bin\less.exe'
Set-Alias python 'C:\Users\fiq\AppData\Local\Programs\Python\Python37\python.exe'
Set-Alias p 'C:\Users\fiq\AppData\Local\Programs\Python\Python37\python.exe'


# Utilities
function which ($command) {
    Get-Command -Name $command -ErrorAction SilentlyContinue |
        Select-Object -ExpandProperty Path -ErrorAction SilentlyContinue
    
}

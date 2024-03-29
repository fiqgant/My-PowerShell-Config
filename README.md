# My PowerShell Config
- [Nerd Fonts](https://www.nerdfonts.com/) Iconic font aggregator, collection, and patcher
- [Scoop](https://scoop.sh/) A command-line installer for Windows
- [Git](https://git-scm.com/) DevOps tool used for source code management
- [Neovim](https://github.com/neovim/neovim) Vim-fork focused on extensibility and usability
- [Oh My Posh](https://ohmyposh.dev/docs) A prompt theme engine for any shell.
- [Terminal Icons](https://github.com/devblackops/Terminal-Icons) A PowerShell module to show file and folder icons in the terminal
- [z](https://github.com/rupa/z) Directory jumper
- [PSReadLine](https://github.com/PowerShell/PSReadLine) A bash inspired readline implementation for PowerShell
- [Fzf](https://github.com/junegunn/fzf) A command-line fuzzy finder


## Screenshots
![alt tag](https://github.com/fiqgant/My-PowerShell-Config/blob/main/Images/SS_1.png)

![alt tag](https://github.com/fiqgant/My-PowerShell-Config/blob/main/Images/SS_2-.png)

![alt tag](https://github.com/fiqgant/My-PowerShell-Config/blob/main/Images/SS_3.png)


## Code

### Prompt
``` Powershell
clear
Import-Module posh-git
Import-Module PSReadLine
Import-Module -Name Terminal-Icons
oh-my-posh init pwsh --config C:\Users\fiq\AppData\Local\Programs\oh-my-posh\themes/cloud-native-azure.omp.json | Invoke-Expression
```

### PSReadline
``` Powershell
Set-PSReadLineOption -EditMode Emacs
Set-PSReadLineOption -BellStyle None
Set-PSReadLineKeyHandler -Chord 'Ctrl+d' -Function DeleteChar
Set-PSReadLineOption -PredictionSource History
```

### Fzf
``` Powershell
Import-Module PSFzf
Set-PsFzfOption -PSReadlineChordProvider 'Ctrl+f' -PSReadlineChordReverseHistory 'Ctrl+r'
```


### Alias
``` Powershell
Set-Alias vim nvim
Set-Alias ll ls
Set-Alias g git
Set-Alias grep findstr
Set-Alias tig 'C:\Program Files\Git\usr\bin\tig.exe'
Set-Alias less 'C:\Program Files\Git\usr\bin\less.exe'
Set-Alias python 'C:\Users\fiq\AppData\Local\Programs\Python\Python39\python.exe'
Set-Alias p 'C:\Users\fiq\AppData\Local\Programs\Python\Python39\python.exe'
```

### Utilities
``` Powershell
function which ($command) {
    Get-Command -Name $command -ErrorAction SilentlyContinue |
        Select-Object -ExpandProperty Path -ErrorAction SilentlyContinue
    
}
```

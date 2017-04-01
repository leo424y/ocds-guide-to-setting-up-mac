# 強迫症的 Mac 設定指南

## 如何配置一個高效的 Mac 工作環境

[English Version](https://github.com/macdao/ocds-guide-to-setting-up-mac/blob/master/README.en.md)

## Table of Contents

1. [OS X](#1-os-x)

   - [功能鍵](#功能鍵)
   - [全鍵盤控制](#全鍵盤控制)
   - [Spotlight 快捷鍵](#spotlight-快捷鍵)
   - [輸入法快捷鍵](#輸入法快捷鍵)
   - [其他快捷鍵](#其他快捷鍵)
   - [設定 Trackpad 輕點來點按](#設定-trackpad-輕點來點按)
   - [語音](#語音)
   - [詞典](#詞典)
   - [Dock Position](#dock-position)
   - [更改 Caps Lock 鍵為 Control 鍵](#更改-caps-lock-鍵為-control-鍵)
   - [Remove all Dock icons[OCD]](#remove-all-dock-iconsocd)
   - [重置 Launchpad 上圖示位置[OCD]](#重置-launchpad-上圖示位置ocd)
   - [建立大小寫敏感的工作區](#建立大小寫敏感的工作區)
   - [Keychain Access](#keychain-access)

2. [常用工具](#2-常用工具)

   - [Homebrew](#homebrew)
   - [Homebrew Cask](#homebrew-cask)
   - [iTerm2](#iterm2)
   - [Oh My Zsh](#oh-my-zsh)
   - [stow](#stow)
   - [Git 常用別名](#git-常用別名)
   - [Scroll Reverser](#scroll-reverser)
   - [ShiftIt](#shiftit)
   - [Sublime Text 2](#sublime-text-2)
   - [MacDown](#macdown)
   - [z](#z)
   - [Vimium](#vimium)
   - [LastPass](#lastpass)
   - [SourceTree](#sourcetree)
   - [CheatSheet](#cheatsheet)
   - [Alfred](#alfred)

3. [開發工具](#3-開發工具)

   - [Java](#java)
   - [jEnv](#jenv)
   - [民間使用的 Java 版本切換方法](#民間使用的-java-版本切換方法)
   - [Java[OCD]](#javaocd)
   - [IntelliJ IDEA](#intellij-idea)
   - [rbenv](#rbenv)
   - [Ruby 常用別名](#ruby-常用別名)

一直想寫這麼一篇文章，把我從同事那裡學到的經驗分享出來。市面上有很多類似的文章，寫得都非常好，讓我受益匪淺。不過我還是有一些自己總結出來的經驗想要分享。

在工作中，我一般會在 1 到 10 人的團隊中，經常會結對程式設計，即兩個人共用一臺 Mac 工作，因此也經常會把 Mac 外接一個大顯示器、滑鼠和鍵盤。我的常用開發平臺有 Java、Ruby、Node.js、Web 等，使用 [JetBrains](https://www.jetbrains.com/) 的開發工具，比如 IntelliJ IDEA、RubyMine、WebStorm 等。

我深知自己的知識有限，所以寫下本文以便和大家切磋交流。同時更有效率的方法和更好的工具也在不斷湧現，我也貪心的希望把更好的方法和工具都收集更到到這裡，我會不斷更新本文，讓它儘量不過時。最新內容請訪問：<https://github.com/macdao/ocds-guide-to-setting-up-mac>。歡迎通過 GitHub 的`Issues`或者直接`Pull Requests`方式來分享你的經驗。期待你的反饋。

我認為“一個高效的 Mac 工作環境”有以下幾個特點：

- 自動化

  舉個例子。手動安裝一個應用，需要1)開啟瀏覽器，2)搜尋應用的名字，3)開啟應用網站，4)尋找下載連結和安裝方法，5)下載並等待下載完成，6)安裝下載檔案，7)可能還有後續的安裝步驟。而自動化安裝一個應用，只需要1)開啟終端工具，2)敲入安裝命令，3)等待完成這幾個步驟。

  自動化可以大大簡化操作，提高效率。

- 統一

  我經常結對程式設計，偶爾會遇到快捷鍵不一樣，命令不同等問題。我強烈建議，至少在一個團隊中，大家儘量使用相同的快捷鍵、命令等環境。（我記得有個實踐就是這個，可是我一直沒找到該實踐的名字和出處，求告訴）

- 夠用

  夠用就好，如果系統本身已經滿足了我的需求，我不會再使用第三方工具。

- 效率

  效率，一切都是為了效率。

本文對於第三方應用如何安裝和使用只有最簡單的介紹，具體還請參考官方網站和相關文件。

有些章節標題標註了[OCD]，意思是這些章節帶有我強烈的個人色彩，如果你跟我臭味相投，歡迎借鑑，如果你並不認同，請忽略掉好了。

PS：雖然本文名為“強迫症”，但其實並不是[真正意義上的強迫症](https://zh.wikipedia.org/wiki/強迫症)，真正意義上的強迫症是一種會對患者的日常生活產生負面影響的疾病。

## 1. OS X

本節介紹作業系統本身的一些設定。

### 功能鍵

預設情況下，F1-F12 都是特殊功能，比如調節螢幕亮度。而當你需要鍵入 F1-F12 時（比如在使用 IntelliJ IDEA 的快捷鍵時），需要同時按住 Fn。這對於開發人員來說是非常不方便的。

把 F1-F12 改成標準功能鍵：選擇`System Preferences` > `Keyboard`，在`Keyboard`標籤頁中選中`Use all F1, F2, etc. keys as standard function keys`。

### 全鍵盤控制

當你在 Sublime Text 裡關閉檔案時，可能會遇到這樣的對話方塊：

![dialog-box-without-all-controls](dialog-box-without-all-controls.png)

注意這個`Save`按鈕跟其他兩個按鈕不太一樣，它的底色是藍的。這種按鈕被稱為預設按鈕，除了用滑鼠點選觸發外，還可以通過回車鍵觸發。

那麼問題來了，如果你不想儲存，想點選`Don't Save`，是不是隻能用滑鼠點選了呢？

並不是這樣：選擇`System Preferences` > `Keyboard`，在`Shortcuts`標籤頁中選擇`All controls`；或者使用快捷鍵`⌃F7`。之後這個對話方塊會變成這樣：

![dialog-box-with-all-controls](dialog-box-with-all-controls.png)

這個`Don't Save`按鈕有了一圈藍邊，這個意味著你可以通過空格鍵觸發。不僅如此，你還可以用`Tab`鍵把藍邊轉移到其他按鈕，來實現全鍵盤控制。

除了`All controls`這個方法，你還可以用`⌘⌫`來選擇`Don't Save`。`⌘⌫`的作用是在包含“刪除”或“不儲存”按鈕的對話方塊中選擇“刪除”或“不儲存”。

除了上述兩個辦法之外，居然還有個方法！就是按`⌘D`！據說是因為按`⌘+按鈕的大寫首字母`可以觸發該按鈕。可是！我按了`⌘C`和`⌘S`想取消和儲存都沒用！但是`⌘D`真的有用！如果僅僅是這也就算了，可是我又手賤試了下 TextEdit，在關閉未儲存的檔案時彈出的對話方塊上有三個按鈕`Delete`、`Cancel`和`Save`。然而`⌘D`和`⌘C`都沒用，但是！`⌘S`可以儲存！我完全不能理解！我整個人幾乎都是崩潰的，只好以咆哮體寫下這段文字。如果誰能解釋請務必告訴我，必有重謝！

`⌘C`不能用應該是因為它繫結到了複製功能；而`⌘D`不能用因為它的作用是從“開啟”對話方塊或“儲存”對話方塊中選擇“桌面”資料夾。

在這個對話方塊上，你可以用`Esc`來執行`Cancel`操作。

### Spotlight 快捷鍵

中文版 OS X 的 Spotlight 的快捷鍵是`⌃Space`。這個快捷鍵有一些問題：

- JetBrains 的 IDE，比如 IntelliJ IDEA、WebStorm 等都使用`⌃Space`作為自動完成這個最常用功能的快捷鍵。我不建議更改 IDE 的快捷鍵，而建議更改 Spotlight 的快捷鍵。
- 對於沒有新增中文輸入法的 Mac 來說，Spotlight 的快捷鍵是`⌘Space`。英語國家的人都是這樣的。所以我建議把 Spotlight 的快捷鍵設定為`⌘Space`，跟他們一致。

### 輸入法快捷鍵

一般來說切換輸入法的快捷鍵是`⌘Space`。由於我建議把 Spotlight 的快捷鍵設定為`⌘Space`，所以我建議把切換輸入法的快捷鍵設定為`⌥Space`。

### 其他快捷鍵

讓雙手儘量多的鍵盤和快捷鍵，少使用滑鼠和觸控板，可以大大提高效率。

- [Mac keyboard shortcts](https://support.apple.com/kb/HT201236)

  蘋果官方文件。當你在寫程式碼，怎麼通過快捷鍵讓游標轉移到行首、行尾、向上翻頁或者將游標移左移一個詞？都在這篇文件裡。

- [Mac keyboard shortcuts for accessibility features](https://support.apple.com/kb/HT204434)

  蘋果官方文件。回車觸發藍底按鈕，空格觸發藍邊按鈕，都出自這裡。

### 設定 Trackpad 輕點來點按

預設情況下按下觸控板才是點按（click）。我喜歡設定成用輕點作為點按：

選擇`System Preferences` > `Trackpad`，在`Point & Click`標籤頁中選中`Tap to click`。

### 語音

OS X 自帶了語音功能，可以用`say`命令讓 Mac 開口說話：

```sh
say hello
```

可以和`&&`或者`;`配合使用來提示你某任務已經完成：

```sh
brew update && brew upgrade && brew cleanup ; say mission complete
```

通過命令列來聽取發音還是有點麻煩。其實我們幾乎可以在任何地方選中單詞，然後使用快捷鍵`⌥+ESC`發音。僅僅需要這樣設定一下：選擇`System Preferences` > `Dictation & Speech`，在`Text to Speech`標籤頁中選中`Speak selected text when the key is pressed`。

### 詞典

OS X 自帶了詞典（Dictionary）。你幾乎可以在任何應用中通過三指輕拍觸控板來現實對應單詞的釋義。

也可以開啟 Dictionary 應用來查詢單詞。

可以在 Dictionary 應用中新增英漢漢英詞典。

### Dock Position

預設 Dock 在螢幕下方。我們的螢幕一般都是 16:10，Dock 在螢幕下方的話會佔據本來就不大的垂直空間。建議把 Dock 放到左邊或者右邊。

### 更改 Caps Lock 鍵為 Control 鍵

我經常用到`Control`鍵，但這個鍵在鍵盤的左下角，很難按到。同時我發現我很少使用`Caps Lock`鍵，我一般會用`Shift`鍵加字母來輸入大寫字母，或者先輸入小寫再（通過快捷鍵）轉換成大寫。

基於以上原因，我把`Caps Lock`鍵的功能改成了`Control`鍵。很多同事也都這麼做的，可能是受到 [HHKB](https://en.wikipedia.org/wiki/Happy_Hacking_Keyboard) 的影響。

設定方法：選擇`System Preferences` > `Keyboard`，在`Keyboard`標籤頁中點選`Modifier Keys...`按鈕，在彈出的視窗中，把`Caps Lock (⇪) Key:`對應的選項改成`⌃ Control`。

### Remove all Dock icons[OCD]

本條目對於強迫症適用。

預設情況下 Dock 被一堆系統自帶的應用佔據著，而其中大部分我都很少使用，當我開啟幾個常用應用後，Dock 上會有很多圖示，每個圖示都會被擠得很小。所以我會把所有 Dock 上固定的圖示都刪掉，這樣一來 Dock 上只有我開啟的應用。

PS：Finder 圖示是刪不掉的。

除了一個一個刪除圖示，也可以通過這個命令來隱藏所有的固定圖示：

```sh
defaults write com.apple.dock static-only -boolean true; killall Dock
```

恢復也非常簡單：

```sh
defaults delete com.apple.dock static-only; killall Dock
```

PS：使用這個方法的話，Dock 上的`Downloads`也會被隱藏掉。

### 重置 Launchpad 上圖示位置[OCD]

本條目對於強迫症適用。

新的應用被安裝後，經常會跑到 Launchpad 的第一屏，所以它們的位置跟安裝的順序有關係，而我更希望它們可以按照某種更加穩定的順序排列，比如按照系統預設的順序：

```sh
defaults write com.apple.dock ResetLaunchPad -bool true; killall Dock
```

在預設順序中，Launchpad 第一屏只有 Apple 自家應用。

### 建立大小寫敏感的工作區

在多人合作的項目開發時，因為 Mac 檔案系統預設是大小寫不敏感的，所以經常會出現一些詭異的問題。建立一個大小寫敏感的工作區（workspace）來解決避免這些問題：

```sh
hdiutil create -type SPARSE -fs 'Case-sensitive Journaled HFS+' -size 100g -volname workspace ~/Documents/workspace.dmg.sparseimage
```

可以通過三種方式掛載映象：

1. 直接雙擊開啟 `~/Documents/workspace.dmg.sparseimage`
2. `open ~/Documents/workspace.dmg.sparseimage`
3. `hdiutil attach ~/Documents/workspace.dmg.sparseimage`

### Keychain Access

鑰匙串訪問（Keychain Access）是一個 OS X 應用程式，對我來說它最大的功能就是檢視已經儲存的各種賬號和密碼，包括 Wi-Fi 密碼。

## 2. 常用工具

本節介紹一些常用的，跟開發沒有直接關係的第三方應用及其設定。

### [Homebrew](http://brew.sh)

包管理工具，官方稱之為`The missing package manager for OS X`。

安裝步驟見官網。

有了 brew 以後，要下載工具，比如 MySQL、Gradle、Maven、Node.js 等工具，就不需要去網上下載了，只要一行命令就能搞定：

```sh
brew install mysql gradle maven node
```

PS：安裝 brew 的時候會自動下載和安裝 Apple 的 Command Line Tools。

brew 的替代品有 [MacPorts](https://www.macports.org/)，現在基本沒人用它。

### [Homebrew Cask](https://caskroom.github.io)

brew-cask 允許你使用命令列安裝 OS X 應用。比如你可以這樣安裝 Chrome：`brew cask install google-chrome`。還有 Evernote、Skype、Sublime Text、VirtualBox 等都可以用 brew-cask 安裝。

brew-cask 是社羣驅動的，如果你發現 brew-cask 上的應用不是最新版本，或者缺少你某個應用，你可以自己提交 pull request。

安裝步驟見官網。

應用也可以通過 App Store 安裝，而且有些應用只能通過 App Store 安裝，比如 Xcode 等一些 Apple 的應用。App Store 沒有對應的命令列工具，還需要 Apple ID。倒是更新起來很方便。

幾乎所有常用的應用都可以通過 brew-cask 安裝，而且是從應用的官網上下載，所以你要安裝新的應用時，建議用 brew-cask 安裝。如果你不知道應用在 brew-cask 中的 ID，可以先用`brew cask search`命令搜尋。

### [iTerm2](https://www.iterm2.com/)

iTerm2 是最常用的終端應用，是 Terminal 應用的替代品。提供了諸如`Split Panes`等[一群實用特性](https://www.iterm2.com/features.html)。它預設的黑色背景讓我毫不猶豫的拋棄了 Terminal。

安裝：

```sh
brew cask install iterm2
```

感謝 brew-cask，我們可以通過命令列自動安裝 iTerm2 了。

在終端裡，除了可以用`⌃E`等快捷鍵（詳見[其他快捷鍵](#其他快捷鍵)）之外，還可以使用`⌥B`、`⌥F`等快捷鍵（具體可以參考[這裡](http://ss64.com/bash/syntax-keyboard.html)）。前提是這樣設定一下：

選擇`Iterm`選單 > `Preferences` > `Profiles`，選擇你在使用的 Profile（預設是`Default`），在`Keys`標籤頁中把`Left option (⌥) key acts as`和`Right option (⌥) key acts as`都設定成`+ESC`。

在開啟新的視窗/標籤頁的時候，預設情況下新視窗總是 HOME 目錄，還需要我每次敲命令才能進入工作目錄。如果想要這個新視窗在開啟的時候就自動進入工作目錄，需要如下設定：

選擇`Iterm`選單 > `Preferences` > `Profiles`，選擇你在使用的 Profile（預設是Default），在`General`標籤頁中的`Working Directory`部分中選擇`Reuse previous seesion's directory`。

至此，Terminal 應用已經出色的完成了其歷史使命。後面命令列就交給 iTerm2 啦。

在 iTerm2 中雙擊會自動選中對應的詞，三擊會選中對應的整行。選中的內容會自動進入剪貼簿，不需要再按`⌘C`複製。

### [Oh My Zsh](http://ohmyz.sh)

預設的 Bash 是黑白的，沒有色彩。而 Oh My Zsh 可以帶你進入彩色時代。Oh My Zsh 同時提供一套外掛和工具，可以簡化命令列操作。後面我們會看到很多介紹，你會看到我愛死這傢伙了。

安裝方法見官網。

目前我使用的外掛有：`git z sublime history rbenv bundler rake`

Oh My Zsh 使用了 Z shell（zsh），一個和 Bash 相似的 Shell，而非 Bash。

在 Z shell 中，`~/.zshrc`是最重要的配置檔案。Oh My Zsh 在安裝的時候會把當前環境的`$PATH`寫入`~/.zshrc`中。這並不是我期望的行為，因為使用了 brew，我們基本不再需要去定製`$PATH`，而 Oh My Zsh 提供的預設`$PATH`值`$HOME/bin:/usr/local/bin:$PATH`是非常合適的一個值，它把`$HOME/bin`加入了`$PATH`，可以讓我們把自己用的指令碼放到`$HOME/bin`下。

所以建議把`~/.zshrc`重置：

```sh
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```

> [2016年6月17號的一次提交](https://github.com/robbyrussell/oh-my-zsh/commit/551abfcbb48a0c001eadef80abc3276af4e9ad26)後，`zshrc.zsh-template`就不再修改`$PATH`了。請找到`# export PATH=$HOME/bin:/usr/local/bin:$PATH`這一行，把前面的`#`去掉。

Oh My Zsh 還有很多[有價值的外掛](https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins-Overview)。

替代品有 [Oh My Fish](https://github.com/oh-my-fish/oh-my-fish)。基於 [Fishshell](http://fishshell.com/) 。

### [Stow](http://www.gnu.org/software/stow/)

GNU stow 是管理符號連結（symlink）的一個小公舉。主要用於 symlink 你的 [dotfiles](http://dotfiles.github.io/) 如 emacs，git，fish/zsh 的配置檔案。安裝只需要

```
brew install stow
```

安裝了 stow 之後，我們可以開始 symlink 一些 dotfiles 了。完整使用 stow 和 dotfiles 的流程可以參考 <https://github.com/jcouyang/dotfiles>

當你的 dotfiles 都妥妥的 symlink 到 `~/dotfiles` 後，push 到 github 上就再也不怕換電腦了。

### Git 常用別名

幾乎每個人都會使用一些方法比如 Git 別名來提高效率，幾乎所有人都會把使用`git st`來代替`git status`。然而這需要手動設定，每個人也都不完全一樣。

Oh My Zsh 提供了一套系統別名（alias），來達到相同的功能。比如`gst`作為`git status`的別名。而且 Git 外掛是 Oh My Zsh 預設啟用的，相當於你使用了 Oh My Zsh，你就擁有了一套高效率的別名，而且還是全球通用的。是不是棒棒噠？下面是一些我常用的別名：

Alias | Command
----- | -------
gapa  | `git add --patch`
gc!   | `git commit -v --amend`
gcl   | `git clone --recursive`
gclean| `git reset --hard && git clean -dfx`
gcm   | `git checkout master`
gcmsg | `git commit -m`
gco   | `git checkout`
gd    | `git diff`
gdca  | `git diff --cached`
glola | `git log --graph --pretty = format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --all`
gp    | `git push`
grbc  | `git rebase --continue`
gst   | `git status`
gup   | `git pull --rebase`
gwip  | `git add -A; git rm $(git ls-files --deleted) 2> /dev/null; git commit -m "--wip--"`


完整列表請參考：<https://github.com/robbyrussell/oh-my-zsh/wiki/Plugin:git>


### Scroll Reverser

當你在瀏覽一個很長的網頁時，你看完了當前顯示的內容，想要看後續的內容，你可以在 Trackpad 上雙指上滑，或者滑鼠滾輪向上滾動。這是被稱作“自然”的滾動方向。

然而在 Windows 裡滑鼠滾動的行為是相反的：滑鼠滾輪向下滾動才會讓瀏覽器顯示後續的內容，向上滾動會達到頁面的頂部。你可以在 OS X 的系統偏好設定裡修改（選擇`System Preferences` > `Trackpad`，在`Scroll & Zoom`標籤頁中不選中`Scroll direction: natural`），但是這樣會同時改變滑鼠滾輪的方向和 Trackpad 的方向。

要想只改變滑鼠滾輪的方向，而保持 Trackpad 依舊是“自然”的，我們需要 Scroll Reverser：

```sh
brew cask install scroll-reverser
```

PS：這貨會讓三指點選失效

### ShiftIt

原生 OS X 下只能手動調整視窗大小，所以我們需要視窗管理工具。我用過很多視窗管理工具，可惜大部分工具都存在快捷鍵衝突的問題（對我來說主要是 IntelliJ IDEA）。ShiftIt 是少見的沒有衝突的視窗管理工具：

```sh
brew cask install shiftit
```

PS：ShiftIt的舊版本需要安裝 X11，最新版本已經修正了這個問題。

替代者有 SizeUp，主要快捷鍵和 ShiftIt 相同。

當然如果喜歡 hacking，[Slate](https://github.com/jigish/slate)  是個不錯的 hackable 的視窗管理工具。配置可以參照 http://thume.ca/howto/2012/11/19/using-slate/

### Sublime Text 2

安裝：

```sh
brew cask install sublime-text
```

在命令列中指定使用 Sublime Text 開啟某檔案，是一個非常常用的功能，一般我們會按照 [OS X Command Line](https://www.sublimetext.com/docs/2/osx_command_line.html) 中所說執行 `ln -s "/Applications/Sublime Text 2.app/Contents/SharedSupport/bin/subl" ~/bin/subl` 來增加`subl`連結。但是如果你用 brew-cask 安裝的話，恭喜你，你不需要執行這個命令，因為 brew-cask 自動幫你做了這件事情。而且你解除安裝 Sublime Text 的時候 brew-cask 會自動刪掉這個連結。

同時 Oh My Zsh 也提供了 Sublime Text 外掛，叫做`sublime`。參考：<https://github.com/robbyrussell/oh-my-zsh/tree/master/plugins/sublime>，這個外掛和通過 brew-cask 安裝的 Sublime Text 完美相容。

替代品有 Atom、TextMate、Sublime Text 3 等，跟 Sublime Text 2 一樣，用 brew-cask 安裝的話命令列工具會被自動加入`$PATH`。

### MacDown

MacDown 是 Markdown 編輯器。由於 Mou 一直不支援程式碼高亮，我就轉向了 MacDown。完美支援 [GFM](https://help.github.com/articles/github-flavored-markdown/)。

我特別喜歡 [Markdown](https://daringfireball.net/projects/markdown/)，我用 Makdown 來寫文章（包括本文），寫幻燈片（[reveal.js](https://github.com/hakimel/reveal.js/)）。Markdown 可以讓我專注於內容本身，而無需花精力在排版和樣式上。

安裝：

```sh
brew cask install macdown
```

### z

在開啟終端後，你是怎麼進入項目的工作目錄？是`cd xxx`，`⌃R`還是用別名？

[z](https://github.com/rupa/z) 工具可以幫你快速進入目錄。比如在我的 Mac 上執行`z cask`就會進入`/usr/local/Library/Taps/caskroom/homebrew-cask/Casks`目錄。

這貨的安裝非常方便，甚至都不需要下載任何東西，因為它已經整合在了 Oh My Zsh 中。編輯`~/.zshrc`檔案，在`plugins=(git)`這行中加上`z`變成`plugins=(git z)`，然後執行`source ~/.zshrc`重新載入配置檔案，就可以使用 z 了。

替代品有 autojump。autojump 需要使用 brew 安裝。

### [Vimium](https://vimium.github.io/)

Vimium 是一個 Google Chrome 擴充套件，讓你可以純鍵盤操作 Chrome，把你的 Chrome 變成“黑客的瀏覽器”。

安裝方法請參考官方網站。

其他瀏覽器也有類似的工具，比如 FireFox 的 [KeySnail](https://github.com/mooz/keysnail)。

### [LastPass](https://lastpass.com)

LastPass 是管理密碼的工具，支援二次驗證，提供所有瀏覽器外掛以及 Mac 桌面版本。

最重要的是，它提供 **命令列** 的版本，可以直接通過 brew 安裝

```sh
brew install lastpass-cli --with-pinentry
```

之後，只需要登陸：

```sh
lpass login you@email.com
```

就可以拷貝密碼或者整合到其他命令中了：

```sh
lpass show --password gmail.com -c
```

### [SourceTree](https://www.sourcetreeapp.com/)

SourceTree 是 Atlassian 公司出品的一款優秀的 Git 圖形化客戶端。如果你發現命令列無法滿足你的要求，可以試試 SourceTree。

安裝：

```sh
brew cask install sourcetree
```

用 brew-cask 安裝會自動增加命令列工具`stree`到`$PATH`裡。在命令列中輸入`stree`可以快速用 SourceTree 開啟當前 Git 倉庫。詳細用法請參見`stree --help`。

### [CheatSheet](http://www.mediaatelier.com/CheatSheet/)

CheatSheet 能夠顯示當前程式的快捷鍵列表，預設的快捷鍵是長按`⌘`。

![CheatSheet](http://www.mediaatelier.com/CheatSheet/imgs/main.png)

安裝：

```sh
brew cask install cheatsheet
```

### [Alfred](https://www.alfredapp.com)

Mac 使用者不用滑鼠鍵盤的必備神器，配合大量 Workflows，習慣之後可以大大減少操作時間。

上手簡單，調教成本在後期自定義 Workflows，不過有大量雷鋒使用者提供的現成擴充套件，訪問[這裡](http://www.alfredworkflow.com/)挑選喜歡的，並可以極其簡單地根據自己的需要修改。

安裝：

```sh
brew cask install alfred
```

## 3. 開發工具

### Java

現在 OS X 都不會自帶 JDK 了，所以進行 Java 開發的話，需要下載 JDK。在 brew-cask 之前，我們需要從 <https://developer.apple.com/downloads/> 或者 Oracle 網站上下載。還有更麻煩的－－解除安裝 JDK 和升級 JDK。

JDK 安裝檔案是 pkg 格式，解除安裝和`.app`不一樣，且沒有自動解除安裝方式。

而 brew-cask 提供了自動安裝和解除安裝功能，能夠自動從官網上下載並安裝 JDK 8。

```sh
brew cask install java
```

如果你需要安裝 JDK 7 或者 JDK 6，可以使用`homebrew-cask-versions`：

```sh
brew tap caskroom/versions
brew cask install java6
```

在 OS X 上，你可以同時安裝多個版本的 JDK。你可以通過命令`/usr/libexec/java_home -V`來檢視安裝了哪幾個 JDK。

那問題來了，當你執行`java`或者 Java 程式時使用的是哪個 JDK 呢？在 OS X 下，`java`也就是`/usr/bin/java`在預設情況下指向的是已經安裝的最新版本。但是你可以設定環境變數`JAVA_HOME`來更改其指向：

```sh
$ java -version
java version "1.8.0_60"
Java(TM) SE Runtime Environment (build 1.8.0_60-b27)
Java HotSpot(TM) 64-Bit Server VM (build 25.60-b23, mixed mode)
$ JAVA_HOME=/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home java -version
java version "1.6.0_65"
Java(TM) SE Runtime Environment (build 1.6.0_65-b14-466.1-11M4716)
Java HotSpot(TM) 64-Bit Server VM (build 20.65-b04-466.1, mixed mode)
```

其中`JAVA_HOME=/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home`可以用`` JAVA_HOME=`/usr/libexec/java_home -v 1.6` ``這種更加通用的方式代替。

### [jEnv](https://github.com/gcuisinier/jenv)

也可以使用 jEnv 來管理不同版本的 JDK，這個工具跟 [rbenv](#rbenv) 類似，通過當前目錄下的`.java-version`來決定使用哪個 JDK。jEnv 也可以用 brew 安裝。不過要使用 jEnv 要有幾個問題：

- 需要手動把`eval "$(jenv init -)"`加入 profile，沒有 Oh My Zsh 外掛。這點是我非常反感的。

  可以把`eval "$(jenv init -)"`加入`~/.zlogin`，這樣可以避免修改`~/.zshrc`。
- 需要手動新增 JDK，不會自動採集系統 JDK。跟 Ruby 不同，OS X 已經提供`/usr/libexec/java_home`工具來管理安裝的 JDK。
- 需要 `jenv rehash`。這個是跟 rbenv 學的。

所以我建議不要使用 jEnv。

### 民間使用的 Java 版本切換方法

新增以下指令碼到當前 shell 配置檔案中：`~/.zprofile`或者`~/.bash_profile`。

```sh
function setjdk() {
    export JAVA_HOME=`/usr/libexec/java_home -v $@`
}
```
這樣我們就可以通過輸入一條命令進行版本切換了：

```sh
setjdk 1.8
```

### Java[OCD]

作為一個強迫症患者，每當我看到 Java 的錯誤寫法就想糾正過來。

當指程式語言時，Java 的正確寫法是首字母大寫，其餘小寫。其他寫法比如`JAVA`、`java`都是不對的。

在其他一些地方會使用小寫的`java`：

- `java`命令
- 原檔案`Main.java`
- 包名`java.lang`

只有在全大寫的標題裡使用`JAVA`或者環境變數`JAVA_HOME`。

### IntelliJ IDEA

Java 開發必備工具 IntelliJ IDEA。可以安裝 Ultimate Edition：

```sh
brew cask install intellij-idea
```

也可以安裝開源免費的 Community Edition：

```sh
brew cask install intellij-idea-ce
```

IntelliJ IDEA 有幾套內建的快捷鍵方案（Keymap）。其中適用於 OS X 的有`Mac OS X`和`Mac OS X 10.5+`兩種。區別是:

- `Mac OS X`方案和其他平臺上的快捷鍵類似，
- 而`Mac OS X 10.5+`更加符合 OS X 常用的快捷鍵。

一個團隊使用不同的快捷鍵會嚴重影響效率。可以用`View | Quick Switch Scheme`（`⌃ Back Quote`）快速切換 Keymap。

如果可以選擇的話，我建議使用`Mac OS X`方案。因為我經常遇到使用 Windows 的客戶，而 Windows 平臺上的快捷鍵和`Mac OS X`方案類似。

可以從 IDEA 的`Help > Default Keymap Reference`開啟快捷鍵的參考手冊。不過從這裡開啟的是`Mac OS X 10.5+`方案的，而`Mac OS X`方案的可以從這裡找到：<http://www.basrikahveci.com/static/ij_keymap_mac.pdf>。

### [rbenv](https://github.com/sstephenson/rbenv)

人人都需要一個 Ruby 版本管理工具。rbenv 就是這樣一個輕量級工具，它可以通過 brew 安裝。

安裝：

```sh
brew install rbenv ruby-build
```

然後在`~/.zshrc`中加上`rbenv`外掛。否則你需要手動新增`eval "$(rbenv init -)"`到`~/zshrc`或者`~/.zprofile`檔案裡。

有時候項目會依賴一些奇怪的版本號，比如`ruby-2.1.0`，這個時候你需要 [rbenv-aliases](https://github.com/tpope/rbenv-aliases) 幫忙：

```sh
brew install rbenv-aliases
```

替代品有 RVM、chruby。因為 RVM 不能通過 brew 安裝，並且安裝的時候會沒有節操的修改一堆檔案，所以被我早早的棄用了。chruby 也是一個輕量級工具，而且可以完美的和 Oh My Zsh 整合在一起，我看到有些生產環境在用它。

### Ruby 常用別名

幾乎所有 Ruby 開發人員都會把`bi`作為`bundle install`的別名。Oh My Zsh 提供`builder`外掛，這個外掛提供了一套別名，比如`bi`、`be`。同時還能讓你在執行一些常用 gem 的時候直接輸入`rspec`，不需要`be rspec`這樣了。具體包括哪些命令請參考[這裡](https://github.com/robbyrussell/oh-my-zsh/tree/master/plugins/bundler)。

Z shell 對於`[`和`]`符號有特殊的處理，所以在執行`rake task[parameter]`的時候會報錯，你需要改成`rake task\[parameter\]`或者`noglob rake task[parameter]`。然而 Oh My Zsh 已經看穿這一切，自帶的 rake 外掛已經解決了這個問題：`brake task[parameter]`。

新增外掛的時候注意把`rake`放到`bundler`後面，例如這樣：

```
plugins=(git z sublime history rbenv bundler rake)
```

## 參考資料

- [Hacker's Guide to Setting up Your Mac](http://lapwinglabs.com/blog/hacker-guide-to-setting-up-your-mac)
- [Setting up a new (OS X) development machine](https://mattstauffer.co/blog/setting-up-a-new-os-x-development-machine-part-1-core-files-and-custom-shell)
- [高效 MacBook 工作環境配置](http://www.xialeizhou.com/?p=71)
- [程式設計師如何優雅地使用 Mac？](http://www.zhihu.com/question/20873070)
- [裝點你的 Dock：外觀篇](http://sspai.com/33493)

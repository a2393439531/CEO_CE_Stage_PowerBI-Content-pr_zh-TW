<properties 
pageTitle="安裝並設定工具以在 GitHub 中進行撰寫" 
description="工具和步驟，以便開始撰寫 Power BI 內容在 GitHub 中的設定。" 
services="contributor-guide" 
documentationCenter="" 
authors="mblythe"  
manager="dongill" />

<tags 
ms.service="contributor-guide"
 ms.devlang="" 
 ms.topic="article"
  ms.tgt_pltfrm="" 
  ms.workload="" 
  ms.date="09/09/2015" 
  ms.author="mblythe" />

#安裝並設定工具以在 GitHub 中進行撰寫

請依照這篇文章，以設定參與的 Power BI 的技術文件的工具。 休閒和偶爾參與者可能可以使用 GitHub 中步驟 2 所述的 UI。

如果您不熟悉 Git，您可能想要想要檢閱一些 Git 術語：[https://help.github.com/articles/github-glossary](https://help.github.com/articles/github-glossary)。 此外，這個 StackOverflow 執行緒包含這組步驟中，您會遇到的 Git 名詞解釋︰ [http://stackoverflow.com/questions/7076164/terminology-used-by-git](http://stackoverflow.com/questions/7076164/terminology-used-by-git)

## Contents

- [建立 GitHub 帳戶並設定您的設定檔](#create-a-github-account-and-set-up-your-profile)
- [申請 Disqus](#sign-up-for-disqus)
- [判斷您是否真的需要遵循這些步驟的其餘部分](#determine-whether-you-really-need-to-follow-the-rest-of-these-steps)
- [GitHub 中的權限](#permissions-in-github)
- [安裝 Git for Windows](#install-git-for-windows)
- [啟用雙因素驗證](#enable-two-factor-authentication)
- [安裝 Markdown 編輯器](#install-a-markdown-editor)
- [設定 Atom](#configure-atom)
- [分岔儲存機制，並將它複製到您的電腦](#fork-the-repository-and-copy-it-to-your-computer)
- [設定您的本機使用者名稱和電子郵件](#configure-your-user-name-and-email-locally)
- [後續步驟](#next-steps)

## 建立 GitHub 帳戶並設定您的設定檔

若要對 Power BI 技術內容，您必須 [GitHub](http://www.github.com) 帳戶。

如果您是 Microsoft 參與者，您需要設定您的 GitHub 帳戶，讓您清楚地識別身為 Microsoft 員工。 設定您的設定檔，如下所示︰

- 
            **設定檔圖片**：您的圖片 (必要)
- 
            **名稱**：您的名字和姓氏 (必要)
- 
            **電子郵件**︰ 您的 Microsoft 電子郵件地址 （必要）
- 
            **公司**: Microsoft Corporation （必要）
- 
            **位置**：列出您的位置 (必要)

您的設定檔應類似於此設定檔：

<p align="center">
 ![GitHub 設定檔範例](./media/tools-and-setup/githubprofile.png)

## 申請 Disqus

每個已發行的 Power BI 技術的文章內含 Disqus 服務所提供的註解資料流。

 ![繼續討論標誌](./media/tools-and-setup/discus.png)

如果您為 Microsoft 員工，而且如果您的作者或參與者的文章，您需要註冊 Disqus 讓您可以參與文件的註解資料流。

1. 登入帳戶在 [http://www.disqus.com/](http://www.disqus.com/)
2. 填妥您的設定檔，如下所示︰

 - 
            **完整名稱**︰ 您的全名與顯示在您的清單，再加上括號括住的資訊，其為您的別名加 @MSFT Microsoft 通訊錄中。 格式︰ *先最後一個 [alias@MSFT]*
 - 
            **位置**︰ 您的部署位置
 - 
            **簡短簡歷**︰ 您的標題

## 判斷您是否真的需要遵循這些步驟的其餘部分

您可能不需要遵循本文中的所有步驟。 這取決於您想要或需要進行內容投稿的排序。

###送出至現有的發行項的純文字變更

如果您只需要或想要讓現有的發行項中文字的更新，您可能不需要遵循其餘的步驟。 您可以使用 GitHub 的 web 架構的 markdown 編輯器提交您的變更。 只要按一下您想要修改的文件中的 [GitHub] 連結︰

 ![GitHub 設定檔範例](./media/tools-and-setup/contributetogit.png)

 然後，按一下 [發行項的 GitHub 版中的 [編輯] 圖示

 ![GitHub 設定檔範例](./media/tools-and-setup/editicon.PNG)

 如此會開啟方便使用 web 編輯器，以簡化將變更送出。 您不需要遵循本文中的其他步驟。

###所有其他變更
您需要安裝工具，如果您想要進行任何下列類型的變更︰

 - 發行項的主要變更
 - 建立及發行新的發行項
 - 加入新的映像或更新映像
 - 經過一段天未發行變更每個這些發行日的更新發行項

 請移至下一節 ！

##GitHub 中的權限

透過我們公開的儲存機制，在 Power BI 技術內容有 GitHub 帳戶具有的任何人都可能導致 [https://github.com/azure/powerbi-content](https://github.com/azure/powerbi-content)。 不需要任何特殊權限。

> [AZURE.NOTE] Powerbi 內容儲存機制會私用，否則在進一步通知。 您應該使用 powerbi-內容-pr 儲存機制。

如果您是 Microsoft 的員工使用 Power BI 內容時，您應該在我們的私用內容儲存機制，powerbi-內容-pr。 請瀏覽 [http://aka.ms/azuregithub](http://aka.ms/azuregithub) 若要取得讀取權限可讓您做出貢獻透過私用儲存機制中-按一下 **團隊一起**, ，和聯結 **定域機組企業讀取**。

## 安裝 Git for Windows

安裝 Git，從 windows [http://git-scm.com/download/win](http://git-scm.com/download/win)。 此下載會安裝 Git 版本控制系統，並安裝 Git Bash，這是您可以用來與您的本機 Git 儲存機制互動的命令列 app。

您可以接受預設設定。如果您想用於 Windows 命令列命令，請，選取選項，讓它。

<p align="center">
 ![GitHub 設定檔範例](./media/tools-and-setup/gitbashinstall.png)

(請注意︰ 這不是 「 Github for Windows 」 相同。 "Github for Windows" 是一個也能運作的不同的 GUI 型工具，如果您想要自行閱讀，請造訪下列位置： 
            [https://windows.github.com/](https://windows.github.com/)) 

## 啟用雙因素驗證

您必須啟用兩個因素驗證 (2FA) 在您的 GitHub 帳戶上如果您使用的私用內容儲存機制中。 您需要在專用的儲存機制中。

若要啟用此功能，請依照下列兩個 GitHub 說明主題中的指示︰

- [有關雙因素驗證](https://help.github.com/articles/about-two-factor-authentication/)
- [建立命令列使用的存取權杖](https://help.github.com/articles/creating-an-access-token-for-command-line-use/)

啟用 2FA 之後，您必須輸入存取權杖，而不是您的 GitHub 密碼，在命令提示字元中，當您嘗試從命令列存取 GitHub 儲存機制。 存取權杖不是當您設定 2FA 取得文字訊息的驗證碼。 它會類似如下的長字串︰ fdd3b7d3d4f0d2bb2cd3d58dba54bd6bafcd8dee。 關於這的一些注意事項︰

- 當您建立存取權杖時，請將它儲存在文字檔案，讓它可立即存取在需要時。

- 稍後，當您需要將語彙基元，知道有兩種方式可以在命令列中貼上︰

 - 按一下命令列視窗左上角的圖示 > 編輯 > 貼。
 - 在視窗的左上角的圖示上按一下滑鼠右鍵，然後按一下 [內容 > 選項 > 快速編輯模式。 這會設定命令列，因此您可以貼上以滑鼠右鍵按一下命令列視窗中。

## 安裝 Markdown 編輯器

我們撰寫內容，而在檔案中，使用簡單的 「 markdown 」 標記法比複雜 「 標記 」 （HTML、 XML 等）。 因此，您將需要安裝 markdown 編輯器。

- 
            **Atom**︰ 大多數人使用 GitHub 的 Atom markdown 編輯器︰ [http://atom.io](http://atom.io)。 它不需要為商業使用授權。 它具有拼字檢查。 

- 
            **記事本**：針對輕量型的選項，可以使用 [記事本]。

- 
            **Prose**：這是可提供預覽的一個輕量型、簡潔、線上和開放原始碼的 Markdown 編輯器。 請瀏覽 [http://prose.io](http://prose.io) 並在您的儲存機制中授權 Prose。

- 
            **
            [Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx)** - Microsoft 在此處的入口。

## 設定 Atom

如果您使用 Atom，您需要設定幾件事。

- Atom 預設會使用 2 個空格做為定位點，但是 Markdown 預期是 4 個空格。 如果您將兩個預設值，您的文章會看起來漂亮在本機預覽中，但不是當匯入 Power BI。 因此，設定要使用 4 個空格 Atom-您可以在檔案中找到這項設定 > 設定 > 編輯器設定 >] 索引標籤的長度。 
- 您可能也想要開啟該段落中的 Soft Wrap，這與 [記事本] 中的「自動換行」意思相同。 
- 若要開啟 markdown 預覽，按一下 [封裝 > Markdown 預覽 > 切換預覽。 您可以使用 Ctrl-Shift-M 切換預覽 HTML 檢視。 

## 分岔儲存機制，並將它複製到您的電腦

1. 在 GitHub 中建立儲存機制的 「 分叉 」: 移至頁面的右上方，然後按一下 [分支] 按鈕。 如果出現提示，請選取您的帳戶做為建立分叉的所在位置。 這會建立 Git 中心帳戶內儲存機制的複本。 一般而言，技術的寫入器和程式管理員需要分岔 powerbi-內容-出版品私用儲存機制。 社群貢獻者需要分岔 powerbi 內容，公用儲存機制。 您只需要將分岔一次。您第一次安裝之後，如果您想要將您的 「 分叉 」 複製到另一部電腦，您只需要執行的命令，請遵循本節中，將儲存機制複製到您的電腦中。  如果您選擇建立這兩個儲存機制分支，您必須建立的每個儲存機制的 「 分叉 」。

2. 複製個人存取權杖，所得 [https://github.com/settings/applications#personal-access-tokens](https://github.com/settings/applications#personal-access-tokens)。 您可以接受語彙基元的預設權限。  將儲存個人的存取權杖，供日後重複使用文字檔案中。

3. 接下來，複製到您的電腦使用您的認證儲存機制嵌入命令字串。  若要這樣做，請開啟 GitBash。  在命令提示字元中輸入以下命令。  此命令會在您的電腦上建立 powerbi-content(-pr) drectory。  如果您使用的預設位置，它將會位於 c:\users<your Windows user name>\powerbi-content(-pr)。

公用的儲存機制︰

        git clone https://[your GitHub user name]:[token]@github.com/<your GitHub user name>/powerbi-content.git

私用儲存機制︰

        git clone https://[your GitHub user name]:[token]@github.com/<your GitHub user name>/powerbi-content-pr.git

例如，此複製命令看起來可能像這樣︰

        git clone https://smithj:b428654321d613773d423ef2f173ddf4a312345@github.com/smithj/powerbi-content-pr.git  

## 設定遠端儲存機制連接並設定認證

輸入下列命令建立根存放庫的參考。 這會設定連線至 github 儲存機制，可讓您可以取得最新的變更到本機電腦，並回到您的變更發送至 GitHub。 在本機，讓您不必每次您嘗試存取的上游的儲存機制和分叉 GitHub 上的輸入您的名稱和密碼，此命令也會設定您的權杖。

公用的儲存機制︰

        cd powerbi-content
        git remote add upstream https://[your GitHub user name]:[token]@github.com/azure/powerbi-content.git
        git fetch upstream

私用儲存機制︰

        cd powerbi-content-pr
        git remote add upstream https://[your GitHub user name]:[token]@github.com/azure/powerbi-content-pr.git
        git fetch upstream

這通常需要一些時間。 執行這項操作之後，就不必再分叉或再次輸入認證。 您只必須分支到本機電腦上重新複製如果您在另一部電腦上設定的工具。


## 設定您的本機使用者名稱和電子郵件

若要確保您以參與者身分正確列出，您需要在 Git 中本機設定您的使用者名稱和電子郵件。

1. 啟動 Git Bash，並切換至 powerbi 內容或 pr-powerbi-內容︰

   ````
   cd powerbi-content
   ````

 或

   ````
   cd powerbi-content-pr
   ````

2. 設定您的使用者名稱，使它符合您在 GitHub 設定檔中設定的名稱：

    ````
    git config --global user.name "John Doe"
    ````
3. 設定您的電子郵件，讓它符合 GitHub 設定檔; 中指定的主要電子郵件如果您是 MSFT 員工時，它應該 MSFT 的電子郵件地址︰

    ````
    git config --global user.email "alias@example.com"
    ````
4. 輸入 `git config -l` 並檢閱您的本機設定，以確保設定中的使用者名稱和電子郵件正確。

##後續步驟

- 
            [建立本機工作分支](./git-commands-for-master.md) 上您的電腦，因此您可以開始工作。
- 複製 [markdown 範本](../markdown templates/markdown-template-for-new-articles.md) 做為新的發行項的基礎。





###著作指南的連結

- [概觀文章](./../README.md)
- [指引文章的索引](./contributor-guide-index.md)



<!--Anchors-->
[使用適合客戶的聲音]: #use-a-customer-friendly-voice
[請考慮當地語系化和機器翻譯]: #consider-localization-and-machine-translation
[監看的其他樣式和聲音問題]: #other-style-and-voice-issues-to-watch-for


[建立 GitHub 帳戶並設定您的設定檔]: #create-a-github-account-and-set-up-your-profile
[判斷您是否真的需要遵循這些步驟的其餘部分]: #determine-whether-you-really-need-to-follow-the-rest-of-these-steps
[GitHub 中的權限]: #permissions-in-github
[安裝 Git for Windows]: #install-git-for-windows
[啟用雙因素驗證]: #enable-two-factor-authentication
[安裝 Markdown 編輯器]: #install-a-markdown-editor
[分岔儲存機制，並將它複製到您的電腦]: #fork-the-repository-and-copy-it-to-your-computer
[安裝 git-認證-winstore]: #install-git-credential-winstore
[申請 Disqus]: #sign-up-for-disqus
[設定您的本機使用者名稱和電子郵件]: #configure-your-user-name-and-email-locally
[後續步驟]: #next-steps

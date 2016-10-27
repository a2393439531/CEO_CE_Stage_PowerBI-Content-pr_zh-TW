<properties 
pageTitle="安裝並設定工具以在 GitHub 中進行撰寫" 
description="Tools and steps to get set up for authoring Power BI content in GitHub." 
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

Follow the steps in this article to set up tools for contributing to the Power BI technical documentation. Casual and occasional contributors probably can use the GitHub UI described in step 2.

如果您不熟悉 Git，您可能想要想要檢閱一些 Git 術語：[https://help.github.com/articles/github-glossary](https://help.github.com/articles/github-glossary)。 In addition, this StackOverflow thread contains a glossary of Git terms you'll encounter in this set of steps: <bpt id="p1">[</bpt>http://stackoverflow.com/questions/7076164/terminology-used-by-git<ept id="p1">](http://stackoverflow.com/questions/7076164/terminology-used-by-git)</ept>

## Contents

- [建立 GitHub 帳戶並設定您的設定檔](#create-a-github-account-and-set-up-your-profile)
- [Sign up for Disqus](#sign-up-for-disqus)
- [Determine whether you really need to follow the rest of these steps](#determine-whether-you-really-need-to-follow-the-rest-of-these-steps)
- [GitHub 中的權限](#permissions-in-github)
- [安裝 Git for Windows](#install-git-for-windows)
- [啟用雙因素驗證](#enable-two-factor-authentication)
- [安裝 Markdown 編輯器](#install-a-markdown-editor)
- [設定 Atom](#configure-atom)
- [Fork the repository and copy it to your computer](#fork-the-repository-and-copy-it-to-your-computer)
- [設定您的本機使用者名稱和電子郵件](#configure-your-user-name-and-email-locally)
- [後續步驟](#next-steps)

## 建立 GitHub 帳戶並設定您的設定檔

To contribute to the Power BI technical content, you'll need a <bpt id="p1">[</bpt>GitHub<ept id="p1">](http://www.github.com)</ept> account.

If you are a Microsoft contributor, you need to set up your GitHub account so you're clearly identified as a Microsoft employee. Set up your profile as follows:

- 
            **設定檔圖片**：您的圖片 (必要)
- 
            **名稱**：您的名字和姓氏 (必要)
- <bpt id="p1">**</bpt>Email<ept id="p1">**</ept>: your Microsoft email address (required)
- <bpt id="p1">**</bpt>Company<ept id="p1">**</ept>: Microsoft Corporation (required)
- 
            **位置**：列出您的位置 (必要)

您的設定檔應類似於此設定檔：

<p align="center">
 ![GitHub 設定檔範例](./media/tools-and-setup/githubprofile.png)

## Sign up for Disqus

Every published Power BI technical article has a comment stream provided by the Disqus service.

 ![Discus logo](./media/tools-and-setup/discus.png)

If you are a Microsoft employee, and if you are the author of or a contributor to an article, you need to sign up for Disqus so you can participate in the comment stream for the article.

1. Sign up for an account at <bpt id="p1">[</bpt>http://www.disqus.com/<ept id="p1">](http://www.disqus.com/)</ept>
2. Fill out your profile as follows:

 - <bpt id="p1">**</bpt>Full Name<ept id="p1">**</ept>: your full name as displayed in your Microsoft address book listing, plus the bracketed info, which is your alias plus @MSFT. Format: <bpt id="p1">*</bpt>First Last [alias@MSFT]<ept id="p1">*</ept>
 - <bpt id="p1">**</bpt>Location<ept id="p1">**</ept>: Your location
 - <bpt id="p1">**</bpt>Short Bio<ept id="p1">**</ept>: Your title

## Determine whether you really need to follow the rest of these steps

You might not need to follow all the steps in this article. It depends on the sort of content contribution you want or need to make.

###Submit a text-only change to an existing article

If you only need or want to make textual updates to an existing article, you probably don't need to follow the rest of the steps. You can use GitHub's web-based markdown editor to submit your changes. Just click the GitHub link in the article you want to modify:

 ![GitHub 設定檔範例](./media/tools-and-setup/contributetogit.png)

 Then, click the edit icon in the GitHub version of the article

 ![GitHub 設定檔範例](./media/tools-and-setup/editicon.PNG)

 That opens the easy-to-use web editor that makes it easy to submit changes. You don't need to follow the other steps in this article.

###All other changes
You need to install the tools if you want to make any of the following sorts of changes:

 - Major changes to an article
 - Create and publish a new article
 - Add new images or update images
 - Update an article over a period of days without publishing changes each of those days

 Go to the next section!

##GitHub 中的權限

Anybody with a GitHub account can contribute to Power BI technical content through our public repository at <bpt id="p1">[</bpt>https://github.com/azure/powerbi-content<ept id="p1">](https://github.com/azure/powerbi-content)</ept>. 不需要任何特殊權限。

> [AZURE.NOTE] The powerbi-content repo will be private until further notice. You should work in the powerbi-content-pr repo.

If you are a Microsoft employee working on Power BI content, you should work in our private content repository, powerbi-content-pr. Visit <bpt id="p1">[</bpt>http://aka.ms/azuregithub<ept id="p1">](http://aka.ms/azuregithub)</ept> to obtain the read permissions that will let you make contributions through the private repo - click <bpt id="p2">**</bpt>Join a Team<ept id="p2">**</ept>, and join <bpt id="p3">**</bpt>cloud-enterprise-read<ept id="p3">**</ept>.

## 安裝 Git for Windows

Install Git for Windows from <bpt id="p1">[</bpt>http://git-scm.com/download/win<ept id="p1">](http://git-scm.com/download/win)</ept>. 此下載會安裝 Git 版本控制系統，並安裝 Git Bash，這是您可以用來與您的本機 Git 儲存機制互動的命令列 app。

You can accept the default settings; if you want the commands to be available within the Windows command line, select the option that enables it.

<p align="center">
 ![GitHub 設定檔範例](./media/tools-and-setup/gitbashinstall.png)

(Note: This is not the same as "Github for Windows". "Github for Windows" 是一個也能運作的不同的 GUI 型工具，如果您想要自行閱讀，請造訪下列位置： 
            [https://windows.github.com/](https://windows.github.com/)) 

## 啟用雙因素驗證

You have to enable two factor authentication (2FA) on your GitHub account if you are working in the private content repository. It's required in the private repository.

To enable this, follow the instructions in both the following GitHub help topics:

- [有關雙因素驗證](https://help.github.com/articles/about-two-factor-authentication/)
- [Creating an access token for command-line use](https://help.github.com/articles/creating-an-access-token-for-command-line-use/)

After you enable 2FA, you have to enter the access token instead of your GitHub password at the command prompt when you try to access a GitHub repository from the command line. The access token is not the authentication code that you get in a text message when you set up 2FA. It's a long string that looks something like this:  fdd3b7d3d4f0d2bb2cd3d58dba54bd6bafcd8dee. A few notes about this:

- When you create your access token, save it in a text file to make it readily accessible when you need it.

- Later, when you need to paste the token, know there are two ways to paste in the command line:

 - Click the icon in the upper left corner of the command line window&gt;Edit&gt;Paste.
 - Right-click the icon in the upper left corner of the window and click Properties&gt;Options&gt;QuickEdit Mode. This configures the command line so you can paste by right-clicking in the command line window.

## 安裝 Markdown 編輯器

We author content using simple "markdown" notation in the files, rather than complex "markup" (HTML, XML, etc.). So, you'll need to install a markdown editor.

- <bpt id="p1">**</bpt>Atom<ept id="p1">**</ept>: Most of us use GitHub's Atom markdown editor: <bpt id="p2">[</bpt>http://atom.io<ept id="p2">](http://atom.io)</ept>. It does not require a license for business use. It has spell check. 

- 
            **記事本**：針對輕量型的選項，可以使用 [記事本]。

- 
            **Prose**：這是可提供預覽的一個輕量型、簡潔、線上和開放原始碼的 Markdown 編輯器。 請瀏覽 [http://prose.io](http://prose.io) 並在您的儲存機制中授權 Prose。

- 
            **
            [Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx)** - Microsoft 在此處的入口。

## 設定 Atom

如果您使用 Atom，您需要設定幾件事。

- Atom 預設會使用 2 個空格做為定位點，但是 Markdown 預期是 4 個空格。 If you leave it at the default of two, your article will look great in local preview, but not when it’s imported into Power BI. So, configure Atom to use 4 spaces - you can find this setting under File&gt;Settings&gt;Editor Settings&gt;Tab Length. 
- 您可能也想要開啟該段落中的 Soft Wrap，這與 [記事本] 中的「自動換行」意思相同。 
- To turn on the markdown preview, click Packages&gt;Markdown Preview&gt;Toggle Preview. 您可以使用 Ctrl-Shift-M 切換預覽 HTML 檢視。 

## Fork the repository and copy it to your computer

1. Create a fork of the repository in GitHub - go to the top-right of the page and click the Fork button. If prompted, select your account as the location where the fork should be created. This creates a copy of the repository within your Git Hub account. Generally speaking, technical writers and program managers need to fork powerbi-content-pr, the private repo. Community contributors need to fork powerbi-content, the public repo. You only need to fork one time; after your first setup, if you want to copy your fork to another computer, you only have to run the commands that follow in this section to copy the repo to your computer.  If you choose to create forks of both repositories, you will need to create a fork for each repository.

2. Copy the Personal Access Token that you got from <bpt id="p1">[</bpt>https://github.com/settings/applications#personal-access-tokens<ept id="p1">](https://github.com/settings/applications#personal-access-tokens)</ept>. You can accept the default permissions for the token.  Save the Personal Access Token in a text file for later reuse.

3. Next, copy the repository to your computer with your credentials embedded in the command string.  To do this, open GitBash.  在命令提示字元中輸入以下命令。  This command creates a powerbi-content(-pr) drectory on your computer.  If you're using the default location, it will be at c:\users<ph id="ph1">&lt;your Windows user name&gt;</ph>\powerbi-content(-pr).

Public repo:

        git clone https://[your GitHub user name]:[token]@github.com/<your GitHub user name>/powerbi-content.git

Private repo:

        git clone https://[your GitHub user name]:[token]@github.com/<your GitHub user name>/powerbi-content-pr.git

For example, this clone command could look something like this:

        git clone https://smithj:b428654321d613773d423ef2f173ddf4a312345@github.com/smithj/powerbi-content-pr.git  

## 設定遠端儲存機制連接並設定認證

Create a reference to the root repository by entering these commands. This sets up connections to the repository in GitHub so that you can get the latest changes onto your local machine and push your changes back to GitHub. This command also configures your token locally so that you don't have to enter your name and password each time you try to access the upstream repo and your fork on GitHub.

Public repo:

        cd powerbi-content
        git remote add upstream https://[your GitHub user name]:[token]@github.com/azure/powerbi-content.git
        git fetch upstream

Private repo:

        cd powerbi-content-pr
        git remote add upstream https://[your GitHub user name]:[token]@github.com/azure/powerbi-content-pr.git
        git fetch upstream

這通常需要一些時間。 After you do this, you won't have to fork again or enter your credentials again. You would only have to copy the forks to a local computer again if you set the tools up on another computer.


## 設定您的本機使用者名稱和電子郵件

若要確保您以參與者身分正確列出，您需要在 Git 中本機設定您的使用者名稱和電子郵件。

1. Start Git Bash, and switch into powerbi-content or powerbi-content-pr:

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
3. Configure your email so it matches the primary email designated in your GitHub profile; if you're a MSFT employee, it should be your MSFT email address:

    ````
    git config --global user.email "alias@example.com"
    ````
4. 輸入 `git config -l` 並檢閱您的本機設定，以確保設定中的使用者名稱和電子郵件正確。

##後續步驟

- <bpt id="p1">[</bpt>Create a local working branch<ept id="p1">](./git-commands-for-master.md)</ept> on your computer so you can start work.
- Copy <bpt id="p1">[</bpt>the markdown template<ept id="p1">](../markdown templates/markdown-template-for-new-articles.md)</ept> as the basis for a new article.





###Contributors' Guide Links

- [概觀文章](./../README.md)
- [指引文章的索引](./contributor-guide-index.md)



<!--Anchors-->
[Use a customer-friendly voice]: #use-a-customer-friendly-voice
[Consider localization and machine translation]: #consider-localization-and-machine-translation
[other style and voice issues to watch for]: #other-style-and-voice-issues-to-watch-for


[建立 GitHub 帳戶並設定您的設定檔]: #create-a-github-account-and-set-up-your-profile
[Determine whether you really need to follow the rest of these steps]: #determine-whether-you-really-need-to-follow-the-rest-of-these-steps
[GitHub 中的權限]: #permissions-in-github
[安裝 Git for Windows]: #install-git-for-windows
[啟用雙因素驗證]: #enable-two-factor-authentication
[安裝 Markdown 編輯器]: #install-a-markdown-editor
[Fork the repository and copy it to your computer]: #fork-the-repository-and-copy-it-to-your-computer
[Install git-credential-winstore]: #install-git-credential-winstore
[Sign up for Disqus]: #sign-up-for-disqus
[設定您的本機使用者名稱和電子郵件]: #configure-your-user-name-and-email-locally
[後續步驟]: #next-steps

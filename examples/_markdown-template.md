<properties
   pageTitle="在瀏覽器] 索引標籤，並搜尋結果中顯示的頁面標題"
   description="將會顯示在登陸頁面和大部分搜尋結果中的文章描述"
   services="service-name"
   documentationCenter="dev-center-name"
   authors="GitHub-alias-of-only-one-author"
   manager="manager-alias"
   editor=""/>

<tags
   ms.service="required"
   ms.devlang="may be required"
   ms.topic="article"
   ms.tgt_pltfrm="may be required"
   ms.workload="required"
   ms.date="mm/dd/yyyy"
   ms.author="Your MSFT alias or your full email address;semicolon separates two or more"/>

# Markdown 範本 （文件標題 1] 或 [H1）︰ 在發行項的最上方的標題

若要從這個範本複製 markdown，複製您的本機儲存機制中的文件或按一下 GitHub UI 的 [原始] 按鈕，複製 markdown。

  ![替代文字。不要讓空白。 描述映像。][8]

簡介段落︰ Lorem dolor amet，adipiscing elit。 Phasellus interdum nulla risus，lacinia 聲明您 imperdiet sed. Mauris dolor mauris 新 sed lacinia nec，euismod 非 felis。 歡 semper 聲明 ultrices。 Maecenas neque nulla condimentum vitae ipsum sit amet，dignissim aliquet nisi。

## 標題 2 (h 2)

Aenean sit amet leo nec purus placerat fermentum ac gravida odio。 在中 faucibus sed urna rhoncus faucibus Aenean tellus lectus。  volutpat 英哩識別碼 purus ultrices iaculis nec 非 neque。 
            [連結文字連結以外 azure.microsoft.com](http://weblogs.asp.net/scottgu)。 在 aliquam pharetra Nullam dictum dolor。 Vivamus ac hendrerit mauris [服務資料夾中的文章連結的範例連結文字](../articles/expressroute/expressroute-bandwidth-upgrade.md)。

取得從 10 倍以上流量 [Google] [gog] 比從 [Yahoo] [yah] 或 [MSN] [msn]。

> [AZURE.NOTE] 縮排的註解文字。  在發行期間，將會加入 '注意事項 」 這個字。 Ut eu pretium lacus。 Nullam purus est，iaculis sed est vel、 euismod vehicula odio。 Curabitur lacinia、 erat tristique iaculis rutrum、 erat sem sodales nisi、 歐盟 condimentum turpis nisi purus。

1. Aenean sit amet leo nec **Purus** placerat fermentum ac gravida odio。

2. Aenean tellus lectus 中 faucius **Rhoncus** faucibus sed urna 中。 Suspendisse volutpat 英哩識別碼 purus ultrices iaculis nec 非 neque。

    ![替代文字。不要讓空白。 收集器賽紅色輛車。][5]

3. 在 aliquam pharetra Nullam dictum dolor。 Vivamus ac hendrerit mauris。 Sed dolor dui condimentum et a，在您的 vehicula varius。

    ![替代文字。不保留空白][6]


Suspendisse volutpat 英哩識別碼 purus ultrices iaculis nec 非 neque。 在 aliquam pharetra Nullam dictum dolor。 Vivamus ac hendrerit mauris。 Otrus informatus: [其他 azure.microsoft.com 文件主題的連結 1](virtual-machines-windows-tutorial.md)

## 標題 (H2)

Ut eu pretium lacus。 Nullam purus est，iaculis sed est vel、 euismod vehicula odio。

1. Curabitur lacinia、 erat tristique iaculis rutrum、 erat sem sodales nisi、 歐盟 condimentum turpis nisi purus。

        - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:
        (NSDictionary *)launchOptions
        {
            // Register for remote notifications
            [[UIApplication sharedApplication] registerForRemoteNotificationTypes:
            UIRemoteNotificationTypeAlert | UIRemoteNotificationTypeBadge | UIRemoteNotificationTypeSound];
            return YES;
        }

2. Vestibulum ante ipsum primis 中 faucibus orci luctus et ultrices posuere cubilia。

        // Because toast alerts don't work when the app is running, the app handles them.
        // This uses the userInfo in the payload to display a UIAlertView.
        - (void)application:(UIApplication *)application didReceiveRemoteNotification:
        (NSDictionary *)userInfo {
            NSLog(@"%@", userInfo);
            UIAlertView *alert = [[UIAlertView alloc] initWithTitle:@"Notification" message:
            [userInfo objectForKey:@"inAppMessage"] delegate:nil cancelButtonTitle:
            @"OK" otherButtonTitles:nil, nil];
            [alert show];
        }


    > [AZURE.NOTE] 非 Duis sed diam <i>您 molestie</i> pharetra eget est。 [其他 azure.microsoft.com 文件主題的連結 2](web-sites-custom-domain-name.md)


Quisque 輸入 eros vel lectus euismod auctor eget sit amet leo。 Proin faucibus 文字 tellus dignissim ultrices。

## 標題 2 (h 2)

1. Maecenas sed condimentum nisi。 Suspendisse potenti。

  + Fusce
  + Malesuada
  + Sem

2. 在 massa eu tellus 新 hendrerit Nullam。

    ![替代文字。不要讓空白。 第 9 頻道視訊的範例。][7]

3. Quisque felis enim fermentum ut aliquam nec，pellentesque pulvinar 憲章。




<!--Every topic should have next steps and links to the next logical set of content to keep the customer engaged-->
## 後續步驟

Vestibul ante ipsum primis 中 faucibus orci luctus et ultrices posuere cubilia Curae;Nullam ultricies，ipsum vitae volutpat hendrerit，purus diam pretium eros，vitae tincidunt nulla lorem sed turpis: [其他 azure.microsoft.com 文件主題的連結 3](storage-whatis-account.md)。

<!--Image references-->
[5]: ./media/_markdown-template/octocats.png
[6]: ./media/_markdown-template/pretty49.png
[7]: ./media/_markdown-template/channel-9.png
[8]: ./media/_markdown-template/copytemplate.png

<!--Reference style links - using these makes the source content way more readable than using inline links-->
[gog]: http://google.com/
[yah]: http://search.yahoo.com/
[msn]: http://search.msn.com/

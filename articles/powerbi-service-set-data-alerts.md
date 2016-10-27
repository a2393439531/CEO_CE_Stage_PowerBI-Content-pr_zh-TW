<properties
   pageTitle="Set data alerts in the Power BI service"
   description="Learn to set alerts to notify you when data in your dashboards changes beyond limits you set in Microsoft Power BI service."
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   featuredVideoId="JbL2-HJ8clE"
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="10/04/2016"
   ms.author="mihart"/>

# Data alerts in Power BI service

Set alerts to notify you when data in your dashboards changes beyond limits you set.  Alerts work for numeric tiles featuring cards and gauges. Only you can see the alerts you set, even if you share your dashboard. Data alerts are fully synchronized across platforms; set and view data alerts <bpt id="p1">[</bpt>in the Power BI mobile app for iPhone<ept id="p1">](powerbi-mobile-set-data-alerts-in-the-iphone-app.md)</ept>, <bpt id="p2">[</bpt>Power BI mobile app for Windows<ept id="p2">](powerbi-mobile-set-data-alerts-in-the-windows-10-mobile-app.md)</ept> and in the Power BI service. They are not available for Power BI Desktop.

![](media/powerbi-service-set-data-alerts/powerbi-alert-types-new.png)

> [AZURE.WARNING] Data-driven alert notifications provide information about your data. If you view your Power BI data on a mobile device and that device gets stolen, we recommend using the Power BI service to turn off all data-driven alert rules.

## Set data alerts in Power BI service
Watch Amanda add some alerts to tiles on her dashboard. Then follow the step-by-step instructions below the video to try it out yourself.

<iframe width="560" height="315" src="https://www.youtube.com/embed/JbL2-HJ8clE" frameborder="0" allowfullscreen></iframe>

This example uses a card tile from the Retail Analysis sample dashboard.

1.  Start on a dashboard. From a dashboard tile, select the ellipses.

    ![](media/powerbi-service-set-data-alerts/powerbi-card.png)

2.  Select the bell icon <ph id="ph1">![](media/powerbi-mobile-set-data-alerts-in-the-iphone-app/PBI_iPhoneBellIconUnselect.png)</ph> to add one or more alerts for <bpt id="p1">**</bpt>Total stores<ept id="p1">**</ept>.

    ![](media/powerbi-service-set-data-alerts/powerbi-set-alert.png)

3.  To start, ensure the slider is set to <bpt id="p1">**</bpt>On<ept id="p1">**</ept>, and give your alert a title. Titles help you easily recognize your alerts.

    ![](media/powerbi-service-set-data-alerts/powerbi-alert-title.png)

4.  Scroll down and enter the alert details.  In this example we'll create an alert that notifies us once a day if the number of total stores goes above 100. Alerts will appear in our Notification center. And we'll have Power BI send us an email as well.

    ![](media/powerbi-service-set-data-alerts/powerbi-set-alert-details.png)

5. Select <bpt id="p1">**</bpt>Save<ept id="p1">**</ept>.


## Receiving alerts
When the data being tracked reaches one of the thresholds you've set, several things will happen. First, Power BI checks to see if it's been more than an hour or more than 24 hours (depending on the option you selected) since the last alert was sent. As long as the data is past the threshold, you'll get an alert.

Next, Power BI sends an alert to your notification center and, optionally, in email. Each alert contains a direct link to your data. Select the link to see the relevant tile where you can explore, share, and learn more.  

1.  If you've set the alert to send you an email, you'll find something like this in your Inbox.

    ![](media/powerbi-service-set-data-alerts/powerbi-alerts-email.png)

2.  Power BI adds a message to your <bpt id="p1">**</bpt>Notification center<ept id="p1">**</ept> and adds a new alert icon to the applicable tile.

    ![](media/powerbi-service-set-data-alerts/powerbi-alert-notifications.png)

4. Open your Notification center to see the alert details.

    ![](media/powerbi-service-set-data-alerts/powerbi-alert-notfication.png)

>[AZURE.NOTE] Alerts only work on data that is refreshed. When data refreshes, Power BI looks to see if an alert is set for that data. If the data has reached an alert threshold, an alert is triggered.


## 管理警示
There are three ways to manage your alerts: From the dashboard tile itself, from the Power BI Settings menu, and on an individual tile in the <bpt id="p1">[</bpt>Power BI mobile app on the iPhone<ept id="p1">](powerbi-mobile-set-data-alerts-in-the-iphone-app.md)</ept> or in the <bpt id="p2">[</bpt>Power BI mobile app for Windows 10<ept id="p2">](powerbi-mobile-set-data-alerts-in-the-windows-10-mobile-app.md)</ept>.

###   From the tile itself

1. If you need to change or remove an alert for a tile, re-open the <bpt id="p1">**</bpt>Manage alerts<ept id="p1">**</ept> window by selecting the bell icon <ph id="ph1">![](media/powerbi-mobile-set-data-alerts-in-the-iphone-app/PBI_iPhoneBellIconUnselect.png)</ph>. All the alerts that you've set for that tile are displayed.

    ![](media/powerbi-service-set-data-alerts/powerbi-see-alerts.png)。

2. To modify an alert, select the arrow to the left of the alert name.

    ![](media/powerbi-service-set-data-alerts/powerbi-see-alerts-arrow.png)。

3. To delete an alert, select the trashcan to the right of the alert name.

      ![](media/powerbi-service-set-data-alerts/powerbi-see-alerts-delete.png)

###   From the Power BI settings menu
1. Select the gear icon from the Power BI menubar.

    ![](media/powerbi-service-set-data-alerts/powerbi-gear-icon.png)。

2. Under <bpt id="p1">**</bpt>Settings<ept id="p1">**</ept> select <bpt id="p2">**</bpt>Alerts<ept id="p2">**</ept>.

    ![](media/powerbi-service-set-data-alerts/powerbi-alert-settings.png)

3. From here you can turn alerts on and off, open the <bpt id="p1">**</bpt>Manage alerts<ept id="p1">**</ept> window to make changes, or delete the alert.


## Tips and troubleshooting

-  Alerts are currently not supported for Bing tiles, or card tiles with date/time measures.

-  Alerts only work with numeric data types.

-  Alerts only work on data that is refreshed. They do not work on static data.

### 請參閱
- [Set data alerts on your iphone](powerbi-mobile-set-data-alerts-in-the-iphone-app.md)
- <bpt id="p1">[</bpt>Get started with Power BI<ept id="p1">](powerbi-service-get-started.md)</ept> More questions? [Try the Power BI Community](http://community.powerbi.com/)

<properties
   pageTitle="Share dashboards and reports with colleagues and others"
   description="How to share Power BI dashboards and reports with colleagues in and out of your organization, and what you need to know about sharing."
   services="powerbi"
   documentationCenter=""
   authors="ajayan"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   featuredVideoId="0tUwn8DHo3s"
   qualityFocus="identified"
   qualityDate="06/22/2016"/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="10/13/2016"
   ms.author="maggies"/>

# <a name="share-a-dashboard-and-reports-with-colleagues-and-others"></a>Share a dashboard and reports with colleagues and others

You can share your dashboards and reports with colleagues in and out of your organization. If they haven't signed up for <bpt id="p1">[</bpt>Power BI<ept id="p1">](http://powerbi.com)</ept>, they'll need to do so to see your dashboard.

What you can share and who you can share it with depends on your and their Power BI licenses. See <bpt id="p1">[</bpt>Licensing requirements for sharing<ept id="p1">](powerbi-service-share-unshare-dashboard.md#licensing-requirements-for-sharing)</ept> below for details.

Dashboards and reports that are shared with you are read-only.  You can't save-as to personalize them. On the other hand, you can make your own copy of dashboards and reports in <bpt id="p1">[</bpt>organizational content packs<ept id="p1">](powerbi-service-organizational-content-packs-introduction.md)</ept>.  See <bpt id="p1">[</bpt>How should I share my dashboard<ept id="p1">](powerbi-service-how-should-i-share-my-dashboard.md)</ept>? to decide which is best for your situation.

><bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: You share dashboards and reports from the Power BI service or the Power BI mobile apps, but not from Power BI Desktop.

Watch Amanda share her dashboard with colleagues inside and outside her company. Then follow the step-by-step instructions below the video to try it out yourself.

<iframe width="560" height="315" src="https://www.youtube.com/embed/0tUwn8DHo3s?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="share-a-dashboard"></a>Share a dashboard

1.   Open the dashboard and select <bpt id="p1">**</bpt>Share<ept id="p1">**</ept> <ph id="ph1">![](media/powerbi-service-share-unshare-dashboard/pbi_share_icon.png)</ph>.

2.  Select <bpt id="p1">**</bpt>In﻿vite<ept id="p1">**</ept> and type the email addresses in the top box and, optionally, modify the message.

    ![](media/powerbi-service-share-unshare-dashboard/power-bi-share-dashboard.png)  

    You can share with people whose addresses are outside your organization, but you'll see a warning.

    ![](media/powerbi-service-share-unshare-dashboard/power-bi-share-outside-organization.png)  

3.  To allow your colleagues to reshare your dashboard with others, check <bpt id="p1">**</bpt>Allow recipients to share your dashboard<ept id="p1">**</ept>.

    Only colleagues in your organization can reshare your dashboard. People outside your organization can view your dashboard but not reshare it.

4.  Select <bpt id="p1">**</bpt>Share.<ept id="p1">**</ept>

    Power BI sends an email invitation with a link to the shared dashboard. Clicking the link adds the dashboard to your colleague's Power BI service. They see this icon <ph id="ph1">![](media/powerbi-service-share-unshare-dashboard/PBI_SharedWithYouIcon.png)</ph> next to the shared dashboard, indicating the dashboard is shared with them.

    If they haven't yet signed up for Power BI, they can create an account after they click the link.

    ><bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: The sharing experience is different for people outside your organization. See <bpt id="p1">[</bpt>When you share with people outside your organization<ept id="p1">](powerbi-service-share-unshare-dashboard.md#when-you-share-your-dashboard-with-people-outside-your-organization)</ept> below for details.

5.  To see who you've already shared the dashboard with, select <bpt id="p1">**</bpt>Access<ept id="p1">**</ept>.

    ![](media/powerbi-service-share-unshare-dashboard/power-bi-shared-with.png)

    People outside your organization are listed as <bpt id="p1">**</bpt>Guest<ept id="p1">**</ept>.

## <a name="notes-about-sharing-a-dashboard"></a>Notes about sharing a dashboard

When you share a dashboard:

-   Everyone you share it with can see your dashboard and interact with your reports in <bpt id="p1">[</bpt>Reading View<ept id="p1">](powerbi-service-open-a-report-in-reading-view.md)</ept>. They can't create new reports or save changes to existing reports.

-   Everyone can even see the changes you make.

-   No-one can see or download the dataset.

-   Everyone can manually <bpt id="p1">[</bpt>refresh the dashboard data<ept id="p1">](powerbi-refresh-data.md)</ept>.

### <a name="when-you-share-your-dashboard-with-colleagues"></a>When you share your dashboard with colleagues

-   If you use Office 365 for email, you can share with members of a distribution group by entering the email address associated with the distribution group.

-   Colleagues who have the same email domain as you, and colleagues whose domain is different but registered within the tenant, can reshare the dashboard. For example, say the domains contoso.com and contoso2.com are registered in the tenant. If your email address is <ph id="ph1">konrads@contoso.com,</ph> then both <ph id="ph2">ravali@contoso.com</ph> and <ph id="ph3">gustav@contoso2.com</ph> can reshare.

    <bpt id="p1">**</bpt>Tip:<ept id="p1">**</ept> If your colleagues already have access to a specific dashboard, you can send a direct link to that dashboard just by copying the URL when you're on the dashboard. 例如：   

    https://powerbi.com/dashboards/g12466b5-a452-4e55-8634-xxxxxxxxxxxx


## <a name="when-you-share-your-dashboard-with-people-outside-your-organization"></a>When you share your dashboard with people outside your organization

When you share with people outside your organization, they get an email with a link to the shared dashboard. They have to sign in to Power BI to see the dashboard. If they don't have a Power BI account, they can create one after clicking the link.

After they sign in, they see the shared dashboard in its own browser window without the left navigation pane, not in their usual Power BI portal. They have to bookmark the link to access this dashboard in the future.

They can't edit any content in this dashboard or report. They can interact with the charts in the report (cross-highlight) and change any filters/slicers available on the reports connected to the dashboard.

Only your direct recipients can see the shared dashboard. In the example above, only <ph id="ph1">Vicki@contoso.com</ph> can see the dashboard. No-one else can see that dashboard, even if they have the link, and Vicki has to use the same email address to access that dashboard. If she signs up with any other email address, she won't have access to the dashboard either.

People outside your organization can't see any data if role- or row-level security is implemented on Analysis Services tabular models on-premises.

## <a name="share-just-a-report"></a>Share just a report
We've seen that when you share a dashboard that has tiles that link to reports, those reports are also shared at the same time. But what if you want to share just a report? Simply send the report page URL to your colleagues. As long as they are members of the same distribution group, in the same email domain as you, or have at least one dashboard that links to that same report (the dashboard has tiles that were pinned from that report), they'll be able to open the report.

See <bpt id="p1">[</bpt>When you share with colleagues, above<ept id="p1">](powerbi-service-share-unshare-dashboard.md#when-you-share-your-dashboard-with-colleagues)</ept>.

### <a name="share-a-filtered-version-of-a-report"></a>Share a filtered version of a report
What if you want to share a filtered version of a report? Maybe a report that only shows data for a specific city or salesperson or year. This can be done by creating a custom URL.

1.   Open the report in <bpt id="p1">[</bpt>Editing view<ept id="p1">](powerbi-service-go-from-reading-view-to-editing-view.md)</ept> and apply the filter. In this example we're filtering the <bpt id="p1">[</bpt>Retail Analysis sample<ept id="p1">](powerbi-sample-tutorial-connect-to-the-samples.md)</ept> to show only District FD-01.

    ![](media/powerbi-service-share-unshare-dashboard/power-bi-filter-report2.png)

2.  Add the following to the end of the report page URL:

    ?filter=tablename/fieldname eq value

    In our example, the name of the table is <bpt id="p1">**</bpt>Store<ept id="p1">**</ept>, the name of the field is <bpt id="p2">**</bpt>Territory<ept id="p2">**</ept>, and the value we want to filter on is <bpt id="p3">**</bpt>NC<ept id="p3">**</ept>.

    ![](media/powerbi-service-share-unshare-dashboard/power-bi-filter-url3.png)

    Your browser adds some special characters to represent slashes and spaces, so you end up with:

    app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-10a61f70f2f5/ReportSection2?filter=Store%252FTerritory%20eq%20NC

    >[AZURE.NOTE]The field must be of type <bpt id="p1">**</bpt>string<ept id="p1">**</ept> and neither the tablename or fieldname can contain spaces.

3.  Send this URL to your colleagues. When they click on the link, Power BI will open a read-only version of the filtered report.

## <a name="licensing-requirements-for-sharing"></a>Licensing requirements for sharing

Sharing content inside and outside your organization both have the same licensing requirements.

If you create your dashboard  with only free Power BI features, your recipients just need a free Power BI license to view the content. If you use Power BI Pro features like groups or on-premises connectivity, your recipients need a Power BI Pro license to view the content.

See <bpt id="p1">[</bpt>Power BI Pro content - what is it?<ept id="p1">](powerbi-power-bi-pro-content-what-is-it.md)</ept> for a more complete list.

This Power BI pricing page, <bpt id="p1">[</bpt>Use Power BI for free or buy Power BI Pro<ept id="p1">](https://powerbi.microsoft.com/pricing)</ept>, is also a useful comparison of the two options.

## <a name="resharing"></a>Resharing

Resharing allows your colleagues to forward the email invitation to others in your organization (the invitation expires after one month). Colleagues can also reshare through the Power BI service and mobile apps. As the owner of the dashboard, you can turn off resharing and you can also revoke resharing on an individual basis (see below).

People outside your organization can't reshare.

## <a name="unshare-a-dashboard"></a>Unshare a dashboard

1.  Open the dashboard and select <bpt id="p1">**</bpt>Share<ept id="p1">**</ept> <ph id="ph1">![](media/powerbi-service-share-unshare-dashboard/pbi_share_icon.png)</ph>.

2.  Select <bpt id="p1">**</bpt>Access<ept id="p1">**</ept> to see the complete list of people.

    ![](media/powerbi-service-share-unshare-dashboard/power-bi-shared-with.png)

3.  Select the ellipsis (<bpt id="p1">**</bpt>...<ept id="p1">**</ept>) next to <bpt id="p2">**</bpt>Can view<ept id="p2">**</ept> and select:

    ![](media/powerbi-service-share-unshare-dashboard/pbi_stop_sharing.png)

    -   <bpt id="p1">**</bpt>Stop sharing<ept id="p1">**</ept> with that person or

    -   <bpt id="p1">**</bpt>Disable reshares<ept id="p1">**</ept> to keep that person from sharing with anyone else.

    -   Or if the person hasn't yet accepted your share invitation, <bpt id="p1">**</bpt>Cancel Invite<ept id="p1">**</ept>.

## <a name="turn-off-resharing"></a>Turn off resharing

Only the dashboard owner can turn resharing on and off.

-   If you haven't sent the sharing invitation yet, clear the <bpt id="p1">**</bpt>Allow recipients to share your dashboard<ept id="p1">**</ept> check box at the bottom of the invitation.

-   If colleagues haven't accepted your sharing invitation yet, cancel the invitation and invite them again without selecting <bpt id="p1">**</bpt>Allow recipients to share your dashboard<ept id="p1">**</ept>.

-   If they have accepted your sharing invitation, select <bpt id="p1">**</bpt>Access<ept id="p1">**</ept>, select the ellipsis (<bpt id="p2">**</bpt>...<ept id="p2">**</ept>) next to <bpt id="p3">**</bpt>Can view<ept id="p3">**</ept> and click <bpt id="p4">**</bpt>Stop sharing<ept id="p4">**</ept>.

    ![](media/powerbi-service-share-unshare-dashboard/pbi_stop_sharing.png)


### <a name="see-also"></a>請參閱

- <bpt id="p1">[</bpt>How should I share my dashboard?<ept id="p1">](powerbi-service-how-should-i-share-my-dashboard.md)</ept>
- <bpt id="p1">[</bpt>Share a dashboard that links to an Excel file<ept id="p1">](powerbi-service-share-dashboard-that-links-to-excel.md)</ept>
- <bpt id="p1">[</bpt>Power BI Pro content - what is it?<ept id="p1">](powerbi-power-bi-pro-content-what-is-it.md)</ept>
- <bpt id="p1">[</bpt>Use Power BI for free or buy Power BI Pro<ept id="p1">](https://powerbi.microsoft.com/pricing)</ept>
- <bpt id="p1">[</bpt>Get Started with Power BI<ept id="p1">](powerbi-service-get-started.md)</ept>
- More questions? <bpt id="p1">[</bpt>Try the Power BI Community<ept id="p1">](http://community.powerbi.com/)</ept>.

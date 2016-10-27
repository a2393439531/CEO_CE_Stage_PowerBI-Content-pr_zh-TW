<properties
pageTitle="Manage your data source - Analysis Services"
description="How to manage the on-premises data gateway and data sources that belong to that gateway. This is for Analysis Services in both Multidimensional and Tabular mode."
services="powerbi"
documentationCenter=""
authors="guyinacube"
manager="erikre"
backup=""
editor=""
tags=""
qualityFocus="monitoring"
qualityDate="06/09/2016"/>

<tags
ms.service="powerbi"
ms.devlang="NA"
ms.topic="article"
ms.tgt_pltfrm="na"
ms.workload="powerbi"
ms.date="10/12/2016"
ms.author="asaxton"/>
# Manage your data source - Analysis Services

Once you have installed the On-premises Data Gateway, you will need to add data sources that can be used with the gateway. This article will look at how to work with gateways and data sources. You can use the Analysis Services data source either for scheduled refresh or for live connections.

<iframe width="560" height="315" src="https://www.youtube.com/embed/ownIGbcRAAU" frameborder="0" allowfullscreen></iframe>

## Download and install the gateway

You can download the gateway from the Power BI service. Select <bpt id="p1">**</bpt>Downloads<ept id="p1">**</ept><ph id="ph1"> &gt; </ph><bpt id="p2">**</bpt>Data Gateway<ept id="p2">**</ept>, or by going to the <bpt id="p3">[</bpt>gateway download page<ept id="p3">](https://go.microsoft.com/fwlink/?LinkId=698861)</ept>.

![](media/powerbi-gateway-onprem/powerbi-download-data-gateway.png)

## Limitations of Analysis Services live connections

You can use a live connection against tabular or multidimensional instances.

|**Server version**|**Required SKU**|
|---|---|
|2012 SP1 CU4 or later|Business Intelligence and Enterprise SKU|
|2014|Business Intelligence and Enterprise SKU|
|2016|Standard SKU or higher|

- Cell level Formatting and translation features are not supported.
- Actions and Named Sets are not exposed to Power BI, but you can still connect to multidimensional cubes that also contain Actions or Named sets and create visuals and reports.

## Add a gateway

To add a Gateway, simply <bpt id="p1">[</bpt>download<ept id="p1">](https://go.microsoft.com/fwlink/?LinkId=698861)</ept> and install the enterprise gateway on a server in your environment. After you have installed the gateway, it will show in the lists of gateways under <bpt id="p1">**</bpt>Manage gateways<ept id="p1">**</ept>.

> [AZURE.NOTE] <bpt id="p1">**</bpt>Manage gateways<ept id="p1">**</ept> will not show up until you are the admin of at least one gateway. This can happen either by being added as an admin or you installing and configuring a gateway.

## Remove a gateway

Removing a gateway will also delete any data sources under that gateway.  This will also break any dashboards and reports that rely on those data sources.

1.  Select the gear icon <ph id="ph1">![](media/powerbi-gateway-enterprise-manage/pbi_gearicon.png)</ph> in the upper-right corner &gt; <bpt id="p1">**</bpt>Manage gateways<ept id="p1">**</ept>.

2.  Gateway &gt; <bpt id="p1">**</bpt>Remove<ept id="p1">**</ept>

    ![](media/powerbi-gateway-enterprise-manage/datasourcesettings7.png)

## Add a data source

You can add a data source by either selecting a gateway and click <bpt id="p1">**</bpt>Add data source<ept id="p1">**</ept>, or go to Gateway &gt; <bpt id="p2">**</bpt>Add data source<ept id="p2">**</ept>.

![](media/powerbi-gateway-enterprise-manage/datasourcesettings1.png)

You can then select the <bpt id="p1">**</bpt>Data Source Type<ept id="p1">**</ept> from the list. Select Analysis Services if you are connecting to either a Multidimensional or Tabular server.

![](media/powerbi-gateway-enterprise-manage/datasourcesettings2-ssas.png)

You will then want to fill in the information for the data source which includes the <bpt id="p1">**</bpt>Server<ept id="p1">**</ept> and the <bpt id="p2">**</bpt>Database<ept id="p2">**</ept>.  

The <bpt id="p1">**</bpt>Username<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Password<ept id="p2">**</ept> that you enter will be used by the gateway to connect to the Analysis Services instance. 

> [AZURE.NOTE] The Windows account you enter must have Server Administrator permissions for the instance you are connecting to. If this account’s password is set to expire, users could get a connection error if the password isn’t updated for the data source. For more information, see the main on-premises data gateway article to learn more about how <bpt id="p1">[</bpt>credentials<ept id="p1">](powerbi-gateway-onprem.md#credentials)</ept> are stored.

![](media/powerbi-gateway-enterprise-manage/datasourcesettings3-ssas.png)

You can click <bpt id="p1">**</bpt>Add<ept id="p1">**</ept> after you have everything filled in.  You can now use this data source for scheduled refresh, or live connections, against an Analysis Services instance that is on premises.  You will see <bpt id="p1">*</bpt>Connection Successful<ept id="p1">*</ept> if it succeeded.

![](media/powerbi-gateway-enterprise-manage/datasourcesettings4.png)

### 進階設定

You can configure the privacy level for your data source. This controls how data can be mashed up. This is only used for scheduled refresh. It does not apply to live connections. [進一步了解](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)

![](media/powerbi-gateway-enterprise-manage/datasourcesettings9.png)

## 'Get Data' experience for Analysis Services in Power BI site

A unique option for Analysis Services is to use Get Data within the Power BI service directly. You can connect to a live Analysis Services data source that is configured within the gateway without needing Power BI Desktop. Your account needs to be listed in the <bpt id="p1">**</bpt>Users<ept id="p1">**</ept> tab for the data source, under the gateway, for it to show up in the list. To connect to the data source, you can do the following.

1. Within the Power BI service, select <bpt id="p1">**</bpt>Get Data<ept id="p1">**</ept>.

2. Select <bpt id="p1">**</bpt>Databases<ept id="p1">**</ept>.

3. Select <bpt id="p1">**</bpt>SQL Server Analysis Services<ept id="p1">**</ept><ph id="ph1"> &gt; </ph><bpt id="p2">**</bpt>Connect<ept id="p2">**</ept>.

4. Select a data source from the list. Any Analysis Services data source that you have access to will be listed here.

5. Select the model that you want to connect to. Then select <bpt id="p1">**</bpt>Connect<ept id="p1">**</ept>.

You will see a dataset show up with the name of the server. You can then select that dataset and begin to create reports on it. This will be working against live data.

## Usernames with Analysis Services

Each time a user interacts with a report connected to Analysis Services, the effective username is passed to the gateway and then onto your on-premises Analysis Services server. The email address, that you sign into Power BI with, is what we will pass to Analysis Services as the effective user. This is passed in the connection property <bpt id="p1">[</bpt>EffectiveUserName<ept id="p1">](https://msdn.microsoft.com/library/dn140245.aspx#bkmk_auth)</ept>. This email address should match a defined UPN within the local Active Directory Domain. The UPN is a property of an Active Directory account. That Windows account then needs to be present in an Analysis Services role. If a match cannot be found, in Active Directory, the login will not be successful. [進一步了解](https://msdn.microsoft.com/library/ms677605.aspx)

You can also map your Power BI sign in name with a local directory UPN. [進一步了解](powerbi-gateway-enterprise-manage-ssas.md#map-user-names)

<iframe width="560" height="315" src="https://www.youtube.com/embed/Qb5EEjkHoLg" frameborder="0" allowfullscreen></iframe>

### How do I tell what my UPN is?

You may not know what your UPN is, and you may not be a domain administrator. You can use the following command from your workstation to find out the UPN for your account.

    whoami /upn

The result will look similar to an email address, but this is the UPN that is on your domain account. If you are using an Analysis Services data source for live connections, and If this doesn't match the email address you sign into Power BI with, you may want to look at how to <bpt id="p1">[</bpt>Map user names<ept id="p1">](#map-user-names)</ept>.

## Map user names

<iframe width="560" height="315" src="https://www.youtube.com/embed/eATPS-c7YRU" frameborder="0" allowfullscreen></iframe>

For Analysis Services data sources, you can configure custom User Principal Name (UPN) rules. This will help you if your Power BI service login names do not match your local directory UPN. For example, if you sign into Power BI with john@contoso.com, but your local directory UPN is john@contoso.local, you can configure a mapping rule to have john@contoso.local passed to Analysis Services.

To get to the UPN Mapping screen, do the following.

1. Go to the <bpt id="p1">**</bpt>gear icon<ept id="p1">**</ept> and select <bpt id="p2">**</bpt>Manage Gateways<ept id="p2">**</ept>.

2. Expand the gateway that contains the Analysis Services data source. Of, if you haven't created the Analysis Services data source, you can do that at this point.

3. Select the data source and then select the <bpt id="p1">**</bpt>Users<ept id="p1">**</ept> tab.

4. Select <bpt id="p1">**</bpt>Map user names<ept id="p1">**</ept>.

    ![](media/powerbi-gateway-enterprise-manage/gateway-enterprise-map-user-names.png)
    
You will then see options to add rules as well as test for a given user.

> [AZURE.NOTE] You may inadvertantly change a user that you didn't intend to. For example, if your <bpt id="p1">**</bpt>Replace (original value)<ept id="p1">**</ept> is <bpt id="p2">*</bpt>@contoso.com<ept id="p2">*</ept> and your <bpt id="p3">**</bpt>With (New name)<ept id="p3">**</ept> is <bpt id="p4">*</bpt>@contoso.local<ept id="p4">*</ept>, all users with a sign in that contains <bpt id="p5">*</bpt>@contoso.com<ept id="p5">*</ept> will then be replaced with <bpt id="p6">*</bpt>@contoso.local<ept id="p6">*</ept>. Also, if your <bpt id="p1">**</bpt>Replace (Original name)<ept id="p1">**</ept> is <bpt id="p2">*</bpt>dave@contoso.com<ept id="p2">*</ept> and your <bpt id="p3">**</bpt>With (New name)<ept id="p3">**</ept> is <bpt id="p4">*</bpt>dave@contoso.local<ept id="p4">*</ept>, a user with the sign in of v-dave@contoso.com would be sent as v-dave<bpt id="p5">*</bpt>@contoso.local<ept id="p5">*</ept>.

Currently you can only supply rules for <bpt id="p1">**</bpt>Effective user names<ept id="p1">**</ept>.

### Working with mapping rules

To create a mapping rule, enter a value for <bpt id="p1">**</bpt>Original name<ept id="p1">**</ept> and <bpt id="p2">**</bpt>New Name<ept id="p2">**</ept> and then select <bpt id="p3">**</bpt>Add<ept id="p3">**</ept>.

|欄位|描述
|---|---|
|Replace (Orignal name)|The email address that you signed into Power BI with.|
|With (New Name)|The value you want to replace it with. The result of the replacement is what will be passed to the <bpt id="p1">*</bpt>EffectiveUserName<ept id="p1">*</ept> property for the Analysis Services connection.|

![](media/powerbi-gateway-enterprise-manage/gateway-enterprise-map-user-names-effective-user-names.png)

When you select an item in the list, you can choose to re-order it by using the <bpt id="p1">**</bpt>chevron icons<ept id="p1">**</ept>, or <bpt id="p2">**</bpt>Delete<ept id="p2">**</ept> the entry.

![](media/powerbi-gateway-enterprise-manage/gateway-enterprise-map-user-names-entry-selected.png)

### Using Wildcard(*)

You can use a wildcard for your <bpt id="p1">**</bpt>Replace (Original name)<ept id="p1">**</ept> string. It can only be used on its own and not with any other string part. This will allow you to take all users and pass a single value to the data source. This is useful when you want all users in your organization to use the same user in your local environment.

### Test a mapping rule

You can validate what an original name will be replaced with by entering a value for <bpt id="p1">**</bpt>Original name<ept id="p1">**</ept> and selecting <bpt id="p2">**</bpt>Test rule<ept id="p2">**</ept>.

![](media/powerbi-gateway-enterprise-manage/gateway-enterprise-test-mapping-rule.png)

> [AZURE.NOTE] Rules that are saved will take a few minutes for the service to start using them. Within the browser, the rule will work immediately.

### Limitations for mapping rules

- Mapping is for the specific data source that is being configured. It is not a global settings. If you have multiple Analysis Services data sources, you will have to map the users for each data source.

## Remove a data source

Removing a data source will break any dashboards or reports that rely on the given data source.  

To remove a Data Source, go to the Data Source &gt; <bpt id="p1">**</bpt>Remove<ept id="p1">**</ept>.

![](media/powerbi-gateway-enterprise-manage/datasourcesettings6.png)

## Manage administrators

On the Administrators tab, for the gateway, you can add, and remove, users that can administer the gateway. You can only add users at this time. Security groups cannot be added.

![](media/powerbi-gateway-enterprise-manage/datasourcesettings8.png)

## 管理使用者

On the Users tab, for the data source, you can add, and remove, users, or security groups, that can use this data source.

> [AZURE.NOTE] The users list only controls who are allowed to publish reports. The report owners can create dashboards, or content packs, and share those with other users.

![](media/powerbi-gateway-enterprise-manage/datasourcesettings5.png)

## Using the data source

After you have created the data source, it will be available to use with either live connections, or through scheduled refresh. 

> [AZURE.NOTE] Server and database name have to match between Power BI Desktop and the data source within the on-premises data gateway!

The link between your dataset and the data source within the gateway is based on your server name and database name. These have to match. For example, if you supply an IP Address for the server name, within Power BI Desktop, you will need to use the IP Address for the data source within the gateway configuration. If you use <bpt id="p1">*</bpt>SERVER\INSTANCE<ept id="p1">*</ept>, in Power BI Desktop, you will need to use the same within the data source configured for the gateway.

This is the case for both live connections and scheduled refresh.

### Using the data source with live connections

You will need to make sure the server and database name matches between Power BI Desktop and the configured data source for the gateway. You will also need to make sure your user is listed in the <bpt id="p1">**</bpt>Users<ept id="p1">**</ept> tab of the data source in order to publish live connection datasets. The selection, for live connections, occurs within Power BI Desktop when you first import data.

After you publish, either from Power BI Desktop or <bpt id="p1">**</bpt>Get Data<ept id="p1">**</ept>, your reports should start working. It may take several minutes, after creating the data source within the gateway, for the connection to be usable.

### Using the data source with scheduled refresh

If you are listed in the <bpt id="p1">**</bpt>Users<ept id="p1">**</ept> tab of the data source configured within the gateway, and the server and database name match, you will see the gateway as an option to use with scheduled refresh.

![](media/powerbi-gateway-enterprise-manage/powerbi-gateway-enterprise-schedule-refresh.png)

## 另請參閱

[On-premises Data Gateway](powerbi-gateway-onprem.md)  
[On-premises Data Gateway - in-depth](powerbi-gateway-onprem-indepth.md)  
[Troubleshooting the On-premises Data Gateway](powerbi-gateway-onprem-tshoot.md)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)
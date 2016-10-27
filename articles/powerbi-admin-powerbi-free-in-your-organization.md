<properties
pageTitle="Power BI (free) in your organization"
description="This article looks at your options for Power BI (free) from an organization perspective. If you are the Administrator of your tenant, this will show you how to manage free sign ups."
services="powerbi"
documentationCenter=""
authors="guyinacube"
manager="mblythe"
backup=""
editor=""
tags=""
qualityFocus="no"
qualityDate=""/>

<tags
ms.service="powerbi"
ms.devlang="NA"
ms.topic="article"
ms.tgt_pltfrm="na"
ms.workload="powerbi"
ms.date="09/21/2016"
ms.author="asaxton"/>
# Power BI (free) in your organization

This will look at how the Power BI (free) offering can be used within your organization. An organization means that you have a tenant and can manage users and services within that tenant. As an administrator, you can control license assignment, or you can allow users to sign up as an individual. We will look at the Power BI (free) license and how you can control individual sign up.

## Individual sign up versus license assignment

Users within your organization can gain access to Power BI in two different ways. They can individually sign up for Power BI, or you can assign a Power BI license to them within the Office 365 admin portal.

Allowing individual sign up reduces the burden, from the organization administrators, by allowing the users that are interested in Power BI to sign up for free. 

For more control, you can block individual sign up and assign Power BI licenses yourself within the Office 365 admin center. This allows you to be specific of who can access what services within your organization. This is also a great option if you have to deal with auditing and need to know exactly who can use what.

## How to get the unlimited license block
Within the Office 365 admin center, under <bpt id="p1">**</bpt>Billing<ept id="p1">**</ept><ph id="ph1"> &gt; </ph><bpt id="p2">**</bpt>Licenses<ept id="p2">**</ept>, you may or may not see Power BI (free) with unlimited licenses.

![](media/powerbi-admin-powerbi-free-in-your-organization/unlimited-licenses.png)
 
This block of licenses will show up after the first time someone signs up for Power BI as an individual. During that process, this license block gets attached to your organization and a license is assigned to the user that is signing up.

If you are blocking individual user sign up, and no one has signed up, you will not see this license block. You can either allow individual user sign ups and have one user sign up, or you can get free licenses through the add subscription Office 365 flow which will be talked about next.

Once the Power BI (free) license block is available, you can assign those licenses to your users. [進一步了解](https://support.office.com/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc)

## Getting free licenses via add subscription within Office 365

1.  Navigate to the <bpt id="p1">[</bpt>Office 365 admin center<ept id="p1">](https://portal.office.com/admin/default.aspx)</ept>.
2.  On the left navigation pane, select <bpt id="p1">**</bpt>Billing<ept id="p1">**</ept><ph id="ph1"> &gt; </ph><bpt id="p2">**</bpt>Subscriptions<ept id="p2">**</ept>.
3.  Select <bpt id="p1">**</bpt>Add subscriptions +<ept id="p1">**</ept> on the right side.
4.  Under Other Plans, hover over the <bpt id="p1">**</bpt>ellipse (…)<ept id="p1">**</ept> for Power BI (free) and select <bpt id="p2">**</bpt>Buy now<ept id="p2">**</ept>.

    ![](media/powerbi-admin-powerbi-free-in-your-organization/buy-powerbi-free.png)

5.  Enter the number of licenses you would like to add and select <bpt id="p1">**</bpt>Check out now<ept id="p1">**</ept> or <bpt id="p2">**</bpt>Add to cart<ept id="p2">**</ept>.

    > [AZURE.NOTE] You can add more at a later date if needed.

6.  Enter the needed information in the check out flow.

There is no purchase when using this approach, although you will need to either enter your credit card information for billing, or choose to be invoiced.

If you decide later that you want to add more licenses, you can go back to <bpt id="p1">**</bpt>Add subscriptions<ept id="p1">**</ept>, and select <bpt id="p2">**</bpt>Change license quantity<ept id="p2">**</ept> for Power BI (free).

![](media/powerbi-admin-powerbi-free-in-your-organization/change-license-quantity.png)
 
You can now assign those licenses to your users. [進一步了解](https://support.office.com/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc)

## Enable, or disable, individual user sign up in Azure Active Directory

As an administrator, you can choose to enable, or disable, individual user sign ups as part of Azure Active Directory (AAD). If you know how to leverage the AAD PowerShell commands, you can enable, or disable, ad-hoc subscriptions yourself. [進一步了解](https://technet.microsoft.com/library/jj151815.aspx)

The AAD setting that controls this is <bpt id="p1">**</bpt>AllowAdHocSubscriptions<ept id="p1">**</ept>. Most tenants will have this setting set to true, which means it is enabled. If you acquired Power BI through a partner, this may be set to false by default, which means it is disabled.

1.  You need to first sign into Azure Active Directory using your Office 365 credential. The first line will prompt you for your credentials. The second line connects to Azure Active Directory.

        $msolcred = get-credential
        connect-msolservice -credential $msolcred
    
    ![](media/powerbi-admin-powerbi-free-in-your-organization/aad-signin.png)

2.  Once you are signed in, you can issue the following command to see what your tenant is currently configured for.

        Get-MsolCompanyInformation | fl AllowAdHocSubscriptions

3.  You can this command to enable ($true) or disable ($false) AllowAdHocSubscriptions.

        Set-MsolCompanySettings -AllowAdHocSubscriptions $true

> [AZURE.NOTE] This blocking prevents new users in your organization from signing up for Power BI. Users that sign up for Power BI prior to disabling new signups for your organization will still retain their licenses.

## 請參閱

[Self-service sign up for Power BI](powerbi-service-self-service-signup-for-power-bi.md)  
[Sign up for Power BI (free) with a custom Azure Active Directory tenant](powerbi-admin-free-with-custom-azure-directory.md)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)
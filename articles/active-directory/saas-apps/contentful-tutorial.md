---
title: 'Tutorial: Azure Active Directory single sign-on (SSO) integration with Contentful | Microsoft Docs'
description: Learn how to configure single sign-on between Azure Active Directory and Contentful.
services: active-directory
author: jeevansd
manager: CelesteDG
ms.reviewer: celested
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.topic: tutorial
ms.date: 08/27/2021
ms.author: jeedes
---

# Tutorial: Azure Active Directory single sign-on (SSO) integration with Contentful

In this tutorial, you'll learn how to integrate Contentful with Azure Active Directory (Azure AD). When you integrate Contentful with Azure AD, you can:

* Control in Azure AD who has access to Contentful.
* Enable your users to be automatically signed-in to Contentful with their Azure AD accounts.
* Manage your accounts in one central location - the Azure portal.

## Prerequisites

To get started, you need the following items:

* An Azure AD subscription. If you don't have a subscription, you can get a [free account](https://azure.microsoft.com/free/).
* Contentful single sign-on (SSO) enabled subscription.

## Scenario description

In this tutorial, you configure and test Azure AD SSO in a test environment.

* Contentful supports **SP and IDP** initiated SSO.
* Contentful supports **Just In Time** user provisioning.
* Contentful supports [Automated user provisioning](contentful-provisioning-tutorial.md).

> [!NOTE]
> The identifier of this application is a fixed string value so only one instance can be configured in one tenant.

## Add Contentful from the gallery

To configure the integration of Contentful into Azure AD, you need to add Contentful from the gallery to your list of managed SaaS apps.

1. Sign in to the Azure portal using either a work or school account, or a personal Microsoft account.
1. In the left navigation pane, select the **Azure Active Directory** service.
1. Navigate to **Enterprise Applications** and then select **All Applications**.
1. To add a new application, select **New application**.
1. In the **Add from the gallery** section, type **Contentful** in the search box.
1. Select **Contentful** in the results, and then add the app. Wait a few seconds while the app is added to your tenant.

## Configure and test Azure AD SSO for Contentful

Configure and test Azure AD SSO with Contentful using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between an Azure AD user and the related user in Contentful.

To configure and test Azure AD SSO with Contentful, perform the following steps:

1. **[Configure Azure AD SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **[Create an Azure AD test user](#create-an-azure-ad-test-user)** - to test Azure AD single sign-on with B.Simon.
    1. **[Assign the Azure AD test user](#assign-the-azure-ad-test-user)** - to enable B.Simon to use Azure AD single sign-on.
1. **[Configure Contentful SSO](#configure-contentful-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Contentful test user](#create-contentful-test-user)** - to have a counterpart of B.Simon in Contentful that is linked to the Azure AD representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

## Configure Azure AD SSO

Follow these steps to enable Azure AD SSO in the Azure portal.

1. In the Azure portal, on the **Contentful** application integration page, find the **Manage** section and select **single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, click the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. In the **Basic SAML Configuration** section, if you want to configure the application in **IDP** initiated mode, perform the following step:

    a. In the **Reply URL** text box, copy the ACS (Assertion Consumer Service) URL from the SSO setup page in Contentful. It will look like this:
    `https://be.contentful.com/sso/<organization_id>/consume`.

1. Click **Set additional URLs** and perform the following step if you want to configure the application in **SP** initiated mode:

    a. In the **Sign-on URL** text box, copy the same ACS (Assertion Consumer Service) URL. It will look like this:
    `https://be.contentful.com/sso/<organization_id>/login`.

	> [!NOTE]
	> These values are not real. Update these values with the actual Reply URL and Sign-On URL by copying the ACS (Assertion Consumer Service) URL from the SSO setup page in Contentful.

1. Contentful application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

	![image](common/default-attributes.png)

1. In addition to above, Contentful application expects few more attributes to be passed back in SAML response which are shown below. These attributes are also pre populated but you can review them as per your requirements.
	
	| Name |  Source Attribute|
	| --------------- | --------- |
	| email | user.userprincipalname |

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section, find **Certificate (Base64)** and select **Download** to download the certificate and save it on your computer.

	![The Certificate download link](common/certificatebase64.png)

1. In the **Set up Contentful** section, copy the login URL to configure Contentful SSO.

	![Copy configuration URLs](media/contentful-tutorial/copy-configuration-urls.png)

### Create an Azure AD test user

In this section, you'll create a test user in the Azure portal called B.Simon.

1. In the left pane in the Azure portal, select **Azure Active Directory**, select **Users**, and then select **All users**.
1. Select **New user** at the top of the screen.
1. In the **User** properties, follow these steps:
   1. In the **Name** field, enter `B.Simon`.  
   1. In the **User name** field, enter the username@companydomain.extension. For example, `B.Simon@contoso.com`.
   1. Select the **Show password** check box, and then write down the value that's displayed in the **Password** box.
   1. Click **Create**.

### Assign the Azure AD test user

In this section, you'll enable B.Simon to use Azure single sign-on by granting access to Contentful.

1. In the Azure portal, select **Enterprise Applications**, and then select **All applications**.
1. In the applications list, select **Contentful**.
1. In the app's overview page, find the **Manage** section and select **Users and groups**.
1. Select **Add user**, then select **Users and groups** in the **Add Assignment** dialog.
1. In the **Users and groups** dialog, select **B.Simon** from the Users list, then click the **Select** button at the bottom of the screen.
1. If you are expecting a role to be assigned to the users, you can select it from the **Select a role** dropdown. If no role has been set up for this app, you see "Default Access" role selected.
1. In the **Add Assignment** dialog, click the **Assign** button.

## Configure Contentful SSO

Follow these steps to configure single sign-on on the **Contentful** side.

1. In [Contentful](https://app.contentful.com), navigate to the SSO setup page in **Organization Settings**.
1. Click on **Set up SSO**.
1. Copy and paste the login URL from the **Set up Contentful** section in Azure AD.
1. Copy and paste the certificate from the Base64 certificate file you downloaded from Azure AD.
1. Set up an SSO name for SP-initiated login.
1. Click on **Enable SSO**.

If that doesn't work, reach out to the [Contentful support team](mailto:support@contentful.com).

### Create Contentful test user

In this section, a user called B.Simon is created in Contentful. Contentful supports just-in-time user provisioning, which is enabled by default. There is no action item for you in this section. If a user doesn't already exist in Contentful, a new one is created after authentication.

Contentful also supports automatic user provisioning, you can find more details [here](./contentful-provisioning-tutorial.md) on how to configure automatic user provisioning.

## Test SSO

In this section, you test your Azure AD single sign-on configuration with following options. 

#### SP initiated:

* Click on **Test this application** in Azure portal. This will redirect to Contentful Sign on URL where you can initiate the login flow.  

* Go to Contentful Sign-on URL directly and initiate the login flow from there.

#### IDP initiated:

* Click on **Test this application** in Azure portal and you should be automatically signed in to the Contentful for which you set up the SSO. 

You can also use Microsoft My Apps to test the application in any mode. When you click the Contentful tile in the My Apps, if configured in SP mode you would be redirected to the application sign on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the Contentful for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](../user-help/my-apps-portal-end-user-access.md).

## Next steps

Once you configure Contentful you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Cloud App Security](/cloud-app-security/proxy-deployment-aad).

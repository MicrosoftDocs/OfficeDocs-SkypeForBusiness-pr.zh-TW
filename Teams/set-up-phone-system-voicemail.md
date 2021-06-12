---
title: 設定 [雲端語音信箱]
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: '瞭解如何為使用者雲端語音信箱帳戶。 '
ms.openlocfilehash: c6fbd02e30c5be0280b05088a1cec281c2534039
ms.sourcegitcommit: 31c5b9cd3d4f500e1f9d7823052dae8f8c298b1e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2021
ms.locfileid: "52901901"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="4dab7-103">設定 [雲端語音信箱]</span><span class="sxs-lookup"><span data-stu-id="4dab7-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="4dab7-104">本文適用于Microsoft 365或Office 365系統管理員，如想要為企業雲端語音信箱設定此功能的系統管理員角色[](/microsoft-365/admin/add-users/about-admin-roles)所述。</span><span class="sxs-lookup"><span data-stu-id="4dab7-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="4dab7-105">雲端語音信箱只支援將語音信箱Exchange信箱中，且不支援任何協力廠商電子郵件系統。</span><span class="sxs-lookup"><span data-stu-id="4dab7-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="4dab7-106">當代理人代表委派者接聽來電時，雲端語音信箱。</span><span class="sxs-lookup"><span data-stu-id="4dab7-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="4dab7-107">使用者可以接收未接來電的通知。</span><span class="sxs-lookup"><span data-stu-id="4dab7-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="4dab7-108">雲端環境：設定適用于雲端語音信箱使用者電話系統設定</span><span class="sxs-lookup"><span data-stu-id="4dab7-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="4dab7-109">針對 Online 電話系統使用者，雲端語音信箱指派授權給使用者之後，系統會自動為使用者設定 **電話系統** 並設定。</span><span class="sxs-lookup"><span data-stu-id="4dab7-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="4dab7-110">針對 Online 商務用 Skype 電話系統內部部署提供電話號碼的使用者，您可能需要使用[Set-CsUser -HostedVoicemail](/powershell/module/skype/set-csuser?view=skype-ps)$True。</span><span class="sxs-lookup"><span data-stu-id="4dab7-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="4dab7-111">設定雲端語音信箱信箱Exchange Server使用者</span><span class="sxs-lookup"><span data-stu-id="4dab7-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="4dab7-112">下列資訊說明如何雲端語音信箱線上的使用者使用電話系統但信箱位於Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="4dab7-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="4dab7-113">語音信箱訊息會透過透過 Exchange 路由的 SMTP 傳送到使用者的信箱Exchange Online Protection。</span><span class="sxs-lookup"><span data-stu-id="4dab7-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="4dab7-114">若要順利傳遞這些郵件，請確定已正確Exchange伺服器與伺服器之間的連接器Exchange連接器Exchange Online Protection;[使用連接器設定郵件Flow。](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)</span><span class="sxs-lookup"><span data-stu-id="4dab7-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="4dab7-115">若要啟用語音信箱功能，例如自訂 商務用 Skype 用戶端中的問候語和視覺語音信箱，必須透過 Microsoft 365 web Services 從 Microsoft 365 或 Office 365 連接到 Exchange Exchange 伺服器信箱。</span><span class="sxs-lookup"><span data-stu-id="4dab7-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="4dab7-116">若要啟用此連接，您必須設定 Exchange 與 Exchange Online 組織之間設定[OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)驗證中所述的新 Exchange 的致法驗證通訊協定，或執行 Exchange 2013 CU5 或更大的 Exchange 混合式精靈。</span><span class="sxs-lookup"><span data-stu-id="4dab7-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="4dab7-117">此外，您必須在 商務用 Skype Online 和 Exchange 伺服器之間設定整合和小Exchange在 商務用 Skype Online 和[Exchange Server 之間設定整合和 OAuth。](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)</span><span class="sxs-lookup"><span data-stu-id="4dab7-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="4dab7-118">設定雲端語音信箱使用者商務用 Skype Server設定</span><span class="sxs-lookup"><span data-stu-id="4dab7-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="4dab7-119">若要設定商務用 Skype伺服器使用者雲端語音信箱，請參閱規劃雲端語音信箱[內部部署使用者的服務](/skypeforbusiness/hybrid/plan-cloud-voicemail)。</span><span class="sxs-lookup"><span data-stu-id="4dab7-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="4dab7-120">在貴組織中啟用受保護的語音信箱</span><span class="sxs-lookup"><span data-stu-id="4dab7-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="4dab7-121">當某人為貴組織的使用者留下語音信箱訊息時，語音信箱會以電子郵件訊息附件形式傳送到使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="4dab7-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="4dab7-122">您可以使用郵件流程規則來申請郵件加密，以防止這些語音信箱訊息轉寄給其他收件者。</span><span class="sxs-lookup"><span data-stu-id="4dab7-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="4dab7-123">當您啟用受保護的語音信箱時，使用者可以在語音信箱中通話，或在 Outlook、Outlook 網頁版或 android 或 iOS 版 Outlook 中開啟郵件，來聆聽受保護的語音信箱訊息。</span><span class="sxs-lookup"><span data-stu-id="4dab7-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="4dab7-124">受保護的語音信箱訊息無法于 商務用 Skype 或 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="4dab7-124">Protected voicemail messages can't be opened in Skype for Business or Microsoft Teams.</span></span>

<span data-ttu-id="4dab7-125">有關郵件加密的資訊，請參閱 [電子郵件加密](/microsoft-365/compliance/email-encryption?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="4dab7-125">For more information about message encryption, see [Email encryption](/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="4dab7-126">若要設定受保護的語音信箱，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="4dab7-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="4dab7-127">使用 https://admin.microsoft.com 具有全域系統管理員許可權的帳戶前往並登錄。</span><span class="sxs-lookup"><span data-stu-id="4dab7-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="4dab7-128">選取 **顯示全部**，然後前往系統管理  >  **中心Exchange。**</span><span class="sxs-lookup"><span data-stu-id="4dab7-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="4dab7-129">在系統管理Exchange，選取 **郵件流程**  >  **規則**。</span><span class="sxs-lookup"><span data-stu-id="4dab7-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="4dab7-130">選取 **+** **新增**，然後選取 Office 365 郵件加密 **郵件的適用和許可權保護**。</span><span class="sxs-lookup"><span data-stu-id="4dab7-130">Select **+** **Add**, and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="4dab7-131">提供新郵件流程規則的名稱，然後在下列的下列條件中選取郵件屬性 ：包括  >    >  **語音信箱的郵件類型**。</span><span class="sxs-lookup"><span data-stu-id="4dab7-131">Provide a name for the new mail flow rule and then under **Apply this rule if**, select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="4dab7-132">選取 **確定**。</span><span class="sxs-lookup"><span data-stu-id="4dab7-132">Select **OK**.</span></span>
6. <span data-ttu-id="4dab7-133">在 **執行下列操作下**，選取 Office 365 郵件加密郵件的適用許可權保護，然後選取選取 **其中一個**。</span><span class="sxs-lookup"><span data-stu-id="4dab7-133">Under **Do the following**, select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="4dab7-134">在 **RMS 範本下**，選取 **不要轉出**。</span><span class="sxs-lookup"><span data-stu-id="4dab7-134">Under **RMS template**, select **Do not forward**.</span></span> <span data-ttu-id="4dab7-135">選取 **確定** ，然後 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="4dab7-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="4dab7-136">如果 **RMS 範本** 清單是空的，您必須設定郵件加密。</span><span class="sxs-lookup"><span data-stu-id="4dab7-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="4dab7-137">有關設定郵件加密的資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="4dab7-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="4dab7-138">設定新的郵件加密功能</span><span class="sxs-lookup"><span data-stu-id="4dab7-138">Set up new Message Encryption capabilities</span></span>](/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="4dab7-139">為 Azure 資訊保護組組及管理範本</span><span class="sxs-lookup"><span data-stu-id="4dab7-139">Configuring and managing templates for Azure Information Protection</span></span>](/information-protection/deploy-use/configure-policy-templates)
    > - [<span data-ttu-id="4dab7-140">電子郵件的請勿轉轉選項</span><span class="sxs-lookup"><span data-stu-id="4dab7-140">Do Not Forward option for emails</span></span>](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="4dab7-141">協助使用者瞭解Teams語音信箱功能</span><span class="sxs-lookup"><span data-stu-id="4dab7-141">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="4dab7-142">我們有下列資訊可讓使用者管理語音信箱設定，以及其他通話Teams：</span><span class="sxs-lookup"><span data-stu-id="4dab7-142">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="4dab7-143">[在 中管理您的通話Teams。](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="4dab7-143">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="4dab7-144">本文說明如何管理所有使用者通話Teams功能。</span><span class="sxs-lookup"><span data-stu-id="4dab7-144">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="4dab7-145">協助使用者瞭解商務用 Skype語音信箱功能</span><span class="sxs-lookup"><span data-stu-id="4dab7-145">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="4dab7-146">我們有訓練資訊和文章，可協助使用者成功使用語音信箱商務用 Skype語音信箱。</span><span class="sxs-lookup"><span data-stu-id="4dab7-146">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="4dab7-147">指向下列文章：</span><span class="sxs-lookup"><span data-stu-id="4dab7-147">Point them to the following articles:</span></span>

- <span data-ttu-id="4dab7-148">檢查[商務用 Skype](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)和選項：本文說明如何在 商務用 Skype 中聆聽語音信箱、變更語音信箱問候語、變更語音信箱設定，以及以不同速度聆聽語音信箱。</span><span class="sxs-lookup"><span data-stu-id="4dab7-148">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="4dab7-149">商務用 Skype 2016 年訓練</span><span class="sxs-lookup"><span data-stu-id="4dab7-149">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="4dab7-150">相關主題</span><span class="sxs-lookup"><span data-stu-id="4dab7-150">Related topics</span></span>
[<span data-ttu-id="4dab7-151">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="4dab7-151">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="4dab7-152">以下是可透過電話系統獲得的功能</span><span class="sxs-lookup"><span data-stu-id="4dab7-152">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="4dab7-153">規劃商務用 Skype 和 Exchange Server 的先決條件的移轉</span><span class="sxs-lookup"><span data-stu-id="4dab7-153">Plan for Skype for Business Server and Exchange Server migration</span></span>](/SkypeForBusiness/hybrid/plan-um-migration)

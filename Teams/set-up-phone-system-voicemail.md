---
title: 設定雲端語音信箱
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: '瞭解如何為您的使用者設定雲端語音信箱。 '
ms.openlocfilehash: 5526bee2bd365a4047e3641ea223941227858d1a
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "44523116"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="e1f9b-103">設定雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="e1f9b-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="e1f9b-104">本文適用于想要為企業中的每個人設定雲端語音信箱功能的[Office 365 系統管理員](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="e1f9b-105">雲端語音信箱支援僅在 Exchange 信箱中存放語音信箱訊息，且不支援任何協力廠商電子郵件系統。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-phone-system-users"></a><span data-ttu-id="e1f9b-106">僅限雲端的環境：為電話系統使用者設定雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="e1f9b-106">Cloud-only environments: Set up Cloud Voicemail for Phone System users</span></span>

<span data-ttu-id="e1f9b-107">針對商務用 Skype Online 和通話方案使用者，在您指派**電話系統**授權及電話號碼之後，就會自動為使用者設定和設定雲端語音信箱。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="e1f9b-108">如果您的方案中不包含電話系統功能，您可能需要購買 [**電話系統**附加元件授權]。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="e1f9b-109">您可能也需要購買 Exchange Online 授權。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="e1f9b-110">請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="e1f9b-111">[指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[指派 Microsoft 團隊附加元件授權](teams-add-on-licensing/assign-teams-add-on-licenses.md)，以及 Exchange Online 授權給您企業中的人員。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-111">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="e1f9b-112">完成之後，他們就可以接收語音信箱訊息了！</span><span class="sxs-lookup"><span data-stu-id="e1f9b-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="e1f9b-113">已新增到2017年3月的語音信箱支援，且預設為所有組織和使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-113">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="e1f9b-114">您可以使用 Windows PowerShell 來停用您組織的方式，並依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-114">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="e1f9b-115">針對 Exchange Server 信箱使用者設定雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="e1f9b-115">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="e1f9b-116">下列資訊是關於設定雲端語音信箱，以與線上使用電話系統但其信箱在 Exchange 伺服器上的使用者搭配使用。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-116">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="e1f9b-117">如果您的方案中不包含電話系統功能，您可能需要購買 [**電話系統**附加元件授權]。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="e1f9b-118">請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-118">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="e1f9b-119">[將 Microsoft 團隊附加元件授權指派](teams-add-on-licensing/assign-teams-add-on-licenses.md)給您企業中的人員。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-119">[Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md) to the people in your business.</span></span>
    
3. <span data-ttu-id="e1f9b-120">已新增到2017年3月的語音信箱支援，且預設為所有組織和使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-120">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="e1f9b-121">您可以使用 Windows PowerShell 來停用您組織的方式，並依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-121">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

4. <span data-ttu-id="e1f9b-122">語音信箱訊息是透過透過 Exchange Online 防護路由的 SMTP 傳送給使用者的 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-122">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="e1f9b-123">若要啟用成功傳遞這些郵件，請確認 exchange 連接器已在 Exchange 伺服器與 Exchange Online 防護之間正確設定;[使用連接器來設定郵件流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-123">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

6. <span data-ttu-id="e1f9b-124">若要啟用語音信箱功能（例如自訂問候語），以及商務用 Skype 用戶端中的視覺語音信箱，必須從 Office 365 連線至 Exchange server 信箱（透過 Exchange Web 服務）。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-124">To enable Voicemail features such as customizing greetings, and visual voicemail in Skype for Business clients, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="e1f9b-125">若要啟用此連線，您必須設定 exchange[與 Exchange Online 組織之間的 [設定 Oauth 驗證](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)] 中所述的新 Exchange Oauth 驗證通訊協定，或從 EXCHANGE 2013 CU5 或更高版本執行 exchange 混合式嚮導。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-125">To enable this connectivity you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="e1f9b-126">此外，您必須在商務用[Skype online 與 Exchange server 之間設定整合與 oauth](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)中所述的商務用 skype Online 與 exchange server 之間設定整合與 oauth。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-126">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="e1f9b-127">針對商務用 Skype Server 使用者設定雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="e1f9b-127">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="e1f9b-128">下列資訊是關於設定雲端語音信箱，以與線上使用 Exchange 和內部部署的使用者進行商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-128">The following information is about configuring Cloud Voicemail to work with users who are online for Exchange and on-premises for Skype for Business.</span></span> 
  
1. <span data-ttu-id="e1f9b-129">您可能需要將 Exchange Online 授權購買給您企業中的人員。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-129">You may need to purchase Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="e1f9b-130">請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-130">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="e1f9b-131">[指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)，以將 Exchange Online 授權給您企業中的人員。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-131">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="e1f9b-132">已新增到2017年3月的語音信箱支援，且預設為所有組織和使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-132">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="e1f9b-133">您可以使用 Windows PowerShell 來停用您組織的方式，並依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-133">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

4. <span data-ttu-id="e1f9b-134">若要為雲端語音信箱設定商務用 Skype server 使用者，請參閱[規劃雲端語音信箱服務給內部部署使用者](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)</span><span class="sxs-lookup"><span data-stu-id="e1f9b-134">To configure Skype for Business server users for Cloud Voicemail please see [Plan Cloud Voicemail service for on-premises users](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)</span></span>


> [!NOTE]
> <span data-ttu-id="e1f9b-135">當代理人代表 delegator 接聽來電時，在雲端語音信箱中不提供通知。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-135">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="e1f9b-136">使用者可以收到未接來電的通知。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-136">Users can receive notifications for missed calls.</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="e1f9b-137">在組織中啟用受保護的語音信箱</span><span class="sxs-lookup"><span data-stu-id="e1f9b-137">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="e1f9b-138">當有人在您的組織中為使用者留下語音信箱訊息時，語音信箱會以電子郵件附件的形式傳送到使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-138">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="e1f9b-139">使用郵件流程規則來套用郵件加密，您可以防止將這些語音信箱訊息轉寄給其他收件者。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-139">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="e1f9b-140">當您啟用受保護的語音信箱時，使用者可以撥入其語音信箱信箱，或開啟 Outlook、Outlook 網頁版或 Android 版 Outlook 中的郵件，以聆聽受保護的語音信箱訊息。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-140">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="e1f9b-141">受保護的語音信箱訊息無法在商務用 Skype 中開啟。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-141">Protected voicemail messages can't be opened in Skype for Business.</span></span>

<span data-ttu-id="e1f9b-142">如需郵件加密的詳細資訊，請參閱[電子郵件加密](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-142">For more information about message encryption, see [Email encryption](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="e1f9b-143">若要設定受保護的語音信箱，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e1f9b-143">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="e1f9b-144">移至 https://admin.microsoft.com 並使用具有全域管理員許可權的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-144">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="e1f9b-145">選取 [**全部顯示**]，然後移至 [**管理員中心**]  >  **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-145">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="e1f9b-146">在 Exchange Admin Center 中，選取 [**郵件流程**  >  **規則**]。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-146">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="e1f9b-147">選取 [ **+** **新增**]，然後選取 [**將 Office 365 郵件加密及版權保護] 套用至郵件**。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-147">Select **+** **Add**, and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="e1f9b-148">提供新郵件流程規則的名稱，然後在 [套用**此規則**] 底下，選取 **[** 郵件內容]，  >  **其中包含 [**  >  **語音信箱**] 這類訊息。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-148">Provide a name for the new mail flow rule and then under **Apply this rule if**, select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="e1f9b-149">選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-149">Select **OK**.</span></span>
6. <span data-ttu-id="e1f9b-150">在 **[執行下列**動作] 底下，選取 **[將 Office 365 郵件加密與版權保護] 給郵件**，然後選取 [**選取一個**]。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-150">Under **Do the following**, select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="e1f9b-151">在 [ **RMS 範本**] 底下，選取 [**不要轉寄**]。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-151">Under **RMS template**, select **Do not forward**.</span></span> <span data-ttu-id="e1f9b-152">選取 **[確定]** ，然後選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-152">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="e1f9b-153">如果**RMS 範本**清單是空的，您必須設定 Office 365 郵件加密。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-153">If the **RMS template** list is empty, you need to set up Office 365 Message Encryption.</span></span> <span data-ttu-id="e1f9b-154">如需設定 Office 365 郵件加密的詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="e1f9b-154">For more information about setting up Office 365 Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="e1f9b-155">設定新的 Office 365 郵件加密功能</span><span class="sxs-lookup"><span data-stu-id="e1f9b-155">Set up new Office 365 Message Encryption capabilities</span></span>](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="e1f9b-156">設定及管理 Azure 資訊保護範本</span><span class="sxs-lookup"><span data-stu-id="e1f9b-156">Configuring and managing templates for Azure Information Protection</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - <span data-ttu-id="e1f9b-157">[電子郵件的 [不要轉寄] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="e1f9b-157">[Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)</span></span>

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="e1f9b-158">設定組織中的語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="e1f9b-158">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="e1f9b-159">針對商務用 Skype 客戶，透過 Microsoft 團隊通話原則停用語音信箱，也可能會停用商務用 Skype 使用者的語音信箱服務。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-159">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="e1f9b-160">預設會啟用語音語音功能，而且預設會針對所有組織和使用者停用「每個語言不過，您可以使用 [[設定 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) ] 和[[授與 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) ] Cmdlet 來控制它們。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-160">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="e1f9b-161">貴組織中的使用者收到的語音信箱訊息是在託管 Office 365 組織的地區 transcribed。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-161">Voicemail messages received by users in your organization are transcribed in the region where your Office 365 organization is hosted.</span></span> <span data-ttu-id="e1f9b-162">您的租使用者主機所在的地區可能不是接收語音信箱訊息的使用者所在的地區。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-162">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="e1f9b-163">若要查看您的租使用者所在的地區，請移至 [[組織設定檔](https://go.microsoft.com/fwlink/p/?linkid=2067339)] 頁面，然後按一下 [**資料位置**] 旁的 [**查看詳細**資料]。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-163">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1f9b-164">您無法使用**CsOnlineVoiceMailPolicy** Cmdlet 來建立用來進行新的新原則遮罩，且無法使用**remove-CsOnlineVoiceMailPolicy** Cmdlet 來移除現有的原則實例。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-164">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="e1f9b-165">您可以使用語音信箱原則管理使用者的 [使用中] 設定。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-165">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="e1f9b-166">若要查看所有可用的語音信箱原則實例，您可以使用[CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-166">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="e1f9b-167">**PS C： \\> CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="e1f9b-167">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![[取得 CsOnlineVoiceMailPolicy 結果] 視窗。](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="e1f9b-169">關閉組織的單位</span><span class="sxs-lookup"><span data-stu-id="e1f9b-169">Turning off transcription for your organization</span></span>

<span data-ttu-id="e1f9b-170">您的組織的預設設定是開啟，您可能會想要使用 [[設定] CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)停用它。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-170">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="e1f9b-171">若要這樣做，請執行：</span><span class="sxs-lookup"><span data-stu-id="e1f9b-171">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="e1f9b-172">為您的組織開啟 [輸入猥褻遮罩]</span><span class="sxs-lookup"><span data-stu-id="e1f9b-172">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="e1f9b-173">預設情況下，您的組織會停用 [只提供猥褻遮罩] 功能。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-173">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="e1f9b-174">如果有業務需求可啟用它，您可以使用 [[設定] CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)來啟用「轉譯猥褻遮罩」。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-174">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="e1f9b-175">若要這樣做，請執行：</span><span class="sxs-lookup"><span data-stu-id="e1f9b-175">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="e1f9b-176">關閉使用者的使用者</span><span class="sxs-lookup"><span data-stu-id="e1f9b-176">Turning off transcription for a user</span></span>

<span data-ttu-id="e1f9b-177">在組織預設設定之前評估使用者原則。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-177">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="e1f9b-178">例如，如果您的所有使用者都能使用語音信箱，您可以指派原則來停用授與特定使用者的[CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-178">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="e1f9b-179">若要停用單一使用者的操作，請執行：</span><span class="sxs-lookup"><span data-stu-id="e1f9b-179">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="e1f9b-180">為使用者開啟 [輸入猥褻遮罩]</span><span class="sxs-lookup"><span data-stu-id="e1f9b-180">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="e1f9b-181">若要針對特定的使用者啟用 [只適用于「猥褻遮罩]，您可以使用[Grant CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) Cmdlet，指派原則來為特定使用者啟用「轉譯猥褻遮罩]。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-181">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="e1f9b-182">若要針對單一使用者啟用 [只使用「猥褻] 遮罩，請執行：</span><span class="sxs-lookup"><span data-stu-id="e1f9b-182">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="e1f9b-183">Office 365 中的語音信箱服務會緩存語音信箱原則，並每4小時更新一次快取。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-183">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours.</span></span> <span data-ttu-id="e1f9b-184">所以，您所做的原則變更可能需要長達4個小時才能套用。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-184">So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="e1f9b-185">協助您的使用者瞭解團隊語音信箱功能</span><span class="sxs-lookup"><span data-stu-id="e1f9b-185">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="e1f9b-186">我們提供下列資訊，讓您的使用者管理其語音信箱設定，以及團隊中的其他通話功能。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-186">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="e1f9b-187">[在團隊中管理您的通話設定](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-187">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="e1f9b-188">本文說明如何管理所有的最終使用者團隊通話功能。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-188">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="e1f9b-189">協助使用者瞭解商務用 Skype 語音信箱功能</span><span class="sxs-lookup"><span data-stu-id="e1f9b-189">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="e1f9b-190">我們有訓練資訊和文章，可協助您的使用者成功使用商務用 Skype 語音信箱。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-190">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="e1f9b-191">請將它們指向下列文章：</span><span class="sxs-lookup"><span data-stu-id="e1f9b-191">Point them to the following articles:</span></span>

- <span data-ttu-id="e1f9b-192">[查看商務用 skype 語音信箱和選項](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)：本文說明如何在商務用 skype 中收聽語音信箱、變更語音信箱問候語、變更語音信箱設定，以及以不同的速度聆聽語音信箱。</span><span class="sxs-lookup"><span data-stu-id="e1f9b-192">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="e1f9b-193">商務用 Skype 2016 訓練</span><span class="sxs-lookup"><span data-stu-id="e1f9b-193">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="e1f9b-194">相關主題</span><span class="sxs-lookup"><span data-stu-id="e1f9b-194">Related topics</span></span>
[<span data-ttu-id="e1f9b-195">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="e1f9b-195">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="e1f9b-196">以下是您在 Office 365 中使用電話系統所取得的結果</span><span class="sxs-lookup"><span data-stu-id="e1f9b-196">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="e1f9b-197">規劃商務用 Skype 和 Exchange Server 的先決條件的移轉</span><span class="sxs-lookup"><span data-stu-id="e1f9b-197">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)


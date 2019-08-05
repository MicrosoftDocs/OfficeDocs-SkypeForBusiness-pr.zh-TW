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
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '瞭解如何為您的使用者設定雲端語音信箱。 '
ms.openlocfilehash: 8417d8338f8ba25b9f3c92d9fc4547ed861f8b8e
ms.sourcegitcommit: 4fb1c691f0f84d47e215c9c1775da9bdba875f61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2019
ms.locfileid: "36184425"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="65df9-103">設定雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="65df9-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="65df9-104">本文適用于想要為企業中的每個人設定雲端語音信箱功能的[Office 365 系統管理員](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="65df9-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="65df9-105">雲端語音信箱支援僅在 Exchange 信箱中存放語音信箱訊息, 且不支援任何協力廠商電子郵件系統。</span><span class="sxs-lookup"><span data-stu-id="65df9-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a><span data-ttu-id="65df9-106">僅限雲端的環境: 設定雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="65df9-106">Cloud-only environments: Set up Cloud Voicemail</span></span>

<span data-ttu-id="65df9-107">針對商務用 Skype Online 和通話方案使用者, 在您指派**電話系統**授權及電話號碼之後, 就會自動為使用者設定和設定雲端語音信箱。</span><span class="sxs-lookup"><span data-stu-id="65df9-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="65df9-108">如果您的方案中不包含電話系統功能, 您可能需要購買 [**電話系統**附加元件授權]。</span><span class="sxs-lookup"><span data-stu-id="65df9-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="65df9-109">您可能也需要購買 Exchange Online 授權。</span><span class="sxs-lookup"><span data-stu-id="65df9-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="65df9-110">請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="65df9-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="65df9-111">[指派或移除商務用 Office 365 的授權](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[指派 Microsoft 團隊授權](assign-teams-licenses.md), 以及 Exchange Online 授權給您企業中的人員。</span><span class="sxs-lookup"><span data-stu-id="65df9-111">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="65df9-112">完成之後, 他們就可以接收語音信箱訊息了!</span><span class="sxs-lookup"><span data-stu-id="65df9-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="65df9-113">已新增到2017年3月的語音信箱支援, 且預設為所有組織和使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="65df9-113">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="65df9-114">您可以使用 Windows PowerShell 來停用您組織的方式, 並依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="65df9-114">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="65df9-115">具有內部部署環境的電話系統</span><span class="sxs-lookup"><span data-stu-id="65df9-115">Phone System with on-premises environments</span></span>

<span data-ttu-id="65df9-116">下列資訊是關於設定雲端語音信箱來與內部部署通話方案環境搭配使用。</span><span class="sxs-lookup"><span data-stu-id="65df9-116">The following information is about configuring Cloud Voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="65df9-117">如果您的方案中不包含電話系統功能, 您可能需要購買 [**電話系統**附加元件授權]。</span><span class="sxs-lookup"><span data-stu-id="65df9-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="65df9-118">您也需要購買 Exchange Online 授權。</span><span class="sxs-lookup"><span data-stu-id="65df9-118">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="65df9-119">請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="65df9-119">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="65df9-120">[指派或移除商務用 Office 365 的授權](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[指派 Microsoft 團隊授權](assign-teams-licenses.md), 以及 Exchange Online 授權給您企業中的人員。</span><span class="sxs-lookup"><span data-stu-id="65df9-120">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="65df9-121">遵循針對您的使用者部署的內部部署 PSTN 呼叫解決方案的指示。</span><span class="sxs-lookup"><span data-stu-id="65df9-121">Follow instructions matching on-premises PSTN calling solution deployed for your users.</span></span> <span data-ttu-id="65df9-122">如果是雲端連接器版本, 請依照[設定商務用 Skype 雲端連接器版本指南](https://technet.microsoft.com/library/mt605228.aspx)中的 [**允許使用者使用電話系統語音及語音信箱服務**] 區段中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="65df9-122">For Cloud Connector Edition, follow instructions in the **Enable users for Phone System voice and voicemail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span> <span data-ttu-id="65df9-123">針對使用商務用 Skype Server 的 PSTN 通話, 請遵循[啟用企業內部部署的使用者](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises)。</span><span class="sxs-lookup"><span data-stu-id="65df9-123">For PSTN calling with Skype for Business Server, follow [Enable the users for Enterprise Voice on premises](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span></span> <span data-ttu-id="65df9-124">針對團隊直接傳送路線, 請遵循設定[直接路由](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)的 [**設定電話號碼] 和 [啟用企業語音及語音信箱**] 區段。</span><span class="sxs-lookup"><span data-stu-id="65df9-124">For Teams Direct Routing, follow  the **Configure the phone number and enable enterprise voice and voicemail** section of [Configure Direct Routing](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span></span>

4. <span data-ttu-id="65df9-125">已新增到2017年3月的語音信箱支援, 且預設為所有組織和使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="65df9-125">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="65df9-126">您可以使用 Windows PowerShell 來停用您組織的方式, 並依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="65df9-126">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="65df9-127">語音信箱訊息是透過透過 Exchange Online 防護路由的 SMTP 傳送給使用者的 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="65df9-127">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="65df9-128">若要啟用成功傳遞這些郵件, 請確認 exchange 連接器已在 Exchange 伺服器與 Exchange Online 防護之間正確設定;[使用連接器來設定郵件流程](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="65df9-128">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

6. <span data-ttu-id="65df9-129">若要啟用語音信箱功能 (例如自訂問候語), 以及商務用 Skype 用戶端中的視覺語音信箱, 必須從 Office 365 連線至 Exchange server 信箱 (透過 Exchange Web 服務)。</span><span class="sxs-lookup"><span data-stu-id="65df9-129">To enable Voicemail features such as customizing greetings, and visual voicemail in Skype for Business clients, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="65df9-130">若要啟用此連線, 您必須設定 exchange[與 Exchange Online 組織之間的 [設定 Oauth 驗證](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)] 中所述的新 Exchange Oauth 驗證通訊協定, 或從 EXCHANGE 2013 CU5 執行 exchange 混合式嚮導, 或等於.</span><span class="sxs-lookup"><span data-stu-id="65df9-130">To enable this connectivity you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="65df9-131">此外, 您必須在商務用[Skype online 與 Exchange server 之間設定整合與 oauth](https://docs.microsoft.com/en-us/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)中所述的商務用 skype Online 與 exchange server 之間設定整合與 oauth。</span><span class="sxs-lookup"><span data-stu-id="65df9-131">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/en-us/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="65df9-132">設定組織中的語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="65df9-132">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="65df9-133">針對商務用 Skype 客戶, 透過 Microsoft 團隊通話原則停用語音信箱, 也可能會停用商務用 Skype 使用者的語音信箱服務。</span><span class="sxs-lookup"><span data-stu-id="65df9-133">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="65df9-134">預設會啟用語音語音功能, 而且預設會針對所有組織和使用者停用「每個語言不過, 您可以使用 [[設定 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) ] 和[[授與 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) ] Cmdlet 來控制它們。</span><span class="sxs-lookup"><span data-stu-id="65df9-134">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="65df9-135">貴組織中的使用者收到的語音信箱訊息是在您的 Office 365 租使用者託管的地區中 transcribed。</span><span class="sxs-lookup"><span data-stu-id="65df9-135">Voicemail messages received by users in your organization are transcribed in the region where your Office 365 tenant is hosted.</span></span> <span data-ttu-id="65df9-136">您的租使用者主機所在的地區可能不是接收語音信箱訊息的使用者所在的地區。</span><span class="sxs-lookup"><span data-stu-id="65df9-136">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="65df9-137">若要查看您的租使用者所在的地區, 請移至 [[組織設定檔](https://go.microsoft.com/fwlink/p/?linkid=2067339)] 頁面, 然後按一下 [**資料位置**] 旁的 [**查看詳細**資料]。</span><span class="sxs-lookup"><span data-stu-id="65df9-137">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="65df9-138">您無法使用**CsOnlineVoiceMailPolicy** Cmdlet 來建立用來進行新的新原則遮罩, 而且您無法使用 CsOnlineVoiceMailPolicy Cmdlet 移除現有**的**原則實例。.</span><span class="sxs-lookup"><span data-stu-id="65df9-138">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="65df9-139">您可以使用語音信箱原則管理使用者的 [使用中] 設定。</span><span class="sxs-lookup"><span data-stu-id="65df9-139">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="65df9-140">若要查看所有可用的語音信箱原則實例, 您可以使用[CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="65df9-140">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="65df9-141">**PS C:\\> CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="65df9-141">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![[取得 CsOnlineVoiceMailPolicy 結果] 視窗。](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="65df9-143">關閉組織的單位</span><span class="sxs-lookup"><span data-stu-id="65df9-143">Turning off transcription for your organization</span></span>

<span data-ttu-id="65df9-144">您的組織的預設設定是開啟, 您可能會想要使用 [[設定] CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)停用它。</span><span class="sxs-lookup"><span data-stu-id="65df9-144">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="65df9-145">若要這樣做, 請執行:</span><span class="sxs-lookup"><span data-stu-id="65df9-145">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="65df9-146">為您的組織開啟 [輸入猥褻遮罩]</span><span class="sxs-lookup"><span data-stu-id="65df9-146">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="65df9-147">預設情況下, 您的組織會停用 [只提供猥褻遮罩] 功能。</span><span class="sxs-lookup"><span data-stu-id="65df9-147">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="65df9-148">如果有業務需求可啟用它, 您可以使用 [[設定] CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)來啟用「轉譯猥褻遮罩」。</span><span class="sxs-lookup"><span data-stu-id="65df9-148">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="65df9-149">若要這樣做, 請執行:</span><span class="sxs-lookup"><span data-stu-id="65df9-149">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="65df9-150">關閉使用者的使用者</span><span class="sxs-lookup"><span data-stu-id="65df9-150">Turning off transcription for a user</span></span>

<span data-ttu-id="65df9-151">在組織預設設定之前評估使用者原則。</span><span class="sxs-lookup"><span data-stu-id="65df9-151">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="65df9-152">例如, 如果您的所有使用者都能使用語音信箱, 您可以指派原則來停用授與特定使用者的[CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="65df9-152">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="65df9-153">若要停用單一使用者的操作, 請執行:</span><span class="sxs-lookup"><span data-stu-id="65df9-153">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="65df9-154">為使用者開啟 [輸入猥褻遮罩]</span><span class="sxs-lookup"><span data-stu-id="65df9-154">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="65df9-155">若要針對特定的使用者啟用 [只適用于「猥褻遮罩], 您可以使用[Grant CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) Cmdlet, 指派原則來為特定使用者啟用「轉譯猥褻遮罩]。</span><span class="sxs-lookup"><span data-stu-id="65df9-155">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="65df9-156">若要針對單一使用者啟用 [只使用「猥褻] 遮罩, 請執行:</span><span class="sxs-lookup"><span data-stu-id="65df9-156">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="65df9-157">Office 365 中的語音信箱服務會緩存語音信箱原則, 並每4小時更新一次快取。</span><span class="sxs-lookup"><span data-stu-id="65df9-157">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours.</span></span> <span data-ttu-id="65df9-158">所以, 您所做的原則變更可能需要長達4個小時才能套用。</span><span class="sxs-lookup"><span data-stu-id="65df9-158">So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="65df9-159">協助使用者瞭解商務用 Skype 語音信箱功能</span><span class="sxs-lookup"><span data-stu-id="65df9-159">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="65df9-160">我們有訓練資訊和文章, 可協助您的使用者成功使用商務用 Skype 語音信箱。</span><span class="sxs-lookup"><span data-stu-id="65df9-160">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="65df9-161">請將它們指向下列文章:</span><span class="sxs-lookup"><span data-stu-id="65df9-161">Point them to the following articles:</span></span>

- <span data-ttu-id="65df9-162">[查看商務用 skype 語音信箱和選項](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): 本文說明如何在商務用 skype 中收聽語音信箱、變更語音信箱問候語、變更語音信箱設定, 以及以不同的速度聆聽語音信箱。</span><span class="sxs-lookup"><span data-stu-id="65df9-162">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="65df9-163">商務用 Skype 2016 訓練</span><span class="sxs-lookup"><span data-stu-id="65df9-163">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="65df9-164">相關主題</span><span class="sxs-lookup"><span data-stu-id="65df9-164">Related topics</span></span>
[<span data-ttu-id="65df9-165">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="65df9-165">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="65df9-166">以下是您在 Office 365 中使用電話系統所取得的結果</span><span class="sxs-lookup"><span data-stu-id="65df9-166">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="65df9-167">規劃商務用 Skype Server 與 Exchange Server 遷移</span><span class="sxs-lookup"><span data-stu-id="65df9-167">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/plan-um-migration)



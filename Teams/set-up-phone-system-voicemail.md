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
ms.openlocfilehash: d747b86d50cf4e81398d53bbc3602bff9cc4351c
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349717"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="12b82-103">設定雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="12b82-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="12b82-104">本文適用于想要為企業中的每個人設定雲端語音信箱功能的[Office 365 系統管理員](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="12b82-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="12b82-105">雲端語音信箱支援僅在 Exchange 信箱中存放語音信箱訊息，且不支援任何協力廠商電子郵件系統。</span><span class="sxs-lookup"><span data-stu-id="12b82-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-cloud-psystem-users"></a><span data-ttu-id="12b82-106">僅限雲端的環境：為雲端 Psystem 使用者設定雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="12b82-106">Cloud-only environments: Set up Cloud Voicemail for Cloud Psystem Users</span></span>

<span data-ttu-id="12b82-107">針對商務用 Skype Online 和通話方案使用者，在您指派**電話系統**授權及電話號碼之後，就會自動為使用者設定和設定雲端語音信箱。</span><span class="sxs-lookup"><span data-stu-id="12b82-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="12b82-108">如果您的方案中不包含電話系統功能，您可能需要購買 [**電話系統**附加元件授權]。</span><span class="sxs-lookup"><span data-stu-id="12b82-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="12b82-109">您可能也需要購買 Exchange Online 授權。</span><span class="sxs-lookup"><span data-stu-id="12b82-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="12b82-110">請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="12b82-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="12b82-111">[指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[指派 Microsoft 團隊附加元件授權](teams-add-on-licensing/assign-teams-add-on-licenses.md)，以及 Exchange Online 授權給您企業中的人員。</span><span class="sxs-lookup"><span data-stu-id="12b82-111">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="12b82-112">完成之後，他們就可以接收語音信箱訊息了！</span><span class="sxs-lookup"><span data-stu-id="12b82-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="12b82-113">已新增到2017年3月的語音信箱支援，且預設為所有組織和使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="12b82-113">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="12b82-114">您可以使用 Windows PowerShell 來停用您組織的方式，並依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="12b82-114">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="12b82-115">針對 Exchange Server 信箱使用者設定雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="12b82-115">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="12b82-116">下列資訊是關於設定雲端語音信箱，以與線上使用電話系統但其信箱在 Exchange 伺服器上的使用者搭配使用。</span><span class="sxs-lookup"><span data-stu-id="12b82-116">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="12b82-117">如果您的方案中不包含電話系統功能，您可能需要購買 [**電話系統**附加元件授權]。</span><span class="sxs-lookup"><span data-stu-id="12b82-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="12b82-118">請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="12b82-118">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="12b82-119">[將 Microsoft 團隊附加元件授權指派](teams-add-on-licensing/assign-teams-add-on-licenses.md)給您企業中的人員。</span><span class="sxs-lookup"><span data-stu-id="12b82-119">[Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md) to the people in your business.</span></span>
    
3. <span data-ttu-id="12b82-120">已新增到2017年3月的語音信箱支援，且預設為所有組織和使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="12b82-120">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="12b82-121">您可以使用 Windows PowerShell 來停用您組織的方式，並依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="12b82-121">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

4. <span data-ttu-id="12b82-122">語音信箱訊息是透過透過 Exchange Online 防護路由的 SMTP 傳送給使用者的 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="12b82-122">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="12b82-123">若要啟用成功傳遞這些郵件，請確認 exchange 連接器已在 Exchange 伺服器與 Exchange Online 防護之間正確設定;[使用連接器來設定郵件流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="12b82-123">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

6. <span data-ttu-id="12b82-124">若要啟用語音信箱功能（例如自訂問候語），以及商務用 Skype 用戶端中的視覺語音信箱，必須從 Office 365 連線至 Exchange server 信箱（透過 Exchange Web 服務）。</span><span class="sxs-lookup"><span data-stu-id="12b82-124">To enable Voicemail features such as customizing greetings, and visual voicemail in Skype for Business clients, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="12b82-125">若要啟用此連線，您必須設定 exchange[與 Exchange Online 組織之間的 [設定 Oauth 驗證](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)] 中所述的新 Exchange Oauth 驗證通訊協定，或從 EXCHANGE 2013 CU5 或更高版本執行 exchange 混合式嚮導。</span><span class="sxs-lookup"><span data-stu-id="12b82-125">To enable this connectivity you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="12b82-126">此外，您必須在商務用[Skype online 與 Exchange server 之間設定整合與 oauth](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)中所述的商務用 skype Online 與 exchange server 之間設定整合與 oauth。</span><span class="sxs-lookup"><span data-stu-id="12b82-126">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="12b82-127">針對商務用 Skype Server 使用者設定雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="12b82-127">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="12b82-128">下列資訊是關於設定雲端語音信箱，以與線上使用 Exchange 和內部部署的使用者進行商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="12b82-128">The following information is about configuring Cloud Voicemail to work with users who are online for Exchange and on-premises for Skype for Business.</span></span> 
  
1. <span data-ttu-id="12b82-129">您可能需要將 Exchange Online 授權購買給您企業中的人員。</span><span class="sxs-lookup"><span data-stu-id="12b82-129">You may need to purchase Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="12b82-130">請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="12b82-130">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="12b82-131">[指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)，以將 Exchange Online 授權給您企業中的人員。</span><span class="sxs-lookup"><span data-stu-id="12b82-131">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="12b82-132">已新增到2017年3月的語音信箱支援，且預設為所有組織和使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="12b82-132">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="12b82-133">您可以使用 Windows PowerShell 來停用您組織的方式，並依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="12b82-133">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

4. <span data-ttu-id="12b82-134">若要為雲端語音信箱設定商務用 Skype server 使用者，請參閱[規劃雲端語音信箱服務給內部部署使用者](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)</span><span class="sxs-lookup"><span data-stu-id="12b82-134">To configure Skype for Business server users for Cloud Voicemail please see [Plan Cloud Voicemail service for on-premises users](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)</span></span>


> [!NOTE]
> <span data-ttu-id="12b82-135">當代理人代表 delegator 接聽來電時，在雲端語音信箱中不提供通知。</span><span class="sxs-lookup"><span data-stu-id="12b82-135">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="12b82-136">使用者可以收到未接來電的通知。</span><span class="sxs-lookup"><span data-stu-id="12b82-136">Users can receive notifications for missed calls.</span></span>

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="12b82-137">設定組織中的語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="12b82-137">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="12b82-138">針對商務用 Skype 客戶，透過 Microsoft 團隊通話原則停用語音信箱，也可能會停用商務用 Skype 使用者的語音信箱服務。</span><span class="sxs-lookup"><span data-stu-id="12b82-138">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="12b82-139">預設會啟用語音語音功能，而且預設會針對所有組織和使用者停用「每個語言不過，您可以使用 [[設定 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) ] 和[[授與 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) ] Cmdlet 來控制它們。</span><span class="sxs-lookup"><span data-stu-id="12b82-139">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="12b82-140">貴組織中的使用者收到的語音信箱訊息是在託管 Office 365 組織的地區 transcribed。</span><span class="sxs-lookup"><span data-stu-id="12b82-140">Voicemail messages received by users in your organization are transcribed in the region where your Office 365 organization is hosted.</span></span> <span data-ttu-id="12b82-141">您的租使用者主機所在的地區可能不是接收語音信箱訊息的使用者所在的地區。</span><span class="sxs-lookup"><span data-stu-id="12b82-141">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="12b82-142">若要查看您的租使用者所在的地區，請移至 [[組織設定檔](https://go.microsoft.com/fwlink/p/?linkid=2067339)] 頁面，然後按一下 [**資料位置**] 旁的 [**查看詳細**資料]。</span><span class="sxs-lookup"><span data-stu-id="12b82-142">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="12b82-143">您無法使用**CsOnlineVoiceMailPolicy** Cmdlet 來建立用來進行新的新原則遮罩，且無法使用**remove-CsOnlineVoiceMailPolicy** Cmdlet 來移除現有的原則實例。</span><span class="sxs-lookup"><span data-stu-id="12b82-143">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="12b82-144">您可以使用語音信箱原則管理使用者的 [使用中] 設定。</span><span class="sxs-lookup"><span data-stu-id="12b82-144">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="12b82-145">若要查看所有可用的語音信箱原則實例，您可以使用[CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="12b82-145">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="12b82-146">**PS C： \\> CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="12b82-146">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![[取得 CsOnlineVoiceMailPolicy 結果] 視窗。](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="12b82-148">關閉組織的單位</span><span class="sxs-lookup"><span data-stu-id="12b82-148">Turning off transcription for your organization</span></span>

<span data-ttu-id="12b82-149">您的組織的預設設定是開啟，您可能會想要使用 [[設定] CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)停用它。</span><span class="sxs-lookup"><span data-stu-id="12b82-149">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="12b82-150">若要這樣做，請執行：</span><span class="sxs-lookup"><span data-stu-id="12b82-150">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="12b82-151">為您的組織開啟 [輸入猥褻遮罩]</span><span class="sxs-lookup"><span data-stu-id="12b82-151">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="12b82-152">預設情況下，您的組織會停用 [只提供猥褻遮罩] 功能。</span><span class="sxs-lookup"><span data-stu-id="12b82-152">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="12b82-153">如果有業務需求可啟用它，您可以使用 [[設定] CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)來啟用「轉譯猥褻遮罩」。</span><span class="sxs-lookup"><span data-stu-id="12b82-153">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="12b82-154">若要這樣做，請執行：</span><span class="sxs-lookup"><span data-stu-id="12b82-154">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="12b82-155">關閉使用者的使用者</span><span class="sxs-lookup"><span data-stu-id="12b82-155">Turning off transcription for a user</span></span>

<span data-ttu-id="12b82-156">在組織預設設定之前評估使用者原則。</span><span class="sxs-lookup"><span data-stu-id="12b82-156">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="12b82-157">例如，如果您的所有使用者都能使用語音信箱，您可以指派原則來停用授與特定使用者的[CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="12b82-157">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="12b82-158">若要停用單一使用者的操作，請執行：</span><span class="sxs-lookup"><span data-stu-id="12b82-158">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="12b82-159">為使用者開啟 [輸入猥褻遮罩]</span><span class="sxs-lookup"><span data-stu-id="12b82-159">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="12b82-160">若要針對特定的使用者啟用 [只適用于「猥褻遮罩]，您可以使用[Grant CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) Cmdlet，指派原則來為特定使用者啟用「轉譯猥褻遮罩]。</span><span class="sxs-lookup"><span data-stu-id="12b82-160">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="12b82-161">若要針對單一使用者啟用 [只使用「猥褻] 遮罩，請執行：</span><span class="sxs-lookup"><span data-stu-id="12b82-161">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="12b82-162">Office 365 中的語音信箱服務會緩存語音信箱原則，並每4小時更新一次快取。</span><span class="sxs-lookup"><span data-stu-id="12b82-162">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours.</span></span> <span data-ttu-id="12b82-163">所以，您所做的原則變更可能需要長達4個小時才能套用。</span><span class="sxs-lookup"><span data-stu-id="12b82-163">So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="12b82-164">協助您的使用者瞭解團隊語音信箱功能</span><span class="sxs-lookup"><span data-stu-id="12b82-164">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="12b82-165">我們提供下列資訊，讓您的使用者管理其語音信箱設定，以及團隊中的其他通話功能。</span><span class="sxs-lookup"><span data-stu-id="12b82-165">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="12b82-166">[在團隊中管理您的通話設定](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)。</span><span class="sxs-lookup"><span data-stu-id="12b82-166">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="12b82-167">本文說明如何管理所有的最終使用者團隊通話功能。</span><span class="sxs-lookup"><span data-stu-id="12b82-167">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="12b82-168">協助使用者瞭解商務用 Skype 語音信箱功能</span><span class="sxs-lookup"><span data-stu-id="12b82-168">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="12b82-169">我們有訓練資訊和文章，可協助您的使用者成功使用商務用 Skype 語音信箱。</span><span class="sxs-lookup"><span data-stu-id="12b82-169">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="12b82-170">請將它們指向下列文章：</span><span class="sxs-lookup"><span data-stu-id="12b82-170">Point them to the following articles:</span></span>

- <span data-ttu-id="12b82-171">[查看商務用 skype 語音信箱和選項](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)：本文說明如何在商務用 skype 中收聽語音信箱、變更語音信箱問候語、變更語音信箱設定，以及以不同的速度聆聽語音信箱。</span><span class="sxs-lookup"><span data-stu-id="12b82-171">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="12b82-172">商務用 Skype 2016 訓練</span><span class="sxs-lookup"><span data-stu-id="12b82-172">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="12b82-173">相關主題</span><span class="sxs-lookup"><span data-stu-id="12b82-173">Related topics</span></span>
[<span data-ttu-id="12b82-174">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="12b82-174">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="12b82-175">以下是您在 Office 365 中使用電話系統所取得的結果</span><span class="sxs-lookup"><span data-stu-id="12b82-175">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="12b82-176">規劃商務用 Skype 和 Exchange Server 的先決條件的移轉</span><span class="sxs-lookup"><span data-stu-id="12b82-176">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)


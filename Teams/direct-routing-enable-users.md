---
title: 啟用使用者進行直接路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解如何啟用使用者Microsoft 電話直接路由。
ms.openlocfilehash: 7d2b7c4b5d6268d1498a47537e0edbbf892198aa
ms.sourcegitcommit: cae94cd5761baafde51aea1137e6d164722eead9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53075366"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="92214-103">啟用使用者進行直接路由、語音和語音信箱</span><span class="sxs-lookup"><span data-stu-id="92214-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="92214-104">本文將說明如何啟用使用者進行電話系統路由。</span><span class="sxs-lookup"><span data-stu-id="92214-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="92214-105">這是下列步驟中的步驟 2，用於配置直接路由：</span><span class="sxs-lookup"><span data-stu-id="92214-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="92214-106">步驟 1.</span><span class="sxs-lookup"><span data-stu-id="92214-106">Step 1.</span></span> [<span data-ttu-id="92214-107">連線系統Microsoft 電話 SBC 並驗證連接</span><span class="sxs-lookup"><span data-stu-id="92214-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="92214-108">**步驟 2.啟用使用者進行直接路由、語音和語音信箱 (**   本文) </span><span class="sxs-lookup"><span data-stu-id="92214-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="92214-109">步驟 3.</span><span class="sxs-lookup"><span data-stu-id="92214-109">Step 3.</span></span> [<span data-ttu-id="92214-110">設定語音路由</span><span class="sxs-lookup"><span data-stu-id="92214-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="92214-111">步驟 4.</span><span class="sxs-lookup"><span data-stu-id="92214-111">Step 4.</span></span> [<span data-ttu-id="92214-112">將數位轉換成替代格式</span><span class="sxs-lookup"><span data-stu-id="92214-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="92214-113">若要瞭解設定直接路由所需的所有步驟，請參閱 [設定直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="92214-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="92214-114">當您準備好啟用使用者進行直接路由時，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="92214-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="92214-115">在授權或Microsoft 365中Office 365使用者，並指派電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="92214-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="92214-116">確保使用者位於線上商務用 Skype中。</span><span class="sxs-lookup"><span data-stu-id="92214-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="92214-117">設定電話號碼，並啟用企業語音和語音信箱。</span><span class="sxs-lookup"><span data-stu-id="92214-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="92214-118">將Teams模式指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="92214-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="92214-119">建立使用者並指派授權</span><span class="sxs-lookup"><span data-stu-id="92214-119">Create a user and assign the license</span></span> 

<span data-ttu-id="92214-120">在 Microsoft 365 或 Office 365 中建立Office 365。</span><span class="sxs-lookup"><span data-stu-id="92214-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="92214-121">不過，Microsoft 建議貴組織選擇一個選項以避免路由問題：</span><span class="sxs-lookup"><span data-stu-id="92214-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="92214-122">在內部部署 Active Directory 中建立使用者，並同步該使用者至雲端。</span><span class="sxs-lookup"><span data-stu-id="92214-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="92214-123">請參閱[整合您的內部部署目錄與 Azure Active Directory。](/azure/active-directory/connect/active-directory-aadconnect)</span><span class="sxs-lookup"><span data-stu-id="92214-123">See [Integrate your on-premises directories with Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="92214-124">直接在 Microsoft 365 系統管理中心 中建立Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="92214-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="92214-125">請參閱個別或大量新增使用者至 Microsoft 365[或 Office 365 - 系統管理協助](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。</span><span class="sxs-lookup"><span data-stu-id="92214-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="92214-126">如果您的 商務用 Skype Online 部署與 商務用 Skype 2015 或 Lync 2010 或 2013 內部部署並存，唯一支援的選項是在內部部署 Active Directory 中建立使用者，並同步處理使用者至雲端 (選項 1) 。</span><span class="sxs-lookup"><span data-stu-id="92214-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="92214-127">有關授權需求的資訊，請參閱規劃直接路由 [中的](direct-routing-plan.md#licensing-and-other-requirements) 授權 [和其他需求](direct-routing-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="92214-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a><span data-ttu-id="92214-128">確保使用者位於線上，且電話號碼不會從內部部署 (同步處理，商務用 Skype Server 企業語音 啟用使用者移Teams直接路由) </span><span class="sxs-lookup"><span data-stu-id="92214-128">Ensure that the user is homed online and phone number is not being synced from on-premises (applicable for Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing)</span></span>

<span data-ttu-id="92214-129">直接路由需要使用者連線。</span><span class="sxs-lookup"><span data-stu-id="92214-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="92214-130">您可以查看 RegistrarPool 參數，此參數需要在 infra.lync.com 中。</span><span class="sxs-lookup"><span data-stu-id="92214-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="92214-131">OnPremLineUriManuallySet 參數也應該設為 True。</span><span class="sxs-lookup"><span data-stu-id="92214-131">OnPremLineUriManuallySet parameter should also to be set to True.</span></span> <span data-ttu-id="92214-132">這是使用線上 PowerShell 來配置電話號碼，並啟用企業語音和語音信箱商務用 Skype達到此目的。</span><span class="sxs-lookup"><span data-stu-id="92214-132">This is achieved by configuring the phone number and enable enterprise voice and voicemail using Skype for Business Online PowerShell.</span></span>

1. <span data-ttu-id="92214-133">連線線上商務用 Skype PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="92214-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="92214-134">發出命令：</span><span class="sxs-lookup"><span data-stu-id="92214-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="92214-135">萬一 OnPremLineUriManuallySet 設定為 False，且 LineUri 會填上 <E.164 電話號碼>，請在使用 商務用 Skype Online PowerShell 設定電話號碼之前，使用內部部署 商務用 Skype 管理命令程式清理參數。</span><span class="sxs-lookup"><span data-stu-id="92214-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, please clean the parameters using on-premises Skype for Business Management Shell, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="92214-136">從 商務用 Skype管理命令命令：</span><span class="sxs-lookup"><span data-stu-id="92214-136">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   <span data-ttu-id="92214-137">將變更同步到 Office 365 預期輸出 `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` 為：</span><span class="sxs-lookup"><span data-stu-id="92214-137">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="92214-138">設定電話號碼並啟用企業語音信箱</span><span class="sxs-lookup"><span data-stu-id="92214-138">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="92214-139">建立使用者並指派授權之後，下一個步驟就是設定使用者的電話號碼和語音信箱。</span><span class="sxs-lookup"><span data-stu-id="92214-139">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="92214-140">若要新增電話號碼並啟用語音信箱：</span><span class="sxs-lookup"><span data-stu-id="92214-140">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="92214-141">連線線上商務用 Skype PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="92214-141">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="92214-142">發出命令：</span><span class="sxs-lookup"><span data-stu-id="92214-142">Issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    <span data-ttu-id="92214-143">例如，若要新增使用者「Spencer Low」的電話號碼，請輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="92214-143">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    <span data-ttu-id="92214-144">如果使用者 "Spencer Low" 和 "Stacy Quinn" 共用相同的底數與唯一副檔名，請輸入下列</span><span class="sxs-lookup"><span data-stu-id="92214-144">If the users "Spencer Low" and "Stacy Quinn" share the same base number with unique extensions, enter the following</span></span>
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1001" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1002" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="92214-145">建議但不需要，使用的電話號碼會以完整的 E.164 電話號碼與國碼進行配置。</span><span class="sxs-lookup"><span data-stu-id="92214-145">It's recommended, but not required, that the phone number used is configured as a full E.164 phone number with country code.</span></span> <span data-ttu-id="92214-146">支援使用擴充功能來設定電話號碼，當針對基本號碼進行查詢時，會用來查詢使用者。</span><span class="sxs-lookup"><span data-stu-id="92214-146">It is supported to configure phone numbers with extensions which will be used to lookup users when the lookup against the base number returns more than one result.</span></span> <span data-ttu-id="92214-147">這可讓公司以相同的基本號碼和唯一分機來設定電話號碼。</span><span class="sxs-lookup"><span data-stu-id="92214-147">This allows companies to configure phone numbers with the same base number and unique extensions.</span></span> <span data-ttu-id="92214-148">若要成功進行尋找，邀請必須包含具有分機的完整號碼，如下所示：</span><span class="sxs-lookup"><span data-stu-id="92214-148">For lookup to be successful, the invite must include the full number with extension as follows:</span></span>
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > <span data-ttu-id="92214-149">如果使用者的電話號碼是內部部署管理，請使用內部部署管理命令商務用 Skype或控制台來設定使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="92214-149">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="92214-150">直接將通話傳送至語音信箱</span><span class="sxs-lookup"><span data-stu-id="92214-150">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="92214-151">直接路由可讓您結束通話給使用者，並直接傳送至使用者的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="92214-151">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="92214-152">如果您想要將通話直接傳送至語音信箱，請將不透明=app：語音信箱附加至要求 URI 標頭。</span><span class="sxs-lookup"><span data-stu-id="92214-152">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="92214-153">例如，"sip：user@yourdomain.com;不透明=app：語音信箱」。</span><span class="sxs-lookup"><span data-stu-id="92214-153">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="92214-154">在這種情況下，Teams不會收到通話通知，通話會直接連接到使用者的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="92214-154">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="92214-155">指派Teams模式給使用者，以確保通話能夠Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="92214-155">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="92214-156">直接路由要求使用者進入僅Teams模式，以確保來電會撥入Teams用戶端。</span><span class="sxs-lookup"><span data-stu-id="92214-156">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="92214-157">若要將使用者置於Teams模式，請指派他們 TeamsUpgradePolicy 的「UpgradeToTeams」實例。</span><span class="sxs-lookup"><span data-stu-id="92214-157">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="92214-158">詳細資訊，請參閱 [IT 系統管理員的升級策略](upgrade-to-teams-on-prem-implement.md)。</span><span class="sxs-lookup"><span data-stu-id="92214-158">For more information, see [Upgrade strategies for IT administrators](upgrade-to-teams-on-prem-implement.md).</span></span> <span data-ttu-id="92214-159">如果貴組織使用 商務用 Skype Server 或 商務用 Skype Online，請參閱下列文章，以瞭解 Skype 與 Teams 之間的互通性：移移和與 商務用 Skype 的[互通性](migration-interop-guidance-for-teams-with-skype.md)。</span><span class="sxs-lookup"><span data-stu-id="92214-159">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="92214-160">另請參閱</span><span class="sxs-lookup"><span data-stu-id="92214-160">See also</span></span>

[<span data-ttu-id="92214-161">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="92214-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="92214-162">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="92214-162">Configure Direct Routing</span></span>](direct-routing-configure.md)

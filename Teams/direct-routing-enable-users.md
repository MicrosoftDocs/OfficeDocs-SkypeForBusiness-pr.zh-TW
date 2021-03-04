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
description: 瞭解如何允許使用者使用 Microsoft Phone System 直接路由。
ms.openlocfilehash: 972bd8d5e01a050a67978560b8de272439fda40d
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421308"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="dc9d7-103">允許使用者進行直接路由、語音和語音信箱</span><span class="sxs-lookup"><span data-stu-id="dc9d7-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="dc9d7-104">本文說明如何讓使用者使用電話系統直接路由。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="dc9d7-105">這是進行直接路由的下列步驟之步驟 2：</span><span class="sxs-lookup"><span data-stu-id="dc9d7-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="dc9d7-106">步驟 1。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-106">Step 1.</span></span> [<span data-ttu-id="dc9d7-107">使用 Microsoft Phone System 連接 SBC 並驗證連接</span><span class="sxs-lookup"><span data-stu-id="dc9d7-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="dc9d7-108">**步驟 2。啟用使用者進行直接路由、語音和語音**   信箱 (本文) </span><span class="sxs-lookup"><span data-stu-id="dc9d7-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="dc9d7-109">步驟 3。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-109">Step 3.</span></span> [<span data-ttu-id="dc9d7-110">設定語音路由</span><span class="sxs-lookup"><span data-stu-id="dc9d7-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="dc9d7-111">步驟 4。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-111">Step 4.</span></span> [<span data-ttu-id="dc9d7-112">將數位轉換成替代格式</span><span class="sxs-lookup"><span data-stu-id="dc9d7-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="dc9d7-113">有關設定直接路由所需之所有步驟的資訊，請參閱設定 [直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="dc9d7-114">當您準備好啟用使用者進行直接路由時，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="dc9d7-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="dc9d7-115">在 Microsoft 365 或 Office 365 中建立使用者，並指派電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="dc9d7-116">確保使用者位於商務用 Skype Online 中。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="dc9d7-117">設定電話號碼，並啟用企業語音和語音信箱。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="dc9d7-118">指派 Teams 模式給使用者。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="dc9d7-119">建立使用者並指派授權</span><span class="sxs-lookup"><span data-stu-id="dc9d7-119">Create a user and assign the license</span></span> 

<span data-ttu-id="dc9d7-120">在 Microsoft 365 或 Office 365 中建立新使用者有兩個選項。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="dc9d7-121">不過，Microsoft 建議貴組織選擇一個選項以避免路由問題：</span><span class="sxs-lookup"><span data-stu-id="dc9d7-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="dc9d7-122">在內部部署 Active Directory 中建立使用者，並同步使用者至雲端。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="dc9d7-123">請參閱[整合內部部署目錄與 Azure Active Directory。](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)</span><span class="sxs-lookup"><span data-stu-id="dc9d7-123">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="dc9d7-124">直接在 Microsoft 365 系統管理中心建立使用者。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="dc9d7-125">請參閱個別或大量新增使用者至 [Microsoft 365 或 Office 365 - 系統管理協助](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="dc9d7-126">如果您的商務用 Skype Online 部署與商務用 Skype 2015 或 Lync 2010 或 2013 內部部署並存，則唯一支援的選項是在內部部署 Active Directory 中建立使用者，並同步處理使用者至雲端 (選項 1) 。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="dc9d7-127">有關授權需求的資訊，請參閱方案直接路由 [中的](direct-routing-plan.md#licensing-and-other-requirements) 授權 [和其他需求](direct-routing-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a><span data-ttu-id="dc9d7-128">確保使用者位於線上，且電話號碼未從內部部署 (適用于啟用商務用 Skype Server Enterprise Voice 的使用者移移至 Teams 直接路由) </span><span class="sxs-lookup"><span data-stu-id="dc9d7-128">Ensure that the user is homed online and phone number is not being synced from on-premises (applicable for Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing)</span></span>

<span data-ttu-id="dc9d7-129">直接路由需要使用者連線上網。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="dc9d7-130">您可以查看 RegistrarPool 參數來檢查，其值必須位於 infra.lync.com 域中。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="dc9d7-131">OnPremLineUriManuallySet 參數也應該設為 True。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-131">OnPremLineUriManuallySet parameter should also to be set to True.</span></span> <span data-ttu-id="dc9d7-132">這是使用商務用 Skype Online PowerShell 來配置電話號碼，並啟用企業語音和語音信箱的方式。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-132">This is achieved by configuring the phone number and enable enterprise voice and voicemail using Skype for Business Online PowerShell.</span></span>

1. <span data-ttu-id="dc9d7-133">連線商務用 Skype Online PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="dc9d7-134">發出命令：</span><span class="sxs-lookup"><span data-stu-id="dc9d7-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="dc9d7-135">如果 OnPremLineUriManuallySet 設定為 False，且 LineUri 填上 <E.164 電話號碼>，請使用內部部署商務用 Skype 管理命令程式清除參數，然後再使用商務用 Skype Online PowerShell 設定電話號碼。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, please clean the parameters using on-premises Skype for Business Management Shell, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="dc9d7-136">從商務用 Skype 管理命令：</span><span class="sxs-lookup"><span data-stu-id="dc9d7-136">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   <span data-ttu-id="dc9d7-137">將變更同步到 Office 365 之後，預期輸出 `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` 為：</span><span class="sxs-lookup"><span data-stu-id="dc9d7-137">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="dc9d7-138">設定電話號碼並啟用企業語音和語音信箱</span><span class="sxs-lookup"><span data-stu-id="dc9d7-138">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="dc9d7-139">在您建立使用者並指派授權之後，下一個步驟是設定使用者的電話號碼和語音信箱。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-139">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="dc9d7-140">若要新增電話號碼並啟用語音信箱：</span><span class="sxs-lookup"><span data-stu-id="dc9d7-140">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="dc9d7-141">連線商務用 Skype Online PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-141">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="dc9d7-142">發出命令：</span><span class="sxs-lookup"><span data-stu-id="dc9d7-142">Issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    <span data-ttu-id="dc9d7-143">例如，若要新增使用者「Spencer Low」的電話號碼，請輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="dc9d7-143">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    <span data-ttu-id="dc9d7-144">如果使用者 "Spencer Low" 和 "Stacy Quinn" 共用相同的底數與唯一的副檔名，請輸入下列專案</span><span class="sxs-lookup"><span data-stu-id="dc9d7-144">If the users "Spencer Low" and "Stacy Quinn" share the same base number with unique extensions, enter the following</span></span>
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="dc9d7-145">建議但並非必要的是，使用的電話號碼會以完整的 E.164 電話號碼與國碼進行配置。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-145">It's recommended, but not required, that the phone number used is configured as a full E.164 phone number with country code.</span></span> <span data-ttu-id="dc9d7-146">支援設定電話號碼與分機，當底數的查詢會返回多個結果時，會用來查詢使用者。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-146">It is supported to configure phone numbers with extensions which will be used to lookup users when the lookup against the base number returns more than one result.</span></span> <span data-ttu-id="dc9d7-147">這可讓公司設定相同基本號碼和唯一分機的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-147">This allows companies to configure phone numbers with the same base number and unique extensions.</span></span> <span data-ttu-id="dc9d7-148">若要成功進行查找，邀請必須包含完整號碼和擴充功能，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dc9d7-148">For lookup to be successful, the invite must include the full number with extension as follows:</span></span>
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > <span data-ttu-id="dc9d7-149">如果使用者的電話號碼是在內部部署管理，請使用內部部署商務用 Skype 管理命令命令程式或控制台來設定使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-149">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="dc9d7-150">將來電直接傳送至語音信箱</span><span class="sxs-lookup"><span data-stu-id="dc9d7-150">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="dc9d7-151">直接路由可讓您結束通話給使用者，並直接傳送至使用者的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-151">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="dc9d7-152">如果您想要直接將通話傳送至語音信箱，請將不透明=app：語音信箱附加至要求 URI 標頭。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-152">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="dc9d7-153">例如，"sip：user@yourdomain.com;opaque=app：voicemail"。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-153">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="dc9d7-154">在這種情況下，Teams 使用者不會收到通話通知，通話會直接連接到使用者的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-154">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="dc9d7-155">指派 Teams 模式給使用者，以確保通話能夠進入 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dc9d7-155">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="dc9d7-156">直接路由要求使用者進入 Teams 僅模式，以確保來電會進入 Teams 用戶端。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-156">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="dc9d7-157">若要將使用者置於 Teams 模式，請指派 TeamsUpgradePolicy 的「UpgradeToTeams」實例給他們。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-157">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="dc9d7-158">詳細資訊請參閱適用于 [IT 系統管理員的升級策略](upgrade-to-teams-on-prem-implement.md)。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-158">For more information, see [Upgrade strategies for IT administrators](upgrade-to-teams-on-prem-implement.md).</span></span> <span data-ttu-id="dc9d7-159">如果貴組織使用商務用 Skype Server 或商務用 Skype Online，請參閱下列文章，瞭解 Skype 與 Teams 之間的互通性：移移與商務用 [Skype 的互通性](migration-interop-guidance-for-teams-with-skype.md)。</span><span class="sxs-lookup"><span data-stu-id="dc9d7-159">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dc9d7-160">另請參閱</span><span class="sxs-lookup"><span data-stu-id="dc9d7-160">See also</span></span>

[<span data-ttu-id="dc9d7-161">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="dc9d7-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="dc9d7-162">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="dc9d7-162">Configure Direct Routing</span></span>](direct-routing-configure.md)

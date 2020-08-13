---
title: 允許使用者直接傳送
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
description: 瞭解如何啟用使用者 Microsoft Phone 系統 Direct 路由。
ms.openlocfilehash: 5fc3955430e5aa441d3c1099a86011d2b0c760f0
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656144"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="58baa-103">允許使用者使用直接路由、語音及語音信箱</span><span class="sxs-lookup"><span data-stu-id="58baa-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="58baa-104">本文說明如何讓使用者使用電話系統直接路由。</span><span class="sxs-lookup"><span data-stu-id="58baa-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="58baa-105">以下是設定直接路由的步驟2：</span><span class="sxs-lookup"><span data-stu-id="58baa-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="58baa-106">步驟1。</span><span class="sxs-lookup"><span data-stu-id="58baa-106">Step 1.</span></span> [<span data-ttu-id="58baa-107">將 SBC 與 Microsoft Phone 系統連接並驗證連接</span><span class="sxs-lookup"><span data-stu-id="58baa-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="58baa-108">**步驟2。在本文中，讓使用者使用直接路由、語音及語音信箱**    () </span><span class="sxs-lookup"><span data-stu-id="58baa-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**    (This article)</span></span>
- <span data-ttu-id="58baa-109">步驟3。</span><span class="sxs-lookup"><span data-stu-id="58baa-109">Step 3.</span></span> [<span data-ttu-id="58baa-110">設定語音路由</span><span class="sxs-lookup"><span data-stu-id="58baa-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="58baa-111">步驟4。</span><span class="sxs-lookup"><span data-stu-id="58baa-111">Step 4.</span></span> [<span data-ttu-id="58baa-112">將數位轉換成替換格式</span><span class="sxs-lookup"><span data-stu-id="58baa-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="58baa-113">如需設定直接路由所需的所有步驟的詳細資訊，請參閱設定 [直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="58baa-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="58baa-114">當您準備好要讓使用者能夠直接傳送時，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="58baa-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="58baa-115">在 Microsoft 365 或 Office 365 中建立使用者，並指派電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="58baa-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="58baa-116">確定使用者是駐留在商務用 Skype Online 中。</span><span class="sxs-lookup"><span data-stu-id="58baa-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="58baa-117">設定電話號碼，並啟用企業語音及語音信箱。</span><span class="sxs-lookup"><span data-stu-id="58baa-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="58baa-118">將 [團隊專用] 模式指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="58baa-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="58baa-119">建立使用者並指派授權</span><span class="sxs-lookup"><span data-stu-id="58baa-119">Create a user and assign the license</span></span> 

<span data-ttu-id="58baa-120">在 Microsoft 365 或 Office 365 中建立新使用者有兩個選項。</span><span class="sxs-lookup"><span data-stu-id="58baa-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="58baa-121">不過，Microsoft 建議您的組織選擇一個選項來避免路由問題：</span><span class="sxs-lookup"><span data-stu-id="58baa-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="58baa-122">在內部部署的 Active Directory 中建立使用者，並將使用者同步處理到雲端。</span><span class="sxs-lookup"><span data-stu-id="58baa-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="58baa-123">請參閱 [將您的內部部署目錄與 Azure Active Directory 整合](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。</span><span class="sxs-lookup"><span data-stu-id="58baa-123">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="58baa-124">直接在 Microsoft 365 系統管理中心建立使用者。</span><span class="sxs-lookup"><span data-stu-id="58baa-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="58baa-125">請參閱 [個別或大量將使用者新增至 Microsoft 365 或 Office 365-系統管理協助](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。</span><span class="sxs-lookup"><span data-stu-id="58baa-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="58baa-126">如果您的商務用 skype Online 部署 coexists 使用商務用 Skype 2015 或 Lync 2010 或2013內部部署，則唯一支援的選項是在內部部署 Active Directory 中建立使用者，並將使用者同步處理到雲端 (選項 1) 。</span><span class="sxs-lookup"><span data-stu-id="58baa-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="58baa-127">如需授權需求的相關資訊，請參閱[規劃直接路由](direct-routing-plan.md)中的[授權和其他需求](direct-routing-plan.md#licensing-and-other-requirements)。</span><span class="sxs-lookup"><span data-stu-id="58baa-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online"></a><span data-ttu-id="58baa-128">確定使用者已在線上</span><span class="sxs-lookup"><span data-stu-id="58baa-128">Ensure that the user is homed online</span></span> 

<span data-ttu-id="58baa-129">[直接傳送] 要求使用者在線上中駐留。</span><span class="sxs-lookup"><span data-stu-id="58baa-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="58baa-130">您可以查看 RegistrarPool 參數，該參數必須在 infra.lync.com 網域中有值。</span><span class="sxs-lookup"><span data-stu-id="58baa-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="58baa-131">[連線至遠端 PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="58baa-131">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="58baa-132">發出命令：</span><span class="sxs-lookup"><span data-stu-id="58baa-132">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
    ``` 

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="58baa-133">設定電話號碼並啟用企業語音及語音信箱</span><span class="sxs-lookup"><span data-stu-id="58baa-133">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="58baa-134">在您建立使用者並指派授權之後，下一步就是設定使用者的電話號碼和語音信箱。</span><span class="sxs-lookup"><span data-stu-id="58baa-134">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="58baa-135">若要新增電話號碼並啟用語音信箱：</span><span class="sxs-lookup"><span data-stu-id="58baa-135">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="58baa-136">連線到遠端 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="58baa-136">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="58baa-137">輸入命令：</span><span class="sxs-lookup"><span data-stu-id="58baa-137">Enter the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```

    <span data-ttu-id="58baa-138">例如，若要將使用者的電話號碼新增至 [Spencer Low]，請輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="58baa-138">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="58baa-139">所使用的電話號碼必須設定為完整的 E. 164 電話號碼（國家/地區碼）。</span><span class="sxs-lookup"><span data-stu-id="58baa-139">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

      > [!NOTE]
      > <span data-ttu-id="58baa-140">如果使用者的電話號碼是在內部部署管理，請使用內部部署商務用 Skype 管理命令介面或 [控制台] 來設定使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="58baa-140">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="58baa-141">設定直接傳送來電至語音信箱</span><span class="sxs-lookup"><span data-stu-id="58baa-141">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="58baa-142">[直接路由] 可讓您結束通話呼叫並直接傳送給使用者的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="58baa-142">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="58baa-143">如果您想要直接將來電傳送到語音信箱，請將不透明的 = app 附加至 [要求 URI 標頭]。</span><span class="sxs-lookup"><span data-stu-id="58baa-143">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="58baa-144">例如，「sip： user@yourdomain .com; 不透明 = app：語音信箱」。</span><span class="sxs-lookup"><span data-stu-id="58baa-144">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="58baa-145">在這種情況下，小組使用者將不會收到來電通知，該通話會直接連線至使用者的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="58baa-145">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="58baa-146">將 [僅限團隊] 模式指派給使用者，以確保在 Microsoft 團隊中撥打土地</span><span class="sxs-lookup"><span data-stu-id="58baa-146">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="58baa-147">直接路由要求使用者只能在 [僅限團隊] 模式中，以確保來電在團隊用戶端中保持通話。</span><span class="sxs-lookup"><span data-stu-id="58baa-147">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="58baa-148">若要將使用者置於 [僅限團隊] 模式，請將 [UpgradeToTeams] TeamsUpgradePolicy 的實例指派給他們。</span><span class="sxs-lookup"><span data-stu-id="58baa-148">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="58baa-149">如需詳細資訊，請參閱適用 [于 IT 系統管理員的升級指導](upgrade-to-teams-on-prem-overview.md)方針。</span><span class="sxs-lookup"><span data-stu-id="58baa-149">For more information, see [Upgrade guidance for IT administrators](upgrade-to-teams-on-prem-overview.md).</span></span> <span data-ttu-id="58baa-150">如果您的組織是使用商務用 Skype Server 或商務用 Skype Online，請參閱下列文章，瞭解 Skype 與團隊之間的互通性資訊： [與商務用 skype 的遷移與互通性](migration-interop-guidance-for-teams-with-skype.md)。</span><span class="sxs-lookup"><span data-stu-id="58baa-150">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="58baa-151">另請參閱</span><span class="sxs-lookup"><span data-stu-id="58baa-151">See also</span></span>

[<span data-ttu-id="58baa-152">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="58baa-152">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="58baa-153">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="58baa-153">Configure Direct Routing</span></span>](direct-routing-configure.md)

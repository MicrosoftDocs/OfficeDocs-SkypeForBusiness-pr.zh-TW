---
title: 停用來完成遷移至雲端混合式
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 本附錄包含詳細的步驟，停用混合式雲端合併彙算 Teams 和商務用 Skype 的一部分。
ms.openlocfilehash: f78c5a5cb792ecdb39125292c531097219dc58e3
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "37924964"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="482b3-103">停用來完成遷移至雲端混合式</span><span class="sxs-lookup"><span data-stu-id="482b3-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="482b3-104">您已經移動所有使用者從內部部署到雲端後，您可以解除委任商業部署內部部署商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="482b3-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="482b3-105">除了移除任何硬體，是以邏輯方式分隔從 Office 365 的內部部署停用混合式的重要步驟。</span><span class="sxs-lookup"><span data-stu-id="482b3-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="482b3-106">停用混合式所組成的 3 個步驟：</span><span class="sxs-lookup"><span data-stu-id="482b3-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="482b3-107">更新為指向 Office 365 的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="482b3-107">Update DNS records to point to Office 365.</span></span>
2. <span data-ttu-id="482b3-108">停用 Office 365 租用戶中的分割網域。</span><span class="sxs-lookup"><span data-stu-id="482b3-108">Disable split domain in the Office 365 tenant.</span></span>
3. <span data-ttu-id="482b3-109">停用通訊與 Office 365 中內部部署的能力。</span><span class="sxs-lookup"><span data-stu-id="482b3-109">Disable ability in on-prem to communicate with Office 365.</span></span>


<span data-ttu-id="482b3-110">您可以視為一個單位一起完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="482b3-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="482b3-111">詳細資料如下所示。</span><span class="sxs-lookup"><span data-stu-id="482b3-111">Details are provided below.</span></span> <span data-ttu-id="482b3-112">此外，管理的指導方針的電話號碼移轉的使用者，一旦中斷連接內部部署。</span><span class="sxs-lookup"><span data-stu-id="482b3-112">In addition, guidelines for managing phone numbers for migrated users, once the on-premises deployment is disconnected.</span></span>

> [!Note] 
> <span data-ttu-id="482b3-113">在極罕見的情況下，變更 DNS 從指向內部部署 Office 365 為您的組織可能會導致同盟與停止運作直到其他組織更新其同盟設定某些其他組織：</span><span class="sxs-lookup"><span data-stu-id="482b3-113">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="482b3-114">任何使用較舊的直接同盟模式 （也稱為允許協力程式伺服器） 的同盟的組織需要更新為其組織若要移除之 proxy FQDN 其允許的網域項目。</span><span class="sxs-lookup"><span data-stu-id="482b3-114">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="482b3-115">此舊版同盟模型不基礎 DNS SRV 記錄，因此這類設定將會過時，一旦您的組織移至雲端。</span><span class="sxs-lookup"><span data-stu-id="482b3-115">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="482b3-116">任何不需要 sipfed.online.lync 啟用主機服務提供者的同盟的組織。<span>，需要更新其組態，以便讓，com。</span><span class="sxs-lookup"><span data-stu-id="482b3-116">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="482b3-117">如果同盟的組織是純內部部署和永遠不會有任何混合或線上租用戶與同盟，這種情況下才可以。</span><span class="sxs-lookup"><span data-stu-id="482b3-117">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="482b3-118">在這種情況下，與這些組織建立同盟將無法運作之前他們啟用其主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="482b3-118">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="482b3-119">如果您懷疑同盟協力任何的廠商可能會使用直接同盟或與任何有 online 同盟或混合組織中，我們建議您傳送這些有關此通訊，準備完成移轉至雲端。</span><span class="sxs-lookup"><span data-stu-id="482b3-119">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="482b3-120">*更新 DNS 以指向 Office 365。*</span><span class="sxs-lookup"><span data-stu-id="482b3-120">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="482b3-121">在內部部署組織的組織的外部 DNS 必須進行更新，讓 Skype for Business 記錄指向 Office 365 而不是在內部部署。</span><span class="sxs-lookup"><span data-stu-id="482b3-121">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="482b3-122">特別是：</span><span class="sxs-lookup"><span data-stu-id="482b3-122">Specifically:</span></span>

    |<span data-ttu-id="482b3-123">Record type (記錄類型)</span><span class="sxs-lookup"><span data-stu-id="482b3-123">Record type</span></span>|<span data-ttu-id="482b3-124">名稱</span><span class="sxs-lookup"><span data-stu-id="482b3-124">Name</span></span>|<span data-ttu-id="482b3-125">TTL</span><span class="sxs-lookup"><span data-stu-id="482b3-125">TTL</span></span>|<span data-ttu-id="482b3-126">Value (值)</span><span class="sxs-lookup"><span data-stu-id="482b3-126">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="482b3-127">SRV</span><span class="sxs-lookup"><span data-stu-id="482b3-127">SRV</span></span>|<span data-ttu-id="482b3-128">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="482b3-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="482b3-129">3600</span><span class="sxs-lookup"><span data-stu-id="482b3-129">3600</span></span>|<span data-ttu-id="482b3-130">100 1 5061 sipfed.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="482b3-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="482b3-131">SRV</span><span class="sxs-lookup"><span data-stu-id="482b3-131">SRV</span></span>|<span data-ttu-id="482b3-132">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="482b3-132">_sip._tls</span></span>|<span data-ttu-id="482b3-133">3600</span><span class="sxs-lookup"><span data-stu-id="482b3-133">3600</span></span>|<span data-ttu-id="482b3-134">100 1 443 sipdir.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="482b3-134">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="482b3-135">CNAME</span><span class="sxs-lookup"><span data-stu-id="482b3-135">CNAME</span></span>| <span data-ttu-id="482b3-136">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="482b3-136">lyncdiscover</span></span>|   <span data-ttu-id="482b3-137">3600</span><span class="sxs-lookup"><span data-stu-id="482b3-137">3600</span></span>|   <span data-ttu-id="482b3-138">webdir.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="482b3-138">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="482b3-139">CNAME</span><span class="sxs-lookup"><span data-stu-id="482b3-139">CNAME</span></span>| <span data-ttu-id="482b3-140">sip</span><span class="sxs-lookup"><span data-stu-id="482b3-140">sip</span></span>|    <span data-ttu-id="482b3-141">3600</span><span class="sxs-lookup"><span data-stu-id="482b3-141">3600</span></span>|   <span data-ttu-id="482b3-142">sipdir.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="482b3-142">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="482b3-143">CNAME</span><span class="sxs-lookup"><span data-stu-id="482b3-143">CNAME</span></span>| <span data-ttu-id="482b3-144">符合</span><span class="sxs-lookup"><span data-stu-id="482b3-144">meet</span></span>|   <span data-ttu-id="482b3-145">3600</span><span class="sxs-lookup"><span data-stu-id="482b3-145">3600</span></span>|   <span data-ttu-id="482b3-146">webdir.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="482b3-146">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="482b3-147">CNAME</span><span class="sxs-lookup"><span data-stu-id="482b3-147">CNAME</span></span>| <span data-ttu-id="482b3-148">dialin</span><span class="sxs-lookup"><span data-stu-id="482b3-148">dialin</span></span>  |<span data-ttu-id="482b3-149">3600</span><span class="sxs-lookup"><span data-stu-id="482b3-149">3600</span></span>|  <span data-ttu-id="482b3-150">webdir.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="482b3-150">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="482b3-151">*停用 Office 365 租用戶中的共用的 SIP 位址空間。*</span><span class="sxs-lookup"><span data-stu-id="482b3-151">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="482b3-152">下列命令，需要完成從 Skype for Business Online PowerShell 視窗。</span><span class="sxs-lookup"><span data-stu-id="482b3-152">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  <span data-ttu-id="482b3-153">*停用通訊與 Office 365 中內部部署的能力。*</span><span class="sxs-lookup"><span data-stu-id="482b3-153">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="482b3-154">必須從內部部署的 PowerShell] 視窗中執行以下命令。</span><span class="sxs-lookup"><span data-stu-id="482b3-154">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="482b3-155">如果您有先前匯入 Skype for Business Online 工作階段啟動新的 Skype for Business PowerShell 工作階段。</span><span class="sxs-lookup"><span data-stu-id="482b3-155">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session.</span></span>

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

### <a name="managing-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="482b3-156">管理已從內部部署移轉的使用者的電話號碼</span><span class="sxs-lookup"><span data-stu-id="482b3-156">Managing phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="482b3-157">系統管理員可以管理先前從內部部署 Skype for Business Server 至雲端，即使之後移動解除委任內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="482b3-157">Admins can manage users that were previously moved from on-premise Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="482b3-158">有 2 不同的可能性：</span><span class="sxs-lookup"><span data-stu-id="482b3-158">There are 2 different possibilities:</span></span>
1.  <span data-ttu-id="482b3-159">如果使用者有 lineURI 內部部署進行移動之前 (可能因為使用者已啟用 Enterprise voice)，如果您想要變更 lineURI，您必須執行此動作的內部部署 AD，並讓值流程至 AAD。</span><span class="sxs-lookup"><span data-stu-id="482b3-159">If the user had a lineURI on-premise before the move (presumably because the user was enabled for Enterprise Voice), if you want to change the lineURI, you must do this in on-premise AD and let the value flow up to AAD.</span></span> <span data-ttu-id="482b3-160">這不需要內部 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="482b3-160">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="482b3-161">相反地，此屬性，可以編輯 Msrtcsip-line，直接在內部部署 Active Directory 中，使用 Active Directory 使用者及電腦] MMC 嵌入式管理單元中，或透過 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="482b3-161">Rather, this attribute, msRTCSIP-Line can be edited directly in the on-premises Active Directory, using either Active Directory Users and Computers MMC snap-in, or via PowerShell.</span></span> <span data-ttu-id="482b3-162">如果使用 MMC 嵌入式管理單元，請開啟 [屬性] 頁面上的使用者，按一下 [屬性編輯器] 索引標籤並尋找 Msrtcsip-line。</span><span class="sxs-lookup"><span data-stu-id="482b3-162">If using the MMC snap-in, open to properties page of the user, and click Attribute Editor tab and find msRTCSIP-Line.</span></span>

2.  <span data-ttu-id="482b3-163">如果使用者沒有 lineURI 在內部進行移動之前的值，您可以修改 skype 組 get-csuser cmdlet 中使用-onpremLineUri 參數 for Business Online Powershell 模組 LineURI。</span><span class="sxs-lookup"><span data-stu-id="482b3-163">If the user did not have a value for lineURI on-prem before the move, you can modify the LineURI using the -onpremLineUri parameters in the set-csuser cmdlet in the Skype for Business Online Powershell module.</span></span>

## <a name="see-also"></a><span data-ttu-id="482b3-164">另請參閱</span><span class="sxs-lookup"><span data-stu-id="482b3-164">See also</span></span>

[<span data-ttu-id="482b3-165">針對小組與 Skype for Business 的雲端彙總</span><span class="sxs-lookup"><span data-stu-id="482b3-165">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

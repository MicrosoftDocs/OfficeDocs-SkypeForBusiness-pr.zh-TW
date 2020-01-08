---
title: 停用混合式以完成移轉至雲端
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
ms.openlocfilehash: d3420c1bd40bbdeeff25747153210c2600d929f6
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/07/2020
ms.locfileid: "40963071"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="ab3d5-103">停用混合式以完成移轉至雲端</span><span class="sxs-lookup"><span data-stu-id="ab3d5-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="ab3d5-104">將所有使用者從內部部署移至雲端之後，您就可以解除內部部署的商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="ab3d5-105">除了移除任何硬體以外，重要的步驟是透過停用混合式的方式，在邏輯上將該內部部署與 Office 365 分開。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="ab3d5-106">停用混合式所組成的 3 個步驟：</span><span class="sxs-lookup"><span data-stu-id="ab3d5-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="ab3d5-107">更新 DNS 記錄，使它指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-107">Update DNS records to point to Office 365.</span></span>

2. <span data-ttu-id="ab3d5-108">在 Office 365 租用戶中停用分割網域。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-108">Disable split domain in the Office 365 tenant.</span></span>

3. <span data-ttu-id="ab3d5-109">停用在內部部署與 Office 365 通訊的功能。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-109">Disable the ability in on-premises to communicate with Office 365.</span></span>

<span data-ttu-id="ab3d5-110">您可以視為一個單位一起完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="ab3d5-111">詳細資料如下所示。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-111">Details are provided below.</span></span> <span data-ttu-id="ab3d5-112">此外，一旦中斷連接內部部署管理已移轉使用者的電話號碼提供指導方針。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-112">In addition, guidelines are provided for managing phone numbers for migrated users once the on-premises deployment is disconnected.</span></span>

> [!Note] 
> <span data-ttu-id="ab3d5-113">在極罕見的情況下，變更 DNS 從指向內部部署 Office 365 為您的組織可能會導致同盟與停止運作直到其他組織更新其同盟設定某些其他組織：</span><span class="sxs-lookup"><span data-stu-id="ab3d5-113">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="ab3d5-114">任何使用較舊的直接同盟模式 （也稱為允許協力程式伺服器） 的同盟的組織需要更新為其組織若要移除之 proxy FQDN 其允許的網域項目。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-114">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="ab3d5-115">此舊版同盟模型不基礎 DNS SRV 記錄，因此這類設定將會過時，一旦您的組織移至雲端。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-115">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="ab3d5-116">任何不需要 sipfed.online.lync 啟用主機服務提供者的同盟的組織。<span>，需要更新其組態，以便讓，com。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-116">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="ab3d5-117">如果同盟的組織是純內部部署和永遠不會有任何混合或線上租用戶與同盟，這種情況下才可以。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-117">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="ab3d5-118">在這種情況下，與這些組織建立同盟將無法運作之前他們啟用其主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-118">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="ab3d5-119">如果您懷疑同盟協力任何的廠商可能會使用直接同盟或與任何有 online 同盟或混合組織中，我們建議您傳送這些有關此通訊，準備完成移轉至雲端。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-119">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="ab3d5-120">*更新 DNS 以指向 Office 365。*</span><span class="sxs-lookup"><span data-stu-id="ab3d5-120">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="ab3d5-121">在內部部署組織的組織的外部 DNS 必須進行更新，讓 Skype for Business 記錄指向 Office 365 而不是在內部部署。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-121">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="ab3d5-122">特別是：</span><span class="sxs-lookup"><span data-stu-id="ab3d5-122">Specifically:</span></span>

    |<span data-ttu-id="ab3d5-123">Record type (記錄類型)</span><span class="sxs-lookup"><span data-stu-id="ab3d5-123">Record type</span></span>|<span data-ttu-id="ab3d5-124">名稱</span><span class="sxs-lookup"><span data-stu-id="ab3d5-124">Name</span></span>|<span data-ttu-id="ab3d5-125">TTL</span><span class="sxs-lookup"><span data-stu-id="ab3d5-125">TTL</span></span>|<span data-ttu-id="ab3d5-126">Value (值)</span><span class="sxs-lookup"><span data-stu-id="ab3d5-126">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="ab3d5-127">SRV</span><span class="sxs-lookup"><span data-stu-id="ab3d5-127">SRV</span></span>|<span data-ttu-id="ab3d5-128">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="ab3d5-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="ab3d5-129">3600</span><span class="sxs-lookup"><span data-stu-id="ab3d5-129">3600</span></span>|<span data-ttu-id="ab3d5-130">100 1 5061 sipfed.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="ab3d5-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ab3d5-131">SRV</span><span class="sxs-lookup"><span data-stu-id="ab3d5-131">SRV</span></span>|<span data-ttu-id="ab3d5-132">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="ab3d5-132">_sip._tls</span></span>|<span data-ttu-id="ab3d5-133">3600</span><span class="sxs-lookup"><span data-stu-id="ab3d5-133">3600</span></span>|<span data-ttu-id="ab3d5-134">100 1 443 sipdir.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="ab3d5-134">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ab3d5-135">CNAME</span><span class="sxs-lookup"><span data-stu-id="ab3d5-135">CNAME</span></span>| <span data-ttu-id="ab3d5-136">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ab3d5-136">lyncdiscover</span></span>|   <span data-ttu-id="ab3d5-137">3600</span><span class="sxs-lookup"><span data-stu-id="ab3d5-137">3600</span></span>|   <span data-ttu-id="ab3d5-138">webdir.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="ab3d5-138">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ab3d5-139">CNAME</span><span class="sxs-lookup"><span data-stu-id="ab3d5-139">CNAME</span></span>| <span data-ttu-id="ab3d5-140">sip</span><span class="sxs-lookup"><span data-stu-id="ab3d5-140">sip</span></span>|    <span data-ttu-id="ab3d5-141">3600</span><span class="sxs-lookup"><span data-stu-id="ab3d5-141">3600</span></span>|   <span data-ttu-id="ab3d5-142">sipdir.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="ab3d5-142">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ab3d5-143">CNAME</span><span class="sxs-lookup"><span data-stu-id="ab3d5-143">CNAME</span></span>| <span data-ttu-id="ab3d5-144">符合</span><span class="sxs-lookup"><span data-stu-id="ab3d5-144">meet</span></span>|   <span data-ttu-id="ab3d5-145">3600</span><span class="sxs-lookup"><span data-stu-id="ab3d5-145">3600</span></span>|   <span data-ttu-id="ab3d5-146">webdir.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="ab3d5-146">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ab3d5-147">CNAME</span><span class="sxs-lookup"><span data-stu-id="ab3d5-147">CNAME</span></span>| <span data-ttu-id="ab3d5-148">dialin</span><span class="sxs-lookup"><span data-stu-id="ab3d5-148">dialin</span></span>  |<span data-ttu-id="ab3d5-149">3600</span><span class="sxs-lookup"><span data-stu-id="ab3d5-149">3600</span></span>|  <span data-ttu-id="ab3d5-150">webdir.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="ab3d5-150">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="ab3d5-151">*停用 Office 365 租用戶中的共用的 SIP 位址空間。*</span><span class="sxs-lookup"><span data-stu-id="ab3d5-151">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="ab3d5-152">下列命令，需要完成從 Skype for Business Online PowerShell 視窗。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-152">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  <span data-ttu-id="ab3d5-153">*停用通訊與 Office 365 中內部部署的能力。*</span><span class="sxs-lookup"><span data-stu-id="ab3d5-153">*Disable ability in on-premises to communicate with Office 365.*</span></span>  
<span data-ttu-id="ab3d5-154">必須從內部部署的 PowerShell] 視窗中執行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ab3d5-154">The command below needs to be done from an on-premises PowerShell window:</span></span>
```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```

### <a name="manage-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="ab3d5-155">管理已從內部部署移轉的使用者的電話號碼</span><span class="sxs-lookup"><span data-stu-id="ab3d5-155">Manage phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="ab3d5-156">系統管理員可以管理先前從內部部署 Skype for Business Server 至雲端，即使之後移動解除委任內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-156">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="ab3d5-157">有兩種不同的可能性：</span><span class="sxs-lookup"><span data-stu-id="ab3d5-157">There are two different possibilities:</span></span>

- <span data-ttu-id="ab3d5-158">使用者沒有 LineURI 在內部進行移動之前的值。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-158">The user did not have a value for LineURI on-premises before the move.</span></span> 

  <span data-ttu-id="ab3d5-159">在此情況下，您可以修改 skype [Set-csuser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)中使用-onpremLineUri 參數 for Business Online PowerShell 模組 LineURI。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-159">In this case, you can modify the LineURI using the -onpremLineUri parameters in the [Set-CsUser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

- <span data-ttu-id="ab3d5-160">具有 LineURI 在內部進行移動之前的使用者 (可能因為使用者已啟用 Enterprise voice)。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-160">The user had a LineURI on-premises before the move (presumably because the user was enabled for Enterprise Voice).</span></span> 

  <span data-ttu-id="ab3d5-161">如果您想要變更 LineURI，您必須執行此動作的內部部署 Active Directory 中，並讓值流程到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-161">If you want to change the LineURI, you must do this in the on-premises Active Directory and let the value flow up to Azure AD.</span></span> <span data-ttu-id="ab3d5-162">這不需要內部 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-162">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="ab3d5-163">相反地，這個屬性，Msrtcsip-line，可直接在內部部署 Active Directory 中，使用 [Active Directory 使用者及電腦] MMC 嵌入式管理單元中，或藉由使用 PowerShell 編輯。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-163">Rather, this attribute, msRTCSIP-Line, can be edited directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in, or by using PowerShell.</span></span> <span data-ttu-id="ab3d5-164">如果您使用 MMC 嵌入式管理單元，開啟至使用者的 [屬性] 頁面上，按一下 [屬性編輯器] 索引標籤，並尋找 Msrtcsip-line。</span><span class="sxs-lookup"><span data-stu-id="ab3d5-164">If you are using the MMC snap-in, open to the properties page of the user, click Attribute Editor tab, and find msRTCSIP-Line.</span></span>

  ![Active Directory 使用者及電腦工具](../media/disable-hybrid-1.png)

## <a name="see-also"></a><span data-ttu-id="ab3d5-166">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ab3d5-166">See also</span></span>

[<span data-ttu-id="ab3d5-167">針對小組與 Skype for Business 的雲端彙總</span><span class="sxs-lookup"><span data-stu-id="ab3d5-167">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

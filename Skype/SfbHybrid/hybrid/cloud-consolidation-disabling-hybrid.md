---
title: 停用混合式完成到雲端的遷移
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
description: 此附錄包含停用混合式的詳細步驟, 做為小組和商務用 Skype 的雲端整合的一部分。
ms.openlocfilehash: 805010aa16ca8159b5e274847ca7ca2b296f214d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185503"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="8512f-103">停用混合式完成到雲端的遷移</span><span class="sxs-lookup"><span data-stu-id="8512f-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="8512f-104">將所有使用者從內部部署移至雲端之後, 您就可以停止使用內部部署商務用 Skype 部署。</span><span class="sxs-lookup"><span data-stu-id="8512f-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="8512f-105">除了移除任何硬體之外, 重要的步驟是透過停用混合式, 以邏輯方式將該內部部署與 Office 365 分開。</span><span class="sxs-lookup"><span data-stu-id="8512f-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="8512f-106">停用混合式包括3個步驟:</span><span class="sxs-lookup"><span data-stu-id="8512f-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="8512f-107">更新 DNS 記錄以指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="8512f-107">Update DNS records to point to Office 365.</span></span>
2. <span data-ttu-id="8512f-108">停用 Office 365 租使用者中的分割網域。</span><span class="sxs-lookup"><span data-stu-id="8512f-108">Disable split domain in the Office 365 tenant.</span></span>
3. <span data-ttu-id="8512f-109">停用內部部署中的功能, 以與 Office 365 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="8512f-109">Disable ability in on-prem to communicate with Office 365.</span></span>


<span data-ttu-id="8512f-110">這些步驟應一起做為一個單元。</span><span class="sxs-lookup"><span data-stu-id="8512f-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="8512f-111">以下提供詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8512f-111">Details are provided below.</span></span>

> [!Note] 
> <span data-ttu-id="8512f-112">在少數情況下, 將 DNS 從指向您組織的 Office 365 的內部部署變更為其他組織, 可能會造成與其他組織的同盟停止運作, 直到其他組織更新其同盟設定為止:</span><span class="sxs-lookup"><span data-stu-id="8512f-112">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="8512f-113">任何使用舊版直接聯盟模型 (又稱為 [允許的夥伴伺服器]) 的同盟組織, 都必須更新其組織的允許網域專案, 才能移除 proxy FQDN。</span><span class="sxs-lookup"><span data-stu-id="8512f-113">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="8512f-114">此舊版同盟模型不是以 DNS SRV 記錄為基礎, 因此當您的組織移到雲端之後, 這類設定就會過期。</span><span class="sxs-lookup"><span data-stu-id="8512f-114">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="8512f-115">沒有已啟用 sipfed 的主機服務提供者的任何聯盟組織。 lync。<span>com 將需要更新其設定, 才能啟用。</span><span class="sxs-lookup"><span data-stu-id="8512f-115">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="8512f-116">只有在同盟組織純粹在內部部署且從未與任何混合式或線上租使用者進行同盟時, 才能使用這種情況。</span><span class="sxs-lookup"><span data-stu-id="8512f-116">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="8512f-117">在這種情況下, 與這些組織的同盟在啟用其主機提供者之前將無法運作。</span><span class="sxs-lookup"><span data-stu-id="8512f-117">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="8512f-118">如果您懷疑任何聯盟夥伴都可能使用直接聯盟, 或是與任何線上或混合式組織共同作業, 我們建議您在準備完成您的雲端遷移時, 傳送與此相關的通訊。</span><span class="sxs-lookup"><span data-stu-id="8512f-118">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="8512f-119">*更新 DNS 以指向 Office 365。*</span><span class="sxs-lookup"><span data-stu-id="8512f-119">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="8512f-120">組織內部部署組織的外部 DNS 必須更新, 才能讓商務用 Skype 記錄指向 Office 365, 而不是內部部署的部署。</span><span class="sxs-lookup"><span data-stu-id="8512f-120">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="8512f-121">說</span><span class="sxs-lookup"><span data-stu-id="8512f-121">Specifically:</span></span>

    |<span data-ttu-id="8512f-122">記錄類型</span><span class="sxs-lookup"><span data-stu-id="8512f-122">Record type</span></span>|<span data-ttu-id="8512f-123">名稱</span><span class="sxs-lookup"><span data-stu-id="8512f-123">Name</span></span>|<span data-ttu-id="8512f-124">TTL</span><span class="sxs-lookup"><span data-stu-id="8512f-124">TTL</span></span>|<span data-ttu-id="8512f-125">值</span><span class="sxs-lookup"><span data-stu-id="8512f-125">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="8512f-126">DNS-SRV</span><span class="sxs-lookup"><span data-stu-id="8512f-126">SRV</span></span>|<span data-ttu-id="8512f-127">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="8512f-127">_sipfederationtls._tcp</span></span>|<span data-ttu-id="8512f-128">3600</span><span class="sxs-lookup"><span data-stu-id="8512f-128">3600</span></span>|<span data-ttu-id="8512f-129">100 1 5061 sipfed (線上) lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="8512f-129">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="8512f-130">DNS-SRV</span><span class="sxs-lookup"><span data-stu-id="8512f-130">SRV</span></span>|<span data-ttu-id="8512f-131">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="8512f-131">_sip._tls</span></span>|<span data-ttu-id="8512f-132">3600</span><span class="sxs-lookup"><span data-stu-id="8512f-132">3600</span></span>|<span data-ttu-id="8512f-133">100 1 443 sipdir (線上) lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="8512f-133">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="8512f-134">CNAME</span><span class="sxs-lookup"><span data-stu-id="8512f-134">CNAME</span></span>| <span data-ttu-id="8512f-135">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8512f-135">lyncdiscover</span></span>|   <span data-ttu-id="8512f-136">3600</span><span class="sxs-lookup"><span data-stu-id="8512f-136">3600</span></span>|   <span data-ttu-id="8512f-137">webdir 為 admin. lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="8512f-137">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="8512f-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="8512f-138">CNAME</span></span>| <span data-ttu-id="8512f-139">呼吸</span><span class="sxs-lookup"><span data-stu-id="8512f-139">sip</span></span>|    <span data-ttu-id="8512f-140">3600</span><span class="sxs-lookup"><span data-stu-id="8512f-140">3600</span></span>|   <span data-ttu-id="8512f-141">sipdir. lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="8512f-141">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="8512f-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="8512f-142">CNAME</span></span>| <span data-ttu-id="8512f-143">符合</span><span class="sxs-lookup"><span data-stu-id="8512f-143">meet</span></span>|   <span data-ttu-id="8512f-144">3600</span><span class="sxs-lookup"><span data-stu-id="8512f-144">3600</span></span>|   <span data-ttu-id="8512f-145">webdir 為 admin. lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="8512f-145">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="8512f-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="8512f-146">CNAME</span></span>| <span data-ttu-id="8512f-147">撥</span><span class="sxs-lookup"><span data-stu-id="8512f-147">dialin</span></span>  |<span data-ttu-id="8512f-148">3600</span><span class="sxs-lookup"><span data-stu-id="8512f-148">3600</span></span>|  <span data-ttu-id="8512f-149">webdir 為 admin. lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="8512f-149">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="8512f-150">*停用 Office 365 租使用者共用的 SIP 位址空間。*</span><span class="sxs-lookup"><span data-stu-id="8512f-150">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="8512f-151">下列命令必須從商務用 Skype Online PowerShell 視窗中完成。</span><span class="sxs-lookup"><span data-stu-id="8512f-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  <span data-ttu-id="8512f-152">*停用內部部署中的功能, 以與 Office 365 進行通訊。*</span><span class="sxs-lookup"><span data-stu-id="8512f-152">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="8512f-153">下列命令必須從內部部署的 PowerShell 視窗完成。</span><span class="sxs-lookup"><span data-stu-id="8512f-153">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="8512f-154">如果您先前已匯入商務用 Skype Online 會話, 請開始新的商務用 Skype PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="8512f-154">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session.</span></span>

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a><span data-ttu-id="8512f-155">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8512f-155">See also</span></span>

[<span data-ttu-id="8512f-156">團隊與商務用 Skype 的雲端整合</span><span class="sxs-lookup"><span data-stu-id="8512f-156">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
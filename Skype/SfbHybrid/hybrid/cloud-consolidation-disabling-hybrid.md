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
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 本附錄包含針對團隊和商務用 Skype 進行雲合併時，停用混合的詳細步驟。
ms.openlocfilehash: 039e8a30495567fe818fe4d60b863f37cf94e049
ms.sourcegitcommit: 0835f4335ebc8ca53b8348e0b1b906828eb4e13e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2020
ms.locfileid: "43918732"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="5f994-103">停用混合式以完成移轉至雲端</span><span class="sxs-lookup"><span data-stu-id="5f994-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="5f994-104">將所有使用者從內部部署移至雲端之後，您就可以解除內部部署的商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="5f994-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="5f994-105">除了移除任何硬體以外，重要的步驟是透過停用混合式的方式，在邏輯上將該內部部署與 Office 365 分開。</span><span class="sxs-lookup"><span data-stu-id="5f994-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="5f994-106">停用混合式包含三個步驟：</span><span class="sxs-lookup"><span data-stu-id="5f994-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="5f994-107">更新 DNS 記錄，使它指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="5f994-107">Update DNS records to point to Office 365.</span></span>

2. <span data-ttu-id="5f994-108">停用 Office 365 組織中的分割網域。</span><span class="sxs-lookup"><span data-stu-id="5f994-108">Disable split domain in the Office 365 organization.</span></span>

3. <span data-ttu-id="5f994-109">停用內部部署中與 Office 365 通訊的功能。</span><span class="sxs-lookup"><span data-stu-id="5f994-109">Disable the ability in on-premises to communicate with Office 365.</span></span>

<span data-ttu-id="5f994-110">這些步驟應該一起做為一個單位。</span><span class="sxs-lookup"><span data-stu-id="5f994-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="5f994-111">以下提供詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5f994-111">Details are provided below.</span></span> <span data-ttu-id="5f994-112">此外，在中斷內部部署的部署後，也會提供指導方針來管理遷移使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="5f994-112">In addition, guidelines are provided for managing phone numbers for migrated users once the on-premises deployment is disconnected.</span></span>

> [!Note] 
> <span data-ttu-id="5f994-113">在極少的情況下，將組織的內部部署至 Office 365 的 DNS 變更為您的組織可能會造成其他一些組織的同盟停止運作，直到其他組織更新其同盟設定為止：</span><span class="sxs-lookup"><span data-stu-id="5f994-113">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="5f994-114">任何使用舊版直接同盟模型（也稱為「允許夥伴伺服器」）的同盟組織，都必須更新其組織的允許網域專案，以移除 proxy FQDN。</span><span class="sxs-lookup"><span data-stu-id="5f994-114">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="5f994-115">這種舊版同盟模型不是以 DNS SRV 記錄為基礎，因此當您的組織移至雲端時，此設定將會到期。</span><span class="sxs-lookup"><span data-stu-id="5f994-115">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="5f994-116">任何沒有啟用 sipfed 之主機服務提供者的同盟組織。<span>com 必須更新其設定，才能啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="5f994-116">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="5f994-117">只有在同盟組織完全存在於內部部署，且決不會與任何混合式或線上租使用者同盟的情況下，才可能出現這種情況。</span><span class="sxs-lookup"><span data-stu-id="5f994-117">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="5f994-118">在此情況下，與這些組織的同盟必須啟用其主機服務提供者後，才能運作。</span><span class="sxs-lookup"><span data-stu-id="5f994-118">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="5f994-119">如果您懷疑任何同盟協力廠商可能使用的是直接同盟或尚未與任何線上或混合組織同盟，我們建議您在準備完成對雲端的遷移時，向他們傳送此資訊的通訊。</span><span class="sxs-lookup"><span data-stu-id="5f994-119">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="5f994-120">*將 DNS 更新為指向 Office 365。*</span><span class="sxs-lookup"><span data-stu-id="5f994-120">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="5f994-121">組織的外部 DNS 必須更新內部部署組織，以便商務用 Skype 記錄指向 Office 365，而不是內部部署。</span><span class="sxs-lookup"><span data-stu-id="5f994-121">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="5f994-122">特別是：</span><span class="sxs-lookup"><span data-stu-id="5f994-122">Specifically:</span></span>

    |<span data-ttu-id="5f994-123">Record type (記錄類型)</span><span class="sxs-lookup"><span data-stu-id="5f994-123">Record type</span></span>|<span data-ttu-id="5f994-124">名稱</span><span class="sxs-lookup"><span data-stu-id="5f994-124">Name</span></span>|<span data-ttu-id="5f994-125">TTL</span><span class="sxs-lookup"><span data-stu-id="5f994-125">TTL</span></span>|<span data-ttu-id="5f994-126">Value (值)</span><span class="sxs-lookup"><span data-stu-id="5f994-126">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="5f994-127">SRV</span><span class="sxs-lookup"><span data-stu-id="5f994-127">SRV</span></span>|<span data-ttu-id="5f994-128">_sipfederationtls。 _tcp</span><span class="sxs-lookup"><span data-stu-id="5f994-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="5f994-129">3600</span><span class="sxs-lookup"><span data-stu-id="5f994-129">3600</span></span>|<span data-ttu-id="5f994-130">100 1 5061 sipfed （lync）。<span>com</span><span class="sxs-lookup"><span data-stu-id="5f994-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="5f994-131">SRV</span><span class="sxs-lookup"><span data-stu-id="5f994-131">SRV</span></span>|<span data-ttu-id="5f994-132">_sip。 _tls</span><span class="sxs-lookup"><span data-stu-id="5f994-132">_sip._tls</span></span>|<span data-ttu-id="5f994-133">3600</span><span class="sxs-lookup"><span data-stu-id="5f994-133">3600</span></span>|<span data-ttu-id="5f994-134">100 1 443 sipdir （lync）。<span>com</span><span class="sxs-lookup"><span data-stu-id="5f994-134">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="5f994-135">CNAME</span><span class="sxs-lookup"><span data-stu-id="5f994-135">CNAME</span></span>| <span data-ttu-id="5f994-136">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5f994-136">lyncdiscover</span></span>|   <span data-ttu-id="5f994-137">3600</span><span class="sxs-lookup"><span data-stu-id="5f994-137">3600</span></span>|   <span data-ttu-id="5f994-138">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="5f994-138">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="5f994-139">CNAME</span><span class="sxs-lookup"><span data-stu-id="5f994-139">CNAME</span></span>| <span data-ttu-id="5f994-140">sip</span><span class="sxs-lookup"><span data-stu-id="5f994-140">sip</span></span>|    <span data-ttu-id="5f994-141">3600</span><span class="sxs-lookup"><span data-stu-id="5f994-141">3600</span></span>|   <span data-ttu-id="5f994-142">sipdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="5f994-142">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="5f994-143">CNAME</span><span class="sxs-lookup"><span data-stu-id="5f994-143">CNAME</span></span>| <span data-ttu-id="5f994-144">滿足</span><span class="sxs-lookup"><span data-stu-id="5f994-144">meet</span></span>|   <span data-ttu-id="5f994-145">3600</span><span class="sxs-lookup"><span data-stu-id="5f994-145">3600</span></span>|   <span data-ttu-id="5f994-146">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="5f994-146">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="5f994-147">CNAME</span><span class="sxs-lookup"><span data-stu-id="5f994-147">CNAME</span></span>| <span data-ttu-id="5f994-148">入</span><span class="sxs-lookup"><span data-stu-id="5f994-148">dialin</span></span>  |<span data-ttu-id="5f994-149">3600</span><span class="sxs-lookup"><span data-stu-id="5f994-149">3600</span></span>|  <span data-ttu-id="5f994-150">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="5f994-150">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="5f994-151">*停用 Office 365 組織中的共用 SIP 位址空間。*</span><span class="sxs-lookup"><span data-stu-id="5f994-151">*Disable shared SIP address space in Office 365 organization.*</span></span>
<span data-ttu-id="5f994-152">以下的命令必須透過商務用 Skype Online PowerShell 視窗執行。</span><span class="sxs-lookup"><span data-stu-id="5f994-152">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  <span data-ttu-id="5f994-153">*停用內部部署中與 Office 365 通訊的功能。*</span><span class="sxs-lookup"><span data-stu-id="5f994-153">*Disable ability in on-premises to communicate with Office 365.*</span></span>  
<span data-ttu-id="5f994-154">以下是必須從內部部署 PowerShell 視窗執行的命令：</span><span class="sxs-lookup"><span data-stu-id="5f994-154">The command below needs to be done from an on-premises PowerShell window:</span></span>

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="5f994-155">管理從內部部署遷移之使用者的電話號碼</span><span class="sxs-lookup"><span data-stu-id="5f994-155">Manage phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="5f994-156">管理員可以管理先前已從內部部署商務用 Skype Server 移至雲端的使用者，即使已解除內部部署的部署。</span><span class="sxs-lookup"><span data-stu-id="5f994-156">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="5f994-157">有兩種不同的可能性：</span><span class="sxs-lookup"><span data-stu-id="5f994-157">There are two different possibilities:</span></span>

- <span data-ttu-id="5f994-158">在移動之前，使用者沒有 LineURI 內部部署的值。</span><span class="sxs-lookup"><span data-stu-id="5f994-158">The user did not have a value for LineURI on-premises before the move.</span></span> 

  <span data-ttu-id="5f994-159">在此情況下，您可以在商務用 Skype Online PowerShell 模組中，使用[Set-CsUser Cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)中的-onpremLineUri 參數修改 LineURI。</span><span class="sxs-lookup"><span data-stu-id="5f994-159">In this case, you can modify the LineURI using the -onpremLineUri parameters in the [Set-CsUser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

- <span data-ttu-id="5f994-160">使用者在移動之前有 LineURI 內部部署（原因是使用者已啟用 Enterprise Voice）。</span><span class="sxs-lookup"><span data-stu-id="5f994-160">The user had a LineURI on-premises before the move (presumably because the user was enabled for Enterprise Voice).</span></span> 

  <span data-ttu-id="5f994-161">如果您想要變更 LineURI，您必須在內部部署 Active Directory 中執行這項作業，並讓此值流向 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="5f994-161">If you want to change the LineURI, you must do this in the on-premises Active Directory and let the value flow up to Azure AD.</span></span> <span data-ttu-id="5f994-162">這不需要內部部署商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="5f994-162">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="5f994-163">相反地，您可以使用 Active Directory 使用者和電腦 MMC 嵌入式管理單元，或是使用 PowerShell，直接在內部部署 Active Directory 中編輯此屬性 msRTCSIP 行。</span><span class="sxs-lookup"><span data-stu-id="5f994-163">Rather, this attribute, msRTCSIP-Line, can be edited directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in, or by using PowerShell.</span></span> <span data-ttu-id="5f994-164">如果您使用的是 MMC 嵌入式管理單元，請開啟至使用者的 [內容] 頁面，按一下 [屬性編輯器] 索引標籤，然後尋找 msRTCSIP 行。</span><span class="sxs-lookup"><span data-stu-id="5f994-164">If you are using the MMC snap-in, open to the properties page of the user, click Attribute Editor tab, and find msRTCSIP-Line.</span></span>

  ![Active Directory 使用者和電腦工具](../media/disable-hybrid-1.png)

## <a name="see-also"></a><span data-ttu-id="5f994-166">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5f994-166">See also</span></span>

[<span data-ttu-id="5f994-167">小組和商務用 Skype 的雲端整合</span><span class="sxs-lookup"><span data-stu-id="5f994-167">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

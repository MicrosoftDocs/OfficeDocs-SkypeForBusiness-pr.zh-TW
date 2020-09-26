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
ms.openlocfilehash: 93aad1ea230d9edbb81673a3ddabc7088b06d422
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277260"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="17144-103">停用混合式以完成移轉至雲端</span><span class="sxs-lookup"><span data-stu-id="17144-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="17144-104">將所有使用者從內部部署移至雲端之後，您就可以解除內部部署的商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="17144-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="17144-105">除了移除任何硬體之外，重要的步驟是透過停用混合式，以邏輯方式將該內部部署與 Microsoft 365 或 Office 365 分開。</span><span class="sxs-lookup"><span data-stu-id="17144-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Microsoft 365 or Office 365 by disabling hybrid.</span></span> <span data-ttu-id="17144-106">停用混合式包含三個步驟：</span><span class="sxs-lookup"><span data-stu-id="17144-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="17144-107">更新 DNS 記錄，以指向 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="17144-107">Update DNS records to point to Microsoft 365 or Office 365.</span></span>

2. <span data-ttu-id="17144-108">停用 Microsoft 365 或 Office 365 組織中的分割網域。</span><span class="sxs-lookup"><span data-stu-id="17144-108">Disable split domain in the Microsoft 365 or Office 365 organization.</span></span>

3. <span data-ttu-id="17144-109">停用內部部署中與 Microsoft 365 或 Office 365 通訊的功能。</span><span class="sxs-lookup"><span data-stu-id="17144-109">Disable the ability in on-premises to communicate with Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="17144-110">這些步驟應該一起做為一個單位。</span><span class="sxs-lookup"><span data-stu-id="17144-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="17144-111">以下提供詳細資料。</span><span class="sxs-lookup"><span data-stu-id="17144-111">Details are provided below.</span></span> <span data-ttu-id="17144-112">此外，在中斷內部部署的部署後，也會提供指導方針來管理遷移使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="17144-112">In addition, guidelines are provided for managing phone numbers for migrated users once the on-premises deployment is disconnected.</span></span>

<span data-ttu-id="17144-113">完成這些步驟之後，就不再使用內部部署商務用 Skype 伺服器，而且可以重新映射這些伺服器。</span><span class="sxs-lookup"><span data-stu-id="17144-113">Once these steps are complete, the on-premises Skype for Business servers are no longer used, and these servers can be re-imaged.</span></span>

> [!Important] 
><span data-ttu-id="17144-114">您應該繼續讓 Active Directory 同步處理中的 msRTCSIP 屬性，透過 Azure AD 連接至 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="17144-114">You should continue to let the msRTCSIP attributes in Active Directory sync via Azure AD Connect into Azure AD.</span></span>  <span data-ttu-id="17144-115">除非受到支援，否則請勿清除任何這些屬性。</span><span class="sxs-lookup"><span data-stu-id="17144-115">Do not clear any of these attributes unless directed to by Support.</span></span>  <span data-ttu-id="17144-116">請勿在內部部署環境中執行 Disable-Get-csuser。</span><span class="sxs-lookup"><span data-stu-id="17144-116">Do not run Disable-CsUser in the on-premises environment.</span></span> <span data-ttu-id="17144-117">如果您需要修改使用者的 SIP 位址，請在您的內部部署 Active Directory 中執行這項作業，並透過 Azure AD Connect 將此變更同步處理到 Azure AD Connect，如下所述。</span><span class="sxs-lookup"><span data-stu-id="17144-117">If you need to modify a user’s SIP address, do this in your on-premises Active Directory and let this change sync into Azure AD via Azure AD Connect as described below.</span></span> <span data-ttu-id="17144-118">同樣地，如果您需要變更電話號碼，且已在內部部署中定義使用者的 LineURI，您應該在內部部署 Active Directory 中修改此值。</span><span class="sxs-lookup"><span data-stu-id="17144-118">Similarly, if you need to change a telephone number and the user’s LineURI is already defined on-premises, you should modify this in the on-premises Active Directory.</span></span>
><span data-ttu-id="17144-119">在您從內部部署遷移之後清除內部部署 msRTCSIP 屬性，可能會導致使用者的服務遺失！</span><span class="sxs-lookup"><span data-stu-id="17144-119">Clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span>


1.  <span data-ttu-id="17144-120">*將 DNS 更新為指向 Microsoft 365 或 Office 365。*</span><span class="sxs-lookup"><span data-stu-id="17144-120">*Update DNS to point to Microsoft 365 or  Office 365.*</span></span>
<span data-ttu-id="17144-121">組織的外部 DNS 必須更新內部部署組織，以便商務用 Skype 記錄指向 Microsoft 365 或 Office 365，而不是內部部署。</span><span class="sxs-lookup"><span data-stu-id="17144-121">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 or Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="17144-122">特別是：</span><span class="sxs-lookup"><span data-stu-id="17144-122">Specifically:</span></span>

    |<span data-ttu-id="17144-123">Record type (記錄類型)</span><span class="sxs-lookup"><span data-stu-id="17144-123">Record type</span></span>|<span data-ttu-id="17144-124">名稱</span><span class="sxs-lookup"><span data-stu-id="17144-124">Name</span></span>|<span data-ttu-id="17144-125">TTL</span><span class="sxs-lookup"><span data-stu-id="17144-125">TTL</span></span>|<span data-ttu-id="17144-126">Value (值)</span><span class="sxs-lookup"><span data-stu-id="17144-126">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="17144-127">SRV</span><span class="sxs-lookup"><span data-stu-id="17144-127">SRV</span></span>|<span data-ttu-id="17144-128">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="17144-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="17144-129">3600</span><span class="sxs-lookup"><span data-stu-id="17144-129">3600</span></span>|<span data-ttu-id="17144-130">100 1 5061 sipfed （lync <span> ）。Com</span><span class="sxs-lookup"><span data-stu-id="17144-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="17144-131">SRV</span><span class="sxs-lookup"><span data-stu-id="17144-131">SRV</span></span>|<span data-ttu-id="17144-132">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="17144-132">_sip._tls</span></span>|<span data-ttu-id="17144-133">3600</span><span class="sxs-lookup"><span data-stu-id="17144-133">3600</span></span>|<span data-ttu-id="17144-134">100 1 443 sipdir （lync <span> ）。Com</span><span class="sxs-lookup"><span data-stu-id="17144-134">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="17144-135">CNAME</span><span class="sxs-lookup"><span data-stu-id="17144-135">CNAME</span></span>| <span data-ttu-id="17144-136">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="17144-136">lyncdiscover</span></span>|   <span data-ttu-id="17144-137">3600</span><span class="sxs-lookup"><span data-stu-id="17144-137">3600</span></span>|   <span data-ttu-id="17144-138"><span>webdir。Com</span><span class="sxs-lookup"><span data-stu-id="17144-138">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="17144-139">CNAME</span><span class="sxs-lookup"><span data-stu-id="17144-139">CNAME</span></span>| <span data-ttu-id="17144-140">sip</span><span class="sxs-lookup"><span data-stu-id="17144-140">sip</span></span>|    <span data-ttu-id="17144-141">3600</span><span class="sxs-lookup"><span data-stu-id="17144-141">3600</span></span>|   <span data-ttu-id="17144-142"><span>sipdir。Com</span><span class="sxs-lookup"><span data-stu-id="17144-142">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="17144-143">CNAME</span><span class="sxs-lookup"><span data-stu-id="17144-143">CNAME</span></span>| <span data-ttu-id="17144-144">滿足</span><span class="sxs-lookup"><span data-stu-id="17144-144">meet</span></span>|   <span data-ttu-id="17144-145">3600</span><span class="sxs-lookup"><span data-stu-id="17144-145">3600</span></span>|   <span data-ttu-id="17144-146"><span>webdir。Com</span><span class="sxs-lookup"><span data-stu-id="17144-146">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="17144-147">CNAME</span><span class="sxs-lookup"><span data-stu-id="17144-147">CNAME</span></span>| <span data-ttu-id="17144-148">入</span><span class="sxs-lookup"><span data-stu-id="17144-148">dialin</span></span>  |<span data-ttu-id="17144-149">3600</span><span class="sxs-lookup"><span data-stu-id="17144-149">3600</span></span>|  <span data-ttu-id="17144-150"><span>webdir。Com</span><span class="sxs-lookup"><span data-stu-id="17144-150">webdir.online.lync.<span>com</span></span>|

    <span data-ttu-id="17144-151">此外，如果存在) 可刪除，則為符合或撥入 (的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="17144-151">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="17144-152">最後，您應該移除內部網路中商務用 Skype 的任何 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="17144-152">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

    > [!Note] 
    > <span data-ttu-id="17144-153">在極少的情況下，將組織的內部部署至 Office 365 的 DNS 變更為您的組織可能會造成其他一些組織的同盟停止運作，直到其他組織更新其同盟設定為止：</span><span class="sxs-lookup"><span data-stu-id="17144-153">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="17144-154">任何使用舊版直接同盟模型的同盟組織 (又稱為允許的夥伴伺服器) ，都必須更新其組織的允許網域專案，以移除 proxy FQDN。</span><span class="sxs-lookup"><span data-stu-id="17144-154">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="17144-155">這種舊版同盟模型不是以 DNS SRV 記錄為基礎，因此當您的組織移至雲端時，此設定將會到期。</span><span class="sxs-lookup"><span data-stu-id="17144-155">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="17144-156">任何沒有啟用 sipfed <span> 之主機服務提供者的同盟組織。com 必須更新其設定，才能啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="17144-156">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="17144-157">只有在同盟組織完全存在於內部部署，且決不會與任何混合式或線上租使用者同盟的情況下，才可能出現這種情況。</span><span class="sxs-lookup"><span data-stu-id="17144-157">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="17144-158">在此情況下，與這些組織的同盟必須啟用其主機服務提供者後，才能運作。</span><span class="sxs-lookup"><span data-stu-id="17144-158">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="17144-159">如果您懷疑任何同盟協力廠商可能使用的是直接同盟或尚未與任何線上或混合組織同盟，我們建議您在準備完成對雲端的遷移時，向他們傳送此資訊的通訊。</span><span class="sxs-lookup"><span data-stu-id="17144-159">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>


2.  <span data-ttu-id="17144-160">*停用 Microsoft 365 或 Office 365 組織中的共用 SIP 位址空間。*</span><span class="sxs-lookup"><span data-stu-id="17144-160">*Disable shared SIP address space in Microsoft 365 or Office 365 organization.*</span></span>
<span data-ttu-id="17144-161">以下的命令必須透過商務用 Skype Online PowerShell 視窗執行。</span><span class="sxs-lookup"><span data-stu-id="17144-161">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  <span data-ttu-id="17144-162">*停用內部部署中與 Microsoft 365 或 Office 365 通訊的功能。*</span><span class="sxs-lookup"><span data-stu-id="17144-162">*Disable ability in on-premises to communicate with Microsoft 365 or Office 365.*</span></span>  
<span data-ttu-id="17144-163">以下是必須從內部部署 PowerShell 視窗執行的命令：</span><span class="sxs-lookup"><span data-stu-id="17144-163">The command below needs to be done from an on-premises PowerShell window:</span></span>

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="17144-164">管理從內部部署遷移之使用者的 sip 位址和電話號碼</span><span class="sxs-lookup"><span data-stu-id="17144-164">Manage sip addresses and phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="17144-165">管理員可以管理先前已從內部部署商務用 Skype Server 移至雲端的使用者，即使已解除內部部署的部署。</span><span class="sxs-lookup"><span data-stu-id="17144-165">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="17144-166">如果您想要變更使用者的 SIP 位址或使用者的列 URI (，且已在內部部署 Active Directory) 中定義 SIP 位址或線路 URI，您必須在內部部署 Active Directory 中進行此項操作，並且讓值 (s) 流向 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="17144-166">If you want to make changes to a user’s SIP address or to a user’s Line URI (and the SIP address or Line URI is already defined in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="17144-167">這不需要內部部署商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="17144-167">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="17144-168">相反地，您可以使用 Active Directory 使用者和電腦 MMC 嵌入式管理單元，或是使用 PowerShell，直接在內部部署 Active Directory 中修改這些屬性。</span><span class="sxs-lookup"><span data-stu-id="17144-168">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in, or by using PowerShell.</span></span> <span data-ttu-id="17144-169">如果您使用的是 MMC 嵌入式管理單元，請開啟使用者的 [屬性] 頁面，按一下 [屬性編輯器] 索引標籤，然後尋找適當的屬性進行修改：</span><span class="sxs-lookup"><span data-stu-id="17144-169">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="17144-170">若要修改使用者的 SIP 位址，請修改 `msRTCSIP-PrimaryUserAddress` 。</span><span class="sxs-lookup"><span data-stu-id="17144-170">To modify a user’s SIP address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="17144-171">此外，如果 `ProxyAddresses` 屬性包含 sip 值，請更新該 sip 值，使其符合新的值 `msRTCSIP-PrimaryUserAddress` 。</span><span class="sxs-lookup"><span data-stu-id="17144-171">In addition, if the `ProxyAddresses` attribute contains a SIP value, update that SIP value to match the new value of `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="17144-172">如果不包含 SIP 值，您可以將它保留空白。</span><span class="sxs-lookup"><span data-stu-id="17144-172">If it does not contain a SIP value, you can leave it blank.</span></span>

- <span data-ttu-id="17144-173">若要修改使用者的電話號碼，請修改 `msRTCSIP-Line` *是否已有值*。</span><span class="sxs-lookup"><span data-stu-id="17144-173">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Active Directory 使用者和電腦工具](../media/disable-hybrid-1.png)
  
<span data-ttu-id="17144-175">如果使用者在 `LineURI` 移動之前沒有內部部署的值，您可以使用商務用 `onpremLineUri` Skype Online PowerShell 模組的 [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) 指令程式中的-參數修改 LineURI。</span><span class="sxs-lookup"><span data-stu-id="17144-175">If the user did not originally have a value for `LineURI` on-premises before the move, you can modify the LineURI using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>


## <a name="see-also"></a><span data-ttu-id="17144-176">請參閱</span><span class="sxs-lookup"><span data-stu-id="17144-176">See also</span></span>

[<span data-ttu-id="17144-177">小組和商務用 Skype 的雲端整合</span><span class="sxs-lookup"><span data-stu-id="17144-177">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

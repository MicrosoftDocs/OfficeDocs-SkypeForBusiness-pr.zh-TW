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
description: 本文包含針對團隊和商務用 Skype 進行雲整合時停用混合式的詳細步驟。
ms.openlocfilehash: 36ec3cba2d821cc8554e0fba95108756c83b7b3d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120352"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud-overview"></a><span data-ttu-id="1010c-103">停用混合式，以完成將遷移至雲端：一覽</span><span class="sxs-lookup"><span data-stu-id="1010c-103">Disable hybrid to complete migration to the cloud: Overview</span></span>

<span data-ttu-id="1010c-104">將所有使用者從內部部署移至雲端之後，您就可以解除內部部署的商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="1010c-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="1010c-105">除了移除任何硬體之外，重要的步驟是透過停用混合式，以邏輯方式將該內部部署與 Microsoft 365 或 Office 365 分開。</span><span class="sxs-lookup"><span data-stu-id="1010c-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Microsoft 365 or Office 365 by disabling hybrid.</span></span> <span data-ttu-id="1010c-106">停用混合式包含三個步驟：</span><span class="sxs-lookup"><span data-stu-id="1010c-106">Disabling hybrid consists of three steps:</span></span>

1. <span data-ttu-id="1010c-107">更新 DNS 記錄，以指向 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="1010c-107">Update DNS records to point to Microsoft 365 or Office 365.</span></span>

2. <span data-ttu-id="1010c-108">停用共用 sip 位址空間 (也稱為「分割網域」 ) 在 Microsoft 365 或 Office 365 組織中。</span><span class="sxs-lookup"><span data-stu-id="1010c-108">Disable shared sip address space (also known as "split domain") in the Microsoft 365 or Office 365 organization.</span></span>

3. <span data-ttu-id="1010c-109">停用內部部署中與 Microsoft 365 或 Office 365 通訊的功能。</span><span class="sxs-lookup"><span data-stu-id="1010c-109">Disable the ability in on-premises to communicate with Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="1010c-110">這些步驟會以邏輯方式分隔商務用 Skype Server 的內部部署與 Office 365，應一起做為一個單位。</span><span class="sxs-lookup"><span data-stu-id="1010c-110">These steps logically separate your on-premise deployment of Skype for Business Server from Office 365 and should be done together as a unit.</span></span> <span data-ttu-id="1010c-111">本文提供每個步驟的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1010c-111">Details for each step are provided in this article below.</span></span> <span data-ttu-id="1010c-112">完成後，您可以使用下列兩種方法之一來解除委任您的內部部署商務用 Skype 部署。</span><span class="sxs-lookup"><span data-stu-id="1010c-112">Once that is complete, you can decommission your on-premises Skype for Business Deployment using one of two methods referenced below.</span></span>

> [!Important] 
><span data-ttu-id="1010c-113">完成此邏輯分隔之後，來自內部部署 Active Directory 的 msRTCSIP 屬性仍然具有值，而且會繼續透過 Azure AD Connect 同步處理到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="1010c-113">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="1010c-114">如何解除委任內部部署環境取決於您想要將這些屬性保留在原處，還是先從您的內部部署 Active Directory 加以清除。</span><span class="sxs-lookup"><span data-stu-id="1010c-114">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="1010c-115">請注意，在您從內部部署遷移之後清除內部部署 msRTCSIP 屬性，可能會導致使用者的服務遺失！</span><span class="sxs-lookup"><span data-stu-id="1010c-115">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="1010c-116">以下說明兩個解除委任方法的詳細資料和折衷。</span><span class="sxs-lookup"><span data-stu-id="1010c-116">Details and tradeoffs of the two decommissioning approaches are described later below.</span></span>

## <a name="disable-hybrid-to-complete-migration-to-the-cloud-detailed-steps"></a><span data-ttu-id="1010c-117">停用混合式以完成將遷移至雲端：詳細步驟</span><span class="sxs-lookup"><span data-stu-id="1010c-117">Disable hybrid to complete migration to the cloud: Detailed Steps</span></span>

1. <span data-ttu-id="1010c-118">*將 DNS 更新為指向 Microsoft 365 或 Office 365。*</span><span class="sxs-lookup"><span data-stu-id="1010c-118">*Update DNS to point to Microsoft 365 or  Office 365.*</span></span> <span data-ttu-id="1010c-119">組織的外部 DNS 必須更新內部部署組織，以便商務用 Skype 記錄指向 Microsoft 365 或 Office 365，而不是內部部署。</span><span class="sxs-lookup"><span data-stu-id="1010c-119">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 or Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="1010c-120">特別是：</span><span class="sxs-lookup"><span data-stu-id="1010c-120">Specifically:</span></span>

    |<span data-ttu-id="1010c-121">Record type (記錄類型)</span><span class="sxs-lookup"><span data-stu-id="1010c-121">Record type</span></span>|<span data-ttu-id="1010c-122">名稱</span><span class="sxs-lookup"><span data-stu-id="1010c-122">Name</span></span>|<span data-ttu-id="1010c-123">TTL</span><span class="sxs-lookup"><span data-stu-id="1010c-123">TTL</span></span>|<span data-ttu-id="1010c-124">Value (值)</span><span class="sxs-lookup"><span data-stu-id="1010c-124">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="1010c-125">SRV</span><span class="sxs-lookup"><span data-stu-id="1010c-125">SRV</span></span>|<span data-ttu-id="1010c-126">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="1010c-126">_sipfederationtls._tcp</span></span>|<span data-ttu-id="1010c-127">3600</span><span class="sxs-lookup"><span data-stu-id="1010c-127">3600</span></span>|<span data-ttu-id="1010c-128">100 1 5061 sipfed （lync <span> ）。Com</span><span class="sxs-lookup"><span data-stu-id="1010c-128">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="1010c-129">SRV</span><span class="sxs-lookup"><span data-stu-id="1010c-129">SRV</span></span>|<span data-ttu-id="1010c-130">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="1010c-130">_sip._tls</span></span>|<span data-ttu-id="1010c-131">3600</span><span class="sxs-lookup"><span data-stu-id="1010c-131">3600</span></span>|<span data-ttu-id="1010c-132">100 1 443 sipdir （lync <span> ）。Com</span><span class="sxs-lookup"><span data-stu-id="1010c-132">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="1010c-133">CNAME</span><span class="sxs-lookup"><span data-stu-id="1010c-133">CNAME</span></span>| <span data-ttu-id="1010c-134">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1010c-134">lyncdiscover</span></span>|   <span data-ttu-id="1010c-135">3600</span><span class="sxs-lookup"><span data-stu-id="1010c-135">3600</span></span>|   <span data-ttu-id="1010c-136"><span>webdir。Com</span><span class="sxs-lookup"><span data-stu-id="1010c-136">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="1010c-137">CNAME</span><span class="sxs-lookup"><span data-stu-id="1010c-137">CNAME</span></span>| <span data-ttu-id="1010c-138">sip</span><span class="sxs-lookup"><span data-stu-id="1010c-138">sip</span></span>|    <span data-ttu-id="1010c-139">3600</span><span class="sxs-lookup"><span data-stu-id="1010c-139">3600</span></span>|   <span data-ttu-id="1010c-140"><span>sipdir。Com</span><span class="sxs-lookup"><span data-stu-id="1010c-140">sipdir.online.lync.<span>com</span></span>|

    <span data-ttu-id="1010c-141">此外，如果存在) 可刪除，則為符合或撥入 (的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="1010c-141">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="1010c-142">最後，您應該移除內部網路中商務用 Skype 的任何 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="1010c-142">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

    > [!Note] 
    > <span data-ttu-id="1010c-143">在極少的情況下，將 DNS 從指向 Microsoft 365 或 Office 365 的內部部署變更為組織可能會造成其他一些組織的同盟停止運作，直到其他組織更新其同盟設定為止：</span><span class="sxs-lookup"><span data-stu-id="1010c-143">In rare cases, changing DNS from pointing on premises to Microsoft 365 or Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="1010c-144">任何使用舊版直接同盟模型的同盟組織 (又稱為允許的夥伴伺服器) ，都必須更新其組織的允許網域專案，以移除 proxy FQDN。</span><span class="sxs-lookup"><span data-stu-id="1010c-144">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="1010c-145">這種舊版同盟模型不是以 DNS SRV 記錄為基礎，因此當您的組織移至雲端時，此設定將會到期。</span><span class="sxs-lookup"><span data-stu-id="1010c-145">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="1010c-146">任何沒有啟用 sipfed <span> 之主機服務提供者的同盟組織。com 必須更新其設定，才能啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="1010c-146">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="1010c-147">只有在同盟組織完全存在於內部部署，且決不會與任何混合式或線上租使用者同盟的情況下，才可能出現這種情況。</span><span class="sxs-lookup"><span data-stu-id="1010c-147">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="1010c-148">在此情況下，與這些組織的同盟必須啟用其主機服務提供者後，才能運作。</span><span class="sxs-lookup"><span data-stu-id="1010c-148">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="1010c-149">如果您懷疑任何同盟協力廠商可能使用的是直接同盟或尚未與任何線上或混合組織同盟，我們建議您在準備完成對雲端的遷移時，向他們傳送此資訊的通訊。</span><span class="sxs-lookup"><span data-stu-id="1010c-149">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>


2.  <span data-ttu-id="1010c-150">*停用 Microsoft 365 或 Office 365 組織中的共用 sip 位址空間。*</span><span class="sxs-lookup"><span data-stu-id="1010c-150">*Disable shared sip address space in Microsoft 365 or Office 365 organization.*</span></span> <span data-ttu-id="1010c-151">以下的命令必須透過商務用 Skype Online PowerShell 視窗執行。</span><span class="sxs-lookup"><span data-stu-id="1010c-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
3.  <span data-ttu-id="1010c-152">*停用內部部署中與 Microsoft 365 或 Office 365 通訊的功能。*</span><span class="sxs-lookup"><span data-stu-id="1010c-152">*Disable the ability in on-premises to communicate with Microsoft 365 or Office 365.*</span></span> <span data-ttu-id="1010c-153">以下是必須從內部部署 PowerShell 視窗執行的命令：</span><span class="sxs-lookup"><span data-stu-id="1010c-153">The command below needs to be done from an on-premises PowerShell window:</span></span>

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="1010c-154">在將使用者從內部部署移至雲端之後管理屬性</span><span class="sxs-lookup"><span data-stu-id="1010c-154">Managing attributes after moving users from on-premises to the cloud</span></span>

<span data-ttu-id="1010c-155">根據預設，所有先前為商務用 Skype Server 啟用後又移至雲端的使用者，在內部部署 Active Directory 中所設定的 msRTCSIP 屬性仍然都是相同的。</span><span class="sxs-lookup"><span data-stu-id="1010c-155">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> <span data-ttu-id="1010c-156">這些屬性在特定 sip 位址 (msRTCSIP-PrimaryUserAddress) 和可能的電話號碼 (msRTCSIP 行) ，請繼續同步處理至 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="1010c-156">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="1010c-157">如果需要變更任何 msRTCSIP 屬性，必須在內部部署 Active Directory 中進行這些變更，然後同步處理至 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="1010c-157">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="1010c-158">不過，當商務用 Skype Server 部署已移除之後，商務用 Skype 伺服器工具將無法用來管理這些屬性。</span><span class="sxs-lookup"><span data-stu-id="1010c-158">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="1010c-159">有兩個選項可用於處理這種情況：</span><span class="sxs-lookup"><span data-stu-id="1010c-159">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="1010c-160">保留已啟用商務用 Skype 伺服器帳戶的使用者，並使用 Active Directory 工具管理 msRTCSIP 屬性。</span><span class="sxs-lookup"><span data-stu-id="1010c-160">Leave users that were enabled for Skype for Business server accounts as is, and manage the  msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="1010c-161">這可確保遷移的使用者不會遺失服務，而且可讓您透過消除 (（例如，擦除) 伺服器，而不需完全退役）來輕鬆移除商務用 Skype 伺服器的部署。</span><span class="sxs-lookup"><span data-stu-id="1010c-161">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="1010c-162">不過，新授權的使用者將不會在您的內部部署 Active Directory 中填入這些屬性，且必須在線上進行管理。</span><span class="sxs-lookup"><span data-stu-id="1010c-162">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="1010c-163">從內部部署 Active Directory 中已遷移的使用者清除所有 msRTCSIP 屬性，並使用線上工具管理這些屬性。</span><span class="sxs-lookup"><span data-stu-id="1010c-163">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="1010c-164">這個方法可讓現有和新使用者使用一致的管理方法，但在內部部署解除委任程式中，可能會導致服務暫時遺失。</span><span class="sxs-lookup"><span data-stu-id="1010c-164">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="1010c-165">方法 1-管理 Active Directory 中使用者的 sip 位址和電話號碼</span><span class="sxs-lookup"><span data-stu-id="1010c-165">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="1010c-166">管理員可以管理先前已從內部部署商務用 Skype Server 移至雲端的使用者，即使已解除內部部署的部署。</span><span class="sxs-lookup"><span data-stu-id="1010c-166">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="1010c-167">若要變更使用者的 sip 位址或使用者的電話號碼 (而且 sip 位址或電話號碼在內部部署 Active Directory) 中已有值，您必須在內部部署 Active Directory 中執行這項作業，並讓) 流向 Azure AD 的值 (s。</span><span class="sxs-lookup"><span data-stu-id="1010c-167">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="1010c-168">這不需要內部部署商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="1010c-168">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="1010c-169">相反地，您可以使用 Active Directory 使用者和電腦 MMC 嵌入式管理單元來直接修改內部部署 Active Directory 中的這些屬性 (，如) 所示，或是使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1010c-169">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="1010c-170">如果您使用的是 MMC 嵌入式管理單元，請開啟使用者的 [屬性] 頁面，按一下 [屬性編輯器] 索引標籤，然後尋找適當的屬性進行修改：</span><span class="sxs-lookup"><span data-stu-id="1010c-170">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="1010c-171">若要修改使用者的 sip 位址，請修改 `msRTCSIP-PrimaryUserAddress` 。</span><span class="sxs-lookup"><span data-stu-id="1010c-171">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="1010c-172">請注意，如果 `ProxyAddresses` 屬性包含 sip 位址，也會將此值更新為最佳作法。</span><span class="sxs-lookup"><span data-stu-id="1010c-172">Note, if the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="1010c-173">雖然所填入的 sip 位址 `ProxyAddresses` 已在 O365 中忽略，但 `msRTCSIP-PrimaryUserAddress` 其他內部部署元件也可以使用它。</span><span class="sxs-lookup"><span data-stu-id="1010c-173">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="1010c-174">若要修改使用者的電話號碼，請修改 `msRTCSIP-Line` *是否已有值*。</span><span class="sxs-lookup"><span data-stu-id="1010c-174">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Active Directory 使用者和電腦工具](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="1010c-176">如果使用者在 `msRTCSIP-Line` 移動之前沒有內部部署的值，您可以使用 `onpremLineUri` 商務用 Skype Online PowerShell 模組的 [Set-CsUser Cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) 中的-參數修改電話號碼。</span><span class="sxs-lookup"><span data-stu-id="1010c-176">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="1010c-177">在您停用混合式之後所建立的新使用者，這些使用者不需要這些步驟，而且可以直接在雲端中管理這些使用者。</span><span class="sxs-lookup"><span data-stu-id="1010c-177">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="1010c-178">如果您習慣使用這些方法的組合，以及在內部部署 Active Directory 中就地保留 msRTCSIP 屬性，則可以直接重新影像內部部署商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="1010c-178">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="1010c-179">不過，如果您想要清除所有 msRTCSIP 屬性，並執行傳統的商務用 Skype 伺服器卸載，請使用方法2。</span><span class="sxs-lookup"><span data-stu-id="1010c-179">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="1010c-180">方法 2-清除 Active Directory 中所有內部部署使用者的商務用 Skype 屬性</span><span class="sxs-lookup"><span data-stu-id="1010c-180">Method 2 - Clear Skype for Business Attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="1010c-181">此選項需要額外的工作量及適當的規劃，因為先前已從內部部署商務用 Skype Server 移至雲端的使用者需要重新布建。</span><span class="sxs-lookup"><span data-stu-id="1010c-181">This option requires additional effort and proper planning because users that were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="1010c-182">這些使用者可以分為兩種不同的類別：沒有電話系統的使用者，以及具有電話系統的使用者。</span><span class="sxs-lookup"><span data-stu-id="1010c-182">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="1010c-183">在將電話號碼轉換成內部部署 Active Directory 至雲端時，具有電話系統服務的使用者將會經歷暫時遺失電話語音的一部分。</span><span class="sxs-lookup"><span data-stu-id="1010c-183">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="1010c-184">**建議您在開始大量使用者作業之前，先執行一些包含少量使用者和電話系統的試驗。**</span><span class="sxs-lookup"><span data-stu-id="1010c-184">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="1010c-185">對於大型部署，使用者可以在不同時間視窗的較小群組中處理。</span><span class="sxs-lookup"><span data-stu-id="1010c-185">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE]
> <span data-ttu-id="1010c-186">若使用者具有比對的 sip 位址和 UserPrincipalName，程式就是最簡單的處理常式。</span><span class="sxs-lookup"><span data-stu-id="1010c-186">The process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="1010c-187">如果組織的使用者在這兩個屬性之間具有非符合性值，請特別注意，以順利進行轉換。</span><span class="sxs-lookup"><span data-stu-id="1010c-187">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span> 


1. <span data-ttu-id="1010c-188">確認下列內部部署商務用 Skype PowerShell Cmdlet 會傳回空的結果。</span><span class="sxs-lookup"><span data-stu-id="1010c-188">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="1010c-189">空的結果表示沒有使用者位於內部部署，且已移動至 Office 365 或已停用：</span><span class="sxs-lookup"><span data-stu-id="1010c-189">An empty result means no users are homed on-premises and have either been moved to Office 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="1010c-190">執行下列內部部署商務用 Skype Server PowerShell Cmdlet 以匯出使用者資料，以記錄使用者的目前電話號碼 (LineUri) 、UserPrincipalName 及相關資訊：</span><span class="sxs-lookup"><span data-stu-id="1010c-190">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="1010c-191">繼續開啟 SfbUserSettings.csv 的檔案，並確認所有使用者資料都已成功匯出之前。</span><span class="sxs-lookup"><span data-stu-id="1010c-191">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="1010c-192">建議保留此檔案的副本。</span><span class="sxs-lookup"><span data-stu-id="1010c-192">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="1010c-193">請勿在下列步驟中將此檔案用於處理使用者。</span><span class="sxs-lookup"><span data-stu-id="1010c-193">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="1010c-194">使用下列步驟建立包含一組使用者的檔案。</span><span class="sxs-lookup"><span data-stu-id="1010c-194">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="1010c-195">在第一組使用者成功完成之後，請繼續進行下一組使用者。</span><span class="sxs-lookup"><span data-stu-id="1010c-195">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="1010c-196">在下列範例中，會依字母順序選取使用者群組，但您可以依據符合您要處理使用者之方式的準則來篩選使用者。</span><span class="sxs-lookup"><span data-stu-id="1010c-196">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="1010c-197">繼續開啟的 SfbUsers.csv 檔案，並確認已順利匯出使用者資料。</span><span class="sxs-lookup"><span data-stu-id="1010c-197">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="1010c-198">在稍後的步驟中，您將需要 LineUri (電話號碼) 、UserPrincipalName、SamAccountName 和 SipAddress。</span><span class="sxs-lookup"><span data-stu-id="1010c-198">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="1010c-199">從 active Directory 中刪除與商務用 Skype Server 相關的屬性資訊，以供您準備更新的使用者集合使用。</span><span class="sxs-lookup"><span data-stu-id="1010c-199">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="1010c-200">此處理程式有兩個步驟，如下所示。</span><span class="sxs-lookup"><span data-stu-id="1010c-200">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="1010c-201">在執行此步驟後的下一個 AAD 同步處理週期之後，已將以前從內部部署商務用 Skype Server 移至雲端的使用者，且已從內部部署商務用 Skype Server 移至雲端的使用者，將無法進行呼叫，直到步驟8成功完成並確認步驟9中。</span><span class="sxs-lookup"><span data-stu-id="1010c-201">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="1010c-202">此外，請確定您已將使用者的電話號碼和相關資訊儲存為步驟2，因為該步驟需要該資訊。</span><span class="sxs-lookup"><span data-stu-id="1010c-202">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="1010c-203">接下來，針對同一組使用者，使用內部部署 Active Directory PowerShell: 清除 msRTCSIP-DeploymentLocator 的值</span><span class="sxs-lookup"><span data-stu-id="1010c-203">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="1010c-204">執行下列內部部署商務用 Skype PowerShell Cmdlet，將 sip 位址值新增回內部部署 Active Directory proxyAddresses。</span><span class="sxs-lookup"><span data-stu-id="1010c-204">Run the following on-premise Skype for Business PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="1010c-205">這會防止依賴此屬性的互通性問題。</span><span class="sxs-lookup"><span data-stu-id="1010c-205">This will prevent interoperability issues that rely on this attribute.</span></span> 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. <span data-ttu-id="1010c-206">執行 Azure AD Sync</span><span class="sxs-lookup"><span data-stu-id="1010c-206">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="1010c-207">等候使用者布建完成。</span><span class="sxs-lookup"><span data-stu-id="1010c-207">Wait for user provisioning to complete.</span></span> <span data-ttu-id="1010c-208">您可以執行下列商務用 Skype Online PowerShell 命令，以監視使用者布建進度。</span><span class="sxs-lookup"><span data-stu-id="1010c-208">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="1010c-209">下列商務用 Skype Online PowerShell 命令會在很快的處理常式完成時傳回空的結果。</span><span class="sxs-lookup"><span data-stu-id="1010c-209">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="1010c-210">執行下列商務用 Skype Online PowerShell 命令指派電話號碼，並為使用者啟用電話系統：</span><span class="sxs-lookup"><span data-stu-id="1010c-210">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  <span data-ttu-id="1010c-211">如果您仍然具有商務用 Skype 端點 (Skype 用戶端或協力廠商電話) ，您也會要將 HostedVoiceMail 設定為 $true。</span><span class="sxs-lookup"><span data-stu-id="1010c-211">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="1010c-212">如果您的組織只對啟用語音功能的使用者使用團隊端點，則此設定不適用於您的使用者。</span><span class="sxs-lookup"><span data-stu-id="1010c-212">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="1010c-213">確認已正確布建具有電話系統功能的使用者。</span><span class="sxs-lookup"><span data-stu-id="1010c-213">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="1010c-214">下列商務用 Skype Online PowerShell 命令會在很快的處理常式完成時傳回空的結果。</span><span class="sxs-lookup"><span data-stu-id="1010c-214">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. <span data-ttu-id="1010c-215">重複步驟3到9，直到處理所有使用者為止。</span><span class="sxs-lookup"><span data-stu-id="1010c-215">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="1010c-216">執行下列兩個 PowerShell 命令，確認已成功處理所有使用者。</span><span class="sxs-lookup"><span data-stu-id="1010c-216">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="1010c-217">內部部署商務用 Skype Server 內部部署 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="1010c-217">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="1010c-218">商務用 Skype Online PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="1010c-218">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 


## <a name="see-also"></a><span data-ttu-id="1010c-219">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1010c-219">See also</span></span>

[<span data-ttu-id="1010c-220">小組和商務用 Skype 的雲端整合</span><span class="sxs-lookup"><span data-stu-id="1010c-220">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
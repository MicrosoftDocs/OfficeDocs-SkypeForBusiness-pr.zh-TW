---
title: 停用混合式完成僅限 Teams 的遷移
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
description: 本文包含停用混合成 Teams 和商務用 Skype 之雲端合併的一部分的詳細步驟。
ms.openlocfilehash: 87bd1f6e0dcabed067174972dd0f0fc51149beb0
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453642"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a><span data-ttu-id="c0cf0-103">停用混合式設定，僅完成 Teams 的遷移</span><span class="sxs-lookup"><span data-stu-id="c0cf0-103">Disable your hybrid configuration to complete migration to Teams Only</span></span> 

<span data-ttu-id="c0cf0-104">本文說明如何在解除您的內部部署商務用 Skype 環境之前停用混合式設定。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-104">This article describes how to disable your hybrid configuration before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="c0cf0-105">這是下列步驟的步驟2，以解除委任您的內部部署環境：</span><span class="sxs-lookup"><span data-stu-id="c0cf0-105">This is step 2 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="c0cf0-106">步驟 1.</span><span class="sxs-lookup"><span data-stu-id="c0cf0-106">Step 1.</span></span> <span data-ttu-id="c0cf0-107">[將所有必要使用者從內部部署移至線上](decommission-move-on-prem-users.md)。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="c0cf0-108">**步驟2。停用您的混合式設定。**</span><span class="sxs-lookup"><span data-stu-id="c0cf0-108">**Step 2. Disable your hybrid configuration.**</span></span> <span data-ttu-id="c0cf0-109"> (本文) </span><span class="sxs-lookup"><span data-stu-id="c0cf0-109">(This article)</span></span>

- <span data-ttu-id="c0cf0-110">步驟 3.</span><span class="sxs-lookup"><span data-stu-id="c0cf0-110">Step 3.</span></span> <span data-ttu-id="c0cf0-111">[從內部部署向線上遷移混合應用程式端點](decommission-move-on-prem-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-111">[Migrate hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="c0cf0-112">步驟 4：</span><span class="sxs-lookup"><span data-stu-id="c0cf0-112">Step 4.</span></span> <span data-ttu-id="c0cf0-113">[移除您的內部部署商務用 Skype 部署](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c0cf0-114">步驟2和3應該在相同維護視窗中進行，因為任何現有的混合應用程式端點在步驟2和步驟3完成之間不會發現。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-114">Steps 2 and 3 should be done in the same maintenance window because any existing hybrid application endpoints will not be discoverable between steps 2 and completion of step 3.</span></span>


## <a name="summary"></a><span data-ttu-id="c0cf0-115">摘要</span><span class="sxs-lookup"><span data-stu-id="c0cf0-115">Summary</span></span>

<span data-ttu-id="c0cf0-116">將所有使用者從商務用 Skype 內部部署升級至僅 Microsoft 365 中 Teams 後，您就可以解除委任內部部署商務用 Skype 部署。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-116">After you have upgraded all users from Skype for Business on-premises to Teams Only in Microsoft 365, you can decommission the on-premises Skype for Business deployment.</span></span>

<span data-ttu-id="c0cf0-117">在您解除委任內部部署商務用 Skype 部署和移除任何硬體之前，您必須以邏輯方式從 Microsoft 365 中停用內部部署，方法是停用混合式。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-117">Before you decommission the on-premises Skype for Business deployment and remove any hardware, you must logically separate the on-premises deployment from Microsoft 365 by disabling hybrid.</span></span> <span data-ttu-id="c0cf0-118">停用混合式包含下列四個步驟：</span><span class="sxs-lookup"><span data-stu-id="c0cf0-118">Disabling hybrid consists of the following four steps:</span></span>

1. <span data-ttu-id="c0cf0-119">[更新 DNS 記錄，以指向 Microsoft 365](#update-dns-to-point-to-microsoft-365)。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-119">[Update DNS records to point to Microsoft 365](#update-dns-to-point-to-microsoft-365).</span></span>

2. <span data-ttu-id="c0cf0-120">[將您組織的共存模式變更為 [Teams]](#change-the-coexistence-mode-for-your-organization-to-teams-only)。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-120">[Change the coexistence mode for your organization to Teams Only](#change-the-coexistence-mode-for-your-organization-to-teams-only).</span></span>

3. <span data-ttu-id="c0cf0-121">[停用 Microsoft 365 組織中的共用 sip 位址空間 (也稱為「分割網域」 ) ](#disable-shared-sip-address-space-in-microsoft-365-organization)。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-121">[Disable shared sip address space (also known as "split domain") in the Microsoft 365 organization](#disable-shared-sip-address-space-in-microsoft-365-organization).</span></span>

4. [<span data-ttu-id="c0cf0-122">停用內部部署與 Microsoft 365 之間的通訊</span><span class="sxs-lookup"><span data-stu-id="c0cf0-122">Disable communication between on-premises and Microsoft 365</span></span>](#disable-communication-between-on-premises-and-microsoft-365)

<span data-ttu-id="c0cf0-123">這些步驟會以邏輯方式將您的內部部署商務用 Skype Server 從 Microsoft 365 中部署，並確保您的組織完全 Teams。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-123">These steps logically separate your on-premises deployment of Skype for Business Server from Microsoft 365 and ensure your organization is fully Teams Only.</span></span> <span data-ttu-id="c0cf0-124">在您完成這些步驟之後，您可以使用[決定如何在解除委任後管理屬性](cloud-consolidation-managing-attributes.md)的兩個方法中所述的其中一個方法，讓您的內部部署商務用 Skype 部署退役。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-124">After you've completed these steps, you can decommission your on-premises Skype for Business deployment by using one of two methods referenced in [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span></span>

> [!Important] 
> <span data-ttu-id="c0cf0-125">完成此邏輯分隔之後，來自內部部署 Active Directory 的 msRTCSIP 屬性仍然具有值，而且會繼續透過 Azure AD 連線同步處理到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-125">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="c0cf0-126">如何解除委任內部部署環境取決於您想要將這些屬性保留在原處，還是先從您的內部部署 Active Directory 加以清除。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-126">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="c0cf0-127">請注意，在您從內部部署遷移之後清除內部部署 msRTCSIP 屬性，可能會導致使用者的服務遺失！</span><span class="sxs-lookup"><span data-stu-id="c0cf0-127">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="c0cf0-128">在 [解除委任後](cloud-consolidation-managing-attributes.md)，會說明兩個解除委任方法的詳細資料和折衷。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-128">Details and tradeoffs of the two decommissioning approaches are described in [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span></span>

## <a name="update-dns-to-point-to-microsoft-365"></a><span data-ttu-id="c0cf0-129">將 DNS 更新為指向 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c0cf0-129">Update DNS to point to Microsoft 365</span></span>

<span data-ttu-id="c0cf0-130">組織的外部 DNS 必須更新內部部署組織，使商務用 Skype 記錄指向 Microsoft 365 而非內部部署。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-130">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 instead of the on-premises deployment.</span></span> 

<span data-ttu-id="c0cf0-131">此外，如果存在) 可刪除，則為符合或撥入 (的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-131">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="c0cf0-132">最後，您應該移除內部網路中商務用 Skype 的任何 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-132">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

<span data-ttu-id="c0cf0-133">如需更新 dns 記錄的詳細資訊，請參閱[更新 dns 專案，讓您的組織全部 Teams](decommission-manage-dns-entries.md)。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-133">For details about updating DNS records, see [Update DNS entries to enable your organization to be all Teams Only](decommission-manage-dns-entries.md).</span></span>

## <a name="change-the-coexistence-mode-for-your-organization-to-teams-only"></a><span data-ttu-id="c0cf0-134">將貴組織的共存模式變更為僅 Teams</span><span class="sxs-lookup"><span data-stu-id="c0cf0-134">Change the coexistence mode for your organization to Teams Only</span></span>

<span data-ttu-id="c0cf0-135">此步驟可確保您組織中的任何新使用者永遠都建立為僅 Teams 使用者。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-135">This step ensures that any new user in your organization is always created as a Teams Only user.</span></span> 

<span data-ttu-id="c0cf0-136">嘗試將租使用者模式變更為 Teams，只會自動檢查是否存在步驟1中已錯過的任何內部部署 DNS 記錄，並在輸出中識別這些記錄。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-136">Attempting to change the tenant mode to Teams Only will automatically check for existence of any on-premises DNS records that may have been missed in step 1 and identify these records in the output.</span></span> <span data-ttu-id="c0cf0-137">只有在更新組織的所有 DNS 記錄後，才能將租使用者模式變更為 Teams 才會失敗。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-137">Changing the tenant mode to Teams Only will not succeed until all DNS records for your organization are updated.</span></span> 

<span data-ttu-id="c0cf0-138">若要將租使用者模式變更為 Teams 只從 Teams PowerShell] 視窗執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-138">To change the tenant mode to Teams Only run the following command from a Teams PowerShell window.</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
```

<span data-ttu-id="c0cf0-139">或者，您也可以使用 Teams 系統管理中心，將租使用者共存模式變更為 TeamsOnly，在 [整個組織設定] 下，> "Teams Upgrade]。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-139">Alternatively, you can use the Teams Admin Center to change the tenant coexistence mode to TeamsOnly, under "Org-wide settings" -> "Teams Upgrade."</span></span>    

## <a name="disable-shared-sip-address-space-in-microsoft-365-organization"></a><span data-ttu-id="c0cf0-140">停用 Microsoft 365 組織中的共用 sip 位址空間</span><span class="sxs-lookup"><span data-stu-id="c0cf0-140">Disable shared sip address space in Microsoft 365 organization</span></span>
    
<span data-ttu-id="c0cf0-141">若要停用共用 sip 位址空間，請從 Teams PowerShell] 視窗中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="c0cf0-141">To disable shared sip address space, run the following command from a Teams PowerShell window.</span></span>

```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
```
 
## <a name="disable-communication-between-on-premises-and-microsoft-365"></a><span data-ttu-id="c0cf0-142">停用內部部署與 Microsoft 365 之間的通訊</span><span class="sxs-lookup"><span data-stu-id="c0cf0-142">Disable communication between on-premises and Microsoft 365</span></span>

<span data-ttu-id="c0cf0-143">若要停用內部部署環境與 Microsoft 365 之間的通訊，請從內部部署 PowerShell 視窗執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c0cf0-143">To disable communication between the on-premises environment and Microsoft 365, run the following command from an on-premises PowerShell window:</span></span>

```PowerShell
Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```


## <a name="see-also"></a><span data-ttu-id="c0cf0-144">請參閱</span><span class="sxs-lookup"><span data-stu-id="c0cf0-144">See also</span></span>

- [<span data-ttu-id="c0cf0-145">Teams 與商務用 Skype 的雲整合</span><span class="sxs-lookup"><span data-stu-id="c0cf0-145">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="c0cf0-146">解除您的內部部署商務用 Skype 環境</span><span class="sxs-lookup"><span data-stu-id="c0cf0-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)


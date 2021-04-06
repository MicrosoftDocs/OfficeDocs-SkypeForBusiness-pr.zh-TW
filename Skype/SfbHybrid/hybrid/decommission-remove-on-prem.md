---
title: 解除委任商務用 Skype Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 解除委任商務用 Skype 伺服器的指示。
ms.openlocfilehash: 668e3d5ebf5dfa03fcfb883adcc3e08fc5924bae
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593877"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="86ff7-103">移除您的內部部署商務用 Skype 部署</span><span class="sxs-lookup"><span data-stu-id="86ff7-103">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="86ff7-104">本文說明如何移除您的內部部署商務用 Skype 部署。</span><span class="sxs-lookup"><span data-stu-id="86ff7-104">This article describes how to remove your on-premises Skype for Business deployment.</span></span> <span data-ttu-id="86ff7-105">這是將您的內部部署環境解除委任之下列步驟的步驟3：</span><span class="sxs-lookup"><span data-stu-id="86ff7-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="86ff7-106">步驟 1.</span><span class="sxs-lookup"><span data-stu-id="86ff7-106">Step 1.</span></span> <span data-ttu-id="86ff7-107">[將所有需要的使用者和應用程式端點從內部部署移至線上](decommission-move-on-prem-users.md)。</span><span class="sxs-lookup"><span data-stu-id="86ff7-107">[Move all required users and application endpoints from on-premises to online](decommission-move-on-prem-users.md).</span></span> 

- <span data-ttu-id="86ff7-108">步驟 2.</span><span class="sxs-lookup"><span data-stu-id="86ff7-108">Step 2.</span></span> <span data-ttu-id="86ff7-109">[停用您的混合](cloud-consolidation-disabling-hybrid.md)式設定。</span><span class="sxs-lookup"><span data-stu-id="86ff7-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="86ff7-110">**步驟3。移除您的內部部署商務用 Skype 部署。**</span><span class="sxs-lookup"><span data-stu-id="86ff7-110">**Step 3. Remove your on-premises Skype for Business deployment.**</span></span> <span data-ttu-id="86ff7-111"> (本文) </span><span class="sxs-lookup"><span data-stu-id="86ff7-111">(This article)</span></span>


> [!IMPORTANT] 
> <span data-ttu-id="86ff7-112">本文中的步驟僅適用于使用方法2管理使用者屬性時[，如下所述。](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory)</span><span class="sxs-lookup"><span data-stu-id="86ff7-112">The steps in this article apply only if you are using Method 2 for managing user attributes, as described [here](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span></span> <span data-ttu-id="86ff7-113">如果您使用方法1，請勿使用本文所述的步驟來移除您的商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="86ff7-113">If you are using Method 1, do not use the steps described in this article to remove your Skype for Business servers.</span></span> <span data-ttu-id="86ff7-114">相反地，您可以重新鏡像伺服器。</span><span class="sxs-lookup"><span data-stu-id="86ff7-114">Instead, you can re-image the servers.</span></span>

<span data-ttu-id="86ff7-115">若要完成本文中的步驟，您需要具備 Schema Admins 群組和 Enterprise Admin 群組的許可權。</span><span class="sxs-lookup"><span data-stu-id="86ff7-115">To complete the steps in this article, you need privileges for both the Schema Admins group and the Enterprise Admin group.</span></span> <span data-ttu-id="86ff7-116">您將需要這些許可權，才能撤銷 Active Directory 網域服務的商務用 Skype 伺服器架構和樹系層級變更。</span><span class="sxs-lookup"><span data-stu-id="86ff7-116">You will need these privileges to undo the Skype for Business Server schema and forest-level changes to Active Directory Domain Services.</span></span> <span data-ttu-id="86ff7-117">您也必須是 RTCUniversalServerAdmins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="86ff7-117">You will also need to be a member of the RTCUniversalServerAdmins group.</span></span>


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a><span data-ttu-id="86ff7-118">準備移除商務用 Skype 部署</span><span class="sxs-lookup"><span data-stu-id="86ff7-118">Prepare to remove the Skype for Business deployment</span></span>

<span data-ttu-id="86ff7-119">將所有必要的使用者帳戶移至雲端後，可能仍然會有一些其他的內部部署物件，例如您將需要清理的連絡人和應用程式。</span><span class="sxs-lookup"><span data-stu-id="86ff7-119">After you move all required user accounts to the cloud, there may still be some remaining on-premises objects such as contacts and applications that you will need clean up.</span></span>

<span data-ttu-id="86ff7-120">使用下列步驟來清除這些物件，並確定您同時是本機系統管理員群組和 RTCUniversalServerAdmins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="86ff7-120">Use the steps below to clean these objects, and make sure you are a member of both the Local Administrator group and the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="86ff7-121">請注意，商務用 Skype Server 2019 中無法使用 ExUmContacts 和 PersistantChatEndPoints。</span><span class="sxs-lookup"><span data-stu-id="86ff7-121">Note that ExUmContacts and PersistantChatEndPoints are not available in Skype for Business Server 2019.</span></span> <span data-ttu-id="86ff7-122">如果您有商務用 Skype Server 2019，應省略下列步驟中的對應 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="86ff7-122">If you have Skype for Business Server 2019, the corresponding cmdlets in the steps below should be omitted.</span></span>

1. <span data-ttu-id="86ff7-123">若要檢查是否有任何與商務用 Skype Server 內部部署相關聯的連絡人或應用程式，請執行下列商務用 Skype Server PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="86ff7-123">To check if there are any contacts or applications associated with the Skype for Business Server on-premises deployment, run the following Skype for Business Server PowerShell cmdlets.</span></span>

   ```PowerShell
   Get-CsMeetingRoom
   Get-CsCommonAreaPhone
   Get-CsAnalogDevice
   Get-CsExUmContact
   Get-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication
   Get-CsPersistentChatEndpoint
   Get-CsAudioTestServiceApplication
   Get-CsCallParkOrbit
   ```
2. <span data-ttu-id="86ff7-124">從步驟1中的 Cmdlet 複查輸出清單。</span><span class="sxs-lookup"><span data-stu-id="86ff7-124">Review the output lists from the cmdlets in Step 1.</span></span> <span data-ttu-id="86ff7-125">然後，如果可以移除物件，請執行下列商務用 Skype Server PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="86ff7-125">Then if objects can be removed, run the following Skype for Business Server PowerShell cmdlets:</span></span>

   ```PowerShell
   Get-CsMeetingRoom | Disable-CsMeetingRoom
   Get-CsCommonAreaPhone | Remove-CsCommonAreaPhone 
   Get-CsAnalogDevice | Remove-CsAnalogDevice
   Get-CsExUmContact | Remove-CsExUmContact
   Get-CsDialInConferencingAccessNumber | Remove-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow | Remove-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint | Remove-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication | Remove-CsTrustedApplication -Force
   Get-CsPersistentChatEndpoint |  Remove-CsPersistentChatEndpoint
   Get-CsCallParkOrbit | Remove-CsCallParkOrbit -Force
   Get-CsVoiceRoute | Remove-CsVoiceRoute -Force
   ```
## <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="86ff7-126">移除您的內部部署商務用 Skype 部署</span><span class="sxs-lookup"><span data-stu-id="86ff7-126">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="86ff7-127">完成所有初步步驟之後，您可以遵循下列步驟移除商務用 Skype 部署：</span><span class="sxs-lookup"><span data-stu-id="86ff7-127">After completing all the preliminary steps, you can remove the Skype for Business deployment by following these steps:</span></span>

1. <span data-ttu-id="86ff7-128">從邏輯上移除商務用 Skype Server 部署，但單一前端除外，如下所示：</span><span class="sxs-lookup"><span data-stu-id="86ff7-128">Logically remove the Skype for Business Server deployment, except for a single front end, as follows:</span></span>

   <span data-ttu-id="86ff7-129">a.</span><span class="sxs-lookup"><span data-stu-id="86ff7-129">a.</span></span> <span data-ttu-id="86ff7-130">更新商務用 Skype 伺服器拓撲，使其具備單一前端集區：</span><span class="sxs-lookup"><span data-stu-id="86ff7-130">Update your Skype for Business Server topology to have a single front-end pool:</span></span>

     - <span data-ttu-id="86ff7-131">在 [拓撲產生器] 中，下載新的複本並流覽至前端集區。</span><span class="sxs-lookup"><span data-stu-id="86ff7-131">In Topology Builder, download a new copy and navigate to the Frontend pool.</span></span>
     - <span data-ttu-id="86ff7-132">以滑鼠右鍵按一下集區，然後按一下 [編輯屬性]。</span><span class="sxs-lookup"><span data-stu-id="86ff7-132">Right-click the pool, and then click **Edit Properties**.</span></span>
     - <span data-ttu-id="86ff7-133">在 [ **關聯**] 中，取消選取媒體元件的 [ **建立 Edge 集** 區 (]) 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="86ff7-133">In **Associations**, uncheck **Associate Edge Pool** (for media components) and click **OK**.</span></span>
     - <span data-ttu-id="86ff7-134">如果有一個以上的前端集區，請移除所有剩餘集區的關聯。</span><span class="sxs-lookup"><span data-stu-id="86ff7-134">If there is more than one Frontend Pool, remove Associations for all remaining pools.</span></span>
     - <span data-ttu-id="86ff7-135">選取 [ **動作] > [移除部署**]。</span><span class="sxs-lookup"><span data-stu-id="86ff7-135">Select **Action > Remove Deployment**.</span></span>
     - <span data-ttu-id="86ff7-136">選取 [ **動作] > [發行拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="86ff7-136">Select **Action > Publish Topology**.</span></span>

    <span data-ttu-id="86ff7-137">b.</span><span class="sxs-lookup"><span data-stu-id="86ff7-137">b.</span></span> <span data-ttu-id="86ff7-138">發行拓撲之後，請完成嚮導中所述的其他步驟。</span><span class="sxs-lookup"><span data-stu-id="86ff7-138">After publishing the topology, complete the additional steps described in the wizard.</span></span>

2. <span data-ttu-id="86ff7-139">執行下列商務用 Skype Server PowerShell Cmdlet，以移除商務用 Skype Server 會議目錄：</span><span class="sxs-lookup"><span data-stu-id="86ff7-139">Remove Skype for Business Server conference directories by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. <span data-ttu-id="86ff7-140">執行下列商務用 Skype Server PowerShell Cmdlet，以完成您的商務用 Skype 伺服器部署的卸載：</span><span class="sxs-lookup"><span data-stu-id="86ff7-140">Finalize the uninstall of your Skype for Business Server deployment by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > <span data-ttu-id="86ff7-141">如果此步驟傳回錯誤，請開啟 Microsoft 支援票證以取得刪除剩餘的陳舊物件的說明。</span><span class="sxs-lookup"><span data-stu-id="86ff7-141">If this step returns an error, please open a Microsoft support ticket to get help removing the remaining stale objects.</span></span>

4. <span data-ttu-id="86ff7-142">執行下列商務用 Skype Server PowerShell Cmdlet 來移除中央管理存放區服務控制點：</span><span class="sxs-lookup"><span data-stu-id="86ff7-142">Remove Central Management Store Service Control Point by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. <span data-ttu-id="86ff7-143">執行下列商務用 Skype Server PowerShell Cmdlet，以復原商務用 Skype Server Active Directory 網域樹系層級變更：</span><span class="sxs-lookup"><span data-stu-id="86ff7-143">Undo Skype for Business Server Active Directory Domain forest-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdDomain
   ```
6. <span data-ttu-id="86ff7-144">執行下列商務用 Skype Server PowerShell Cmdlet，以復原商務用 Skype Server Active Directory 網域架構變更：</span><span class="sxs-lookup"><span data-stu-id="86ff7-144">Undo Skype for Business Server Active Directory Domain schema changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a><span data-ttu-id="86ff7-145">另請參閱</span><span class="sxs-lookup"><span data-stu-id="86ff7-145">See also</span></span>

- [<span data-ttu-id="86ff7-146">解除委任您的內部部署商務用 Skype 環境</span><span class="sxs-lookup"><span data-stu-id="86ff7-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="86ff7-147">將使用者和端點移至雲端</span><span class="sxs-lookup"><span data-stu-id="86ff7-147">Move user and endpoints to the cloud</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="86ff7-148">停用混合式設定</span><span class="sxs-lookup"><span data-stu-id="86ff7-148">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)















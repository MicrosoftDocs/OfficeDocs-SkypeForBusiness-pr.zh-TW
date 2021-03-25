---
title: 在商務用 Skype Server 中刪除現有的 SIP 主幹設定設定集合
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 摘要：瞭解如何使用商務用 Skype Server 控制台刪除主幹設定設定的集合。
ms.openlocfilehash: 8ea3ef931c8e09a235adc816cd993468d7d79b47
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111849"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="91ed7-103">在商務用 Skype Server 中刪除現有的 SIP 主幹設定設定集合</span><span class="sxs-lookup"><span data-stu-id="91ed7-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="91ed7-104">**摘要：** 瞭解如何使用商務用 Skype Server 控制台刪除主幹設定設定的集合。</span><span class="sxs-lookup"><span data-stu-id="91ed7-104">**Summary:** Learn how to delete a collection of trunk configuration settings by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="91ed7-105">SIP 主幹設定設定定義轉送伺服器和公用交換電話網路 (PSTN) 閘道、IP-Public 分支 eXchange (PBX) 或會話邊界控制器（在服務提供者上 (SBC) ）之間的關聯性和功能。</span><span class="sxs-lookup"><span data-stu-id="91ed7-105">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="91ed7-106">這些設定將指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="91ed7-106">These settings do such things as specify:</span></span>
  
- <span data-ttu-id="91ed7-107">主幹是否啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="91ed7-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="91ed7-108">在哪個條件下會傳送即時傳輸控制通訊協定 (RTCP) 封包。</span><span class="sxs-lookup"><span data-stu-id="91ed7-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="91ed7-109">在每個主幹上是否需要 (SRTP) 加密的安全即時傳輸通訊協定。</span><span class="sxs-lookup"><span data-stu-id="91ed7-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="91ed7-110">當您安裝商務用 Skype Server 時，系統會為您建立一個全域 SIP 主幹設定的集合。</span><span class="sxs-lookup"><span data-stu-id="91ed7-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="91ed7-111">此設定的全域集合無法刪除。</span><span class="sxs-lookup"><span data-stu-id="91ed7-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="91ed7-112">不過，您可以使用商務用 Skype Server 控制台或 [get-cstrunkconfiguration](/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) Cmdlet，將全域集合中的屬性「重設」為其預設值。</span><span class="sxs-lookup"><span data-stu-id="91ed7-112">However, you can use the Skype for Business Server Control Panel or the [Remove-CsTrunkConfiguration](/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="91ed7-113">例如，如果已將 Enable3pccRefer 屬性設為 True，則在重設全域集合時，Enable3pccRefer 屬性會還原為預設值 False。</span><span class="sxs-lookup"><span data-stu-id="91ed7-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>
  
<span data-ttu-id="91ed7-p103">管理員也可建立網站範圍或服務範圍 (針對個別 PSTN 閘道) 的自訂主幹組態設定；這些自訂設定是可移除的。移除這些自訂設定時，請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="91ed7-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>
  
- <span data-ttu-id="91ed7-p104">如移除服務範圍設定，原先這些設定所管理的 SIP 主幹會由套用網站的設定來管理 (如果存在的話)。如果網站設定不存在，這些主幹將會由主幹組態設定的全域集合來管理。</span><span class="sxs-lookup"><span data-stu-id="91ed7-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
    
- <span data-ttu-id="91ed7-118">如移除網站範圍設定，則所有原先這些設定管理的 SIP 主幹將會由主幹組態設定的全域集合來管理。</span><span class="sxs-lookup"><span data-stu-id="91ed7-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="91ed7-119">使用商務用 Skype Server 控制台移除主幹設定設定</span><span class="sxs-lookup"><span data-stu-id="91ed7-119">To remove trunk configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="91ed7-120">在商務用 Skype Server 控制台中，按一下 [ **語音路由** ]，然後按一下 [ **主幹** 設定]。</span><span class="sxs-lookup"><span data-stu-id="91ed7-120">In Skype for Business Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>
    
2. <span data-ttu-id="91ed7-p105">在 **[主幹組態]** 索引標籤中，選取要刪除的 SIP 主幹組態設定集合，然後按一下 **[編輯]**，再按一下 **[刪除]**。如要在同一個操作中刪除多個集合，先按一下要刪除的第一個集合，然後按住 Ctrl 鍵，再按一下其他任何要移除的集合。</span><span class="sxs-lookup"><span data-stu-id="91ed7-p105">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**. To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
    
3. <span data-ttu-id="91ed7-p106">集合的 **[狀態]** 屬性將會更新為 **[未認可]**。如要認可變更並刪除集合，請按一下 **[認可]**，然後按一下 **[全部認可]**。</span><span class="sxs-lookup"><span data-stu-id="91ed7-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
    
4. <span data-ttu-id="91ed7-125">在 **[未認可的語音組態設定]** 對話方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="91ed7-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
    
5. <span data-ttu-id="91ed7-126">在 [ **商務用 Skype 伺服器控制台** ] 對話方塊中，按一下 **[確定**]。</span><span class="sxs-lookup"><span data-stu-id="91ed7-126">In the **Skype for Business Server Control Panel** dialog box click **OK**.</span></span>
    
6. <span data-ttu-id="91ed7-127">如果您改變心意決定不要刪除集合，請按一下 **[認可]**，然後按一下 **[取消所有未認可的變更]**。</span><span class="sxs-lookup"><span data-stu-id="91ed7-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="91ed7-128">當 [ **商務用 Skype Server 控制台** ] 對話方塊出現時，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="91ed7-128">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="91ed7-129">使用商務用 Skype Server 管理命令介面 Cmdlet 移除主幹設定設定</span><span class="sxs-lookup"><span data-stu-id="91ed7-129">Removing Trunk Configuration Settings by Using Skype for Business Server Management Shell Cmdlets</span></span>

<span data-ttu-id="91ed7-130">您可以使用商務用 Skype Server 管理命令介面和 **get-cstrunkconfiguration** Cmdlet 來刪除主幹設定設定。</span><span class="sxs-lookup"><span data-stu-id="91ed7-130">You can delete trunk configuration settings by using Skype for Business Server Management Shell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="91ed7-131">您可以從商務用 Skype Server 管理命令介面或從商務用 Skype Server 管理命令介面的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="91ed7-131">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="91ed7-132">移除指定的設定集合</span><span class="sxs-lookup"><span data-stu-id="91ed7-132">To remove a specified collection of settings</span></span>

- <span data-ttu-id="91ed7-133">以下命令會移除已套用至 Redmond 網站的主幹組態設定：</span><span class="sxs-lookup"><span data-stu-id="91ed7-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="91ed7-134">若要移除所有套用至網站範圍的集合</span><span class="sxs-lookup"><span data-stu-id="91ed7-134">To remove all the collections applied to the site scope</span></span>

- <span data-ttu-id="91ed7-135">以下命令會移除所有已套用至服務範圍的主幹組態設定：</span><span class="sxs-lookup"><span data-stu-id="91ed7-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="91ed7-136">移除啟用媒體旁路的所有集合</span><span class="sxs-lookup"><span data-stu-id="91ed7-136">To remove all the collections where media bypass is enabled</span></span>

- <span data-ttu-id="91ed7-137">以下命令會移除所有已啟用媒體旁路的主幹組態設定：</span><span class="sxs-lookup"><span data-stu-id="91ed7-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

<span data-ttu-id="91ed7-138">如需詳細資訊，請參閱 [get-cstrunkconfiguration](/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="91ed7-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span>

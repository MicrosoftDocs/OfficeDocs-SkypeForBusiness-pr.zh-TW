---
title: 刪除現有的 SIP 主幹組態設定 skype for Business Server 集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'SIP 主幹組態設定用於定義中繼伺服器與服務提供者的公用交換電話網路 (PSTN) 閘道、IP 公用交換機 (PBX) 或工作階段邊界控制器 (SBC) 之間的關係和功能。 '
ms.openlocfilehash: 09f5e7fda03c5e0e5221661f87482b67192ce302
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045055"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="4fac4-103">刪除現有的 SIP 主幹組態設定 skype for Business Server 集合</span><span class="sxs-lookup"><span data-stu-id="4fac4-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="4fac4-p101">SIP 主幹組態設定用於定義中繼伺服器與服務提供者的公用交換電話網路 (PSTN) 閘道、IP 公用交換機 (PBX) 或工作階段邊界控制器 (SBC) 之間的關係和功能。這些設定將指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="4fac4-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

- <span data-ttu-id="4fac4-106">主幹是否啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="4fac4-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="4fac4-107">傳送即時傳輸控制通訊協定 (RTCP) 封包的情況。</span><span class="sxs-lookup"><span data-stu-id="4fac4-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="4fac4-108">每個主幹是否需要安全即時通訊協定 (SRTP) 加密。</span><span class="sxs-lookup"><span data-stu-id="4fac4-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="4fac4-109">當您安裝 Skype for Business Server 時，為您建立的 SIP 主幹組態設定全域集合。</span><span class="sxs-lookup"><span data-stu-id="4fac4-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="4fac4-110">此設定的全域集合無法刪除。</span><span class="sxs-lookup"><span data-stu-id="4fac4-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="4fac4-111">不過，您可以使用商務用 Skype 商務 ServerControl 面板或[Remove-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet 」 重設 」 為其預設值的全域集合中的屬性。</span><span class="sxs-lookup"><span data-stu-id="4fac4-111">However, you can use the Skype for Business ServerControl Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="4fac4-112">例如，如果已將 Enable3pccRefer 屬性設為 True，則在重設全域集合時，Enable3pccRefer 屬性會還原為預設值 False。</span><span class="sxs-lookup"><span data-stu-id="4fac4-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="4fac4-p103">管理員也可建立網站範圍或服務範圍 (針對個別 PSTN 閘道) 的自訂主幹組態設定；這些自訂設定是可移除的。移除這些自訂設定時，請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="4fac4-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>

- <span data-ttu-id="4fac4-p104">如移除服務範圍設定，原先這些設定所管理的 SIP 主幹會由套用網站的設定來管理 (如果存在的話)。如果網站設定不存在，這些主幹將會由主幹組態設定的全域集合來管理。</span><span class="sxs-lookup"><span data-stu-id="4fac4-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
- <span data-ttu-id="4fac4-117">如移除網站範圍設定，則所有原先這些設定管理的 SIP 主幹將會由主幹組態設定的全域集合來管理。</span><span class="sxs-lookup"><span data-stu-id="4fac4-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<span data-ttu-id="4fac4-118">**若要移除主幹組態設定與 Skype for Business Server Control Panel**</span><span class="sxs-lookup"><span data-stu-id="4fac4-118">**To remove trunk configuration settings with the Skype for Business Server Control Panel**</span></span> 

1. <span data-ttu-id="4fac4-119">Skype for Business Server Control Panel 中，按一下 [**語音路由**]，然後按一下 [**主幹組態**。</span><span class="sxs-lookup"><span data-stu-id="4fac4-119">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="4fac4-120">[**主幹組態**] 索引標籤中，選取要刪除，按一下 [**編輯**]，然後按一下 [**刪除**的 SIP 主幹組態設定的集合。</span><span class="sxs-lookup"><span data-stu-id="4fac4-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit**, and then click **Delete**.</span></span> <span data-ttu-id="4fac4-121">如要在同一個操作中刪除多個集合，先按一下要刪除的第一個集合，然後按住 Ctrl 鍵，再按一下其他任何要移除的集合。</span><span class="sxs-lookup"><span data-stu-id="4fac4-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
3. <span data-ttu-id="4fac4-p106">集合的 **[狀態]** 屬性將會更新為 **[未認可]**。如要認可變更並刪除集合，請按一下 **[認可]**，然後按一下 **[全部認可]**。</span><span class="sxs-lookup"><span data-stu-id="4fac4-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
4. <span data-ttu-id="4fac4-124">在 **[未認可的語音組態設定]** 對話方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="4fac4-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
5. <span data-ttu-id="4fac4-125">**Skype for Business Server Control Panel** ] 對話方塊中，按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="4fac4-125">In the **Skype for Business Server Control Panel** dialog box, click **OK**.</span></span>
6. <span data-ttu-id="4fac4-126">如果您改變心意，並決定不要刪除集合，按一下 [**認可**]，然後再按一下 [**取消所有未認可的變更**。</span><span class="sxs-lookup"><span data-stu-id="4fac4-126">If you change your mind and decide not to delete the collection, click **Commit**, and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="4fac4-127">**Skype for Business Server Control Panel** ] 對話方塊出現時，按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="4fac4-127">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4fac4-128">使用 Windows PowerShell cmdlet 移除主幹組態設定</span><span class="sxs-lookup"><span data-stu-id="4fac4-128">Removing trunk configuration settings by using Windows PowerShell cmdlets</span></span>


<span data-ttu-id="4fac4-129">您可以使用 Windows PowerShell 和**Remove-cstrunkconfiguration** cmdlet 來刪除主幹組態設定。</span><span class="sxs-lookup"><span data-stu-id="4fac4-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="4fac4-130">您可以執行此 cmdlet 可能是來自 Skype for Business Server 管理命令介面或從 Windows PowerShell 的遠端工作階段。</span><span class="sxs-lookup"><span data-stu-id="4fac4-130">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="4fac4-131">**若要移除指定的設定集合**</span><span class="sxs-lookup"><span data-stu-id="4fac4-131">**To remove a specified collection of settings**</span></span>

<span data-ttu-id="4fac4-132">以下命令會移除已套用至 Redmond 網站的主幹組態設定：</span><span class="sxs-lookup"><span data-stu-id="4fac4-132">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>

`Remove-CsTrunkConfiguration -Identity site:Redmond`

<span data-ttu-id="4fac4-133">**若要移除所有套用至網站範圍的集合**</span><span class="sxs-lookup"><span data-stu-id="4fac4-133">**To remove all the collections applied to the site scope**</span></span>

<span data-ttu-id="4fac4-134">以下命令會移除所有已套用至服務範圍的主幹組態設定：</span><span class="sxs-lookup"><span data-stu-id="4fac4-134">This command removes all the trunk configuration settings applied to the service scope:</span></span>

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

<span data-ttu-id="4fac4-135">**若要移除所有媒體旁路的集合是已啟用**</span><span class="sxs-lookup"><span data-stu-id="4fac4-135">**To remove all the collections where media bypass is enabled**</span></span>

<span data-ttu-id="4fac4-136">以下命令會移除所有已啟用媒體旁路的主幹組態設定：</span><span class="sxs-lookup"><span data-stu-id="4fac4-136">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

<span data-ttu-id="4fac4-137">如需詳細資訊，請參閱[Remove-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="4fac4-137">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet.</span></span>

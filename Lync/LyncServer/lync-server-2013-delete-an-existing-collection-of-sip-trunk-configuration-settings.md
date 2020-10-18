---
title: 刪除現有的 SIP 主幹配置設定集合
description: 刪除現有的 SIP 主幹設定的集合。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of SIP trunk configuration settings
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49733614
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98acede458d34eb30202d898414b2e17076d32d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572819"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="a86a0-103">在 Lync Server 2013 中刪除現有的 SIP 主幹設定的集合</span><span class="sxs-lookup"><span data-stu-id="a86a0-103">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a86a0-104">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="a86a0-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="a86a0-p101">SIP 主幹組態設定用於定義中繼伺服器與服務提供者的公用交換電話網路 (PSTN) 閘道、IP 公用交換機 (PBX) 或工作階段邊界控制器 (SBC) 之間的關係和功能。這些設定將指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="a86a0-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="a86a0-107">主幹是否啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="a86a0-107">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="a86a0-108">傳送即時傳輸控制通訊協定 (RTCP) 封包的情況。</span><span class="sxs-lookup"><span data-stu-id="a86a0-108">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="a86a0-109">每個主幹是否需要安全即時通訊協定 (SRTP) 加密。</span><span class="sxs-lookup"><span data-stu-id="a86a0-109">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="a86a0-110">當您安裝 Microsoft Lync Server 2013 時，系統會為您建立一個全域 SIP 主幹設定的集合。</span><span class="sxs-lookup"><span data-stu-id="a86a0-110">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="a86a0-111">此設定的全域集合無法刪除。</span><span class="sxs-lookup"><span data-stu-id="a86a0-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="a86a0-112">不過，您可以使用 Lync Server 控制台或 [get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) Cmdlet，將全域集合中的屬性「重設」為其預設值。</span><span class="sxs-lookup"><span data-stu-id="a86a0-112">However, you can use the Lync Server Control Panel or the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="a86a0-113">例如，如果已將 Enable3pccRefer 屬性設為 True，則在重設全域集合時，Enable3pccRefer 屬性會還原為預設值 False。</span><span class="sxs-lookup"><span data-stu-id="a86a0-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="a86a0-p103">管理員也可建立網站範圍或服務範圍 (針對個別 PSTN 閘道) 的自訂主幹組態設定；這些自訂設定是可移除的。移除這些自訂設定時，請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="a86a0-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>

  - <span data-ttu-id="a86a0-p104">如移除服務範圍設定，原先這些設定所管理的 SIP 主幹會由套用網站的設定來管理 (如果存在的話)。如果網站設定不存在，這些主幹將會由主幹組態設定的全域集合來管理。</span><span class="sxs-lookup"><span data-stu-id="a86a0-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>

  - <span data-ttu-id="a86a0-118">如移除網站範圍設定，則所有原先這些設定管理的 SIP 主幹將會由主幹組態設定的全域集合來管理。</span><span class="sxs-lookup"><span data-stu-id="a86a0-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="a86a0-119">使用 Lync Server 控制台移除主幹設定設定</span><span class="sxs-lookup"><span data-stu-id="a86a0-119">To remove trunk configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a86a0-120">在 [Lync Server 控制台] 中，按一下 [ **語音路由** ]，然後按一下 [ **主幹**設定]。</span><span class="sxs-lookup"><span data-stu-id="a86a0-120">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="a86a0-p105">在 **[主幹組態]** 索引標籤中，選取要刪除的 SIP 主幹組態設定集合，然後按一下 **[編輯]**，再按一下 **[刪除]**。如要在同一個操作中刪除多個集合，先按一下要刪除的第一個集合，然後按住 Ctrl 鍵，再按一下其他任何要移除的集合。</span><span class="sxs-lookup"><span data-stu-id="a86a0-p105">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**. To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>

3.  <span data-ttu-id="a86a0-p106">集合的 **[狀態]** 屬性將會更新為 **[未認可]**。如要認可變更並刪除集合，請按一下 **[認可]**，然後按一下 **[全部認可]**。</span><span class="sxs-lookup"><span data-stu-id="a86a0-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

4.  <span data-ttu-id="a86a0-125">在 **[未認可的語音組態設定]** 對話方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a86a0-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

5.  <span data-ttu-id="a86a0-126">在 **[Microsoft Lync Server 2013 控制台]** 對話方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a86a0-126">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

6.  <span data-ttu-id="a86a0-p107">如果您改變心意決定不要刪除集合，請按一下 **[認可]**，然後按一下 **[取消所有未認可的變更]**。在顯示 **[Microsoft Lync Server 2013 控制台]** 對話方塊時，按一下 **[確認]**。</span><span class="sxs-lookup"><span data-stu-id="a86a0-p107">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**. When the **Microsoft Lync Server 2013 Control Panel** dialog box appears, click **OK**.</span></span>

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a86a0-129">使用 Windows PowerShell Cmdlet 移除主幹設定設定</span><span class="sxs-lookup"><span data-stu-id="a86a0-129">Removing Trunk Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a86a0-130">您可以使用 Windows PowerShell 和 **get-cstrunkconfiguration** Cmdlet 來刪除主幹設定設定。</span><span class="sxs-lookup"><span data-stu-id="a86a0-130">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="a86a0-131">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a86a0-131">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a86a0-132">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="a86a0-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="a86a0-133">移除指定的設定集合</span><span class="sxs-lookup"><span data-stu-id="a86a0-133">To remove a specified collection of settings</span></span>

  - <span data-ttu-id="a86a0-134">以下命令會移除已套用至 Redmond 網站的主幹組態設定：</span><span class="sxs-lookup"><span data-stu-id="a86a0-134">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="a86a0-135">若要移除所有套用至網站範圍的集合</span><span class="sxs-lookup"><span data-stu-id="a86a0-135">To remove all the collections applied to the site scope</span></span>

  - <span data-ttu-id="a86a0-136">以下命令會移除所有已套用至服務範圍的主幹組態設定：</span><span class="sxs-lookup"><span data-stu-id="a86a0-136">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="a86a0-137">移除啟用媒體旁路的所有集合</span><span class="sxs-lookup"><span data-stu-id="a86a0-137">To remove all the collections where media bypass is enabled</span></span>

  - <span data-ttu-id="a86a0-138">以下命令會移除所有已啟用媒體旁路的主幹組態設定：</span><span class="sxs-lookup"><span data-stu-id="a86a0-138">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

<span data-ttu-id="a86a0-139">如需詳細資訊，請參閱 [get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="a86a0-139">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


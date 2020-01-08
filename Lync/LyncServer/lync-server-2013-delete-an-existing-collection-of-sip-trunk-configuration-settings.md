---
title: 刪除現有的 SIP 幹線配置設定集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of SIP trunk configuration settings
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49733614
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b896d53760184d15b02afed14b8a9c0d660f96b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="1b49c-102">刪除 Lync Server 2013 中現有的 SIP 幹線配置設定集合</span><span class="sxs-lookup"><span data-stu-id="1b49c-102">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b49c-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="1b49c-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="1b49c-104">SIP 幹線設定設定會定義在服務提供者上，exchange 中繼伺服器與公用交換式電話網絡（PSTN）閘道、IP 公用分支 exchange （PBX）或會話邊界控制器（SBC）之間的關聯性與能力。</span><span class="sxs-lookup"><span data-stu-id="1b49c-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="1b49c-105">這些設定會以指定的方式執行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1b49c-105">These settings do such things as specify:</span></span>

  - <span data-ttu-id="1b49c-106">是否應該在 trunks 上啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="1b49c-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="1b49c-107">傳送即時傳輸控制通訊協定（RTCP）資料包的條件。</span><span class="sxs-lookup"><span data-stu-id="1b49c-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="1b49c-108">每個幹線是否都需要安全的即時通訊協定（SRTP）加密。</span><span class="sxs-lookup"><span data-stu-id="1b49c-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="1b49c-109">當您安裝 Microsoft Lync Server 2013 時，系統會為您建立一個全域 SIP 幹線配置設定。</span><span class="sxs-lookup"><span data-stu-id="1b49c-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="1b49c-110">這個全域設定集合無法刪除。</span><span class="sxs-lookup"><span data-stu-id="1b49c-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="1b49c-111">不過，您可以使用 Lync Server [控制台] 或 [[移除-new-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) ] Cmdlet，將全域集合中的屬性「重設」為預設值。</span><span class="sxs-lookup"><span data-stu-id="1b49c-111">However, you can use the Lync Server Control Panel or the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="1b49c-112">例如，如果您已將 Enable3pccRefer 屬性設為 True，當您重設全域集合時，Enable3pccRefer 屬性將會還原為預設值 False。</span><span class="sxs-lookup"><span data-stu-id="1b49c-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="1b49c-113">系統管理員也可以在網站範圍或服務範圍（針對個別 PSTN 閘道）建立自訂主幹設定設定。您可以移除這些自訂設定。</span><span class="sxs-lookup"><span data-stu-id="1b49c-113">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed.</span></span> <span data-ttu-id="1b49c-114">移除這些自訂設定時，請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="1b49c-114">When removing these custom settings keep the following in mind:</span></span>

  - <span data-ttu-id="1b49c-115">如果您移除服務範圍設定，這些設定所管理的 SIP 幹線將由套用至其網站的設定來管理（如果存在的話）。</span><span class="sxs-lookup"><span data-stu-id="1b49c-115">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist.</span></span> <span data-ttu-id="1b49c-116">如果網站設定不存在，這些 trunks 就會受到中繼設定設定的全域集合的管理。</span><span class="sxs-lookup"><span data-stu-id="1b49c-116">If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>

  - <span data-ttu-id="1b49c-117">如果您移除網站範圍的設定，由這些設定所管理的任何 SIP trunks 現在都將由「中繼設定」全域集合來管理。</span><span class="sxs-lookup"><span data-stu-id="1b49c-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="1b49c-118">使用 Lync Server 控制台移除主幹設定設定</span><span class="sxs-lookup"><span data-stu-id="1b49c-118">To remove trunk configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1b49c-119">在 Lync Server [控制台] 中，按一下 [**語音路由**]，然後按一下 [**幹線**設定]。</span><span class="sxs-lookup"><span data-stu-id="1b49c-119">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="1b49c-120">在 [**幹線**設定] 索引標籤上，選取要刪除的 SIP 中繼設定的集合，按一下 [**編輯**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="1b49c-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**.</span></span> <span data-ttu-id="1b49c-121">若要在相同的作業中刪除多個集合，請按一下要刪除的第一個集合，然後按住 Ctrl 鍵並按一下您想要移除的任何其他集合。</span><span class="sxs-lookup"><span data-stu-id="1b49c-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>

3.  <span data-ttu-id="1b49c-122">集合的**State**屬性會更新為**未提交**。</span><span class="sxs-lookup"><span data-stu-id="1b49c-122">The **State** property for the collection will be updated to **Uncommitted**.</span></span> <span data-ttu-id="1b49c-123">若要確認變更，並刪除收藏，請按一下 [**認可**]，然後按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="1b49c-123">To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

4.  <span data-ttu-id="1b49c-124">在 [**未提交的語音設定**] 對話方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1b49c-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

5.  <span data-ttu-id="1b49c-125">在 [ **Microsoft Lync Server 2013 控制台**] 對話方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1b49c-125">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

6.  <span data-ttu-id="1b49c-126">如果您改變主意，並決定不刪除收藏，請按一下 [**認可**]，然後按一下 [**取消所有未提交的變更**]。</span><span class="sxs-lookup"><span data-stu-id="1b49c-126">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="1b49c-127">當 [ **Microsoft Lync Server 2013 控制台**] 對話方塊出現時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1b49c-127">When the **Microsoft Lync Server 2013 Control Panel** dialog box appears, click **OK**.</span></span>

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1b49c-128">使用 Windows PowerShell Cmdlet 移除主幹設定設定</span><span class="sxs-lookup"><span data-stu-id="1b49c-128">Removing Trunk Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1b49c-129">您可以使用 Windows PowerShell 與**Remove new-cstrunkconfiguration** Cmdlet 來刪除主幹設定設定。</span><span class="sxs-lookup"><span data-stu-id="1b49c-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="1b49c-130">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1b49c-130">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1b49c-131">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="1b49c-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="1b49c-132">移除指定的設定集合</span><span class="sxs-lookup"><span data-stu-id="1b49c-132">To remove a specified collection of settings</span></span>

  - <span data-ttu-id="1b49c-133">下列命令會移除套用至雷德蒙網站的幹線設定設定：</span><span class="sxs-lookup"><span data-stu-id="1b49c-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="1b49c-134">若要移除所有套用至網站範圍的集合</span><span class="sxs-lookup"><span data-stu-id="1b49c-134">To remove all the collections applied to the site scope</span></span>

  - <span data-ttu-id="1b49c-135">這個命令會移除所有已套用至服務範圍的中繼設定設定：</span><span class="sxs-lookup"><span data-stu-id="1b49c-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="1b49c-136">若要移除已啟用媒體旁路的所有集合</span><span class="sxs-lookup"><span data-stu-id="1b49c-136">To remove all the collections where media bypass is enabled</span></span>

  - <span data-ttu-id="1b49c-137">下列命令會移除已啟用媒體略過的所有主幹設定設定：</span><span class="sxs-lookup"><span data-stu-id="1b49c-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

<span data-ttu-id="1b49c-138">如需詳細資訊，請參閱[Remove new-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="1b49c-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


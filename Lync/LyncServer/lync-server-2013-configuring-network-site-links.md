---
title: Lync Server 2013：設定網路站台連結
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50457100f1ba476fd3ddfa923b73acd6bfe6d843
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a><span data-ttu-id="f8711-102">在 Lync Server 2013 中設定網路站台連結</span><span class="sxs-lookup"><span data-stu-id="f8711-102">Configuring network site links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8711-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f8711-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f8711-104">在通話許可控制 (CAC) 組態中，您可以建立網路網站間原則以定義直接連結的網站之間的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="f8711-104">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="f8711-105">當網路網站共用直接連結時，您可以定義這兩個網站之間音訊與視訊連線的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="f8711-105">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="f8711-106">您無法使用 Lync Server 控制台設定網路網站原則，這只可以使用 Lync Server 管理命令介面中的 Cmdlet 進行。</span><span class="sxs-lookup"><span data-stu-id="f8711-106">You cannot use the Lync Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="f8711-107">您可以建立、修改及移除網路站台連結 (也稱為從 Lync Server 管理命令介面) 網路內部網站原則。</span><span class="sxs-lookup"><span data-stu-id="f8711-107">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Lync Server Management Shell.</span></span>

<div>

## <a name="to-create-a-network-site-link"></a><span data-ttu-id="f8711-108">若要建立網路網站連結</span><span class="sxs-lookup"><span data-stu-id="f8711-108">To create a network site link</span></span>

1.  <span data-ttu-id="f8711-109">以[Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="f8711-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f8711-110">啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="f8711-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f8711-111">在命令提示字元中輸入下列命令，其中的值換成您組態適用的有效值：</span><span class="sxs-lookup"><span data-stu-id="f8711-111">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="f8711-112">這個範例會建立名為雷諾的新網路站台連結 \_ ，此連結會設定雷諾和上點網路網站之間的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="f8711-112">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="f8711-113">網路網站與頻寬原則設定檔在執行此命令前即必須存在。</span><span class="sxs-lookup"><span data-stu-id="f8711-113">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="f8711-114">如需詳細的參數描述，請參閱 Lync Server 管理命令介面檔中的[CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 。</span><span class="sxs-lookup"><span data-stu-id="f8711-114">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="f8711-115">若要擷取可套用至網路網站連結之頻寬原則設定檔的清單，請呼叫 **Get-CsNetworkBandwidthPolicyProfile** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f8711-115">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="f8711-116">如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) 。</span><span class="sxs-lookup"><span data-stu-id="f8711-116">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-link"></a><span data-ttu-id="f8711-117">若要修改網路網站連結</span><span class="sxs-lookup"><span data-stu-id="f8711-117">To modify a network site link</span></span>

1.  <span data-ttu-id="f8711-118">以[Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="f8711-118">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f8711-119">啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="f8711-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f8711-120">使用 **Set-CsNetworkInterSitePolicy** Cmdlet 來修改某個網路網站連結的內容。</span><span class="sxs-lookup"><span data-stu-id="f8711-120">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="f8711-121">您可以修改相連網站的其中一端網站 (或兩端網站都修改)，並且可以修改與連結相關聯的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="f8711-121">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="f8711-122">以下是修改名為雷諾上海之網站連結的頻寬原則設定檔的範例 \_ ：</span><span class="sxs-lookup"><span data-stu-id="f8711-122">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="f8711-123">如需詳細的參數描述，請參閱 Lync Server 管理命令介面檔中的[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) 。</span><span class="sxs-lookup"><span data-stu-id="f8711-123">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site-link"></a><span data-ttu-id="f8711-124">若要刪除網路網站連結</span><span class="sxs-lookup"><span data-stu-id="f8711-124">To delete a network site link</span></span>

1.  <span data-ttu-id="f8711-125">以[Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="f8711-125">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f8711-126">啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="f8711-126">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f8711-127">使用 **Remove-CsNetworkInterSitePolicy** Cmdlet 來移除網路網站連結。</span><span class="sxs-lookup"><span data-stu-id="f8711-127">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="f8711-128">下列範例會刪除雷諾 \_ 上海網路站台連結：</span><span class="sxs-lookup"><span data-stu-id="f8711-128">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="f8711-129">如需詳細的參數描述，請參閱 Lync Server 管理命令介面檔中的[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) 。</span><span class="sxs-lookup"><span data-stu-id="f8711-129">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f8711-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f8711-130">See Also</span></span>


[<span data-ttu-id="f8711-131">Lync Server 2013 中的通話許可控制 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="f8711-131">Call admission control cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/)  


[<span data-ttu-id="f8711-132">新 CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f8711-132">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[<span data-ttu-id="f8711-133">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f8711-133">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[<span data-ttu-id="f8711-134">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f8711-134">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[<span data-ttu-id="f8711-135">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f8711-135">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[<span data-ttu-id="f8711-136">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="f8711-136">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


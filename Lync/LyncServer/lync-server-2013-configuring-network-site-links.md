---
title: Lync Server 2013：設定網路網站連結
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd0ddd5e28cd37cd31e28e5c6427b9b700b5a4c9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a><span data-ttu-id="d0c7b-102">在 Lync Server 2013 中設定網路網站連結</span><span class="sxs-lookup"><span data-stu-id="d0c7b-102">Configuring network site links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0c7b-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d0c7b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d0c7b-104">在呼叫許可控制（CAC）配置中，您可以建立網路間原則，以定義直接連結之網站之間的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="d0c7b-104">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="d0c7b-105">當網路網站共用直接連結時，音訊與視頻連線的頻寬限制可以在這兩個網站之間定義。</span><span class="sxs-lookup"><span data-stu-id="d0c7b-105">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="d0c7b-106">您無法使用 Lync Server [控制台] 來設定網路網站原則，只能使用 Lync Server 管理命令介面中的 Cmdlet 來執行此操作。</span><span class="sxs-lookup"><span data-stu-id="d0c7b-106">You cannot use the Lync Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="d0c7b-107">您可以從 Lync Server 管理命令介面建立、修改及移除網路網站連結（又稱為「網路間的網站」原則）。</span><span class="sxs-lookup"><span data-stu-id="d0c7b-107">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Lync Server Management Shell.</span></span>

<div>

## <a name="to-create-a-network-site-link"></a><span data-ttu-id="d0c7b-108">建立網路網站連結</span><span class="sxs-lookup"><span data-stu-id="d0c7b-108">To create a network site link</span></span>

1.  <span data-ttu-id="d0c7b-109">登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。</span><span class="sxs-lookup"><span data-stu-id="d0c7b-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="d0c7b-110">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d0c7b-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d0c7b-111">在命令提示字元中，輸入下列命令，以取代有效的設定值：</span><span class="sxs-lookup"><span data-stu-id="d0c7b-111">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="d0c7b-112">這個範例會建立名為 Reno\_的新網路網站連結，以設定 Reno 與新的網路網站之間的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="d0c7b-112">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="d0c7b-113">在執行這個命令之前，必須已經存在網路網站和頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="d0c7b-113">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="d0c7b-114">如需詳細的參數描述，請參閱 Lync Server 管理命令介面檔中的[新 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 。</span><span class="sxs-lookup"><span data-stu-id="d0c7b-114">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="d0c7b-115">若要取得可套用至 network site link 的頻寬原則配置檔案清單，請呼叫**CsNetworkBandwidthPolicyProfile** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d0c7b-115">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="d0c7b-116">如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) 。</span><span class="sxs-lookup"><span data-stu-id="d0c7b-116">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-link"></a><span data-ttu-id="d0c7b-117">修改網路網站連結</span><span class="sxs-lookup"><span data-stu-id="d0c7b-117">To modify a network site link</span></span>

1.  <span data-ttu-id="d0c7b-118">登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。</span><span class="sxs-lookup"><span data-stu-id="d0c7b-118">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="d0c7b-119">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d0c7b-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d0c7b-120">使用**CsNetworkInterSitePolicy** Cmdlet 來修改指定的網路網站連結的屬性。</span><span class="sxs-lookup"><span data-stu-id="d0c7b-120">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="d0c7b-121">您可以修改（或兩者）或連線的網站，也可以修改與連結相關聯的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="d0c7b-121">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="d0c7b-122">以下是修改名為 Reno\_的網站連結的頻寬原則設定檔範例：</span><span class="sxs-lookup"><span data-stu-id="d0c7b-122">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="d0c7b-123">如需詳細的參數描述，請參閱 Lync Server 管理命令介面檔中的[設定 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) 。</span><span class="sxs-lookup"><span data-stu-id="d0c7b-123">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site-link"></a><span data-ttu-id="d0c7b-124">刪除網路網站連結</span><span class="sxs-lookup"><span data-stu-id="d0c7b-124">To delete a network site link</span></span>

1.  <span data-ttu-id="d0c7b-125">登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。</span><span class="sxs-lookup"><span data-stu-id="d0c7b-125">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="d0c7b-126">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d0c7b-126">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d0c7b-127">使用**CsNetworkInterSitePolicy** Cmdlet 來移除網路網站連結。</span><span class="sxs-lookup"><span data-stu-id="d0c7b-127">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="d0c7b-128">下列範例會刪除 Reno\_的 [上海網路] 網站連結：</span><span class="sxs-lookup"><span data-stu-id="d0c7b-128">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="d0c7b-129">如需詳細的參數描述，請參閱 Lync Server 管理命令介面檔中的[Remove CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) 。</span><span class="sxs-lookup"><span data-stu-id="d0c7b-129">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d0c7b-130">請參閱</span><span class="sxs-lookup"><span data-stu-id="d0c7b-130">See Also</span></span>


[<span data-ttu-id="d0c7b-131">在 Lync Server 2013 中呼叫許可控制 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d0c7b-131">Call admission control cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/)  


[<span data-ttu-id="d0c7b-132">新-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="d0c7b-132">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[<span data-ttu-id="d0c7b-133">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="d0c7b-133">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[<span data-ttu-id="d0c7b-134">移除-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="d0c7b-134">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[<span data-ttu-id="d0c7b-135">CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="d0c7b-135">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[<span data-ttu-id="d0c7b-136">CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="d0c7b-136">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：查看網路頻寬原則設定檔資訊
description: Lync Server 2013：查看網路頻寬原則設定檔資訊。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network bandwidth policy profile information
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49733866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c72a3533ae6f49f91db91b2c3b515c0b5153ec27
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565399"
---
# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a><span data-ttu-id="9b4b0-103">在 Lync Server 2013 中查看網路頻寬原則設定檔資訊</span><span class="sxs-lookup"><span data-stu-id="9b4b0-103">Viewing network bandwidth policy profile information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b4b0-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9b4b0-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9b4b0-105">頻寬原則為通話許可控制 (CAC) 的一部分，用於定義某些形式的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="9b4b0-105">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="9b4b0-106">在 Microsoft Lync Server 2013 中，只有音訊和影片形式可以獲指派頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="9b4b0-106">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="9b4b0-107">您可以設定整體頻寬限制和工作階段限制。</span><span class="sxs-lookup"><span data-stu-id="9b4b0-107">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="9b4b0-108">您可以使用 Lync Server 控制台建立、修改或刪除這些原則的容器設定檔。</span><span class="sxs-lookup"><span data-stu-id="9b4b0-108">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="9b4b0-109">每個頻寬原則設定檔可以與一或多個網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="9b4b0-109">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="9b4b0-110">請使用下列程式來查看頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="9b4b0-110">Use the following procedures to view a bandwidth policy profile.</span></span> <span data-ttu-id="9b4b0-111">若要建立或修改頻寬原則設定檔，請參閱 [建立或修改 Lync Server 2013 中的頻寬原則設定檔](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="9b4b0-111">To create or modify a bandwidth policy profile, see [Creating or modifying bandwidth policy profiles in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span></span>

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="9b4b0-112">若要查看頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="9b4b0-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="9b4b0-113">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="9b4b0-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9b4b0-114">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="9b4b0-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9b4b0-115">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="9b4b0-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9b4b0-116">在左導覽列中，按一下 **[網路設定]**，再按一下 **[頻寬原則]**。</span><span class="sxs-lookup"><span data-stu-id="9b4b0-116">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="9b4b0-117">在 [ **頻寬原則** ] 頁面上，按一下您要查看的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="9b4b0-117">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="9b4b0-118">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="9b4b0-118">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9b4b0-119">使用 Windows PowerShell Cmdlet 來查看網路頻寬原則設定檔資訊</span><span class="sxs-lookup"><span data-stu-id="9b4b0-119">Viewing Network Bandwidth Policy Profile Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9b4b0-120">您可以使用 Windows PowerShell 和 Get-CsNetworkBandwidthPolicyProfile Cmdlet 來查看網路頻寬設定檔。</span><span class="sxs-lookup"><span data-stu-id="9b4b0-120">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="9b4b0-121">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9b4b0-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9b4b0-122">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="9b4b0-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="9b4b0-123">若要查看網路頻寬原則設定檔資訊</span><span class="sxs-lookup"><span data-stu-id="9b4b0-123">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="9b4b0-124">若要查看所有網路頻寬原則設定檔的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="9b4b0-124">To view information about all your network bandwidth policy profiles, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="9b4b0-125">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="9b4b0-125">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

<span data-ttu-id="9b4b0-126">如需詳細資訊，請參閱 [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="9b4b0-126">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9b4b0-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9b4b0-127">See Also</span></span>


[<span data-ttu-id="9b4b0-128">在 Lync Server 2013 中建立或修改頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="9b4b0-128">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[<span data-ttu-id="9b4b0-129">在 Lync Server 2013 中刪除網路頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="9b4b0-129">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="9b4b0-130">在 Lync Server 2013 中設定通話許可控制</span><span class="sxs-lookup"><span data-stu-id="9b4b0-130">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


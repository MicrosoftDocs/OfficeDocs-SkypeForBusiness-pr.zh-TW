---
title: Lync Server 2013：啟用網路媒體旁路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e0b5e7b060d056a785e80fdf29ded718d120bc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="fee11-102">在 Lync Server 2013 中啟用網路媒體旁路</span><span class="sxs-lookup"><span data-stu-id="fee11-102">Enabling network media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fee11-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="fee11-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="fee11-104">在 Microsoft Lync Server 2013 部署中，媒體旁路設定會全域運用。</span><span class="sxs-lookup"><span data-stu-id="fee11-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="fee11-105">[旁路媒體] 允許呼叫繞過中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="fee11-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="fee11-106">如需有關何時使用媒體旁路的詳細資料，請參閱規劃區段中的[Lync Server 2013 中的媒體旁路規劃](lync-server-2013-planning-for-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="fee11-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.</span></span>

<span data-ttu-id="fee11-107">您可以從 Lync Server [控制台] 啟用和設定 [媒體旁路]。</span><span class="sxs-lookup"><span data-stu-id="fee11-107">You can enable and configure media bypass from the Lync Server Control Panel.</span></span>

<div>

## <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="fee11-108">啟用和設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="fee11-108">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="fee11-109">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="fee11-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fee11-110">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="fee11-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fee11-111">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="fee11-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fee11-112">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**全域**]。</span><span class="sxs-lookup"><span data-stu-id="fee11-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="fee11-113">在 [**全域**] 頁面上，按一下 [**全域**配置]。</span><span class="sxs-lookup"><span data-stu-id="fee11-113">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="fee11-114">永遠只有一個設定，且永遠會將它命名為 Global。</span><span class="sxs-lookup"><span data-stu-id="fee11-114">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="fee11-115">按一下 [**編輯**] 功能表上的 [**查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="fee11-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="fee11-116">在 [**編輯全域設定**] 頁面上，按一下 [**啟用旁路媒體**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fee11-116">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="fee11-117">選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="fee11-117">Select one of the following options:</span></span>
    
      - <span data-ttu-id="fee11-118">**[永遠略過**   ] 選取此選項，即可在所有通話中嘗試媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="fee11-118">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="fee11-119">如果啟用 [通話許可控制（CAC）]，此選項將無法使用。</span><span class="sxs-lookup"><span data-stu-id="fee11-119">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="fee11-120">如果未啟用 CAC，請在下列情況下選取此選項：</span><span class="sxs-lookup"><span data-stu-id="fee11-120">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="fee11-121">您不需要頻寬控制。</span><span class="sxs-lookup"><span data-stu-id="fee11-121">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="fee11-122">不需要精確的設定來判斷何時應發生旁路。</span><span class="sxs-lookup"><span data-stu-id="fee11-122">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="fee11-123">閘道與用戶端之間有完整的連線能力。</span><span class="sxs-lookup"><span data-stu-id="fee11-123">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="fee11-124">\*\*\*\* 如果啟用了 CAC，請使用網站和地區設定，預設會選取此選項，且無法進行變更。   </span><span class="sxs-lookup"><span data-stu-id="fee11-124">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="fee11-125">選取此選項時，系統會使用網路設定網站和區域來判斷何時可能會略過媒體。</span><span class="sxs-lookup"><span data-stu-id="fee11-125">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="fee11-126">如果您選取此選項，您可以選擇針對未對應的網站啟用 [旁路]。</span><span class="sxs-lookup"><span data-stu-id="fee11-126">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="fee11-127">如果您的一個或多個大型網站與不具備頻寬限制（例如大型中央網站）的同一個區域相關聯，且您還有一些與有頻寬限制的同一個區域相關聯的分支網站，請按一下 [為未**對應的網站啟用旁路**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fee11-127">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="fee11-128">當您針對未對應的網站啟用 [旁路] 時，系統會簡化配置，因為您只需指定與分支網站相關聯的子網，而不需要指定所有與所有網站相關聯的子網。</span><span class="sxs-lookup"><span data-stu-id="fee11-128">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="fee11-129">如果啟用 CAC，我們建議您不要選取 [**啟用旁路未對應的網站**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fee11-129">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="fee11-130">按一下 [**認可**]，儲存您的變更。</span><span class="sxs-lookup"><span data-stu-id="fee11-130">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fee11-131">請參閱</span><span class="sxs-lookup"><span data-stu-id="fee11-131">See Also</span></span>


[<span data-ttu-id="fee11-132">在 Lync Server 2013 中停用網路媒體旁路</span><span class="sxs-lookup"><span data-stu-id="fee11-132">Disabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-disabling-network-media-bypass.md)  


[<span data-ttu-id="fee11-133">Lync Server 2013 中的全域媒體旁路選項</span><span class="sxs-lookup"><span data-stu-id="fee11-133">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="fee11-134">在 Lync Server 2013 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="fee11-134">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：啟用網路媒體旁路
description: Lync Server 2013：啟用網路媒體旁路。
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
ms.openlocfilehash: 1218376903aa42e1ea55205e3a9e8d16aade9a3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546549"
---
# <a name="enabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="479b9-103">在 Lync Server 2013 中啟用網路媒體旁路</span><span class="sxs-lookup"><span data-stu-id="479b9-103">Enabling network media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="479b9-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="479b9-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="479b9-105">媒體旁路設定會在 Microsoft Lync Server 2013 部署中全域套用。</span><span class="sxs-lookup"><span data-stu-id="479b9-105">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="479b9-106">媒體旁路允許來電略過轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="479b9-106">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="479b9-107">如需有關何時使用媒體旁路的詳細資訊，請參閱規劃區段中的在 [Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md) 。</span><span class="sxs-lookup"><span data-stu-id="479b9-107">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.</span></span>

<span data-ttu-id="479b9-108">您可以從 Lync Server [控制台] 啟用和設定媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="479b9-108">You can enable and configure media bypass from the Lync Server Control Panel.</span></span>

<div>

## <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="479b9-109">啟用及設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="479b9-109">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="479b9-110">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="479b9-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="479b9-111">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="479b9-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="479b9-112">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="479b9-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="479b9-113">在左導覽列中，按一下 **[網路設定]**，然後按一下 **[全域]**。</span><span class="sxs-lookup"><span data-stu-id="479b9-113">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="479b9-114">在 **[全域]** 頁面上，按一下 **[全域]** 設定。</span><span class="sxs-lookup"><span data-stu-id="479b9-114">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="479b9-115">永遠只有一個設定，而且永遠稱為 Global。</span><span class="sxs-lookup"><span data-stu-id="479b9-115">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="479b9-116">在 [ **編輯** ] 功能表上，按一下 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="479b9-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="479b9-117">在 [ **編輯通用設定** ] 頁面上，按一下 [ **啟用媒體旁路** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="479b9-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="479b9-118">請選取下列任一選項：</span><span class="sxs-lookup"><span data-stu-id="479b9-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="479b9-119">**永遠略過**    選取此選項，可在所有呼叫時嘗試媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="479b9-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="479b9-120">如果已啟用 (CAC) 的通話許可控制，此選項將無法使用。</span><span class="sxs-lookup"><span data-stu-id="479b9-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="479b9-121">如果未啟用 CAC，請在下列情況下選取此選項：</span><span class="sxs-lookup"><span data-stu-id="479b9-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="479b9-122">不需要頻寬控制。</span><span class="sxs-lookup"><span data-stu-id="479b9-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="479b9-123">不需要微調設定，就能決定何時應該應該發生旁路。</span><span class="sxs-lookup"><span data-stu-id="479b9-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="479b9-124">閘道和用戶端之間有完整的連線能力。</span><span class="sxs-lookup"><span data-stu-id="479b9-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="479b9-125">**使用網站與地區**     設定如果啟用 CAC，預設會選取此選項，而且無法變更。</span><span class="sxs-lookup"><span data-stu-id="479b9-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="479b9-126">選取此選項時，會使用網路設定網站和區域來決定何時可以進行媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="479b9-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="479b9-127">如果您選取此選項，您可以針對未對應的網站，選擇啟用旁路。</span><span class="sxs-lookup"><span data-stu-id="479b9-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="479b9-128">只有當您有一個或多個大型網站與沒有頻寬限制的相同區域相關聯時，才會按一下 [為 **未對應的網站啟用旁路** ] 核取方塊 (例如，大型中央網站) ，而且您也有一些分支網站與具有頻寬限制的相同地區相關聯。</span><span class="sxs-lookup"><span data-stu-id="479b9-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="479b9-129">當您為未對應的網站啟用旁路時，將會簡化設定，因為您只會指定與分支網站相關聯的子網，而不需要指定所有網站相關聯的所有子網。</span><span class="sxs-lookup"><span data-stu-id="479b9-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="479b9-130">如果啟用 CAC，建議您不要選取 [為 **未對應的網站啟用旁路** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="479b9-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="479b9-131">按一下 [ **認可** ] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="479b9-131">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="479b9-132">另請參閱</span><span class="sxs-lookup"><span data-stu-id="479b9-132">See Also</span></span>


[<span data-ttu-id="479b9-133">停用 Lync Server 2013 中的網路媒體旁路</span><span class="sxs-lookup"><span data-stu-id="479b9-133">Disabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-disabling-network-media-bypass.md)  


[<span data-ttu-id="479b9-134">Lync Server 2013 中的全域媒體旁路選項</span><span class="sxs-lookup"><span data-stu-id="479b9-134">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="479b9-135">在 Lync Server 2013 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="479b9-135">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


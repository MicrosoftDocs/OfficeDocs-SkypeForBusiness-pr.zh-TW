---
title: 確認拓撲資訊
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69add03365fa55ba3b08ac4c6b7a1dd60a6294f2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a><span data-ttu-id="55e95-102">確認拓撲資訊</span><span class="sxs-lookup"><span data-stu-id="55e95-102">Verify topology information</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55e95-103">_**主題上次修改日期：** 2012年-09-26_</span><span class="sxs-lookup"><span data-stu-id="55e95-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="55e95-104">確認已順利完成合併的第一個步驟是檢視合併與 Lync Server 2013 的 Office Communications Server 2007 R2 拓撲資訊。</span><span class="sxs-lookup"><span data-stu-id="55e95-104">The first step in verifying the merge completed successfully is to view the Office Communications Server 2007 R2 topology information that you merged with Lync Server 2013.</span></span> <span data-ttu-id="55e95-105">在拓撲產生器中，[ **BackCompatSite** ] 節點會顯示每個 Office Communications Server 2007 R2 集區和所合併的伺服器的完整的網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="55e95-105">In Topology Builder, the **BackCompatSite** node displays the fully qualified domain name (FQDN) of each Office Communications Server 2007 R2 pool and server that you merged.</span></span>

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a><span data-ttu-id="55e95-106">若要在拓撲產生器中檢視 BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="55e95-106">To view BackCompatSite in Topology Builder</span></span>

1.  <span data-ttu-id="55e95-107">在 Office Communications Server 2007 R2 環境中，開啟 Office Communications Server 2007 R2 系統管理工具]，然後記下舊版集區和伺服器的 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="55e95-107">In your Office Communications Server 2007 R2 environment, open the Office Communications Server 2007 R2 administrative tool and note the FQDNs of the legacy pools and servers.</span></span>

2.  <span data-ttu-id="55e95-108">在 Lync Server 2013 環境中，開啟拓撲產生器]，然後展開 [ **BackCompatSite** ] 節點。</span><span class="sxs-lookup"><span data-stu-id="55e95-108">In your Lync Server 2013 environment, open Topology Builder and then expand the **BackCompatSite** node.</span></span>

3.  <span data-ttu-id="55e95-109">確認所合併的伺服器與集區的 fqdn 均有顯示。</span><span class="sxs-lookup"><span data-stu-id="55e95-109">Verify that the FQDNs for the pools and servers that you merge are displayed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="55e95-110">您的前端伺服器或 Standard Edition server 上沒看到<STRONG>BackCompatSite</STRONG>中組合的伺服器角色的任何資訊。</span><span class="sxs-lookup"><span data-stu-id="55e95-110">You do not see any information in <STRONG>BackCompatSite</STRONG> for server roles that are collocated on a Front End Server or Standard Edition server.</span></span> <span data-ttu-id="55e95-111">顯示所需的 Office Communications Server 2007 R2 和 Lync Server 2013 之間的互通性伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="55e95-111">Only server roles that are required for interoperability between Office Communications Server 2007 R2 and Lync Server 2013 are shown.</span></span>

    
    </div>

<span data-ttu-id="55e95-112">![拓撲產生器 BackCompatSite] 對話方塊](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "拓撲產生器 BackCompatSite] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="55e95-112">![Topology Builder BackCompatSite dialog box](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder BackCompatSite dialog box")</span></span>

<span data-ttu-id="55e95-113">您也可以使用 Lync Server 2013 控制台檢視合併後的拓撲。</span><span class="sxs-lookup"><span data-stu-id="55e95-113">You can also use Lync Server 2013 Control Panel to view your merged topology.</span></span> <span data-ttu-id="55e95-114">在 Lync Server 2013 控制台中，您可以看到每個伺服器 FQDN、 集區 FQDN] 中，並合併拓撲的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="55e95-114">In Lync Server 2013 Control Panel, you can see each server FQDN, pool FQDN, and site name for your merged topology.</span></span> <span data-ttu-id="55e95-115">合併的伺服器有**BackCompatSite**的**網站**名稱。</span><span class="sxs-lookup"><span data-stu-id="55e95-115">Merged servers have a **Site** name of **BackCompatSite**.</span></span>

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a><span data-ttu-id="55e95-116">若要在 Lync Server 2013 Control Panel 中檢視合併後的拓撲</span><span class="sxs-lookup"><span data-stu-id="55e95-116">To view the merged topology in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="55e95-117">開啟 Lync Server 2013 控制台。</span><span class="sxs-lookup"><span data-stu-id="55e95-117">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="55e95-118">按一下 **[拓撲]**。</span><span class="sxs-lookup"><span data-stu-id="55e95-118">Click **Topology**.</span></span>

3.  <span data-ttu-id="55e95-119">在 [**狀態**] 索引標籤，確認伺服器和集區所合併出現的 [**網站**] 欄中尋找**BackCompatSite** 。</span><span class="sxs-lookup"><span data-stu-id="55e95-119">On the **Status** tab, verify that servers and pools you merged appear by looking for **BackCompatSite** in the **Site** column.</span></span>

<span data-ttu-id="55e95-120">![Lync Server Control Panel 顯示合併後的拓撲](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Lync Server Control Panel 顯示合併後的拓撲")</span><span class="sxs-lookup"><span data-stu-id="55e95-120">![Lync Server Control Panel showing merged topology](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Lync Server Control Panel showing merged topology")</span></span>

<span data-ttu-id="55e95-121">若要查看合併的集區相關的詳細資料，請使用**Get-cspool** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="55e95-121">To see more detail about a merged pool, use the **Get-CsPool** cmdlet.</span></span> <span data-ttu-id="55e95-122">除了在拓撲產生器和 Lync Server 2013 控制台的資訊，此 cmdlet 會顯示 [Lync Server 2013 集區執行的服務。</span><span class="sxs-lookup"><span data-stu-id="55e95-122">In addition to the information that is available in Topology Builder and Lync Server 2013 Control Panel, this cmdlet displays the services that run on the Lync Server 2013 pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="55e95-123">當您執行合併列印精靈在拓撲產生器之後發行拓撲時，會議目錄被合併到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="55e95-123">When you publish the topology after running the Merge wizard in Topology Builder, conference directories are merged to Lync Server 2013.</span></span> <span data-ttu-id="55e95-124">藉由執行<STRONG>Get-csconferencedirectory</STRONG> cmdlet 可驗證會議目錄。</span><span class="sxs-lookup"><span data-stu-id="55e95-124">Conference directories can be verified by running the <STRONG>Get-CsConferenceDirectory</STRONG> cmdlet.</span></span>



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a><span data-ttu-id="55e95-125">若要檢視合併後集區上的服務</span><span class="sxs-lookup"><span data-stu-id="55e95-125">To view services on a merged pool</span></span>

1.  <span data-ttu-id="55e95-126">開啟 [Lync Server 2013 管理命令介面]。</span><span class="sxs-lookup"><span data-stu-id="55e95-126">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="55e95-127">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="55e95-127">At the command line, type the following:</span></span>
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    <span data-ttu-id="55e95-128">例如：</span><span class="sxs-lookup"><span data-stu-id="55e95-128">For example:</span></span>
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a><span data-ttu-id="55e95-129">若要確認會議目錄合併</span><span class="sxs-lookup"><span data-stu-id="55e95-129">To verify conference directories merged</span></span>

1.  <span data-ttu-id="55e95-130">開啟 [Lync Server 2013 管理命令介面]。</span><span class="sxs-lookup"><span data-stu-id="55e95-130">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="55e95-131">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="55e95-131">At the command line, type the following:</span></span>
    
        Get-CsConferenceDirectory

3.  <span data-ttu-id="55e95-132">確認集區或您要合併的伺服器的所有會議目錄都皆已在 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="55e95-132">Verify that all the conference directories for the pool or server you are merging are now in Lync Server 2013.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


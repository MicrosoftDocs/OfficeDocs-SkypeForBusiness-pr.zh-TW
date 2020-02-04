---
title: 驗證拓撲資訊
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
ms.openlocfilehash: ec6c73f274cb67b527aaf1147f20e83959487255
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a><span data-ttu-id="93287-102">驗證拓撲資訊</span><span class="sxs-lookup"><span data-stu-id="93287-102">Verify topology information</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93287-103">_**主題上次修改日期：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="93287-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="93287-104">驗證已成功完成合併的第一個步驟是，要查看您與 Lync Server 2013 合併的 Office 通訊伺服器 2007 R2 拓撲資訊。</span><span class="sxs-lookup"><span data-stu-id="93287-104">The first step in verifying the merge completed successfully is to view the Office Communications Server 2007 R2 topology information that you merged with Lync Server 2013.</span></span> <span data-ttu-id="93287-105">在拓撲建立器中， **BackCompatSite**節點會顯示您合併的每個 Office 通訊伺服器 2007 R2 池和伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="93287-105">In Topology Builder, the **BackCompatSite** node displays the fully qualified domain name (FQDN) of each Office Communications Server 2007 R2 pool and server that you merged.</span></span>

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a><span data-ttu-id="93287-106">在拓撲產生器中查看 BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="93287-106">To view BackCompatSite in Topology Builder</span></span>

1.  <span data-ttu-id="93287-107">在您的 Office 通訊伺服器 2007 R2 環境中，開啟 Office 通訊伺服器 2007 R2 管理工具，並記下舊版池和伺服器的 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="93287-107">In your Office Communications Server 2007 R2 environment, open the Office Communications Server 2007 R2 administrative tool and note the FQDNs of the legacy pools and servers.</span></span>

2.  <span data-ttu-id="93287-108">在 Lync Server 2013 環境中，開啟 [拓撲建立器]，然後展開 [ **BackCompatSite** ] 節點。</span><span class="sxs-lookup"><span data-stu-id="93287-108">In your Lync Server 2013 environment, open Topology Builder and then expand the **BackCompatSite** node.</span></span>

3.  <span data-ttu-id="93287-109">確認會顯示您所合併之池和伺服器的 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="93287-109">Verify that the FQDNs for the pools and servers that you merge are displayed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="93287-110">您不會在<STRONG>BackCompatSite</STRONG>中看到在前端伺服器或標準版伺服器上 collocated 的伺服器角色的任何資訊。</span><span class="sxs-lookup"><span data-stu-id="93287-110">You do not see any information in <STRONG>BackCompatSite</STRONG> for server roles that are collocated on a Front End Server or Standard Edition server.</span></span> <span data-ttu-id="93287-111">顯示 Office 通訊伺服器 2007 R2 和 Lync Server 2013 之間的互通性所需的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="93287-111">Only server roles that are required for interoperability between Office Communications Server 2007 R2 and Lync Server 2013 are shown.</span></span>

    
    </div>

<span data-ttu-id="93287-112">![拓撲產生器的 [BackCompatSite] 對話方塊](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "拓撲產生器的 [BackCompatSite] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="93287-112">![Topology Builder BackCompatSite dialog box](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder BackCompatSite dialog box")</span></span>

<span data-ttu-id="93287-113">您也可以使用 Lync Server 2013 [控制台] 來查看合併的拓撲。</span><span class="sxs-lookup"><span data-stu-id="93287-113">You can also use Lync Server 2013 Control Panel to view your merged topology.</span></span> <span data-ttu-id="93287-114">在 Lync Server 2013 的 [控制台] 中，您可以查看合併後拓撲的每個伺服器 FQDN、池 FQDN 和網站名稱。</span><span class="sxs-lookup"><span data-stu-id="93287-114">In Lync Server 2013 Control Panel, you can see each server FQDN, pool FQDN, and site name for your merged topology.</span></span> <span data-ttu-id="93287-115">合併伺服器的**網站**名稱為**BackCompatSite**。</span><span class="sxs-lookup"><span data-stu-id="93287-115">Merged servers have a **Site** name of **BackCompatSite**.</span></span>

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a><span data-ttu-id="93287-116">在 Lync Server 2013 的 [控制台] 中查看合併的拓撲</span><span class="sxs-lookup"><span data-stu-id="93287-116">To view the merged topology in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="93287-117">開啟 Lync Server 2013 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="93287-117">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="93287-118">按一下 [**拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="93287-118">Click **Topology**.</span></span>

3.  <span data-ttu-id="93287-119">在 [**狀態**] 索引標籤上，請在 [**網站**] 欄中尋找 [ **BackCompatSite** ]，確認您已合併的伺服器和池都出現。</span><span class="sxs-lookup"><span data-stu-id="93287-119">On the **Status** tab, verify that servers and pools you merged appear by looking for **BackCompatSite** in the **Site** column.</span></span>

<span data-ttu-id="93287-120">![顯示合併拓撲的 Lync Server 控制台](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "顯示合併拓撲的 Lync Server 控制台")</span><span class="sxs-lookup"><span data-stu-id="93287-120">![Lync Server Control Panel showing merged topology](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Lync Server Control Panel showing merged topology")</span></span>

<span data-ttu-id="93287-121">若要查看合併池的更多詳細資料，請使用**CsPool** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="93287-121">To see more detail about a merged pool, use the **Get-CsPool** cmdlet.</span></span> <span data-ttu-id="93287-122">除了拓撲結構建立器和 Lync Server 2013 [控制台] 中提供的資訊，此 Cmdlet 還會顯示在 Lync Server 2013 池中執行的服務。</span><span class="sxs-lookup"><span data-stu-id="93287-122">In addition to the information that is available in Topology Builder and Lync Server 2013 Control Panel, this cmdlet displays the services that run on the Lync Server 2013 pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="93287-123">在拓撲建立器中執行合併嚮導後發佈拓撲，會議目錄會合並至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="93287-123">When you publish the topology after running the Merge wizard in Topology Builder, conference directories are merged to Lync Server 2013.</span></span> <span data-ttu-id="93287-124">您可以執行<STRONG>CsConferenceDirectory</STRONG> Cmdlet 來驗證會議目錄。</span><span class="sxs-lookup"><span data-stu-id="93287-124">Conference directories can be verified by running the <STRONG>Get-CsConferenceDirectory</STRONG> cmdlet.</span></span>



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a><span data-ttu-id="93287-125">若要在合併的文檔池中查看服務</span><span class="sxs-lookup"><span data-stu-id="93287-125">To view services on a merged pool</span></span>

1.  <span data-ttu-id="93287-126">開啟 Lync Server 2013 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="93287-126">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="93287-127">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="93287-127">At the command line, type the following:</span></span>
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    <span data-ttu-id="93287-128">例如：</span><span class="sxs-lookup"><span data-stu-id="93287-128">For example:</span></span>
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a><span data-ttu-id="93287-129">驗證已合併的會議目錄</span><span class="sxs-lookup"><span data-stu-id="93287-129">To verify conference directories merged</span></span>

1.  <span data-ttu-id="93287-130">開啟 Lync Server 2013 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="93287-130">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="93287-131">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="93287-131">At the command line, type the following:</span></span>
    
        Get-CsConferenceDirectory

3.  <span data-ttu-id="93287-132">確認目前在 Lync Server 2013 中的是您要合併之池或伺服器的所有會議目錄。</span><span class="sxs-lookup"><span data-stu-id="93287-132">Verify that all the conference directories for the pool or server you are merging are now in Lync Server 2013.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


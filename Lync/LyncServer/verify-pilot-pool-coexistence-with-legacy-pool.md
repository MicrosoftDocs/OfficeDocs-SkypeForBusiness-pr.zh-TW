---
title: 驗證試驗集區與舊版集區共存
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe3b3e04940c90cba4e46fc165c2494f77105667
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="faaea-102">驗證試驗集區與舊版集區共存</span><span class="sxs-lookup"><span data-stu-id="faaea-102">Verify pilot pool coexistence with legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="faaea-103">_**主題上次修改日期：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="faaea-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="faaea-104">部署試生產池之後，您必須使用 [管理工具] 來查看池資訊，以驗證這兩個池的共存性。</span><span class="sxs-lookup"><span data-stu-id="faaea-104">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="faaea-105">針對 Lync Server 2013 池與舊版池，您必須使用 Lync Server 2013 控制台和拓撲建立工具。</span><span class="sxs-lookup"><span data-stu-id="faaea-105">For the Lync Server 2013 pools and legacy pools, you must use the Lync Server 2013 Control Panel and Topology Builder tools.</span></span>

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a><span data-ttu-id="faaea-106">確認 Lync Server 2013 服務已啟動</span><span class="sxs-lookup"><span data-stu-id="faaea-106">Verify that Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="faaea-107">從 Lync Server 2013 前端伺服器流覽至 [管理工具\\服務] 小程式。</span><span class="sxs-lookup"><span data-stu-id="faaea-107">From the Lync Server 2013 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="faaea-108">確認下列服務正在前端伺服器上執行：</span><span class="sxs-lookup"><span data-stu-id="faaea-108">Verify that the following services are running on the Front End Server:</span></span>

<span data-ttu-id="faaea-109">**Lync Server 2013 服務**</span><span class="sxs-lookup"><span data-stu-id="faaea-109">**Lync Server 2013 services**</span></span>

<span data-ttu-id="faaea-110">![已啟動的 Lync Server 服務清單](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "已啟動的 Lync Server 服務清單")</span><span class="sxs-lookup"><span data-stu-id="faaea-110">![List of Lync Server Services Started](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "List of Lync Server Services Started")</span></span>

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a><span data-ttu-id="faaea-111">開啟 Lync Server 2013 [控制台]</span><span class="sxs-lookup"><span data-stu-id="faaea-111">Open the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="faaea-112">在 Lync Server 2013 部署中，從前端伺服器開啟 Lync Server 2013 [控制台]，然後選取 [Lync Server 2010] 資源庫。</span><span class="sxs-lookup"><span data-stu-id="faaea-112">From the Front End Server in your Lync Server 2013 deployment, open the Lync Server 2013 Control Panel and select the Lync Server 2010 pool.</span></span> <span data-ttu-id="faaea-113">重複此程式以開啟 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="faaea-113">Repeat the procedure to open the Lync Server 2013 pool.</span></span>

<span data-ttu-id="faaea-114">**開啟 Lync Server 2013 [控制台]**</span><span class="sxs-lookup"><span data-stu-id="faaea-114">**Open Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="faaea-115">![[選取 URL] 對話方塊](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "[選取 URL] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="faaea-115">![Select URL dialog box](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Select URL dialog box")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="faaea-116">在 Lync Server 2013 上，您必須先將 Silverlight 升級至 Silverlight 版本5，然後才能使用 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="faaea-116">On Lync Server 2013, you must upgrade Silverlight to Silverlight version 5 prior to using the Lync Server Control Panel.</span></span>



</div>

<span data-ttu-id="faaea-117">此拓撲現在包含 Lync Server 2010 和 Lync Server 2013 伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="faaea-117">This topology now includes Lync Server 2010 and Lync Server 2013 server roles.</span></span>

<span data-ttu-id="faaea-118">**Lync Server 2013 [控制台拓撲] 頁面**</span><span class="sxs-lookup"><span data-stu-id="faaea-118">**Lync Server 2013 Control Panel Topology page**</span></span>

<span data-ttu-id="faaea-119">![[Lync Server 控制台 - 拓撲] 頁面](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "[Lync Server 控制台 - 拓撲] 頁面")</span><span class="sxs-lookup"><span data-stu-id="faaea-119">![Lync Server Control Panel - Topology page](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server Control Panel - Topology page")</span></span>

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a><span data-ttu-id="faaea-120">不要嘗試在 Lync Server 2010 拓撲建立器中開啟拓撲</span><span class="sxs-lookup"><span data-stu-id="faaea-120">Don’t attempt to open the topology in Lync Server 2010 Topology Builder</span></span>

<span data-ttu-id="faaea-121">如果您嘗試使用 Lync Server 2010 拓撲建立器開啟拓撲，您會遇到下列錯誤。</span><span class="sxs-lookup"><span data-stu-id="faaea-121">If you attempt to open the topology using Lync Server 2010 Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="faaea-122">只能使用 Lync Server 2013 拓撲產生器來查看拓撲。</span><span class="sxs-lookup"><span data-stu-id="faaea-122">The topology can only be viewed using Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="faaea-123">Lync server 2013 拓撲建立器必須用來為 Lync Server 2013 和 Lync Server 2010 建立池。</span><span class="sxs-lookup"><span data-stu-id="faaea-123">The Lync Server 2013 Topology Builder must be used to create pools for both Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="faaea-124">**Lync Server 2010 拓撲建立器錯誤訊息**</span><span class="sxs-lookup"><span data-stu-id="faaea-124">**Lync Server 2010 Topology Builder error message**</span></span>

<span data-ttu-id="faaea-125">![Lync Server 拓撲產生器 MMC 貼齊錯誤](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server 拓撲產生器 MMC 貼齊錯誤")</span><span class="sxs-lookup"><span data-stu-id="faaea-125">![Lync Server Topology Builder MMC Snap Error](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server Topology Builder MMC Snap Error")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 確認舊版集區與試驗集區共存
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
ms.openlocfilehash: 6c30f15b7a4e40b5c814ed5f21d07e213b69cf10
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="6d467-102">確認舊版集區與試驗集區共存</span><span class="sxs-lookup"><span data-stu-id="6d467-102">Verify pilot pool coexistence with legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d467-103">_**主題上次修改日期：** 2012年-09-29_</span><span class="sxs-lookup"><span data-stu-id="6d467-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="6d467-104">部署試驗集區之後，您需要確認兩個集區共存所使用的系統管理工具來檢視的集區資訊。</span><span class="sxs-lookup"><span data-stu-id="6d467-104">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="6d467-105">Lync Server 2013 集區與舊版的集區，您必須使用 Lync Server 2013 控制台] 及 [拓撲產生器工具。</span><span class="sxs-lookup"><span data-stu-id="6d467-105">For the Lync Server 2013 pools and legacy pools, you must use the Lync Server 2013 Control Panel and Topology Builder tools.</span></span>

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a><span data-ttu-id="6d467-106">確認 Lync Server 2013 服務已啟動</span><span class="sxs-lookup"><span data-stu-id="6d467-106">Verify that Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="6d467-107">從 Lync Server 2013 前端伺服器，瀏覽至 [系統管理工具]\\服務] 小程式。</span><span class="sxs-lookup"><span data-stu-id="6d467-107">From the Lync Server 2013 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="6d467-108">確認下列服務正在執行前端伺服器上：</span><span class="sxs-lookup"><span data-stu-id="6d467-108">Verify that the following services are running on the Front End Server:</span></span>

<span data-ttu-id="6d467-109">**Lync Server 2013 服務**</span><span class="sxs-lookup"><span data-stu-id="6d467-109">**Lync Server 2013 services**</span></span>

<span data-ttu-id="6d467-110">![啟動 Lync Server 服務的清單](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "啟動 Lync Server 服務的清單")</span><span class="sxs-lookup"><span data-stu-id="6d467-110">![List of Lync Server Services Started](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "List of Lync Server Services Started")</span></span>

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a><span data-ttu-id="6d467-111">開啟 Lync Server 2013 控制台</span><span class="sxs-lookup"><span data-stu-id="6d467-111">Open the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="6d467-112">從前端伺服器 Lync Server 2013 部署中，開啟 Lync Server 2013 控制台]，選取 [Lync Server 2010 集區。</span><span class="sxs-lookup"><span data-stu-id="6d467-112">From the Front End Server in your Lync Server 2013 deployment, open the Lync Server 2013 Control Panel and select the Lync Server 2010 pool.</span></span> <span data-ttu-id="6d467-113">重複此程序來開啟 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="6d467-113">Repeat the procedure to open the Lync Server 2013 pool.</span></span>

<span data-ttu-id="6d467-114">**開啟 Lync Server 2013 控制台**</span><span class="sxs-lookup"><span data-stu-id="6d467-114">**Open Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="6d467-115">![選取 [URL] 對話方塊](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "選取 [URL] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="6d467-115">![Select URL dialog box](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Select URL dialog box")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6d467-116">在 Lync Server 2013，您必須升級為 Silverlight 版本 5 才能使用 Lync Server Control Panel 的 Silverlight。</span><span class="sxs-lookup"><span data-stu-id="6d467-116">On Lync Server 2013, you must upgrade Silverlight to Silverlight version 5 prior to using the Lync Server Control Panel.</span></span>



</div>

<span data-ttu-id="6d467-117">現在此拓撲包含 Lync Server 2010 和 Lync Server 2013 伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="6d467-117">This topology now includes Lync Server 2010 and Lync Server 2013 server roles.</span></span>

<span data-ttu-id="6d467-118">**Lync Server 2013 控制台拓撲頁面**</span><span class="sxs-lookup"><span data-stu-id="6d467-118">**Lync Server 2013 Control Panel Topology page**</span></span>

<span data-ttu-id="6d467-119">![Lync Server 控制台的拓撲] 頁面上](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server 控制台的拓撲] 頁面上")</span><span class="sxs-lookup"><span data-stu-id="6d467-119">![Lync Server Control Panel - Topology page](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server Control Panel - Topology page")</span></span>

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a><span data-ttu-id="6d467-120">請勿嘗試在 Lync Server 2010 拓撲產生器] 中開啟拓撲</span><span class="sxs-lookup"><span data-stu-id="6d467-120">Don’t attempt to open the topology in Lync Server 2010 Topology Builder</span></span>

<span data-ttu-id="6d467-121">如果您嘗試開啟拓撲中使用 Lync Server 2010 拓撲產生器]，就會發生下列錯誤。</span><span class="sxs-lookup"><span data-stu-id="6d467-121">If you attempt to open the topology using Lync Server 2010 Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="6d467-122">拓撲只能檢視使用 Lync Server 2013 拓撲產生器]。</span><span class="sxs-lookup"><span data-stu-id="6d467-122">The topology can only be viewed using Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="6d467-123">Lync Server 2013 拓撲產生器必須用來建立 Lync Server 2013 和 Lync Server 2010 的集區。</span><span class="sxs-lookup"><span data-stu-id="6d467-123">The Lync Server 2013 Topology Builder must be used to create pools for both Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="6d467-124">**Lync Server 2010 拓撲產生器錯誤訊息**</span><span class="sxs-lookup"><span data-stu-id="6d467-124">**Lync Server 2010 Topology Builder error message**</span></span>

<span data-ttu-id="6d467-125">![Lync Server 拓撲產生器] MMC 貼齊錯誤](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server 拓撲產生器] MMC 貼齊錯誤")</span><span class="sxs-lookup"><span data-stu-id="6d467-125">![Lync Server Topology Builder MMC Snap Error](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server Topology Builder MMC Snap Error")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


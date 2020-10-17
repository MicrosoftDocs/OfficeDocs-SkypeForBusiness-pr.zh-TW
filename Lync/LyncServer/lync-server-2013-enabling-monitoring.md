---
title: Lync Server 2013：啟用監控
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0b637ea06d0255d53f73eef0385c3e929045071
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528530"
---
# <a name="enabling-monitoring-in-lync-server-2013"></a><span data-ttu-id="5e1c9-102">啟用 Lync Server 2013 中的監控</span><span class="sxs-lookup"><span data-stu-id="5e1c9-102">Enabling monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e1c9-103">_**主題上次修改日期：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="5e1c9-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="5e1c9-104">雖然整合的資料集合代理程式會在每一部前端伺服器上自動安裝及啟用，但這並不意味著您會在完成安裝 Microsoft Lync Server 2013 時，自動開始收集監控資料。</span><span class="sxs-lookup"><span data-stu-id="5e1c9-104">Although the unified data collection agents are automatically installed and activated on each Front End server, that does not mean that you will automatically begin to collect monitoring data the moment you finish installing Microsoft Lync Server 2013.</span></span> <span data-ttu-id="5e1c9-105">您還必須執行下列兩個動作：將前端伺服器/前端集區與監控資料庫建立關聯，且您必須啟用全域範圍及/或網站範圍的詳細通話記錄 (CDR) 及/或經驗品質 (QoE) 監視。</span><span class="sxs-lookup"><span data-stu-id="5e1c9-105">Instead, you must do two things: you must associate your Front End servers/Front End pools with a monitoring database, and you must enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global scope and/or the site scope.</span></span>

<span data-ttu-id="5e1c9-106">如需將前端伺服器或前端集區與監控資料庫相關聯的逐步指示，請參閱部署指南中的主題：將 [監視存放區與前端集區相關聯的 Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) 。</span><span class="sxs-lookup"><span data-stu-id="5e1c9-106">For step-by-step instructions on associating Front End servers or Front End pools with a monitoring database, see the topic [Associating a monitoring store with a Front End pool in Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) in the Deployment guide.</span></span> <span data-ttu-id="5e1c9-107">即使建立好這些關聯並發行新的 Lync Server 拓撲之後，您還是不能收集監視資料。</span><span class="sxs-lookup"><span data-stu-id="5e1c9-107">After these associations have been made, and after your new Lync Server topology has been published, you will still not be able to collect monitoring data.</span></span> <span data-ttu-id="5e1c9-108">這是因為在您安裝 Lync Server 2013 時，預設會停用 CDR 和 QoE 資料收集。</span><span class="sxs-lookup"><span data-stu-id="5e1c9-108">That's because, by default, both CDR and QoE data collection is disabled when you install Lync Server 2013.</span></span>

<span data-ttu-id="5e1c9-109">若要開始收集資料，您必須啟用 CDR 及/或 QoE 監視。</span><span class="sxs-lookup"><span data-stu-id="5e1c9-109">In order to begin data collection you will need to enable CDR and/or QoE monitoring.</span></span> <span data-ttu-id="5e1c9-110"> (請注意，您不需要同時啟用 CDR 和 QoE 監控;如果您願意，您可以啟用一種監控類型，讓其他類型保持停用。 ) 若要在全域範圍啟用 CDR 監控，請在 Lync Server 管理命令介面中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="5e1c9-110">(Note that you do not have to enable both CDR and QoE monitoring; if you prefer, you can enable one type of monitoring while leaving the other type disabled.) To enable CDR monitoring at the global scope run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="5e1c9-111">或者，您可以從 Lync Server 2013 控制台中啟用 CDR 監控。</span><span class="sxs-lookup"><span data-stu-id="5e1c9-111">Alternatively, you can enable CDR monitoring from within the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="5e1c9-112">在 [Lync Server 控制台] 中，完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="5e1c9-112">From within the Lync Server Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="5e1c9-113">按一下 [監視]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5e1c9-113">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="5e1c9-114">在 [詳細通話記錄]\*\*\*\* 索引標籤上，按兩下 [全域]\*\*\*\* 設定。</span><span class="sxs-lookup"><span data-stu-id="5e1c9-114">On the **Call Detail Recording** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="5e1c9-115">在 [編輯詳細通話記錄 (CDR) 設定]\*\*\*\* 窗格中，選取 [啟用 CDR 監視]\*\*\*\*，然後按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5e1c9-115">In the **Edit Call Detail Recording (CDR) Setting** pane, select **Enable monitoring of CDRs** and then click **Commit**.</span></span>

<span data-ttu-id="5e1c9-116">若要在全域範圍啟用 QoE 監視，請在 Lync Server 管理命令介面中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="5e1c9-116">To enable QoE monitoring at the global scope, run this command from within the Lync Server Management Shell:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

<span data-ttu-id="5e1c9-117">如果您願意，也可以在 Lync Server 控制台中啟用 QoE 監視。</span><span class="sxs-lookup"><span data-stu-id="5e1c9-117">If you prefer, you can also enable QoE monitoring from within the Lync Server Control Panel.</span></span> <span data-ttu-id="5e1c9-118">請從控制台，完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="5e1c9-118">From within the Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="5e1c9-119">按一下 [監視]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5e1c9-119">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="5e1c9-120">在 [經驗品質資料]\*\*\*\* 索引標籤上，按兩下 [全域]\*\*\*\* 設定。</span><span class="sxs-lookup"><span data-stu-id="5e1c9-120">On the **Quality of Experience Data** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="5e1c9-121">在 [編輯經驗品質 (QoE) 設定]\*\*\*\* 窗格中，選取 [啟用 QoE 資料監視]\*\*\*\*，然後按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5e1c9-121">In the **Edit Quality of Experience (QoE) Setting** pane, select **Enable monitoring of QoE data** and then click **Commit**.</span></span>

<span data-ttu-id="5e1c9-122">如前所述，上述的範例可啟用全域範圍的監視；也就是說，其可啟用您整個組織的 CDR 和 QoE 監視。</span><span class="sxs-lookup"><span data-stu-id="5e1c9-122">As noted, the preceding examples enable monitoring at the global scope; that is, they enable CDR and QoE monitoring throughout your organization.</span></span> <span data-ttu-id="5e1c9-123">此外，您也可以在網站範圍建立個別的 CDR 和 QoE 組態設定，然後再分別針對每個網站啟用或停用監視。</span><span class="sxs-lookup"><span data-stu-id="5e1c9-123">Alternatively, you can create separate CDR and QoE configuration settings at the site scope, and then selectively enable or disable monitoring for each site.</span></span> <span data-ttu-id="5e1c9-124">例如，您可以啟用 Redmond 網站的 CDR 監視，然後停用 Dublin 網站的 CDR 監視。</span><span class="sxs-lookup"><span data-stu-id="5e1c9-124">For example, you could enable CDR monitoring for your Redmond site, yet disable CDR monitoring for your Dublin site.</span></span> <span data-ttu-id="5e1c9-125">如需管理監控設定設定的詳細資訊，請參閱部署指南主題， [設定 Lync Server 2013 中的詳細通話記錄及經驗品質設定](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="5e1c9-125">For more information on managing your monitoring configuration settings, see the Deployment guide topic [Configuring call detail recording and Quality of Experience settings in Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


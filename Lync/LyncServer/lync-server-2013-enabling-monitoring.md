---
title: Lync Server 2013：啟用監視
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2b13028390328e93a9e90636962dedea8ea8ec9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-monitoring-in-lync-server-2013"></a><span data-ttu-id="04dc9-102">在 Lync Server 2013 中啟用監視</span><span class="sxs-lookup"><span data-stu-id="04dc9-102">Enabling monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04dc9-103">_**主題上次修改日期：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="04dc9-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="04dc9-104">雖然整合的資料收集代理程式會在每個前端伺服器上自動安裝並啟用，這並不表示您會在完成安裝 Microsoft Lync Server 2013 的時刻，自動開始收集監視資料。</span><span class="sxs-lookup"><span data-stu-id="04dc9-104">Although the unified data collection agents are automatically installed and activated on each Front End server, that does not mean that you will automatically begin to collect monitoring data the moment you finish installing Microsoft Lync Server 2013.</span></span> <span data-ttu-id="04dc9-105">相反地，您必須執行兩個動作：您必須將前端伺服器/前端池與監控資料庫建立關聯，而且您必須啟用 [呼叫詳細資料錄製（CDR）] 和/或 [（QoE）] （在全域範圍和/或網站範圍中）的監視品質（）。</span><span class="sxs-lookup"><span data-stu-id="04dc9-105">Instead, you must do two things: you must associate your Front End servers/Front End pools with a monitoring database, and you must enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global scope and/or the site scope.</span></span>

<span data-ttu-id="04dc9-106">如需將前端伺服器或頂層池與監視資料庫相關聯的逐步指示，請參閱部署指南中的[使用 Lync Server 2013 中的 [監視存儲] 與 [前端] 池關聯](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md)的主題。</span><span class="sxs-lookup"><span data-stu-id="04dc9-106">For step-by-step instructions on associating Front End servers or Front End pools with a monitoring database, see the topic [Associating a monitoring store with a Front End pool in Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) in the Deployment guide.</span></span> <span data-ttu-id="04dc9-107">建立這些關聯之後，且在您新的 Lync Server 拓撲發佈之後，您仍然無法收集監視資料。</span><span class="sxs-lookup"><span data-stu-id="04dc9-107">After these associations have been made, and after your new Lync Server topology has been published, you will still not be able to collect monitoring data.</span></span> <span data-ttu-id="04dc9-108">這是因為，在您安裝 Lync Server 2013 時，會停用 CDR 與 QoE 資料收集。</span><span class="sxs-lookup"><span data-stu-id="04dc9-108">That's because, by default, both CDR and QoE data collection is disabled when you install Lync Server 2013.</span></span>

<span data-ttu-id="04dc9-109">若要開始收集資料，您需要啟用 CDR 和/或 QoE 監視。</span><span class="sxs-lookup"><span data-stu-id="04dc9-109">In order to begin data collection you will need to enable CDR and/or QoE monitoring.</span></span> <span data-ttu-id="04dc9-110">（請注意，您不需要同時啟用 CDR 與 QoE 監視; 如果您想要的話，您可以啟用一種監視類型，讓其他類型保持停用。）若要在全域範圍啟用 CDR 監視，請在 Lync Server 管理命令介面中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="04dc9-110">(Note that you do not have to enable both CDR and QoE monitoring; if you prefer, you can enable one type of monitoring while leaving the other type disabled.) To enable CDR monitoring at the global scope run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="04dc9-111">或者，您可以在 Lync Server 2013 的 [控制台] 中啟用 CDR 監視。</span><span class="sxs-lookup"><span data-stu-id="04dc9-111">Alternatively, you can enable CDR monitoring from within the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="04dc9-112">在 Lync Server [控制台] 中，完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="04dc9-112">From within the Lync Server Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="04dc9-113">按一下 [**監視**]。</span><span class="sxs-lookup"><span data-stu-id="04dc9-113">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="04dc9-114">在 [**通話詳細資料記錄**] 索引標籤上，按兩下 [**全域**] 設定。</span><span class="sxs-lookup"><span data-stu-id="04dc9-114">On the **Call Detail Recording** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="04dc9-115">在 [**編輯通話詳細資料錄製（CDR）] 設定**窗格中，選取 [**啟用 CDRs 監視**]，然後按一下 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="04dc9-115">In the **Edit Call Detail Recording (CDR) Setting** pane, select **Enable monitoring of CDRs** and then click **Commit**.</span></span>

<span data-ttu-id="04dc9-116">若要在全域範圍中啟用 QoE 監視，請在 Lync Server 管理命令介面內執行此命令：</span><span class="sxs-lookup"><span data-stu-id="04dc9-116">To enable QoE monitoring at the global scope, run this command from within the Lync Server Management Shell:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

<span data-ttu-id="04dc9-117">如果您想要的話，您也可以在 Lync Server 的 [控制台] 中啟用 QoE 監視。</span><span class="sxs-lookup"><span data-stu-id="04dc9-117">If you prefer, you can also enable QoE monitoring from within the Lync Server Control Panel.</span></span> <span data-ttu-id="04dc9-118">從 [控制] 面板中，完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="04dc9-118">From within the Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="04dc9-119">按一下 [**監視**]。</span><span class="sxs-lookup"><span data-stu-id="04dc9-119">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="04dc9-120">在 [**體驗品質**] 的 [資料] 索引標籤上，按兩下 [**全域**] 設定。</span><span class="sxs-lookup"><span data-stu-id="04dc9-120">On the **Quality of Experience Data** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="04dc9-121">在 [**編輯體驗品質（QoE）] 設定**窗格中，選取 [**啟用 QoE 資料的監視**]，然後按一下 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="04dc9-121">In the **Edit Quality of Experience (QoE) Setting** pane, select **Enable monitoring of QoE data** and then click **Commit**.</span></span>

<span data-ttu-id="04dc9-122">如前所述，前面的範例可在全域範圍內啟用監視;也就是說，它們可在整個組織中啟用 CDR 與 QoE 監視。</span><span class="sxs-lookup"><span data-stu-id="04dc9-122">As noted, the preceding examples enable monitoring at the global scope; that is, they enable CDR and QoE monitoring throughout your organization.</span></span> <span data-ttu-id="04dc9-123">或者，您可以在網站範圍中建立個別的 CDR 及 QoE 設定設定，然後有選擇性地針對每個網站啟用或停用監視。</span><span class="sxs-lookup"><span data-stu-id="04dc9-123">Alternatively, you can create separate CDR and QoE configuration settings at the site scope, and then selectively enable or disable monitoring for each site.</span></span> <span data-ttu-id="04dc9-124">例如，您可以為雷德蒙的網站啟用 CDR 監視，但卻停用了您的都柏林網站的 CDR 監視。</span><span class="sxs-lookup"><span data-stu-id="04dc9-124">For example, you could enable CDR monitoring for your Redmond site, yet disable CDR monitoring for your Dublin site.</span></span> <span data-ttu-id="04dc9-125">如需管理監視設定設定的詳細資訊，請參閱在[Lync Server 2013 中設定通話詳細資料錄製和體驗品質設定](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md)的 [部署指南] 主題。</span><span class="sxs-lookup"><span data-stu-id="04dc9-125">For more information on managing your monitoring configuration settings, see the Deployment guide topic [Configuring call detail recording and Quality of Experience settings in Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


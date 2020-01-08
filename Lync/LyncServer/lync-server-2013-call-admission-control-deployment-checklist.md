---
title: Lync Server 2013：呼叫許可控制部署檢查清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdda2e5231beb9f8303684ff29075c6322654945
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975805"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="dc9bd-102">Lync Server 2013 的呼叫許可控制部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="dc9bd-102">Call admission control deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc9bd-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="dc9bd-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="dc9bd-104">使用下列檢查清單來確認您已完成所有必要的設定工作，以部署呼叫許可控制（CAC）。</span><span class="sxs-lookup"><span data-stu-id="dc9bd-104">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy call admission control (CAC).</span></span>

  - <span data-ttu-id="dc9bd-105">如果一或多個邊緣伺服器已部署，則必須將每個外部介面 IP 位址新增到 [網路設定] 中的子網清單中，位元遮罩為32。</span><span class="sxs-lookup"><span data-stu-id="dc9bd-105">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="dc9bd-106">您也應該將這個子網（IP 位址）與「A/V Edge」服務所部署之地理位置的 [網路 site ID] 建立關聯。</span><span class="sxs-lookup"><span data-stu-id="dc9bd-106">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dc9bd-107">Edge 伺服器不是實現 CAC 所必需的。</span><span class="sxs-lookup"><span data-stu-id="dc9bd-107">Edge servers are not required to implement CAC.</span></span>

    
    </div>

  - <span data-ttu-id="dc9bd-108">確認 CAC 已啟用，不論是透過 Lync Server [控制台]，或是執行在[Lync server 2013 的 [啟用呼叫許可控制](lync-server-2013-enable-call-admission-control.md)] 中指定的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dc9bd-108">Make sure that CAC is enabled, either through Lync Server Control Panel or by running the cmdlet as specified in [Enable call admission control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span></span>

  - <span data-ttu-id="dc9bd-109">確定所有中央網站都已啟用 CAC。</span><span class="sxs-lookup"><span data-stu-id="dc9bd-109">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="dc9bd-110">這可以透過拓撲產生器完成。</span><span class="sxs-lookup"><span data-stu-id="dc9bd-110">This can be done through the Topology Builder.</span></span> <span data-ttu-id="dc9bd-111">如果您發佈時產生警告，*請勿*忽略。</span><span class="sxs-lookup"><span data-stu-id="dc9bd-111">If a warning is generated when you publish, *do not* ignore it.</span></span>

  - <span data-ttu-id="dc9bd-112">確認在商業網路中管理的所有子網都已設定在 [網路設定] 中。</span><span class="sxs-lookup"><span data-stu-id="dc9bd-112">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="dc9bd-113">在[Lync Server 2013 中將子網與網路網站建立](lync-server-2013-associate-a-subnet-with-a-network-site.md)關聯，也必須將每個子網與網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="dc9bd-113">It is also essential that every subnet be associated to a network site, as explained in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

  - <span data-ttu-id="dc9bd-114">確定所有前端伺服器、Survivable 分支裝置（SBAs）、音訊/視訊會議伺服器（如果在個別的池中），以及在 [網路設定] 設定中設定了轉送伺服器的子網或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="dc9bd-114">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


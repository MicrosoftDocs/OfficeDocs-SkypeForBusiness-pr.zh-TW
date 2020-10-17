---
title: Lync Server 2013：通話許可控制的部署檢查清單
description: Lync Server 2013：通話許可控制部署檢查清單。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db7a69bda3048f93089a47b43a0b433946b783f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569189"
---
# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="3e56f-103">Lync Server 2013 的通話許可控制部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="3e56f-103">Call admission control deployment checklist for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e56f-104">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="3e56f-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="3e56f-105">使用下列檢查清單，確認您已完成所有必要的設定工作，以將通話許可控制部署 (CAC) 。</span><span class="sxs-lookup"><span data-stu-id="3e56f-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy call admission control (CAC).</span></span>

  - <span data-ttu-id="3e56f-106">如果已部署一或多部 Edge Server，則每個外部介面 IP 位址都必須新增至網路設定設定中的子網清單，而位元遮罩為32。</span><span class="sxs-lookup"><span data-stu-id="3e56f-106">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="3e56f-107">您也應該針對部署 A/V Edge service 的地理位置，將該子網 (IP 位址) 與網路網站識別碼產生關聯。</span><span class="sxs-lookup"><span data-stu-id="3e56f-107">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e56f-108">不需要 Edge server 來執行 CAC。</span><span class="sxs-lookup"><span data-stu-id="3e56f-108">Edge servers are not required to implement CAC.</span></span>

    
    </div>

  - <span data-ttu-id="3e56f-109">確定 CAC 已啟用，不論是透過 Lync Server 控制台，還是透過在 Lync Server 2013 中的 [ [啟用通話許可控制](lync-server-2013-enable-call-admission-control.md)] 中所指定的方式執行。</span><span class="sxs-lookup"><span data-stu-id="3e56f-109">Make sure that CAC is enabled, either through Lync Server Control Panel or by running the cmdlet as specified in [Enable call admission control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span></span>

  - <span data-ttu-id="3e56f-110">確定所有中央網站皆已啟用 CAC。</span><span class="sxs-lookup"><span data-stu-id="3e56f-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="3e56f-111">這可以透過拓撲產生器來完成。</span><span class="sxs-lookup"><span data-stu-id="3e56f-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="3e56f-112">如果您發佈時產生警告， *請勿* 略過。</span><span class="sxs-lookup"><span data-stu-id="3e56f-112">If a warning is generated when you publish, *do not* ignore it.</span></span>

  - <span data-ttu-id="3e56f-113">請確定 [網路設定] 中已設定商業網路中所管理的所有子網。</span><span class="sxs-lookup"><span data-stu-id="3e56f-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="3e56f-114">將每個子網與網路網站相關聯也是必要的，如在 [Lync Server 2013 中將子網與網路網站關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)的說明。</span><span class="sxs-lookup"><span data-stu-id="3e56f-114">It is also essential that every subnet be associated to a network site, as explained in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

  - <span data-ttu-id="3e56f-115">請確定所有前端伺服器、Survivable 分支裝置 (Sba) 、Audio/Video 會議服務器 (如在不同的集區) 中，以及在 [網路設定] 中設定轉送伺服器時的子網或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3e56f-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


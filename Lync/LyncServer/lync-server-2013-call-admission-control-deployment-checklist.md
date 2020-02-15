---
title: Lync Server 2013： 通話許可控制部署檢查清單
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
ms.openlocfilehash: 1a8dc32eb017baf832128301b9639aefe23ae4ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="b1b04-102">Lync Server 2013 的通話許可控制部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="b1b04-102">Call admission control deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1b04-103">_**主題上次修改日期：** 2012年-10-22_</span><span class="sxs-lookup"><span data-stu-id="b1b04-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="b1b04-104">若要確認您已完成所有必要的組態工作，以部署通話許可控制 (CAC) 使用下列檢查清單。</span><span class="sxs-lookup"><span data-stu-id="b1b04-104">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy call admission control (CAC).</span></span>

  - <span data-ttu-id="b1b04-105">如果部署一或多個 Edge Server，每個外部介面 IP 位址必須新增至 [子網路] 清單中的網路組態設定，32 位元遮罩。</span><span class="sxs-lookup"><span data-stu-id="b1b04-105">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="b1b04-106">您應該也關聯此子網路 （IP 位址） 的地理位置的網路網站識別碼其中 A / V Edge service 部署。</span><span class="sxs-lookup"><span data-stu-id="b1b04-106">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b1b04-107">若要實作 CAC 不需要 edge server。</span><span class="sxs-lookup"><span data-stu-id="b1b04-107">Edge servers are not required to implement CAC.</span></span>

    
    </div>

  - <span data-ttu-id="b1b04-108">請務必啟用 CAC，透過 Lync Server Control Panel 或執行[Lync Server 2013 中的啟用通話許可控制](lync-server-2013-enable-call-admission-control.md)中所指定的指令程式。</span><span class="sxs-lookup"><span data-stu-id="b1b04-108">Make sure that CAC is enabled, either through Lync Server Control Panel or by running the cmdlet as specified in [Enable call admission control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span></span>

  - <span data-ttu-id="b1b04-109">請確定所有的中央網站中已啟用 CAC。</span><span class="sxs-lookup"><span data-stu-id="b1b04-109">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="b1b04-110">這可以透過 [拓撲產生器]。</span><span class="sxs-lookup"><span data-stu-id="b1b04-110">This can be done through the Topology Builder.</span></span> <span data-ttu-id="b1b04-111">如果當您發佈時，會產生警告，*不*忽略它。</span><span class="sxs-lookup"><span data-stu-id="b1b04-111">If a warning is generated when you publish, *do not* ignore it.</span></span>

  - <span data-ttu-id="b1b04-112">請確定網路組態設定中的設定受管理的企業網路中的所有子網路。</span><span class="sxs-lookup"><span data-stu-id="b1b04-112">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="b1b04-113">它也是不可或缺的每一個子網路是與相關聯的網路網站，[建立關聯的子網路與網路網站在 Lync Server 2013 中](lync-server-2013-associate-a-subnet-with-a-network-site.md)所述。</span><span class="sxs-lookup"><span data-stu-id="b1b04-113">It is also essential that every subnet be associated to a network site, as explained in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

  - <span data-ttu-id="b1b04-114">請確定所有前端伺服器、 Survivable Branch Appliance (Sba)、 音訊/視訊會議伺服器 （如果位於不同集區），和中繼伺服器的 IP 位址的子網路的網路組態設定中設定。</span><span class="sxs-lookup"><span data-stu-id="b1b04-114">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


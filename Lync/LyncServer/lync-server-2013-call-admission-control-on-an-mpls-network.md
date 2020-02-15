---
title: MPLS 網路上的 Lync Server 2013： 通話許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on an MPLS network
ms:assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398168(v=OCS.15)
ms:contentKeyID: 48183387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8da29eb8825154f3e149d56b6bd9e4c4e7452652
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-an-mpls-network-with-lync-server-2013"></a><span data-ttu-id="8febe-102">MPLS 網路與 Lync Server 2013 上的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="8febe-102">Call admission control on an MPLS network with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8febe-103">_**主題上次修改日期：** 2012年-09-22_</span><span class="sxs-lookup"><span data-stu-id="8febe-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="8febe-p101">在多重通訊協定標籤交換 (Multiprotocol Label Switching，MPLS) 網路中，所有網站都由完整網狀 (Full-Mesh) 連線。也就是，所有網站都會直接連線至網際網路服務提供者的 MPLS 骨幹，而且每個網站都已佈建要透過 MPLS 雲端的 WAN 連結使用的頻寬。沒有網路集線器或中央網站可控制 IP 路由。下圖顯示以 MPLS 技術為基礎的簡易網路。</span><span class="sxs-lookup"><span data-stu-id="8febe-p101">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="8febe-108">**MPLS 網路範例**</span><span class="sxs-lookup"><span data-stu-id="8febe-108">**Example MPLS network**</span></span>

<span data-ttu-id="8febe-109">![使用 MPLS 的 CAC](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "使用 MPLS 的 CAC")</span><span class="sxs-lookup"><span data-stu-id="8febe-109">![CAC with MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "CAC with MPLS")</span></span>

<span data-ttu-id="8febe-p102">若要在 MPLS 網路中部署通話許可控制 (CAC)，您可建立網路地區代表 MPLS 雲端，以及建立網路網站代表每個 MPLS 衛星網站。下圖說明如何設定網路地區和網路網站以代表上圖中的 MPLS 網路範例。整體頻寬限制和頻寬工作階段限制都是以從每個網路網站連至代表 MPLS 雲端之網路地區的 WAN 連結為基礎。</span><span class="sxs-lookup"><span data-stu-id="8febe-p102">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="8febe-113">**MPLS 網路的網路地區和網路網站**</span><span class="sxs-lookup"><span data-stu-id="8febe-113">**Network region and network sites for an MPLS network**</span></span>

<span data-ttu-id="8febe-114">![通話許可控制 (CAC) 具有 MPLS 圖表](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "通話許可控制 (CAC) 具有 MPLS 圖表")</span><span class="sxs-lookup"><span data-stu-id="8febe-114">![Call Admission Control (CAC) with MPLS diagram](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Call Admission Control (CAC) with MPLS diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>


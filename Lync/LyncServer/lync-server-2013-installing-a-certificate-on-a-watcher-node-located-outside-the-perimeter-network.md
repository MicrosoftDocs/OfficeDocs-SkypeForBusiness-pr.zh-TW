---
title: Lync Server 2013：在周邊網路以外的監視節點上安裝憑證
description: Lync Server 2013：在周邊網路以外的監視節點上安裝憑證。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66f40886e9784b5bd4182a60b955745b5daf2034
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574029"
---
# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a><span data-ttu-id="aacc5-103">在 Lync Server 2013 周邊網路以外的監看員節點上安裝憑證</span><span class="sxs-lookup"><span data-stu-id="aacc5-103">Installing a certificate on a watcher node located outside the perimeter network of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aacc5-104">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="aacc5-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="aacc5-105">在周邊網路中執行的 System Center Operations Manager 代理 (例如 Lync Server Edge Server) （如外部綜合交易觀察器節點) 或跨 Active Directory 網域服務信任界限） (以外，可能需要設定 System Center Operations Manager 閘道伺服器。</span><span class="sxs-lookup"><span data-stu-id="aacc5-105">System Center Operations Manager agents running in a perimeter network (such as a Lync Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory Domain Services trust boundary, might require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="aacc5-106">這個伺服器角色可讓與 Root Management Server 沒有任何信任關係的代理程式發出通知。</span><span class="sxs-lookup"><span data-stu-id="aacc5-106">This server role allows agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="aacc5-107">如需詳細資訊，請參閱 System Center Operations Manager 中的「管理 Operations Manager 中的閘道伺服器2007」。 TechNet 程式庫位置 [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703) 。</span><span class="sxs-lookup"><span data-stu-id="aacc5-107">For details, see "Managing Gateway Servers in Operations Manager 2007" in the System Center Operations Manager TechNet Library at [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703).</span></span>

<span data-ttu-id="aacc5-108">如果您在這些位置中的其中一個位置部署代理程式，您也需要要求及設定憑證，以啟用監看員節點，將提醒傳送至 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="aacc5-108">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="aacc5-109">為了簡化這個程序，Operations Manager 團隊已建立一套公用程式，讓您要求正確類型的憑證，並安裝於監控程式節點電腦上。</span><span class="sxs-lookup"><span data-stu-id="aacc5-109">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="aacc5-110">如需詳細資訊，以及若要下載這些公用程式，請參閱「使用憑證產生嚮導輕鬆取得非網域加入的代理程式的憑證」博客文章 [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421) 。</span><span class="sxs-lookup"><span data-stu-id="aacc5-110">For details, and to download these utilities, see the "Obtaining Certificates for Non-Domain Joined Agents Made Easy With Certificate Generation Wizard" blog article at [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


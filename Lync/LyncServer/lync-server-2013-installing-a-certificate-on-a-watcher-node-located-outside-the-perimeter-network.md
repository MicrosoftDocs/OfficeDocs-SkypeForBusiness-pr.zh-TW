---
title: Lync Server 2013： 在位於周邊網路外的監看員節點上安裝憑證
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
ms.openlocfilehash: 74d89b14b783e2b78050b2db8e71a1009c974384
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029544"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a><span data-ttu-id="6392b-102">位於 Lync Server 2013 的周邊網路外的監看員節點上安裝憑證</span><span class="sxs-lookup"><span data-stu-id="6392b-102">Installing a certificate on a watcher node located outside the perimeter network of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6392b-103">_**主題上次修改日期：** 2012年-10-22_</span><span class="sxs-lookup"><span data-stu-id="6392b-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="6392b-104">System Center Operations Manager 代理程式執行在周邊網路中 （例如，Lync Server Edge Server)，外部企業版 （例如的外部的綜合交易監看員節點），或跨 Active Directory 網域服務信任界限，可能會需要系統中心 Operations Manager 閘道伺服器的設定。</span><span class="sxs-lookup"><span data-stu-id="6392b-104">System Center Operations Manager agents running in a perimeter network (such as a Lync Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory Domain Services trust boundary, might require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="6392b-105">這個伺服器角色可讓與 Root Management Server 沒有任何信任關係的代理程式發出通知。</span><span class="sxs-lookup"><span data-stu-id="6392b-105">This server role allows agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="6392b-106">如需詳細資訊，請參閱 「 管理閘道 Servers in Operations Manager 2007 」 在系統管理中心 Operations Manager TechNet Library [http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703)。</span><span class="sxs-lookup"><span data-stu-id="6392b-106">For details, see "Managing Gateway Servers in Operations Manager 2007" in the System Center Operations Manager TechNet Library at [http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703).</span></span>

<span data-ttu-id="6392b-107">如果您部署中其中一個位置的代理程式，您還必須要求以及設定可讓要傳送提醒給 System Center Operations Manager 的監看員節點的憑證。</span><span class="sxs-lookup"><span data-stu-id="6392b-107">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="6392b-108">為了簡化這個程序，Operations Manager 團隊已建立一套公用程式，讓您要求正確類型的憑證，並安裝於監控程式節點電腦上。</span><span class="sxs-lookup"><span data-stu-id="6392b-108">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="6392b-109">如需詳細資訊，以及下載這些公用程式，請參閱位於的 「 取得憑證的非網域加入代理程式進行簡單與憑證產生精靈 」 部落格文章[http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421)。</span><span class="sxs-lookup"><span data-stu-id="6392b-109">For details, and to download these utilities, see the "Obtaining Certificates for Non-Domain Joined Agents Made Easy With Certificate Generation Wizard" blog article at [http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 設定試驗集區部署的 DNS 記錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49733855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 549aa706700d7f2163e9149d8dd29311141968e0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="0afb0-102">設定試驗集區部署的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="0afb0-102">Configure DNS records for pilot pool deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0afb0-103">_**主題上次修改日期：** 2012年-09-29_</span><span class="sxs-lookup"><span data-stu-id="0afb0-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="0afb0-104">之前部署 Lync Server 2013 試驗集區，您必須更新試驗集區的 DNS 主機的項目。</span><span class="sxs-lookup"><span data-stu-id="0afb0-104">Prior to deploying the Lync Server 2013 pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="0afb0-105">若要順利完成此程序，您應該伺服器或網域的 Domain Admins 群組成員或 DnsAdmins 群組成員登入。</span><span class="sxs-lookup"><span data-stu-id="0afb0-105">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="0afb0-106">**設定 DNS 主機 A 記錄**</span><span class="sxs-lookup"><span data-stu-id="0afb0-106">**To configure DNS Host A records**</span></span>

1.  <span data-ttu-id="0afb0-107">在網域名稱系統 (DNS) 伺服器上，依序按一下 **[開始]**、**[系統管理工具]** 和 **[DNS]**。</span><span class="sxs-lookup"><span data-stu-id="0afb0-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="0afb0-108">在您網域的主控台樹狀目錄中，展開 [**正向對應區域**，，然後在要安裝 Lync Server 2013 的網域上按一下滑鼠右鍵。</span><span class="sxs-lookup"><span data-stu-id="0afb0-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="0afb0-109">按一下 **[新增主機 (A 或 AAAA)]**。</span><span class="sxs-lookup"><span data-stu-id="0afb0-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="0afb0-110">按一下 [**名稱**]，輸入 （網域會假設該名稱的區域來記錄中所定義，而不需輸入為 A 記錄的一部分） 的 Lync Server 2013 集區的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="0afb0-110">Click **Name**, type the host name for the Lync Server 2013 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="0afb0-111">按一下 [ **IP 位址**] 中，輸入前端集區的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0afb0-111">Click **IP Address**, type the IP address for the Front End pool.</span></span>

6.  <span data-ttu-id="0afb0-112">按一下 **[新增主機]**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="0afb0-112">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="0afb0-113">完成時，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="0afb0-113">When you are finished, click **Done**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


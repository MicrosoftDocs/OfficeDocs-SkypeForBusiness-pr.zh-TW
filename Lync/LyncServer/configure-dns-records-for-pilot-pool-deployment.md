---
title: 為試驗集區部署設定 DNS 記錄
description: 設定試驗集區部署的 DNS 記錄。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 1e41e163432ba910f6d083cc508e8ad8c9f2006d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548489"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="9363a-103">為試驗集區部署設定 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="9363a-103">Configure DNS records for pilot pool deployment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9363a-104">_**主題上次修改日期：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="9363a-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="9363a-105">在部署 Lync Server 2013 試驗集區之前，您必須更新 DNS 主機試驗集區的專案。</span><span class="sxs-lookup"><span data-stu-id="9363a-105">Prior to deploying the Lync Server 2013 pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="9363a-106">若要順利完成此程式，您應該以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。</span><span class="sxs-lookup"><span data-stu-id="9363a-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="9363a-107">**設定 DNS 主機 A 記錄**</span><span class="sxs-lookup"><span data-stu-id="9363a-107">**To configure DNS Host A records**</span></span>

1.  <span data-ttu-id="9363a-108">在網域名稱系統 (DNS) 伺服器上，依序按一下 **[開始]**、**[系統管理工具]** 和 **[DNS]**。</span><span class="sxs-lookup"><span data-stu-id="9363a-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="9363a-109">在您網域的主控台樹中，展開 [ **正向對應區域**]，然後在將安裝 Lync Server 2013 的網域上按一下滑鼠右鍵。</span><span class="sxs-lookup"><span data-stu-id="9363a-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="9363a-110">按一下 **[新增主機 (A 或 AAAA)]**。</span><span class="sxs-lookup"><span data-stu-id="9363a-110">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="9363a-111">依序按一下 [ **名稱**]、[Lync Server 2013 集區的主機名稱] (功能變數名稱會從記錄定義所在的區域來假設，而不需要在 A 記錄) 中輸入。</span><span class="sxs-lookup"><span data-stu-id="9363a-111">Click **Name**, type the host name for the Lync Server 2013 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="9363a-112">按一下 [ **IP 位址**]，輸入前端集區的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="9363a-112">Click **IP Address**, type the IP address for the Front End pool.</span></span>

6.  <span data-ttu-id="9363a-113">按一下 **[新增主機]**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="9363a-113">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="9363a-114">完成時，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="9363a-114">When you are finished, click **Done**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


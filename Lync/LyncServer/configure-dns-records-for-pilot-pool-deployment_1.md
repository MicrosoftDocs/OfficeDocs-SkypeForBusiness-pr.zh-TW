---
title: 設定試驗集區部署的 DNS 記錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: 5c7a6e10-e1e9-4479-9bf9-d4a3e2e09ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688072(v=OCS.15)
ms:contentKeyID: 49733666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 612857ba1a0ec599b0011ab5779cb7fc4b5a0615
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="96fcf-102">設定試驗集區部署的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="96fcf-102">Configure DNS records for pilot pool deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96fcf-103">_**主題上次修改日期：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="96fcf-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="96fcf-104">在部署 Lync Server 2013 試驗池之前，您必須更新 DNS 主機以取得試驗池的專案。</span><span class="sxs-lookup"><span data-stu-id="96fcf-104">Prior to deploying the Lync Server 2013 pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="96fcf-105">若要成功完成此程式，您應該以網域系統管理員群組或 DnsAdmins 群組的成員的身分登入伺服器或網域。</span><span class="sxs-lookup"><span data-stu-id="96fcf-105">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="96fcf-106">**設定 DNS 主機 A 記錄**</span><span class="sxs-lookup"><span data-stu-id="96fcf-106">**To configure DNS Host A records**</span></span>

1.  <span data-ttu-id="96fcf-107">在 [網域名稱系統（DNS）] 伺服器上，按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="96fcf-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="96fcf-108">在您網域的 [主控台樹] 中，展開 [**轉寄查閱區域**]，然後以滑鼠右鍵按一下將安裝 Lync Server 2013 的網域。</span><span class="sxs-lookup"><span data-stu-id="96fcf-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="96fcf-109">按一下 **[新增主機（A 或 AAAA）**]。</span><span class="sxs-lookup"><span data-stu-id="96fcf-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="96fcf-110">按一下 [**名稱**]，輸入該池的主機名稱（功能變數名稱是從定義該記錄的區域中假設，而且不需要輸入為 A 記錄的一部分）。</span><span class="sxs-lookup"><span data-stu-id="96fcf-110">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="96fcf-111">按一下 [ **IP 位址**]，輸入頂層端池的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="96fcf-111">Click **IP Address**, type the IP address for the Front End pool.</span></span>

6.  <span data-ttu-id="96fcf-112">按一下 [**新增主機**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="96fcf-112">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="96fcf-113">完成後，請按一下 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="96fcf-113">When you are finished, click **Done**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


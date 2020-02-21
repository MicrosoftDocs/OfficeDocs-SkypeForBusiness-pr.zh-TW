---
title: 更新 DNS SRV 記錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49733765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9df74033156e03cf7047b4d4bfbb2dbc83595b9b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a><span data-ttu-id="7018c-102">更新 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="7018c-102">Update DNS SRV records</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7018c-103">_**主題上次修改日期：** 2012年-09-29_</span><span class="sxs-lookup"><span data-stu-id="7018c-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="7018c-104">若要順利完成此程序，您應該伺服器或網域的 Domain Admins 群組成員或 DnsAdmins 群組成員登入。</span><span class="sxs-lookup"><span data-stu-id="7018c-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="7018c-105">本主題說明如何移轉至 Lync Server 2013 之後更新的網域名稱系統 (DNS) 記錄。</span><span class="sxs-lookup"><span data-stu-id="7018c-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="7018c-106">所有使用者已都移至 Lync Server 2013 之後，但解除委任舊版 Office Communications Server 2007 R2 集區或 Director 之前，您必須在每個 SIP 網域的內部部署 DNS 中更新 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="7018c-106">After all users have been moved to Lync Server 2013, but before the legacy Office Communications Server 2007 R2 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="7018c-107">此程序假設您的內部 DNS 有 SIP 使用者網域的區域。</span><span class="sxs-lookup"><span data-stu-id="7018c-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="7018c-108">**若要設定 DNS SRV 記錄**</span><span class="sxs-lookup"><span data-stu-id="7018c-108">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="7018c-109">在 DNS 伺服器上，按一下 [**開始]**、 [**系統管理工具**] 和 [ **DNS**。</span><span class="sxs-lookup"><span data-stu-id="7018c-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="7018c-110">在 [SIP 網域的主控台樹狀目錄，請依序展開 [**正向對應區域**，展開 SIP 網域中安裝 Lync Server 2013，並瀏覽至**\_tcp**設定。</span><span class="sxs-lookup"><span data-stu-id="7018c-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="7018c-111">在右窗格中，以滑鼠右鍵按一下 [ \*\* \_sipinternaltls**並選取 [**內容\*\*]。</span><span class="sxs-lookup"><span data-stu-id="7018c-111">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="7018c-112">在 [**提供這項服務的主機**，更新主機 FQDN 以指向 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="7018c-112">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="7018c-113">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7018c-113">Click **OK**.</span></span>

<span data-ttu-id="7018c-114">**若要確認可以解析前端集區或 Standard Edition server 的 FQDN**</span><span class="sxs-lookup"><span data-stu-id="7018c-114">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="7018c-115">登入網域中的用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="7018c-115">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="7018c-116">按一下 [開始]\*\*\*\*，然後按一下 [執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7018c-116">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="7018c-117">在 [**開啟**] 方塊中輸入**cmd**，，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="7018c-117">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="7018c-118">在命令提示字元處，輸入**nslookup** \<的前端集區 FQDN\>或\<Standard Edition server 的 FQDN\>，然後按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="7018c-118">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="7018c-119">確認您收到的 fqdn 解析為適當的 IP 位址的回覆。</span><span class="sxs-lookup"><span data-stu-id="7018c-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


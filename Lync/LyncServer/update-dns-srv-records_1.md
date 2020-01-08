---
title: 更新 DNS SRV 記錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Update DNS SRV records
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49733765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97ff3eed81a90960444b260bd0ca5b9c4c67022e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a><span data-ttu-id="ee05d-102">更新 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="ee05d-102">Update DNS SRV records</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee05d-103">_**主題上次修改日期：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="ee05d-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="ee05d-104">若要成功完成此程式，您應該以網域系統管理員群組或 DnsAdmins 群組成員的身分登入伺服器或網域。</span><span class="sxs-lookup"><span data-stu-id="ee05d-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="ee05d-105">本主題說明如何在遷移至 Lync Server 2013 之後，更新網域名稱系統（DNS）記錄。</span><span class="sxs-lookup"><span data-stu-id="ee05d-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="ee05d-106">將所有使用者移至 Lync Server 2013 之後，但在解除舊版 Office 通訊伺服器 2007 R2 池或主管之後，您就必須更新每個 SIP 網域之內部 DNS 中的 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="ee05d-106">After all users have been moved to Lync Server 2013, but before the legacy Office Communications Server 2007 R2 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="ee05d-107">這個程式假設您的內部 DNS 擁有您 SIP 使用者網域的區域。</span><span class="sxs-lookup"><span data-stu-id="ee05d-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="ee05d-108">**若要設定 DNS SRV 記錄**</span><span class="sxs-lookup"><span data-stu-id="ee05d-108">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="ee05d-109">在 DNS 伺服器上，按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="ee05d-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="ee05d-110">在您 SIP 網域的 [主控台樹] 中，展開 [**轉寄查閱區域**]，展開已安裝 Lync Server 2013 的 SIP 網域，然後流覽至\*\* \_tcp\*\*設定。</span><span class="sxs-lookup"><span data-stu-id="ee05d-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="ee05d-111">在右窗格中，以滑鼠\*\* \_\*\* 按右鍵 [sipinternaltls]，然後選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="ee05d-111">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="ee05d-112">在**提供此服務的主機**中，更新主機 FQDN 以指向 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="ee05d-112">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="ee05d-113">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ee05d-113">Click **OK**.</span></span>

<span data-ttu-id="ee05d-114">**確認可以解析前端池或標準版伺服器的 FQDN**</span><span class="sxs-lookup"><span data-stu-id="ee05d-114">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="ee05d-115">登入網域中的用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="ee05d-115">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="ee05d-116">按一下 [**開始**]，然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="ee05d-116">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="ee05d-117">在 [**開啟**] 方塊中，輸入**cmd**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ee05d-117">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="ee05d-118">在命令提示字元中， \*\*\*\* \<輸入頂層結束池\>的 nslookup FQDN 或\<標準版伺服器\>的 FQDN，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="ee05d-118">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="ee05d-119">確認您收到的回復會解析為適當的 FQDN IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ee05d-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


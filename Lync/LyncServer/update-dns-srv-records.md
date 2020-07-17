---
title: 更新 DNS SRV 記錄
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85b286355f765342a2c7b240f23e0aac1c7daad6
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a><span data-ttu-id="02e98-102">更新 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="02e98-102">Update DNS SRV records</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02e98-103">_**主題上次修改日期：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="02e98-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="02e98-104">若要順利完成此程式，您應該以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。</span><span class="sxs-lookup"><span data-stu-id="02e98-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="02e98-105">本主題說明如何在遷移至 Lync Server 2013 後，更新網域名稱系統（DNS）記錄。</span><span class="sxs-lookup"><span data-stu-id="02e98-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="02e98-106">將所有使用者移至 Lync Server 2013 之後，但在解除舊版 Lync Server 2010 集區或 Director 之前，您必須針對每個 SIP 網域更新內部 DNS 中的 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="02e98-106">After all users have been moved to Lync Server 2013, but before the legacy Lync Server 2010 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="02e98-107">此程式假設您的內部 DNS 具有您 SIP 使用者網域的區域。</span><span class="sxs-lookup"><span data-stu-id="02e98-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="02e98-108">**設定 DNS SRV 記錄**</span><span class="sxs-lookup"><span data-stu-id="02e98-108">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="02e98-109">在 DNS 伺服器上，按一下 [**開始**]，按一下 [系統**管理工具**]，然後按一下 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="02e98-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="02e98-110">在 SIP 網域的主控台樹中，展開 [**正向對應區域**]，展開 [已安裝 Lync Server 2013 的 SIP 網域]，然後流覽至 [ \*\* \_ tcp\*\* ] 設定。</span><span class="sxs-lookup"><span data-stu-id="02e98-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="02e98-111">在右窗格中，以滑鼠右鍵按一下 [ \*\* \_ sipinternaltls\*\* ]，然後選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="02e98-111">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="02e98-112">在 [**提供這項服務的主機**] 中，將主機 FQDN 更新為指向 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="02e98-112">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="02e98-113">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="02e98-113">Click **OK**.</span></span>

<span data-ttu-id="02e98-114">**確認可解析前端集區或 Standard Edition server 的 FQDN**</span><span class="sxs-lookup"><span data-stu-id="02e98-114">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="02e98-115">登入網域中的用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="02e98-115">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="02e98-116">按一下 [開始]\*\*\*\*，然後按一下 [執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="02e98-116">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="02e98-117">在 [**開啟**] 方塊中輸入**cmd**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="02e98-117">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="02e98-118">在命令提示字元中輸入**nslookup** \<FQDN of the Front End pool\> 或 \<FQDN of the Standard Edition server\> ，然後按 enter 鍵。</span><span class="sxs-lookup"><span data-stu-id="02e98-118">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="02e98-119">請確認您收到的回復可解析為 FQDN 的適當 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="02e98-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


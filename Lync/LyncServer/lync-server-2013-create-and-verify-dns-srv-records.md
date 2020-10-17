---
title: Lync Server 2013：建立並驗證 DNS SRV 記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b80b5dccfeab136f02705264fea985550cb11240
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501720"
---
# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a><span data-ttu-id="3d988-102">在 Lync Server 2013 中建立並驗證 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="3d988-102">Create and verify DNS SRV records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d988-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="3d988-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="3d988-104">若要順利完成此程序，您至少應該以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。</span><span class="sxs-lookup"><span data-stu-id="3d988-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="3d988-105">本主題說明如何在 Lync Server 2013 部署中設定網域名稱系統 (DNS) 記錄，以及自動用戶端登入所需的記錄。</span><span class="sxs-lookup"><span data-stu-id="3d988-105">This topic describes how to configure the Domain Name System (DNS) records that you are required to create in Lync Server 2013 deployments and those required for automatic client sign in.</span></span> <span data-ttu-id="3d988-106">當您建立前端集區時，安裝程式會為集區建立 Active Directory 物件和設定，包括集區的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="3d988-106">When you create a Front End pool, Setup creates Active Directory objects and settings for the pool, including the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="3d988-107">為 Standard Edition server 建立類似的物件和設定。</span><span class="sxs-lookup"><span data-stu-id="3d988-107">Similar objects and settings are created for a Standard Edition server.</span></span> <span data-ttu-id="3d988-108">若要讓用戶端能夠連線至集區或 Standard Edition 伺服器，則必須在 DNS 中登錄集區或 Standard Edition server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3d988-108">For clients to be able to connect to the pool or Standard Edition server, the FQDN of the pool or Standard Edition server must be registered in DNS.</span></span> <span data-ttu-id="3d988-109">您必須在內部 DNS 中為每個 SIP 網域建立 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="3d988-109">You must create DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="3d988-110">此程式假設您的內部 DNS 具有您 SIP 使用者網域的區域。</span><span class="sxs-lookup"><span data-stu-id="3d988-110">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<div>

## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="3d988-111">設定 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="3d988-111">To configure a DNS SRV record</span></span>

1.  <span data-ttu-id="3d988-112">在 DNS 伺服器上，按一下 [ **開始**]，按一下 [系統 **管理工具**]，然後按一下 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="3d988-112">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="3d988-113">在 SIP 網域的主控台樹中，展開 [ **正向對應區域**]，然後在將安裝 Lync Server 2013 的 SIP 網域上按一下滑鼠右鍵。</span><span class="sxs-lookup"><span data-stu-id="3d988-113">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the SIP domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="3d988-114">按一下 [ **其他新記錄**]。</span><span class="sxs-lookup"><span data-stu-id="3d988-114">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="3d988-115">在 [ **選取資源記錄類型**] 中，按一下 [ \*\*服務位置] (SRV) \*\*]，然後按一下 [ **建立記錄**]。</span><span class="sxs-lookup"><span data-stu-id="3d988-115">In **Select a resource record type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="3d988-116">按一下 [**服務**]，然後輸入\*\* \_ sipinternaltls\*\*。</span><span class="sxs-lookup"><span data-stu-id="3d988-116">Click **Service**, and then type **\_sipinternaltls**.</span></span>

6.  <span data-ttu-id="3d988-117">按一下 [**通訊協定**]，然後輸入\*\* \_ tcp\*\*。</span><span class="sxs-lookup"><span data-stu-id="3d988-117">Click **Protocol**, and then type **\_tcp**.</span></span>

7.  <span data-ttu-id="3d988-118">按一下 [ **埠號碼**]，然後輸入 **5061**。</span><span class="sxs-lookup"><span data-stu-id="3d988-118">Click **Port Number**, and then type **5061**.</span></span>

8.  <span data-ttu-id="3d988-119">按一下 [ **提供這項服務的主機**]，然後輸入集區或 Standard Edition SERVER 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3d988-119">Click **Host offering this service**, and then type the FQDN of the pool or Standard Edition server.</span></span>

9.  <span data-ttu-id="3d988-120">按一下 **[確定]**，然後按一下 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="3d988-120">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a><span data-ttu-id="3d988-121">驗證 DNS SRV 記錄的建立</span><span class="sxs-lookup"><span data-stu-id="3d988-121">To verify the creation of a DNS SRV record</span></span>

1.  <span data-ttu-id="3d988-122">使用已驗證使用者群組的成員帳戶，或具有相等許可權的帳戶，登入網域中的用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="3d988-122">Log on to a client computer in the domain with an account that is a member of the Authenticated Users group or has equivalent permissions.</span></span>

2.  <span data-ttu-id="3d988-123">按一下 **[開始]**，再按一下 **[執行]**。</span><span class="sxs-lookup"><span data-stu-id="3d988-123">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="3d988-124">在 [ **開啟** ] 方塊中輸入 **cmd**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3d988-124">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="3d988-125">在命令提示字元中輸入 **nslookup**，然後按 enter 鍵。</span><span class="sxs-lookup"><span data-stu-id="3d988-125">At the command prompt, type **nslookup**, and then press ENTER.</span></span>

5.  <span data-ttu-id="3d988-126">輸入 **set type = srv**，然後按 enter 鍵。</span><span class="sxs-lookup"><span data-stu-id="3d988-126">Type **set type=srv**, and then press ENTER.</span></span>

6.  <span data-ttu-id="3d988-127">輸入\*\* \_ sipinternaltls。 \_tcp.contoso.com\*\*，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="3d988-127">Type **\_sipinternaltls.\_tcp.contoso.com**, and then press ENTER.</span></span> <span data-ttu-id="3d988-128">傳輸層安全性 (TLS) record 顯示的輸出如下：</span><span class="sxs-lookup"><span data-stu-id="3d988-128">The output displayed for the Transport Layer Security (TLS) record is as follows:</span></span>
    
    <span data-ttu-id="3d988-129">伺服器： \<dns server\> . contoso.com</span><span class="sxs-lookup"><span data-stu-id="3d988-129">Server: \<dns server\>.contoso.com</span></span>
    
    <span data-ttu-id="3d988-130">位址： \<IP address of DNS server\></span><span class="sxs-lookup"><span data-stu-id="3d988-130">Address: \<IP address of DNS server\></span></span>
    
    <span data-ttu-id="3d988-131">非絕對回應：</span><span class="sxs-lookup"><span data-stu-id="3d988-131">Non-authoritative answer:</span></span>
    
    <span data-ttu-id="3d988-132">\_sipinternaltls。 \_tcp.contoso.com SRV 服務位置：</span><span class="sxs-lookup"><span data-stu-id="3d988-132">\_sipinternaltls.\_tcp.contoso.com SRV service location:</span></span>
    
    <span data-ttu-id="3d988-133">priority = 0</span><span class="sxs-lookup"><span data-stu-id="3d988-133">priority = 0</span></span>
    
    <span data-ttu-id="3d988-134">權數 = 0</span><span class="sxs-lookup"><span data-stu-id="3d988-134">weight = 0</span></span>
    
    <span data-ttu-id="3d988-135">埠 = 5061</span><span class="sxs-lookup"><span data-stu-id="3d988-135">port = 5061</span></span>
    
    <span data-ttu-id="3d988-136">svr hostname = poolname.contoso.com (或 Standard Edition server A record) </span><span class="sxs-lookup"><span data-stu-id="3d988-136">svr hostname = poolname.contoso.com (or Standard Edition server A record)</span></span>
    
    <span data-ttu-id="3d988-137">poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> 或（ \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> 或） \<IP address of the Standard Edition server\></span><span class="sxs-lookup"><span data-stu-id="3d988-137">poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> or \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> or \<IP address of the Standard Edition server\></span></span>

7.  <span data-ttu-id="3d988-138">完成後，請在命令提示字元處輸入 **exit**，然後按 enter 鍵。</span><span class="sxs-lookup"><span data-stu-id="3d988-138">When you are finished, at the command prompt, type **exit**, and then press ENTER.</span></span>

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="3d988-139">確認可解析前端集區或 Standard Edition server 的 FQDN</span><span class="sxs-lookup"><span data-stu-id="3d988-139">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1.  <span data-ttu-id="3d988-140">登入網域中的用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="3d988-140">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="3d988-141">按一下 **[開始]**，再按一下 **[執行]**。</span><span class="sxs-lookup"><span data-stu-id="3d988-141">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="3d988-142">在 [ **開啟** ] 方塊中輸入 **cmd**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3d988-142">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="3d988-143">在命令提示字元中輸入 **nslookup** \<FQDN of the Front End pool\> 或 \<FQDN of the Standard Edition server\> ，然後按 enter 鍵。</span><span class="sxs-lookup"><span data-stu-id="3d988-143">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="3d988-144">請確認您收到的回復可解析為 FQDN 的適當 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3d988-144">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013： 建立並確認 DNS SRV 記錄
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
ms.openlocfilehash: e6f56b2c406a14a6a1781705017d13d8b823472c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a><span data-ttu-id="41b26-102">建立並確認 Lync Server 2013 中的 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="41b26-102">Create and verify DNS SRV records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41b26-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="41b26-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="41b26-104">若要順利完成此程序，您至少應該以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。</span><span class="sxs-lookup"><span data-stu-id="41b26-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="41b26-105">本主題說明如何設定您所建立的 Lync Server 2013 部署以及所需的用戶端自動登入的網域名稱系統 (DNS) 記錄。</span><span class="sxs-lookup"><span data-stu-id="41b26-105">This topic describes how to configure the Domain Name System (DNS) records that you are required to create in Lync Server 2013 deployments and those required for automatic client sign in.</span></span> <span data-ttu-id="41b26-106">當您建立前端集區時，安裝程式會建立集區，包括集區完整的網域名稱 (FQDN) 設定及 Active Directory 物件。</span><span class="sxs-lookup"><span data-stu-id="41b26-106">When you create a Front End pool, Setup creates Active Directory objects and settings for the pool, including the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="41b26-107">Standard Edition server 建立類似物件和設定。</span><span class="sxs-lookup"><span data-stu-id="41b26-107">Similar objects and settings are created for a Standard Edition server.</span></span> <span data-ttu-id="41b26-108">若要能夠連線到集區或 Standard Edition server 的用戶端，集區或 Standard Edition server 的 FQDN 必須登錄在 DNS 中。</span><span class="sxs-lookup"><span data-stu-id="41b26-108">For clients to be able to connect to the pool or Standard Edition server, the FQDN of the pool or Standard Edition server must be registered in DNS.</span></span> <span data-ttu-id="41b26-109">您必須針對每個 SIP 網域內部部署 DNS 中建立 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="41b26-109">You must create DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="41b26-110">此程序假設您的內部 DNS 有 SIP 使用者網域的區域。</span><span class="sxs-lookup"><span data-stu-id="41b26-110">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<div>

## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="41b26-111">若要設定 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="41b26-111">To configure a DNS SRV record</span></span>

1.  <span data-ttu-id="41b26-112">在 DNS 伺服器上，按一下 [**開始]**、 [**系統管理工具**] 和 [ **DNS**。</span><span class="sxs-lookup"><span data-stu-id="41b26-112">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="41b26-113">在 SIP 網域的主控台樹狀目錄，展開 [**正向對應區域**，，然後在要安裝 Lync Server 2013 的 SIP 網域上按一下滑鼠右鍵。</span><span class="sxs-lookup"><span data-stu-id="41b26-113">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the SIP domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="41b26-114">按一下 [**新增其他記錄**]。</span><span class="sxs-lookup"><span data-stu-id="41b26-114">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="41b26-115">在 [**選擇資源記錄類型**，按一下 [**服務位置 (SRV)**，，，然後按一下 [**建立記錄**。</span><span class="sxs-lookup"><span data-stu-id="41b26-115">In **Select a resource record type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="41b26-116">按一下 [**服務**]，然後輸入**\_sipinternaltls**。</span><span class="sxs-lookup"><span data-stu-id="41b26-116">Click **Service**, and then type **\_sipinternaltls**.</span></span>

6.  <span data-ttu-id="41b26-117">按一下 [**通訊協定**，然後輸入**\_tcp**。</span><span class="sxs-lookup"><span data-stu-id="41b26-117">Click **Protocol**, and then type **\_tcp**.</span></span>

7.  <span data-ttu-id="41b26-118">按一下 [**連接埠號碼**，然後輸入**5061**。</span><span class="sxs-lookup"><span data-stu-id="41b26-118">Click **Port Number**, and then type **5061**.</span></span>

8.  <span data-ttu-id="41b26-119">按一下 [**提供這項服務的主機**，，，然後輸入集區或 Standard Edition server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="41b26-119">Click **Host offering this service**, and then type the FQDN of the pool or Standard Edition server.</span></span>

9.  <span data-ttu-id="41b26-120">按一下 [**確定**]，然後按一下 [**完成**。</span><span class="sxs-lookup"><span data-stu-id="41b26-120">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a><span data-ttu-id="41b26-121">若要確認 DNS SRV 記錄的建立</span><span class="sxs-lookup"><span data-stu-id="41b26-121">To verify the creation of a DNS SRV record</span></span>

1.  <span data-ttu-id="41b26-122">以 Authenticated Users 群組成員或具有相等權限的帳戶的網域中的用戶端電腦登入。</span><span class="sxs-lookup"><span data-stu-id="41b26-122">Log on to a client computer in the domain with an account that is a member of the Authenticated Users group or has equivalent permissions.</span></span>

2.  <span data-ttu-id="41b26-123">按一下 [開始]\*\*\*\*，然後按一下 [執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="41b26-123">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="41b26-124">在 [**開啟**] 方塊中輸入**cmd**，，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="41b26-124">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="41b26-125">在命令提示字元處，輸入**nslookup**，，然後按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="41b26-125">At the command prompt, type **nslookup**, and then press ENTER.</span></span>

5.  <span data-ttu-id="41b26-126">型別**設定 type = srv**，然後按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="41b26-126">Type **set type=srv**, and then press ENTER.</span></span>

6.  <span data-ttu-id="41b26-127">類型**\_sipinternaltls。\_tcp.contoso.com**，然後按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="41b26-127">Type **\_sipinternaltls.\_tcp.contoso.com**, and then press ENTER.</span></span> <span data-ttu-id="41b26-128">顯示傳輸層安全性 (TLS) 記錄的輸出是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="41b26-128">The output displayed for the Transport Layer Security (TLS) record is as follows:</span></span>
    
    <span data-ttu-id="41b26-129">Server: \<dns server\>。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="41b26-129">Server: \<dns server\>.contoso.com</span></span>
    
    <span data-ttu-id="41b26-130">地址： \<DNS 伺服器 IP 位址\></span><span class="sxs-lookup"><span data-stu-id="41b26-130">Address: \<IP address of DNS server\></span></span>
    
    <span data-ttu-id="41b26-131">非代表性頁面的答案：</span><span class="sxs-lookup"><span data-stu-id="41b26-131">Non-authoritative answer:</span></span>
    
    <span data-ttu-id="41b26-132">\_sipinternaltls。\_tcp.contoso.com SRV 服務位置：</span><span class="sxs-lookup"><span data-stu-id="41b26-132">\_sipinternaltls.\_tcp.contoso.com SRV service location:</span></span>
    
    <span data-ttu-id="41b26-133">優先順序 = 0</span><span class="sxs-lookup"><span data-stu-id="41b26-133">priority = 0</span></span>
    
    <span data-ttu-id="41b26-134">weight = 0</span><span class="sxs-lookup"><span data-stu-id="41b26-134">weight = 0</span></span>
    
    <span data-ttu-id="41b26-135">連接埠 = 5061</span><span class="sxs-lookup"><span data-stu-id="41b26-135">port = 5061</span></span>
    
    <span data-ttu-id="41b26-136">svr hostname = poolname.contoso.com （或 Standard Edition server A 記錄）</span><span class="sxs-lookup"><span data-stu-id="41b26-136">svr hostname = poolname.contoso.com (or Standard Edition server A record)</span></span>
    
    <span data-ttu-id="41b26-137">poolname.contoso.com internet address =\<負載平衡器虛擬 IP 位址\>或\<只能有一個 Enterprise Edition 伺服器與集區的單一 Enterprise Edition 伺服器的 IP 位址\>或\<Standard Edition server 的 IP 位址\></span><span class="sxs-lookup"><span data-stu-id="41b26-137">poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> or \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> or \<IP address of the Standard Edition server\></span></span>

7.  <span data-ttu-id="41b26-138">完成時，在命令提示字元處，輸入**exit**，並按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="41b26-138">When you are finished, at the command prompt, type **exit**, and then press ENTER.</span></span>

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="41b26-139">若要確認可以解析前端集區或 Standard Edition server 的 FQDN</span><span class="sxs-lookup"><span data-stu-id="41b26-139">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1.  <span data-ttu-id="41b26-140">登入網域中的用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="41b26-140">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="41b26-141">按一下 [開始]\*\*\*\*，然後按一下 [執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="41b26-141">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="41b26-142">在 [**開啟**] 方塊中輸入**cmd**，，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="41b26-142">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="41b26-143">在命令提示字元處，輸入**nslookup** \<的前端集區 FQDN\>或\<Standard Edition server 的 FQDN\>，然後按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="41b26-143">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="41b26-144">確認您收到的 fqdn 解析為適當的 IP 位址的回覆。</span><span class="sxs-lookup"><span data-stu-id="41b26-144">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


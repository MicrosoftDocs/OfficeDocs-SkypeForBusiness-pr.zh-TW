---
title: 建立 DNS SRV 記錄，以與主控 Exchange UM 整合
description: 建立 DNS SRV 記錄，以與主控 Exchange UM 整合。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 694a595977abe33bebbb5fbcf2a508c9bb4e35a4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542139"
---
# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a><span data-ttu-id="503e5-103">建立 DNS SRV 記錄，以與主控 Exchange UM 整合</span><span class="sxs-lookup"><span data-stu-id="503e5-103">Create a DNS SRV record for integration with hosted Exchange UM</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="503e5-104">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="503e5-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="503e5-105">本主題說明如何針對 Lync Server 2013 Edge Server 所需的 (DNS) SRV 記錄，設定網域名稱系統，以路由傳送至主控 Exchange 服務（如 Microsoft Exchange Online）。</span><span class="sxs-lookup"><span data-stu-id="503e5-105">This topic describes how to configure the Domain Name System (DNS) SRV record that is required for a Lync Server 2013 Edge Server to route to a hosted Exchange service such as Microsoft Exchange Online.</span></span>

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a><span data-ttu-id="503e5-106">若要為主控的 Exchange 服務建立外部 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="503e5-106">To create an external DNS SRV record for the hosted Exchange service</span></span>

1.  <span data-ttu-id="503e5-107">以 DnsAdmins 群組成員的身分登入外部 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="503e5-107">Log on to the external DNS server as a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="503e5-108">依序按一下 [開始]\*\*\*\*、[系統管理工具]\*\*\*\* 及 [DNS]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="503e5-108">Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="503e5-109">在 SIP 網域的主控台樹中，展開 [ **正向對應區域**]，然後選取將安裝 Lync Server 2013 的 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="503e5-109">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and select the SIP domain in which Lync Server 2013 will be installed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="503e5-110">您必須在將安裝 Lync Server 的 SIP 網域中建立 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="503e5-110">You must create the DNS SRV record in the SIP domain in which Lync Server is or will be installed.</span></span> <span data-ttu-id="503e5-111">當您建立 SRV 記錄時，用於提供此服務欄位之主機的 FQDN 必須是 Edge 集區的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="503e5-111">When you create the SRV record, the FQDN used for the Host offering this service field must be the external FQDN of the Edge pool.</span></span> <span data-ttu-id="503e5-112">例如，如果您 Edge 集區的外部 FQDN 是 edge01.contoso.net，請輸入該值。</span><span class="sxs-lookup"><span data-stu-id="503e5-112">For example, if the external FQDN of your Edge pool is edge01.contoso.net, enter that value.</span></span> <span data-ttu-id="503e5-113">這也必須與 DNS 主機位於相同的網域中 () 記錄。</span><span class="sxs-lookup"><span data-stu-id="503e5-113">This must also be in the same domain as the DNS Hosts (A) record.</span></span>

    
    </div>

4.  <span data-ttu-id="503e5-114">以滑鼠右鍵按一下選取的網域，然後按一下 [ **其他新記錄**]。</span><span class="sxs-lookup"><span data-stu-id="503e5-114">Right-click the selected domain, and then click **Other New Records**.</span></span>

5.  <span data-ttu-id="503e5-115">在 [ **資源記錄類型**] 中，按一下 [ \*\*服務位置] (SRV) \*\*]，然後按一下 [ **建立記錄**]。</span><span class="sxs-lookup"><span data-stu-id="503e5-115">In **Resource Record Type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

6.  <span data-ttu-id="503e5-116">在 [**新增資源記錄**] 中，按一下 [**服務**]，然後輸入\*\* \_ sipfederationtls\*\*。</span><span class="sxs-lookup"><span data-stu-id="503e5-116">In **New Resource Record**, click **Service**, and then type **\_sipfederationtls**.</span></span>

7.  <span data-ttu-id="503e5-117">按一下 [**通訊協定**]，然後輸入\*\* \_ tcp\*\*。</span><span class="sxs-lookup"><span data-stu-id="503e5-117">Click **Protocol**, and then type **\_tcp**.</span></span>

8.  <span data-ttu-id="503e5-118">按一下 [ **埠號碼**]，然後輸入 **5061**。</span><span class="sxs-lookup"><span data-stu-id="503e5-118">Click **Port Number**, and then type **5061**.</span></span>

9.  <span data-ttu-id="503e5-119">按一下 [ **提供這項服務的主機**]，然後輸入 lync Server 2013 Edge 集區的完整功能變數名稱 (FQDN) ，為受信任的外部用戶端提供 lync server 2013 系統的存取權。</span><span class="sxs-lookup"><span data-stu-id="503e5-119">Click **Host offering this service**, and then type the fully qualified domain name (FQDN) of the Lync Server 2013 Edge pool that provides access to your Lync Server 2013 system for trusted external clients.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="503e5-120">網域也必須設定為 Exchange Online 設定中的「授權」、「公認的網域」。</span><span class="sxs-lookup"><span data-stu-id="503e5-120">The domain must also be set up as an authoritative, accepted domain in your Exchange Online settings.</span></span> <span data-ttu-id="503e5-121">如需詳細資訊，請參閱建立公認的網域 at <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A> 。</span><span class="sxs-lookup"><span data-stu-id="503e5-121">For details, see Create Accepted Domains at <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A>.</span></span>

    
    </div>

10. <span data-ttu-id="503e5-122">按一下 **[確定]**，然後按一下 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="503e5-122">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a><span data-ttu-id="503e5-123">確認已成功建立 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="503e5-123">To verify that the DNS SRV record was created successfully</span></span>

1.  <span data-ttu-id="503e5-124">登入網域中的用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="503e5-124">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="503e5-125">按一下 **[開始]**，再按一下 **[執行]**。</span><span class="sxs-lookup"><span data-stu-id="503e5-125">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="503e5-126">在命令提示字元中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="503e5-126">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN Lync Edge Pool>

4.  <span data-ttu-id="503e5-127">請確認您收到的回復可解析為 FQDN 的適當 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="503e5-127">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="503e5-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="503e5-128">See Also</span></span>


[<span data-ttu-id="503e5-129">在 Lync Server 2013 中建立反向 proxy 伺服器的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="503e5-129">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


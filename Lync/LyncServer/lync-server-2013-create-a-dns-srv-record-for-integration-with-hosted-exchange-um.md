---
title: 建立與裝載 Exchange UM 整合的 DNS SRV 記錄
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
ms.openlocfilehash: c30164813619a271f2321db3ff3e8019067193c0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a><span data-ttu-id="92bc1-102">建立與裝載 Exchange UM 整合的 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="92bc1-102">Create a DNS SRV record for integration with hosted Exchange UM</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92bc1-103">_**上次修改主題：** 2013年-02-20 個_</span><span class="sxs-lookup"><span data-stu-id="92bc1-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="92bc1-104">本主題說明如何設定網域名稱系統 (DNS) SRV 記錄所需的 Lync Server 2013 Edge Server 路由傳送至裝載的 Exchange 服務，例如 Microsoft Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="92bc1-104">This topic describes how to configure the Domain Name System (DNS) SRV record that is required for a Lync Server 2013 Edge Server to route to a hosted Exchange service such as Microsoft Exchange Online.</span></span>

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a><span data-ttu-id="92bc1-105">若要建立託管式 Exchange 服務的外部 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="92bc1-105">To create an external DNS SRV record for the hosted Exchange service</span></span>

1.  <span data-ttu-id="92bc1-106">以 DnsAdmins 群組成員身分登入外部 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="92bc1-106">Log on to the external DNS server as a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="92bc1-107">依序按一下 [開始]\*\*\*\*、[系統管理工具]\*\*\*\* 及 [DNS]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="92bc1-107">Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="92bc1-108">在 [SIP 網域的主控台樹狀目錄，展開 [**正向對應區域**]，然後選取 [在要安裝 Lync Server 2013 的 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="92bc1-108">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and select the SIP domain in which Lync Server 2013 will be installed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="92bc1-109">您必須在 Lync Server 是或安裝的 SIP 網域中建立 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="92bc1-109">You must create the DNS SRV record in the SIP domain in which Lync Server is or will be installed.</span></span> <span data-ttu-id="92bc1-110">當您建立的 SRV 記錄時，用於提供此服務欄位主機的 FQDN 必須將 Edge 集區的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="92bc1-110">When you create the SRV record, the FQDN used for the Host offering this service field must be the external FQDN of the Edge pool.</span></span> <span data-ttu-id="92bc1-111">例如，如果您的 Edge 集區的外部 FQDN 是 edge01.contoso.net，請輸入這個值。</span><span class="sxs-lookup"><span data-stu-id="92bc1-111">For example, if the external FQDN of your Edge pool is edge01.contoso.net, enter that value.</span></span> <span data-ttu-id="92bc1-112">這也必須位於相同網域的 DNS 主機 (A) 記錄。</span><span class="sxs-lookup"><span data-stu-id="92bc1-112">This must also be in the same domain as the DNS Hosts (A) record.</span></span>

    
    </div>

4.  <span data-ttu-id="92bc1-113">選取的網域，以滑鼠右鍵按一下，然後按一下 [**新增其他記錄**。</span><span class="sxs-lookup"><span data-stu-id="92bc1-113">Right-click the selected domain, and then click **Other New Records**.</span></span>

5.  <span data-ttu-id="92bc1-114">在 [**資源記錄類型**] 中，按一下 [**服務位置 (SRV)**，，，然後按一下 [**建立記錄**。</span><span class="sxs-lookup"><span data-stu-id="92bc1-114">In **Resource Record Type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

6.  <span data-ttu-id="92bc1-115">在 [**新增資源記錄**中，按一下**服務**]，然後輸入**\_sipfederationtls**。</span><span class="sxs-lookup"><span data-stu-id="92bc1-115">In **New Resource Record**, click **Service**, and then type **\_sipfederationtls**.</span></span>

7.  <span data-ttu-id="92bc1-116">按一下 [**通訊協定**，然後輸入**\_tcp**。</span><span class="sxs-lookup"><span data-stu-id="92bc1-116">Click **Protocol**, and then type **\_tcp**.</span></span>

8.  <span data-ttu-id="92bc1-117">按一下 [**連接埠號碼**，然後輸入**5061**。</span><span class="sxs-lookup"><span data-stu-id="92bc1-117">Click **Port Number**, and then type **5061**.</span></span>

9.  <span data-ttu-id="92bc1-118">按一下 [**提供這項服務的主機**，，然後輸入為信任的外部用戶端提供 Lync Server 2013 系統存取權的 Lync Server 2013 Edge 集區的 [完整的網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="92bc1-118">Click **Host offering this service**, and then type the fully qualified domain name (FQDN) of the Lync Server 2013 Edge pool that provides access to your Lync Server 2013 system for trusted external clients.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="92bc1-119">網域必須也設定為授權、 公認的網域在您的 Exchange Online 設定。</span><span class="sxs-lookup"><span data-stu-id="92bc1-119">The domain must also be set up as an authoritative, accepted domain in your Exchange Online settings.</span></span> <span data-ttu-id="92bc1-120">如需詳細資訊，請參閱建立公認的網域在<A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A>。</span><span class="sxs-lookup"><span data-stu-id="92bc1-120">For details, see Create Accepted Domains at <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A>.</span></span>

    
    </div>

10. <span data-ttu-id="92bc1-121">按一下 [**確定**]，然後按一下 [**完成**。</span><span class="sxs-lookup"><span data-stu-id="92bc1-121">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a><span data-ttu-id="92bc1-122">若要確認已成功建立 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="92bc1-122">To verify that the DNS SRV record was created successfully</span></span>

1.  <span data-ttu-id="92bc1-123">登入網域中的用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="92bc1-123">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="92bc1-124">按一下 [開始]\*\*\*\*，然後按一下 [執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="92bc1-124">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="92bc1-125">在命令提示字元中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="92bc1-125">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN Lync Edge Pool>

4.  <span data-ttu-id="92bc1-126">確認您收到的 fqdn 解析為適當的 IP 位址的回覆。</span><span class="sxs-lookup"><span data-stu-id="92bc1-126">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="92bc1-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="92bc1-127">See Also</span></span>


[<span data-ttu-id="92bc1-128">在 Lync Server 2013 中建立反向 proxy 伺服器的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="92bc1-128">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


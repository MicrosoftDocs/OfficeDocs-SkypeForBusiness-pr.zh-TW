---
title: Lync Server 2013：整合內部部署整合通訊的指導方針
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44f032f7dd7d11d70ac912b2005f3ad9f7ddad69
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536920"
---
# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="45ec2-102">整合內部部署整合通訊和 Lync Server 2013 的指導方針</span><span class="sxs-lookup"><span data-stu-id="45ec2-102">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45ec2-103">_**主題上次修改日期：** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="45ec2-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="45ec2-104">以下是部署企業語音時所需考慮的指導方針和最佳作法：</span><span class="sxs-lookup"><span data-stu-id="45ec2-104">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="45ec2-105">只有在您同時使用 UCMA 4 時，Exchange 整合通訊 (UM) 才會支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="45ec2-105">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span>



</div>

  - <span data-ttu-id="45ec2-106">部署 Lync Server 2013 Standard Edition Server 或前端集區。</span><span class="sxs-lookup"><span data-stu-id="45ec2-106">Deploy a Lync Server 2013 Standard Edition server or a Front End pool.</span></span> <span data-ttu-id="45ec2-107">如需安裝的詳細資訊，請參閱部署檔中的 [部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="45ec2-107">For details about installation, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="45ec2-108">與 Exchange 系統管理員合作，確認每一個人將要執行的工作，以確保能夠順暢、成功地整合。</span><span class="sxs-lookup"><span data-stu-id="45ec2-108">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>

  - <span data-ttu-id="45ec2-109">在您要為 Exchange UM 啟用使用者的每個 Exchange 整合通訊 (UM) 樹系中，部署 Exchange 信箱伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="45ec2-109">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="45ec2-110">如需安裝 Exchange 伺服器角色的詳細資訊，請參閱 Microsoft Exchange Server 2013 檔。</span><span class="sxs-lookup"><span data-stu-id="45ec2-110">For details about installing Exchange server roles, see the Microsoft Exchange Server 2013 documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="45ec2-111">安裝 Exchange 整合通訊 (UM) 時，會將其設定為使用自我簽署憑證。</span><span class="sxs-lookup"><span data-stu-id="45ec2-111">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span><BR><span data-ttu-id="45ec2-112">不過，自我簽署憑證不會讓 Lync Server 2013 和 Exchange UM 彼此信任，這就是為何必須從兩部伺服器信任的憑證授權單位單位要求個別憑證。</span><span class="sxs-lookup"><span data-stu-id="45ec2-112">The self-signed certificate, however, does not enable Lync Server 2013 and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span>

    
    </div>

  - <span data-ttu-id="45ec2-113">如果 Lync Server 2013 和 Exchange UM 安裝在不同的樹系中，請將每個 Exchange 樹系設定為信任 Lync Server 2013 樹系和 Lync Server 2013 樹系，以信任每個 Exchange 樹系。</span><span class="sxs-lookup"><span data-stu-id="45ec2-113">If Lync Server 2013 and Exchange UM are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange forest.</span></span> <span data-ttu-id="45ec2-114">此外，您也可以在 Lync Server 2013 樹系中的使用者物件上設定使用者的 Exchange UM 設定，通常是使用腳本或跨樹系工具（例如身分識別生命週期管理員 (ILM) ）。</span><span class="sxs-lookup"><span data-stu-id="45ec2-114">Also, set the users’ Exchange UM settings on the user objects in the Lync Server 2013 forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>

  - <span data-ttu-id="45ec2-115">必要時，安裝 Exchange 管理主控台以便管理 Unified Messaging 伺服器。</span><span class="sxs-lookup"><span data-stu-id="45ec2-115">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>

  - <span data-ttu-id="45ec2-116">取得 Outlook Voice Access 和自動語音應答的有效電話號碼。</span><span class="sxs-lookup"><span data-stu-id="45ec2-116">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>

  - <span data-ttu-id="45ec2-117">如果您使用的 Exchange UM 版本低於 Microsoft Exchange Server 2010 Service Pack 1 (SP1) ，則為 Exchange UM SIP URI 撥號對應表和 Enterprise Voice 撥號對應表的座標名稱。</span><span class="sxs-lookup"><span data-stu-id="45ec2-117">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span>

<div>

## <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="45ec2-118">部署重複的 Exchange UM 伺服器</span><span class="sxs-lookup"><span data-stu-id="45ec2-118">Deploying Redundant Exchange UM Servers</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="45ec2-119">建議您為組織設定的每個 Exchange UM SIP URI 撥號對應表，至少部署兩部執行 Exchange UM 服務的伺服器。</span><span class="sxs-lookup"><span data-stu-id="45ec2-119">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="45ec2-120">除了提供擴充的容量之外，部署冗余伺服器也可提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="45ec2-120">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="45ec2-121">當伺服器失敗時，Lync Server 2013 可以設定成容錯移轉至另一部伺服器。</span><span class="sxs-lookup"><span data-stu-id="45ec2-121">In the event of an server failure, Lync Server 2013 can be configured to fail over to another server.</span></span>



</div>

<span data-ttu-id="45ec2-122">以下範例設定可提供 Exchange UM 恢復能力。</span><span class="sxs-lookup"><span data-stu-id="45ec2-122">The following example configurations provide Exchange UM resiliency.</span></span>

<span data-ttu-id="45ec2-123">**範例 1：Exchange UM 恢復能力**</span><span class="sxs-lookup"><span data-stu-id="45ec2-123">**Example 1: Exchange UM Resiliency**</span></span>

<span data-ttu-id="45ec2-124">![Exchange UM 範例1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM 範例1")</span><span class="sxs-lookup"><span data-stu-id="45ec2-124">![Exchange UM Example 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM Example 1")</span></span>

<span data-ttu-id="45ec2-125">在範例 1 中，Tukwila 資料中心內的 Exchange UM 伺服器 1 和伺服器 2 均已啟用；Dublin 資料中心內的 Exchange UM 伺服器 3 和伺服器 4 均已啟用。</span><span class="sxs-lookup"><span data-stu-id="45ec2-125">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center.</span></span> <span data-ttu-id="45ec2-126">在 Tukwila 中發生 Exchange UM 中斷的情況時，網域名稱系統 (DNS) 伺服器1和2的記錄應該設定為分別指向 servers 3 和4。</span><span class="sxs-lookup"><span data-stu-id="45ec2-126">In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively.</span></span> <span data-ttu-id="45ec2-127">在都柏林中發生 Exchange UM 中斷的情況時，伺服器3和4的 DNS A 記錄應該設定為分別指向 servers 1 和2。</span><span class="sxs-lookup"><span data-stu-id="45ec2-127">In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="45ec2-128">在範例 1 中，您還需要在每部 Exchange UM 伺服器上指派以下任一憑證：</span><span class="sxs-lookup"><span data-stu-id="45ec2-128">For Example 1, you should also assign one of following certificate on each Exchange UM server:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="45ec2-129">在主體替代名稱 (SAN) 中使用含萬用字元的憑證。</span><span class="sxs-lookup"><span data-stu-id="45ec2-129">Use a certificate with a wildcard in the Subject Alternative Name (SAN).</span></span></P>
> <LI>
> <P><span data-ttu-id="45ec2-130">將 SAN 中每四個 Exchange UM 伺服器的完整功能變數名稱 (FQDN) 放入該功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="45ec2-130">Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span></P></LI></UL>



</div>

<span data-ttu-id="45ec2-131">**範例 2：Exchange UM 恢復能力**</span><span class="sxs-lookup"><span data-stu-id="45ec2-131">**Example 2: Exchange UM Resiliency**</span></span>

<span data-ttu-id="45ec2-132">![Exchange UM 範例2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM 範例2")</span><span class="sxs-lookup"><span data-stu-id="45ec2-132">![Exchange UM Example 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM Example 2")</span></span>

<span data-ttu-id="45ec2-p106">在範例 2 中，於正常運作情況下，Tukwila 資料中心內的 Exchange UM 伺服器 1 和伺服器 2 均已啟用；Dublin 資料中心內的 Exchange UM 伺服器 3 和伺服器 4 均已啟用。這四部伺服器均包含在 Tukwila 使用者的 SIP URI 撥號對應表中，不過伺服器 3 和 4 均已停用。當 Tukwila 的 Exchange UM 伺服器發生如停止運作等的情況時，應停用 Exchange UM 伺服器 1 和 2 並啟用 Exchange UM 伺服器 3 和 4，以將 Tukwila Exchange UM 的流量路由傳送至 Dublin 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="45ec2-p106">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled. In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>

<span data-ttu-id="45ec2-136">如需如何啟用或停用 Exchange 2013 整合通訊的詳細資訊，請參閱「整合 Exchange 2013 UM 搭配 Lync Server」 [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372) 。</span><span class="sxs-lookup"><span data-stu-id="45ec2-136">For details about how to enable or disable Unified Messaging on Exchange 2013, see “Integrate Exchange 2013 UM with Lync Server” at [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

<span data-ttu-id="45ec2-137">如需如何在 Microsoft Exchange Server 2010 上啟用或停用整合通訊的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="45ec2-137">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>

  - <span data-ttu-id="45ec2-138">「在 Exchange 2010 上啟用整合通訊」 [https://go.microsoft.com/fwlink/p/?LinkId=204418](https://go.microsoft.com/fwlink/p/?linkid=204418) 。</span><span class="sxs-lookup"><span data-stu-id="45ec2-138">"Enable Unified Messaging on Exchange 2010" at [https://go.microsoft.com/fwlink/p/?LinkId=204418](https://go.microsoft.com/fwlink/p/?linkid=204418).</span></span>

  - <span data-ttu-id="45ec2-139">「在 Exchange 2010 上停用整合通訊」 [https://go.microsoft.com/fwlink/p/?LinkId=204416](https://go.microsoft.com/fwlink/p/?linkid=204416) 。</span><span class="sxs-lookup"><span data-stu-id="45ec2-139">"Disable Unified Messaging on Exchange 2010" at [https://go.microsoft.com/fwlink/p/?LinkId=204416](https://go.microsoft.com/fwlink/p/?linkid=204416).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="45ec2-140">另請參閱</span><span class="sxs-lookup"><span data-stu-id="45ec2-140">See Also</span></span>


[<span data-ttu-id="45ec2-141">整合內部部署整合通訊和 Lync Server 2013 的部署程式</span><span class="sxs-lookup"><span data-stu-id="45ec2-141">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


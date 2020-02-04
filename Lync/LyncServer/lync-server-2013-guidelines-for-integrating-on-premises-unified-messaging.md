---
title: Lync Server 2013：整合內部部署 Unified Messaging 的指導方針
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
ms.openlocfilehash: 3f3e57245f0a8edf5b545f9a67547e6be6f63399
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="ceaaa-102">整合內部部署 Unified Messaging 和 Lync Server 2013 的指導方針</span><span class="sxs-lookup"><span data-stu-id="ceaaa-102">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ceaaa-103">_**主題上次修改日期：** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="ceaaa-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="ceaaa-104">下列是在您部署企業語音時要考慮的指導方針和最佳做法：</span><span class="sxs-lookup"><span data-stu-id="ceaaa-104">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ceaaa-105">Exchange 整合通訊（UM）只有在您同時使用 UCMA 4 時才支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-105">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span>



</div>

  - <span data-ttu-id="ceaaa-106">部署 Lync Server 2013 標準版伺服器或前端池。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-106">Deploy a Lync Server 2013 Standard Edition server or a Front End pool.</span></span> <span data-ttu-id="ceaaa-107">如需安裝的詳細資訊，請參閱部署檔中的 [[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) ]。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-107">For details about installation, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="ceaaa-108">與 Exchange 管理員共同確認您將執行的工作，以確保順利且順利地整合。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-108">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>

  - <span data-ttu-id="ceaaa-109">在您要啟用 Exchange UM 使用者的每個 Exchange 整合通訊（UM）目錄林中，部署 Exchange 信箱伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-109">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="ceaaa-110">如需安裝 Exchange server 角色的詳細資料，請參閱 Microsoft Exchange Server 2013 檔。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-110">For details about installing Exchange server roles, see the Microsoft Exchange Server 2013 documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ceaaa-111">安裝 Exchange 整合通訊（UM）後，系統會將它設定為使用自行簽署式認證。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-111">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span><BR><span data-ttu-id="ceaaa-112">但自行簽署式認證不會啟用 Lync Server 2013 與 Exchange UM 互相信任，這就是為什麼必須從兩個伺服器信任的憑證授權單位要求個別憑證的原因。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-112">The self-signed certificate, however, does not enable Lync Server 2013 and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span>

    
    </div>

  - <span data-ttu-id="ceaaa-113">如果 Lync Server 2013 與 Exchange UM 安裝在不同的林中，請將每個 Exchange 林設定為信任 Lync Server 2013 林，以及 Lync Server 2013 目錄林，以信任每個 Exchange 目錄林。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-113">If Lync Server 2013 and Exchange UM are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange forest.</span></span> <span data-ttu-id="ceaaa-114">此外，您也可以在 Lync Server 2013 林中的使用者物件上設定使用者的 Exchange UM 設定，通常是使用腳本或跨林工具（例如 [身分識別週期管理員（ILM）]）。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-114">Also, set the users’ Exchange UM settings on the user objects in the Lync Server 2013 forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>

  - <span data-ttu-id="ceaaa-115">如有需要，請安裝 Exchange 管理主控台來管理您的整合郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-115">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>

  - <span data-ttu-id="ceaaa-116">取得 Outlook 語音存取和自動語音應答的有效電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-116">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>

  - <span data-ttu-id="ceaaa-117">如果您使用的 Exchange UM 版本早于 Microsoft Exchange Server 2010 Service Pack 1 （SP1），請調整 Exchange UM SIP URI 撥號方案和企業語音撥號方案的名稱。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-117">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span>

<div>

## <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="ceaaa-118">部署重複的 Exchange UM 伺服器</span><span class="sxs-lookup"><span data-stu-id="ceaaa-118">Deploying Redundant Exchange UM Servers</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ceaaa-119">我們建議您在針對您的組織設定的每個 Exchange UM SIP URI 撥號方案中，部署至少有兩個 Exchange UM 服務正在執行的伺服器。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-119">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="ceaaa-120">除了提供擴充的容量之外，部署冗余伺服器也提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-120">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="ceaaa-121">當伺服器發生故障時，可以將 Lync Server 2013 設定為容錯移轉到另一個伺服器。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-121">In the event of an server failure, Lync Server 2013 can be configured to fail over to another server.</span></span>



</div>

<span data-ttu-id="ceaaa-122">下列範例配置提供 Exchange UM 復原。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-122">The following example configurations provide Exchange UM resiliency.</span></span>

<span data-ttu-id="ceaaa-123">**範例1： Exchange UM 復原**</span><span class="sxs-lookup"><span data-stu-id="ceaaa-123">**Example 1: Exchange UM Resiliency**</span></span>

<span data-ttu-id="ceaaa-124">![Exchange UM 範例 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM 範例 1")</span><span class="sxs-lookup"><span data-stu-id="ceaaa-124">![Exchange UM Example 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM Example 1")</span></span>

<span data-ttu-id="ceaaa-125">在範例1中，Exchange UM 伺服器1和2在 Tukwila 資料中心中啟用，而在都柏林資料中心啟用 Exchange UM 伺服器3和4。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-125">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center.</span></span> <span data-ttu-id="ceaaa-126">在 Tukwila 中發生 Exchange UM 停用時，網域名稱系統（DNS）會將伺服器1和2的記錄分別設定為指向 [伺服器 3] 和 [4]。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-126">In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively.</span></span> <span data-ttu-id="ceaaa-127">在都柏林中發生 Exchange UM 停用時，伺服器3和4的 DNS A 記錄應該設定為分別指向 [伺服器 1] 和 [2]。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-127">In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ceaaa-128">例如1，您也應該在每個 Exchange UM 伺服器上指派下列其中一個憑證：</span><span class="sxs-lookup"><span data-stu-id="ceaaa-128">For Example 1, you should also assign one of following certificate on each Exchange UM server:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="ceaaa-129">在 Subject 備用名稱（SAN）中使用萬用字元的憑證。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-129">Use a certificate with a wildcard in the Subject Alternative Name (SAN).</span></span></P>
> <LI>
> <P><span data-ttu-id="ceaaa-130">在 SAN 中，將四個 Exchange UM 伺服器的完整功能變數名稱（FQDN）放在一起。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-130">Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span></P></LI></UL>



</div>

<span data-ttu-id="ceaaa-131">**範例2： Exchange UM 復原**</span><span class="sxs-lookup"><span data-stu-id="ceaaa-131">**Example 2: Exchange UM Resiliency**</span></span>

<span data-ttu-id="ceaaa-132">![Exchange UM 範例 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM 範例 2")</span><span class="sxs-lookup"><span data-stu-id="ceaaa-132">![Exchange UM Example 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM Example 2")</span></span>

<span data-ttu-id="ceaaa-133">在範例2的 [一般操作條件] 下，Exchange UM 伺服器1和2在 Tukwila 資料中心中啟用，且在都柏林資料中心啟用 Exchange UM 伺服器3和4。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-133">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center.</span></span> <span data-ttu-id="ceaaa-134">所有四個伺服器都包含在 Tukwila 使用者的 SIP URI 撥號計畫中;不過，伺服器3和4會停用。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-134">All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled.</span></span> <span data-ttu-id="ceaaa-135">例如，在 Tukwila 中發生 Exchange um 停用時，應該停用 exchange UM 伺服器1和2，然後啟用 Exchange UM 伺服器3和4，以便將 Tukwila Exchange UM 流量路由到都柏林中的伺服器。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-135">In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>

<span data-ttu-id="ceaaa-136">如需有關如何啟用或停用 Exchange 2013 整合訊息的詳細資訊，請參閱「將 Exchange 2013 UM 與 Lync [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)Server 整合在。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-136">For details about how to enable or disable Unified Messaging on Exchange 2013, see “Integrate Exchange 2013 UM with Lync Server” at [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

<span data-ttu-id="ceaaa-137">如需有關如何啟用或停用 Microsoft Exchange Server 2010 整合訊息的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="ceaaa-137">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>

  - <span data-ttu-id="ceaaa-138">[在[http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418)Exchange 2010 上啟用整合訊息]。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-138">"Enable Unified Messaging on Exchange 2010" at [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418).</span></span>

  - <span data-ttu-id="ceaaa-139">[停用 Exchange 2010 上的整合郵件[http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416)]。</span><span class="sxs-lookup"><span data-stu-id="ceaaa-139">"Disable Unified Messaging on Exchange 2010" at [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ceaaa-140">請參閱</span><span class="sxs-lookup"><span data-stu-id="ceaaa-140">See Also</span></span>


[<span data-ttu-id="ceaaa-141">整合內部部署 Unified Messaging 和 Lync Server 2013 的部署程序</span><span class="sxs-lookup"><span data-stu-id="ceaaa-141">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：在 Microsoft Exchange Server 上設定整合通訊，以與 Lync Server 搭配使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 462252b1826802ec424c6684e3a6347754095508
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517050"
---
# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a><span data-ttu-id="de3f5-102">在 Microsoft Exchange Server 上設定整合通訊以搭配 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de3f5-102">Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de3f5-103">_**主題上次修改日期：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="de3f5-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="de3f5-104">如果您想要使用 Exchange 整合通訊 (UM) 提供適用于 Enterprise Voice 使用者的呼叫回應、Outlook Voice Access 或自動語音應答服務，請參閱規劃檔中的 <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Exchange 整合通訊（Lync Server 2013</A> ）中的 [規劃 Exchange 整合通訊整合]，然後依照本節中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="de3f5-104">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planning for Exchange Unified Messaging integration in Lync Server 2013</A> in the Planning documentation, and then follow the instructions in this section.</span></span>



</div>

<span data-ttu-id="de3f5-105">若要設定 Exchange 整合通訊 (UM) 以使用 Enterprise Voice，您必須執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="de3f5-105">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

  - <span data-ttu-id="de3f5-106">在執行 Exchange 整合通訊 (UM) 服務的伺服器上設定憑證</span><span class="sxs-lookup"><span data-stu-id="de3f5-106">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="de3f5-107">將所有用戶端存取和信箱伺服器新增至所有 UM SIP URI 撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="de3f5-107">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="de3f5-108">如果不是，則輸出通話路由不會如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="de3f5-108">If not, outbound call routing won’t work as expected.</span></span>

    
    </div>

  - <span data-ttu-id="de3f5-109">視需要建立一個或多個 UM SIP URI 撥號對應表，以及訂閱者存取電話號碼，然後建立對應的 Lync Server 撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="de3f5-109">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding Lync Server dial plans.</span></span>

  - <span data-ttu-id="de3f5-110">使用 **exchucutil.ps1** 腳本執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="de3f5-110">Use the **exchucutil.ps1** script to:</span></span>
    
      - <span data-ttu-id="de3f5-111">建立 UM IP 閘道。</span><span class="sxs-lookup"><span data-stu-id="de3f5-111">Create UM IP gateways.</span></span>
    
      - <span data-ttu-id="de3f5-112">建立 UM 群組搜尋。</span><span class="sxs-lookup"><span data-stu-id="de3f5-112">Create UM hunt groups.</span></span>
    
      - <span data-ttu-id="de3f5-113">授與 Lync Server 2013 讀取 UM Active Directory 網域服務物件的許可權。</span><span class="sxs-lookup"><span data-stu-id="de3f5-113">Grant Lync Server 2013 permission to read UM Active Directory Domain Services objects.</span></span>

  - <span data-ttu-id="de3f5-114">建立 UM 自動語音應答物件。</span><span class="sxs-lookup"><span data-stu-id="de3f5-114">Create a UM auto-attendant object.</span></span>

  - <span data-ttu-id="de3f5-115">建立訂閱者存取物件。</span><span class="sxs-lookup"><span data-stu-id="de3f5-115">Create a subscriber access object.</span></span>

  - <span data-ttu-id="de3f5-116">為每個使用者建立 SIP URI，並將使用者與 UM SIP URI 撥號對應表相關聯。</span><span class="sxs-lookup"><span data-stu-id="de3f5-116">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="de3f5-117">需求和建議</span><span class="sxs-lookup"><span data-stu-id="de3f5-117">Requirements and Recommendations</span></span>

<span data-ttu-id="de3f5-118">在您開始之前，本節中的檔會假設您已部署下列 Exchange 2013 角色： Client Access 和信箱。</span><span class="sxs-lookup"><span data-stu-id="de3f5-118">Before you begin, the documentation in this section assumes that you have deployed the following Exchange 2013 roles: Client Access and Mailbox.</span></span> <span data-ttu-id="de3f5-119">在 Microsoft Exchange Server 2013 中，Exchange UM 會在這些伺服器上以服務的身分執行。</span><span class="sxs-lookup"><span data-stu-id="de3f5-119">In Microsoft Exchange Server 2013, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="de3f5-120">如需部署 Exchange 2013 的詳細資訊，請參閱 Exchange 2013 TechNet 程式庫，網址為 [https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)</span><span class="sxs-lookup"><span data-stu-id="de3f5-120">For details about deploying Exchange 2013, see the Exchange 2013 TechNet Library at [https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)</span></span>

<span data-ttu-id="de3f5-121">也請注意以下事項：</span><span class="sxs-lookup"><span data-stu-id="de3f5-121">Also note the following:</span></span>

  - <span data-ttu-id="de3f5-122">如果已在多個樹系中安裝 Exchange UM，則必須針對每個 UM 樹系執行 Exchange Server 整合步驟。</span><span class="sxs-lookup"><span data-stu-id="de3f5-122">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="de3f5-123">此外，每個 UM 樹系都必須設定為信任已部署 Lync Server 2013 的樹系，而且部署 Lync Server 2013 的樹系必須設定為信任每個 UM 樹系。</span><span class="sxs-lookup"><span data-stu-id="de3f5-123">In addition, each UM forest must be configured to trust the forest in which Lync Server 2013 is deployed, and the forest in which Lync Server 2013 is deployed must be configured to trust each UM forest.</span></span>

  - <span data-ttu-id="de3f5-124">在執行整合通訊服務的 Exchange 伺服器角色，以及執行 Lync Server 2013 的伺服器上執行整合步驟。</span><span class="sxs-lookup"><span data-stu-id="de3f5-124">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Lync Server 2013.</span></span> <span data-ttu-id="de3f5-125">在您執行 Lync Server 2013 整合步驟之前，您應該先執行 Exchange Server 整合通訊整合步驟。</span><span class="sxs-lookup"><span data-stu-id="de3f5-125">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="de3f5-126">若要查看在哪些伺服器及系統管理員角色上執行哪些整合步驟，請參閱 <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">整合內部部署整合通訊和 Lync Server 2013 的部署程式</A>。</span><span class="sxs-lookup"><span data-stu-id="de3f5-126">To see which integration steps are performed on which servers and by which administrator roles, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

<span data-ttu-id="de3f5-127">在執行 Exchange UM 的每一部伺服器上都必須提供下列工具：</span><span class="sxs-lookup"><span data-stu-id="de3f5-127">The following tools must be available on each server running Exchange UM:</span></span>

  - <span data-ttu-id="de3f5-128">Exchange 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="de3f5-128">Exchange Management Shell</span></span>

  - <span data-ttu-id="de3f5-129">指令碼 **exchucutil.ps1**，它會執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="de3f5-129">The script **exchucutil.ps1**, which performs the following tasks:</span></span>
    
      - <span data-ttu-id="de3f5-130">為每個 Lync Server 2013 建立 UM IP 閘道。</span><span class="sxs-lookup"><span data-stu-id="de3f5-130">Creates a UM IP gateway for each Lync Server 2013.</span></span>
    
      - <span data-ttu-id="de3f5-131">為每一個閘道建立群組搜尋。</span><span class="sxs-lookup"><span data-stu-id="de3f5-131">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="de3f5-132">每個群組搜尋的引導識別碼會指定與閘道相關聯之前端集區或 Standard Edition server 所使用的 UM SIP URI 撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="de3f5-132">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    
      - <span data-ttu-id="de3f5-133">授與 Lync Server 2013 在 Active Directory 網域服務中讀取 Exchange UM 物件的許可權。</span><span class="sxs-lookup"><span data-stu-id="de3f5-133">Grants Lync Server 2013 permission to read Exchange UM objects in Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="de3f5-134">本章節內容</span><span class="sxs-lookup"><span data-stu-id="de3f5-134">In This Section</span></span>

  - [<span data-ttu-id="de3f5-135">在執行 Microsoft Exchange Server 整合通訊的伺服器上設定憑證</span><span class="sxs-lookup"><span data-stu-id="de3f5-135">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [<span data-ttu-id="de3f5-136">在 Microsoft Exchange 上設定 Lync Server 2013 的整合通訊</span><span class="sxs-lookup"><span data-stu-id="de3f5-136">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


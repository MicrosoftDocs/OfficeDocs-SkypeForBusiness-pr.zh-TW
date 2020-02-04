---
title: Lync Server 2013：設定 Microsoft Exchange Server 上的 Unified Messaging 以搭配 Lync Serve 使用
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
ms.openlocfilehash: 5e2bc41d4fa0411c4184c0edda35d6d0cd98df9a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a><span data-ttu-id="a7240-102">設定 Microsoft Exchange Server 上的 Unified Messaging 以搭配 Lync Server 2013 使用</span><span class="sxs-lookup"><span data-stu-id="a7240-102">Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7240-103">_**主題上次修改日期：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="a7240-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a7240-104">如果您想要使用 Exchange 整合訊息（UM）來提供呼叫應答、Outlook Voice Access 或適用于企業語音使用者的自動助理服務，請參閱規劃檔中的<A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Lync Server 2013 中的 Exchange 整合訊息整合規劃</A>，然後依照本節中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="a7240-104">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planning for Exchange Unified Messaging integration in Lync Server 2013</A> in the Planning documentation, and then follow the instructions in this section.</span></span>



</div>

<span data-ttu-id="a7240-105">若要設定 Exchange 整合通訊（UM）以搭配企業語音使用，您必須執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="a7240-105">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

  - <span data-ttu-id="a7240-106">在運行 Exchange 整合通訊（UM）服務的伺服器上設定憑證</span><span class="sxs-lookup"><span data-stu-id="a7240-106">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a7240-107">將所有用戶端存取和信箱伺服器新增到所有 UM SIP URI 撥號方案。</span><span class="sxs-lookup"><span data-stu-id="a7240-107">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="a7240-108">如果不是，傳出通話路由將無法如期運作。</span><span class="sxs-lookup"><span data-stu-id="a7240-108">If not, outbound call routing won’t work as expected.</span></span>

    
    </div>

  - <span data-ttu-id="a7240-109">視需要建立一個或多個 UM SIP URI 撥號方案，以及訂閱者存取電話號碼，然後建立對應的 Lync Server 撥號方案。</span><span class="sxs-lookup"><span data-stu-id="a7240-109">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding Lync Server dial plans.</span></span>

  - <span data-ttu-id="a7240-110">使用**exchucutil. ps1**腳本來：</span><span class="sxs-lookup"><span data-stu-id="a7240-110">Use the **exchucutil.ps1** script to:</span></span>
    
      - <span data-ttu-id="a7240-111">建立 UM IP 閘道。</span><span class="sxs-lookup"><span data-stu-id="a7240-111">Create UM IP gateways.</span></span>
    
      - <span data-ttu-id="a7240-112">建立 UM 查尋群組。</span><span class="sxs-lookup"><span data-stu-id="a7240-112">Create UM hunt groups.</span></span>
    
      - <span data-ttu-id="a7240-113">授與 Lync Server 2013 讀取 UM Active Directory 網域服務物件的許可權。</span><span class="sxs-lookup"><span data-stu-id="a7240-113">Grant Lync Server 2013 permission to read UM Active Directory Domain Services objects.</span></span>

  - <span data-ttu-id="a7240-114">建立 UM 自動助理物件。</span><span class="sxs-lookup"><span data-stu-id="a7240-114">Create a UM auto-attendant object.</span></span>

  - <span data-ttu-id="a7240-115">建立訂閱者存取物件。</span><span class="sxs-lookup"><span data-stu-id="a7240-115">Create a subscriber access object.</span></span>

  - <span data-ttu-id="a7240-116">為每位使用者建立 SIP URI，並將使用者與 UM SIP URI 撥號方案產生關聯。</span><span class="sxs-lookup"><span data-stu-id="a7240-116">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="a7240-117">需求與建議</span><span class="sxs-lookup"><span data-stu-id="a7240-117">Requirements and Recommendations</span></span>

<span data-ttu-id="a7240-118">在開始之前，本節中的檔假設您已部署下列 Exchange 2013 角色：用戶端存取和信箱。</span><span class="sxs-lookup"><span data-stu-id="a7240-118">Before you begin, the documentation in this section assumes that you have deployed the following Exchange 2013 roles: Client Access and Mailbox.</span></span> <span data-ttu-id="a7240-119">在 Microsoft Exchange Server 2013 中，Exchange UM 在這些伺服器上以服務的方式執行。</span><span class="sxs-lookup"><span data-stu-id="a7240-119">In Microsoft Exchange Server 2013, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="a7240-120">如需有關部署 Exchange 2013 的詳細資訊，請參閱 Exchange 2013 TechNet 文件庫，網址為[http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)</span><span class="sxs-lookup"><span data-stu-id="a7240-120">For details about deploying Exchange 2013, see the Exchange 2013 TechNet Library at [http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)</span></span>

<span data-ttu-id="a7240-121">另請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="a7240-121">Also note the following:</span></span>

  - <span data-ttu-id="a7240-122">如果 Exchange UM 安裝在多個目錄林中，則必須針對每個 UM 林執行 Exchange Server 整合步驟。</span><span class="sxs-lookup"><span data-stu-id="a7240-122">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="a7240-123">此外，每個 UM 目錄林都必須設定為信任已部署 Lync Server 2013 的林，而部署 Lync Server 2013 的林必須設定為信任每個 UM 目錄林。</span><span class="sxs-lookup"><span data-stu-id="a7240-123">In addition, each UM forest must be configured to trust the forest in which Lync Server 2013 is deployed, and the forest in which Lync Server 2013 is deployed must be configured to trust each UM forest.</span></span>

  - <span data-ttu-id="a7240-124">整合步驟是在執行整合訊息服務的 Exchange 伺服器角色，以及在執行 Lync Server 2013 的伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="a7240-124">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Lync Server 2013.</span></span> <span data-ttu-id="a7240-125">在執行 Lync Server 2013 整合步驟之前，您應該執行 Exchange Server 整合訊息整合的步驟。</span><span class="sxs-lookup"><span data-stu-id="a7240-125">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a7240-126">若要查看對哪些伺服器以及哪些系統管理員角色執行哪些整合步驟，請參閱<A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">整合內部部署整合訊息和 Lync Server 2013 的部署程式</A>。</span><span class="sxs-lookup"><span data-stu-id="a7240-126">To see which integration steps are performed on which servers and by which administrator roles, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

<span data-ttu-id="a7240-127">在執行 Exchange UM 的每個伺服器上，都必須提供下列工具：</span><span class="sxs-lookup"><span data-stu-id="a7240-127">The following tools must be available on each server running Exchange UM:</span></span>

  - <span data-ttu-id="a7240-128">Exchange 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="a7240-128">Exchange Management Shell</span></span>

  - <span data-ttu-id="a7240-129">腳本**exchucutil. ps1**，可執行下列任務：</span><span class="sxs-lookup"><span data-stu-id="a7240-129">The script **exchucutil.ps1**, which performs the following tasks:</span></span>
    
      - <span data-ttu-id="a7240-130">為每個 Lync Server 2013 建立 UM IP 閘道。</span><span class="sxs-lookup"><span data-stu-id="a7240-130">Creates a UM IP gateway for each Lync Server 2013.</span></span>
    
      - <span data-ttu-id="a7240-131">為每個閘道建立一個 [查尋] 群組。</span><span class="sxs-lookup"><span data-stu-id="a7240-131">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="a7240-132">每個查尋群組的先導識別碼，會指定與閘道相關聯的前端池或標準版伺服器所使用的 UM SIP URI 撥號方案。</span><span class="sxs-lookup"><span data-stu-id="a7240-132">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    
      - <span data-ttu-id="a7240-133">授予 Lync Server 2013 在 Active Directory 網域服務中讀取 Exchange UM 物件的許可權。</span><span class="sxs-lookup"><span data-stu-id="a7240-133">Grants Lync Server 2013 permission to read Exchange UM objects in Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a7240-134">本節內容</span><span class="sxs-lookup"><span data-stu-id="a7240-134">In This Section</span></span>

  - [<span data-ttu-id="a7240-135">在運行 Microsoft Exchange Server 整合通訊的伺服器上設定憑證</span><span class="sxs-lookup"><span data-stu-id="a7240-135">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [<span data-ttu-id="a7240-136">在 Microsoft Exchange for Lync Server 2013 中設定整合通訊</span><span class="sxs-lookup"><span data-stu-id="a7240-136">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


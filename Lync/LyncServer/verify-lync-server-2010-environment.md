---
title: 驗證 Lync Server 2010 環境
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 248d779bc43b7c3e220728222aca030036f17e00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a><span data-ttu-id="851fa-102">驗證 Lync Server 2010 環境</span><span class="sxs-lookup"><span data-stu-id="851fa-102">Verify Lync Server 2010 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="851fa-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="851fa-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="851fa-104">在使用 Lync Server 2010 的共存狀態中部署 Lync Server 2013 之前，您必須確認已設定並啟動 Lync Server 2010 服務。</span><span class="sxs-lookup"><span data-stu-id="851fa-104">Before deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you need to verify that Lync Server 2010 services have been configured and started.</span></span> <span data-ttu-id="851fa-105">在部署 Lync Server 2013 試驗池之前，請務必先找出舊版環境中存在的重要服務和功能。</span><span class="sxs-lookup"><span data-stu-id="851fa-105">It is important to identify key services and features that exist in your legacy environment, prior to deploying a Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="851fa-106">在使用舊版 XMPP 部署在共存狀態中部署 Microsoft Lync Server 2013 XMPP 之前，您必須確認已設定並啟動舊版 XMPP 服務，並識別舊版 XMPP 設定支援的聯盟夥伴。</span><span class="sxs-lookup"><span data-stu-id="851fa-106">Before deploying Microsoft Lync Server 2013 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="851fa-107">驗證舊版 Lync Server 2010 部署需要下列各項：</span><span class="sxs-lookup"><span data-stu-id="851fa-107">Verifying your legacy Lync Server 2010 deployment entails the following:</span></span>

  - <span data-ttu-id="851fa-108">驗證 Lync Server 2010 服務已啟動</span><span class="sxs-lookup"><span data-stu-id="851fa-108">Verifying the Lync Server 2010 services are started</span></span>

  - <span data-ttu-id="851fa-109">在 Lync Server 2010 中查看拓撲和使用者。</span><span class="sxs-lookup"><span data-stu-id="851fa-109">Reviewing the topology and users in Lync Server 2010.</span></span>

  - <span data-ttu-id="851fa-110">驗證同盟和 Edge 伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="851fa-110">Verifying the federation and Edge server settings.</span></span>

  - <span data-ttu-id="851fa-111">驗證 XMPP 服務和聯盟夥伴。</span><span class="sxs-lookup"><span data-stu-id="851fa-111">Verifying XMPP services and federated partners.</span></span>

<span data-ttu-id="851fa-112">**驗證 Lync Server 2010 服務已啟動**</span><span class="sxs-lookup"><span data-stu-id="851fa-112">**Verify Lync Server 2010 Services are started**</span></span>

1.  <span data-ttu-id="851fa-113">從 Lync Server 2010 前端伺服器流覽至 [管理工具\\服務] 小程式。</span><span class="sxs-lookup"><span data-stu-id="851fa-113">From the Lync Server 2010 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="851fa-114">確認下列服務正在前端伺服器上執行：</span><span class="sxs-lookup"><span data-stu-id="851fa-114">Verify that the following services are running on the Front End Server:</span></span>
    
    <span data-ttu-id="851fa-115">![在]前端伺服器上執行的服務清單（在(images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "前端伺服器")上執行的服務）</span><span class="sxs-lookup"><span data-stu-id="851fa-115">![List of services running on Front End Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "List of services running on Front End Server")</span></span>

<span data-ttu-id="851fa-116">**在 Lync Server [控制台] 中查看 Lync Server 2010 拓撲**</span><span class="sxs-lookup"><span data-stu-id="851fa-116">**Review the Lync Server 2010 topology in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="851fa-117">使用 RTCUniversalServerAdmins 群組成員的帳戶或 CsAdministrator 或 CsUserAdministrator 系統管理角色的成員登入前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="851fa-117">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="851fa-118">開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="851fa-118">Open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="851fa-119">選取 [**拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="851fa-119">Select **Topology**.</span></span> <span data-ttu-id="851fa-120">確認您的 Lync Server 2010 部署中的各個伺服器都已列出。</span><span class="sxs-lookup"><span data-stu-id="851fa-120">Verify that the various servers in your Lync Server 2010 deployment are listed.</span></span>
    
    <span data-ttu-id="851fa-121">![Lync server 2010 [控制台拓撲] 頁面][(images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "lync Server 2010] 控制台的 [拓撲圖] 頁面")</span><span class="sxs-lookup"><span data-stu-id="851fa-121">![Lync Server 2010 Control Panel topology page](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 Control Panel topology page")</span></span>

<span data-ttu-id="851fa-122">**在 Lync Server [控制台] 中查看 Lync Server 2010 使用者**</span><span class="sxs-lookup"><span data-stu-id="851fa-122">**To review Lync Server 2010 users in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="851fa-123">開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="851fa-123">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="851fa-124">選取 [**使用者**]，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="851fa-124">Select **Users** and then click **Find**.</span></span>

3.  <span data-ttu-id="851fa-125">確認 [**註冊機構池**] 欄針對列出的每位使用者，指向 [Lync Server 2010] 池。</span><span class="sxs-lookup"><span data-stu-id="851fa-125">Verify that the **Registrar Pool** column points to the Lync Server 2010 pool for each user listed.</span></span>
    
    <span data-ttu-id="851fa-126">![Lync server 2010 [控制台]] 會列出使用者的(images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "lync Server 2010 [控制台")]</span><span class="sxs-lookup"><span data-stu-id="851fa-126">![Lync Server 2010 Control Panel listing users](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Control Panel listing users")</span></span>

<span data-ttu-id="851fa-127">**驗證 Lync Server 2010 Edge 與同盟設定**</span><span class="sxs-lookup"><span data-stu-id="851fa-127">**To verify Lync Server 2010 Edge and Federation Settings**</span></span>

1.  <span data-ttu-id="851fa-128">啟動拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="851fa-128">Start Topology Builder.</span></span>

2.  <span data-ttu-id="851fa-129">選取 [**從現有的部署下載拓撲**。</span><span class="sxs-lookup"><span data-stu-id="851fa-129">Select **Download Topology from existing deployment**.</span></span>

3.  <span data-ttu-id="851fa-130">選擇檔案名，然後以預設的 tbxml 檔案類型儲存拓撲。</span><span class="sxs-lookup"><span data-stu-id="851fa-130">Choose a file name and save the topology with the default .tbxml file type.</span></span>

4.  <span data-ttu-id="851fa-131">展開 Lync Server 2010 節點，以顯示部署中的各種伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="851fa-131">Expand the Lync Server 2010 node to reveal the various server roles in the deployment.</span></span>

5.  <span data-ttu-id="851fa-132">選取 [網站] 節點，然後驗證是否已設定 [**網站同盟路由指派**] 值。</span><span class="sxs-lookup"><span data-stu-id="851fa-132">Select the site node and verify if a **Site federation route assignment** value is set.</span></span>
    
    <span data-ttu-id="851fa-133">![拓撲建立器、網站同盟路由](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "拓撲建立器、網站同盟路由")</span><span class="sxs-lookup"><span data-stu-id="851fa-133">![Topology Builder, Site Federation Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topology Builder, Site Federation Route")</span></span>

6.  <span data-ttu-id="851fa-134">接著，選取 [標準版伺服器] 或 [企業版頂層端] 池。</span><span class="sxs-lookup"><span data-stu-id="851fa-134">Next, select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="851fa-135">判斷是否已針對低於 [資源**關聯**性] 的媒體設定 Edge 池。</span><span class="sxs-lookup"><span data-stu-id="851fa-135">Determine if an Edge pool has been configured for Media below **Associations**.</span></span>
    
    <span data-ttu-id="851fa-136">![顯示]伺服器和池拓撲建立器的拓撲產生器，(images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "顯示伺服器和池")</span><span class="sxs-lookup"><span data-stu-id="851fa-136">![Topology Builder showing servers and pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topology Builder showing servers and pools")</span></span>

7.  <span data-ttu-id="851fa-137">最後，選取 [邊緣] 池，並識別下一個躍點池是否已設定在**下一個躍點選取範圍**下。</span><span class="sxs-lookup"><span data-stu-id="851fa-137">Finally, select the Edge pool and identify if a Next hop pool is configured below **Next hop selection**.</span></span>
    
    <span data-ttu-id="851fa-138">![拓撲建立器，下一個躍點選取](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "拓撲建立器，下一個躍點選取")</span><span class="sxs-lookup"><span data-stu-id="851fa-138">![Topology Builder, Next hop selection](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topology Builder, Next hop selection")</span></span>

<span data-ttu-id="851fa-139">**驗證舊版 XMPP 聯盟合作夥伴設定**</span><span class="sxs-lookup"><span data-stu-id="851fa-139">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="851fa-140">從舊版 XMPP 伺服器流覽至 [管理工具\\服務] 小程式。</span><span class="sxs-lookup"><span data-stu-id="851fa-140">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="851fa-141">確認已啟動 Office 通訊伺服器 XMPP 閘道服務。</span><span class="sxs-lookup"><span data-stu-id="851fa-141">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="851fa-142">![Office 通訊伺服器 XMPP 閘道服務](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "OFFICE 通訊伺服器 XMPP 閘道服務")</span><span class="sxs-lookup"><span data-stu-id="851fa-142">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>


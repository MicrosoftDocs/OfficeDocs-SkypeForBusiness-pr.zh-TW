---
title: 確認 Lync Server 2010 環境
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72b04170df1a616aec595f72dce74cd15e8059b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a><span data-ttu-id="fb2fa-102">確認 Lync Server 2010 環境</span><span class="sxs-lookup"><span data-stu-id="fb2fa-102">Verify Lync Server 2010 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb2fa-103">_**主題上次修改日期：** 2012年-10-19_</span><span class="sxs-lookup"><span data-stu-id="fb2fa-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="fb2fa-104">在部署前處於共存狀態 」 與 Lync Server 2010 中的 Lync Server 2013，您需要確認 Lync Server 2010 服務已設定且啟動。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-104">Before deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you need to verify that Lync Server 2010 services have been configured and started.</span></span> <span data-ttu-id="fb2fa-105">請務必識別主要服務和存在於舊版環境，再部署 Lync Server 2013 試驗集區中的功能。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-105">It is important to identify key services and features that exist in your legacy environment, prior to deploying a Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="fb2fa-106">之前部署 Microsoft Lync Server 2013 XMPP 處於共存狀態與舊版 XMPP 部署，您必須確認舊版 XMPP 服務已設定並開始，並識別舊版 XMPP 設定為支援的同盟協力廠商。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-106">Before deploying Microsoft Lync Server 2013 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="fb2fa-107">確認舊版 Lync Server 2010 部署需要下列：</span><span class="sxs-lookup"><span data-stu-id="fb2fa-107">Verifying your legacy Lync Server 2010 deployment entails the following:</span></span>

  - <span data-ttu-id="fb2fa-108">確認 Lync Server 2010 服務已啟動</span><span class="sxs-lookup"><span data-stu-id="fb2fa-108">Verifying the Lync Server 2010 services are started</span></span>

  - <span data-ttu-id="fb2fa-109">檢閱的拓撲和 Lync Server 2010 中的使用者。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-109">Reviewing the topology and users in Lync Server 2010.</span></span>

  - <span data-ttu-id="fb2fa-110">確認同盟和 Edge server 設定。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-110">Verifying the federation and Edge server settings.</span></span>

  - <span data-ttu-id="fb2fa-111">確認 XMPP 服務和同盟協力廠商。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-111">Verifying XMPP services and federated partners.</span></span>

<span data-ttu-id="fb2fa-112">**確認 Lync Server 2010 服務已啟動**</span><span class="sxs-lookup"><span data-stu-id="fb2fa-112">**Verify Lync Server 2010 Services are started**</span></span>

1.  <span data-ttu-id="fb2fa-113">從 Lync Server 2010 前端伺服器，瀏覽至 [系統管理工具]\\服務] 小程式。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-113">From the Lync Server 2010 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="fb2fa-114">確認下列服務正在執行前端伺服器上：</span><span class="sxs-lookup"><span data-stu-id="fb2fa-114">Verify that the following services are running on the Front End Server:</span></span>
    
    <span data-ttu-id="fb2fa-115">![在前端伺服器上執行的服務清單](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "在前端伺服器上執行的服務清單")</span><span class="sxs-lookup"><span data-stu-id="fb2fa-115">![List of services running on Front End Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "List of services running on Front End Server")</span></span>

<span data-ttu-id="fb2fa-116">**檢閱 Lync Server Control Panel 中的 Lync Server 2010 拓撲**</span><span class="sxs-lookup"><span data-stu-id="fb2fa-116">**Review the Lync Server 2010 topology in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="fb2fa-117">使用 RTCUniversalServerAdmins 群組的成員帳戶、CsAdministrator 成員帳戶或 CsUserAdministrator 系統管理角色的成員帳戶，登入前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-117">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="fb2fa-118">開啟 Lync Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-118">Open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="fb2fa-119">選取 [**拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-119">Select **Topology**.</span></span> <span data-ttu-id="fb2fa-120">確認 Lync Server 2010 部署中的各種伺服器已列出。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-120">Verify that the various servers in your Lync Server 2010 deployment are listed.</span></span>
    
    <span data-ttu-id="fb2fa-121">![Lync Server 2010 控制台拓撲] 頁面上](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 控制台拓撲] 頁面上")</span><span class="sxs-lookup"><span data-stu-id="fb2fa-121">![Lync Server 2010 Control Panel topology page](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 Control Panel topology page")</span></span>

<span data-ttu-id="fb2fa-122">**若要檢閱 Lync Server Control Panel 中的 Lync Server 2010 使用者**</span><span class="sxs-lookup"><span data-stu-id="fb2fa-122">**To review Lync Server 2010 users in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="fb2fa-123">開啟 Lync Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-123">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="fb2fa-124">選取 [**使用者**]，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-124">Select **Users** and then click **Find**.</span></span>

3.  <span data-ttu-id="fb2fa-125">確認 [**登錄器集區**] 欄中指向列出每個使用者的 Lync Server 2010 集區。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-125">Verify that the **Registrar Pool** column points to the Lync Server 2010 pool for each user listed.</span></span>
    
    <span data-ttu-id="fb2fa-126">![列出使用者的 Lync Server 2010 Control Panel](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "列出使用者的 Lync Server 2010 Control Panel")</span><span class="sxs-lookup"><span data-stu-id="fb2fa-126">![Lync Server 2010 Control Panel listing users](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Control Panel listing users")</span></span>

<span data-ttu-id="fb2fa-127">**若要確認 Lync Server 2010 Edge 和同盟設定**</span><span class="sxs-lookup"><span data-stu-id="fb2fa-127">**To verify Lync Server 2010 Edge and Federation Settings**</span></span>

1.  <span data-ttu-id="fb2fa-128">啟動拓撲產生器]。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-128">Start Topology Builder.</span></span>

2.  <span data-ttu-id="fb2fa-129">選取 [**從現有部署下載拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-129">Select **Download Topology from existing deployment**.</span></span>

3.  <span data-ttu-id="fb2fa-130">選擇 [檔案名稱，預設的.tbxml 檔案類型儲存拓撲。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-130">Choose a file name and save the topology with the default .tbxml file type.</span></span>

4.  <span data-ttu-id="fb2fa-131">展開 [Lync Server 2010] 節點，顯示部署中的各種伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-131">Expand the Lync Server 2010 node to reveal the various server roles in the deployment.</span></span>

5.  <span data-ttu-id="fb2fa-132">選取 [網站] 節點，並確認已設定**站台同盟路由指派**值。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-132">Select the site node and verify if a **Site federation route assignment** value is set.</span></span>
    
    <span data-ttu-id="fb2fa-133">![拓撲產生器中，站台同盟路由](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "拓撲產生器中，站台同盟路由")</span><span class="sxs-lookup"><span data-stu-id="fb2fa-133">![Topology Builder, Site Federation Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topology Builder, Site Federation Route")</span></span>

6.  <span data-ttu-id="fb2fa-134">下一步]，選取 [Standard Edition Server 或 Enterprise Edition 前端集區]。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-134">Next, select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="fb2fa-135">判斷是否已設定媒體下方**關聯**Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-135">Determine if an Edge pool has been configured for Media below **Associations**.</span></span>
    
    <span data-ttu-id="fb2fa-136">![顯示伺服器和集區的拓撲產生器](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "顯示伺服器和集區的拓撲產生器")</span><span class="sxs-lookup"><span data-stu-id="fb2fa-136">![Topology Builder showing servers and pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topology Builder showing servers and pools")</span></span>

7.  <span data-ttu-id="fb2fa-137">最後，選取 [Edge 集區並識別是否有設定**下一個躍點選取範圍**的下一個躍點集區。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-137">Finally, select the Edge pool and identify if a Next hop pool is configured below **Next hop selection**.</span></span>
    
    <span data-ttu-id="fb2fa-138">![拓撲產生器中下, 一個躍點選取範圍](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "拓撲產生器中下, 一個躍點選取範圍")</span><span class="sxs-lookup"><span data-stu-id="fb2fa-138">![Topology Builder, Next hop selection](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topology Builder, Next hop selection")</span></span>

<span data-ttu-id="fb2fa-139">**確認舊版 XMPP 同盟協力廠商設定**</span><span class="sxs-lookup"><span data-stu-id="fb2fa-139">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="fb2fa-140">從舊版 XMPP 伺服器瀏覽至系統管理工具\\服務] 小程式。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-140">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="fb2fa-141">確認 Office Communications Server XMPP 閘道服務已啟動。</span><span class="sxs-lookup"><span data-stu-id="fb2fa-141">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="fb2fa-142">![Office Communications Server XMPP 閘道服務](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP 閘道服務")</span><span class="sxs-lookup"><span data-stu-id="fb2fa-142">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>


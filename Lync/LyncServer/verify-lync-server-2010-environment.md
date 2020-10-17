---
title: 驗證 Lync Server 2010 環境
description: 驗證 Lync Server 2010 環境。
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
ms.openlocfilehash: 570fd2a9efdc90899ff4f91146b7aeb1991f6764
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555579"
---
# <a name="verify-lync-server-2010-environment"></a><span data-ttu-id="2608b-103">驗證 Lync Server 2010 環境</span><span class="sxs-lookup"><span data-stu-id="2608b-103">Verify Lync Server 2010 environment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2608b-104">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="2608b-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="2608b-105">在使用 Lync Server 2010 的共存狀態中部署 Lync Server 2013 之前，您必須確認已設定並啟動 Lync Server 2010 服務。</span><span class="sxs-lookup"><span data-stu-id="2608b-105">Before deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you need to verify that Lync Server 2010 services have been configured and started.</span></span> <span data-ttu-id="2608b-106">在部署 Lync Server 2013 試驗集區之前，請務必先識別舊環境中存在的重要服務和功能。</span><span class="sxs-lookup"><span data-stu-id="2608b-106">It is important to identify key services and features that exist in your legacy environment, prior to deploying a Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="2608b-107">在採用舊版 XMPP 部署的共存狀態中部署 Microsoft Lync Server 2013 XMPP 之前，您必須確認舊版 XMPP 服務已設定並啟動，並識別舊版 XMPP 設定所支援的同盟合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="2608b-107">Before deploying Microsoft Lync Server 2013 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="2608b-108">驗證舊版 Lync Server 2010 部署需要下列專案：</span><span class="sxs-lookup"><span data-stu-id="2608b-108">Verifying your legacy Lync Server 2010 deployment entails the following:</span></span>

  - <span data-ttu-id="2608b-109">驗證是否已啟動 Lync Server 2010 服務</span><span class="sxs-lookup"><span data-stu-id="2608b-109">Verifying the Lync Server 2010 services are started</span></span>

  - <span data-ttu-id="2608b-110">在 Lync Server 2010 中查看拓撲和使用者。</span><span class="sxs-lookup"><span data-stu-id="2608b-110">Reviewing the topology and users in Lync Server 2010.</span></span>

  - <span data-ttu-id="2608b-111">驗證同盟及 Edge server 設定。</span><span class="sxs-lookup"><span data-stu-id="2608b-111">Verifying the federation and Edge server settings.</span></span>

  - <span data-ttu-id="2608b-112">驗證 XMPP 服務和同盟協力廠商。</span><span class="sxs-lookup"><span data-stu-id="2608b-112">Verifying XMPP services and federated partners.</span></span>

<span data-ttu-id="2608b-113">**驗證是否已啟動 Lync Server 2010 服務**</span><span class="sxs-lookup"><span data-stu-id="2608b-113">**Verify Lync Server 2010 Services are started**</span></span>

1.  <span data-ttu-id="2608b-114">從 Lync Server 2010 前端伺服器，流覽至 [系統管理工具 \\ 服務] 小程式。</span><span class="sxs-lookup"><span data-stu-id="2608b-114">From the Lync Server 2010 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="2608b-115">確認下列服務正在前端伺服器上執行：</span><span class="sxs-lookup"><span data-stu-id="2608b-115">Verify that the following services are running on the Front End Server:</span></span>
    
    <span data-ttu-id="2608b-116">![前端伺服器上執行的服務清單](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "前端伺服器上執行的服務清單")</span><span class="sxs-lookup"><span data-stu-id="2608b-116">![List of services running on Front End Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "List of services running on Front End Server")</span></span>

<span data-ttu-id="2608b-117">**在 Lync Server 控制台中檢查 Lync Server 2010 拓撲**</span><span class="sxs-lookup"><span data-stu-id="2608b-117">**Review the Lync Server 2010 topology in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="2608b-118">使用 RTCUniversalServerAdmins 群組的成員帳戶、CsAdministrator 成員帳戶或 CsUserAdministrator 系統管理角色的成員帳戶，登入前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="2608b-118">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="2608b-119">開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="2608b-119">Open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="2608b-120">選取 [ **拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="2608b-120">Select **Topology**.</span></span> <span data-ttu-id="2608b-121">確認您的 Lync Server 2010 部署中的各種伺服器都已列出。</span><span class="sxs-lookup"><span data-stu-id="2608b-121">Verify that the various servers in your Lync Server 2010 deployment are listed.</span></span>
    
    <span data-ttu-id="2608b-122">![Lync Server 2010 控制台拓撲頁面](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 控制台拓撲頁面")</span><span class="sxs-lookup"><span data-stu-id="2608b-122">![Lync Server 2010 Control Panel topology page](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 Control Panel topology page")</span></span>

<span data-ttu-id="2608b-123">**在 Lync Server 控制台中檢查 Lync Server 2010 使用者**</span><span class="sxs-lookup"><span data-stu-id="2608b-123">**To review Lync Server 2010 users in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="2608b-124">開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="2608b-124">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="2608b-125">選取 [ **使用者** ]，然後按一下 [ **尋找**]。</span><span class="sxs-lookup"><span data-stu-id="2608b-125">Select **Users** and then click **Find**.</span></span>

3.  <span data-ttu-id="2608b-126">確認 [ **註冊集** 區] 欄針對所列的每位使用者，指向 [Lync Server 2010 集區]。</span><span class="sxs-lookup"><span data-stu-id="2608b-126">Verify that the **Registrar Pool** column points to the Lync Server 2010 pool for each user listed.</span></span>
    
    <span data-ttu-id="2608b-127">![Lync Server 2010 控制台，列出使用者](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 控制台，列出使用者")</span><span class="sxs-lookup"><span data-stu-id="2608b-127">![Lync Server 2010 Control Panel listing users](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Control Panel listing users")</span></span>

<span data-ttu-id="2608b-128">**驗證 Lync Server 2010 Edge 及同盟設定**</span><span class="sxs-lookup"><span data-stu-id="2608b-128">**To verify Lync Server 2010 Edge and Federation Settings**</span></span>

1.  <span data-ttu-id="2608b-129">啟動拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="2608b-129">Start Topology Builder.</span></span>

2.  <span data-ttu-id="2608b-130">選取 [ **從現有的部署下載拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="2608b-130">Select **Download Topology from existing deployment**.</span></span>

3.  <span data-ttu-id="2608b-131">選擇檔案名，並以預設的 redmond.tbxml 檔案類型儲存拓撲。</span><span class="sxs-lookup"><span data-stu-id="2608b-131">Choose a file name and save the topology with the default .tbxml file type.</span></span>

4.  <span data-ttu-id="2608b-132">展開 Lync Server 2010 節點，以顯示部署中的各種伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="2608b-132">Expand the Lync Server 2010 node to reveal the various server roles in the deployment.</span></span>

5.  <span data-ttu-id="2608b-133">選取 [網站] 節點，並確認是否已設定 [ **網站同盟路由指派** ] 值。</span><span class="sxs-lookup"><span data-stu-id="2608b-133">Select the site node and verify if a **Site federation route assignment** value is set.</span></span>
    
    <span data-ttu-id="2608b-134">![拓撲產生器的網站同盟路由](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "拓撲產生器的網站同盟路由")</span><span class="sxs-lookup"><span data-stu-id="2608b-134">![Topology Builder, Site Federation Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topology Builder, Site Federation Route")</span></span>

6.  <span data-ttu-id="2608b-135">接下來，選取 [Standard Edition Server] 或 [Enterprise Edition 前端集區]。</span><span class="sxs-lookup"><span data-stu-id="2608b-135">Next, select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="2608b-136">判斷是否已針對下層 **關聯**的媒體設定 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="2608b-136">Determine if an Edge pool has been configured for Media below **Associations**.</span></span>
    
    <span data-ttu-id="2608b-137">![顯示伺服器和集區的拓撲產生器](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "顯示伺服器和集區的拓撲產生器")</span><span class="sxs-lookup"><span data-stu-id="2608b-137">![Topology Builder showing servers and pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topology Builder showing servers and pools")</span></span>

7.  <span data-ttu-id="2608b-138">最後，選取 Edge 集區，並識別下一個躍點集區是否已在 **下一個躍點選取範圍**下設定。</span><span class="sxs-lookup"><span data-stu-id="2608b-138">Finally, select the Edge pool and identify if a Next hop pool is configured below **Next hop selection**.</span></span>
    
    <span data-ttu-id="2608b-139">![拓撲產生器，下一個躍點選取範圍](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "拓撲產生器，下一個躍點選取範圍")</span><span class="sxs-lookup"><span data-stu-id="2608b-139">![Topology Builder, Next hop selection](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topology Builder, Next hop selection")</span></span>

<span data-ttu-id="2608b-140">**驗證舊版 XMPP 同盟協力廠商設定**</span><span class="sxs-lookup"><span data-stu-id="2608b-140">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="2608b-141">在舊版 XMPP 伺服器上，流覽至 [系統管理工具 \\ 服務] 小程式。</span><span class="sxs-lookup"><span data-stu-id="2608b-141">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="2608b-142">確認已啟動 Office 通訊伺服器 XMPP 閘道服務。</span><span class="sxs-lookup"><span data-stu-id="2608b-142">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="2608b-143">![Office 通訊伺服器 XMPP 閘道服務](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office 通訊伺服器 XMPP 閘道服務")</span><span class="sxs-lookup"><span data-stu-id="2608b-143">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>


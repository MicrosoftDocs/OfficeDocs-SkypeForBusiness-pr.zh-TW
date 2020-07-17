---
title: 部署試驗 Edge Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4245efe0faf5dfe947cc52fb22a447e46c0b3e8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="04dd2-102">部署試驗 Edge Server</span><span class="sxs-lookup"><span data-stu-id="04dd2-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04dd2-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="04dd2-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="04dd2-104">本主題著重于部署 Lync Server 2013 Edge Server 之前，請先注意您應注意的配置設定。</span><span class="sxs-lookup"><span data-stu-id="04dd2-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="04dd2-105">本節只著重在試驗 Edge 集區部署期間應該考量的要點。</span><span class="sxs-lookup"><span data-stu-id="04dd2-105">This section only highlights key points you should consider as part of your pilot Edge pool deployment.</span></span> <span data-ttu-id="04dd2-106">如需詳細步驟，請參閱部署檔中的「[部署 Lync Server 2013 中的外部使用者存取](lync-server-2013-deploying-external-user-access.md)」，它會說明部署程式，也會提供外部使用者存取的設定資訊。</span><span class="sxs-lookup"><span data-stu-id="04dd2-106">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="04dd2-p102">啟動 [定義新 Edge 集區精靈]\*\*\*\* 逐步完成設定，請檢閱下列步驟中的重要組態設定。請注意，下面只列出了「定義新 Edge 集區精靈」\*\*\*\* 部分頁面而已。</span><span class="sxs-lookup"><span data-stu-id="04dd2-p102">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="04dd2-109">**定義 Edge 集區**</span><span class="sxs-lookup"><span data-stu-id="04dd2-109">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="04dd2-110">使用拓撲產生器，開啟試驗集區拓撲。</span><span class="sxs-lookup"><span data-stu-id="04dd2-110">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="04dd2-111">流覽至 [Lync Server 2013] 節點。</span><span class="sxs-lookup"><span data-stu-id="04dd2-111">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="04dd2-112">用滑鼠右鍵按一下 [Edge 集區]\*\*\*\*，然後按一下 [新增 Edge 集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="04dd2-112">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="04dd2-113">![[定義新的 Edge 集區] 對話方塊](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "[定義新的 Edge 集區] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="04dd2-113">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="04dd2-114">Edge 集區可以是 [多部電腦集區]\*\*\*\* 或 [單一電腦集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="04dd2-114">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="04dd2-115">![[定義 Edge 集區 FQDN] 對話方塊](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "[定義 Edge 集區 FQDN] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="04dd2-115">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="04dd2-116">在「選取功能」\*\*\*\* 頁面上，請勿啟用同盟或 XMPP 同盟。</span><span class="sxs-lookup"><span data-stu-id="04dd2-116">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="04dd2-117">同盟和 XMPP 同盟目前是透過舊版 Office 通訊伺服器 2007 R2 Edge Server 路由傳送。</span><span class="sxs-lookup"><span data-stu-id="04dd2-117">Federation and XMPP federation are currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="04dd2-118">在移轉的後期階段，將會設定這些功能。</span><span class="sxs-lookup"><span data-stu-id="04dd2-118">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="04dd2-119">![[選取功能] 對話方塊](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "[選取功能] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="04dd2-119">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="04dd2-120">接著，繼續完成下列精靈頁面：「選取 IP 選項」\*\*\*\*、「外部 FQDN」\*\*\*\*、「定義內部 IP 位址」\*\*\*\* 及「定義外部 IP 位址」\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="04dd2-120">Next, continue completing the following wizard pages: **Select IP options**, **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="04dd2-121">在 [**定義下一個躍點]** 頁面上，選取 Lync Server 2013 Edge 集區的下一個躍點 Director。</span><span class="sxs-lookup"><span data-stu-id="04dd2-121">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2013 Edge pool.</span></span>
    
    <span data-ttu-id="04dd2-122">![[定義新的 Edge 集區] 對話方塊，下一個躍點集區清單](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "[定義新的 Edge 集區] 對話方塊，下一個躍點集區清單")</span><span class="sxs-lookup"><span data-stu-id="04dd2-122">![Define New Edge Pool dialog, Next hop pool list](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Define New Edge Pool dialog, Next hop pool list")</span></span>

7.  <span data-ttu-id="04dd2-123">在 [**建立前端**集區] 頁面上，請勿在此時間建立集區與此 Edge 集區的關聯。</span><span class="sxs-lookup"><span data-stu-id="04dd2-123">On the **Associate Front End pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="04dd2-124">外部媒體流量目前是透過舊版 Office 通訊伺服器 2007 R2 Edge Server 路由傳送。</span><span class="sxs-lookup"><span data-stu-id="04dd2-124">External media traffic is currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="04dd2-125">這項設定到了移轉的後期階段還會再調整。</span><span class="sxs-lookup"><span data-stu-id="04dd2-125">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="04dd2-126">![[定義新的 Edge 集區] 對話方塊](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "[定義新的 Edge 集區] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="04dd2-126">![Define New Edge Pool dialog](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Define New Edge Pool dialog")</span></span>

8.  <span data-ttu-id="04dd2-127">按一下 [完成]\*\*\*\*，然後 [發行]\*\*\*\* 拓撲。</span><span class="sxs-lookup"><span data-stu-id="04dd2-127">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="04dd2-128">請遵循部署檔中的[Lync Server 2013 安裝 Edge](lync-server-2013-install-edge-servers.md) server 中的步驟，將檔案安裝在新的 Edge Server 上、設定憑證，然後啟動服務。</span><span class="sxs-lookup"><span data-stu-id="04dd2-128">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="04dd2-129">在部署檔中遵循在[Lync Server 2013 部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)主題的指導方針非常重要。</span><span class="sxs-lookup"><span data-stu-id="04dd2-129">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="04dd2-130">本節只提供安裝這些伺服器角色時，部分組態設定的指示。</span><span class="sxs-lookup"><span data-stu-id="04dd2-130">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="04dd2-131">現在，您應該會有傳統的 Office 通訊伺服器 2007 R2 Edge Server 部署，其使用 BackCompatSite 所表示的狀態，與 Lync Server 2013 Edge server 部署平行。</span><span class="sxs-lookup"><span data-stu-id="04dd2-131">You should now have a legacy Office Communications Server 2007 R2 Edge server deployment, indicated by the presence of the BackCompatSite, in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="04dd2-132">同盟設定為使用 Office 通訊伺服器 2007 R2 Director。</span><span class="sxs-lookup"><span data-stu-id="04dd2-132">Federation is configured to use the Office Communications Server 2007 R2 Director.</span></span> <span data-ttu-id="04dd2-133">確認部署雙方皆可正常運作、服務已啟用，且您也能管理每個部署，接著，就可以前往下一個階段。</span><span class="sxs-lookup"><span data-stu-id="04dd2-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

<span data-ttu-id="04dd2-134">![顯示 OCS Edge Server 的拓撲產生器](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "顯示 OCS Edge Server 的拓撲產生器")</span><span class="sxs-lookup"><span data-stu-id="04dd2-134">![Topology Builder showing OCS Edge Server](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topology Builder showing OCS Edge Server")</span></span>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 部署試驗 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4d8fbf34e618c5bf41d3b005c70897c5dddb69
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="3baef-102">部署試驗 Edge Server</span><span class="sxs-lookup"><span data-stu-id="3baef-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3baef-103">_**主題上次修改日期：** 2012年-10-19_</span><span class="sxs-lookup"><span data-stu-id="3baef-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3baef-104">本主題會醒目提示您應該要知道再部署 Lync Server 2013 Edge Server 的組態設定。</span><span class="sxs-lookup"><span data-stu-id="3baef-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="3baef-105">針對 Lync Server 2013 的部署和設定程序是非常類似於 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="3baef-105">The deployment and configuration processes for Lync Server 2013 are very similar to Lync Server 2010.</span></span> <span data-ttu-id="3baef-106">本節只著重在部署試驗集區時應該考量的要點。</span><span class="sxs-lookup"><span data-stu-id="3baef-106">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="3baef-107">如需詳細步驟，請參閱部署文件，其中說明的部署程序，同時也讓外部使用者存取的組態資訊中的[Deploying Lync Server 2013 中的外部使用者存取](lync-server-2013-deploying-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="3baef-107">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="3baef-p102">啟動 [定義新 Edge 集區精靈]\*\*\*\* 逐步完成設定，請檢閱下列步驟中的重要組態設定。請注意，下面只列出了「定義新 Edge 集區精靈」\*\*\*\* 部分頁面而已。</span><span class="sxs-lookup"><span data-stu-id="3baef-p102">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="3baef-110">**定義 Edge 集區**</span><span class="sxs-lookup"><span data-stu-id="3baef-110">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="3baef-111">以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。</span><span class="sxs-lookup"><span data-stu-id="3baef-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="3baef-112">瀏覽至 [Lync Server 2013] 節點。</span><span class="sxs-lookup"><span data-stu-id="3baef-112">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="3baef-113">用滑鼠右鍵按一下 [Edge 集區]\*\*\*\*，然後按一下 [新增 Edge 集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3baef-113">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="3baef-114">![定義新的 Edge 集區] 對話方塊](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "定義新的 Edge 集區] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="3baef-114">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="3baef-115">Edge 集區可以是 [多部電腦集區]\*\*\*\* 或 [單一電腦集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3baef-115">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="3baef-116">![定義 Edge 集區 FQDN] 對話方塊](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "定義 Edge 集區 FQDN] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="3baef-116">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="3baef-117">在「選取功能」\*\*\*\* 頁面上，請勿啟用同盟或 XMPP 同盟。</span><span class="sxs-lookup"><span data-stu-id="3baef-117">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="3baef-118">同盟和 XMPP 同盟兩者目前路由到舊版的 Lync Server 2010 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="3baef-118">Federation and XMPP federation are both currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="3baef-119">在移轉的後期階段，將會設定這些功能。</span><span class="sxs-lookup"><span data-stu-id="3baef-119">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="3baef-120">![[選取功能] 對話方塊](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "[選取功能] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="3baef-120">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="3baef-121">接下來，繼續完成下列精靈頁面：**外部 Fqdn**、**定義內部 IP 位址**，以及**定義外部 IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="3baef-121">Next, continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="3baef-122">在 [**定義下一個躍點**] 頁面上，選取 Lync Server 2010 Edge 集區的下一個躍點的 Director。</span><span class="sxs-lookup"><span data-stu-id="3baef-122">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2010 Edge pool.</span></span>
    
    <span data-ttu-id="3baef-123">![定義下一個躍點] 對話方塊](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "定義下一個躍點] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="3baef-123">![Define the Next Hop dialog box](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Define the Next Hop dialog box")</span></span>

7.  <span data-ttu-id="3baef-124">在**建立關聯的前端或中繼集區]** 頁面上，不會關聯的集區與此 Edge 集區這一次。</span><span class="sxs-lookup"><span data-stu-id="3baef-124">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="3baef-125">外部媒體流量目前路由到舊版的 Lync Server 2010 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="3baef-125">External media traffic is currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="3baef-126">這項設定到了移轉的後期階段還會再調整。</span><span class="sxs-lookup"><span data-stu-id="3baef-126">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="3baef-127">![建立前端集區] 對話方塊中的關聯](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "建立前端集區] 對話方塊中的關聯")</span><span class="sxs-lookup"><span data-stu-id="3baef-127">![Associate Front End Pools dialog box](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Associate Front End Pools dialog box")</span></span>

8.  <span data-ttu-id="3baef-128">按一下 [完成]\*\*\*\*，然後 [發行]\*\*\*\* 拓撲。</span><span class="sxs-lookup"><span data-stu-id="3baef-128">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="3baef-129">請遵循[Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md)中新的 Edge Server 上安裝檔案、 設定憑證及啟動服務部署 > 文件中的步驟。</span><span class="sxs-lookup"><span data-stu-id="3baef-129">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="3baef-130">都是非常重要的是您遵循部署文件中的主題[部署 Lync Server 2013 中的外部使用者存取](lync-server-2013-deploying-external-user-access.md)中的指導方針。</span><span class="sxs-lookup"><span data-stu-id="3baef-130">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="3baef-131">本節只提供安裝這些伺服器角色時，部分組態設定的指示。</span><span class="sxs-lookup"><span data-stu-id="3baef-131">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="3baef-132">現在，您應該有舊版 Lync Server 2010 Edge Server 與 Lync Server 2013 Edge server 部署同時部署。</span><span class="sxs-lookup"><span data-stu-id="3baef-132">You should now have a legacy Lync Server 2010 Edge Server deployed in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="3baef-133">確認部署雙方皆可正常運作、服務已啟用，且您也能管理每個部署，接著，就可以前往下一個階段。</span><span class="sxs-lookup"><span data-stu-id="3baef-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


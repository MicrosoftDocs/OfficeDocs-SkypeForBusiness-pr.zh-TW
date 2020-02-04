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
ms.openlocfilehash: cc9f88d731873a16535e80eb0726aec8335e447b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="1cecf-102">部署試驗 Edge Server</span><span class="sxs-lookup"><span data-stu-id="1cecf-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1cecf-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="1cecf-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="1cecf-104">本主題重點說明在部署 Lync Server 2013 Edge 伺服器之前，您應該注意的配置設定。</span><span class="sxs-lookup"><span data-stu-id="1cecf-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="1cecf-105">Lync Server 2013 的部署與設定處理常式與 Lync Server 2010 非常類似。</span><span class="sxs-lookup"><span data-stu-id="1cecf-105">The deployment and configuration processes for Lync Server 2013 are very similar to Lync Server 2010.</span></span> <span data-ttu-id="1cecf-106">此區段只會醒目提示您要考慮的重要重點，做為您的試驗池部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="1cecf-106">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="1cecf-107">如需詳細步驟，請參閱部署檔中的[Lync Server 2013 部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)（描述部署程式），同時提供外部使用者存取的設定資訊。</span><span class="sxs-lookup"><span data-stu-id="1cecf-107">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="1cecf-108">當您流覽 [**定義新的邊緣池**] 嚮導時，請參閱下列步驟中所示的 [金鑰設定] 設定。</span><span class="sxs-lookup"><span data-stu-id="1cecf-108">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="1cecf-109">請注意，只有幾頁會顯示 [**定義新的邊緣池**] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="1cecf-109">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="1cecf-110">**定義邊緣池**</span><span class="sxs-lookup"><span data-stu-id="1cecf-110">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="1cecf-111">登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。</span><span class="sxs-lookup"><span data-stu-id="1cecf-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="1cecf-112">流覽至 Lync Server 2013 節點。</span><span class="sxs-lookup"><span data-stu-id="1cecf-112">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="1cecf-113">以滑鼠右鍵按一下 [**邊緣池**]，然後按一下 [**新增邊緣池**]。</span><span class="sxs-lookup"><span data-stu-id="1cecf-113">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="1cecf-114">![[定義新的 Edge 集區] 對話方塊](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "[定義新的 Edge 集區] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="1cecf-114">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="1cecf-115">Edge 池可以是**多個電腦池**或**單一電腦池**。</span><span class="sxs-lookup"><span data-stu-id="1cecf-115">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="1cecf-116">![[定義 Edge 集區 FQDN] 對話方塊](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "[定義 Edge 集區 FQDN] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="1cecf-116">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="1cecf-117">在 [**選取功能**] 頁面上，不要啟用同盟或 XMPP 同盟。</span><span class="sxs-lookup"><span data-stu-id="1cecf-117">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="1cecf-118">同盟與 XMPP 同盟目前是透過舊版 Lync Server 2010 Edge 伺服器路由。</span><span class="sxs-lookup"><span data-stu-id="1cecf-118">Federation and XMPP federation are both currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="1cecf-119">這些功能將會在稍後的遷移階段進行設定。</span><span class="sxs-lookup"><span data-stu-id="1cecf-119">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="1cecf-120">![[選取功能] 對話方塊](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "[選取功能] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="1cecf-120">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="1cecf-121">接著，繼續完成下列嚮導頁面：**外部 fqdn**、**定義內部 ip 位址**，以及**定義外部 ip 位址**。</span><span class="sxs-lookup"><span data-stu-id="1cecf-121">Next, continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="1cecf-122">在 [**定義下一個躍點]** 頁面上，選取 Lync Server 2010 Edge 池下一個躍點的主管。</span><span class="sxs-lookup"><span data-stu-id="1cecf-122">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2010 Edge pool.</span></span>
    
    <span data-ttu-id="1cecf-123">![[定義下一個躍點] 對話方塊](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "[定義下一個躍點] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="1cecf-123">![Define the Next Hop dialog box](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Define the Next Hop dialog box")</span></span>

7.  <span data-ttu-id="1cecf-124">在 [**關聯前端或轉送池**] 頁面上，請勿在此時將池與此 Edge 池建立關聯。</span><span class="sxs-lookup"><span data-stu-id="1cecf-124">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="1cecf-125">外部媒體流量目前是透過舊版 Lync Server 2010 Edge 伺服器路由。</span><span class="sxs-lookup"><span data-stu-id="1cecf-125">External media traffic is currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="1cecf-126">此設定將會在稍後的遷移階段進行設定。</span><span class="sxs-lookup"><span data-stu-id="1cecf-126">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="1cecf-127">![[建立前端集區的關聯] 對話方塊](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "[建立前端集區的關聯] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="1cecf-127">![Associate Front End Pools dialog box](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Associate Front End Pools dialog box")</span></span>

8.  <span data-ttu-id="1cecf-128">按一下 **[完成]** ，然後**發佈**拓撲。</span><span class="sxs-lookup"><span data-stu-id="1cecf-128">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="1cecf-129">請依照部署檔中的[Lync Server 2013 安裝邊緣](lync-server-2013-install-edge-servers.md)伺服器中的步驟進行，以在新的 Edge 伺服器上安裝檔案、設定憑證，然後啟動服務。</span><span class="sxs-lookup"><span data-stu-id="1cecf-129">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="1cecf-130">在部署檔中，請遵循在[Lync Server 2013 中部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)主題中的準則，這一點非常重要。</span><span class="sxs-lookup"><span data-stu-id="1cecf-130">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="1cecf-131">本節僅提供安裝這些伺服器角色時設定設定的一些指導方針。</span><span class="sxs-lookup"><span data-stu-id="1cecf-131">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="1cecf-132">您現在應該會與 Lync Server 2013 Edge 伺服器部署並行部署舊版 Lync Server 2010 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="1cecf-132">You should now have a legacy Lync Server 2010 Edge Server deployed in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="1cecf-133">確認這兩個部署都能正常運作、服務已啟動，而且您可以在移至下一個階段之前管理每個部署。</span><span class="sxs-lookup"><span data-stu-id="1cecf-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


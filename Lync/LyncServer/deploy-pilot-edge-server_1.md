---
title: 部署試驗 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 686973f9334b9bf376a2e56c52f3306cf243c0eb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="f4355-102">部署試驗 Edge Server</span><span class="sxs-lookup"><span data-stu-id="f4355-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4355-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="f4355-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="f4355-104">本主題重點說明在部署 Lync Server 2013 Edge 伺服器之前，您應該注意的配置設定。</span><span class="sxs-lookup"><span data-stu-id="f4355-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="f4355-105">此區段只會醒目提示您要考慮的重要重點，就像是您的試點邊緣池部署。</span><span class="sxs-lookup"><span data-stu-id="f4355-105">This section only highlights key points you should consider as part of your pilot Edge pool deployment.</span></span> <span data-ttu-id="f4355-106">如需詳細步驟，請參閱部署檔中的[Lync Server 2013 部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)（描述部署程式），同時提供外部使用者存取的設定資訊。</span><span class="sxs-lookup"><span data-stu-id="f4355-106">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="f4355-107">當您流覽 [**定義新的邊緣池**] 嚮導時，請參閱下列步驟中所示的 [金鑰設定] 設定。</span><span class="sxs-lookup"><span data-stu-id="f4355-107">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="f4355-108">請注意，只有幾頁會顯示 [**定義新的邊緣池**] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="f4355-108">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="f4355-109">**定義邊緣池**</span><span class="sxs-lookup"><span data-stu-id="f4355-109">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="f4355-110">使用 [拓撲建立器] 開啟 [試驗] 泳池拓撲。</span><span class="sxs-lookup"><span data-stu-id="f4355-110">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="f4355-111">流覽至 Lync Server 2013 節點。</span><span class="sxs-lookup"><span data-stu-id="f4355-111">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="f4355-112">以滑鼠右鍵按一下 [**邊緣池**]，然後按一下 [**新增邊緣池**]。</span><span class="sxs-lookup"><span data-stu-id="f4355-112">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="f4355-113">![[定義新的 Edge 集區] 對話方塊](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "[定義新的 Edge 集區] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="f4355-113">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="f4355-114">Edge 池可以是**多個電腦池**或**單一電腦池**。</span><span class="sxs-lookup"><span data-stu-id="f4355-114">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="f4355-115">![[定義 Edge 集區 FQDN] 對話方塊](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "[定義 Edge 集區 FQDN] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="f4355-115">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="f4355-116">在 [**選取功能**] 頁面上，不要啟用同盟或 XMPP 同盟。</span><span class="sxs-lookup"><span data-stu-id="f4355-116">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="f4355-117">同盟與 XMPP 同盟目前是透過舊版 Office 通訊伺服器 2007 R2 Edge 伺服器路由。</span><span class="sxs-lookup"><span data-stu-id="f4355-117">Federation and XMPP federation are currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="f4355-118">這些功能將會在稍後的遷移階段進行設定。</span><span class="sxs-lookup"><span data-stu-id="f4355-118">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="f4355-119">![[選取功能] 對話方塊](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "[選取功能] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="f4355-119">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="f4355-120">接著，繼續完成下列嚮導頁面：**選取 [IP 選項**]、[**外部 fqdn**]、[**定義內部 Ip 位址**]，並**定義外部 ip 位址**。</span><span class="sxs-lookup"><span data-stu-id="f4355-120">Next, continue completing the following wizard pages: **Select IP options**, **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="f4355-121">在 [**定義下一個躍點]** 頁面上，選取 Lync Server 2013 Edge 池下一個躍點的主管。</span><span class="sxs-lookup"><span data-stu-id="f4355-121">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2013 Edge pool.</span></span>
    
    <span data-ttu-id="f4355-122">![[定義新的 Edge 集區] 對話方塊，下一個躍點集區清單](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "[定義新的 Edge 集區] 對話方塊，下一個躍點集區清單")</span><span class="sxs-lookup"><span data-stu-id="f4355-122">![Define New Edge Pool dialog, Next hop pool list](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Define New Edge Pool dialog, Next hop pool list")</span></span>

7.  <span data-ttu-id="f4355-123">在 [**關聯前端池**] 頁面上，請勿在此時將池與此 Edge 池建立關聯。</span><span class="sxs-lookup"><span data-stu-id="f4355-123">On the **Associate Front End pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="f4355-124">外部媒體流量目前是透過舊版 Office 通訊伺服器 2007 R2 Edge 伺服器路由。</span><span class="sxs-lookup"><span data-stu-id="f4355-124">External media traffic is currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="f4355-125">此設定將會在稍後的遷移階段進行設定。</span><span class="sxs-lookup"><span data-stu-id="f4355-125">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="f4355-126">![[定義新的 Edge 集區] 對話方塊](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "[定義新的 Edge 集區] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="f4355-126">![Define New Edge Pool dialog](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Define New Edge Pool dialog")</span></span>

8.  <span data-ttu-id="f4355-127">按一下 **[完成]** ，然後**發佈**拓撲。</span><span class="sxs-lookup"><span data-stu-id="f4355-127">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="f4355-128">請依照部署檔中的[Lync Server 2013 安裝邊緣](lync-server-2013-install-edge-servers.md)伺服器中的步驟進行，以在新的 Edge 伺服器上安裝檔案、設定憑證，然後啟動服務。</span><span class="sxs-lookup"><span data-stu-id="f4355-128">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="f4355-129">在部署檔中，請遵循在[Lync Server 2013 中部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)主題中的準則，這一點非常重要。</span><span class="sxs-lookup"><span data-stu-id="f4355-129">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="f4355-130">本節僅提供安裝這些伺服器角色時設定設定的一些指導方針。</span><span class="sxs-lookup"><span data-stu-id="f4355-130">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="f4355-131">您現在應該擁有舊版 Office 通訊伺服器 2007 R2 Edge 伺服器部署，並以與 Lync Server 2013 Edge 伺服器部署並行的方式來指示 BackCompatSite。</span><span class="sxs-lookup"><span data-stu-id="f4355-131">You should now have a legacy Office Communications Server 2007 R2 Edge server deployment, indicated by the presence of the BackCompatSite, in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="f4355-132">同盟已設定為使用 Office 通訊伺服器 2007 R2 控制器。</span><span class="sxs-lookup"><span data-stu-id="f4355-132">Federation is configured to use the Office Communications Server 2007 R2 Director.</span></span> <span data-ttu-id="f4355-133">確認這兩個部署都能正常運作、服務已啟動，而且您可以在移至下一個階段之前管理每個部署。</span><span class="sxs-lookup"><span data-stu-id="f4355-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

<span data-ttu-id="f4355-134">![顯示 OCS Edge Server 的拓撲產生器](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "顯示 OCS Edge Server 的拓撲產生器")</span><span class="sxs-lookup"><span data-stu-id="f4355-134">![Topology Builder showing OCS Edge Server](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topology Builder showing OCS Edge Server")</span></span>

</div>

<span> </span>

</div>

</div>

</div>


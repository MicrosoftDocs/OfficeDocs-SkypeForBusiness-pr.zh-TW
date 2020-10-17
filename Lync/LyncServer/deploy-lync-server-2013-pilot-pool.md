---
title: 部署 Lync Server 2013 試驗集區
description: 部署 Lync Server 2013 試驗集區。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a599cee1719f773ebbf3cf5a71405aa9b7259261
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550789"
---
# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="b93a9-103">部署 Lync Server 2013 試驗集區</span><span class="sxs-lookup"><span data-stu-id="b93a9-103">Deploy Lync Server 2013 pilot pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b93a9-104">_**主題上次修改日期：** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="b93a9-104">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="b93a9-105">遷移至 Lync Server 2013 所需的第一步是部署試驗集區。</span><span class="sxs-lookup"><span data-stu-id="b93a9-105">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="b93a9-106">試驗集區是您用 Lync Server 2010 部署來測試 Lync Server 2013 共存的位置。</span><span class="sxs-lookup"><span data-stu-id="b93a9-106">The pilot pool is where you test coexistence of Lync Server 2013 with your Lync Server 2010 deployment.</span></span> <span data-ttu-id="b93a9-107">共存是一種暫時的狀態，會持續進行，直到您將所有使用者和集區移至 Lync Server 2013 為止。</span><span class="sxs-lookup"><span data-stu-id="b93a9-107">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="b93a9-108">當您部署試驗集區時，會用到 [定義新前端集區精靈]。</span><span class="sxs-lookup"><span data-stu-id="b93a9-108">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="b93a9-109">您應該在 lync server 2010 集區中的 Lync Server 2013 試驗集區中部署相同的功能和工作負載。</span><span class="sxs-lookup"><span data-stu-id="b93a9-109">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Lync Server 2010 pool.</span></span> <span data-ttu-id="b93a9-110">如果您已部署封存伺服器、監控伺服器或 System Center Operations Manager 以封存或監控 Lync Server 2010 環境，且您想要在整個遷移期間繼續封存或監控，您也必須在試驗環境中部署這些功能。</span><span class="sxs-lookup"><span data-stu-id="b93a9-110">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Lync Server 2010 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="b93a9-111">您部署以封存或監視 Lync Server 2010 環境的版本，將不會在 Lync Server 2013 環境中捕獲資料。</span><span class="sxs-lookup"><span data-stu-id="b93a9-111">The version you deployed to archive or monitor your Lync Server 2010 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b93a9-112">下列程序討論在整個試驗集區部署程序中，應考量的功能和設定。</span><span class="sxs-lookup"><span data-stu-id="b93a9-112">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="b93a9-113">本節只著重在部署試驗集區時應該考量的要點。</span><span class="sxs-lookup"><span data-stu-id="b93a9-113">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="b93a9-114">如需詳細步驟，請參閱 <A href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</A> 部署指南。</span><span class="sxs-lookup"><span data-stu-id="b93a9-114">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="b93a9-115">**部署 Lync Server 2013 試驗集區**</span><span class="sxs-lookup"><span data-stu-id="b93a9-115">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="b93a9-116">以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。</span><span class="sxs-lookup"><span data-stu-id="b93a9-116">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="b93a9-117">展開樹狀目錄，直到您進入 **Lync Server 2013** **Enterprise Edition 前端**集區。</span><span class="sxs-lookup"><span data-stu-id="b93a9-117">Expand the tree until you reach **Lync Server 2013** **Enterprise Edition Front End pools**.</span></span>

3.  <span data-ttu-id="b93a9-118">以滑鼠右鍵按一下 [ **Enterprise Edition 前端**集區]，然後選取 [ **新增前端集**區]。</span><span class="sxs-lookup"><span data-stu-id="b93a9-118">Right click **Enterprise Edition Front End pools**, and select **New Front End Pool**.</span></span>
    
    <span data-ttu-id="b93a9-119">![拓撲產生器伺服器集區選取子功能表](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "拓撲產生器伺服器集區選取子功能表")</span><span class="sxs-lookup"><span data-stu-id="b93a9-119">![Topology Builder Server pool selection submenu](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Topology Builder Server pool selection submenu")</span></span>

4.  <span data-ttu-id="b93a9-120">輸入集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b93a9-120">Enter the pool FQDN.</span></span> <span data-ttu-id="b93a9-121">當您定義試驗集區時，您可以選擇部署 Enterprise Edition 前端集區或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="b93a9-121">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="b93a9-122">Lync Server 2013 不需要您的試驗集區功能符合您舊版集區中部署的功能。</span><span class="sxs-lookup"><span data-stu-id="b93a9-122">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="b93a9-123">您為試驗集區所定義的集區或伺服器完整網域名稱 (FQDN) 不得重複。</span><span class="sxs-lookup"><span data-stu-id="b93a9-123">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="b93a9-124">它不符合目前部署的 Lync Server 2010 集區或任何其他目前部署的伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="b93a9-124">It cannot match the name of the currently deployed Lync Server 2010 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="b93a9-125">![[定義新前端集區] [FQDN] 頁面](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "[定義新前端集區] [FQDN] 頁面")</span><span class="sxs-lookup"><span data-stu-id="b93a9-125">![Define New Front End Pool Wizard FQDN page](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Define New Front End Pool Wizard FQDN page")</span></span>

5.  <span data-ttu-id="b93a9-126">在「選取功能」\*\*\*\* 頁面上，選取您希望此前端集區擁有的功能之對應核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b93a9-126">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="b93a9-127">例如，如果您只部署立即訊息 (IM) 和目前狀態功能，則可以選取 [會議] 核取方塊以允許多方 IM，但是不要選取 [電話撥入式 (PSTN) 會議]、[企業語音] 或 [通話許可控制] 核取方塊，因為這些功能代表語音、視訊和共同作業會議功能。</span><span class="sxs-lookup"><span data-stu-id="b93a9-127">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="b93a9-128">如需選取功能的其他資訊，請參閱部署檔中的在 [Lync server 2013 中定義及設定前端集區或 Standard Edition server](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="b93a9-128">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="b93a9-129">![前端集區選取功能頁面](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "前端集區選取功能頁面")</span><span class="sxs-lookup"><span data-stu-id="b93a9-129">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

6.  <span data-ttu-id="b93a9-130">在 [ **選取組合伺服器角色** ] 頁面上，建議您在 Lync server 2013 中組合轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="b93a9-130">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="b93a9-131">當您將舊版拓撲與 Lync Server 2013 合併時，我們必須先組合 Lync Server 2010 轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="b93a9-131">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Lync Server 2010 Mediation Server.</span></span> <span data-ttu-id="b93a9-132">在合併拓撲並設定 Lync Server 2013 轉送伺服器之後，您可以決定是否要保留組合轉送伺服器，或在將轉送伺服器角色移2013至獨立伺服器時，將其變更為獨立伺服器。</span><span class="sxs-lookup"><span data-stu-id="b93a9-132">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="b93a9-133">![前端集區選取 [組合伺服器角色] 頁面](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "前端集區選取 [組合伺服器角色] 頁面")</span><span class="sxs-lookup"><span data-stu-id="b93a9-133">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

7.  <span data-ttu-id="b93a9-p108">在「建立伺服器角色與此前端集區的關聯」\*\*\*\* 頁面上，於試驗集區部署期間，請勿選擇 [啟用要由此前端集區的媒體元件使用的 Edge 集區]\*\*\*\* 選項。此為您會在移轉後期階段時才啟用及上線的功能。目前請將此設定保留清空。</span><span class="sxs-lookup"><span data-stu-id="b93a9-p108">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option. This is a feature you will enable and bring online in a later phase of migration. Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="b93a9-137">![[建立伺服器角色與前端集區的關聯] 頁面](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "[建立伺服器角色與前端集區的關聯] 頁面")</span><span class="sxs-lookup"><span data-stu-id="b93a9-137">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

8.  <span data-ttu-id="b93a9-138">在「選取 Office Web Apps Server」\*\*\*\* 頁面上，按一下 [新增]\*\*\*\*，並指定應用程式伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b93a9-138">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="b93a9-139">![定義新的 Office Web Apps Server FQDN 屬性](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "定義新的 Office Web Apps Server FQDN 屬性")</span><span class="sxs-lookup"><span data-stu-id="b93a9-139">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

9.  <span data-ttu-id="b93a9-140">在 [ **定義封存 SQL Server 存放區** ] 頁面上，定義 lync server 封存與監控的 sql server 儲存區時，請選取先前針對 lync server 2013 建立的 sql server 實例。</span><span class="sxs-lookup"><span data-stu-id="b93a9-140">On the **Define the Archiving SQL Server store** page, when defining the SQL Server store for both Lync Server Archiving and Monitoring, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="b93a9-141">![定義封存 SQL Server 儲存區頁面](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "定義封存 SQL Server 儲存區頁面")</span><span class="sxs-lookup"><span data-stu-id="b93a9-141">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

10. <span data-ttu-id="b93a9-142">若要發行您的拓撲，請以滑鼠右鍵按一下 [ **Lync Server** ] 節點，然後按一下 [ **發行拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="b93a9-142">To publish your topology, right-click the **Lync Server** node, and then click **Publish Topology**.</span></span>
    
    <span data-ttu-id="b93a9-143">![顯示已設定拓撲的拓撲產生器](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "顯示已設定拓撲的拓撲產生器")</span><span class="sxs-lookup"><span data-stu-id="b93a9-143">![Topology Builder displaying a configured topology](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Topology Builder displaying a configured topology")</span></span>

11. <span data-ttu-id="b93a9-144">當發行程序完成時，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="b93a9-144">When the publish process has completed, click **Finish**.</span></span>

<span data-ttu-id="b93a9-145">若要安裝設定存放區的本機複本並啟動必要的服務，請參閱部署檔中的 [設定前端伺服器和前端集區的 Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) 。</span><span class="sxs-lookup"><span data-stu-id="b93a9-145">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>


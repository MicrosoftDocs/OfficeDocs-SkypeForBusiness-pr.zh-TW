---
title: 部署 Lync Server 2013 試驗集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af8c2f5ed78bb228c4e650da983a1c82456c47b4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180496"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="fc57b-102">部署 Lync Server 2013 試驗集區</span><span class="sxs-lookup"><span data-stu-id="fc57b-102">Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc57b-103">_**主題上次修改日期：** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="fc57b-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="fc57b-104">遷移至 Lync Server 2013 所需的第一步是部署試驗集區。</span><span class="sxs-lookup"><span data-stu-id="fc57b-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="fc57b-105">試驗集區是您用 Office 通訊伺服器 2007 R2 部署來測試 Lync Server 2013 共存的位置。</span><span class="sxs-lookup"><span data-stu-id="fc57b-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="fc57b-106">共存是一種暫時的狀態，會持續進行，直到您將所有使用者和集區移至 Lync Server 2013 為止。</span><span class="sxs-lookup"><span data-stu-id="fc57b-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="fc57b-107">當您部署試驗集區時，會用到 [定義新前端集區精靈]。</span><span class="sxs-lookup"><span data-stu-id="fc57b-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="fc57b-108">您應該在您的 Office 通訊伺服器 2007 R2 集區中，部署 Lync Server 2013 試驗集區中的相同功能和工作負載。</span><span class="sxs-lookup"><span data-stu-id="fc57b-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="fc57b-109">如果您已部署封存伺服器、監控伺服器或 System Center Operations Manager 以封存或監控您的 Office 通訊伺服器 2007 R2 環境，而且您想要在整個遷移期間繼續封存或監控，您也必須在試驗環境中部署這些功能。</span><span class="sxs-lookup"><span data-stu-id="fc57b-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Office Communications Server 2007 R2 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="fc57b-110">您部署的版本若要封存或監視您的 Office 通訊伺服器 2007 R2 環境，將不會在 Lync Server 2013 環境中捕獲資料。</span><span class="sxs-lookup"><span data-stu-id="fc57b-110">The version you deployed to archive or monitor your Office Communications Server 2007 R2 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fc57b-111">下列程序討論在整個試驗集區部署程序中，應考量的功能和設定。</span><span class="sxs-lookup"><span data-stu-id="fc57b-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="fc57b-112">本節只著重在部署試驗集區時應該考量的要點。</span><span class="sxs-lookup"><span data-stu-id="fc57b-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="fc57b-113">如需詳細步驟，請參閱<A href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</A>部署指南。</span><span class="sxs-lookup"><span data-stu-id="fc57b-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="fc57b-114">**部署 Lync Server 2013 試驗集區**</span><span class="sxs-lookup"><span data-stu-id="fc57b-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="fc57b-115">以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。</span><span class="sxs-lookup"><span data-stu-id="fc57b-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="fc57b-116">開啟拓撲產生器，並選擇建立新拓撲。</span><span class="sxs-lookup"><span data-stu-id="fc57b-116">Open Topology Builder and choose to create a new topology.</span></span>

3.  <span data-ttu-id="fc57b-117">輸入主要 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="fc57b-117">Enter the primary SIP domain.</span></span>
    
    <span data-ttu-id="fc57b-118">![建立新的拓撲，定義主域頁面](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "建立新的拓撲，定義主域頁面")</span><span class="sxs-lookup"><span data-stu-id="fc57b-118">![Create New Topology, Define primary domain page](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Create New Topology, Define primary domain page")</span></span>

4.  <span data-ttu-id="fc57b-119">繼續完成精靈直到您達到 [定義新前端集區精靈]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fc57b-119">Continue completing the wizard until you reach the **Define the New Front End pool** wizard.</span></span> <span data-ttu-id="fc57b-120">按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="fc57b-120">Click Next.</span></span>

5.  <span data-ttu-id="fc57b-121">輸入集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fc57b-121">Enter the pool FQDN.</span></span> <span data-ttu-id="fc57b-122">當您定義試驗集區時，您可以選擇部署 Enterprise Edition 前端集區或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="fc57b-122">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="fc57b-123">Lync Server 2013 不需要您的試驗集區功能符合您舊版集區中部署的功能。</span><span class="sxs-lookup"><span data-stu-id="fc57b-123">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="fc57b-124">您為試驗集區所定義的集區或伺服器完整網域名稱 (FQDN) 不得重複。</span><span class="sxs-lookup"><span data-stu-id="fc57b-124">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="fc57b-125">它不符合目前部署的 Office 通訊伺服器 2007 R2 集區或任何其他目前已部署的伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="fc57b-125">It cannot match the name of the currently deployed Office Communications Server 2007 R2 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="fc57b-126">![[定義前端集區 FQDN] 頁面](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "[定義前端集區 FQDN] 頁面")</span><span class="sxs-lookup"><span data-stu-id="fc57b-126">![Define the Front End pool FQDN page](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Define the Front End pool FQDN page")</span></span>

6.  <span data-ttu-id="fc57b-127">定義將要新增至集區的電腦。</span><span class="sxs-lookup"><span data-stu-id="fc57b-127">Define the computer that will be added to the pool.</span></span>
    
    <span data-ttu-id="fc57b-128">![[定義新前端集區] 對話方塊](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "[定義新前端集區] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="fc57b-128">![Define New Front End Pool dialog](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Define New Front End Pool dialog")</span></span>

7.  <span data-ttu-id="fc57b-129">在「選取功能」\*\*\*\* 頁面上，選取您希望此前端集區擁有的功能之對應核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fc57b-129">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="fc57b-130">例如，如果您只部署立即訊息 (IM) 和目前狀態功能，則可以選取 [會議] 核取方塊以允許多方 IM，但是不要選取 [電話撥入式 (PSTN) 會議]、[企業語音] 或 [通話許可控制] 核取方塊，因為這些功能代表語音、視訊和共同作業會議功能。</span><span class="sxs-lookup"><span data-stu-id="fc57b-130">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="fc57b-131">如需選取功能的其他資訊，請參閱部署檔中的在[Lync server 2013 中定義及設定前端集區或 Standard Edition server](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="fc57b-131">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="fc57b-132">![前端集區選取功能頁面](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "前端集區選取功能頁面")</span><span class="sxs-lookup"><span data-stu-id="fc57b-132">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

8.  <span data-ttu-id="fc57b-133">在 [**選取組合伺服器角色**] 頁面上，建議您在 Lync server 2013 中組合轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="fc57b-133">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="fc57b-134">當您將舊版拓撲與 Lync Server 2013 合併時，我們必須先組合 Office 通訊伺服器 2007 R2 轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="fc57b-134">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Office Communications Server 2007 R2 Mediation Server.</span></span> <span data-ttu-id="fc57b-135">在合併拓撲並設定 Lync Server 2013 轉送伺服器之後，您可以決定是否要保留組合轉送伺服器，或在將轉送伺服器角色移2013至獨立伺服器時，將其變更為獨立伺服器。</span><span class="sxs-lookup"><span data-stu-id="fc57b-135">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="fc57b-136">![前端集區選取 [組合伺服器角色] 頁面](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "前端集區選取 [組合伺服器角色] 頁面")</span><span class="sxs-lookup"><span data-stu-id="fc57b-136">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

9.  <span data-ttu-id="fc57b-p109">在「建立伺服器角色與此前端集區的關聯」\*\*\*\* 頁面上，於試驗集區部署期間，請勿選擇 [啟用要由此前端集區的媒體元件使用的 Edge 集區]\*\*\*\* 選項。此為您會在移轉後期階段時才啟用及上線的功能。目前請將此設定保留清空。</span><span class="sxs-lookup"><span data-stu-id="fc57b-p109">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option. This is a feature you will enable and bring online in a later phase of migration. Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="fc57b-140">![[建立伺服器角色與前端集區的關聯] 頁面](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "[建立伺服器角色與前端集區的關聯] 頁面")</span><span class="sxs-lookup"><span data-stu-id="fc57b-140">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

10. <span data-ttu-id="fc57b-141">在「選取 Office Web Apps Server」\*\*\*\* 頁面上，按一下 [新增]\*\*\*\*，並指定應用程式伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fc57b-141">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="fc57b-142">![定義新的 Office Web Apps Server FQDN 屬性](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "定義新的 Office Web Apps Server FQDN 屬性")</span><span class="sxs-lookup"><span data-stu-id="fc57b-142">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

11. <span data-ttu-id="fc57b-143">在 [**定義封存 SQL Server 存放區**] 頁面上，選取先前針對 Lync Server 2013 建立的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="fc57b-143">On the **Define the Archiving SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="fc57b-144">![定義封存 SQL Server 儲存區頁面](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "定義封存 SQL Server 儲存區頁面")</span><span class="sxs-lookup"><span data-stu-id="fc57b-144">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

12. <span data-ttu-id="fc57b-145">在 [**定義監控 SQL Server 存放區**] 頁面上，選取先前針對 Lync Server 2013 建立的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="fc57b-145">On the **Define the Monitoring SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span> <span data-ttu-id="fc57b-146">按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fc57b-146">Click **Finish**.</span></span>

13. <span data-ttu-id="fc57b-147">從拓撲產生器最上面的節點，用滑鼠右鍵按一下 [Lync Server]\*\*\*\*，再按一下 [編輯內容]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fc57b-147">From the top node of Topology Builder, right click **Lync Server** and click **Edit Properties.**</span></span> <span data-ttu-id="fc57b-148">按一下 [簡單 URL]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fc57b-148">Click **Simple URLs**.</span></span>

14. <span data-ttu-id="fc57b-149">更新 [系統管理存取 URL]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fc57b-149">Update the **Administrative access URL**.</span></span>
    
    <span data-ttu-id="fc57b-150">![編輯屬性、簡單 URLs 頁面](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "編輯屬性、簡單 URLs 頁面")</span><span class="sxs-lookup"><span data-stu-id="fc57b-150">![Edit Properties, Simple URLs page](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Edit Properties, Simple URLs page")</span></span>
    
    <span data-ttu-id="fc57b-151">如需簡單 URLs 的其他資訊，請參閱部署檔中的主題[編輯或設定簡單 URLs Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) 。</span><span class="sxs-lookup"><span data-stu-id="fc57b-151">For additional information on Simple URLs, see the topic [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

15. <span data-ttu-id="fc57b-152">從 [編輯內容]\*\*\*\* 中，按一下 [中央管理伺服器]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fc57b-152">From the **Edit Properties**, click **Central Management Server**.</span></span>

16. <span data-ttu-id="fc57b-153">從下拉式清單中，選取 [Lync Server 2013 集區]。</span><span class="sxs-lookup"><span data-stu-id="fc57b-153">From the drop-down list, select the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="fc57b-154">![編輯屬性、中央管理伺服器頁面](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "編輯屬性、中央管理伺服器頁面")</span><span class="sxs-lookup"><span data-stu-id="fc57b-154">![Edit Properties, Central Management Server page](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Edit Properties, Central Management Server page")</span></span>

17. <span data-ttu-id="fc57b-155">按一下 [確定]，以關閉「編輯內容」\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="fc57b-155">Click OK to close **the Edit Properties** page.</span></span>

18. <span data-ttu-id="fc57b-156">從 [動作]\*\*\*\* 功能表中，選取 [發行拓撲]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fc57b-156">From the **Action** menu, select **Publish Topology**.</span></span>

19. <span data-ttu-id="fc57b-157">當發行程序完成時，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fc57b-157">When the publish process has completed, click **Finish**.</span></span>

20. <span data-ttu-id="fc57b-158">返回至 [Lync Server 2013 部署嚮導]，按一下 [**安裝或更新 Lync Server 系統**]。</span><span class="sxs-lookup"><span data-stu-id="fc57b-158">Returning to the Lync Server 2013 Deployment Wizard, click **Install or Update Lync Server System**.</span></span>
    
    <span data-ttu-id="fc57b-159">![Lync Server 2013 部署嚮導](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 部署嚮導")</span><span class="sxs-lookup"><span data-stu-id="fc57b-159">![Lync Server 2013 Deployment Wizard](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 Deployment Wizard")</span></span>

<span data-ttu-id="fc57b-160">若要安裝設定存放區的本機複本並啟動必要的服務，請參閱部署檔中的[設定前端伺服器和前端集區的 Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) 。</span><span class="sxs-lookup"><span data-stu-id="fc57b-160">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>


---
title: 部署試生產池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 遷移到商務用 Skype Server 2019 所需的第一個步驟就是部署試驗池。 試驗池是您使用舊版部署來測試商務用 Skype Server 2019 的共存位置。 [共存] 是一個暫時的狀態, 一直持續到您將所有使用者和池移至商務用 Skype Server 2019 為止。
ms.openlocfilehash: dc0e5b984aaa9ed931f3937b253fbe40aef9b051
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238856"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a><span data-ttu-id="ae17f-105">部署商務用 Skype Server 2019 試用版池</span><span class="sxs-lookup"><span data-stu-id="ae17f-105">Deploy Skype for Business Server 2019 pilot pool</span></span>

<span data-ttu-id="ae17f-106">遷移到商務用 Skype Server 2019 所需的第一個步驟就是部署試驗池。</span><span class="sxs-lookup"><span data-stu-id="ae17f-106">One of the first steps required for migration to Skype for Business Server 2019 is to deploy a pilot pool.</span></span> <span data-ttu-id="ae17f-107">試驗池是您使用舊版部署來測試商務用 Skype Server 2019 的共存位置。</span><span class="sxs-lookup"><span data-stu-id="ae17f-107">The pilot pool is where you test coexistence of Skype for Business Server 2019 with your legacy deployment.</span></span> <span data-ttu-id="ae17f-108">[共存] 是一個暫時的狀態, 一直持續到您將所有使用者和池移至商務用 Skype Server 2019 為止。</span><span class="sxs-lookup"><span data-stu-id="ae17f-108">Coexistence is a temporary state that lasts until you have moved all users and pools to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="ae17f-109">當您部署試生產池時, 請使用 [定義新的前端池] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="ae17f-109">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="ae17f-110">您應該在您的 [商務用 Skype Server 2019 試驗] 池中部署與舊版池中相同的功能和工作負荷。</span><span class="sxs-lookup"><span data-stu-id="ae17f-110">You should deploy the same features and workloads in your Skype for Business Server 2019 pilot pool that you have in your legacy pool.</span></span> <span data-ttu-id="ae17f-111">如果您已部署封存伺服器、監視伺服器或 System Center Operations Manager 以進行封存或監視舊版環境, 而您想要在整個遷移期間繼續進行封存或監視, 您也必須在您的電腦中部署這些功能。試驗環境。</span><span class="sxs-lookup"><span data-stu-id="ae17f-111">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your legacy environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="ae17f-112">您部署以封存或監視舊版環境的版本, 將無法在商務用 Skype Server 2019 環境中捕獲資料。</span><span class="sxs-lookup"><span data-stu-id="ae17f-112">The version you deployed to archive or monitor your legacy environment will not capture data in your Skype for Business Server 2019 environment.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ae17f-113">下列程式討論您在整個試驗池部署程式中應考慮的功能和設定。</span><span class="sxs-lookup"><span data-stu-id="ae17f-113">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="ae17f-114">此區段只會醒目提示您要考慮的重要重點, 做為您的試驗池部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="ae17f-114">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a><span data-ttu-id="ae17f-115">若要部署商務用 Skype Server 2019 試生產池</span><span class="sxs-lookup"><span data-stu-id="ae17f-115">To deploy a Skype for Business Server 2019 pilot pool</span></span>

1. <span data-ttu-id="ae17f-116">登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。</span><span class="sxs-lookup"><span data-stu-id="ae17f-116">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="ae17f-117">展開樹狀結構, 直到您到達**商務用 Skype Server 2019** > **企業版前端池**為止。</span><span class="sxs-lookup"><span data-stu-id="ae17f-117">Expand the tree until you reach **Skype for Business Server 2019** > **Enterprise Edition Front End pools**.</span></span>
    
3. <span data-ttu-id="ae17f-118">以滑鼠右鍵按一下 [**企業版前端池**], 然後選取 [**新增前端端池**]。</span><span class="sxs-lookup"><span data-stu-id="ae17f-118">Right-click **Enterprise Edition Front End pools** and select **New Front End Pool**.</span></span>
  
4. <span data-ttu-id="ae17f-119">輸入 [池] 完全合格的功能變數名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="ae17f-119">Enter the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="ae17f-120">當您定義您的試驗池時, 您可以選擇部署企業版的前端池或標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="ae17f-120">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="ae17f-121">商務用 Skype Server 2019 不需要您的試點專案區功能與舊版池中部署的功能相符。</span><span class="sxs-lookup"><span data-stu-id="ae17f-121">Skype for Business Server 2019 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="ae17f-122">您為試驗池定義的池或伺服器 FQDN 必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ae17f-122">The pool or server FQDN that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="ae17f-123">它無法與目前部署的舊版池或任何其他伺服器的名稱相符。</span><span class="sxs-lookup"><span data-stu-id="ae17f-123">It cannot match the name of the currently deployed legacy pool or any other servers currently deployed.</span></span> 
  
5. <span data-ttu-id="ae17f-124">在 [**選取功能**] 頁面上, 選取您要用於此前端池之功能的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ae17f-124">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="ae17f-125">例如, 如果您只部署立即訊息 (IM) 和目前狀態功能, 您可以選取 [會議] 核取方塊以允許多方 IM, 但不會選取撥入 (PSTN) 會議、企業語音或通話許可控制檢查方塊, 因為它們代表語音、影片和共同作業會議功能。</span><span class="sxs-lookup"><span data-stu-id="ae17f-125">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but you would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. <span data-ttu-id="ae17f-126">我們建議您在 [**選取 collocated 伺服器角色**] 頁面上, 選擇要在商務用 Skype server 2019 中 Collocate 轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="ae17f-126">On the **Select collocated server roles** page, we recommend that you choose to collocate the Mediation Server in Skype for Business Server 2019.</span></span> <span data-ttu-id="ae17f-127">在與商務用 Skype Server 2019 合併舊版拓撲時, 我們必須先 collocate 舊版的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="ae17f-127">When merging a legacy topology with Skype for Business Server 2019, we require that you first collocate the legacy Mediation Server.</span></span> <span data-ttu-id="ae17f-128">在合併拓朴並設定商務用 Skype Server 2019 轉送伺服器之後, 您可以決定是否要保留 collocated 轉送伺服器, 或在您將轉送伺服器角色移至商務用 Skype Server 時, 將它變更為獨立伺服器在後期部署程式中的2019。</span><span class="sxs-lookup"><span data-stu-id="ae17f-128">After merging the topologies and configuring the Skype for Business Server 2019 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Skype for Business Server 2019 later in the deployment process.</span></span> 
   
7. <span data-ttu-id="ae17f-129">在 [**將伺服器角色與此前端池建立關聯**] 頁面上的 [試驗池] 部署期間,*請*不要選擇 [**啟用此前端池的媒體元件要使用 Edge 池**] 選項。</span><span class="sxs-lookup"><span data-stu-id="ae17f-129">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, *do not* choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="ae17f-130">這是您將在稍後的遷移階段啟用並加入線上的功能。</span><span class="sxs-lookup"><span data-stu-id="ae17f-130">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="ae17f-131">暫時清除此設定。</span><span class="sxs-lookup"><span data-stu-id="ae17f-131">Keep this setting cleared for now.</span></span> 
  
8. <span data-ttu-id="ae17f-132">在 [**選取 Office Web Apps 伺服器**] 頁面上, 按一下 [**新增**], 然後指定應用程式伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ae17f-132">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
  
9. <span data-ttu-id="ae17f-133">在 [**定義封存 SQL Server store** ] 頁面上, 為 [商務用 skype server 封存與監視] 定義 sql server store 時, 請選取先前針對商務用 skype server 2019 建立的 sql server 實例。</span><span class="sxs-lookup"><span data-stu-id="ae17f-133">On the **Define the Archiving SQL Server store** page, when defining the SQL Server store for both Skype for Business Server Archiving and Monitoring, select the SQL Server instance created earlier for Skype for Business Server 2019.</span></span> 
  
10. <span data-ttu-id="ae17f-134">若要發佈拓撲, 請以滑鼠右鍵按一下**商務用 Skype Server**節點, 然後按一下 [**發佈拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="ae17f-134">To publish your topology, right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
  
11. <span data-ttu-id="ae17f-135">發佈程式完成後, 請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="ae17f-135">When the publish process has completed, click **Finish**.</span></span>

12. <span data-ttu-id="ae17f-136">在移至下一個名為「驗證試點伺服器與舊版池共存」的區段之前, 您需要安裝我們剛剛在已發佈拓撲中定義的商務用 Skype Server 新的 [前端試驗] 池, 請依照這裡所述的程式[安裝 skype。拓撲結構中伺服器上的商務伺服器](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="ae17f-136">Before moving to the next section called "Verify pilot pool coexistence with legacy pool" you need to install the Skype for Business Server new Front End pilot pool we just defined in the published topology, follow the procedures outlined here [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>

13. <span data-ttu-id="ae17f-137">完成上一個步驟之後, 請移至下一節, 以驗證與舊版池共存的試驗池。</span><span class="sxs-lookup"><span data-stu-id="ae17f-137">Once previous step is complete, move to the next section to Verify pilot pool coexistence with legacy pool.</span></span>
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  


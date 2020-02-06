---
title: 在商務用 Skype Server 中安裝系統管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 摘要：瞭解如何安裝商務用 Skype Server 安裝所需的管理工具。 從 Microsoft 評估中心下載免費試用版商務用 Skype Server，網址為： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。
ms.openlocfilehash: 3abf2eb35a4593f25db75e175f3cd30fdf49e21b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790171"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="4ac06-104">在商務用 Skype Server 中安裝系統管理工具</span><span class="sxs-lookup"><span data-stu-id="4ac06-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="4ac06-105">**摘要：** 瞭解如何安裝商務用 Skype Server 安裝所需的管理工具。</span><span class="sxs-lookup"><span data-stu-id="4ac06-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="4ac06-106">從 Microsoft 評估中心下載免費試用版商務用 Skype Server，網址為： [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="4ac06-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="4ac06-107">[管理工具] 包括 [拓撲建立器] 和 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="4ac06-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="4ac06-108">系統管理工具必須安裝在拓撲中的至少一個伺服器，或是執行商務用 Skype Server 支援的 Windows OS 版本的64位管理工作站。</span><span class="sxs-lookup"><span data-stu-id="4ac06-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="4ac06-109">您可以依照任何循序執行步驟1到5。</span><span class="sxs-lookup"><span data-stu-id="4ac06-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="4ac06-110">不過，您必須在順序中執行步驟6、7和8，並在步驟1到5之後，如圖表中所述。</span><span class="sxs-lookup"><span data-stu-id="4ac06-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="4ac06-111">安裝 [管理工具] 是8的步驟3。</span><span class="sxs-lookup"><span data-stu-id="4ac06-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![概覽圖表](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="4ac06-113">安裝商務用 Skype Server 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="4ac06-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="4ac06-114">商務用 Skype Server 的安裝媒體提供彈性的體驗。</span><span class="sxs-lookup"><span data-stu-id="4ac06-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="4ac06-115">當您第一次執行 setup.exe 時，只會安裝 [商務用 Skype Server 部署] 嚮導和商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="4ac06-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="4ac06-116">使用這兩個工具（稱為核心元件），您可以繼續安裝程式，但不會提供整個商務用 Skype 伺服器環境的主要功能。</span><span class="sxs-lookup"><span data-stu-id="4ac06-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="4ac06-117">安裝核心元件之後，就會自動啟動 [部署] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="4ac06-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="4ac06-118">標題為 [**安裝管理工具**] 的 [部署嚮導] 區段會安裝商務用 Skype server 拓撲產生器和商務用 Skype server 控制台。</span><span class="sxs-lookup"><span data-stu-id="4ac06-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4ac06-119">每個商務用 Skype Server 環境都必須至少有一個伺服器安裝了 [管理工具]。</span><span class="sxs-lookup"><span data-stu-id="4ac06-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="4ac06-120">觀看**安裝管理工具**的影片步驟：</span><span class="sxs-lookup"><span data-stu-id="4ac06-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="4ac06-121">從 [部署] 嚮導安裝商務用 Skype Server 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="4ac06-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="4ac06-122">插入商務用 Skype Server 安裝媒體。</span><span class="sxs-lookup"><span data-stu-id="4ac06-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="4ac06-123">如果安裝程式沒有自動開始，請按兩下 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="4ac06-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="4ac06-124">安裝媒體需要 Microsoft Visual c + + 才能執行。</span><span class="sxs-lookup"><span data-stu-id="4ac06-124">The installation media requires Microsoft Visual C++ to run.</span></span> <span data-ttu-id="4ac06-125">隨即會彈出一個對話方塊，詢問您是否要安裝它。</span><span class="sxs-lookup"><span data-stu-id="4ac06-125">A dialog box will pop up asking if you want to install it.</span></span> <span data-ttu-id="4ac06-126">按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="4ac06-126">Click **Yes**.</span></span>
    
3. <span data-ttu-id="4ac06-127">您可以使用 [智慧設定] （在商務用 Skype Server 中的新功能）來連線至網際網路，在安裝程式中檢查更新。</span><span class="sxs-lookup"><span data-stu-id="4ac06-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="4ac06-128">如此一來，您就可以在安裝時，確認您的產品有最新的更新，從而提供更佳的體驗。</span><span class="sxs-lookup"><span data-stu-id="4ac06-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="4ac06-129">按一下 [**安裝**] 以開始安裝。</span><span class="sxs-lookup"><span data-stu-id="4ac06-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="4ac06-130">仔細閱讀授權協定，如果您同意，請選取 [**我接受授權合約中的條款**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="4ac06-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="4ac06-131">商務用 Skype Server 核心元件將會安裝在伺服器上。</span><span class="sxs-lookup"><span data-stu-id="4ac06-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="4ac06-132">核心元件包括下列各項，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="4ac06-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![[應用程式] 畫面中的核心元件。](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="4ac06-134">**商務用 Skype Server 部署嚮導**提供啟動 pad 以安裝商務用 Skype Server 各種元件的部署程式。</span><span class="sxs-lookup"><span data-stu-id="4ac06-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="4ac06-135">**商務用 Skype Server Management 命令**介面可供您管理商務用 Skype Server 的預先設定 PowerShell 程式。</span><span class="sxs-lookup"><span data-stu-id="4ac06-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="4ac06-136">核心元件的安裝完成後，商務用 Skype Server 部署嚮導就會自動啟動，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="4ac06-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![商務用 Skype Server 部署嚮導](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="4ac06-138">除了核心元件之外，您也需要在環境中至少有一台伺服器上安裝商務用 Skype Server 拓撲建立器和商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="4ac06-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="4ac06-139">按一下 [部署嚮導] 上的 [**安裝管理工具**]。</span><span class="sxs-lookup"><span data-stu-id="4ac06-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="4ac06-140">按一下 **[下一步]** 以開始安裝。</span><span class="sxs-lookup"><span data-stu-id="4ac06-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="4ac06-141">安裝完成後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="4ac06-141">Once the installation has completed, click **Finish**.</span></span> <span data-ttu-id="4ac06-142">管理工具現已新增至伺服器，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="4ac06-142">The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![商務用 Skype Server 系統管理工具](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="4ac06-144">**商務用 Skype Server 拓撲**建立器用來建立、部署及管理拓撲的程式。</span><span class="sxs-lookup"><span data-stu-id="4ac06-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="4ac06-145">**商務用 Skype Server**的 [控制台]用來管理安裝的程式。</span><span class="sxs-lookup"><span data-stu-id="4ac06-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    


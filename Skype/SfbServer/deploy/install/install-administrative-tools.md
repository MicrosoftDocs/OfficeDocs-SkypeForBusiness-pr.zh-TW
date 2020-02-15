---
title: 安裝 Business Server skype 的系統管理工具
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
description: 摘要： 了解如何安裝系統管理工具安裝所需的的 Skype for Business Server。 下載 Microsoft 評估管理中心，從 Business Server Skype 免費試用版： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。
ms.openlocfilehash: 27cda52612eef1259017250ebcc4669e45165229
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018264"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="445e8-104">安裝 Business Server skype 的系統管理工具</span><span class="sxs-lookup"><span data-stu-id="445e8-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="445e8-105">**摘要：** 了解如何安裝系統管理工具安裝所需的的 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="445e8-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="445e8-106">下載 Microsoft 評估管理中心，從 Business Server Skype 免費試用版： [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="445e8-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="445e8-107">系統管理工具包括拓撲產生器] 及 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="445e8-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="445e8-108">系統管理工具必須安裝在至少一部伺服器拓撲或執行支援 skype for Business Server 的 Windows 作業系統版本的 64 位元管理工作站上。</span><span class="sxs-lookup"><span data-stu-id="445e8-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="445e8-109">您可以執行步驟 1 到 5，以任何順序。</span><span class="sxs-lookup"><span data-stu-id="445e8-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="445e8-110">不過，您必須先執行步驟 6、 7 和 8 順序，並在步驟 1 到 5 之後，在圖表中所述。</span><span class="sxs-lookup"><span data-stu-id="445e8-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="445e8-111">安裝系統管理工具是 8 的步驟 3。</span><span class="sxs-lookup"><span data-stu-id="445e8-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![概觀圖表](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="445e8-113">安裝 Skype for Business Server 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="445e8-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="445e8-114">Skype for Business Server 安裝媒體，可提供彈性的體驗。</span><span class="sxs-lookup"><span data-stu-id="445e8-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="445e8-115">當您第一次執行 Setup.exe 時，只有已安裝的工具是 Skype for Business Server 部署精靈與 Skype for Business Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="445e8-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="445e8-116">使用這兩種工具，稱為核心元件]，您可以繼續安裝程序，但它們不提供主要功能商務伺服器環境的整體 skype。</span><span class="sxs-lookup"><span data-stu-id="445e8-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="445e8-117">安裝核心元件之後，會自動啟動 [部署精靈。</span><span class="sxs-lookup"><span data-stu-id="445e8-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="445e8-118">] 區段中的標題為 [**安裝系統管理工具]** [部署精靈安裝 Skype 商務 Server 拓撲產生器與 Skype for Business Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="445e8-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="445e8-119">每個 Skype for Business Server 環境中必須至少一部伺服器已安裝系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="445e8-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="445e8-120">觀賞影片步驟的**安裝系統管理工具**：</span><span class="sxs-lookup"><span data-stu-id="445e8-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="445e8-121">安裝 Skype for Business Server 系統管理工具，從 [部署精靈</span><span class="sxs-lookup"><span data-stu-id="445e8-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="445e8-122">插入 Skype for Business Server 安裝媒體。</span><span class="sxs-lookup"><span data-stu-id="445e8-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="445e8-123">如果安裝程式不會自動開始，按兩下 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="445e8-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="445e8-124">安裝媒體需要 Microsoft 若要執行的 Visual c + +。</span><span class="sxs-lookup"><span data-stu-id="445e8-124">The installation media requires Microsoft Visual C++ to run.</span></span> <span data-ttu-id="445e8-125">就會出現對話方塊詢問您是否要安裝它。</span><span class="sxs-lookup"><span data-stu-id="445e8-125">A dialog box will pop up asking if you want to install it.</span></span> <span data-ttu-id="445e8-126">按一下 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="445e8-126">Click **Yes**.</span></span>
    
3. <span data-ttu-id="445e8-127">使用智慧型安裝程式，Skype for Business Server 中的新功能，您可以連線到網際網路，才能在安裝過程中檢查有更新。</span><span class="sxs-lookup"><span data-stu-id="445e8-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="445e8-128">此提供更好的經驗，以確定您在安裝有產品最新的更新。</span><span class="sxs-lookup"><span data-stu-id="445e8-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="445e8-129">按一下 **[安裝]** 開始安裝。</span><span class="sxs-lookup"><span data-stu-id="445e8-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="445e8-130">請仔細檢閱授權合約，以及如果您同意，請選取 [**我接受授權合約中的條款**]，並按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="445e8-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="445e8-131">Skype for Business 伺服器核心元件將會安裝在伺服器上。</span><span class="sxs-lookup"><span data-stu-id="445e8-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="445e8-132">核心元件包括下列項目，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="445e8-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![在應用程式] 畫面中的核心元件。](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="445e8-134">**Skype for Business Server 部署精靈**提供啟動平台安裝各種元件的 Skype for Business Server 部署計畫。</span><span class="sxs-lookup"><span data-stu-id="445e8-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="445e8-135">**Skype for Business Server 管理命令介面**一種預先設定的 PowerShell 程式可用於管理的 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="445e8-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="445e8-136">核心元件安裝完成後，Skype for Business Server 部署精靈將會自動啟動，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="445e8-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Skype for Business Server 部署精靈](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="445e8-138">除了核心元件] 中，您也需要安裝用 Skype 商務 Server 拓撲產生器與 Skype for Business Server Control Panel 環境中的至少一部伺服器上。</span><span class="sxs-lookup"><span data-stu-id="445e8-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="445e8-139">按一下 [部署精靈中的 [**安裝系統管理工具**]。</span><span class="sxs-lookup"><span data-stu-id="445e8-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="445e8-140">按 [下一步]\*\*\*\* 開始安裝。</span><span class="sxs-lookup"><span data-stu-id="445e8-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="445e8-141">當安裝完成時，按一下 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="445e8-141">Once the installation has completed, click **Finish**.</span></span> <span data-ttu-id="445e8-142">系統管理工具現在會被新增至伺服器時，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="445e8-142">The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Skype for Business Server 系統管理工具](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="445e8-144">**Skype for Business Server 拓撲產生器**程式，用來建立、 部署及管理拓撲。</span><span class="sxs-lookup"><span data-stu-id="445e8-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="445e8-145">**Skype for Business Server Control Panel**用來管理安裝程式。</span><span class="sxs-lookup"><span data-stu-id="445e8-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    


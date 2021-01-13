---
title: 在商務用 Skype Server 中安裝系統管理工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：瞭解如何安裝商務用 Skype Server 安裝所需的系統管理工具。 從 Microsoft 評估中心下載免費試用版的商務用 Skype Server，網址如下： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。
ms.openlocfilehash: ab3e64ae5d330c5b24eff7c23172b1141ff75527
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812103"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="bab9d-104">在商務用 Skype Server 中安裝系統管理工具</span><span class="sxs-lookup"><span data-stu-id="bab9d-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="bab9d-105">**摘要：** 瞭解如何安裝商務用 Skype Server 安裝所需的系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="bab9d-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="bab9d-106">從 Microsoft 評估中心下載免費試用版的商務用 Skype Server，網址如下： [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 。</span><span class="sxs-lookup"><span data-stu-id="bab9d-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="bab9d-107">系統管理工具組括拓撲產生器和 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="bab9d-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="bab9d-108">系統管理工具必須安裝在拓撲中至少一部伺服器上，或執行支援商務用 Skype Server 之 Windows 作業系統版本的64位管理工作站。</span><span class="sxs-lookup"><span data-stu-id="bab9d-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="bab9d-109">您可以依任何循序執行步驟1到5。</span><span class="sxs-lookup"><span data-stu-id="bab9d-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="bab9d-110">不過，您必須依序執行步驟6、7和8，並在步驟1到5之後進行，如圖表中所述。</span><span class="sxs-lookup"><span data-stu-id="bab9d-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="bab9d-111">安裝系統管理工具的步驟3之8。</span><span class="sxs-lookup"><span data-stu-id="bab9d-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![一覽表圖表](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="bab9d-113">安裝商務用 Skype Server 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="bab9d-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="bab9d-114">商務用 Skype Server 的安裝媒體可提供彈性的體驗。</span><span class="sxs-lookup"><span data-stu-id="bab9d-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="bab9d-115">當您第一次執行 Setup.exe 時，只有安裝的工具是商務用 Skype Server 部署嚮導和商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="bab9d-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="bab9d-116">使用這兩個工具（稱為核心元件），您可以繼續安裝程式，但不會提供整個商務用 Skype Server 環境的主要功能。</span><span class="sxs-lookup"><span data-stu-id="bab9d-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="bab9d-117">安裝核心元件後，就會自動啟動部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="bab9d-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="bab9d-118">「 **安裝系統管理工具** 」部署嚮導的區段會安裝商務用 Skype server 拓撲產生器和商務用 Skype server 控制台。</span><span class="sxs-lookup"><span data-stu-id="bab9d-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bab9d-119">每個商務用 Skype 伺服器環境都必須至少有一個伺服器安裝了系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="bab9d-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="bab9d-120">觀賞 **安裝系統管理工具** 的影片步驟：</span><span class="sxs-lookup"><span data-stu-id="bab9d-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="bab9d-121">從部署嚮導安裝商務用 Skype Server 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="bab9d-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="bab9d-122">插入商務用 Skype Server 安裝媒體。</span><span class="sxs-lookup"><span data-stu-id="bab9d-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="bab9d-123">如果安裝程式未自動開始，請按兩下 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="bab9d-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="bab9d-124">安裝媒體需要 Microsoft Visual c + + 才能執行。</span><span class="sxs-lookup"><span data-stu-id="bab9d-124">The installation media requires Microsoft Visual C++ to run.</span></span> <span data-ttu-id="bab9d-125">隨即會彈出一個對話方塊，詢問您是否要安裝。</span><span class="sxs-lookup"><span data-stu-id="bab9d-125">A dialog box will pop up asking if you want to install it.</span></span> <span data-ttu-id="bab9d-126">按一下 [是]。</span><span class="sxs-lookup"><span data-stu-id="bab9d-126">Click **Yes**.</span></span>
    
3. <span data-ttu-id="bab9d-127">您可以使用 Smart Setup （商務用 Skype Server 中的新功能），連線至網際網路，以在安裝程式期間檢查更新。</span><span class="sxs-lookup"><span data-stu-id="bab9d-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="bab9d-128">這可讓您在安裝時，確保產品有最新的更新，以獲得較佳的體驗。</span><span class="sxs-lookup"><span data-stu-id="bab9d-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="bab9d-129">按一下 **[安裝]** 開始安裝。</span><span class="sxs-lookup"><span data-stu-id="bab9d-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="bab9d-130">請仔細閱讀授權合約，如果同意，請選取 [ **我接受授權合約中的條款**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="bab9d-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="bab9d-131">商務用 Skype Server 核心元件將會安裝在伺服器上。</span><span class="sxs-lookup"><span data-stu-id="bab9d-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="bab9d-132">核心元件包含下列，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="bab9d-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![[應用程式] 畫面中的核心元件。](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="bab9d-134">**商務用 Skype Server 部署嚮導** 為安裝商務用 Skype Server 的各種元件提供啟動墊的部署程式。</span><span class="sxs-lookup"><span data-stu-id="bab9d-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="bab9d-135">**商務用 Skype Server 管理命令** 介面可供您管理商務用 Skype Server 的預先設定的 PowerShell 程式。</span><span class="sxs-lookup"><span data-stu-id="bab9d-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="bab9d-136">核心元件的安裝完成後，商務用 Skype Server 部署嚮導將會自動啟動，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="bab9d-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![商務用 Skype Server 部署嚮導](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="bab9d-138">除了核心元件之外，您還需要在環境中至少一部伺服器上安裝商務用 Skype Server 拓撲產生器和商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="bab9d-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="bab9d-139">按一下 [部署嚮導] 上的 [ **安裝系統管理工具** ]。</span><span class="sxs-lookup"><span data-stu-id="bab9d-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="bab9d-140">按 [下一步] 開始安裝。</span><span class="sxs-lookup"><span data-stu-id="bab9d-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="bab9d-141">完成安裝後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="bab9d-141">Once the installation has completed, click **Finish**.</span></span> <span data-ttu-id="bab9d-142">系統管理工具現在已新增至伺服器，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="bab9d-142">The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![商務用 Skype Server 系統管理工具](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="bab9d-144">**商務用 Skype Server 拓撲** 產生器用來建立、部署及管理拓撲的程式。</span><span class="sxs-lookup"><span data-stu-id="bab9d-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="bab9d-145">**商務用 Skype Server 控制台** 用來管理安裝的程式。</span><span class="sxs-lookup"><span data-stu-id="bab9d-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    


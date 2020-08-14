---
title: 安裝商務用 Skype Server 的必要條件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
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
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 摘要：瞭解在安裝商務用 Skype Server 之前，必須先設定的伺服器和伺服器角色。 從 Microsoft 評估中心下載免費試用版的商務用 Skype Server，網址如下： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。
ms.openlocfilehash: fedcebe601d21f0e581795c264ed26c6e90716bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018254"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a><span data-ttu-id="e1a0f-104">安裝商務用 Skype Server 的必要條件</span><span class="sxs-lookup"><span data-stu-id="e1a0f-104">Install prerequisites for Skype for Business Server</span></span>
 
<span data-ttu-id="e1a0f-105">**摘要：** 深入瞭解在安裝商務用 Skype Server 之前，必須先設定的伺服器和伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server.</span></span> <span data-ttu-id="e1a0f-106">從 [Microsoft 評估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)下載商務用 Skype Server 免費試用版。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="e1a0f-107">安裝必要條件包含在拓撲中的每一部伺服器上安裝必要的角色和功能，以設定 Windows Server。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="e1a0f-108">這些需求是以伺服器在拓撲中所能滿足的角色為基礎。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="e1a0f-109">您可以依任何循序執行步驟1到5。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="e1a0f-110">不過，您必須依序執行步驟6、7和8，並在步驟1到5之後進行，如圖表中所述。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="e1a0f-111">安裝必要條件是步驟1之8。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-111">Installing prerequisites is step 1 of 8.</span></span>
  
![一覽表圖表-安裝必要條件。](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="e1a0f-113">安裝 Windows Server</span><span class="sxs-lookup"><span data-stu-id="e1a0f-113">Setup Windows Server</span></span>

<span data-ttu-id="e1a0f-114">商務用 Skype 伺服器需要 Windows Server 作業系統和許多必要條件才能安裝。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-114">Skype for Business Server requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="e1a0f-115">如需規劃必要條件的詳細資訊，請參閱 [商務用 Skype server 的伺服器需求](../../../SfBServer2019/plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="e1a0f-116">此程式會使用 Windows Server 2012 R2。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-116">This procedure uses Windows Server 2012 R2.</span></span> <span data-ttu-id="e1a0f-117">如果您使用的是不同版本的 Windows Server，此程式可能會稍有不同。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-117">If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e1a0f-118">開始之前，請先使用 Windows Update 確定 Windows Server 是最新的。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![最新的 Windows Server。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="e1a0f-120">觀賞 **安裝必要條件**的影片步驟：</span><span class="sxs-lookup"><span data-stu-id="e1a0f-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="e1a0f-121">為前端伺服器安裝必要的角色和功能</span><span class="sxs-lookup"><span data-stu-id="e1a0f-121">Install required roles and features for front-end servers</span></span>

<span data-ttu-id="e1a0f-122">您可以使用伺服器管理員安裝必要的角色和功能。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-122">You can install the required roles and features using Server Manager.</span></span> 
    
1. <span data-ttu-id="e1a0f-123">安裝 [適用于商務用 Skype server 之伺服器需求](../../../SfBServer2019/plan/system-requirements.md)中列出的必要條件軟體功能。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-123">Install the prerequisite software features listed in [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="e1a0f-124">必要的軟體必須位於會執行商務用 Skype 伺服器的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-124">The required software must be on the server that will run Skype for Business Server.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="e1a0f-125">Windows Server 2012 R2 預設不會安裝必要功能的所有來源檔案。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-125">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="e1a0f-126">如果伺服器未連線到網際網路，您必須插入 Windows Server 2012 R2 媒體，然後選取 [ **指定替代來源路徑** ] 以安裝必要的功能。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-126">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="e1a0f-127">來源檔案位於 sources\sxs 目錄中。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-127">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="e1a0f-128">例如，如果 Windows Server 2012 R2 媒體位於磁碟機 D，您會將路徑設定為 `d:\sources\sxs` 。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-128">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="e1a0f-129">您必須具備 Windows Update 中的最新更新，才會有重要的更新。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-129">It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="e1a0f-130">如果您未連線到網際網路，則必須手動安裝所有相關的更新，以及必要更新的任何必要條件。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-130">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
1. <span data-ttu-id="e1a0f-131">當對話方塊指出安裝已完成時，您必須重新開機伺服器才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-131">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
1. <span data-ttu-id="e1a0f-132">再次執行 **Windows Update** ，以檢查是否有安裝的角色和服務的任何更新。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-132">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
1. <span data-ttu-id="e1a0f-133">如果您要在此伺服器上使用商務用 Skype Server 控制台，您也必須安裝 Silverlight。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-133">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="e1a0f-134">若要安裝 Silverlight，請參閱 [Microsoft Silverlight](https://www.microsoft.com/silverlight/)。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-134">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="e1a0f-135">執行非前端伺服器角色的伺服器必要條件，例如 Director、Persistent Chat 或 Edge 的角色，都有自己的必要條件。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-135">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="e1a0f-136">如需每種伺服器類型所需的確切必要條件的詳細資訊，請參閱 [商務用 Skype server 的伺服器需求](../../../SfBServer2019/plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e1a0f-136">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  


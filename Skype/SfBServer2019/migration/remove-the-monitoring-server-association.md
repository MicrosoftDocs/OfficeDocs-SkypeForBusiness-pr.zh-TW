---
title: 移除監控伺服器關聯
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 若要移除監控伺服器，您必須變更或清除關聯的前端集區、前端伺服器、Survivable 分支裝置和 Survivable 分支伺服器上的相依性。 您可以編輯前端集區、前端伺服器、Survivable 分支裝置和 Survivable 分支伺服器的屬性，以移除相依性。 在 [拓撲產生器] 中清除相依性和刪除伺服器之後，系統會通知您也會刪除拓撲產生器中相關聯的資料庫存放區物件。
ms.openlocfilehash: dafbeb88773330164a5daf2144988d1afb2776a8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753415"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="083ec-105">移除監控伺服器關聯</span><span class="sxs-lookup"><span data-stu-id="083ec-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="083ec-106">若要移除監控伺服器，您必須變更或清除關聯的前端集區、前端伺服器、Survivable 分支裝置和 Survivable 分支伺服器上的相依性。</span><span class="sxs-lookup"><span data-stu-id="083ec-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="083ec-107">您可以編輯前端集區、前端伺服器、Survivable 分支裝置及 Survivable 分支伺服器的屬性，以移除相依性。</span><span class="sxs-lookup"><span data-stu-id="083ec-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="083ec-108">在 [拓撲產生器] 中清除相依性和刪除伺服器之後，系統會通知您也會刪除拓撲產生器中相關聯的資料庫存放區物件。</span><span class="sxs-lookup"><span data-stu-id="083ec-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="083ec-109">若要移除監控伺服器關聯</span><span class="sxs-lookup"><span data-stu-id="083ec-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="083ec-110">在商務用 Skype Server 2019 前端伺服器上，開啟拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="083ec-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="083ec-111">流覽至 [舊版安裝] 節點。</span><span class="sxs-lookup"><span data-stu-id="083ec-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="083ec-112">在 [拓撲產生器] 中，根據監控伺服器定義的位置，展開 [ **Enterprise Edition 前端**集區]、[ **Standard Edition 前端伺服器**] 或 [**分支網站**]。</span><span class="sxs-lookup"><span data-stu-id="083ec-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="083ec-113">如果您有相關聯的 Survivable 分支伺服器，請展開 [**分支網站**]，展開分支網站名稱，然後展開 [ **Survivable 分支裝置**]。</span><span class="sxs-lookup"><span data-stu-id="083ec-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="083ec-114">使用者介面中的**Survivable 分支裝置**會同時套用至 Survivable branch Server 和 Survivable branch 裝置。</span><span class="sxs-lookup"><span data-stu-id="083ec-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="083ec-115">以滑鼠右鍵按一下與監控伺服器相關聯的集區、伺服器或裝置，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="083ec-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="083ec-116">在 [**編輯屬性**] 的 **[一般**  >  **關聯**] 底下，清除 [**關聯監控伺服器**] 核取方塊，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="083ec-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="083ec-117">針對與監控伺服器關聯的任何其他集區、伺服器或裝置，重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="083ec-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="083ec-118">以滑鼠右鍵按一下監控伺服器，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="083ec-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="083ec-119">在 [刪除相依存放區]\*\*\*\* 上，按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="083ec-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="083ec-120">視需要發行拓撲、檢查複寫狀態，並執行商務用 Skype Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="083ec-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    


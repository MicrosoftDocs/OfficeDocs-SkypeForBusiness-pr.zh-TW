---
title: 移除監視伺服器關聯
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 若要移除監視伺服器, 您需要變更或清除相關聯的 [前端] 池、[前端伺服器]、[Survivable 分支裝置] 和 [Survivable 分支伺服器] 的相依性。 您可以編輯 [前端] 池、[前端伺服器]、[Survivable 分支裝置] 和 [Survivable 分支伺服器] 的屬性, 以移除相依性。 清除相依性並刪除拓撲建立器中的伺服器之後, 系統會通知您, 拓撲結構庫中相關聯的資料庫存放物件也會被刪除。
ms.openlocfilehash: 366bb67815df99542b893e9ced79c1fc1f0e3e9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193277"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="51a45-105">移除監視伺服器關聯</span><span class="sxs-lookup"><span data-stu-id="51a45-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="51a45-106">若要移除監視伺服器, 您需要變更或清除相關聯的 [前端] 池、[前端伺服器]、[Survivable 分支裝置] 和 [Survivable 分支伺服器] 的相依性。</span><span class="sxs-lookup"><span data-stu-id="51a45-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="51a45-107">您可以編輯 [前端] 池、[前端伺服器]、[Survivable 分支裝置] 和 [Survivable 分支伺服器] 的屬性, 以移除相依性。</span><span class="sxs-lookup"><span data-stu-id="51a45-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="51a45-108">清除相依性並刪除拓撲建立器中的伺服器之後, 系統會通知您, 拓撲結構庫中相關聯的資料庫存放物件也會被刪除。</span><span class="sxs-lookup"><span data-stu-id="51a45-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="51a45-109">移除監視伺服器關聯</span><span class="sxs-lookup"><span data-stu-id="51a45-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="51a45-110">在商務用 Skype Server 2019 前端伺服器上, 開啟拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="51a45-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="51a45-111">流覽至 [舊版安裝] 節點。</span><span class="sxs-lookup"><span data-stu-id="51a45-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="51a45-112">在拓撲建立器中, 根據監視伺服器的定義位置, 展開 [**企業版前端池**]、[**標準版前端伺服器**] 或 [**分支網站**]。</span><span class="sxs-lookup"><span data-stu-id="51a45-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="51a45-113">如果您有關聯的 Survivable 分支伺服器, 請展開 [**分支網站**], 展開分支網站名稱, 然後展開 [ **Survivable 分支裝置**]。</span><span class="sxs-lookup"><span data-stu-id="51a45-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="51a45-114">使用者介面中的**Survivable 分支裝置**同時適用于 Survivable 分支伺服器和 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="51a45-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="51a45-115">以滑鼠右鍵按一下與監視伺服器相關聯的 [池]、[伺服器] 或 [裝置], 然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="51a45-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="51a45-116">在 [**編輯屬性**] 的 **[一般** > **關聯**] 底下, 清除 [**建立監視伺服器關聯**] 核取方塊, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="51a45-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="51a45-117">針對與監視伺服器相關聯的任何其他池、伺服器或裝置, 重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="51a45-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="51a45-118">以滑鼠右鍵按一下監視伺服器, 然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="51a45-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="51a45-119">在 [**刪除相依儲存區**] 中, 按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="51a45-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="51a45-120">如有需要, 請發佈拓撲、檢查複製狀態, 以及執行商務用 Skype Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="51a45-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    


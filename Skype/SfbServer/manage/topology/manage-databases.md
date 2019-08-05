---
title: 在商務用 Skype Server 中使用 AlwaysOn 可用性群組管理資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: '摘要: 瞭解如何將更多商務用 Skype Server 資料庫新增至現有的 AlwaysOn 可用性群組, 並瞭解在 Skype 中修補或升級作為 AlwaysOn 可用性群組一部分的後端伺服器之後所需的其他步驟。商務伺服器。'
ms.openlocfilehash: c6d8877448a68aa2331f3c290170418f6dca08ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187105"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="94099-103">在商務用 Skype Server 中使用 AlwaysOn 可用性群組管理資料庫</span><span class="sxs-lookup"><span data-stu-id="94099-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="94099-104">使用本文中的步驟, 在商務用 Skype Server 的現有 AlwaysOn 可用性群組中新增更多商務用 Skype Server 資料庫, 並在您修補或升級屬於 AlwaysOn 的後端伺服器之後, 找出必要的額外步驟商務用 Skype Server 中的 [可用性] 群組。</span><span class="sxs-lookup"><span data-stu-id="94099-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="94099-105">新增資料庫至 AlwaysOn 可用性群組</span><span class="sxs-lookup"><span data-stu-id="94099-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="94099-106">開啟 SQL Server Management Studio, 然後流覽至 [AlwaysOn 可用性] 群組。</span><span class="sxs-lookup"><span data-stu-id="94099-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="94099-107">將它容錯移轉到主要複本。</span><span class="sxs-lookup"><span data-stu-id="94099-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="94099-108">在 [拓撲建立器] 中, 將 [AlwaysOn 可用性] 群組的 SQL Server FQDN 設定為該組主要節點的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="94099-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="94099-109">開啟拓撲建立器, 選取 [**從現有部署下載拓撲**], 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="94099-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="94099-110">展開 [商務用 Skype 伺服器]、展開您的拓撲, 然後展開 **[SQL Server 存放區**]。</span><span class="sxs-lookup"><span data-stu-id="94099-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="94099-111">以滑鼠右鍵按一下新 [AlwaysOn 可用性] 群組的 SQL 存放區, 然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="94099-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="94099-112">在頁面底部的 [ **SQL SERVER FQDN** ] 方塊中, 輸入 [AlwaysOn 可用性] 群組主要節點的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="94099-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="94099-113">發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="94099-113">Publish the topology.</span></span> <span data-ttu-id="94099-114">從 [**動作**] 功能表按一下 [**拓撲**], 然後按一下 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="94099-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="94099-115">然後在確認頁面中, 按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="94099-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="94099-116">使用 SQL Server Management Studio 將新資料庫新增至 [AlwaysOn 可用性] 群組。</span><span class="sxs-lookup"><span data-stu-id="94099-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="94099-117">在 AlwaysOn 可用性群組中修補或更新 SQL Server</span><span class="sxs-lookup"><span data-stu-id="94099-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="94099-118">在針對屬於 AlwaysOn 可用性群組的後端伺服器進行修補之後, 您必須重新發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="94099-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="94099-119">在商務用 Skype 伺服器或伺服器上安裝更新。</span><span class="sxs-lookup"><span data-stu-id="94099-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="94099-120">在商務用 Skype 管理 Shell 中執行下列 PowerShell 命令 (以適當 permissioned 的帳戶登入, 以將變更套用至 SQL AlwaysOn 資料庫), 如下所示:</span><span class="sxs-lookup"><span data-stu-id="94099-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="94099-121">其中 [sqlpool.contoso.com] 會以您的 AlwaysOn 可用性群組的完整功能變數名稱 (FQDN) 取代。</span><span class="sxs-lookup"><span data-stu-id="94099-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>

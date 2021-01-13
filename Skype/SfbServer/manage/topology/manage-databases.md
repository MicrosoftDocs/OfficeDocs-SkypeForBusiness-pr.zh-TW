---
title: 在商務用 Skype Server 中管理具有 AlwaysOn 可用性群組的資料庫
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 摘要：瞭解如何將更多商務用 Skype Server 資料庫新增至現有的 AlwaysOn 可用性群組，以及在修補或升級後端伺服器（屬於商務用 Skype Server 中的 AlwaysOn 可用性群組一部分）之後，瞭解必要的額外步驟。
ms.openlocfilehash: 444194c9cda5f4c3f82e6f3f7698395dce1a5d07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826363"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="5e89d-103">在商務用 Skype Server 中管理具有 AlwaysOn 可用性群組的資料庫</span><span class="sxs-lookup"><span data-stu-id="5e89d-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="5e89d-104">使用本文中的步驟，將更多商務用 Skype 伺服器資料庫新增至現有的 AlwaysOn 可用性群組中的商務用 Skype Server 中，並在修補或升級後端伺服器（屬於商務用 Skype Server 中的 AlwaysOn 可用性群組一部分）之後，查看必要的額外步驟。</span><span class="sxs-lookup"><span data-stu-id="5e89d-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="5e89d-105">將資料庫新增至 AlwaysOn 可用性群組</span><span class="sxs-lookup"><span data-stu-id="5e89d-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="5e89d-106">開啟 SQL Server Management Studio，然後流覽至 [AlwaysOn 可用性] 群組。</span><span class="sxs-lookup"><span data-stu-id="5e89d-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="5e89d-107">將其容錯移轉至主要複本。</span><span class="sxs-lookup"><span data-stu-id="5e89d-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="5e89d-108">在 [拓撲產生器] 中，將 [AlwaysOn 可用性] 群組的 SQL Server FQDN 設定為該群組主要節點的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5e89d-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="5e89d-109">開啟拓撲產生器，選取 [ **從現有的部署下載拓撲**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="5e89d-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="5e89d-110">展開 [商務用 Skype 伺服器]，展開您的拓撲，然後展開 **[SQL Server 儲存區**]。</span><span class="sxs-lookup"><span data-stu-id="5e89d-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="5e89d-111">以滑鼠右鍵按一下新 AlwaysOn 可用性群組的 SQL 存放區，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="5e89d-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="5e89d-112">在頁面底部的 [ **SQL SERVER FQDN** ] 方塊中，輸入 AlwaysOn 可用性群組之主要節點的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5e89d-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="5e89d-113">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="5e89d-113">Publish the topology.</span></span> <span data-ttu-id="5e89d-114">從 [ **動作** ] 功能表中，按一下 [ **拓撲** ]，然後再 **發佈**。</span><span class="sxs-lookup"><span data-stu-id="5e89d-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="5e89d-115">然後在 [確認] 頁面中按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5e89d-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="5e89d-116">使用 SQL Server Management Studio 將新資料庫新增至 AlwaysOn 可用性群組。</span><span class="sxs-lookup"><span data-stu-id="5e89d-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="5e89d-117">在 AlwaysOn 可用性群組中修補或更新 SQL Server</span><span class="sxs-lookup"><span data-stu-id="5e89d-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="5e89d-118">在修補屬於 AlwaysOn 可用性群組一部分的後端伺服器之後，您必須重新發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="5e89d-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="5e89d-119">在商務用 Skype 伺服器或伺服器上安裝更新。</span><span class="sxs-lookup"><span data-stu-id="5e89d-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="5e89d-120">在商務用 Skype 管理命令介面中執行下列 PowerShell 命令 (以適當專屬許可權將變更套用至 SQL AlwaysOn 資料庫的帳戶進行登錄) 如下所示：</span><span class="sxs-lookup"><span data-stu-id="5e89d-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="5e89d-121">其中 [sqlpool.contoso.com] 會以 AlwaysOn 可用性群組的完整功能變數名稱 (FQDN) 取代。</span><span class="sxs-lookup"><span data-stu-id="5e89d-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>

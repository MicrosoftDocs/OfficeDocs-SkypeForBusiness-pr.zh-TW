---
title: 新增常設聊天室規範備份 SQL Server 儲存區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: 您可以設定備份合規性 SQL Server 存放區, 該伺服器將提供持久聊天伺服器或持久聊天伺服器相容性 SQL Server 書店的備份資料庫。
ms.openlocfilehash: 457874f87266453939c75cdef50d30231d8610bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187957"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a><span data-ttu-id="ac599-103">新增常設聊天室規範備份 SQL Server 儲存區</span><span class="sxs-lookup"><span data-stu-id="ac599-103">Add Persistent Chat Compliance Backup SQL Server Store</span></span>
 
<span data-ttu-id="ac599-104">您可以設定備份合規性 SQL Server 存放區, 該伺服器將提供持久聊天伺服器或持久聊天伺服器相容性 SQL Server 書店的備份資料庫。</span><span class="sxs-lookup"><span data-stu-id="ac599-104">You configure the Backup compliance SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server compliance SQL Server stores.</span></span>
  
 <span data-ttu-id="ac599-105">**SQL server store**: 選取現有的 SQL Server, 並選擇性地使用持久聊天的實例。</span><span class="sxs-lookup"><span data-stu-id="ac599-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="ac599-106">按一下 [**新增**] 以定義新的 SQL Server, 以及可選擇的持續聊天備份合規性資料的新實例。</span><span class="sxs-lookup"><span data-stu-id="ac599-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="ac599-107">選取 [**啟用 SQL server store 鏡像**] 核取方塊, 以設定 SQL Server 資料庫及選用的實例, 該範例會為持續聊天備份合規性資料提供鏡像資料庫。</span><span class="sxs-lookup"><span data-stu-id="ac599-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="ac599-108">從清單中選取 [**鏡像 Sql server** ], 將 sql server 和選用實例當作持久的 [聊天備份合規性 sql server] 的 sql server 鏡像。</span><span class="sxs-lookup"><span data-stu-id="ac599-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup compliance SQL Server.</span></span>
  
<span data-ttu-id="ac599-109">按一下 [**新增**] 來定義新的 SQL server, 也可以選擇使用持久聊天 SQL server 鏡像的新實例。</span><span class="sxs-lookup"><span data-stu-id="ac599-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="ac599-110">選取 [使用 SQL Server 鏡像見證啟用自動容錯移轉]\*\*\*\* 清單，此 SQL Server 會在容錯移轉案例中擔任見證伺服器。</span><span class="sxs-lookup"><span data-stu-id="ac599-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="ac599-111">見證伺服器不會針對持久聊天伺服器進行鏡像或主機資料, 但可確保鏡像配置中只有一個 SQL Server 在任何時候都是作用中的 SQL 伺服器。</span><span class="sxs-lookup"><span data-stu-id="ac599-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="ac599-112">按一下 [**新增**] 以定義新的 SQL Server 見證 (可選擇永久聊天備份合規性 SQL server 鏡像見證的實例)。</span><span class="sxs-lookup"><span data-stu-id="ac599-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="ac599-113">按 [上一步] \*\*\*\* 回到上一個集區定義對話方塊。</span><span class="sxs-lookup"><span data-stu-id="ac599-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="ac599-114">當您完成輸入此池子的 [備份 SQL Server store 設定] 選項, 然後繼續進行持續聊天伺服器池定義時, 請按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="ac599-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="ac599-115">按一下 [取消]\*\*\*\* 捨棄所有變更，並結束 [定義新的常設聊天室集區精靈]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac599-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="ac599-116">按一下 [說明]\*\*\*\* 存取即時線上說明，例如此頁面。</span><span class="sxs-lookup"><span data-stu-id="ac599-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ac599-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ac599-117">See also</span></span>

[<span data-ttu-id="ac599-118">在商務用 Skype Server 2015 中規劃常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="ac599-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="ac599-119">商務用 Skype Server 2015 的伺服器需求</span><span class="sxs-lookup"><span data-stu-id="ac599-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="ac599-120">常設聊天室伺服器的硬體與軟體需求</span><span class="sxs-lookup"><span data-stu-id="ac599-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="ac599-121">設定常設聊天室伺服器的規範服務</span><span class="sxs-lookup"><span data-stu-id="ac599-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
  
[<span data-ttu-id="ac599-122">設定常設聊天室伺服器的高可用性和災害復原</span><span class="sxs-lookup"><span data-stu-id="ac599-122">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

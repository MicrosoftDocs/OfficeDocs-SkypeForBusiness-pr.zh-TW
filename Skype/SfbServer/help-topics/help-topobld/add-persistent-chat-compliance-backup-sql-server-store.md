---
title: 新增常設聊天室規範備份 SQL Server 儲存區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: 您可以設定備份規範 SQL Server 儲存區，為 Persistent Chat Server 或 Persistent Chat Server 規範 SQL Server 儲存區提供備份資料庫。
ms.openlocfilehash: 9251c322560d06652c4eefe80b6c05a51aa9f922
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218694"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a><span data-ttu-id="683dd-103">新增常設聊天室規範備份 SQL Server 儲存區</span><span class="sxs-lookup"><span data-stu-id="683dd-103">Add Persistent Chat Compliance Backup SQL Server Store</span></span>
 
<span data-ttu-id="683dd-104">您可以設定備份規範 SQL Server 儲存區，為 Persistent Chat Server 或 Persistent Chat Server 規範 SQL Server 儲存區提供備份資料庫。</span><span class="sxs-lookup"><span data-stu-id="683dd-104">You configure the Backup compliance SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server compliance SQL Server stores.</span></span>
  
 <span data-ttu-id="683dd-105">**SQL server 儲存區**：選取現有的 SQL Server，並選擇性地選取持久聊天的實例。</span><span class="sxs-lookup"><span data-stu-id="683dd-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="683dd-106">按一下 [ **新增** ] 可定義新的 SQL Server，並選擇性地定義持久聊天備份規範資料的新實例。</span><span class="sxs-lookup"><span data-stu-id="683dd-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="683dd-107">選取 [ **啟用 Sql server 儲存區鏡像** ] 核取方塊可設定 sql server 資料庫和選用實例，為持久聊天備份規範資料提供鏡像資料庫。</span><span class="sxs-lookup"><span data-stu-id="683dd-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="683dd-108">從 [ **鏡像 Sql server 儲存區** ] 清單中，選取要充當持久聊天備份規範 sql SERVER 之 sql server 鏡像的 sql server 和選用實例。</span><span class="sxs-lookup"><span data-stu-id="683dd-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup compliance SQL Server.</span></span>
  
<span data-ttu-id="683dd-109">按一下 [ **新增** ] 可定義新的 SQL server，並選擇性地定義 PERSISTENT Chat SQL server 鏡像的新實例。</span><span class="sxs-lookup"><span data-stu-id="683dd-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="683dd-110">選取 [使用 SQL Server 鏡像見證啟用自動容錯移轉]\*\*\*\* 清單，此 SQL Server 會在容錯移轉案例中擔任見證伺服器。</span><span class="sxs-lookup"><span data-stu-id="683dd-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="683dd-111">見證伺服器不會鏡像或裝載 Persistent 聊天伺服器的資料，但可確保鏡像設定中每次只有一部 SQL Server 成為使用中的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="683dd-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="683dd-112">按一下 [ **新增** ] 可定義新的 SQL Server 見證，並選擇性地定義持久聊天備份規範 SQL server 鏡像見證的實例。</span><span class="sxs-lookup"><span data-stu-id="683dd-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="683dd-113">按 [上一步]\*\*\*\* 回到上一個集區定義對話方塊。</span><span class="sxs-lookup"><span data-stu-id="683dd-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="683dd-114">完成輸入此集區之備份 SQL Server 儲存區設定的選項之後，按 **[下一步]** ，以繼續使用 Persistent Chat Server 集區定義。</span><span class="sxs-lookup"><span data-stu-id="683dd-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="683dd-115">按一下 [取消]\*\*\*\* 捨棄所有變更，並結束 [定義新的常設聊天室集區精靈]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="683dd-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="683dd-116">按一下 [說明]\*\*\*\* 存取即時線上說明，例如此頁面。</span><span class="sxs-lookup"><span data-stu-id="683dd-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="683dd-117">請參閱</span><span class="sxs-lookup"><span data-stu-id="683dd-117">See also</span></span>

[<span data-ttu-id="683dd-118">在商務用 Skype Server 2015 中規劃 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="683dd-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="683dd-119">商務用 Skype Server 2015 的伺服器需求</span><span class="sxs-lookup"><span data-stu-id="683dd-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="683dd-120">商務用 Skype 2015 Server 中的 Persistent Chat Server 的硬體和軟體需求</span><span class="sxs-lookup"><span data-stu-id="683dd-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="683dd-121">在商務用 Skype Server 2015 中設定 Persistent Chat Server 的合規性服務</span><span class="sxs-lookup"><span data-stu-id="683dd-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
  
[<span data-ttu-id="683dd-122">在商務用 Skype Server 2015 中設定 Persistent Chat Server 的高可用性和嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="683dd-122">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

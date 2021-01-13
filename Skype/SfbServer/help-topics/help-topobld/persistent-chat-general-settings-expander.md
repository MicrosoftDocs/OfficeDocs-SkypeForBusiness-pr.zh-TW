---
title: 常設聊天室一般設定展開工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 您可以透過設定或定義下列內容，來編輯 Persistent Chat Server 或 Persistent Chat Server 集區的一般設定：
ms.openlocfilehash: 5c0884f4877e622a82b58ea914ffa934eecc3291
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823849"
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="64ec4-103">常設聊天室一般設定展開工具</span><span class="sxs-lookup"><span data-stu-id="64ec4-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="64ec4-104">您可以透過設定或定義下列內容，來編輯 Persistent Chat Server 或 Persistent Chat Server 集區的 **一般** 設定：</span><span class="sxs-lookup"><span data-stu-id="64ec4-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="64ec4-105">**一般**</span><span class="sxs-lookup"><span data-stu-id="64ec4-105">**General**</span></span>
  
- <span data-ttu-id="64ec4-106">**FQDN**：編輯此設定以定義 Persistent chat Server 或 Persistent chat server 集區的完整功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="64ec4-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="64ec4-107">**常設聊天室集區的顯示名稱**：定義此設定可為伺服器或集區提供使用者易記及易於讀取的設定。</span><span class="sxs-lookup"><span data-stu-id="64ec4-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="64ec4-108">這項設定可讓您的使用者更輕鬆地依顯示名稱關聯指定的持續聊天伺服器或 Persistent Chat Server 集區，而不是更難於瞭解完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="64ec4-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="64ec4-109">**常設聊天室連接埠**：指定用於常設聊天室的連接埠。</span><span class="sxs-lookup"><span data-stu-id="64ec4-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="64ec4-110">您可以透過設定或定義下列內容，來編輯 Persistent Chat Server 或 Persistent Chat Server 集區的 **關聯** 性設定：</span><span class="sxs-lookup"><span data-stu-id="64ec4-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="64ec4-111">**協會**</span><span class="sxs-lookup"><span data-stu-id="64ec4-111">**Associations**</span></span>
  
- <span data-ttu-id="64ec4-112">**Sql server 儲存區**：從清單中選取 SQL server 儲存區和選用的命名實例。</span><span class="sxs-lookup"><span data-stu-id="64ec4-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="64ec4-113">按一下 [新增] 定義新的 SQL Server 儲存區和選用執行個體。</span><span class="sxs-lookup"><span data-stu-id="64ec4-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="64ec4-114">如果您想啟用主要 SQL Server 儲存區的鏡像，請選取 [ **啟用 SQL Server 儲存區鏡像** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="64ec4-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="64ec4-115">如果您選擇啟用 SQL Server 儲存區鏡像，請從 [ **鏡像 SQL Server 儲存區**] 清單中選取儲存區和實例。</span><span class="sxs-lookup"><span data-stu-id="64ec4-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="64ec4-116">按一下 [新增] 定義新的 SQL Server 儲存區和選用執行個體。</span><span class="sxs-lookup"><span data-stu-id="64ec4-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="64ec4-117">如果您想自動容錯移轉主要 SQL Server 儲存區，請選取 [ **使用 SQL Server 鏡像見證啟用自動容錯移轉** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="64ec4-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="64ec4-118">如果您選擇啟用 SQL Server 儲存區鏡像見證以啟用自動容錯移轉，請從清單中選取儲存區和實例。</span><span class="sxs-lookup"><span data-stu-id="64ec4-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="64ec4-119">按一下 [新增] 定義見證儲存區的新 SQL Server 儲存區和選用執行個體。</span><span class="sxs-lookup"><span data-stu-id="64ec4-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="64ec4-120">如果您想要啟用 SQL Server 嚴重損壞修復，請選取 [ **使用備份 SQL Server 儲存區來啟用** 嚴重損壞修復] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="64ec4-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="64ec4-121">如果選擇啟用嚴重損壞修復，請從 [備份 SQL Server 儲存區] 清單中選取儲存區和執行個體。</span><span class="sxs-lookup"><span data-stu-id="64ec4-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="64ec4-122">按一下 [新增] 定義新的 SQL Server 儲存區和選用執行個體。</span><span class="sxs-lookup"><span data-stu-id="64ec4-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="64ec4-123">如果您想啟用備份 SQL Server 鏡像儲存區的鏡像，請選取 [ **啟用 SQL Server 儲存區鏡像** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="64ec4-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="64ec4-124">如果您選擇啟用備份 SQL Server 儲存區鏡像，請從 [ **備份 Sql server 儲存區鏡像**] 清單中選取儲存區和實例。</span><span class="sxs-lookup"><span data-stu-id="64ec4-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="64ec4-125">按一下 [新增] 定義新的 SQL Server 儲存區和選用執行個體。</span><span class="sxs-lookup"><span data-stu-id="64ec4-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="64ec4-126">如果您想自動容錯移轉備份 SQL Server 儲存區，請選取 [ **使用 SQL Server 鏡像見證啟用自動容錯移轉** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="64ec4-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="64ec4-127">如果您選擇啟用 SQL Server 儲存區鏡像見證以啟用自動容錯移轉，請從清單中選取儲存區和實例。</span><span class="sxs-lookup"><span data-stu-id="64ec4-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="64ec4-128">按一下 [新增] 定義見證儲存區的新 SQL Server 儲存區和選用執行個體。</span><span class="sxs-lookup"><span data-stu-id="64ec4-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="64ec4-129">如果您想啟用規範資料庫，請選取 [啟用規範] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="64ec4-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="64ec4-130">如果選擇啟用規範，請從 [規範 SQL Server 儲存區] 清單中選取儲存區和執行個體。</span><span class="sxs-lookup"><span data-stu-id="64ec4-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="64ec4-131">按一下 [新增] 定義新的 SQL Server 儲存區和選用執行個體。</span><span class="sxs-lookup"><span data-stu-id="64ec4-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="64ec4-132">如果您想啟用規範 SQL Server 儲存區的鏡像，請選取 [ **啟用 SQL server 儲存區鏡像** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="64ec4-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="64ec4-133">如果您選擇啟用規範 SQL Server 儲存區鏡像，請從 [ **規範 Sql server 儲存區鏡像**] 清單中選取儲存區和實例。</span><span class="sxs-lookup"><span data-stu-id="64ec4-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="64ec4-134">按一下 [新增] 定義新的 SQL Server 儲存區和選用執行個體。</span><span class="sxs-lookup"><span data-stu-id="64ec4-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="64ec4-135">如果您想自動容錯移轉規範 SQL Server 儲存區，請選取 [ **使用 SQL Server 鏡像見證啟用自動容錯移轉** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="64ec4-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="64ec4-136">如果您選擇啟用 SQL Server 儲存區鏡像見證以啟用自動容錯移轉，請從清單中選取儲存區和實例。</span><span class="sxs-lookup"><span data-stu-id="64ec4-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="64ec4-137">按一下 [新增] 定義見證儲存區的新 SQL Server 儲存區和選用執行個體。</span><span class="sxs-lookup"><span data-stu-id="64ec4-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="64ec4-138">如果選擇啟用規範，請從 [備份規範 SQL Server 儲存區] 清單中選取儲存區和執行個體。</span><span class="sxs-lookup"><span data-stu-id="64ec4-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="64ec4-139">按一下 [新增] 定義新的 SQL Server 儲存區和選用執行個體。</span><span class="sxs-lookup"><span data-stu-id="64ec4-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="64ec4-140">如果您想啟用規範 SQL Server 儲存區的鏡像，請選取 [ **啟用 SQL server 儲存區鏡像** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="64ec4-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="64ec4-141">如果您選擇啟用規範 SQL Server 儲存區鏡像，請從 [ **備份規範 Sql server 儲存區鏡像**] 清單中選取儲存區和實例。</span><span class="sxs-lookup"><span data-stu-id="64ec4-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="64ec4-142">按一下 [新增] 定義新的 SQL Server 儲存區和選用執行個體。</span><span class="sxs-lookup"><span data-stu-id="64ec4-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="64ec4-143">如果您想自動容錯移轉備份規範 SQL Server 儲存區，請選取 [ **使用 SQL Server 鏡像見證啟用自動容錯移轉** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="64ec4-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="64ec4-144">如果您選擇啟用 SQL Server 儲存區鏡像見證以啟用自動容錯移轉，請從清單中選取儲存區和實例。</span><span class="sxs-lookup"><span data-stu-id="64ec4-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="64ec4-145">按一下 [新增] 定義見證儲存區的新 SQL Server 儲存區和選用執行個體。</span><span class="sxs-lookup"><span data-stu-id="64ec4-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="64ec4-146">**檔存放區** 從清單中選取檔案存放區位置，或按一下 [ **新增** ] 建立新的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="64ec4-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
  <span data-ttu-id="64ec4-147">**確定**：接受並認可對話方塊的變更。</span><span class="sxs-lookup"><span data-stu-id="64ec4-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="64ec4-148">**取消**：捨棄變更，並關閉對話方塊。</span><span class="sxs-lookup"><span data-stu-id="64ec4-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="64ec4-149">**說明**：顯示此說明畫面。</span><span class="sxs-lookup"><span data-stu-id="64ec4-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="64ec4-150">另請參閱</span><span class="sxs-lookup"><span data-stu-id="64ec4-150">See also</span></span>

[<span data-ttu-id="64ec4-151">在商務用 Skype Server 2015 中規劃 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="64ec4-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="64ec4-152">將 Persistent Chat Server 新增至您的商務用 Skype Server 2015 拓撲</span><span class="sxs-lookup"><span data-stu-id="64ec4-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="64ec4-153">在商務用 Skype Server 2015 中設定 Persistent Chat Server 的高可用性和嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="64ec4-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

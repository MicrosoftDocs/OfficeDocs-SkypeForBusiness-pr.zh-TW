---
title: 移轉程序 - 詳細資料
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39560d69842c104c7db956418dabac9aa6d29d7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a><span data-ttu-id="407fe-102">移轉程序 - 詳細資料</span><span class="sxs-lookup"><span data-stu-id="407fe-102">Migration process - details</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="407fe-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="407fe-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="407fe-104">使用下列先決條件及詳細步驟，將 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天遷移至 Lync Server 2013、持續聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="407fe-104">Use the following prerequisites and detailed steps to migrate either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="prerequisites-for-migration"></a><span data-ttu-id="407fe-105">遷移的先決條件</span><span class="sxs-lookup"><span data-stu-id="407fe-105">Prerequisites for Migration</span></span>

<span data-ttu-id="407fe-106">在將 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天遷移至 Lync Server 2013、持續聊天伺服器前，請確定您已符合下列先決條件。</span><span class="sxs-lookup"><span data-stu-id="407fe-106">Be sure that you’ve met the following prerequisites before migrating either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

1.  <span data-ttu-id="407fe-107">部署至少一個 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="407fe-107">Deploy at least one Lync Server 2013 pool.</span></span> <span data-ttu-id="407fe-108">如果您有多個 Lync Server 2013 池，請決定將哪個 Lync Server 2013 池作為新 Lync Server 2013 持久性聊天伺服器池的主池。</span><span class="sxs-lookup"><span data-stu-id="407fe-108">If you have multiple Lync Server 2013 pools, decide which Lync Server 2013 pool will be the home pool for the new Lync Server 2013 Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="407fe-109">安裝 Lync Server 2013，持續聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="407fe-109">Install the Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="407fe-110">它將會是空白（無類別、會議室或增益集）。</span><span class="sxs-lookup"><span data-stu-id="407fe-110">It will be empty (no categories, rooms, or add-ins).</span></span> <span data-ttu-id="407fe-111">在您遷移舊版類別、會議室或增益集之前，您可以在 Lync Server 2013 （持久的聊天伺服器部署）中建立會議室、類別或增益集。</span><span class="sxs-lookup"><span data-stu-id="407fe-111">Before you migrate your legacy categories, rooms, or add-ins, you can create rooms, categories, or add-ins in your Lync Server 2013, Persistent Chat Server deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="407fe-112">請注意，這些新建立的專案可能會與您遷移的舊版專案發生衝突。</span><span class="sxs-lookup"><span data-stu-id="407fe-112">Be aware that these newly created items may conflict with legacy items that you migrate.</span></span> <span data-ttu-id="407fe-113">避免任何命名衝突;否則，當您遷移舊版資料時，會覆寫這些資料。</span><span class="sxs-lookup"><span data-stu-id="407fe-113">Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.</span></span>

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a><span data-ttu-id="407fe-114">準備來源資料以供遷移</span><span class="sxs-lookup"><span data-stu-id="407fe-114">Preparing the Source Data for Migration</span></span>

<span data-ttu-id="407fe-115">請執行下列步驟，以正確準備您的來來源資料以供遷移。</span><span class="sxs-lookup"><span data-stu-id="407fe-115">Perform the following steps to properly prepare your source data for migration.</span></span>

1.  <span data-ttu-id="407fe-116">針對 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天備份源資料庫。</span><span class="sxs-lookup"><span data-stu-id="407fe-116">Back up the source databases for either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span> <span data-ttu-id="407fe-117">如需有關備份 SQL Server 的詳細資訊，請參閱「備份概述（SQL Server <http://go.microsoft.com/fwlink/p/?linkid=254851>）」。</span><span class="sxs-lookup"><span data-stu-id="407fe-117">For details about backing up SQL Server, see "Backup Overview (SQL Server)" at <http://go.microsoft.com/fwlink/p/?linkid=254851>.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="407fe-118">Active Directory 網域服務應該是相同的。</span><span class="sxs-lookup"><span data-stu-id="407fe-118">Active Directory Domain Services should be the same.</span></span> <span data-ttu-id="407fe-119">做為遷移的條件，您無法在不同的部署（尤其是在不同的 Active Directory 林中）遷移到某個池。</span><span class="sxs-lookup"><span data-stu-id="407fe-119">As a condition for migration, you cannot migrate to a pool in a different deployment (specifically, in a different Active Directory forest).</span></span>

    
    </div>

2.  <span data-ttu-id="407fe-120">檢查您的 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天聊天室和類別設定。</span><span class="sxs-lookup"><span data-stu-id="407fe-120">Inspect your Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat chat rooms and category configuration.</span></span> <span data-ttu-id="407fe-121">您現有舊版部署中的類別、會議室或增益集的任何變更都將由群組聊天系統管理工具來完成。</span><span class="sxs-lookup"><span data-stu-id="407fe-121">Any changes to categories, rooms, or add-ins in your existing legacy deployment will be done by the Group Chat Admin Tool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="407fe-122">Lync Server 2013 中的類別、會議室或增益集的任何變更，都是由 Lync Server 的 [控制台] 或 [Windows PowerShell Cmdlet] 執行。</span><span class="sxs-lookup"><span data-stu-id="407fe-122">Any changes to categories, rooms, or add-ins in your Lync Server 2013, Persistent Chat Server deployment are performed by the Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

    
    </div>
    
    <span data-ttu-id="407fe-123">請依照下列步驟，為您的舊版系統做好遷移準備。</span><span class="sxs-lookup"><span data-stu-id="407fe-123">Follow these steps to prepare your legacy system for migration.</span></span>
    
    1.  <span data-ttu-id="407fe-124">永久聊天伺服器支援單一等級的類別，不像一組深階層的類別。</span><span class="sxs-lookup"><span data-stu-id="407fe-124">Persistent Chat Server supports a single level of categories, unlike a deep hierarchical set of categories.</span></span> <span data-ttu-id="407fe-125">遷移之後，子類別會以完整的父類別名稱作為首碼。</span><span class="sxs-lookup"><span data-stu-id="407fe-125">After migration, the subcategories are prefixed with full parent category names.</span></span> <span data-ttu-id="407fe-126">您可能會想要簡化並拼合現有的類別結構，讓產生的結構符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="407fe-126">You might want to simplify and flatten your existing category structure so that the resulting structure meets your requirements.</span></span>
    
    2.  <span data-ttu-id="407fe-127">驗證根類別的**管理員**。</span><span class="sxs-lookup"><span data-stu-id="407fe-127">Verify the **Managers** at the root Category.</span></span> <span data-ttu-id="407fe-128">如果此階層有任何管理員，則在遷移之後，這些使用者會被新增為系統**管理員所有的會議室**。</span><span class="sxs-lookup"><span data-stu-id="407fe-128">If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration.</span></span> <span data-ttu-id="407fe-129">如果這不是貴組織的需求，您必須從 root 類別中移除這些管理員。</span><span class="sxs-lookup"><span data-stu-id="407fe-129">If this is not a requirement for your organization, you need to remove these Managers from the root Category.</span></span>
    
    3.  <span data-ttu-id="407fe-130">確認會議室名稱的長度。</span><span class="sxs-lookup"><span data-stu-id="407fe-130">Verify the length of room names.</span></span> <span data-ttu-id="407fe-131">遷移之後，由於簡化的類別結構，如果該會議室存在於子類別底下，則其會以完整的父類別名稱作為首碼。</span><span class="sxs-lookup"><span data-stu-id="407fe-131">After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names.</span></span> <span data-ttu-id="407fe-132">命名限制是256個字元，包括父類別名稱。</span><span class="sxs-lookup"><span data-stu-id="407fe-132">The naming limit is 256 characters, including parent category names.</span></span> <span data-ttu-id="407fe-133">您必須確認會議室名稱的長度，而且可能會縮短長度（如果太長的話）。</span><span class="sxs-lookup"><span data-stu-id="407fe-133">You must verify the length of the room names and possibly shorten the length, if they are too long.</span></span>
    
    4.  <span data-ttu-id="407fe-134">在 Lync Server 2013 中，如果 [類別**邀請**] 設定設為 true，您可以選擇 [true] 或 [false]，以在該類別下的會議室進行邀請。</span><span class="sxs-lookup"><span data-stu-id="407fe-134">In Lync Server 2013, if the category **invitations** settings are set to true, you can choose true or false for invitations to rooms under that category.</span></span> <span data-ttu-id="407fe-135">不過，如果 [類別邀請] 設定設為 [false]，該類別下的會議室會關閉邀請。</span><span class="sxs-lookup"><span data-stu-id="407fe-135">However if the category invitations settings are set to false, rooms under that category have invitations turned off.</span></span> <span data-ttu-id="407fe-136">在遷移之前，您必須先重設舊版 Lync 伺服器群組聊天伺服器版本中的邀請設定（如果您想要在特定類別中存在會議室）。</span><span class="sxs-lookup"><span data-stu-id="407fe-136">Before migration, you must reset the invitation settings in your legacy Lync Server Group Chat Server version, if you want room(s) to exist under a specific category.</span></span> <span data-ttu-id="407fe-137">否則，在遷移期間，Lync Server 2013 會顯示警告，並將房間設定為預設值 false。</span><span class="sxs-lookup"><span data-stu-id="407fe-137">Otherwise, during migration, Lync Server 2013 displays warnings and sets rooms to the default value of false.</span></span>
    
    5.  <span data-ttu-id="407fe-138">如果您使用的是聊天室中的檔案，您必須在遷移之後，將檔案手動儲存至新的持久聊天檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="407fe-138">If you used files in chat rooms, you must XCOPY the files manually to the new Persistent Chat file store after migration.</span></span> <span data-ttu-id="407fe-139">工具不會執行此動作。</span><span class="sxs-lookup"><span data-stu-id="407fe-139">The tools don’t do this.</span></span>
    
    6.  <span data-ttu-id="407fe-140">如果您有同盟使用者和聯盟使用者的聊天室，請注意持續聊天伺服器不支援同盟。</span><span class="sxs-lookup"><span data-stu-id="407fe-140">If you had federated users and rooms with federated users, be aware that Persistent Chat Server does not support federation.</span></span> <span data-ttu-id="407fe-141">將會遷移含聯盟使用者的聊天室;不過，使用者本身將無法存取內容，因為不支援聯盟存取。</span><span class="sxs-lookup"><span data-stu-id="407fe-141">Rooms with federated users will be migrated; however, the users themselves won’t be able to access the content, because federated access is not supported.</span></span>
    
    7.  <span data-ttu-id="407fe-142">找出您不想要遷移的那些聊天室，並將它們標示為 [已停用]。</span><span class="sxs-lookup"><span data-stu-id="407fe-142">Identify those rooms that you do not want to migrate, and mark them as disabled.</span></span>
    
    8.  <span data-ttu-id="407fe-143">找出您要將聊天室內容移植到哪個日期之後。</span><span class="sxs-lookup"><span data-stu-id="407fe-143">Identify the date beyond which you want to migrate the chat room content.</span></span> <span data-ttu-id="407fe-144">例如，您可能不想要在2010年1月1日之前遷移郵件，因為這些訊息可能已過時或與遷移無關。</span><span class="sxs-lookup"><span data-stu-id="407fe-144">For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.</span></span>

</div>

<div>

## <a name="performing-the-migration"></a><span data-ttu-id="407fe-145">執行遷移</span><span class="sxs-lookup"><span data-stu-id="407fe-145">Performing the Migration</span></span>

<span data-ttu-id="407fe-146">請執行下列步驟以遷移舊版群組聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="407fe-146">Perform the following steps to migrate your legacy Group Chat Server.</span></span>

1.  <span data-ttu-id="407fe-147">關閉 Lync Server 2010、群組聊天、Office 通訊伺服器 2007 R2 群組聊天或 Lync Server 2013、持續聊天伺服器服務。</span><span class="sxs-lookup"><span data-stu-id="407fe-147">Shut down the Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat or Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="407fe-148">所有服務都必須停止，所以請在有足夠的停機時間時，進行規劃以進行這項作業。</span><span class="sxs-lookup"><span data-stu-id="407fe-148">All services must be stopped, so plan to do this at a time when there is enough downtime.</span></span> <span data-ttu-id="407fe-149">如先前所述，請務必備份您目前的 [群組聊天] 資料庫。</span><span class="sxs-lookup"><span data-stu-id="407fe-149">As previously described, make sure to back up your current Group Chat database.</span></span>

2.  <span data-ttu-id="407fe-150">以永久聊天管理員 RBAC 角色（CsPersistentChatAdministrator）的成員身分執行 Windows PowerShell **Export CsPersistentChatData** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="407fe-150">Run the Windows PowerShell **Export-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="407fe-151">如需匯出/匯入 Cmdlet 的詳細資料，請參閱[在 Lync server 2013 中使用 Windows PowerShell Cmdlet 來疑難排解永久聊天伺服器](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)設定。</span><span class="sxs-lookup"><span data-stu-id="407fe-151">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>
    
    <span data-ttu-id="407fe-152">檢查匯出的內容。</span><span class="sxs-lookup"><span data-stu-id="407fe-152">Inspect the exported contents.</span></span>

3.  <span data-ttu-id="407fe-153">在您準備好要匯入之前，請先關閉 Lync Server 2013、持續聊天伺服器服務。</span><span class="sxs-lookup"><span data-stu-id="407fe-153">Before you’re ready to import, shut down Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="407fe-154">所有服務都必須停止，所以請在有足夠的停機時間時，進行規劃以進行這項作業。</span><span class="sxs-lookup"><span data-stu-id="407fe-154">All services need to be stopped, so plan to do this at a time when there is enough downtime.</span></span>

4.  <span data-ttu-id="407fe-155">如果您已在 Lync Server 2013 部署中建立了任何類別、會議室或增益集，請執行持久聊天資料庫的備份。</span><span class="sxs-lookup"><span data-stu-id="407fe-155">Perform a backup of the Persistent Chat database if you had created any categories, rooms, or add-ins in your Lync Server 2013 deployment before the migration.</span></span> <span data-ttu-id="407fe-156">匯出/匯入程式將能將舊版資料合併到 Lync Server 2013 部署，但如果不小心覆寫內容，您就會想要備份資料庫（例如，如果命名衝突仍然存在）。</span><span class="sxs-lookup"><span data-stu-id="407fe-156">The export/import process will be able to merge the legacy data into the Lync Server 2013 deployment, but you’ll want to back up the database in case that content is inadvertently overwritten (for example, if naming conflicts still exist).</span></span>

5.  <span data-ttu-id="407fe-157">使用 [ **WhatIf** ] 命令執行 Windows PowerShell **Import CsPersistentChatData** Cmdlet （匯入工具），以使用已遷移的資料來填入持久性聊天伺服器池的後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="407fe-157">Run the Windows PowerShell **Import-CsPersistentChatData** cmdlet (import tool), with a **WhatIf** command to populate the Back End Server of the Persistent Chat Server pool with migrated data.</span></span> <span data-ttu-id="407fe-158">在處理常式中會進行一些轉換，以適應簡化的管理模型。</span><span class="sxs-lookup"><span data-stu-id="407fe-158">Some conversions happen in the process to accommodate the simplified administration model.</span></span> <span data-ttu-id="407fe-159">修正所出現的任何錯誤或警告。</span><span class="sxs-lookup"><span data-stu-id="407fe-159">Fix any errors or warnings that appear.</span></span>

6.  <span data-ttu-id="407fe-160">以永久聊天系統管理員 RBAC 角色（CsPersistentChatAdministrator）的成員身分執行永久聊天伺服器 Windows PowerShell 匯**入-CsPersistentChatData** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="407fe-160">Run the Persistent Chat Server Windows PowerShell **Import-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="407fe-161">如需匯出/匯入 Cmdlet 的詳細資料，請參閱[在 Lync server 2013 中使用 Windows PowerShell Cmdlet 來疑難排解永久聊天伺服器](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)設定。</span><span class="sxs-lookup"><span data-stu-id="407fe-161">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>

7.  <span data-ttu-id="407fe-162">您必須將所有上傳的檔案（整個資料夾） XCOPY 為新的 Lync Server 2013、永久聊天檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="407fe-162">You must XCOPY all uploaded files (the entire folder) to the new Lync Server 2013, Persistent Chat file store.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="407fe-163">Lync 2013 （用戶端）不支援上傳或查看聊天室中的檔案。</span><span class="sxs-lookup"><span data-stu-id="407fe-163">The Lync 2013 (client) does not support uploading or viewing files in chat rooms.</span></span> <span data-ttu-id="407fe-164">您仍然可以使用舊版用戶端來張貼及查看聊天室中的檔案。</span><span class="sxs-lookup"><span data-stu-id="407fe-164">You can still use the legacy client to post and view files in the room.</span></span>

    
    </div>

8.  <span data-ttu-id="407fe-165">將 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天查閱伺服器 URI 移植至 Lync Server 2013，持續聊天伺服器連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="407fe-165">Port the Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat Lookup Server URI to the Lync Server 2013, Persistent Chat Server contact object.</span></span> <span data-ttu-id="407fe-166">如果您的 Lync 2010 群組聊天或 Office Communicator 2007 R2 群組的聊天用戶端需要連線到最新的 Lync 2013、持續聊天（用戶端），而不需任何用戶端設定變更，就必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="407fe-166">The following steps are required if either your Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat clients need to connect to the latest Lync 2013, Persistent Chat (client) after migration without any client-side configuration changes:</span></span>
    
      - <span data-ttu-id="407fe-167">刪除 ocschat@\<功能變數名稱稱\>[.com 查閱伺服器使用者帳戶]。</span><span class="sxs-lookup"><span data-stu-id="407fe-167">Delete the ocschat@\<domainName\>.com Lookup Server user account.</span></span> <span data-ttu-id="407fe-168">這是用來指向 Lync Server 2010 中的查閱服務，群組聊天。</span><span class="sxs-lookup"><span data-stu-id="407fe-168">This was used to point to the Lookup Service in Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="407fe-169">您可以在稍後卸載該池並移除信任的專案。</span><span class="sxs-lookup"><span data-stu-id="407fe-169">You can uninstall the pool and remove trusted entries later.</span></span>
    
      - <span data-ttu-id="407fe-170">若要建立舊版端點（持久聊天伺服器連絡人物件），請執行具有相同 SIP URI 的 Windows PowerShell Cmdlet （ **CsPersistentChatEndpoint**），讓舊版用戶端能在服務重新開機時有效運作。</span><span class="sxs-lookup"><span data-stu-id="407fe-170">Create a legacy endpoint (Persistent Chat Server contact object) by running the Windows PowerShell cmdlet, **New-CsPersistentChatEndpoint**, with the identical SIP URI so that the legacy client will work effectively when the service is restarted.</span></span>
    
    <span data-ttu-id="407fe-171">強制執行的遷移程式已完成。</span><span class="sxs-lookup"><span data-stu-id="407fe-171">The mandatory migration process is complete at this point.</span></span> <span data-ttu-id="407fe-172">Lync 2010 群組聊天（用戶端）或 Office Communicator 2007 R2 群組聊天（用戶端）現在可以透明地連線到新的持續聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="407fe-172">Lync 2010 Group Chat (clients) or Office Communicator 2007 R2 Group Chat (clients) can connect to the new Persistent Chat Server pool now, transparently.</span></span>
    
    <span data-ttu-id="407fe-173">針對 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天，請遵循這些額外的解除授權步驟。</span><span class="sxs-lookup"><span data-stu-id="407fe-173">Follow these additional decommissioning steps for Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span>

9.  <span data-ttu-id="407fe-174">開啟新的持續聊天伺服器池中的所有電腦，以啟動持續聊天伺服器服務。</span><span class="sxs-lookup"><span data-stu-id="407fe-174">Start the Persistent Chat Server services by turning on all computers in the new Persistent Chat Server pool.</span></span>

10. <span data-ttu-id="407fe-175">使用 Lync Server [控制台] 和 [Windows PowerShell Cmdlet] 驗證資料是否已順利遷移。</span><span class="sxs-lookup"><span data-stu-id="407fe-175">Use the Lync Server Control Panel and Windows PowerShell cmdlets to verify that the data has migrated successfully.</span></span>

11. <span data-ttu-id="407fe-176">從群組聊天伺服器池中的電腦卸載 Lync 2010 群組聊天或 Office Communicator 2007 R2 群組聊天。</span><span class="sxs-lookup"><span data-stu-id="407fe-176">Uninstall Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat from the computers in the Group Chat Server pool.</span></span>

12. <span data-ttu-id="407fe-177">使用 Windows PowerShell Cmdlet 刪除受信任的應用程式和受信任的應用程式池。</span><span class="sxs-lookup"><span data-stu-id="407fe-177">Delete the trusted application and trusted application pool using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="407fe-178">此選項會從 [中央管理] 存放區及與 Active Directory 中相關聯的信任服務專案（TSEs）刪除這些專案。</span><span class="sxs-lookup"><span data-stu-id="407fe-178">This deletes these items from the Central Management store and the associated Trusted Service Entries (TSEs) from the Active Directory.</span></span> <span data-ttu-id="407fe-179">或者，此步驟的運作方式是使用 [拓撲建立器] （信任的應用程式/池也有一個專用節點）。</span><span class="sxs-lookup"><span data-stu-id="407fe-179">Alternatively, this step works by using the Topology Builder (the trusted applications/pools have a dedicated node there, also).</span></span>

13. <span data-ttu-id="407fe-180">您現在可以透過新的用戶端開始啟用持續聊天伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="407fe-180">You can now begin to enable Persistent Chat Server functionality through the new clients.</span></span> <span data-ttu-id="407fe-181">如需啟用持久聊天伺服器的詳細資料，請參閱[在 Lync server 2013 中部署持久聊天伺服器](lync-server-2013-deploying-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="407fe-181">For details about enabling Persistent Chat Server, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="407fe-182">Lync Server 2013 支援多個持續聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="407fe-182">Lync Server 2013 supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="407fe-183">不過，我們支援將 Lync 2010 群組聊天或 Office 通訊伺服器 2007 R2&nbsp;群組聊天池遷移至單一 Lync server 2013、持續聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="407fe-183">However, we support migrating a Lync 2010 Group Chat or Office Communications Server 2007 R2&nbsp;Group Chat pool to a single Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="407fe-184">您可以在您的部署中新增其他新的持久性聊天伺服器池，以符合法規需求（例如，將資料保留在指定的地理位置）。</span><span class="sxs-lookup"><span data-stu-id="407fe-184">You can add additional new Persistent Chat Server pools in your deployment to meet the regulatory needs (for example, keeping data within a given geography).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


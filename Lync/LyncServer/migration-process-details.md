---
title: 遷移程式-詳細資料
description: 遷移程式-詳細資料。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8ecc5f23a328aef7cc65ad84e28dbb629d44b91
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569579"
---
# <a name="migration-process---details"></a><span data-ttu-id="e887b-103">遷移程式-詳細資料</span><span class="sxs-lookup"><span data-stu-id="e887b-103">Migration process - details</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e887b-104">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e887b-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e887b-105">使用下列必要條件和詳細步驟，將 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天遷移至 Lync Server 2013、Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="e887b-105">Use the following prerequisites and detailed steps to migrate either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="prerequisites-for-migration"></a><span data-ttu-id="e887b-106">遷移的必要條件</span><span class="sxs-lookup"><span data-stu-id="e887b-106">Prerequisites for Migration</span></span>

<span data-ttu-id="e887b-107">在將 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天遷移至 Lync Server 2013、Persistent Chat Server 之前，請確定您已符合下列必要條件。</span><span class="sxs-lookup"><span data-stu-id="e887b-107">Be sure that you’ve met the following prerequisites before migrating either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

1.  <span data-ttu-id="e887b-108">部署至少一個 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="e887b-108">Deploy at least one Lync Server 2013 pool.</span></span> <span data-ttu-id="e887b-109">如果您有多個 Lync Server 2013 集區，請決定哪個 Lync Server 2013 集區將會成為新 Lync Server 2013 Persistent Chat Server 集區的主集區。</span><span class="sxs-lookup"><span data-stu-id="e887b-109">If you have multiple Lync Server 2013 pools, decide which Lync Server 2013 pool will be the home pool for the new Lync Server 2013 Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="e887b-110">安裝 Lync Server 2013，Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="e887b-110">Install the Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="e887b-111"> (無類別、會議室或增益集) ，它將會是空的。</span><span class="sxs-lookup"><span data-stu-id="e887b-111">It will be empty (no categories, rooms, or add-ins).</span></span> <span data-ttu-id="e887b-112">在遷移舊版類別、聊天室或增益集之前，您可以在 Lync Server 2013 中建立聊天室、類別或增益集。</span><span class="sxs-lookup"><span data-stu-id="e887b-112">Before you migrate your legacy categories, rooms, or add-ins, you can create rooms, categories, or add-ins in your Lync Server 2013, Persistent Chat Server deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e887b-113">請注意，這些新建立的專案可能會與您遷移的舊版專案產生衝突。</span><span class="sxs-lookup"><span data-stu-id="e887b-113">Be aware that these newly created items may conflict with legacy items that you migrate.</span></span> <span data-ttu-id="e887b-114">避免任何命名衝突;否則，在遷移舊版資料時，將會覆寫這些資料。</span><span class="sxs-lookup"><span data-stu-id="e887b-114">Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.</span></span>

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a><span data-ttu-id="e887b-115">準備要遷移的來來源資料</span><span class="sxs-lookup"><span data-stu-id="e887b-115">Preparing the Source Data for Migration</span></span>

<span data-ttu-id="e887b-116">請執行下列步驟，正確準備您的來來源資料以進行遷移。</span><span class="sxs-lookup"><span data-stu-id="e887b-116">Perform the following steps to properly prepare your source data for migration.</span></span>

1.  <span data-ttu-id="e887b-117">備份 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天的來源資料庫。</span><span class="sxs-lookup"><span data-stu-id="e887b-117">Back up the source databases for either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span> <span data-ttu-id="e887b-118">如需備份 SQL Server 的詳細資訊，請參閱《備份一覽 (SQL Server) 」 <https://go.microsoft.com/fwlink/p/?linkid=254851> 。</span><span class="sxs-lookup"><span data-stu-id="e887b-118">For details about backing up SQL Server, see "Backup Overview (SQL Server)" at <https://go.microsoft.com/fwlink/p/?linkid=254851>.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e887b-119">Active Directory 網域服務應該相同。</span><span class="sxs-lookup"><span data-stu-id="e887b-119">Active Directory Domain Services should be the same.</span></span> <span data-ttu-id="e887b-120">作為遷移的條件，您無法在不同的 Active Directory 樹系) 中，以不同的部署 (方式遷移至集區。</span><span class="sxs-lookup"><span data-stu-id="e887b-120">As a condition for migration, you cannot migrate to a pool in a different deployment (specifically, in a different Active Directory forest).</span></span>

    
    </div>

2.  <span data-ttu-id="e887b-121">檢查您的 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天聊天室和類別設定。</span><span class="sxs-lookup"><span data-stu-id="e887b-121">Inspect your Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat chat rooms and category configuration.</span></span> <span data-ttu-id="e887b-122">您現有舊版部署中的類別、聊天室或增益集的任何變更，都是由 Group Chat 系統管理工具進行。</span><span class="sxs-lookup"><span data-stu-id="e887b-122">Any changes to categories, rooms, or add-ins in your existing legacy deployment will be done by the Group Chat Admin Tool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e887b-123">Lync server 2013 中的類別、會議室或增益集的任何變更，都是由 Lync Server 控制台或 Windows PowerShell Cmdlet 執行。</span><span class="sxs-lookup"><span data-stu-id="e887b-123">Any changes to categories, rooms, or add-ins in your Lync Server 2013, Persistent Chat Server deployment are performed by the Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

    
    </div>
    
    <span data-ttu-id="e887b-124">請遵循下列步驟，為遷移準備舊版系統。</span><span class="sxs-lookup"><span data-stu-id="e887b-124">Follow these steps to prepare your legacy system for migration.</span></span>
    
    1.  <span data-ttu-id="e887b-125">Persistent Chat Server 支援單一等級的類別，不同于一組 deep 階層的類別。</span><span class="sxs-lookup"><span data-stu-id="e887b-125">Persistent Chat Server supports a single level of categories, unlike a deep hierarchical set of categories.</span></span> <span data-ttu-id="e887b-126">遷移後，子類別會以完整的父類別名稱做為首碼。</span><span class="sxs-lookup"><span data-stu-id="e887b-126">After migration, the subcategories are prefixed with full parent category names.</span></span> <span data-ttu-id="e887b-127">您可能想要簡化及展隨現有的類別結構，讓產生的結構符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="e887b-127">You might want to simplify and flatten your existing category structure so that the resulting structure meets your requirements.</span></span>
    
    2.  <span data-ttu-id="e887b-128">驗證根類別的 **管理員** 。</span><span class="sxs-lookup"><span data-stu-id="e887b-128">Verify the **Managers** at the root Category.</span></span> <span data-ttu-id="e887b-129">如果此層級有任何主管，則遷移後，系統會將這些使用者新增為 **管理員** 。</span><span class="sxs-lookup"><span data-stu-id="e887b-129">If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration.</span></span> <span data-ttu-id="e887b-130">如果這不是組織的必要條件，您必須從 root 類別中移除這些管理員。</span><span class="sxs-lookup"><span data-stu-id="e887b-130">If this is not a requirement for your organization, you need to remove these Managers from the root Category.</span></span>
    
    3.  <span data-ttu-id="e887b-131">驗證會議室名稱的長度。</span><span class="sxs-lookup"><span data-stu-id="e887b-131">Verify the length of room names.</span></span> <span data-ttu-id="e887b-132">遷移後，由於簡化的類別結構，如果子類別的聊天室存在，則會以完整的父類別名稱做為加上首碼。</span><span class="sxs-lookup"><span data-stu-id="e887b-132">After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names.</span></span> <span data-ttu-id="e887b-133">命名限制為256個字元，包含父類別名稱。</span><span class="sxs-lookup"><span data-stu-id="e887b-133">The naming limit is 256 characters, including parent category names.</span></span> <span data-ttu-id="e887b-134">您必須確認會議室名稱的長度，而且可能會縮短長度（如果這些名稱過長）。</span><span class="sxs-lookup"><span data-stu-id="e887b-134">You must verify the length of the room names and possibly shorten the length, if they are too long.</span></span>
    
    4.  <span data-ttu-id="e887b-135">在 [Lync Server 2013] 中，如果類別 **邀請** 設定設定為 true，您可以選擇 true 或 false，以在該類別下的聊天室邀請。</span><span class="sxs-lookup"><span data-stu-id="e887b-135">In Lync Server 2013, if the category **invitations** settings are set to true, you can choose true or false for invitations to rooms under that category.</span></span> <span data-ttu-id="e887b-136">不過，如果類別邀請設定設定為 false，則該類別下的會議室會關閉邀請。</span><span class="sxs-lookup"><span data-stu-id="e887b-136">However if the category invitations settings are set to false, rooms under that category have invitations turned off.</span></span> <span data-ttu-id="e887b-137">在遷移之前，您必須重設舊版 Lync Server 群組聊天伺服器版本中的邀請設定（如果您想要讓 () 在特定類別下存在）。</span><span class="sxs-lookup"><span data-stu-id="e887b-137">Before migration, you must reset the invitation settings in your legacy Lync Server Group Chat Server version, if you want room(s) to exist under a specific category.</span></span> <span data-ttu-id="e887b-138">否則，在遷移期間，Lync Server 2013 會顯示警告，並將聊天室的預設值設為 false。</span><span class="sxs-lookup"><span data-stu-id="e887b-138">Otherwise, during migration, Lync Server 2013 displays warnings and sets rooms to the default value of false.</span></span>
    
    5.  <span data-ttu-id="e887b-139">如果您使用聊天室中的檔案，您必須在遷移後，手動將檔案以 XCOPY 方式新增至新的持久聊天檔存放區。</span><span class="sxs-lookup"><span data-stu-id="e887b-139">If you used files in chat rooms, you must XCOPY the files manually to the new Persistent Chat file store after migration.</span></span> <span data-ttu-id="e887b-140">工具不會這麼做。</span><span class="sxs-lookup"><span data-stu-id="e887b-140">The tools don’t do this.</span></span>
    
    6.  <span data-ttu-id="e887b-141">如果您有同盟使用者與同盟使用者和聊天室，請注意 Persistent Chat Server 不支援同盟。</span><span class="sxs-lookup"><span data-stu-id="e887b-141">If you had federated users and rooms with federated users, be aware that Persistent Chat Server does not support federation.</span></span> <span data-ttu-id="e887b-142">會遷移具有同盟使用者的聊天室;不過，由於不支援同盟存取，使用者本身將無法存取內容。</span><span class="sxs-lookup"><span data-stu-id="e887b-142">Rooms with federated users will be migrated; however, the users themselves won’t be able to access the content, because federated access is not supported.</span></span>
    
    7.  <span data-ttu-id="e887b-143">識別您不想遷移的聊天室，將其標記為 [已停用]。</span><span class="sxs-lookup"><span data-stu-id="e887b-143">Identify those rooms that you do not want to migrate, and mark them as disabled.</span></span>
    
    8.  <span data-ttu-id="e887b-144">識別您想要遷移聊天室內容的日期以外的日期。</span><span class="sxs-lookup"><span data-stu-id="e887b-144">Identify the date beyond which you want to migrate the chat room content.</span></span> <span data-ttu-id="e887b-145">例如，您可能不想要遷移超過2010年1月1日的郵件，因為這些郵件可能已過時，或與遷移無關。</span><span class="sxs-lookup"><span data-stu-id="e887b-145">For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.</span></span>

</div>

<div>

## <a name="performing-the-migration"></a><span data-ttu-id="e887b-146">執行遷移</span><span class="sxs-lookup"><span data-stu-id="e887b-146">Performing the Migration</span></span>

<span data-ttu-id="e887b-147">請執行下列步驟，以遷移舊版群組聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="e887b-147">Perform the following steps to migrate your legacy Group Chat Server.</span></span>

1.  <span data-ttu-id="e887b-148">關閉 Lync Server 2010、群組聊天、Office 通訊伺服器 2007 R2 群組聊天或 Lync Server 2013、Persistent Chat Server 服務。</span><span class="sxs-lookup"><span data-stu-id="e887b-148">Shut down the Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat or Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="e887b-149">所有服務都必須停止，所以計畫在有足夠的停機時間時執行此作業。</span><span class="sxs-lookup"><span data-stu-id="e887b-149">All services must be stopped, so plan to do this at a time when there is enough downtime.</span></span> <span data-ttu-id="e887b-150">如先前所述，請務必備份目前的群組聊天資料庫。</span><span class="sxs-lookup"><span data-stu-id="e887b-150">As previously described, make sure to back up your current Group Chat database.</span></span>

2.  <span data-ttu-id="e887b-151">以 Persistent Chat 系統管理員 RBAC 角色的成員身分 (CsPersistentChatAdministrator) 執行 Windows PowerShell **Export-CsPersistentChatData** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e887b-151">Run the Windows PowerShell **Export-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="e887b-152">如需匯出/匯入 Cmdlet 的詳細資訊，請參閱 [在 Lync server 2013 中使用 Windows PowerShell Cmdlet 疑難排解 Persistent Chat Server](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)設定。</span><span class="sxs-lookup"><span data-stu-id="e887b-152">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>
    
    <span data-ttu-id="e887b-153">檢查匯出的內容。</span><span class="sxs-lookup"><span data-stu-id="e887b-153">Inspect the exported contents.</span></span>

3.  <span data-ttu-id="e887b-154">在您準備匯入之前，請關閉 Lync Server 2013，Persistent Chat Server 服務。</span><span class="sxs-lookup"><span data-stu-id="e887b-154">Before you’re ready to import, shut down Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="e887b-155">所有服務都必須停止，所以規劃若有足夠的停機時間，請執行此動作。</span><span class="sxs-lookup"><span data-stu-id="e887b-155">All services need to be stopped, so plan to do this at a time when there is enough downtime.</span></span>

4.  <span data-ttu-id="e887b-156">在遷移之前，如果您已在 Lync Server 2013 部署中建立任何類別、聊天室或增益集，請執行 Persistent Chat 資料庫的備份。</span><span class="sxs-lookup"><span data-stu-id="e887b-156">Perform a backup of the Persistent Chat database if you had created any categories, rooms, or add-ins in your Lync Server 2013 deployment before the migration.</span></span> <span data-ttu-id="e887b-157">匯出/匯入程式可將舊版資料合併至 Lync Server 2013 部署，但是您會想要備份資料庫，以防無意中覆寫內容 (例如，如果仍然存在命名衝突) 。</span><span class="sxs-lookup"><span data-stu-id="e887b-157">The export/import process will be able to merge the legacy data into the Lync Server 2013 deployment, but you’ll want to back up the database in case that content is inadvertently overwritten (for example, if naming conflicts still exist).</span></span>

5.  <span data-ttu-id="e887b-158">執行 Windows PowerShell **Import-CsPersistentChatData** Cmdlet (Import tool) ，使用 **WhatIf** 命令，以使用已遷移的資料填入 Persistent Chat Server 集區的後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="e887b-158">Run the Windows PowerShell **Import-CsPersistentChatData** cmdlet (import tool), with a **WhatIf** command to populate the Back End Server of the Persistent Chat Server pool with migrated data.</span></span> <span data-ttu-id="e887b-159">在處理過程中會進行部分轉換，以容納簡化的管理模型。</span><span class="sxs-lookup"><span data-stu-id="e887b-159">Some conversions happen in the process to accommodate the simplified administration model.</span></span> <span data-ttu-id="e887b-160">修正出現的任何錯誤或警告。</span><span class="sxs-lookup"><span data-stu-id="e887b-160">Fix any errors or warnings that appear.</span></span>

6.  <span data-ttu-id="e887b-161">執行 Persistent Chat Server Windows PowerShell **Import-CsPersistentChatData** Cmdlet 作為 Persistent CHAT administrator RBAC role 的成員 (CsPersistentChatAdministrator) 。</span><span class="sxs-lookup"><span data-stu-id="e887b-161">Run the Persistent Chat Server Windows PowerShell **Import-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="e887b-162">如需匯出/匯入 Cmdlet 的詳細資訊，請參閱 [在 Lync server 2013 中使用 Windows PowerShell Cmdlet 疑難排解 Persistent Chat Server](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)設定。</span><span class="sxs-lookup"><span data-stu-id="e887b-162">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>

7.  <span data-ttu-id="e887b-163">您必須將所有上傳的檔案 (整個資料夾中) 新增至新的 Lync Server 2013，Persistent Chat file store。</span><span class="sxs-lookup"><span data-stu-id="e887b-163">You must XCOPY all uploaded files (the entire folder) to the new Lync Server 2013, Persistent Chat file store.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e887b-164">Lync 2013 (用戶端) 不支援上傳或查看聊天室中的檔案。</span><span class="sxs-lookup"><span data-stu-id="e887b-164">The Lync 2013 (client) does not support uploading or viewing files in chat rooms.</span></span> <span data-ttu-id="e887b-165">您仍然可以使用舊版用戶端來開機自檢及查看聊天室中的檔案。</span><span class="sxs-lookup"><span data-stu-id="e887b-165">You can still use the legacy client to post and view files in the room.</span></span>

    
    </div>

8.  <span data-ttu-id="e887b-166">Port the Lync Server 2010，Group Chat 或 Office 通訊伺服器 2007 R2 Group Chat Lookup Server URI 至 Lync Server 2013，Persistent Chat Server contact 物件。</span><span class="sxs-lookup"><span data-stu-id="e887b-166">Port the Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat Lookup Server URI to the Lync Server 2013, Persistent Chat Server contact object.</span></span> <span data-ttu-id="e887b-167">如果您的 Lync 2010 群組聊天或 Office Communicator 2007 R2 群組聊天用戶端需要連線至最新的 Lync 2013、Persistent Chat (用戶端) 不需要任何用戶端設定變更，則需要下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e887b-167">The following steps are required if either your Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat clients need to connect to the latest Lync 2013, Persistent Chat (client) after migration without any client-side configuration changes:</span></span>
    
      - <span data-ttu-id="e887b-168">刪除 ocschat@ \<domainName\> .Com 查閱伺服器使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="e887b-168">Delete the ocschat@\<domainName\>.com Lookup Server user account.</span></span> <span data-ttu-id="e887b-169">這是用來指向 Lync Server 2010，Group Chat 中的查閱服務。</span><span class="sxs-lookup"><span data-stu-id="e887b-169">This was used to point to the Lookup Service in Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="e887b-170">您可以在稍後卸載集區和移除信任的專案。</span><span class="sxs-lookup"><span data-stu-id="e887b-170">You can uninstall the pool and remove trusted entries later.</span></span>
    
      - <span data-ttu-id="e887b-171">使用相同的 SIP URI 來執行 Windows PowerShell Cmdlet **New-CsPersistentChatEndpoint**，以建立舊版端點 (Persistent Chat Server contact 物件) ，如此一來，舊版用戶端才能有效地在服務重新開機時運作。</span><span class="sxs-lookup"><span data-stu-id="e887b-171">Create a legacy endpoint (Persistent Chat Server contact object) by running the Windows PowerShell cmdlet, **New-CsPersistentChatEndpoint**, with the identical SIP URI so that the legacy client will work effectively when the service is restarted.</span></span>
    
    <span data-ttu-id="e887b-172">強制執行的遷移程式已完成。</span><span class="sxs-lookup"><span data-stu-id="e887b-172">The mandatory migration process is complete at this point.</span></span> <span data-ttu-id="e887b-173">Lync 2010 Group Chat (用戶端) 或 Office Communicator 2007 R2 Group Chat (用戶端) 可以立即連線到新的 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="e887b-173">Lync 2010 Group Chat (clients) or Office Communicator 2007 R2 Group Chat (clients) can connect to the new Persistent Chat Server pool now, transparently.</span></span>
    
    <span data-ttu-id="e887b-174">請遵循下列有關 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天的額外解除的步驟。</span><span class="sxs-lookup"><span data-stu-id="e887b-174">Follow these additional decommissioning steps for Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span>

9.  <span data-ttu-id="e887b-175">開啟新的 Persistent Chat Server 集區中的所有電腦，以啟動 Persistent Chat Server 服務。</span><span class="sxs-lookup"><span data-stu-id="e887b-175">Start the Persistent Chat Server services by turning on all computers in the new Persistent Chat Server pool.</span></span>

10. <span data-ttu-id="e887b-176">使用 Lync Server 控制台和 Windows PowerShell Cmdlet，確認資料已成功遷移。</span><span class="sxs-lookup"><span data-stu-id="e887b-176">Use the Lync Server Control Panel and Windows PowerShell cmdlets to verify that the data has migrated successfully.</span></span>

11. <span data-ttu-id="e887b-177">從群組聊天伺服器集區中的電腦卸載 Lync 2010 群組聊天或 Office Communicator 2007 R2 群組聊天。</span><span class="sxs-lookup"><span data-stu-id="e887b-177">Uninstall Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat from the computers in the Group Chat Server pool.</span></span>

12. <span data-ttu-id="e887b-178">使用 Windows PowerShell Cmdlet 刪除受信任的應用程式和信任的應用程式集區。</span><span class="sxs-lookup"><span data-stu-id="e887b-178">Delete the trusted application and trusted application pool using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="e887b-179">這會從中央管理存放區中刪除這些專案，以及從 Active Directory (TSEs) 相關聯的信任服務專案。</span><span class="sxs-lookup"><span data-stu-id="e887b-179">This deletes these items from the Central Management store and the associated Trusted Service Entries (TSEs) from the Active Directory.</span></span> <span data-ttu-id="e887b-180">或者，此步驟的運作方式是使用拓撲產生器 (信任的應用程式/集區有專用的節點，也就是) 。</span><span class="sxs-lookup"><span data-stu-id="e887b-180">Alternatively, this step works by using the Topology Builder (the trusted applications/pools have a dedicated node there, also).</span></span>

13. <span data-ttu-id="e887b-181">您現在可以開始透過新用戶端來啟用 Persistent Chat Server 功能。</span><span class="sxs-lookup"><span data-stu-id="e887b-181">You can now begin to enable Persistent Chat Server functionality through the new clients.</span></span> <span data-ttu-id="e887b-182">如需啟用 Persistent Chat Server 的詳細資訊，請參閱 [在 Lync server 2013 中部署 Persistent Chat server](lync-server-2013-deploying-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e887b-182">For details about enabling Persistent Chat Server, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e887b-183">Lync Server 2013 支援多個 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="e887b-183">Lync Server 2013 supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="e887b-184">不過，我們支援將 Lync 2010 群組聊天或 Office 通訊伺服器 2007 R2 &nbsp; 群組聊天集區遷移至單一 Lync server 2013，Persistent Chat server 集區。</span><span class="sxs-lookup"><span data-stu-id="e887b-184">However, we support migrating a Lync 2010 Group Chat or Office Communications Server 2007 R2&nbsp;Group Chat pool to a single Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="e887b-185">您可以在部署中新增其他的持久聊天伺服器集區，以符合法規需求 (例如，在指定的地理位置內保留資料) 。</span><span class="sxs-lookup"><span data-stu-id="e887b-185">You can add additional new Persistent Chat Server pools in your deployment to meet the regulatory needs (for example, keeping data within a given geography).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


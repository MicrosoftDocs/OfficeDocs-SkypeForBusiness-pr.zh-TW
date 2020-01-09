---
title: 管理常設聊天室伺服器中的聊天室
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 摘要：瞭解如何在商務用 Skype Server 2015 中管理持久聊天伺服器聊天室。
ms.openlocfilehash: cbced7f62a4684e5541e35b5985b7e93cc7d3e66
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992118"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="c5339-103">管理常設聊天室伺服器中的聊天室</span><span class="sxs-lookup"><span data-stu-id="c5339-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c5339-104">**摘要：** 瞭解如何在商務用 Skype Server 2015 中管理持續聊天伺服器聊天室。</span><span class="sxs-lookup"><span data-stu-id="c5339-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c5339-105">使用正確的類別，就能更輕鬆地建立及管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="c5339-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="c5339-106">類別定義誰可以建立或加入聊天室。</span><span class="sxs-lookup"><span data-stu-id="c5339-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="c5339-107">在您嘗試管理聊天室之前，請務必閱讀[商務用 Skype server 2015 中的持續聊天類別、聊天室，以及使用者角色](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)，並在[商務用 skype Server 2015 中管理永久性聊天伺服器的類別](categories.md)。</span><span class="sxs-lookup"><span data-stu-id="c5339-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c5339-108">商務用 Skype Server 2015 提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="c5339-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c5339-109">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="c5339-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="c5339-110">如需詳細資訊，請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="c5339-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="c5339-111">如果您需要使用持續聊天，您可以選擇將需要此功能的使用者遷移至小組，或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="c5339-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="c5339-112">您可以使用 Windows PowerShell 命令列介面來設定及管理聊天室，或使用商務用 Skype 用戶端（如果您是聊天室的成員）來進行設定和管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="c5339-112">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="c5339-113">本主題說明如何使用 Windows PowerShell 命令列介面管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="c5339-113">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="c5339-114">如果您想要使用商務用 Skype 用戶端管理聊天室，請參閱用戶端說明。</span><span class="sxs-lookup"><span data-stu-id="c5339-114">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="c5339-115">聊天室可以是兩種類型的其中一種： [標準] 和 [Auditorium]。</span><span class="sxs-lookup"><span data-stu-id="c5339-115">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="c5339-116">標準聊天室可讓所有成員張貼及讀取訊息。</span><span class="sxs-lookup"><span data-stu-id="c5339-116">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="c5339-117">Auditorium 是一種在其中只有簡報者可以張貼的聊天室，但所有人都可以閱讀。</span><span class="sxs-lookup"><span data-stu-id="c5339-117">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="c5339-118">誰可以存取及管理聊天室，取決於使用者角色，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c5339-118">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="c5339-119">使用者必須是聊天室的成員，才能張貼及閱讀郵件。</span><span class="sxs-lookup"><span data-stu-id="c5339-119">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="c5339-120">您可以將簡報者張貼到 Auditorium 會議室。</span><span class="sxs-lookup"><span data-stu-id="c5339-120">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="c5339-121">系統管理員可以從任何聊天室刪除較舊的內容（例如，在特定日期之前發佈的內容），讓資料庫不會變得太大。</span><span class="sxs-lookup"><span data-stu-id="c5339-121">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="c5339-122">系統管理員也可以移除或取代被視為不適用於特定聊天室的郵件。</span><span class="sxs-lookup"><span data-stu-id="c5339-122">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="c5339-123">使用者（包括郵件作者）無法刪除任何聊天室中的內容。</span><span class="sxs-lookup"><span data-stu-id="c5339-123">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="c5339-124">聊天室管理員可以對所有聊天室屬性進行變更，包括停用會議室。</span><span class="sxs-lookup"><span data-stu-id="c5339-124">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="c5339-125">不過，經理不能刪除聊天室，或變更聊天室的類別。</span><span class="sxs-lookup"><span data-stu-id="c5339-125">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="c5339-126">只有系統管理員才能在已建立聊天室後刪除聊天室。</span><span class="sxs-lookup"><span data-stu-id="c5339-126">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="c5339-127">您可以使用下列 Windows PowerShell Cmdlet 來設定和管理聊天室：</span><span class="sxs-lookup"><span data-stu-id="c5339-127">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="c5339-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="c5339-128">**Cmdlet**</span></span>|<span data-ttu-id="c5339-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="c5339-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c5339-130">新-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="c5339-130">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="c5339-131">建立新聊天室</span><span class="sxs-lookup"><span data-stu-id="c5339-131">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="c5339-132">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="c5339-132">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="c5339-133">設定現有聊天室的設定;將使用者和使用者群組指派給聊天室</span><span class="sxs-lookup"><span data-stu-id="c5339-133">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="c5339-134">CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="c5339-134">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="c5339-135">取得會議室的相關資訊</span><span class="sxs-lookup"><span data-stu-id="c5339-135">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="c5339-136">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="c5339-136">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="c5339-137">從聊天室中清除聊天室或訊息</span><span class="sxs-lookup"><span data-stu-id="c5339-137">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="c5339-138">移除-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="c5339-138">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="c5339-139">移除會議室</span><span class="sxs-lookup"><span data-stu-id="c5339-139">Remove a room</span></span>  <br/> |
|<span data-ttu-id="c5339-140">移除-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="c5339-140">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="c5339-141">移除聊天室中的郵件</span><span class="sxs-lookup"><span data-stu-id="c5339-141">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="c5339-142">您可以使用**CsPersistentChatRoom** Cmdlet 來建立聊天室和 CsPersistentChatRoom Cmdlet 來**設定**現有聊天室，包括新增使用者至聊天室。</span><span class="sxs-lookup"><span data-stu-id="c5339-142">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="c5339-143">您可以針對聊天室設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="c5339-143">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="c5339-144">禁止.</span><span class="sxs-lookup"><span data-stu-id="c5339-144">Disabled.</span></span> <span data-ttu-id="c5339-145">可讓您停用或啟用聊天室。</span><span class="sxs-lookup"><span data-stu-id="c5339-145">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="c5339-146">邀請.</span><span class="sxs-lookup"><span data-stu-id="c5339-146">Invitations.</span></span> <span data-ttu-id="c5339-147">可讓您啟用或停用聊天室邀請函，當使用者已新增為聊天室成員時，就會通知使用者。</span><span class="sxs-lookup"><span data-stu-id="c5339-147">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="c5339-148">[繼承] 中邀請函的預設設定，這會造成聊天室採用其所屬類別上設定的邀請設定。</span><span class="sxs-lookup"><span data-stu-id="c5339-148">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="c5339-149">將 [邀請] 設定設定為 [聊天室] 層級的 false，即可覆蓋類別設定。</span><span class="sxs-lookup"><span data-stu-id="c5339-149">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="c5339-150">考慮.</span><span class="sxs-lookup"><span data-stu-id="c5339-150">Privacy.</span></span> <span data-ttu-id="c5339-151">可讓您指定聊天室是開啟、關閉或秘密。</span><span class="sxs-lookup"><span data-stu-id="c5339-151">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="c5339-152">任何人都可以搜尋並存取 [開啟聊天室]。</span><span class="sxs-lookup"><span data-stu-id="c5339-152">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="c5339-153">任何人都可以搜尋關閉的聊天室，但只能透過成員存取。</span><span class="sxs-lookup"><span data-stu-id="c5339-153">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="c5339-154">密碼室只能透過聊天室的成員進行搜尋和存取。</span><span class="sxs-lookup"><span data-stu-id="c5339-154">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="c5339-155">根據預設，每個新的聊天室最初都設定為 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="c5339-155">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="c5339-156">輸入.</span><span class="sxs-lookup"><span data-stu-id="c5339-156">Type.</span></span> <span data-ttu-id="c5339-157">可讓您指定聊天室是標準室，也就是接受任何成員張貼的訊息，或是 Auditorium 聊天室，只接受簡報者張貼的訊息。</span><span class="sxs-lookup"><span data-stu-id="c5339-157">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="c5339-158">增益集.</span><span class="sxs-lookup"><span data-stu-id="c5339-158">Addin.</span></span> <span data-ttu-id="c5339-159">可讓您將先前設定的增益集與聊天室建立關聯，這可讓成員在參與時查看 URL 內容。</span><span class="sxs-lookup"><span data-stu-id="c5339-159">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="c5339-160">除了上述參數之外， **CsPersistentChatRoom** Cmdlet 還可讓您將使用者指派給聊天室，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c5339-160">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="c5339-161">會員.</span><span class="sxs-lookup"><span data-stu-id="c5339-161">Members.</span></span> <span data-ttu-id="c5339-162">配置聊天室的成員資格。</span><span class="sxs-lookup"><span data-stu-id="c5339-162">Configures membership for the chat room.</span></span> <span data-ttu-id="c5339-163">您可以透過指定使用者的 SIP 位址，使用單一 Cmdlet 來新增或移除個別或多個成員。</span><span class="sxs-lookup"><span data-stu-id="c5339-163">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="c5339-164">若要允許大量新增使用者，也可以指定 Active Directory 組織單位或通訊群組。</span><span class="sxs-lookup"><span data-stu-id="c5339-164">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="c5339-165">主管.</span><span class="sxs-lookup"><span data-stu-id="c5339-165">Managers.</span></span> <span data-ttu-id="c5339-166">可讓您將主管指派給聊天室。</span><span class="sxs-lookup"><span data-stu-id="c5339-166">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="c5339-167">管理員有權定義聊天室的成員資格，以及其他設定。</span><span class="sxs-lookup"><span data-stu-id="c5339-167">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="c5339-168">演示.</span><span class="sxs-lookup"><span data-stu-id="c5339-168">Presenters.</span></span> <span data-ttu-id="c5339-169">可讓您將簡報者指派給 Auditorium 聊天室。</span><span class="sxs-lookup"><span data-stu-id="c5339-169">Lets you assign presenters to an Auditorium chat room.</span></span> 
    
  <span data-ttu-id="c5339-170">如需語法的詳細資料（包括所有參數），請參閱[商務用 Skype Server 2015 管理命令](../management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="c5339-170">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="c5339-171">建立新聊天室</span><span class="sxs-lookup"><span data-stu-id="c5339-171">Create a new room</span></span>

<span data-ttu-id="c5339-172">您可以使用**新的 CsPersistentChatRoom** Cmdlet 來建立新的聊天室。</span><span class="sxs-lookup"><span data-stu-id="c5339-172">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="c5339-173">例如，下列命令會在 [pool atl-cs-001.contoso.com] 上建立一個名為 ITChatRoom 的新聊天室。</span><span class="sxs-lookup"><span data-stu-id="c5339-173">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="c5339-174">在這個範例中，聊天室會新增至 [IT] 類別：</span><span class="sxs-lookup"><span data-stu-id="c5339-174">In this example, the chat room is added to the IT category:</span></span>
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="c5339-175">**注意：** 如果下列其中一項為 true，則不需要 PersistentChatPoolFqdn：</span><span class="sxs-lookup"><span data-stu-id="c5339-175">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="c5339-176">只有一個持續聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="c5339-176">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="c5339-177">您可以將池 FQDN 提供給類別。</span><span class="sxs-lookup"><span data-stu-id="c5339-177">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="c5339-178">您提供一個 [池 FQDN] 來新增聊天室。</span><span class="sxs-lookup"><span data-stu-id="c5339-178">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="c5339-179">設定現有的聊天室</span><span class="sxs-lookup"><span data-stu-id="c5339-179">Configure an existing room</span></span>

<span data-ttu-id="c5339-180">您可以使用**CsPersistentChatRoom Cmdlet 設定**現有的聊天室。</span><span class="sxs-lookup"><span data-stu-id="c5339-180">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="c5339-181">例如，下列命令會將 user1 做為成員和簡報者，以及 testCat Auditorium 聊天室的管理員。</span><span class="sxs-lookup"><span data-stu-id="c5339-181">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="c5339-182">下一個範例會將 active Directory 中的 NorthAmericaUsers OU 中的所有使用者新增至 [北美] 聊天室：</span><span class="sxs-lookup"><span data-stu-id="c5339-182">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="c5339-183">下一個範例會將財務通訊群組中的所有成員新增至相同的聊天室：</span><span class="sxs-lookup"><span data-stu-id="c5339-183">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="c5339-184">停用或啟用聊天室</span><span class="sxs-lookup"><span data-stu-id="c5339-184">Disable or enable a room</span></span>

<span data-ttu-id="c5339-185">如果永久聊天室的主題已不再相關，您可以停用聊天室，讓使用者無法使用該聊天室。</span><span class="sxs-lookup"><span data-stu-id="c5339-185">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="c5339-186">停用聊天室時，所有成員都會立即中斷與聊天室的連線。</span><span class="sxs-lookup"><span data-stu-id="c5339-186">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="c5339-187">停用聊天室之後，使用者就無法在聊天室搜尋中重新加入或尋找。</span><span class="sxs-lookup"><span data-stu-id="c5339-187">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="c5339-188">如果聊天室的記錄繼續存在，則在停用聊天室時，內容會保留下來。</span><span class="sxs-lookup"><span data-stu-id="c5339-188">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="c5339-189">不過，在聊天室保持在停用狀態時，搜尋中不會顯示該內容。</span><span class="sxs-lookup"><span data-stu-id="c5339-189">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="c5339-190">如果您稍後啟用聊天室，使用者就可以搜尋在停用聊天室之前所張貼的訊息。</span><span class="sxs-lookup"><span data-stu-id="c5339-190">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="c5339-191">如需有關設定聊天室歷程記錄的詳細資訊，請參閱[在商務用 Skype server 2015 的永久聊天伺服器中管理類別](categories.md)。</span><span class="sxs-lookup"><span data-stu-id="c5339-191">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="c5339-192">如果聊天室停用，則會保留其成員資格清單及其他設定。</span><span class="sxs-lookup"><span data-stu-id="c5339-192">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="c5339-193">以管理員身分，您可以啟用已停用的聊天室，而且不需要手動重新建立設定。</span><span class="sxs-lookup"><span data-stu-id="c5339-193">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="c5339-194">您可以使用**CsPersistentChatRoom** Cmdlet 來停用聊天室，並將 Disabled 參數設定為 True：</span><span class="sxs-lookup"><span data-stu-id="c5339-194">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="c5339-195">若要啟用聊天室，請將 Disabled 參數設定為 False：</span><span class="sxs-lookup"><span data-stu-id="c5339-195">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a><span data-ttu-id="c5339-196">取得會議室的相關資訊</span><span class="sxs-lookup"><span data-stu-id="c5339-196">Get information about rooms</span></span>

<span data-ttu-id="c5339-197">若要取得針對貴組織中設定使用的聊天室相關資訊，您可以使用**CsPersistentChatRoom** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c5339-197">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="c5339-198">下列命令會傳回在組織中設定為使用的所有聊天室的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="c5339-198">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="c5339-199">移除聊天室中的所有內容</span><span class="sxs-lookup"><span data-stu-id="c5339-199">Remove all content from a room</span></span>

<span data-ttu-id="c5339-200">您可以使用**Clear CsPersistentChatRoom** Cmdlet 來移除聊天室的內容。</span><span class="sxs-lookup"><span data-stu-id="c5339-200">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="c5339-201">例如，下列命令會移除已在2015年3月1日之前或之前新增到聊天室中的持續聊天室 ITChatRoom 中的所有內容：</span><span class="sxs-lookup"><span data-stu-id="c5339-201">For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="c5339-202">移除聊天室中的郵件</span><span class="sxs-lookup"><span data-stu-id="c5339-202">Remove a message from a room</span></span>

<span data-ttu-id="c5339-203">您可以在永久聊天資料庫中移除一或多封郵件，並選擇性地使用**CsPersistentChatMessage** Cmdlet，以預設訊息或由系統管理員提供的訊息取代郵件。</span><span class="sxs-lookup"><span data-stu-id="c5339-203">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet.</span></span> <span data-ttu-id="c5339-204">例如，下列命令會移除使用者 kenmyer@contoso.com 張貼的 ITChatRoom 聊天室中的所有郵件：</span><span class="sxs-lookup"><span data-stu-id="c5339-204">For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="c5339-205">下一個範例會將所有已移除的郵件取代為不能再使用的筆記：</span><span class="sxs-lookup"><span data-stu-id="c5339-205">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="c5339-206">移除會議室</span><span class="sxs-lookup"><span data-stu-id="c5339-206">Remove a room</span></span>

<span data-ttu-id="c5339-207">您可以使用**CsPersistentChatRoom** Cmdlet 來移除聊天室。</span><span class="sxs-lookup"><span data-stu-id="c5339-207">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="c5339-208">例如，下列命令會移除聊天室 RedmondChatRoom：</span><span class="sxs-lookup"><span data-stu-id="c5339-208">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="c5339-209">將會議室從一個類別移到另一個類別</span><span class="sxs-lookup"><span data-stu-id="c5339-209">Move a room from one category to another</span></span>

<span data-ttu-id="c5339-210">如果聊天室管理員有其他類別的建立**者**許可權，他/她可以將會議室從一個類別移到另一個類別。</span><span class="sxs-lookup"><span data-stu-id="c5339-210">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="c5339-211">不會刪除並重新建立聊天室。</span><span class="sxs-lookup"><span data-stu-id="c5339-211">The room is not deleted and recreated.</span></span> <span data-ttu-id="c5339-212">變更是資料庫中的關聯。</span><span class="sxs-lookup"><span data-stu-id="c5339-212">It is a change of association within the database.</span></span>
  
<span data-ttu-id="c5339-213">變更聊天室類別應該很少進行，且需要小心。</span><span class="sxs-lookup"><span data-stu-id="c5339-213">Changing a chat room category should be done rarely and with caution.</span></span> <span data-ttu-id="c5339-214">類別會決定聊天室的允許成員資格，因此當聊天室移至另一個類別時，新類別不再支援的所有系統存取控制清單（Sacl）都將清除。</span><span class="sxs-lookup"><span data-stu-id="c5339-214">A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged.</span></span> <span data-ttu-id="c5339-215">例如，如果使用者是聊天室的成員，而且已不再是新類別中的允許成員，就會修改聊天室成員資格，並將該使用者從聊天室中移除。</span><span class="sxs-lookup"><span data-stu-id="c5339-215">For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  


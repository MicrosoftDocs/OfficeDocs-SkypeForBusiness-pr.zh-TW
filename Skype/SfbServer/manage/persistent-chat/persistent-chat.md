---
title: 管理商務用 Skype Server 2015 中的常設聊天室
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 摘要：瞭解如何在商務用 Skype Server 2015 中管理持續聊天伺服器。
ms.openlocfilehash: 97cce8adedbb4dea932084497006e3c17bfdd7d8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817319"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="9d519-103">管理商務用 Skype Server 2015 中的常設聊天室</span><span class="sxs-lookup"><span data-stu-id="9d519-103">Manage Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9d519-104">**摘要：** 瞭解如何在商務用 Skype Server 2015 中管理持續聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="9d519-104">**Summary:** Learn how to manage Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9d519-105">當您為您的組織設定持續聊天伺服器時，您會在部署期間指定初始配置。</span><span class="sxs-lookup"><span data-stu-id="9d519-105">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="9d519-106">不過，有時您可能會想要變更實現持久聊天伺服器支援的方式。</span><span class="sxs-lookup"><span data-stu-id="9d519-106">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="9d519-107">例如，您可能需要針對貴組織內的特定團隊或群組，將持續聊天伺服器支援與控制項設定成不同的方式。</span><span class="sxs-lookup"><span data-stu-id="9d519-107">For example you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="9d519-108">本節提供的資訊和程式可協助您自訂持續聊天伺服器部署。</span><span class="sxs-lookup"><span data-stu-id="9d519-108">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="9d519-109">如需有關您可以針對持久聊天伺服器設定的功能和功能的詳細資訊，請參閱[在商務用 Skype server 2015 中規劃持久聊天伺服器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="9d519-109">For details about the features and functionality that you can configure for Persistent Chat Server, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="9d519-110">如需部署持久聊天伺服器的詳細資訊，請參閱[在商務用 Skype server 2015 中部署持久聊天伺服器](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="9d519-110">For details about deploying Persistent Chat Server, see [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="9d519-111">商務用 Skype Server 2015 提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="9d519-111">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="9d519-112">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="9d519-112">The same functionality is available in Teams.</span></span> <span data-ttu-id="9d519-113">如需詳細資訊，請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="9d519-113">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="9d519-114">如果您需要使用持續聊天，您可以選擇將需要此功能的使用者遷移至小組，或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="9d519-114">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
<span data-ttu-id="9d519-115">您可以使用 [控制台] 或使用 Windows PowerShell Cmdlet 來管理持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="9d519-115">You can manage Persistent Chat Server by using the Control Panel or by using Windows PowerShell cmdlets.</span></span> 
  
<span data-ttu-id="9d519-116">若要使用 [控制台]：</span><span class="sxs-lookup"><span data-stu-id="9d519-116">To use the Control Panel:</span></span>
  
1. <span data-ttu-id="9d519-117">使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。</span><span class="sxs-lookup"><span data-stu-id="9d519-117">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="9d519-118">從 [**開始**] 功能表中，選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗，然後輸入管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="9d519-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="9d519-119">在左側導覽列中，按一下 [**持續聊天**]。</span><span class="sxs-lookup"><span data-stu-id="9d519-119">In the left navigation bar, click **Persistent Chat**.</span></span>
    
<span data-ttu-id="9d519-120">下表摘要列出可用來協助您管理持久聊天伺服器的 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9d519-120">The following table summarizes the Windows PowerShell cmdlets available to help you manage Persistent Chat Server.</span></span> <span data-ttu-id="9d519-121">如需語法的詳細資料（包括所有可用的參數），請參閱[商務用 Skype Server 2015 管理命令](../management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="9d519-121">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="9d519-122">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="9d519-122">**Cmdlet**</span></span>|<span data-ttu-id="9d519-123">**說明**</span><span class="sxs-lookup"><span data-stu-id="9d519-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9d519-124">新-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="9d519-124">New-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="9d519-125">建立新類別</span><span class="sxs-lookup"><span data-stu-id="9d519-125">Creates a new category</span></span>  <br/> |
|<span data-ttu-id="9d519-126">Set-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="9d519-126">Set-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="9d519-127">配置現有類別的設定</span><span class="sxs-lookup"><span data-stu-id="9d519-127">Configures settings for an existing category</span></span>  <br/> |
|<span data-ttu-id="9d519-128">CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="9d519-128">Get-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="9d519-129">檢索類別的相關資訊</span><span class="sxs-lookup"><span data-stu-id="9d519-129">Retrieves information about categories</span></span>  <br/> |
|<span data-ttu-id="9d519-130">移除-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="9d519-130">Remove-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="9d519-131">移除類別</span><span class="sxs-lookup"><span data-stu-id="9d519-131">Removes a category</span></span>  <br/> |
|<span data-ttu-id="9d519-132">新-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="9d519-132">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="9d519-133">建立新聊天室</span><span class="sxs-lookup"><span data-stu-id="9d519-133">Creates a new chat room</span></span>  <br/> |
|<span data-ttu-id="9d519-134">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="9d519-134">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="9d519-135">配置現有聊天室的設定;將使用者和使用者群組指派給聊天室</span><span class="sxs-lookup"><span data-stu-id="9d519-135">Configures settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="9d519-136">CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="9d519-136">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="9d519-137">檢索會議室的相關資訊</span><span class="sxs-lookup"><span data-stu-id="9d519-137">Retrieves information about rooms</span></span>  <br/> |
|<span data-ttu-id="9d519-138">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="9d519-138">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="9d519-139">從聊天室清除聊天室或訊息</span><span class="sxs-lookup"><span data-stu-id="9d519-139">Clears a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="9d519-140">移除-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="9d519-140">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="9d519-141">移除聊天室</span><span class="sxs-lookup"><span data-stu-id="9d519-141">Removes a room</span></span>  <br/> |
|<span data-ttu-id="9d519-142">移除-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="9d519-142">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="9d519-143">移除聊天室中的郵件</span><span class="sxs-lookup"><span data-stu-id="9d519-143">Removes messages from a room</span></span>  <br/> |
|<span data-ttu-id="9d519-144">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="9d519-144">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="9d519-145">建立新的增益集</span><span class="sxs-lookup"><span data-stu-id="9d519-145">Creates a new add-in</span></span>  <br/> |
|<span data-ttu-id="9d519-146">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="9d519-146">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="9d519-147">配置現有增益集的設定</span><span class="sxs-lookup"><span data-stu-id="9d519-147">Configures settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="9d519-148">CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="9d519-148">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="9d519-149">檢索增益集的相關資訊</span><span class="sxs-lookup"><span data-stu-id="9d519-149">Retrieves information about add-ins</span></span>  <br/> |
|<span data-ttu-id="9d519-150">移除-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="9d519-150">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="9d519-151">移除增益集</span><span class="sxs-lookup"><span data-stu-id="9d519-151">Removes an add-in</span></span>  <br/> |
|<span data-ttu-id="9d519-152">Set-CsPersistentChatComplianceConfiguration</span><span class="sxs-lookup"><span data-stu-id="9d519-152">Set-CsPersistentChatComplianceConfiguration</span></span>  <br/> |<span data-ttu-id="9d519-153">修改現有的合規性配置設定集合</span><span class="sxs-lookup"><span data-stu-id="9d519-153">Modifies an existing collection of compliance configuration settings</span></span>  <br/> |
|<span data-ttu-id="9d519-154">Export-CsPersistentChatData</span><span class="sxs-lookup"><span data-stu-id="9d519-154">Export-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="9d519-155">從持久性聊天資料庫匯出資料</span><span class="sxs-lookup"><span data-stu-id="9d519-155">Exports data from a Persistent Chat database</span></span>  <br/> |
|<span data-ttu-id="9d519-156">匯入-CsPersistentChatData</span><span class="sxs-lookup"><span data-stu-id="9d519-156">Import-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="9d519-157">匯入從舊版 Lync Server 匯出的資料</span><span class="sxs-lookup"><span data-stu-id="9d519-157">Imports data that was exported from a previous version of Lync Server</span></span>  <br/> |
   


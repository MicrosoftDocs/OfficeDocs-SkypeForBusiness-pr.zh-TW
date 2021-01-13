---
title: 常設聊天室增益集主要頁面
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
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: 您可以使用 [Persistent Chat] 頁面的 [增益集] 區段，將 URLs 與 Persistent 聊天室產生關聯。 這些 URLs 會出現在交談擴充性窗格中的聊天室中的用戶端。 管理員必須將增益集加入至已註冊的增益集清單中，且聊天室管理員/創作者必須與其中一個已註冊的增益集產生關聯，使用者才能在用戶端看到此升級。
ms.openlocfilehash: ee747e12b4a6209d831588e68533531b0a7d95ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803793"
---
# <a name="persistent-chat-add-in-main-page"></a><span data-ttu-id="2ebcc-105">常設聊天室增益集主要頁面</span><span class="sxs-lookup"><span data-stu-id="2ebcc-105">Persistent Chat Add-in Main Page</span></span>

<span data-ttu-id="2ebcc-106">您可以使用 [ **Persistent chat** ] 頁面的 [**增益集**] 區段，將 URLs 與 persistent 聊天室產生關聯。</span><span class="sxs-lookup"><span data-stu-id="2ebcc-106">You can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="2ebcc-107">這些 URLs 會出現在交談擴充性窗格中的聊天室中的用戶端。</span><span class="sxs-lookup"><span data-stu-id="2ebcc-107">These URLs appear in the client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="2ebcc-108">管理員必須將增益集加入至已註冊的增益集清單中，且聊天室管理員/創作者必須與其中一個已註冊的增益集產生關聯，使用者才能在用戶端看到此升級。</span><span class="sxs-lookup"><span data-stu-id="2ebcc-108">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators must associate rooms with one of the registered add-ins before users can see this upgrade in their client.</span></span>

<span data-ttu-id="2ebcc-109">增益集可擴充聊天室體驗。</span><span class="sxs-lookup"><span data-stu-id="2ebcc-109">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="2ebcc-110">一般增益集可能會包含指向 Silverlight 應用程式的 URL，該應用程式會在將股市代號傳送至聊天室時進行截獲，並在 [擴充性] 窗格中顯示 stock 記錄。</span><span class="sxs-lookup"><span data-stu-id="2ebcc-110">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="2ebcc-111">其他範例還包括在聊天室中嵌入 OneNote 2013 URL 做為增益集，以包含一些分享內容，例如「第一印象」或「本日熱門話題」。</span><span class="sxs-lookup"><span data-stu-id="2ebcc-111">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<span data-ttu-id="2ebcc-112">若要建立 Persistent 聊天室的增益集，請參閱 [在商務用 Skype Server 2015 中設定 Persistent 聊天室的增益集](../../manage/persistent-chat/configure-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="2ebcc-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span></span> <span data-ttu-id="2ebcc-113">如果您是 Persistent Chat Administrator，您可以使用 [控制台] 或 [Windows PowerShell Cmdlet 來建立增益集。</span><span class="sxs-lookup"><span data-stu-id="2ebcc-113">If you are a Persistent Chat Administrator, you can create add-ins by using the control panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="2ebcc-114">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="2ebcc-114">Tasks you can perform</span></span>

<span data-ttu-id="2ebcc-115">您可以在「增益集」頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="2ebcc-115">You can perform the following tasks on the **Add-in** page:</span></span>

- [<span data-ttu-id="2ebcc-116">在商務用 Skype Server 2015 中設定持久聊天室的增益集</span><span class="sxs-lookup"><span data-stu-id="2ebcc-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="2ebcc-117">設定聊天室的增益集</span><span class="sxs-lookup"><span data-stu-id="2ebcc-117">To configure Add-ins for chat rooms</span></span>

<span data-ttu-id="2ebcc-118">下列清單說明頁面上的功能表、命令、欄位及內容。</span><span class="sxs-lookup"><span data-stu-id="2ebcc-118">The following lists describe the menus, command, fields, and properties on the page.</span></span>

1. <span data-ttu-id="2ebcc-119">使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。</span><span class="sxs-lookup"><span data-stu-id="2ebcc-119">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="2ebcc-120">從 [ **開始** ] 功能表中，選取商務用 Skype Server 控制台或開啟瀏覽器視窗，然後輸入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="2ebcc-120">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="2ebcc-121">如需您可以用來啟動控制台之不同方法的詳細資訊，請參閱 [Open Lync Server 系統管理工具](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2ebcc-121">For details about the different methods that you can use to start control panel, see [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span></span>

3. <span data-ttu-id="2ebcc-122">在左導覽列中，按一下 [常設聊天室]，然後按一下 [增益集]。</span><span class="sxs-lookup"><span data-stu-id="2ebcc-122">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>

    <span data-ttu-id="2ebcc-123">若為多個 Persistent Chat Server 集區部署，請從下拉式清單中選取適當的集區。</span><span class="sxs-lookup"><span data-stu-id="2ebcc-123">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4. <span data-ttu-id="2ebcc-124">在 **[增益集]** 頁面上，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="2ebcc-124">On the **Add-in** page, click **New**.</span></span>

5. <span data-ttu-id="2ebcc-125">在 [ **選取服務**] 中，選取對應至您需要建立增益集之 Persistent Chat Server 集區的服務。</span><span class="sxs-lookup"><span data-stu-id="2ebcc-125">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="2ebcc-126">增益集不得從一個集區移動到另一個集區，或是在不同集區之間共用。</span><span class="sxs-lookup"><span data-stu-id="2ebcc-126">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6. <span data-ttu-id="2ebcc-127">在 **[新增增益集]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="2ebcc-127">In **New Add-in**, do the following:</span></span>

   - <span data-ttu-id="2ebcc-128">在 **[名稱]** 中，指定新增益集的名稱。</span><span class="sxs-lookup"><span data-stu-id="2ebcc-128">In **Name**, specify a name for the new add-in.</span></span>

   - <span data-ttu-id="2ebcc-p107">在 **[URL]** 中，指定要與增益集建立關聯的 URL。URL 限於 http 和 https 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="2ebcc-p107">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7. <span data-ttu-id="2ebcc-131">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="2ebcc-131">Click **Commit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ebcc-132">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2ebcc-132">See also</span></span>

<span data-ttu-id="2ebcc-133">如需 Persistent Chat Server 功能及功能的詳細資訊，請參閱 [Plan For Persistent Chat server In 商務用 skype server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、 [在商務用 skype server 2015 中部署 persistent chat](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)Server，以及 [在商務用 Skype Server 2015 中管理 persistent chat server](../../manage/persistent-chat/persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="2ebcc-133">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>



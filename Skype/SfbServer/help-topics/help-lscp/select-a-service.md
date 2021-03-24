---
title: 選取服務
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectPool
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6086162-8a41-4e75-afa3-7d1889ffdc90
description: 使用 [選取服務] 對話方塊，尋找您環境中可用的服務。 若要使用現有的服務，請按一下清單中的服務，然後按一下 [確定]。
ms.openlocfilehash: 06ee0217a8a495a881c9925c57e33311e4944607
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108039"
---
# <a name="select-a-service"></a><span data-ttu-id="0a7ba-104">選取服務</span><span class="sxs-lookup"><span data-stu-id="0a7ba-104">Select a Service</span></span>

<span data-ttu-id="0a7ba-105">使用 [ **選取服務** ] 對話方塊，尋找您環境中可用的服務。</span><span class="sxs-lookup"><span data-stu-id="0a7ba-105">Use the **Select a Service** dialog box to find services available in your environment.</span></span> <span data-ttu-id="0a7ba-106">若要使用現有的服務，請按一下清單中的服務，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="0a7ba-106">To use an existing service, click a service in the list and then click **OK**.</span></span>

<span data-ttu-id="0a7ba-107">如需您可以使用商務用 Skype Server 控制台執行的不同程式的詳細資訊，請參閱 [管理商務用 Skype server 2015](../../manage/manage.md)。</span><span class="sxs-lookup"><span data-stu-id="0a7ba-107">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="0a7ba-108">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="0a7ba-108">Tasks you can perform</span></span>

<span data-ttu-id="0a7ba-109">您可以在 [ **選取服務** ] 頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="0a7ba-109">You can perform the following tasks on the **Select a Service** page:</span></span>

- [<span data-ttu-id="0a7ba-110">設定類別</span><span class="sxs-lookup"><span data-stu-id="0a7ba-110">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="0a7ba-111">為聊天室設定增益集</span><span class="sxs-lookup"><span data-stu-id="0a7ba-111">Configure Add-ins for Rooms</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-add-ins-for-rooms)

- [<span data-ttu-id="0a7ba-112">以全域方式設定或針對常設聊天室伺服器集區設定常設聊天室伺服器選項</span><span class="sxs-lookup"><span data-stu-id="0a7ba-112">Configure Persistent Chat Server Options Globally or for Persistent Chat Server Pool</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool)

<span data-ttu-id="0a7ba-113">如需您可以使用商務用 Skype Server 控制台執行的不同程式的詳細資訊，請參閱 [管理商務用 Skype server 2015](../../manage/manage.md)。</span><span class="sxs-lookup"><span data-stu-id="0a7ba-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="0a7ba-114">設定聊天室的類別</span><span class="sxs-lookup"><span data-stu-id="0a7ba-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="0a7ba-115">在 [ **選取服務**] 中，選取對應至需要建立類別之 Persistent Chat Server 集區的服務。</span><span class="sxs-lookup"><span data-stu-id="0a7ba-115">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="0a7ba-116">服務是 persistent chat Server 集區，Persistent Chat (用戶端) 使用它來識別類別所屬的集區。</span><span class="sxs-lookup"><span data-stu-id="0a7ba-116">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="0a7ba-117">類別只能隸屬于一部 Persistent Chat Server 集區，無法移至另一個集區，或與另一個集區共用。</span><span class="sxs-lookup"><span data-stu-id="0a7ba-117">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="0a7ba-118">為聊天室設定增益集</span><span class="sxs-lookup"><span data-stu-id="0a7ba-118">To configure add-ins for chat rooms</span></span>

<span data-ttu-id="0a7ba-119">在 [ **選取服務**] 中，選取對應至您需要建立增益集之 Persistent Chat Server 集區的服務。</span><span class="sxs-lookup"><span data-stu-id="0a7ba-119">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="0a7ba-120">增益集不得從一個集區移動到另一個集區，或是在不同集區之間共用。</span><span class="sxs-lookup"><span data-stu-id="0a7ba-120">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="0a7ba-121">設定特定 Persistent Chat Server 集區的持續聊天選項</span><span class="sxs-lookup"><span data-stu-id="0a7ba-121">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

<span data-ttu-id="0a7ba-122">在 [ **選取服務**] 中，選取要設定之持久聊天伺服器集區相關聯的服務。</span><span class="sxs-lookup"><span data-stu-id="0a7ba-122">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

<span data-ttu-id="0a7ba-123">如需 Persistent Chat Server 功能及功能的詳細資訊，請參閱規劃檔中的 [Persistent Chat Server 綜述](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) 。</span><span class="sxs-lookup"><span data-stu-id="0a7ba-123">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="0a7ba-124">如需使用持續性聊天伺服器設定的詳細資訊，請參閱設定 [Persistent Chat server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) In the Deployment 檔和 [管理 Lync Server 2013，Persistent Chat server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in Operations 檔中。</span><span class="sxs-lookup"><span data-stu-id="0a7ba-124">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>
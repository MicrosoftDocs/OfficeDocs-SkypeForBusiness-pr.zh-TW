---
title: 回應群組建立新的或編輯現有的代理群組
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
ROBOTS: NOINDEX, NOFOLLOW
description: 代理人群組會定義接聽回應群組 (稱為代理人) 電話的人選，以及要套用至群組中所有代理人的設定。
ms.openlocfilehash: bafa1ae490da49c8a4af096129a122315a2a7809
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192374"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a><span data-ttu-id="8d7a5-103">回應群組：建立新代理人群組或編輯現有代理人群組</span><span class="sxs-lookup"><span data-stu-id="8d7a5-103">Response Groups: Create New or Edit Existing Agent Group</span></span>

<span data-ttu-id="8d7a5-104">代理人群組會定義接聽回應群組 (稱為代理人) 電話的人選，以及要套用至群組中所有代理人的設定。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-104">Agent groups define who can answer calls to a response group (known as agents) and the settings that apply to all the agents in the group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="8d7a5-105">UI 參考</span><span class="sxs-lookup"><span data-stu-id="8d7a5-105">UI Reference</span></span>

<span data-ttu-id="8d7a5-106">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="8d7a5-107">**名稱**每個代理群組都需要一個唯一的名稱。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-107">**Name** Each agent group requires a unique name.</span></span> <span data-ttu-id="8d7a5-108">使用識別群組函數的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-108">Use a descriptive name that identifies the group's function.</span></span> <span data-ttu-id="8d7a5-109">例如, [技術支援中心]。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-109">For example, Help Desk.</span></span>

- <span data-ttu-id="8d7a5-110">**描述**此為選用欄位。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-110">**Description** This field is optional.</span></span> <span data-ttu-id="8d7a5-111">使用它來提供群組的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-111">Use it to provide additional details about the group.</span></span>

- <span data-ttu-id="8d7a5-112">**參與原則**指定代理程式登入回應群組的方式:</span><span class="sxs-lookup"><span data-stu-id="8d7a5-112">**Participation policy** Specify the way that agents are to sign into the response group:</span></span>

  - <span data-ttu-id="8d7a5-p103">選取 [非正式]\*\*\*\*，指定群組中的代理人不需要登入及登出。非正式代理人登入時即會自動登入。**非正式**為預設設定。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-p103">Select **Informal** to specify that the agents in the group do not need to sign in and out. Informal agents are automatically signed in when they sign in. The default is **Informal**.</span></span>

  - <span data-ttu-id="8d7a5-115">選取 [**正式**], 指定群組中的代理程式必須登入和登出。當您選取此選項時, 代理程式會按一下用戶端中的功能表項目來開啟瀏覽器, 並顯示網頁主控台來登入和登出。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-115">Select **Formal** to specify that the agents in the group must sign in and out. When you select this option, agents click a menu item in the client to open a browser and display a web page console for signing in and out.</span></span>

- <span data-ttu-id="8d7a5-116">**警示時間 (秒)** 在向下一個可用的代理程式提供通話之前, 請先指定撥打代理程式的秒數。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-116">**Alert time (seconds)** Specify the number of seconds to ring an agent before offering the call to the next available agent.</span></span> <span data-ttu-id="8d7a5-117">此值必須至少10秒, 且少於180秒。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-117">The value must be at least 10 seconds and less than 180 seconds.</span></span> <span data-ttu-id="8d7a5-118">預設值為20秒。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-118">The default is 20 seconds.</span></span>

- <span data-ttu-id="8d7a5-119">**路由方法**選取決定代理接收通話順序的方法:</span><span class="sxs-lookup"><span data-stu-id="8d7a5-119">**Routing method** Select the method for determining the order in which agents receive calls:</span></span>

  - <span data-ttu-id="8d7a5-120">選取 [最長閒置時間]\*\*\*\* 將新的電話清單提供給已閒置 (目前狀態已是 [線上]\*\*\*\* 或 [非使用中]\*\*\*\*) 最長時間的代理人。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-120">Select **Longest idle** to offer a new call first to the agent who has been idle (has had a presence of **Available** or **Inactive**) the longest.</span></span>

  - <span data-ttu-id="8d7a5-p105">選取 [平行]\*\*\*\* 同時提供新電話給所有線上代理人。電話會傳送給第一個接聽的代理人。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-p105">Select **Parallel** to offer a new call to all available agents at the same time. The call is sent to the first agent who accepts it.</span></span>

  - <span data-ttu-id="8d7a5-123">選取 [循環配置資源]\*\*\*\* 以輪流提供新電話給每位代理人。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-123">Select **Round robin** to offer a new call to each agent in turn.</span></span>

  - <span data-ttu-id="8d7a5-124">選取 [循序]\*\*\*\* 一律依照 [代理人]\*\*\*\* 清單中所列出的順序，將新電話提供給代理人。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-124">Select **Serial** to always offer a new call to agents in the order in which they are listed in the **Agent** list.</span></span>

  - <span data-ttu-id="8d7a5-125">選取 [**助理**], 就能在登入的所有代理及回應群組應用程式 (無論其目前狀態為何), 提供新的呼叫。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-125">Select **Attendant** to offer a new call to all agents who are signed in and the Response Group application at the same time, regardless of their current presence.</span></span> <span data-ttu-id="8d7a5-126">已設定為代理程式的系統管理員和用戶端使用者可以查看所有等待的通話, 並以任何順序接聽等待通話。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-126">Attendants and client users who are configured as agents can see all the calls that are waiting and can answer waiting calls in any order.</span></span> <span data-ttu-id="8d7a5-127">電話會傳送給第一個接聽的代理人，而其他服務員及使用者將不再看到此電話。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-127">The call is sent to the first agent who accepts it, and the other attendants and users no longer see the call.</span></span>

- <span data-ttu-id="8d7a5-128">**代理**程式依下列其中一種方式, 選取要作為回應群組之代理人的使用者:</span><span class="sxs-lookup"><span data-stu-id="8d7a5-128">**Agents** Select the users who are to be agents for the response group in one of the following ways:</span></span>

  - <span data-ttu-id="8d7a5-129">選取 [**使用現有的電子郵件通訊群組清單**] 來使用 Exchange 通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-129">Select **Use an existing email distribution list** to use an Exchange distribution list.</span></span> <span data-ttu-id="8d7a5-130">請在 [通訊群組清單位址]\*\*\*\* 中輸入通訊群組清單的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-130">Type the email address of the distribution list in **Distribution list address**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8d7a5-p108">您可以僅選取一個代理人群組的通訊群組清單。若通訊群組清單包含巢狀通訊群組清單，那些巢狀通訊群組清單將不會包含在代理人群組中。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-p108">You can select only one distribution list for an agent group. If the distribution list includes nested distribution lists, the nested distribution lists are not included in the agent group.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8d7a5-133">代理人列在通訊群組清單中的順序，會影響代理人接聽循環配置資源電話及循序路由電話的順序。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-133">The order in which agents are listed in the distribution list affects the order in which agents receive calls for round robin and serial routing.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8d7a5-134">回應群組管理員或使用者可能會看到隱藏的成員資格或隱藏清單。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-134">Hidden memberships or hidden lists might become visible to Response Group administrators or users.</span></span> <span data-ttu-id="8d7a5-135">如需詳細資訊, 請參閱[在商務用 Skype 中建立或修改代理群組](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md)。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-135">For details, see [Create or modify an agent group in Skype for Business](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span></span>

  - <span data-ttu-id="8d7a5-p110">選取 [定義代理人自訂群組]\*\*\*\* 以選取您要指派作為回應群組代理人的使用者。按一下 [選取]\*\*\*\* 將代理人新增至清單。按一下 [移除]\*\*\*\* 可從清單刪除選取的代理人。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-p110">Select **Define a custom group of agents** to select the users you want to assign as agents for the response group. Click **Select** to add an agent to the list. Click **Remove** to delete a selected agent from the list.</span></span>

    <span data-ttu-id="8d7a5-p111">使用向上鍵及向下鍵可在代理人清單中移動選取的代理人。代理人在清單中的順序，會影響代理人接聽循環配置資源電話及循序路由電話的順序。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-p111">The up and down arrows move a selected agent up and down in the agent list. The order of agents in the list affects the order in which agents receive calls for round robin and serial routing.</span></span>

<span data-ttu-id="8d7a5-141">如需回應群組功能與功能的詳細資訊, 請參閱規劃檔中的[商務用 Skype 伺服器中的回應群組應用程式規劃](../../../plan-your-deployment/enterprise-voice-solution/response-group.md)。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-141">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="8d7a5-142">如需管理代理人群組的詳細資訊，請參閱作業文件中的〈[Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-142">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>



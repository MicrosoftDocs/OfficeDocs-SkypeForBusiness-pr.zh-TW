---
title: 回應群組建立新的或編輯現有的代理群組
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
description: 代理人群組會定義接聽回應群組 (稱為代理人) 電話的人選，以及要套用至群組中所有代理人的設定。
ms.openlocfilehash: 5468b5a542472ac3f736163d5a4daea620246a28
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189574"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a><span data-ttu-id="2e180-103">回應群組：建立新代理人群組或編輯現有代理人群組</span><span class="sxs-lookup"><span data-stu-id="2e180-103">Response Groups: Create New or Edit Existing Agent Group</span></span>

<span data-ttu-id="2e180-104">代理人群組會定義接聽回應群組 (稱為代理人) 電話的人選，以及要套用至群組中所有代理人的設定。</span><span class="sxs-lookup"><span data-stu-id="2e180-104">Agent groups define who can answer calls to a response group (known as agents) and the settings that apply to all the agents in the group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="2e180-105">UI 參考</span><span class="sxs-lookup"><span data-stu-id="2e180-105">UI Reference</span></span>

<span data-ttu-id="2e180-106">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="2e180-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="2e180-107">**名稱**每個代理群組都需要一個唯一的名稱。</span><span class="sxs-lookup"><span data-stu-id="2e180-107">**Name** Each agent group requires a unique name.</span></span> <span data-ttu-id="2e180-108">使用識別群組函數的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="2e180-108">Use a descriptive name that identifies the group's function.</span></span> <span data-ttu-id="2e180-109">例如, [技術支援中心]。</span><span class="sxs-lookup"><span data-stu-id="2e180-109">For example, Help Desk.</span></span>

- <span data-ttu-id="2e180-110">**描述**此為選用欄位。</span><span class="sxs-lookup"><span data-stu-id="2e180-110">**Description** This field is optional.</span></span> <span data-ttu-id="2e180-111">使用它來提供群組的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2e180-111">Use it to provide additional details about the group.</span></span>

- <span data-ttu-id="2e180-112">**參與原則**指定代理程式登入回應群組的方式:</span><span class="sxs-lookup"><span data-stu-id="2e180-112">**Participation policy** Specify the way that agents are to sign into the response group:</span></span>

  - <span data-ttu-id="2e180-p103">選取 [非正式]\*\*\*\*，指定群組中的代理人不需要登入及登出。非正式代理人登入時即會自動登入。**非正式**為預設設定。</span><span class="sxs-lookup"><span data-stu-id="2e180-p103">Select **Informal** to specify that the agents in the group do not need to sign in and out. Informal agents are automatically signed in when they sign in. The default is **Informal**.</span></span>

  - <span data-ttu-id="2e180-115">選取 [**正式**], 指定群組中的代理程式必須登入和登出。當您選取此選項時, 代理程式會按一下用戶端中的功能表項目來開啟瀏覽器, 並顯示網頁主控台來登入和登出。</span><span class="sxs-lookup"><span data-stu-id="2e180-115">Select **Formal** to specify that the agents in the group must sign in and out. When you select this option, agents click a menu item in the client to open a browser and display a web page console for signing in and out.</span></span>

- <span data-ttu-id="2e180-116">**警示時間 (秒)** 在向下一個可用的代理程式提供通話之前, 請先指定撥打代理程式的秒數。</span><span class="sxs-lookup"><span data-stu-id="2e180-116">**Alert time (seconds)** Specify the number of seconds to ring an agent before offering the call to the next available agent.</span></span> <span data-ttu-id="2e180-117">此值必須至少10秒, 且少於180秒。</span><span class="sxs-lookup"><span data-stu-id="2e180-117">The value must be at least 10 seconds and less than 180 seconds.</span></span> <span data-ttu-id="2e180-118">預設值為20秒。</span><span class="sxs-lookup"><span data-stu-id="2e180-118">The default is 20 seconds.</span></span>

- <span data-ttu-id="2e180-119">**路由方法**選取決定代理接收通話順序的方法:</span><span class="sxs-lookup"><span data-stu-id="2e180-119">**Routing method** Select the method for determining the order in which agents receive calls:</span></span>

  - <span data-ttu-id="2e180-120">選取 [最長閒置時間]\*\*\*\* 將新的電話清單提供給已閒置 (目前狀態已是 [線上]\*\*\*\* 或 [非使用中]\*\*\*\*) 最長時間的代理人。</span><span class="sxs-lookup"><span data-stu-id="2e180-120">Select **Longest idle** to offer a new call first to the agent who has been idle (has had a presence of **Available** or **Inactive**) the longest.</span></span>

  - <span data-ttu-id="2e180-p105">選取 [平行]\*\*\*\* 同時提供新電話給所有線上代理人。電話會傳送給第一個接聽的代理人。</span><span class="sxs-lookup"><span data-stu-id="2e180-p105">Select **Parallel** to offer a new call to all available agents at the same time. The call is sent to the first agent who accepts it.</span></span>

  - <span data-ttu-id="2e180-123">選取 [循環配置資源]\*\*\*\* 以輪流提供新電話給每位代理人。</span><span class="sxs-lookup"><span data-stu-id="2e180-123">Select **Round robin** to offer a new call to each agent in turn.</span></span>

  - <span data-ttu-id="2e180-124">選取 [循序]\*\*\*\* 一律依照 [代理人]\*\*\*\* 清單中所列出的順序，將新電話提供給代理人。</span><span class="sxs-lookup"><span data-stu-id="2e180-124">Select **Serial** to always offer a new call to agents in the order in which they are listed in the **Agent** list.</span></span>

  - <span data-ttu-id="2e180-125">選取 [**助理**], 就能在登入的所有代理及回應群組應用程式 (無論其目前狀態為何), 提供新的呼叫。</span><span class="sxs-lookup"><span data-stu-id="2e180-125">Select **Attendant** to offer a new call to all agents who are signed in and the Response Group application at the same time, regardless of their current presence.</span></span> <span data-ttu-id="2e180-126">已設定為代理程式的系統管理員和用戶端使用者可以查看所有等待的通話, 並以任何順序接聽等待通話。</span><span class="sxs-lookup"><span data-stu-id="2e180-126">Attendants and client users who are configured as agents can see all the calls that are waiting and can answer waiting calls in any order.</span></span> <span data-ttu-id="2e180-127">電話會傳送給第一個接聽的代理人，而其他服務員及使用者將不再看到此電話。</span><span class="sxs-lookup"><span data-stu-id="2e180-127">The call is sent to the first agent who accepts it, and the other attendants and users no longer see the call.</span></span>

- <span data-ttu-id="2e180-128">**代理**程式依下列其中一種方式, 選取要作為回應群組之代理人的使用者:</span><span class="sxs-lookup"><span data-stu-id="2e180-128">**Agents** Select the users who are to be agents for the response group in one of the following ways:</span></span>

  - <span data-ttu-id="2e180-129">選取 [**使用現有的電子郵件通訊群組清單**] 來使用 Exchange 通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="2e180-129">Select **Use an existing email distribution list** to use an Exchange distribution list.</span></span> <span data-ttu-id="2e180-130">請在 [通訊群組清單位址]\*\*\*\* 中輸入通訊群組清單的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="2e180-130">Type the email address of the distribution list in **Distribution list address**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e180-p108">您可以僅選取一個代理人群組的通訊群組清單。若通訊群組清單包含巢狀通訊群組清單，那些巢狀通訊群組清單將不會包含在代理人群組中。</span><span class="sxs-lookup"><span data-stu-id="2e180-p108">You can select only one distribution list for an agent group. If the distribution list includes nested distribution lists, the nested distribution lists are not included in the agent group.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e180-133">代理人列在通訊群組清單中的順序，會影響代理人接聽循環配置資源電話及循序路由電話的順序。</span><span class="sxs-lookup"><span data-stu-id="2e180-133">The order in which agents are listed in the distribution list affects the order in which agents receive calls for round robin and serial routing.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e180-134">回應群組管理員或使用者可能會看到隱藏的成員資格或隱藏清單。</span><span class="sxs-lookup"><span data-stu-id="2e180-134">Hidden memberships or hidden lists might become visible to Response Group administrators or users.</span></span> <span data-ttu-id="2e180-135">如需詳細資訊, 請參閱[在商務用 Skype 2015 中建立或修改代理群組](../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md)。</span><span class="sxs-lookup"><span data-stu-id="2e180-135">For details, see [Create or modify an agent group in Skype for Business 2015](../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span></span>

  - <span data-ttu-id="2e180-p110">選取 [定義代理人自訂群組]\*\*\*\* 以選取您要指派作為回應群組代理人的使用者。按一下 [選取]\*\*\*\* 將代理人新增至清單。按一下 [移除]\*\*\*\* 可從清單刪除選取的代理人。</span><span class="sxs-lookup"><span data-stu-id="2e180-p110">Select **Define a custom group of agents** to select the users you want to assign as agents for the response group. Click **Select** to add an agent to the list. Click **Remove** to delete a selected agent from the list.</span></span>

    <span data-ttu-id="2e180-p111">使用向上鍵及向下鍵可在代理人清單中移動選取的代理人。代理人在清單中的順序，會影響代理人接聽循環配置資源電話及循序路由電話的順序。</span><span class="sxs-lookup"><span data-stu-id="2e180-p111">The up and down arrows move a selected agent up and down in the agent list. The order of agents in the list affects the order in which agents receive calls for round robin and serial routing.</span></span>

<span data-ttu-id="2e180-141">如需回應群組功能與功能的詳細資訊, 請參閱規劃檔中的[商務用 Skype Server 2015 中的回應群組應用程式規劃](../../plan-your-deployment/enterprise-voice-solution/response-group.md)。</span><span class="sxs-lookup"><span data-stu-id="2e180-141">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="2e180-142">如需管理代理人群組的詳細資訊，請參閱作業文件中的〈[Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="2e180-142">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>



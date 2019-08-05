---
title: 回應群組佇列建立新的或編輯現有的
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: 回應群組佇列將呼叫控制到回應群組, 直到工程師接聽通話。
ms.openlocfilehash: 20a2066cbbece953e8f050919d8531f887f676ff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192369"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="b8f8c-103">回應群組佇列：建立新的或編輯現有佇列</span><span class="sxs-lookup"><span data-stu-id="b8f8c-103">Response Groups Queue: Create New or Edit Existing</span></span>

<span data-ttu-id="b8f8c-104">回應群組佇列將呼叫控制到回應群組, 直到工程師接聽通話。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="b8f8c-105">UI 參考</span><span class="sxs-lookup"><span data-stu-id="b8f8c-105">UI Reference</span></span>

<span data-ttu-id="b8f8c-106">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="b8f8c-107">**名稱**每個佇列必須具有名稱。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="b8f8c-108">輸入佇列的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-108">Type a descriptive name for the queue.</span></span>

- <span data-ttu-id="b8f8c-109">**描述**此為選用欄位。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-109">**Description** This field is optional.</span></span> <span data-ttu-id="b8f8c-110">使用它來提供有關佇列的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-110">Use it to provide additional details about the queue.</span></span>

- <span data-ttu-id="b8f8c-111">**群組**選取您要指派給佇列的代理群組。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="b8f8c-112">按一下 [**選取**], 將代理群組新增至清單。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="b8f8c-113">按一下 [**移除**], 從清單中刪除選取的 [代理] 群組。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-113">Click **Remove** to delete the selected agent group from the list.</span></span>

    <span data-ttu-id="b8f8c-114">您可以使用向上鍵或向下鍵，在清單中上移或下移您所選取的代理人群組。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="b8f8c-115">代理人群組的順序會影響商務用 Skype 伺服器搜尋可用的代理程式的順序。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="b8f8c-116">也就是說，搜尋可用代理人時，會先搜尋清單中的第一個群組，之後才會搜尋第二個與之後的群組。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>

- <span data-ttu-id="b8f8c-117">**啟用佇列**超時選取此核取方塊, 以指定呼叫者在撥打電話前等候保留的最長時間週期。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="b8f8c-118">如果您選取此選項, 您也需要指定下列專案:</span><span class="sxs-lookup"><span data-stu-id="b8f8c-118">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="b8f8c-119">**超時時間 (秒)** 選取或輸入呼叫者在撥打電話前可以等候的最大秒數。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>

  - <span data-ttu-id="b8f8c-120">**通話動作**選取來電超時時所發生的動作。您的選擇如下:</span><span class="sxs-lookup"><span data-stu-id="b8f8c-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>

  - <span data-ttu-id="b8f8c-121">**中斷連線**</span><span class="sxs-lookup"><span data-stu-id="b8f8c-121">**Disconnect**</span></span>

  - <span data-ttu-id="b8f8c-122">**轉寄到語音信箱**如果您選取此選項, 請在 [ **sip 位址**] 中, 輸入 [sip:<username> @ <domainname> sip:bob@contoso.com)] 中的語音信箱位址 (例如,)。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="b8f8c-123">**轉寄至電話號碼**如果您選取此選項, 請在 [ **sip 位址**] 中, 輸入 [sip:<number> @ <domainname> ] 的電話號碼 (例如, sip:+14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="b8f8c-124">**轉寄到 SIP 位址**選取此選項可將通話轉寄給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="b8f8c-125">在 [ **sip 位址**] 中, 在 [sip 格式] 中輸入使用者<username>@<domainname>的 URI:。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="b8f8c-126">**轉寄至另一個佇列**如果您選取此選項, 請流覽至通話超時時接收通話的佇列。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>

- <span data-ttu-id="b8f8c-127">**啟用佇列溢出**選取此核取方塊, 以指定佇列可以保留的呼叫數目上限。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="b8f8c-128">如果您選取此選項, 您也需要指定下列專案:</span><span class="sxs-lookup"><span data-stu-id="b8f8c-128">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="b8f8c-129">**最大通話數**選取或輸入佇列可以保留的呼叫數目上限。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>

  - <span data-ttu-id="b8f8c-130">**轉接來電**選取在達到佇列溢出閾值時, 要採取行動的通話。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>

  - <span data-ttu-id="b8f8c-131">**通話動作**選取符合佇列溢出閾值時所發生的動作。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="b8f8c-132">您的選擇如下:</span><span class="sxs-lookup"><span data-stu-id="b8f8c-132">Your choices are:</span></span>

  - <span data-ttu-id="b8f8c-133">**中斷連線**</span><span class="sxs-lookup"><span data-stu-id="b8f8c-133">**Disconnect**</span></span>

  - <span data-ttu-id="b8f8c-134">**轉寄到語音信箱**如果您選取此選項, 請在 [ **sip 位址**] 中, 輸入 [sip:<username> @ <domainname> sip:bob@contoso.com)] 中的語音信箱位址 (例如,)。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="b8f8c-135">**轉寄至電話號碼**如果您選取此選項, 請在 [ **sip 位址**] 中, 輸入 [sip:<number> @ <domainname> ] 的電話號碼 (例如, sip:+14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="b8f8c-136">**轉寄到 SIP 位址**選取此選項可將通話轉寄給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="b8f8c-137">在 [ **sip 位址**] 中, 在 [sip 格式] 中輸入使用者<username>@<domainname>的 URI:。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="b8f8c-138">**轉寄至另一個佇列**如果您選取此選項, 請在達到佇列溢出閾值時, 流覽到要接收呼叫的佇列。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>

<span data-ttu-id="b8f8c-139">如需回應群組功能與功能的詳細資訊, 請參閱規劃檔中的[商務用 Skype 伺服器中的回應群組應用程式規劃](../../../plan-your-deployment/enterprise-voice-solution/response-group.md)。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="b8f8c-140">如需使用佇列的詳細資訊，請參閱作業文件中的〈[Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="b8f8c-140">For details about working with queues, see [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>



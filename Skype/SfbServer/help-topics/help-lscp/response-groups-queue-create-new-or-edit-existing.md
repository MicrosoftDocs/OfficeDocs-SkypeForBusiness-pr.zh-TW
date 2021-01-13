---
title: 回應群組佇列建立新的或編輯現有
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
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: 回應群組佇列會將呼叫保留到回應群組，直到代理接聽來電為止。
ms.openlocfilehash: cfe2d212f90f8dcdf83b8f827ebf470245ce87fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829313"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="48dda-103">回應群組佇列：建立新的或編輯現有</span><span class="sxs-lookup"><span data-stu-id="48dda-103">Response Groups Queue: Create New or Edit Existing</span></span>

<span data-ttu-id="48dda-104">回應群組佇列會將呼叫保留到回應群組，直到代理接聽來電為止。</span><span class="sxs-lookup"><span data-stu-id="48dda-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="48dda-105">UI 參考</span><span class="sxs-lookup"><span data-stu-id="48dda-105">UI Reference</span></span>

<span data-ttu-id="48dda-106">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="48dda-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="48dda-107">**名稱** 每個佇列都必須有名稱。</span><span class="sxs-lookup"><span data-stu-id="48dda-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="48dda-108">輸入佇列的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="48dda-108">Type a descriptive name for the queue.</span></span>

- <span data-ttu-id="48dda-109">**描述** 此欄位是選用的。</span><span class="sxs-lookup"><span data-stu-id="48dda-109">**Description** This field is optional.</span></span> <span data-ttu-id="48dda-110">使用它提供有關佇列的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="48dda-110">Use it to provide additional details about the queue.</span></span>

- <span data-ttu-id="48dda-111">**群組** 選取您要指派給佇列的代理人群組。</span><span class="sxs-lookup"><span data-stu-id="48dda-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="48dda-112">按一下 [ **選取** ]，將代理群組新增至清單。</span><span class="sxs-lookup"><span data-stu-id="48dda-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="48dda-113">按一下 [ **移除** ]，從清單中刪除選取的代理人群組。</span><span class="sxs-lookup"><span data-stu-id="48dda-113">Click **Remove** to delete the selected agent group from the list.</span></span>

    <span data-ttu-id="48dda-114">向上及向中箭號會在清單中上下移動選取的代理群組。</span><span class="sxs-lookup"><span data-stu-id="48dda-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="48dda-115">代理人群組的順序會影響商務用 Skype 伺服器搜尋可用之代理人的順序。</span><span class="sxs-lookup"><span data-stu-id="48dda-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="48dda-116">也就是說，會先搜尋清單中的第一個群組，以取得可用的代理程式，後面接著第二個群組，依此類推。</span><span class="sxs-lookup"><span data-stu-id="48dda-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>

- <span data-ttu-id="48dda-117">**啟用佇列** 超時選取此核取方塊可指定來電者等候通話之前等候保留的時間上限。</span><span class="sxs-lookup"><span data-stu-id="48dda-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="48dda-118">如果您選取此選項，您也必須指定下列專案：</span><span class="sxs-lookup"><span data-stu-id="48dda-118">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="48dda-119">**(秒的超時時間)** 選取或輸入來電者可以等候代理接聽通話的最長秒數。</span><span class="sxs-lookup"><span data-stu-id="48dda-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>

  - <span data-ttu-id="48dda-120">**通話動作** 選取來電超時時所發生的動作。您可以選擇：</span><span class="sxs-lookup"><span data-stu-id="48dda-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>

  - <span data-ttu-id="48dda-121">**中斷連線**</span><span class="sxs-lookup"><span data-stu-id="48dda-121">**Disconnect**</span></span>

  - <span data-ttu-id="48dda-122">**轉寄至語音信箱** 如果您選取此選項，請在 [ **sip 位址**] 的 [sip： (格式] 中輸入語音信箱位址， <username> @ <domainname> 例如，sip:bob@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="48dda-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="48dda-123">**轉寄至電話號碼** 如果您選取此選項，請在 [ **sip 位址**] 中，輸入 [sip： (格式的電話號碼] <number> @ <domainname> 例如，sip:+14255550121@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="48dda-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="48dda-124">**轉寄至 SIP 位址** 選取這個選項，將來電轉寄給另一個使用者。</span><span class="sxs-lookup"><span data-stu-id="48dda-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="48dda-125">在 [ **sip 位址**] 中，以 [sip：] 的格式輸入使用者的 URI <username> @ <domainname> 。</span><span class="sxs-lookup"><span data-stu-id="48dda-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="48dda-126">**轉寄到另一個佇列** 如果您選取此選項，請流覽至通話超時時要接聽通話的佇列。</span><span class="sxs-lookup"><span data-stu-id="48dda-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>

- <span data-ttu-id="48dda-127">**啟用佇列溢出** 選取此核取方塊可指定佇列可以保留的通話數目上限。</span><span class="sxs-lookup"><span data-stu-id="48dda-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="48dda-128">如果您選取此選項，您也必須指定下列專案：</span><span class="sxs-lookup"><span data-stu-id="48dda-128">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="48dda-129">**呼叫數目上限** 選取或輸入佇列可以保留的通話數目上限。</span><span class="sxs-lookup"><span data-stu-id="48dda-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>

  - <span data-ttu-id="48dda-130">**轉寄通話** 選擇符合佇列溢出臨界值時，要採取行動的呼叫。</span><span class="sxs-lookup"><span data-stu-id="48dda-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>

  - <span data-ttu-id="48dda-131">**通話動作** 選取達到佇列溢出閾值時所發生的動作。</span><span class="sxs-lookup"><span data-stu-id="48dda-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="48dda-132">您可以選擇：</span><span class="sxs-lookup"><span data-stu-id="48dda-132">Your choices are:</span></span>

  - <span data-ttu-id="48dda-133">**中斷連線**</span><span class="sxs-lookup"><span data-stu-id="48dda-133">**Disconnect**</span></span>

  - <span data-ttu-id="48dda-134">**轉寄至語音信箱** 如果您選取此選項，請在 [ **sip 位址**] 的 [sip： (格式] 中輸入語音信箱位址， <username> @ <domainname> 例如，sip:bob@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="48dda-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="48dda-135">**轉寄至電話號碼** 如果您選取此選項，請在 [ **sip 位址**] 中，輸入 [sip： (格式的電話號碼] <number> @ <domainname> 例如，sip:+14255550121@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="48dda-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="48dda-136">**轉寄至 SIP 位址** 選取這個選項，將來電轉寄給另一個使用者。</span><span class="sxs-lookup"><span data-stu-id="48dda-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="48dda-137">在 [ **sip 位址**] 中，以 [sip：] 的格式輸入使用者的 URI <username> @ <domainname> 。</span><span class="sxs-lookup"><span data-stu-id="48dda-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="48dda-138">**轉寄到另一個佇列** 如果您選取此選項，請流覽至滿足佇列溢出閾值時要接聽通話的佇列。</span><span class="sxs-lookup"><span data-stu-id="48dda-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>

<span data-ttu-id="48dda-139">如需有關回應群組功能及功能的詳細資訊，請參閱規劃檔中的在 [商務用 Skype Server 2015 中規劃回應群組應用程式](../../plan-your-deployment/enterprise-voice-solution/response-group.md) 。</span><span class="sxs-lookup"><span data-stu-id="48dda-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="48dda-140">如需使用佇列的詳細資訊，請參閱 Operations 檔中的 [管理回應群組佇列](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="48dda-140">For details about working with queues, see [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>



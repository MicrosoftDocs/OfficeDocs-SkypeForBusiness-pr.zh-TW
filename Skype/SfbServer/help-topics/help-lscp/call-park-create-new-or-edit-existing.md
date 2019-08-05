---
title: 通話駐留建立新的或編輯現有的
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: 通話駐留數位範圍定義將暫停通話一直留在他人取得或超時的暫時號碼。
ms.openlocfilehash: 8e6748f0e106195148453094de3b95e9dc48254c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193181"
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="ce763-103">通話駐留：建立新的或編輯現有</span><span class="sxs-lookup"><span data-stu-id="ce763-103">Call Park: Create New or Edit Existing</span></span>

<span data-ttu-id="ce763-104">通話駐留數位範圍定義將暫停通話一直留在他人取得或超時的暫時號碼。</span><span class="sxs-lookup"><span data-stu-id="ce763-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="ce763-105">UI 參考</span><span class="sxs-lookup"><span data-stu-id="ce763-105">UI Reference</span></span>

<span data-ttu-id="ce763-106">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="ce763-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="ce763-107">**名稱**輸入識別數位範圍的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="ce763-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="ce763-108">在您儲存編號範圍之後, 此名稱就無法變更。</span><span class="sxs-lookup"><span data-stu-id="ce763-108">After you save the number range, this name cannot be changed.</span></span>

- <span data-ttu-id="ce763-109">**數位範圍**在第一個欄位中, 輸入數位範圍的起始編號。</span><span class="sxs-lookup"><span data-stu-id="ce763-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="ce763-110">在第二個欄位中, 輸入數位範圍的結束數位。</span><span class="sxs-lookup"><span data-stu-id="ce763-110">In the second field, type the ending number of the number range.</span></span>

  - <span data-ttu-id="ce763-111">該範圍的起始號碼必須小於或等於範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="ce763-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="ce763-112">該範圍的起始號碼值的長度必須等於範圍的結束號碼值長度。</span><span class="sxs-lookup"><span data-stu-id="ce763-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="ce763-p103">號碼範圍必須是唯一的。此範圍不得與其他任何範圍重疊。</span><span class="sxs-lookup"><span data-stu-id="ce763-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="ce763-115">如果數位範圍是以字元\*或 # 開頭, 則範圍必須大於100。</span><span class="sxs-lookup"><span data-stu-id="ce763-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

  - <span data-ttu-id="ce763-116">有效值: 必須符合正則運算式字串 ([\\* | #]？ [1-9] \d{0,7}) |([1-9] \d{0,8})。</span><span class="sxs-lookup"><span data-stu-id="ce763-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="ce763-117">這表示值必須是以字元\*或 # 或數位1到 9 (第一個字元不能是零) 開頭的字串。</span><span class="sxs-lookup"><span data-stu-id="ce763-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="ce763-118">如果第一個字元是\*或 #, 則下列字元必須是1到9的數位 (不能是零)。</span><span class="sxs-lookup"><span data-stu-id="ce763-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="ce763-119">後續字元可以是從0到9的任何數位, 最多可達七個其他字元 (例如,\*"#6000"、\*"92000"、"95551212" 和 "915551212")。</span><span class="sxs-lookup"><span data-stu-id="ce763-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="ce763-120">如果第一個字元不\*是或 #, 則第一個字元必須是數位1到 9 (不能是零), 然後再加上最多八個字元 (例如: 915551212; 41212; 300)。</span><span class="sxs-lookup"><span data-stu-id="ce763-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>

  - <span data-ttu-id="ce763-p105">每個集區的號碼總數不得超過 50,000 個。每個號碼範圍通常會涵蓋 100 個以下的號碼，但只要總數不超過 10,000 個號碼，則範圍可以大一些。例如，與其指定起始號碼 7000000 與結束號碼 8000000，請考慮指定起始號碼 7000000 與結束號碼 7000100。</span><span class="sxs-lookup"><span data-stu-id="ce763-p105">You should not have more than a total of 50,000 numbers per pool. Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

- <span data-ttu-id="ce763-124">**目的地伺服器的 FQDN**選取託管通話駐留應用程式之應用程式服務的完整功能變數名稱 (FQDN) 或服務識別碼。</span><span class="sxs-lookup"><span data-stu-id="ce763-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="ce763-125">在數位範圍內, 由 start 編號和結束號碼所指定範圍內的所有來電都會路由到這個伺服器或池子。</span><span class="sxs-lookup"><span data-stu-id="ce763-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>

<span data-ttu-id="ce763-126">如需通話寄存功能與功能的詳細資料, 請參閱[在商務用 Skype 2015 中規劃通話寄存](../../plan-your-deployment/enterprise-voice-solution/call-park.md)。</span><span class="sxs-lookup"><span data-stu-id="ce763-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="ce763-127">如需使用通話駐留編號範圍的詳細資料, 請參閱[設定停用通話的電話號碼延伸](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ce763-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>



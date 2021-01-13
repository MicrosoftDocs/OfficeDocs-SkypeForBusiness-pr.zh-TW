---
title: 通話駐留建立新的或編輯現有
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
ROBOTS: NOINDEX, NOFOLLOW
description: 通話駐留號碼範圍定義在有人接聽或下班時，寄存通話保留的臨時號碼。
ms.openlocfilehash: aa89ddc094f85607afb37c455b0f5a5e05df70de
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820093"
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="c16c0-103">通話駐留：建立新的或編輯現有</span><span class="sxs-lookup"><span data-stu-id="c16c0-103">Call Park: Create New or Edit Existing</span></span>

<span data-ttu-id="c16c0-104">通話駐留號碼範圍定義在有人接聽或下班時，寄存通話保留的臨時號碼。</span><span class="sxs-lookup"><span data-stu-id="c16c0-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c16c0-105">UI 參考</span><span class="sxs-lookup"><span data-stu-id="c16c0-105">UI Reference</span></span>

<span data-ttu-id="c16c0-106">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="c16c0-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="c16c0-107">**名稱** 輸入識別號碼範圍的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="c16c0-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="c16c0-108">在您儲存編號範圍後，就無法變更此名稱。</span><span class="sxs-lookup"><span data-stu-id="c16c0-108">After you save the number range, this name cannot be changed.</span></span>

- <span data-ttu-id="c16c0-109">**號碼範圍** 在第一個欄位中，輸入號碼範圍的開始號碼。</span><span class="sxs-lookup"><span data-stu-id="c16c0-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="c16c0-110">在第二個欄位中，輸入號碼範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="c16c0-110">In the second field, type the ending number of the number range.</span></span>

  - <span data-ttu-id="c16c0-111">該範圍的起始號碼必須小於或等於範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="c16c0-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="c16c0-112">該範圍的起始號碼值的長度必須等於範圍的結束號碼值長度。</span><span class="sxs-lookup"><span data-stu-id="c16c0-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="c16c0-113">號碼範圍必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c16c0-113">The number range must be unique.</span></span> <span data-ttu-id="c16c0-114">此範圍不得與其他任何範圍重疊。</span><span class="sxs-lookup"><span data-stu-id="c16c0-114">This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="c16c0-115">如果號碼範圍開頭為字元 \* 或 #，則範圍必須大於100。</span><span class="sxs-lookup"><span data-stu-id="c16c0-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

  - <span data-ttu-id="c16c0-116">有效的值：必須符合正則運算式字串 ( [ \\ \* | #]？ [1-9] \d {0,7}) | ( [1-9] \d {0,8}) 。</span><span class="sxs-lookup"><span data-stu-id="c16c0-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="c16c0-117">這表示值必須是以字元 \* 或 # 或數位1到9為開頭的字串。 (第一個字元不能是零) 。</span><span class="sxs-lookup"><span data-stu-id="c16c0-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="c16c0-118">如果第一個字元是 \* 或 #，下列字元必須是1到9的數位， (不能是零) 。</span><span class="sxs-lookup"><span data-stu-id="c16c0-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="c16c0-119">後續字元可以是0到9的任何數位，最多可以有七個其他字元 (例如，"#6000"、" \* 92000"、" \* 95551212" 和 "915551212" ) 。</span><span class="sxs-lookup"><span data-stu-id="c16c0-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="c16c0-120">如果第一個字元不是 \* 或 #，則第一個字元必須是1到)  (9 的數位，然後是0到9的數位，都是0到 9 (例如： 915551212; 41212; 300) 。</span><span class="sxs-lookup"><span data-stu-id="c16c0-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>

  - <span data-ttu-id="c16c0-121">每個集區不得超過總50000數目。</span><span class="sxs-lookup"><span data-stu-id="c16c0-121">You should not have more than a total of 50,000 numbers per pool.</span></span> <span data-ttu-id="c16c0-122">每個號碼範圍通常會包含100或更少的數位，但是只要包含少於10000數目，就會有很大的增加。</span><span class="sxs-lookup"><span data-stu-id="c16c0-122">Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers.</span></span> <span data-ttu-id="c16c0-123">例如，與其指定開頭號碼 7000000 與結束號碼 8000000，請考慮指定開始號碼 7000000 與結束號碼 7000100。</span><span class="sxs-lookup"><span data-stu-id="c16c0-123">For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

- <span data-ttu-id="c16c0-124">**目的地伺服器的 FQDN** 選取主控通話駐留應用程式之應用程式服務的完整功能變數名稱 (FQDN) 或服務識別碼。</span><span class="sxs-lookup"><span data-stu-id="c16c0-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="c16c0-125">所有寄存在號碼範圍中的 start 編號和結束編號所指定之範圍內的通話，將會路由傳送至此伺服器或集區。</span><span class="sxs-lookup"><span data-stu-id="c16c0-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>

<span data-ttu-id="c16c0-126">如需通話駐留功能及功能的詳細資訊，請參閱 [在商務用 Skype 中規劃通話駐留](../../../plan-your-deployment/enterprise-voice-solution/call-park.md)。</span><span class="sxs-lookup"><span data-stu-id="c16c0-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="c16c0-127">如需使用通話駐留號碼範圍的詳細資訊，請參閱 [設定寄存通話的電話號碼分機號碼](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c16c0-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>



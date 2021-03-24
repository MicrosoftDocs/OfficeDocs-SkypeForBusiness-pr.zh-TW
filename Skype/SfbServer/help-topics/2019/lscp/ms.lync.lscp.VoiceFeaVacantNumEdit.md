---
title: 未指派電話號碼建立新的或編輯現有
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: 未指派號碼是對您的組織有效但未指派給使用者或電話的電話號碼。未指派的號碼表可識別您希望用來處理撥打至未指派號碼的方式。
ms.openlocfilehash: 49837269f81eaee09a0c191008234345d1d6d19f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097049"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="17486-104">未指派電話號碼：建立新的或編輯現有</span><span class="sxs-lookup"><span data-stu-id="17486-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

> [!NOTE]
> <span data-ttu-id="17486-105">當您整合商務用 Skype 2019 與 Exchange 2013 或 Exchange 2016 時，Exchange UM 仍可用於商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="17486-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="17486-106">由於 Exchange 2019 中的支援變更，因此會取消考慮 Exchange UM 整合，以取代雲端語音信箱和雲端自動語音應答功能。</span><span class="sxs-lookup"><span data-stu-id="17486-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="17486-p103">未指派號碼是對您的組織有效但未指派給使用者或電話的電話號碼。未指派號碼是對您的組織有效但未指派給使用者或電話的電話號碼。
</span><span class="sxs-lookup"><span data-stu-id="17486-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="17486-p104">當您結束建立新的未指派號碼範圍或編輯現有的未指派號碼範圍時，請按一下 [確定] 返回列出所有號碼範圍的「未指派號碼」頁面。除非您按一下「未指派號碼」頁面上的 [全部認可]，否則資料庫不會認可您在「新增未指派號碼範圍」頁面或「編輯未指派號碼範圍」頁面上所做的變更。</span><span class="sxs-lookup"><span data-stu-id="17486-p104">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges. The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="17486-111">UI 參考</span><span class="sxs-lookup"><span data-stu-id="17486-111">UI Reference</span></span>

<span data-ttu-id="17486-112">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="17486-112">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="17486-113">**名稱** 請輸入識別未指派號碼範圍的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="17486-113">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="17486-114">在您儲存範圍之後，就無法變更此名稱。</span><span class="sxs-lookup"><span data-stu-id="17486-114">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="17486-115">**號碼範圍** 在第一個欄位中，輸入未指派號碼範圍的開始號碼。</span><span class="sxs-lookup"><span data-stu-id="17486-115">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="17486-116">在第二個欄位中，輸入該範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="17486-116">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="17486-117">該範圍的起始號碼必須小於或等於範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="17486-117">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="17486-118">如果範圍的開始號碼或範圍的結束號碼包含分機號碼，則範圍的開始號碼和結束號碼都必須包含分機，且開始號碼和結束號碼的分機號碼必須相同。</span><span class="sxs-lookup"><span data-stu-id="17486-118">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="17486-119">該數位必須符合正則運算式 (`tel:`) ？ (\+) ？ [1-9] \d {0,17} (; ext = [1-9] \d {0,9}) ？。</span><span class="sxs-lookup"><span data-stu-id="17486-119">The number must match the regular expression (`tel:`)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="17486-120">這表示數位可以以字串 ' 電話：」開頭。</span><span class="sxs-lookup"><span data-stu-id="17486-120">This means the number may begin with the string 'tel:'.</span></span> <span data-ttu-id="17486-121">如果您未指定該字串，就會自動為您新增該字串，例如加號 (+) ，以及數位1到9。</span><span class="sxs-lookup"><span data-stu-id="17486-121">If you don't specify that string, it will be automatically added for you, such as a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="17486-122">電話號碼最多可達 17 位，且後面可以再加分機，格式為 ;ext= 分機號碼。</span><span class="sxs-lookup"><span data-stu-id="17486-122">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="17486-123">**宣告服務** 選取 [ **宣告** ]，讓宣告應用程式處理來電或 **exchange Um** ，讓 exchange um 自動語音應答處理傳入的呼叫。</span><span class="sxs-lookup"><span data-stu-id="17486-123">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="17486-124">若您選取 [宣告服務] 的 [宣告]：</span><span class="sxs-lookup"><span data-stu-id="17486-124">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="17486-125">**目的地伺服器的 FQDN** 選取執行宣告應用程式的應用程式服務的服務 ID，該應用程式會處理對此未指派號碼範圍的撥入呼叫。</span><span class="sxs-lookup"><span data-stu-id="17486-125">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="17486-126">**宣告** 選取要為此未指派號碼範圍播放的宣告。</span><span class="sxs-lookup"><span data-stu-id="17486-126">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="17486-127">若您選取 [宣告服務] 的 [Exchange UM]：</span><span class="sxs-lookup"><span data-stu-id="17486-127">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="17486-128">**自動語音應答電話號碼** 選取 Exchange UM 自動語音應答的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="17486-128">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="17486-129">如需公告功能及功能的詳細資訊，請參閱規劃檔中的在 [商務用 Skype 中規劃宣告應用程式](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) 。</span><span class="sxs-lookup"><span data-stu-id="17486-129">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="17486-130">如需使用未指派號碼範圍的詳細資訊，請參閱作業文件中的＜[Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers)＞。</span><span class="sxs-lookup"><span data-stu-id="17486-130">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers) in the Operations documentation.</span></span>
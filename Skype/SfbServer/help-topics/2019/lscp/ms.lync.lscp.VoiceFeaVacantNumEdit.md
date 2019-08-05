---
title: 未指定的電話號碼建立新的或編輯現有的
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: 未指派號碼是對您的組織有效但未指派給使用者或電話的電話號碼。未指派號碼表指出您希望如何處理撥打至未指定號碼的通話。
ms.openlocfilehash: 05b0d3efe383f2056ed49be7d8ebb811643cd02d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191668"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="17aca-104">未指定的電話號碼: 建立新的或編輯現有的</span><span class="sxs-lookup"><span data-stu-id="17aca-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

> [!NOTE]
> <span data-ttu-id="17aca-105">當您將商務用 Skype 2019 與 Exchange 2013 或 Exchange 2016 整合時, Exchange UM 仍可在商務用 Skype Server 2019 中使用。</span><span class="sxs-lookup"><span data-stu-id="17aca-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="17aca-106">由於 Exchange 2019 中的支援變更, 因此需要取消 Exchange UM 整合, 以取代雲端語音信箱和雲端自動語音應答功能。</span><span class="sxs-lookup"><span data-stu-id="17aca-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="17aca-p103">未指派號碼是對您的組織有效但未指派給使用者或電話的電話號碼。未指派號碼表指出您希望如何處理撥打至未指定號碼的通話。</span><span class="sxs-lookup"><span data-stu-id="17aca-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="17aca-109">當您完成建立新的未指派編號範圍或編輯現有的數位範圍時, 請按一下 **[確定]** , 返回列出所有數位範圍的 [**未指定的號碼**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="17aca-109">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges.</span></span> <span data-ttu-id="17aca-110">您在新的 [**未指定**的數位範圍] 頁面或 [**編輯未指派的號碼] Rage**頁面上所做的變更, 直到您在 [**未指定的號碼**] 頁面上按一下 [**全部提交**] 為止。</span><span class="sxs-lookup"><span data-stu-id="17aca-110">The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="17aca-111">UI 參考</span><span class="sxs-lookup"><span data-stu-id="17aca-111">UI Reference</span></span>

<span data-ttu-id="17aca-112">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="17aca-112">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="17aca-113">**名稱**輸入識別未指定的數位範圍的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="17aca-113">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="17aca-114">在您儲存範圍之後, 此名稱就無法變更。</span><span class="sxs-lookup"><span data-stu-id="17aca-114">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="17aca-115">**數位範圍**在第一個欄位中, 輸入未指定的數位範圍的起始編號。</span><span class="sxs-lookup"><span data-stu-id="17aca-115">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="17aca-116">在第二個欄位中, 輸入範圍的結束數位。</span><span class="sxs-lookup"><span data-stu-id="17aca-116">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="17aca-117">該範圍的起始號碼必須小於或等於範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="17aca-117">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="17aca-118">如果範圍的起始編號或範圍的結束數位包含分機號碼, 則起始編號與範圍的結束數位都必須包含延伸, 且起始編號和所需的延伸號碼必須是相同的。結束數位。</span><span class="sxs-lookup"><span data-stu-id="17aca-118">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="17aca-119">這個數位必須符合正則運算式 (電話:) 嗎？ (\+)?[1-9] \d{0,17}(; ext = [1-9] \d{0,9})？。</span><span class="sxs-lookup"><span data-stu-id="17aca-119">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="17aca-120">這表示數位可能會從電話號碼開始: (如果您沒有指定該字串將會自動新增為您), 請使用加號 (+), 以及1到9的數位。</span><span class="sxs-lookup"><span data-stu-id="17aca-120">This means the number may begin with the string tel: (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="17aca-121">電話號碼最多可達 17 位，且後面可以再加分機，格式為 ;ext= 分機號碼。</span><span class="sxs-lookup"><span data-stu-id="17aca-121">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="17aca-122">**宣告服務**選取 [**宣告**], 讓宣告應用程式處理撥出通話或**exchange Um** , 讓 exchange um 自動語音應答處理撥入通話。</span><span class="sxs-lookup"><span data-stu-id="17aca-122">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="17aca-123">如果您已選取 [**宣告**發佈**服務**]:</span><span class="sxs-lookup"><span data-stu-id="17aca-123">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="17aca-124">**目的地伺服器的 FQDN**選取執行宣告應用程式的應用程式服務的服務識別碼, 該 app 服務會處理撥入通話至此範圍的未指定號碼。</span><span class="sxs-lookup"><span data-stu-id="17aca-124">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="17aca-125">**宣告**選取要在此未指定編號範圍中播放的宣告。</span><span class="sxs-lookup"><span data-stu-id="17aca-125">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="17aca-126">如果您已選取 [ **EXCHANGE UM**以供**宣告服務**]:</span><span class="sxs-lookup"><span data-stu-id="17aca-126">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="17aca-127">**自動助理電話號碼**選取 Exchange UM 自動語音應答的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="17aca-127">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="17aca-128">如需公告功能和功能的詳細資訊, 請參閱規劃檔中的[商務用 Skype 中的宣告應用程式規劃](../../../plan-your-deployment/enterprise-voice-solution/announcement.md)。</span><span class="sxs-lookup"><span data-stu-id="17aca-128">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="17aca-129">如需使用未指派號碼範圍的詳細資訊，請參閱作業文件中的〈[Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="17aca-129">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>



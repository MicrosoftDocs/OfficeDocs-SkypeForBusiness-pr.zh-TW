---
title: 建立 Microsoft 365 使用者、新增商務語音授權，並指派電話號碼
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb8277c11cbcc459da9da8fd8d4f5b9c329470f3
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269279"
---
# <a name="create-and-license-business-voice-users-and-assign-them-phone-numbers"></a><span data-ttu-id="9f9c8-102">建立及授權商務語音使用者，並指派電話號碼給使用者</span><span class="sxs-lookup"><span data-stu-id="9f9c8-102">Create and license users and assign phone numbers to them</span></span>

<span data-ttu-id="9f9c8-103">若要使用 :::no-loc text="Microsoft 365 Business Voice":::，您需要具備 :::no-loc text="Microsoft 365 Business Voice with SMS"::: 授權的 :::no-loc text="Microsoft 365"::: 帳戶。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-103">To use :::no-loc text="Microsoft 365 Business Voice":::, you need a :::no-loc text="Microsoft 365"::: account that has a :::no-loc text="Microsoft 365 Business Voice with SMS"::: license.</span></span> <span data-ttu-id="9f9c8-104">具備帳戶和授權後，您就可以為其指派電話號碼。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-104">When you have an account and license, you can assign a phone number to it.</span></span>

## <a name="create-and-license-users"></a><span data-ttu-id="9f9c8-105">建立並授權使用者</span><span class="sxs-lookup"><span data-stu-id="9f9c8-105">Create and license users</span></span>

<span data-ttu-id="9f9c8-106">按照[個別或大量將使用者新增至 :::no-loc text="Office 365":::](https://docs.microsoft.com/office365/admin/add-users/add-users) 中的步驟。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-106">Follow the steps in [Add users individually or in bulk to :::no-loc text="Office 365":::](https://docs.microsoft.com/office365/admin/add-users/add-users) to add one or more users.</span></span>

> [!NOTE]
> <span data-ttu-id="9f9c8-107">在 **[指派產品授權]** 窗格中，選取 **:::no-loc text="Microsoft 365 Business Voice with SMS":::**。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-107">In the **Assign product licenses** pane, be sure to select **:::no-loc text="Microsoft 365 Business Voice with SMS":::**.</span></span>

## <a name="assign-phone-numbers-to-users"></a><span data-ttu-id="9f9c8-108">將電話號碼指派給使用者</span><span class="sxs-lookup"><span data-stu-id="9f9c8-108">Assign phone numbers to users</span></span>

<span data-ttu-id="9f9c8-109">建立使用者並指派 :::no-loc text="Microsoft 365 Business Voice with SMS"::: 授權後，您就可以為其指派電話號碼。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-109">After users have been created and assigned a :::no-loc text="Microsoft 365 Business Voice with SMS"::: license, you can assign phone numbers to them.</span></span> <span data-ttu-id="9f9c8-110">針對需要撥打或接聽外部電話號碼的使用者，每位使用者皆需要一個未指派的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-110">You need one unassigned phone number for each user that needs to make or receive calls to or from external phone numbers.</span></span> <span data-ttu-id="9f9c8-111">如果您未指派的電話號碼不夠，請參閱本文稍後的[取得更多電話號碼](#get-more-phone-numbers)。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-111">If you don't have enough unassigned phone numbers, see [Get more phone numbers](#get-more-phone-numbers) later in this article.</span></span>

1. <span data-ttu-id="9f9c8-112">移至https://admin.teams.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-112">Go to https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="9f9c8-113">輸入電話號碼要求的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-113">Enter a name and description for the phone number request</span></span>
3. <span data-ttu-id="9f9c8-114">選取 [**語音** > **電話號碼]**。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-114">Select **Voice** > **Phone numbers**</span></span>
4. <span data-ttu-id="9f9c8-115">選取您要指派給使用者的電話號碼，然後選取 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-115">Select a phone number you want to assign to a user and select **Edit**</span></span>
5. <span data-ttu-id="9f9c8-116">在 **[編輯]** 面板的 **[指派至]** 中輸入要指派電話號碼的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-116">In the **Edit** panel, enter the name of the user you want to assign the number to in **Assigned to** and select Assign</span></span> <span data-ttu-id="9f9c8-117">然後選取 **[指派]**。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-117">Then select **Assign**.</span></span>
6. <span data-ttu-id="9f9c8-118">在 **[緊急位置]** 中，輸入使用者所在的位置，然後選取 **[套用]**</span><span class="sxs-lookup"><span data-stu-id="9f9c8-118">In **Emergency location**, enter the location where the user is located, and then select **Apply**</span></span>

## <a name="get-more-phone-numbers"></a><span data-ttu-id="9f9c8-119">取得更多電話號碼</span><span class="sxs-lookup"><span data-stu-id="9f9c8-119">Get more phone numbers</span></span>

<span data-ttu-id="9f9c8-120">如果您沒有足夠的電話號碼可以指派給新使用者，您可以取得更多。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-120">If you don't have enough phone numbers to assign to new users, you can get more.</span></span> <span data-ttu-id="9f9c8-121">可能需要最多 24 小時的時間才能讓號碼使用。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-121">It may take up to 24 hours for numbers that you order to become available.</span></span>

1. <span data-ttu-id="9f9c8-122">移至https://admin.teams.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-122">Go to https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="9f9c8-123">輸入電話號碼要求的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-123">Enter a name and description for the phone number request</span></span>
3. <span data-ttu-id="9f9c8-124">選取 **[語音]** > **[電話號碼]** > **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-124">Select **Voice** > **Phone numbers** > **Add**.</span></span>
4. <span data-ttu-id="9f9c8-125">選擇電話號碼的國家或地區。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-125">Choose the country or region where the phone number should be created</span></span>
5. <span data-ttu-id="9f9c8-126">在 **[號碼類型]** 中，選取 **[使用者 (訂閱者)]**。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-126">In **Number type**, select **User (subscriber)**</span></span>
6. <span data-ttu-id="9f9c8-127">在 **[位置]** 中，搜尋使用者的位置並選取。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-127">In **Location**, search for the location of the user and select it.</span></span> <span data-ttu-id="9f9c8-128">您也可以選擇 **[新增位置]**。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-128">You can also choose to **Add a location**.</span></span>
7. <span data-ttu-id="9f9c8-129">選擇區號、輸入需要的電話號碼數，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-129">Choose an area code, enter the number of phone numbers to get, and then click **Next**</span></span>
8. <span data-ttu-id="9f9c8-130">等待保留電話號碼，然後檢視取得的號碼。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-130">Wait for the phone numbers to be reserved, and then view the numbers that you get.</span></span> <span data-ttu-id="9f9c8-131">如果均已確認，請選取 **[下單]**，然後選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="9f9c8-131">If everything looks ok, select **Place order** and then **Finish**.</span></span>

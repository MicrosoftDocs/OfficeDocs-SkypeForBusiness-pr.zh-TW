---
title: 設定Microsoft 365 商務語音電話號碼
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 瞭解如何為貴Microsoft 365 商務語音使用者和服務設定電話號碼。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89cb3764e30fa0bf4fcfa9d6a18d29ca69786cef
ms.sourcegitcommit: 2419348e964cfe97b72d533f267c5d7055d5366f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/12/2021
ms.locfileid: "52910035"
---
# <a name="step-2-set-up-business-voice-phone-numbers"></a><span data-ttu-id="13614-103">步驟 2：設定商務語音電話號碼</span><span class="sxs-lookup"><span data-stu-id="13614-103">Step 2: Set up Business Voice phone numbers</span></span>

<span data-ttu-id="13614-104">在組織中設定使用者或自動助理之前，您必須取得他們的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="13614-104">Before you can set up users or auto attendants in your organization, you need to get phone numbers for them.</span></span> <span data-ttu-id="13614-105">有幾種不同類型的電話號碼，不過以下是您需要在此步驟中新增的兩種號碼類型：</span><span class="sxs-lookup"><span data-stu-id="13614-105">There are several different types of phone numbers, however the following are the two types of numbers that you need to add in this step:</span></span>

- <span data-ttu-id="13614-106">**服務編號** 這些號碼用於自動語音機、音訊會議和通話佇列。</span><span class="sxs-lookup"><span data-stu-id="13614-106">**Service numbers** These numbers are used for auto attendants, audio conferencing, and call queues.</span></span> <span data-ttu-id="13614-107">它們可以是付費或免付費號碼，而且可以同時處理大量通話。</span><span class="sxs-lookup"><span data-stu-id="13614-107">They can be toll or toll-free numbers and can handle large amounts of calls at the same time.</span></span> <span data-ttu-id="13614-108">您的公司電話號碼必須成為服務號碼，因為稍後的步驟會指派給自動總機。</span><span class="sxs-lookup"><span data-stu-id="13614-108">Your company phone number needs to be a service number because it'll be assigned to an auto attendant in a later step.</span></span>
- <span data-ttu-id="13614-109">**訂閱者號碼** 這些號碼會用於一般使用者，讓他們可以撥打和接聽電話。</span><span class="sxs-lookup"><span data-stu-id="13614-109">**Subscriber numbers** These numbers are used for regular users so they can make and receive phone calls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13614-110">即使您想要使用現有的電話號碼，您也需要建立暫時電話號碼，並指派給公司的主要電話線和使用者。</span><span class="sxs-lookup"><span data-stu-id="13614-110">Even if you want to use your existing phone numbers, you need to create and assign temporary phone numbers to your company's main phone line and your users.</span></span> <span data-ttu-id="13614-111">您可以在稍後的步驟中，以現有的電話號碼取代這些暫住號碼。</span><span class="sxs-lookup"><span data-stu-id="13614-111">You'll be able to replace these temporary numbers with your existing phone numbers in a later step.</span></span>

> [!NOTE]
> <span data-ttu-id="13614-112">您的新電話號碼可能需要數小時才能在 Teams。</span><span class="sxs-lookup"><span data-stu-id="13614-112">It may take several hours for your new phone numbers to become available in Teams.</span></span>

<span data-ttu-id="13614-113">下列影片將說明如何在系統管理中心完成Teams步驟。</span><span class="sxs-lookup"><span data-stu-id="13614-113">The following video shows you how to complete these steps in the Teams admin center.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWENzQ]

## <a name="set-up-a-service-number"></a><span data-ttu-id="13614-114">設定服務號碼</span><span class="sxs-lookup"><span data-stu-id="13614-114">Set up a service number</span></span>

<span data-ttu-id="13614-115">您現在設定的服務號碼將在公司主要電話號碼的稍後步驟中使用。</span><span class="sxs-lookup"><span data-stu-id="13614-115">The service number you set up now will be used in a later step for your company's main phone number.</span></span>

1. <span data-ttu-id="13614-116">開啟 Microsoft Teams系統管理中心，然後使用全域系統管理員使用者登入 (這通常是您用來註冊帳戶Microsoft 365) 。</span><span class="sxs-lookup"><span data-stu-id="13614-116">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="13614-117">在左側流覽中，前往 <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**[語音** 電話  >  **數位，**</a>然後按一下 [**新增**。</span><span class="sxs-lookup"><span data-stu-id="13614-117">In the left navigation, go to <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Voice** > **Phone numbers**</a>, and then click **Add**.</span></span>
3. <span data-ttu-id="13614-118">輸入訂單名稱並新增描述。</span><span class="sxs-lookup"><span data-stu-id="13614-118">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="13614-119">在位置和數量頁面上，執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="13614-119">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="13614-120">在 **國家/地區下**，選取國家/地區。</span><span class="sxs-lookup"><span data-stu-id="13614-120">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="13614-121">在 **數位類型** 下，選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="13614-121">Under **Number type**, select one of the following options:</span></span>

        - <span data-ttu-id="13614-122">**自動 (付費)** 一般、非免付費的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="13614-122">**Auto attendant (Toll)** Regular, non-toll-free, phone number.</span></span> <span data-ttu-id="13614-123">長途費用會向來電者收取。</span><span class="sxs-lookup"><span data-stu-id="13614-123">Long distance fees are charged to the caller.</span></span>
        - <span data-ttu-id="13614-124">**自動 (免付費)** 撥打美國和加拿大 (免費電話) 或免費電話 () 電話號碼。</span><span class="sxs-lookup"><span data-stu-id="13614-124">**Auto attendant (Toll Free)** Toll-free (US and Canada) or freephone (UK) phone number.</span></span> <span data-ttu-id="13614-125">長途費用會向貴公司收取。</span><span class="sxs-lookup"><span data-stu-id="13614-125">Long distances fees are charged to your company.</span></span> <span data-ttu-id="13614-126">在選取此選項之前，您必須購買通訊信用額度。</span><span class="sxs-lookup"><span data-stu-id="13614-126">Before you can select this option, you need to purchase Communication Credits.</span></span> <span data-ttu-id="13614-127">若要詳細資訊，請參閱我需要購買哪些產品，以[使用Microsoft 365 商務語音？](what-to-buy.md)。</span><span class="sxs-lookup"><span data-stu-id="13614-127">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>

    3. <span data-ttu-id="13614-128">在 **數量下**，選取 **1**。</span><span class="sxs-lookup"><span data-stu-id="13614-128">Under **Quantity**, select **1**.</span></span>
        > [!NOTE]
        > <span data-ttu-id="13614-129">如果您收到 **訊息：您** 沒有足夠的授權要求更多這類號碼，請確定您購買的是 Business Voice 授權。</span><span class="sxs-lookup"><span data-stu-id="13614-129">If you get the message **You don't have enough licenses to request more numbers of this type**, make sure you've purchased Business Voice licenses.</span></span> <span data-ttu-id="13614-130">若要詳細資訊，請參閱我需要購買哪些產品，以[使用Microsoft 365 商務語音？](what-to-buy.md)。</span><span class="sxs-lookup"><span data-stu-id="13614-130">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
    4. <span data-ttu-id="13614-131">選擇位置 **或** 區碼 **，取決於您** 是想要使用位置的城市搜尋電話號碼，還是想要搜尋特定區碼中的號碼。</span><span class="sxs-lookup"><span data-stu-id="13614-131">Choose either **Location** or **Area code**, depending on whether you want to search for phone numbers using a location's city, or if you want to search for numbers in a specific area code.</span></span>
    5. <span data-ttu-id="13614-132">如果您 **選取位置**：</span><span class="sxs-lookup"><span data-stu-id="13614-132">If you select **Location**:</span></span>

        1. <span data-ttu-id="13614-133">輸入緊急位址位於 [設定緊急位置位置> 步驟 [](set-up-emergency-locations.md)中的城市，或如果您需要為另一個辦公室或家用辦公室建立新位置，請按一下 [**新增位置**> 。</span><span class="sxs-lookup"><span data-stu-id="13614-133">Type the city in which your emergency address is located in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
        2. <span data-ttu-id="13614-134">在 **區碼下**，選取區碼， **然後選取下** 一步以保留您的號碼。</span><span class="sxs-lookup"><span data-stu-id="13614-134">Under **Area code**, select an area code, and then select **Next** to reserve your number.</span></span>

    6. <span data-ttu-id="13614-135">如果您選取區 **碼，** 輸入要搜尋的區碼，然後 **選取下一** 步以保留您的號碼。</span><span class="sxs-lookup"><span data-stu-id="13614-135">If you select **Area code**, type the area code you want to search, and then select **Next** to reserve your number.</span></span>

5. <span data-ttu-id="13614-136">選取您想要的號碼。</span><span class="sxs-lookup"><span data-stu-id="13614-136">Select the number you want.</span></span> <span data-ttu-id="13614-137">您還有 10 分鐘的時間來選取電話號碼並下訂單。</span><span class="sxs-lookup"><span data-stu-id="13614-137">You have 10 minutes to select your phone number and place your order.</span></span> <span data-ttu-id="13614-138">如果您花的時間超過 10 分鐘，電話號碼會回到號碼庫。</span><span class="sxs-lookup"><span data-stu-id="13614-138">If you take more than 10 minutes, the phone number will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="13614-139">當您準備好要下單時，請按一下 [ **下單**，然後 **完成**</span><span class="sxs-lookup"><span data-stu-id="13614-139">When you're ready to place your order, click **Place order**, and then **Finish**</span></span>

## <a name="set-up-phone-numbers-for-your-users"></a><span data-ttu-id="13614-140">設定使用者的電話號碼</span><span class="sxs-lookup"><span data-stu-id="13614-140">Set up phone numbers for your users</span></span>

1. <span data-ttu-id="13614-141">開啟 Microsoft Teams系統管理中心，然後使用全域系統管理員使用者登入 (這通常是您用來註冊帳戶Microsoft 365) 。</span><span class="sxs-lookup"><span data-stu-id="13614-141">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="13614-142">在左側流覽中，前往 <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**[語音** 電話  >  **數位，**</a>然後按一下 [**新增**。</span><span class="sxs-lookup"><span data-stu-id="13614-142">In the left navigation, go to <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Voice** > **Phone numbers**</a>, and then click **Add**.</span></span>
3. <span data-ttu-id="13614-143">輸入訂單名稱並新增描述。</span><span class="sxs-lookup"><span data-stu-id="13614-143">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="13614-144">在位置和數量頁面上，執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="13614-144">On the Location and quantity page, do the following:</span></span>

    1. <span data-ttu-id="13614-145">在 **國家/地區下**，選取國家/地區。</span><span class="sxs-lookup"><span data-stu-id="13614-145">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="13614-146">在 **數位類型** 下，選取 **使用者 (訂閱) 。**</span><span class="sxs-lookup"><span data-stu-id="13614-146">Under **Number type**, select **User (subscriber)**.</span></span>
    3. <span data-ttu-id="13614-147">在 **數量** 下，輸入貴組織想要的數位數目。</span><span class="sxs-lookup"><span data-stu-id="13614-147">Under **Quantity**, enter the number of numbers that you want for your organization.</span></span>
    4. <span data-ttu-id="13614-148">選擇位置 **或** 區碼 **，取決於您** 是想要使用位置的城市搜尋電話號碼，還是想要搜尋特定區碼中的號碼。</span><span class="sxs-lookup"><span data-stu-id="13614-148">Choose either **Location** or **Area code**, depending on whether you want to search for phone numbers using a location's city, or if you want to search for numbers in a specific area code.</span></span>
    5. <span data-ttu-id="13614-149">如果您 **選取位置**：</span><span class="sxs-lookup"><span data-stu-id="13614-149">If you select **Location**:</span></span>

        1. <span data-ttu-id="13614-150">輸入緊急位址位於 [設定緊急位置位置> 步驟 [](set-up-emergency-locations.md)中的城市，或如果您需要為另一個辦公室或家用辦公室建立新位置，請按一下 [**新增位置**> 。</span><span class="sxs-lookup"><span data-stu-id="13614-150">Type the city in which your emergency address is located in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
        2. <span data-ttu-id="13614-151">在 **區碼下**，選取區碼， **然後選取下** 一步以保留您的號碼。</span><span class="sxs-lookup"><span data-stu-id="13614-151">Under **Area code**, select an area code, and then select **Next** to reserve your number.</span></span>

    6. <span data-ttu-id="13614-152">如果您選取區 **碼，** 輸入要搜尋的區碼，然後 **選取下一** 步以保留您的號碼。</span><span class="sxs-lookup"><span data-stu-id="13614-152">If you select **Area code**, type the area code you want to search, and then select **Next** to reserve your number.</span></span>
5. <span data-ttu-id="13614-153">選取您想要的數位。</span><span class="sxs-lookup"><span data-stu-id="13614-153">Select the numbers you want.</span></span> <span data-ttu-id="13614-154">您還有 10 分鐘的時間來選取電話號碼並下訂單。</span><span class="sxs-lookup"><span data-stu-id="13614-154">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="13614-155">如果您花的時間超過 10 分鐘，電話號碼會回到號碼庫。</span><span class="sxs-lookup"><span data-stu-id="13614-155">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="13614-156">當您準備好要下單時，請按一下 [ **下單**，然後 **完成**。</span><span class="sxs-lookup"><span data-stu-id="13614-156">When you're ready to place your order, click **Place order**, and then **Finish**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="13614-157">下一個步驟：指派授權給Teams使用者</span><span class="sxs-lookup"><span data-stu-id="13614-157">Next step: Assign licenses to Teams users</span></span>](set-up-licenses.md)

---
title: 設定Microsoft 365 商務語音資源帳戶
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
description: 瞭解如何設定與自動Microsoft 365 商務語音一起使用的資源帳戶。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76e91a650e9e72c21a39d292e32fe5ff8ecbf80b
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130342"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a><span data-ttu-id="6d6a3-103">步驟 4：設定商務語音資源帳戶</span><span class="sxs-lookup"><span data-stu-id="6d6a3-103">Step 4: Set up a Business Voice resource account</span></span>

<span data-ttu-id="6d6a3-104">在 Microsoft Teams中，每個自動電話機或通話佇列都需要資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-104">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="6d6a3-105">資源帳戶也可能被指派服務電話號碼。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-105">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="6d6a3-106">這是您將電話號碼指派給自動語音機和通話佇列，讓來自Teams的來電者能夠到達自動語音機或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-106">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

## <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="6d6a3-107">取得虛擬使用者授權</span><span class="sxs-lookup"><span data-stu-id="6d6a3-107">Obtain virtual user licenses</span></span>

<span data-ttu-id="6d6a3-108">資源帳戶需要授權才能使用自動電話機和通話佇列。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-108">Resource accounts require a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="6d6a3-109">您可以使用免費的虛擬使用者 *Microsoft 365 電話系統虛擬使用者* 授權。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-109">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span>

1. <span data-ttu-id="6d6a3-110">請Microsoft 365系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-110">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="6d6a3-111">前往 **帳單**  >  **購買服務**  >  **附加元件**  >  **查看所有附加元件產品**</span><span class="sxs-lookup"><span data-stu-id="6d6a3-111">Go to **Billing** > **Purchase services** > **Add-ons** > **See all Add-ons products**</span></span>
3. <span data-ttu-id="6d6a3-112">卷起到結尾以尋找Microsoft 365 電話系統 **– 虛擬使用者** 授權。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-112">Scroll to the end to find the **Microsoft 365 Phone System – Virtual User** license.</span></span> <span data-ttu-id="6d6a3-113">選取 **詳細** 資料，然後 **選取購買**。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-113">Select **Details**, then **Buy**.</span></span>
4. <span data-ttu-id="6d6a3-114">在授權購買頁面上，選取您想要的虛擬使用者授權數目。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-114">On the license purchase page, select the number of virtual user licenses you want.</span></span> <span data-ttu-id="6d6a3-115">針對您打算設定的每個自動電話機和通話佇列，您需要一個虛擬授權。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-115">You need one virtual license for each auto attendant and call queue you plan to set up.</span></span> <span data-ttu-id="6d6a3-116">我們建議您至少選取五個授權，以便日後輕鬆設定更多自動電話機和通話佇列，而不需要立即購買更多授權。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-116">We recommend selecting at least five licenses so you can easily set up more auto attendants and call queues in the future without having to purchase more licenses right away.</span></span>
5. <span data-ttu-id="6d6a3-117">取消 **勾選自動指派給沒有授權的所有使用者**。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-117">Uncheck **Automatically assign to all of your users with no licenses**.</span></span>
6. <span data-ttu-id="6d6a3-118">選取 **現在簽出**。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-118">Select **Check out now**.</span></span>
7. <span data-ttu-id="6d6a3-119">確認您的訂單， **選取下一** 步，然後 **下單**。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-119">Confirm your order, select **Next**, and then **Place order**.</span></span>

> [!NOTE]
> <span data-ttu-id="6d6a3-120">請記住，您仍必須  **購買授權** ，即使其成本為零。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-120">Keep in mind you must still  **Buy** the license even though it has a cost of zero.</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="6d6a3-121">建立資源帳戶</span><span class="sxs-lookup"><span data-stu-id="6d6a3-121">Create a resource account</span></span>

<span data-ttu-id="6d6a3-122">在您收到您的 Microsoft 365 電話系統 *- 虛擬使用者* 授權之後，您可以建立資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-122">After you've received your *Microsoft 365 Phone System - Virtual User* license, you can create your resource account.</span></span>

![新增資源帳戶使用者介面的螢幕擷取畫面](../media/resource-account-add.png)

1. <span data-ttu-id="6d6a3-124">在 Teams系統管理中心中，展開 **整個組織設定**，然後按一下 [**資源帳戶**。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-124">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>
2. <span data-ttu-id="6d6a3-125">選取 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-125">Select **Add**.</span></span>
3. <span data-ttu-id="6d6a3-126">在新增 **資源帳戶窗格中** ，填寫 **顯示名稱**，然後填入 **使用者名稱**。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-126">In the **Add resource account** pane, fill out **Display name**, and then **Username**.</span></span> <span data-ttu-id="6d6a3-127">選擇描述性顯示名稱 ，例如「主行自動助理」，以描述資源帳戶的用途。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-127">Choose a descriptive display name such as "Main line auto attendant" to describe the purpose of the resource account.</span></span>
4. <span data-ttu-id="6d6a3-128">在 **資源帳戶類型中**，選取自動 **助理**。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-128">In **Resource account type**, select **Auto attendant**.</span></span>
5. <span data-ttu-id="6d6a3-129">選取 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-129">Select **Save**.</span></span>

![資源帳戶清單的螢幕擷取畫面](../media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="6d6a3-131">指派授權</span><span class="sxs-lookup"><span data-stu-id="6d6a3-131">Assign a license</span></span>

<span data-ttu-id="6d6a3-132">建立資源帳戶之後，您需要指派一個Microsoft 365 電話系統 *- 虛擬* 使用者 *授權或電話系統* 授權。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-132">After you've created your resource account, you need to assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![系統管理中心指派授權使用者介面的螢幕擷取畫面Microsoft 365螢幕擷取畫面](../media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="6d6a3-134">在 Microsoft 365系統管理中心，前往 **使用者**  >  **活動使用者**。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-134">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>
2. <span data-ttu-id="6d6a3-135">選取您的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-135">Select your resource account.</span></span>
1. <span data-ttu-id="6d6a3-136">在 "**授權與應用程式"** 選項卡的 **"授權**" 下，選取 Microsoft 365 電話系統 -**虛擬使用者**。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-136">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>
1. <span data-ttu-id="6d6a3-137">選取 **儲存變更，** 然後 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-137">Select **Save changes** and then **Close**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="6d6a3-138">指派服務號碼</span><span class="sxs-lookup"><span data-stu-id="6d6a3-138">Assign a service number</span></span>

![指派服務編號使用者介面的螢幕擷取畫面](../media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="6d6a3-140">在 Teams系統管理中心，請前往整個 **組織設定**，然後前往 **資源帳戶**。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-140">In the Teams admin center, go to **Org-wide settings** and then **Resource accounts**.</span></span> 
1. <span data-ttu-id="6d6a3-141">選取您剛剛建立的資源帳戶，然後按一下 [ **指派/取消指派**> 。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-141">Select the resource account you just created, and then click **Assign/unassign**.</span></span>
1. <span data-ttu-id="6d6a3-142">在 電話 **數位類型** 下拉式下拉清單 **中，選擇** Online 。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-142">In the **Phone number type** dropdown, choose **Online**.</span></span>
1. <span data-ttu-id="6d6a3-143">在 **[已指派的電話號碼** > 方塊中，搜尋您想要使用的號碼，然後按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-143">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span> <span data-ttu-id="6d6a3-144">請務必包含國家/地區代碼 (例如 **+1** 250 555 0012) </span><span class="sxs-lookup"><span data-stu-id="6d6a3-144">Be sure to include the country code (for example, **+1** 250 555 0012)</span></span>
1. <span data-ttu-id="6d6a3-145">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-145">Click **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="6d6a3-146">由於已選取要新增號碼的自動話務員，因此不需要選取指派給下的自動電話機。</span><span class="sxs-lookup"><span data-stu-id="6d6a3-146">You don't need to select an auto attendant under **Assign to** because the auto attendant you want to add the number to is already selected.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6d6a3-147">下一個步驟：指派電話號碼給使用者</span><span class="sxs-lookup"><span data-stu-id="6d6a3-147">Next step: Assign phone numbers to your users</span></span>](set-up-assign-numbers.md)

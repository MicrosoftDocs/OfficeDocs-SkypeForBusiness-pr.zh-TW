---
title: 設定 Microsoft 365 商務語音資源帳戶
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
ms.openlocfilehash: df5001b6f757b407e96a473d302c79d837af957c
ms.sourcegitcommit: 38fa37d83704200911866cf017566fcb128ea2fe
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105165"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a><span data-ttu-id="9900e-103">步驟 4：設定商務語音資源帳戶</span><span class="sxs-lookup"><span data-stu-id="9900e-103">Step 4: Set up a Business Voice resource account</span></span>

<span data-ttu-id="9900e-104">資源帳戶不會指派給任何特定使用者。</span><span class="sxs-lookup"><span data-stu-id="9900e-104">Resource accounts aren't assigned to any specific user.</span></span> <span data-ttu-id="9900e-105">相反地，使用免費虛擬使用者授權的資源帳戶，會由裝置和服務在 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="9900e-105">Instead, resource accounts, which use a free virtual user license, are used by devices and services in Microsoft 365.</span></span> <span data-ttu-id="9900e-106">在 Microsoft Teams中，資源帳戶會指派電話號碼，然後與自動總機和通話佇列相關聯。</span><span class="sxs-lookup"><span data-stu-id="9900e-106">In Microsoft Teams, resource accounts are assigned phone numbers and are then associated with auto attendants and call queues.</span></span>

<span data-ttu-id="9900e-107">將資源帳戶與自動電話機和通話佇列建立關聯，您可以新增一或多個付費電話號碼或免付費電話號碼。</span><span class="sxs-lookup"><span data-stu-id="9900e-107">By associating resource accounts to auto attendants and call queues, you can add one or more toll or toll-free phone numbers to them.</span></span> <span data-ttu-id="9900e-108">例如，您可以將一個資源帳戶與付費號碼關聯到當地來電者的自動語音服務。</span><span class="sxs-lookup"><span data-stu-id="9900e-108">For example, you could associate one resource account with a toll number to an auto attendant for local callers.</span></span> <span data-ttu-id="9900e-109">針對長途通話，您可以將另一個資源帳戶與免付費號碼關聯到相同的自動電話機。</span><span class="sxs-lookup"><span data-stu-id="9900e-109">For long distance calls, you could associate another resource account with a toll-free number to the same auto attendant.</span></span>

<span data-ttu-id="9900e-110">本文中的各節將說明如何設定資源帳戶，然後為其指派電話號碼。</span><span class="sxs-lookup"><span data-stu-id="9900e-110">The sections in this article show you how to set up a resource account and then assign a phone number to it.</span></span> <span data-ttu-id="9900e-111">稍後，您將將資源帳戶與自動助理建立關聯。</span><span class="sxs-lookup"><span data-stu-id="9900e-111">Later on, you'll associate the resource account with an auto attendant.</span></span>

<span data-ttu-id="9900e-112">下列影片將說明如何在系統管理中心完成Teams步驟。</span><span class="sxs-lookup"><span data-stu-id="9900e-112">The following video shows you how to complete these steps in the Teams admin center.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OFYG]

## <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="9900e-113">取得虛擬使用者授權</span><span class="sxs-lookup"><span data-stu-id="9900e-113">Obtain virtual user licenses</span></span>

<span data-ttu-id="9900e-114">資源帳戶需要授權才能使用自動電話機和通話佇列。</span><span class="sxs-lookup"><span data-stu-id="9900e-114">Resource accounts require a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="9900e-115">您可以使用免費的虛擬使用者 *Microsoft 365 電話系統虛擬使用者* 授權。</span><span class="sxs-lookup"><span data-stu-id="9900e-115">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span>

> [!NOTE]
> <span data-ttu-id="9900e-116">如果您註冊了商務語音試用期間，您只需要執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="9900e-116">You should only need to perform the following steps if you've signed up for a Business Voice trial period.</span></span> <span data-ttu-id="9900e-117">如果您購買 Business Voice 授權，虛擬授權應該已經適用于您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="9900e-117">If you purchased Business Voice licenses, virtual licenses should already be applied to your account.</span></span> 
>
> <span data-ttu-id="9900e-118">若要查看您是否已經有虛擬授權，請Microsoft 365全域系統管理員許可權的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="9900e-118">To see if you already have virtual licenses, log into Microsoft 365 using an account with Global admin permissions.</span></span> <span data-ttu-id="9900e-119">然後前往帳單> [您的產品](https://admin.microsoft.com/Adminportal/Home#/subscriptions)。</span><span class="sxs-lookup"><span data-stu-id="9900e-119">Then go to Billing > [Your products](https://admin.microsoft.com/Adminportal/Home#/subscriptions).</span></span> <span data-ttu-id="9900e-120">如果您有虛擬授權，這些授權會顯示為 Microsoft 365 電話系統 **- 虛擬使用者**。</span><span class="sxs-lookup"><span data-stu-id="9900e-120">If you have virtual licenses, they'll appear as **Microsoft 365 Phone System - Virtual User**.</span></span>

1. <span data-ttu-id="9900e-121">開啟 Microsoft 365 系統管理中心，然後使用全域系統管理員的使用者登入 (通常是您用來註冊 Microsoft 365) 。</span><span class="sxs-lookup"><span data-stu-id="9900e-121">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="9900e-122">在左側流覽窗格中，前往帳單 <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">\*\*\*\*  >  **購買服務**</a>附加元件  >    >  **查看所有附加元件產品**。</span><span class="sxs-lookup"><span data-stu-id="9900e-122">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">**Billing** > **Purchase services**</a> > **Add-ons** > **See all Add-ons products**.</span></span>
3. <span data-ttu-id="9900e-123">卷起到最後以尋找Microsoft 365 電話系統 **– 虛擬使用者** 授權。</span><span class="sxs-lookup"><span data-stu-id="9900e-123">Scroll to the end to find the **Microsoft 365 Phone System – Virtual User** license.</span></span> <span data-ttu-id="9900e-124">選取 **詳細** 資料，然後 **選取購買**。</span><span class="sxs-lookup"><span data-stu-id="9900e-124">Select **Details**, then **Buy**.</span></span>
4. <span data-ttu-id="9900e-125">在授權購買頁面上，選取您想要的虛擬使用者授權數目。</span><span class="sxs-lookup"><span data-stu-id="9900e-125">On the license purchase page, select the number of virtual user licenses you want.</span></span> <span data-ttu-id="9900e-126">針對您打算設定的每個自動電話機和通話佇列，您需要一個虛擬授權。</span><span class="sxs-lookup"><span data-stu-id="9900e-126">You need one virtual license for each auto attendant and call queue you plan to set up.</span></span> <span data-ttu-id="9900e-127">我們建議您至少選取五個授權，以便日後輕鬆設定更多自動電話機和通話佇列，而不需要立即購買更多授權。</span><span class="sxs-lookup"><span data-stu-id="9900e-127">We recommend selecting at least five licenses so you can easily set up more auto attendants and call queues in the future without having to purchase more licenses right away.</span></span>
5. <span data-ttu-id="9900e-128">取消 **勾選自動指派給沒有授權的所有使用者**。</span><span class="sxs-lookup"><span data-stu-id="9900e-128">Uncheck **Automatically assign to all of your users with no licenses**.</span></span>
6. <span data-ttu-id="9900e-129">選取 **現在簽出**。</span><span class="sxs-lookup"><span data-stu-id="9900e-129">Select **Check out now**.</span></span>
7. <span data-ttu-id="9900e-130">確認您的訂單， **選取下一** 步，然後 **下單**。</span><span class="sxs-lookup"><span data-stu-id="9900e-130">Confirm your order, select **Next**, and then **Place order**.</span></span>

> [!NOTE]
> <span data-ttu-id="9900e-131">請記住，您仍必須  **購買授權** ，即使其成本為零。</span><span class="sxs-lookup"><span data-stu-id="9900e-131">Keep in mind you must still  **Buy** the license even though it has a cost of zero.</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="9900e-132">建立資源帳戶</span><span class="sxs-lookup"><span data-stu-id="9900e-132">Create a resource account</span></span>

<span data-ttu-id="9900e-133">在您收到您的 Microsoft 365 電話系統 *- 虛擬使用者* 授權之後，您可以建立您的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="9900e-133">After you've received your *Microsoft 365 Phone System - Virtual User* license, you can create your resource account.</span></span>

![新增資源帳戶使用者介面的螢幕擷取畫面](../media/resource-account-add.png)

1. <span data-ttu-id="9900e-135">開啟 Microsoft Teams系統管理中心，然後使用全域系統管理員使用者登入 (這通常是您用來註冊帳戶Microsoft 365) 。</span><span class="sxs-lookup"><span data-stu-id="9900e-135">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="9900e-136">在左側流覽窗格中，前往 <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**全組織** 設定  >  **資源帳戶**</a>。</span><span class="sxs-lookup"><span data-stu-id="9900e-136">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
3. <span data-ttu-id="9900e-137">選取 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="9900e-137">Select **Add**.</span></span>
4. <span data-ttu-id="9900e-138">在新增 **資源帳戶窗格中** ，填寫 **顯示名稱**，然後填入 **使用者名稱**。</span><span class="sxs-lookup"><span data-stu-id="9900e-138">In the **Add resource account** pane, fill out **Display name**, and then **Username**.</span></span> <span data-ttu-id="9900e-139">選擇描述性顯示名稱 ，例如「主行自動助理」，以描述資源帳戶的用途。</span><span class="sxs-lookup"><span data-stu-id="9900e-139">Choose a descriptive display name such as "Main line auto attendant" to describe the purpose of the resource account.</span></span>
5. <span data-ttu-id="9900e-140">在 **資源帳戶類型中**，選取自動 **助理**。</span><span class="sxs-lookup"><span data-stu-id="9900e-140">In **Resource account type**, select **Auto attendant**.</span></span>
6. <span data-ttu-id="9900e-141">選取 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="9900e-141">Select **Save**.</span></span>

![資源帳戶清單的螢幕擷取畫面](../media/resource-accounts-auto-attendant-only-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="9900e-143">指派授權</span><span class="sxs-lookup"><span data-stu-id="9900e-143">Assign a license</span></span>

<span data-ttu-id="9900e-144">建立資源帳戶之後，您需要指派一個Microsoft 365 電話系統 *- 虛擬* 使用者 *授權或電話系統* 授權。</span><span class="sxs-lookup"><span data-stu-id="9900e-144">After you've created your resource account, you need to assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![指派授權使用者介面的螢幕擷取畫面Microsoft 365 系統管理中心](../media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="9900e-146">開啟 Microsoft 365 系統管理中心，然後使用全域系統管理員的使用者登入 (通常是您用來註冊 Microsoft 365) 。</span><span class="sxs-lookup"><span data-stu-id="9900e-146">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="9900e-147">在左側流覽窗格中，前往使用者 <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">\*\*\*\*  >  **活動使用者**</a>。</span><span class="sxs-lookup"><span data-stu-id="9900e-147">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">**Users** > **Active users**</a>.</span></span>
1. <span data-ttu-id="9900e-148">選取您的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="9900e-148">Select your resource account.</span></span>
1. <span data-ttu-id="9900e-149">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span><span class="sxs-lookup"><span data-stu-id="9900e-149">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>
1. <span data-ttu-id="9900e-150">選取 **儲存變更，** 然後 **選取** 關閉 。</span><span class="sxs-lookup"><span data-stu-id="9900e-150">Select **Save changes** and then **Close**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="9900e-151">指派服務編號</span><span class="sxs-lookup"><span data-stu-id="9900e-151">Assign a service number</span></span>

![指派服務編號使用者介面的螢幕擷取畫面](../media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="9900e-153">開啟 Microsoft Teams系統管理中心，然後使用全域系統管理員使用者登入 (這通常是您用來註冊帳戶Microsoft 365) 。</span><span class="sxs-lookup"><span data-stu-id="9900e-153">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="9900e-154">在左側流覽窗格中，前往 <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**全組織** 設定  >  **資源帳戶**</a>。</span><span class="sxs-lookup"><span data-stu-id="9900e-154">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
1. <span data-ttu-id="9900e-155">選取您剛剛建立的資源帳戶，然後按一下 [ **指派/取消指派**> 。</span><span class="sxs-lookup"><span data-stu-id="9900e-155">Select the resource account you just created, and then click **Assign/unassign**.</span></span>
1. <span data-ttu-id="9900e-156">在 電話 **數位類型** 下拉式下拉清單 **中，選擇** Online 。</span><span class="sxs-lookup"><span data-stu-id="9900e-156">In the **Phone number type** dropdown, choose **Online**.</span></span>
1. <span data-ttu-id="9900e-157">在 **[指派的電話號碼>** 方塊中，搜尋您用的電話號碼，然後按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="9900e-157">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span> <span data-ttu-id="9900e-158">請務必包含國家/地區代碼 (例如 **+1** 250 555 0012) </span><span class="sxs-lookup"><span data-stu-id="9900e-158">Be sure to include the country code (for example, **+1** 250 555 0012)</span></span>
1. <span data-ttu-id="9900e-159">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="9900e-159">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9900e-160">下一個步驟：指派電話號碼給使用者</span><span class="sxs-lookup"><span data-stu-id="9900e-160">Next step: Assign phone numbers to your users</span></span>](set-up-assign-numbers.md)

---
title: 設定運算子連接
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 深入瞭解如何設定運算子連接。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4f4ec3d1d7cf39402da562e5939d794ac9f1624
ms.sourcegitcommit: 1b057bfcc3207960b956962845fd5051afe91722
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/15/2021
ms.locfileid: "52947575"
---
# <a name="configure-operator-connect"></a><span data-ttu-id="b5be2-103">設定運算子連接</span><span class="sxs-lookup"><span data-stu-id="b5be2-103">Configure Operator Connect</span></span>

>[!NOTE]
><span data-ttu-id="b5be2-104">運算子連接目前僅適用于公用 **預覽** 版。</span><span class="sxs-lookup"><span data-stu-id="b5be2-104">Operator Connect is currently available only in **public preview**.</span></span> <span data-ttu-id="b5be2-105">公開預覽可讓您測試即將推出的功能，並提供意見回饋。</span><span class="sxs-lookup"><span data-stu-id="b5be2-105">Public preview allows you to test upcoming features and provide feedback.</span></span> <span data-ttu-id="b5be2-106">公開預覽中包含的功能可能不完整、可能會變更，且 Office 365 政府雲端不支援。</span><span class="sxs-lookup"><span data-stu-id="b5be2-106">Features included in public preview may not be complete, may undergo changes, and are not supported in Office 365 Government Clouds.</span></span>

<span data-ttu-id="b5be2-107">本文將說明如何設定運算子連接。</span><span class="sxs-lookup"><span data-stu-id="b5be2-107">This article describes how to configure Operator Connect.</span></span> <span data-ttu-id="b5be2-108">在配置運算子連接之前，請務必閱讀運算子 [連接](operator-connect-plan.md) 方案，以瞭解先決條件和授權的資訊。</span><span class="sxs-lookup"><span data-stu-id="b5be2-108">Before configuring Operator Connect, be sure to read [Plan for Operator Connect](operator-connect-plan.md) for information about prerequisites and licensing.</span></span>

## <a name="enable-an-operator"></a><span data-ttu-id="b5be2-109">啟用運算子</span><span class="sxs-lookup"><span data-stu-id="b5be2-109">Enable an operator</span></span>

<span data-ttu-id="b5be2-110">您可以在 Teams 系統管理中心啟用、編輯及移除運算子。</span><span class="sxs-lookup"><span data-stu-id="b5be2-110">You can enable, edit, and remove operators in the Teams Admin Center.</span></span> <span data-ttu-id="b5be2-111">在左側流覽窗格中，前往語音> **運算子**。</span><span class="sxs-lookup"><span data-stu-id="b5be2-111">In the left navigation pane, go to **Voice > Operators**.</span></span>

<span data-ttu-id="b5be2-112">若要啟用運算子：</span><span class="sxs-lookup"><span data-stu-id="b5be2-112">To enable an operator:</span></span>

1. <span data-ttu-id="b5be2-113">**選擇運算子。**</span><span class="sxs-lookup"><span data-stu-id="b5be2-113">**Choose an operator.**</span></span> <span data-ttu-id="b5be2-114">在 " **所有運算子"** 的 Tab 中，根據地區或服務篩選可用的運算子，以尋找適合您語音需求的運算子。</span><span class="sxs-lookup"><span data-stu-id="b5be2-114">In the **All operators** tab, filter available operators by region or service to find the right operator for your voice needs.</span></span> <span data-ttu-id="b5be2-115">然後選取您想要啟用的運算子。</span><span class="sxs-lookup"><span data-stu-id="b5be2-115">Then select the operator you want to enable.</span></span>  

2. <span data-ttu-id="b5be2-116">**選取國家/地區。**</span><span class="sxs-lookup"><span data-stu-id="b5be2-116">**Select countries.**</span></span> <span data-ttu-id="b5be2-117">在 **運算子設定** 下，選取您想要使用所選運算子啟用的國家/地區。</span><span class="sxs-lookup"><span data-stu-id="b5be2-117">Under **Operator settings**, select the countries you want to enable with your selected operator.</span></span>

3. <span data-ttu-id="b5be2-118">**提供連絡人資訊 (選) 。**</span><span class="sxs-lookup"><span data-stu-id="b5be2-118">**Provide contact information (optional).**</span></span> <span data-ttu-id="b5be2-119">如果您想要讓接線員連上運算子 Connect 的其他資訊，請勾選該方塊，並提供您的連絡人資訊。</span><span class="sxs-lookup"><span data-stu-id="b5be2-119">If you want operators to contact you with additional information about Operator Connect, check the box and provide your contact information.</span></span>  

4. <span data-ttu-id="b5be2-120">**接受資料傳輸通知。**</span><span class="sxs-lookup"><span data-stu-id="b5be2-120">**Accept the data transfer notice.**</span></span>

5. <span data-ttu-id="b5be2-121">**新增運算子。**</span><span class="sxs-lookup"><span data-stu-id="b5be2-121">**Add your operator.**</span></span> <span data-ttu-id="b5be2-122">選取 **新增為我的運算子** 以儲存。</span><span class="sxs-lookup"><span data-stu-id="b5be2-122">Select **Add as my operator** to save.</span></span>

## <a name="set-up-phone-numbers"></a><span data-ttu-id="b5be2-123">設定電話號碼</span><span class="sxs-lookup"><span data-stu-id="b5be2-123">Set up phone numbers</span></span>

<span data-ttu-id="b5be2-124">您設定電話號碼的方式取決於您要設定新使用者的電話號碼，或移動 Microsoft 通話方案或直接路由的現有號碼。</span><span class="sxs-lookup"><span data-stu-id="b5be2-124">How you set up phone numbers depends on whether you're setting up numbers for new users, or moving existing numbers from either Microsoft Calling Plans or Direct Routing.</span></span>

- <span data-ttu-id="b5be2-125">如果您需要取得新使用者的電話號碼，請參閱取得新 Teams [使用者的電話號碼](#acquire-numbers-for-new-teams-users)。</span><span class="sxs-lookup"><span data-stu-id="b5be2-125">If you need to acquire phone numbers for new users, see [Acquire numbers for new Teams users](#acquire-numbers-for-new-teams-users).</span></span>

- <span data-ttu-id="b5be2-126">如果您想要將現有的號碼從通話方案移至運算子連接，請參閱將號碼從通話方案移至 [運算子連接](#move-numbers-from-calling-plans-to-operator-connect)。</span><span class="sxs-lookup"><span data-stu-id="b5be2-126">If you want to move existing numbers from Calling Plans to Operator Connect, see [Move numbers from Calling Plans to Operator Connect](#move-numbers-from-calling-plans-to-operator-connect).</span></span>

- <span data-ttu-id="b5be2-127">如果您想要將現有號碼從直接路由移至運算子連接，請參閱將號碼從直接路由 [移至運算子連接](#move-numbers-from-direct-routing-to-operator-connect)。</span><span class="sxs-lookup"><span data-stu-id="b5be2-127">If you want to move existing numbers from Direct Routing to Operator Connect, see [Move numbers from Direct Routing to Operator Connect](#move-numbers-from-direct-routing-to-operator-connect).</span></span>

>[!IMPORTANT]
><span data-ttu-id="b5be2-128">**緊急位址：** 與緊急位址相關聯的電話號碼是由您的接線員管理。</span><span class="sxs-lookup"><span data-stu-id="b5be2-128">**Emergency addresses:** Phone numbers associated with emergency addresses are managed by your operator.</span></span> <span data-ttu-id="b5be2-129">在 Teams 系統管理中心建立緊急位址後，您的接線員會指派電話號碼給這些緊急位址。</span><span class="sxs-lookup"><span data-stu-id="b5be2-129">Once you create emergency addresses in the Teams admin center, your operator will assign phone numbers to those emergency addresses.</span></span> <span data-ttu-id="b5be2-130">若要變更緊急位址及其指派的電話號碼，請與您的接線員聯繫。</span><span class="sxs-lookup"><span data-stu-id="b5be2-130">To make changes to emergency addresses and their assigned phone numbers, contact your operator.</span></span>

### <a name="acquire-numbers-for-new-teams-users"></a><span data-ttu-id="b5be2-131">取得新 Teams 使用者的數位</span><span class="sxs-lookup"><span data-stu-id="b5be2-131">Acquire numbers for new Teams users</span></span>

<span data-ttu-id="b5be2-132">若要取得新 Teams 使用者的數位，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b5be2-132">To acquire numbers for new Teams users, follow these steps:</span></span>

1. <span data-ttu-id="b5be2-133">**指派電話系統授權。**</span><span class="sxs-lookup"><span data-stu-id="b5be2-133">**Assign a Phone System license.**</span></span> <span data-ttu-id="b5be2-134">您可以從 Microsoft 365 系統管理中心或 PowerShell 指派電話系統授權給使用者。</span><span class="sxs-lookup"><span data-stu-id="b5be2-134">You can assign a Phone System license to your users from the Microsoft 365 admin center or using PowerShell.</span></span> <span data-ttu-id="b5be2-135">詳細資訊，請參閱指派 [Teams 附加元件授權給使用者](teams-add-on-licensing/assign-teams-add-on-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="b5be2-135">For more information, see [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>

2. <span data-ttu-id="b5be2-136">**請確定您目前使用 Teams 模式。**</span><span class="sxs-lookup"><span data-stu-id="b5be2-136">**Make sure you're in Teams only mode.**</span></span> <span data-ttu-id="b5be2-137">若要檢查貴組織是否位於 Teams 模式，請在 Teams 系統管理中心，前往 Teams 升級> **全組織設定**。</span><span class="sxs-lookup"><span data-stu-id="b5be2-137">To check if your organization is in Teams only mode, in the Teams admin center, go to **Org-wide settings > Teams upgrade**.</span></span> <span data-ttu-id="b5be2-138">若要檢查使用者是否位於 Teams 模式，請前往使用者 **並選取** 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="b5be2-138">To check if a user is in Teams only mode, go to **Users** and select a user account.</span></span> <span data-ttu-id="b5be2-139">在帳戶 **選項卡** 的 **Teams 升級下** ，確認您的共存模式已設定為'僅 Teams'。</span><span class="sxs-lookup"><span data-stu-id="b5be2-139">In the **Account** tab, under **Teams upgrade,** verify that your coexistence mode is set to 'Teams only.'</span></span>

3. <span data-ttu-id="b5be2-140">**建立及驗證緊急位址。**</span><span class="sxs-lookup"><span data-stu-id="b5be2-140">**Create and validate emergency addresses.**</span></span> <span data-ttu-id="b5be2-141">在 Teams 系統管理中心，前往緊急> **位置設定** 緊急位址。</span><span class="sxs-lookup"><span data-stu-id="b5be2-141">In the Teams admin center, go to **Locations > Emergency addresses** to set up emergency addresses.</span></span> <span data-ttu-id="b5be2-142">若要深入瞭解，請參閱 [新增、變更或移除貴組織的緊急位置](add-change-remove-emergency-location-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="b5be2-142">To learn more, see [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md).</span></span>

4. <span data-ttu-id="b5be2-143">**取得數位。**</span><span class="sxs-lookup"><span data-stu-id="b5be2-143">**Acquire numbers.**</span></span> <span data-ttu-id="b5be2-144">請前往您的接線員網站訂購及取得電話號碼。</span><span class="sxs-lookup"><span data-stu-id="b5be2-144">Go to your operator's website to order and acquire phone numbers.</span></span> <span data-ttu-id="b5be2-145">有關運算子網站的清單 [，請參閱運算子](#operators)。</span><span class="sxs-lookup"><span data-stu-id="b5be2-145">For a list of operator websites, see [Operators](#operators).</span></span> <span data-ttu-id="b5be2-146">您必須提供租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="b5be2-146">You'll need to provide your tenant ID.</span></span> <span data-ttu-id="b5be2-147">如果您不知道您的租使用者識別碼，請參閱尋找您的 [Microsoft 365 租使用者識別碼](/onedrive/find-your-office-365-tenant-id) 以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="b5be2-147">If you don't know your tenant ID, see [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id) for more information.</span></span>

5. <span data-ttu-id="b5be2-148">**指派數位。**</span><span class="sxs-lookup"><span data-stu-id="b5be2-148">**Assign numbers.**</span></span> <span data-ttu-id="b5be2-149">您的接線員完成訂單後，就會將號碼上傳至您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="b5be2-149">Once your operator completes the order, they'll upload numbers to your tenant.</span></span> <span data-ttu-id="b5be2-150">您可以流覽 Teams 系統管理中心中的號碼和提供者，> **電話號碼**。</span><span class="sxs-lookup"><span data-stu-id="b5be2-150">You can view the numbers and the provider in the Teams admin center by going to **Voice > Phone numbers**.</span></span> <span data-ttu-id="b5be2-151">使用 Teams 系統管理中心或 PowerShell 指派號碼給使用者。</span><span class="sxs-lookup"><span data-stu-id="b5be2-151">Assign numbers to users by using the Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="b5be2-152">詳細資訊，請參閱指派 [數位](#assign-numbers)。</span><span class="sxs-lookup"><span data-stu-id="b5be2-152">For more information, see [Assign numbers](#assign-numbers).</span></span>
 

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a><span data-ttu-id="b5be2-153">將號碼從通話方案移至運算子連接</span><span class="sxs-lookup"><span data-stu-id="b5be2-153">Move numbers from Calling Plans to Operator Connect</span></span>

1. <span data-ttu-id="b5be2-154">請連連您的接線員，將您的號碼移植到運算子 Connect。</span><span class="sxs-lookup"><span data-stu-id="b5be2-154">Contact your operator to port your numbers to Operator Connect.</span></span> <span data-ttu-id="b5be2-155">請參閱 [運算子](#operators) 以尋找您的運算子網站。</span><span class="sxs-lookup"><span data-stu-id="b5be2-155">See [Operators](#operators) to find your operator's website.</span></span>

2. <span data-ttu-id="b5be2-156">您的接線員完成移移訂單之後，您可以取消為使用者的通話方案電話號碼進行分配，並移除通話方案授權。</span><span class="sxs-lookup"><span data-stu-id="b5be2-156">After your operator completes the porting order, you can unassign your users' Calling Plan phone numbers, and remove the Calling Plan License.</span></span> <span data-ttu-id="b5be2-157">然後，您的運算子可以將數位上傳到您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="b5be2-157">Then, your operator can upload the numbers to your tenant.</span></span>

3. <span data-ttu-id="b5be2-158">使用 Teams 系統管理中心或 PowerShell 將號碼指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="b5be2-158">Assign Operator Connect numbers to users by using the Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="b5be2-159">詳細資訊，請參閱指派 [數位](#assign-numbers)。</span><span class="sxs-lookup"><span data-stu-id="b5be2-159">For more information, see [Assign numbers](#assign-numbers).</span></span>

 
### <a name="move-numbers-from-direct-routing-to-operator-connect"></a><span data-ttu-id="b5be2-160">將號碼從直接路由移至運算子連接</span><span class="sxs-lookup"><span data-stu-id="b5be2-160">Move numbers from Direct Routing to Operator Connect</span></span>

1. <span data-ttu-id="b5be2-161">從使用者移除現有電話號碼，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b5be2-161">Remove the existing telephone number from the user as follows:</span></span>  

   <span data-ttu-id="b5be2-162">執行下列 PowerShell 命令以取得現有的 On-prem Line URI：</span><span class="sxs-lookup"><span data-stu-id="b5be2-162">Get the existing On-prem Line URI by running the following PowerShell command:</span></span>

   ```
   Get-CsOnlineUser -Identity <user> | select OnPremLineURI 
   ```

   <span data-ttu-id="b5be2-163">執行下列 PowerShell 命令以移除 On-prem Line URI：</span><span class="sxs-lookup"><span data-stu-id="b5be2-163">Remove the On-prem Line URI by running the following PowerShell command:</span></span>  

   ```
   Set-CsUser -identity <user> - OnPremLineURI $null 
   ```

2. <span data-ttu-id="b5be2-164">移除任何與使用者相關聯的 PSTNUsage，否則通話會路由至 PSTN 使用量中指定的閘道。</span><span class="sxs-lookup"><span data-stu-id="b5be2-164">Remove any PSTNUsage associated with your users, otherwise calls will be routed to the gateway specified in the PSTN Usage.</span></span> <span data-ttu-id="b5be2-165">若要瞭解如何移除 PSTN 使用量，請參閱 [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="b5be2-165">To learn how to remove PSTN usage, see [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps).</span></span>

3. <span data-ttu-id="b5be2-166">請前往您的接線員網站訂購及取得電話號碼。</span><span class="sxs-lookup"><span data-stu-id="b5be2-166">Go to your operator's website to order and acquire phone numbers.</span></span> <span data-ttu-id="b5be2-167">有關運算子網站的清單 [，請參閱運算子](#operators)。</span><span class="sxs-lookup"><span data-stu-id="b5be2-167">For a list of operator websites, see [Operators](#operators).</span></span> <span data-ttu-id="b5be2-168">您必須提供租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="b5be2-168">You'll need to provide your tenant ID.</span></span> <span data-ttu-id="b5be2-169">如果您不知道您的租使用者識別碼，請參閱尋找您的 [Microsoft 365 租使用者識別碼](/onedrive/find-your-office-365-tenant-id) 以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="b5be2-169">If you don't know your tenant ID, see [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id) for more information.</span></span>

4. <span data-ttu-id="b5be2-170">您的接線員完成訂單後，就會將號碼上傳至您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="b5be2-170">Once your operator completes the order, they'll upload numbers to your tenant.</span></span> <span data-ttu-id="b5be2-171">您可以流覽 Teams 系統管理中心中的號碼和提供者，> **電話號碼**。</span><span class="sxs-lookup"><span data-stu-id="b5be2-171">You can view the numbers and the provider in the Teams admin center by going to **Voice > Phone numbers**.</span></span> <span data-ttu-id="b5be2-172">使用 Teams 系統管理中心或 PowerShell 將號碼指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="b5be2-172">Assign Operator Connect numbers to users by using the Teams admin center or by using  PowerShell.</span></span> <span data-ttu-id="b5be2-173">詳細資訊，請參閱指派 [數位](#assign-numbers)。</span><span class="sxs-lookup"><span data-stu-id="b5be2-173">For more information, see [Assign numbers](#assign-numbers).</span></span>

   

### <a name="assign-numbers"></a><span data-ttu-id="b5be2-174">指派數位</span><span class="sxs-lookup"><span data-stu-id="b5be2-174">Assign numbers</span></span>

<span data-ttu-id="b5be2-175">無論您是新增 Teams 使用者，或將現有使用者移動至 Operator Connect，指派號碼的步驟如下：</span><span class="sxs-lookup"><span data-stu-id="b5be2-175">Whether you're adding new Teams users or moving existing users to Operator Connect, the steps for assigning numbers are as follows:</span></span>

<span data-ttu-id="b5be2-176">若要使用 Teams 系統管理中心指派號碼，請前往 **電話號碼**。</span><span class="sxs-lookup"><span data-stu-id="b5be2-176">To assign numbers by using the Teams admin center, go to **Phone numbers**.</span></span> <span data-ttu-id="b5be2-177">步驟與指派通話方案號碼的步驟相同。</span><span class="sxs-lookup"><span data-stu-id="b5be2-177">The steps are the same as assigning numbers for Calling Plans.</span></span> <span data-ttu-id="b5be2-178">詳細資訊，請參閱 [指派電話號碼給使用者](assign-change-or-remove-a-phone-number-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="b5be2-178">For more information, see [Assign a phone number to a user](assign-change-or-remove-a-phone-number-for-a-user.md).</span></span>

<span data-ttu-id="b5be2-179">若要使用 PowerShell 指派數位，請使用 Set-CsOnlineVoiceUser Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b5be2-179">To assign numbers by using PowerShell, use the Set-CsOnlineVoiceUser cmdlet as follows:</span></span>

```
Set-CsOnlineVoiceUser -Identity <user>  -TelephoneNumber <phone number> 
```

<span data-ttu-id="b5be2-180">例如：</span><span class="sxs-lookup"><span data-stu-id="b5be2-180">For example:</span></span>

```
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

<span data-ttu-id="b5be2-181">若要瞭解如何指派電話號碼給使用者，請參閱指派、變更或移除使用者 [的電話號碼](assign-change-or-remove-a-phone-number-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="b5be2-181">For more information about how to assign phone numbers to your users, see [Assign, change, or remove a phone number for a user](assign-change-or-remove-a-phone-number-for-a-user.md).</span></span>



## <a name="manage-your-operators"></a><span data-ttu-id="b5be2-182">管理運算子</span><span class="sxs-lookup"><span data-stu-id="b5be2-182">Manage your operators</span></span>

<span data-ttu-id="b5be2-183">在 "我的運算子" 選項卡中，您可以查看運算子及其狀態，並變更下列選取專案：</span><span class="sxs-lookup"><span data-stu-id="b5be2-183">From the My operators tab, you can view your operators and their status and make the following changes to your selections:</span></span>  

- <span data-ttu-id="b5be2-184">根據國家/地區管理運算子服務</span><span class="sxs-lookup"><span data-stu-id="b5be2-184">Manage operator services by country</span></span>
- <span data-ttu-id="b5be2-185">暫停運算子</span><span class="sxs-lookup"><span data-stu-id="b5be2-185">Suspend an operator</span></span>
- <span data-ttu-id="b5be2-186">移除運算子</span><span class="sxs-lookup"><span data-stu-id="b5be2-186">Remove an operator</span></span>

> [!NOTE]
> <span data-ttu-id="b5be2-187">在將接線員從貴組織或國家/地區移除之前，您必須移除指派給組織或國家/地區使用者的所有電話號碼，並請聯絡接線員以釋出號碼。</span><span class="sxs-lookup"><span data-stu-id="b5be2-187">Before removing an operator from your organization or from a country, you must remove all phone numbers assigned to users in the organization or country and contact the operator to release the numbers.</span></span>

## <a name="operators"></a><span data-ttu-id="b5be2-188">運算元</span><span class="sxs-lookup"><span data-stu-id="b5be2-188">Operators</span></span>

<span data-ttu-id="b5be2-189">您可以到此處連結的網站，從下列運算子取得電話號碼：</span><span class="sxs-lookup"><span data-stu-id="b5be2-189">You can acquire phone numbers from the following operators by going to the websites linked here:</span></span>


|<span data-ttu-id="b5be2-190">運算元</span><span class="sxs-lookup"><span data-stu-id="b5be2-190">Operator</span></span>  |<span data-ttu-id="b5be2-191">運算子網站</span><span class="sxs-lookup"><span data-stu-id="b5be2-191">Operator website</span></span>  |
|---------|---------|
|`BT`     |     https://www.globalservices.bt.com/en/aboutus/operator-connect        |
|`Deutsche Telekom`     |   https://cloud.telekom.de/de/blog/cloud-software/microsoft-teams-operator-connect      |
|`Intrado`     | https://insight.intrado.com/operator-connect       |
|`NTT`     |  https://www.hello.global.ntt/operator-connect       |
|`NuWave`     |   https://ipilot.io/microsoft-operator-connect/   |
|`Orange Business Services`     | https://www.orange-business.com/en/blogs/operator-connect-orange-and-microsoft-streamline-calling-for-teams-users        |
|`Pure IP`    | https://info.pure-ip.com/operator-connect        |
|`Rogers`    | https://www.rogers.com/business/products-and-solutions/microsoft-365-business-voice        |
|`TATA Communications`     |  https://www.tatacommunications.com/solutions/unified-communications/unified-communications-as-a-service/microsoft-teams-solutions/       |
|`Telenor`     | https://www.telenor.no/bedrift/telefoni/teams/operator-connect        |
|`Verizon`     |  https://www.verizon.com/business/resources/lp/operator-connect       |

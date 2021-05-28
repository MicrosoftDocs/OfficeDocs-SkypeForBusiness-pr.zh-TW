---
title: 設定運算子連線
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
description: 深入瞭解如何設定運算子連線。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e82c862810448552bb9d2dc2d721815b5db43f55
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689890"
---
# <a name="configure-operator-connect"></a><span data-ttu-id="7768f-103">設定運算子連線</span><span class="sxs-lookup"><span data-stu-id="7768f-103">Configure Operator Connect</span></span>

>[!NOTE]
><span data-ttu-id="7768f-104">運算子連線目前僅適用于公用 **預覽**。</span><span class="sxs-lookup"><span data-stu-id="7768f-104">Operator Connect is currently available only in **public preview**.</span></span> <span data-ttu-id="7768f-105">公開預覽可讓您測試即將推出的功能，並提供意見回饋。</span><span class="sxs-lookup"><span data-stu-id="7768f-105">Public preview allows you to test upcoming features and provide feedback.</span></span> <span data-ttu-id="7768f-106">公用預覽中包含的功能可能不完整、可能會變更，且雲端版Office 365 政府版支援。</span><span class="sxs-lookup"><span data-stu-id="7768f-106">Features included in public preview may not be complete, may undergo changes, and are not supported in Office 365 Government Clouds.</span></span>

<span data-ttu-id="7768f-107">本文將說明如何設定運算子連線。</span><span class="sxs-lookup"><span data-stu-id="7768f-107">This article describes how to configure Operator Connect.</span></span> <span data-ttu-id="7768f-108">在安裝運算子連線，請務必閱讀運算子方案[連線，以](operator-connect-plan.md)瞭解先決條件和授權的資訊。</span><span class="sxs-lookup"><span data-stu-id="7768f-108">Before configuring Operator Connect, be sure to read [Plan for Operator Connect](operator-connect-plan.md) for information about prerequisites and licensing.</span></span>

## <a name="enable-an-operator"></a><span data-ttu-id="7768f-109">啟用運算子</span><span class="sxs-lookup"><span data-stu-id="7768f-109">Enable an operator</span></span>

<span data-ttu-id="7768f-110">您可以在系統管理中心啟用、編輯及移除Teams運算子。</span><span class="sxs-lookup"><span data-stu-id="7768f-110">You can enable, edit, and remove operators in the Teams Admin Center.</span></span> <span data-ttu-id="7768f-111">在左側流覽窗格中，前往語音> **運算子**。</span><span class="sxs-lookup"><span data-stu-id="7768f-111">In the left navigation pane, go to **Voice > Operators**.</span></span>

<span data-ttu-id="7768f-112">若要啟用運算子：</span><span class="sxs-lookup"><span data-stu-id="7768f-112">To enable an operator:</span></span>

1. <span data-ttu-id="7768f-113">**選擇運算子。**</span><span class="sxs-lookup"><span data-stu-id="7768f-113">**Choose an operator.**</span></span> <span data-ttu-id="7768f-114">在 " **所有運算子"** 的 Tab 中，根據地區或服務篩選可用的運算子，以尋找適合您語音需求的運算子。</span><span class="sxs-lookup"><span data-stu-id="7768f-114">In the **All operators** tab, filter available operators by region or service to find the right operator for your voice needs.</span></span> <span data-ttu-id="7768f-115">然後選取您想要啟用的運算子。</span><span class="sxs-lookup"><span data-stu-id="7768f-115">Then select the operator you want to enable.</span></span>  

2. <span data-ttu-id="7768f-116">**選取國家/地區。**</span><span class="sxs-lookup"><span data-stu-id="7768f-116">**Select countries.**</span></span> <span data-ttu-id="7768f-117">在 **運算子設定** 下，選取您想要使用所選運算子啟用的國家/地區。</span><span class="sxs-lookup"><span data-stu-id="7768f-117">Under **Operator settings**, select the countries you want to enable with your selected operator.</span></span>

3. <span data-ttu-id="7768f-118">**提供連絡人資訊 (選) 。**</span><span class="sxs-lookup"><span data-stu-id="7768f-118">**Provide contact information (optional).**</span></span> <span data-ttu-id="7768f-119">如果您想要讓運算子與您聯繫，並提供有關運算子連線，請勾選該方塊，並提供您的連絡人資訊。</span><span class="sxs-lookup"><span data-stu-id="7768f-119">If you want operators to contact you with additional information about Operator Connect, check the box and provide your contact information.</span></span>  

4. <span data-ttu-id="7768f-120">**接受資料傳輸通知。**</span><span class="sxs-lookup"><span data-stu-id="7768f-120">**Accept the data transfer notice.**</span></span>

5. <span data-ttu-id="7768f-121">**新增運算子。**</span><span class="sxs-lookup"><span data-stu-id="7768f-121">**Add your operator.**</span></span> <span data-ttu-id="7768f-122">選取 **新增為我的運算子** 以儲存。</span><span class="sxs-lookup"><span data-stu-id="7768f-122">Select **Add as my operator** to save.</span></span>

## <a name="set-up-phone-numbers"></a><span data-ttu-id="7768f-123">設定電話號碼</span><span class="sxs-lookup"><span data-stu-id="7768f-123">Set up phone numbers</span></span>

<span data-ttu-id="7768f-124">您設定電話號碼的方式取決於您要設定新使用者的電話號碼，或移動 Microsoft 通話方案或直接路由的現有號碼。</span><span class="sxs-lookup"><span data-stu-id="7768f-124">How you set up phone numbers depends on whether you're setting up numbers for new users, or moving existing numbers from either Microsoft Calling Plans or Direct Routing.</span></span>

- <span data-ttu-id="7768f-125">如果您需要取得新使用者的電話號碼，請參閱取得新[使用者Teams號碼](#acquire-numbers-for-new-teams-users)。</span><span class="sxs-lookup"><span data-stu-id="7768f-125">If you need to acquire phone numbers for new users, see [Acquire numbers for new Teams users](#acquire-numbers-for-new-teams-users).</span></span>

- <span data-ttu-id="7768f-126">如果您想要將現有的號碼從通話方案移至運算子連線，請參閱將號碼從通話方案移至[運算子連線。](#move-numbers-from-calling-plans-to-operator-connect)</span><span class="sxs-lookup"><span data-stu-id="7768f-126">If you want to move existing numbers from Calling Plans to Operator Connect, see [Move numbers from Calling Plans to Operator Connect](#move-numbers-from-calling-plans-to-operator-connect).</span></span>

- <span data-ttu-id="7768f-127">如果您想要將現有號碼從直接路由移至運算子連線，請參閱將數位從直接路由移至[運算子連線。](#move-numbers-from-direct-routing-to-operator-connect)</span><span class="sxs-lookup"><span data-stu-id="7768f-127">If you want to move existing numbers from Direct Routing to Operator Connect, see [Move numbers from Direct Routing to Operator Connect](#move-numbers-from-direct-routing-to-operator-connect).</span></span>

>[!IMPORTANT]
><span data-ttu-id="7768f-128">**緊急位址：** 與從運算子取得的號碼相關聯的緊急位址會直接與運算子管理。</span><span class="sxs-lookup"><span data-stu-id="7768f-128">**Emergency addresses:** Emergency addresses associated with a number acquired from the operator are managed directly with the operator.</span></span> <span data-ttu-id="7768f-129">請聯絡接線員進行變更。</span><span class="sxs-lookup"><span data-stu-id="7768f-129">Please contact the operator to make any changes.</span></span>

### <a name="acquire-numbers-for-new-teams-users"></a><span data-ttu-id="7768f-130">取得新使用者Teams號碼</span><span class="sxs-lookup"><span data-stu-id="7768f-130">Acquire numbers for new Teams users</span></span>

<span data-ttu-id="7768f-131">若要取得新使用者Teams號碼，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7768f-131">To acquire numbers for new Teams users, follow these steps:</span></span>

1. <span data-ttu-id="7768f-132">**指派授權電話系統授權。**</span><span class="sxs-lookup"><span data-stu-id="7768f-132">**Assign a Phone System license.**</span></span> <span data-ttu-id="7768f-133">您可以指派授權電話系統系統管理中心或使用 PowerShell Microsoft 365使用者。</span><span class="sxs-lookup"><span data-stu-id="7768f-133">You can assign a Phone System license to your users from the Microsoft 365 admin center or using PowerShell.</span></span> <span data-ttu-id="7768f-134">詳細資訊，請參閱指派[Teams附加元件授權給使用者](teams-add-on-licensing/assign-teams-add-on-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="7768f-134">For more information, see [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>

2. <span data-ttu-id="7768f-135">**請確定您目前使用 TeamsOnly 模式。**</span><span class="sxs-lookup"><span data-stu-id="7768f-135">**Make sure you're in TeamsOnly mode.**</span></span> <span data-ttu-id="7768f-136">若要檢查，請在 Teams 系統管理中心，前往整個 **組織設定以> Teams升級**。</span><span class="sxs-lookup"><span data-stu-id="7768f-136">To check, in the Teams admin center, go to **Org-wide settings > Teams upgrade**.</span></span> <span data-ttu-id="7768f-137">共存模式應設為僅Teams模式。</span><span class="sxs-lookup"><span data-stu-id="7768f-137">The coexistence mode should be set to Teams only.</span></span>

3. <span data-ttu-id="7768f-138">**建立及驗證緊急位址。**</span><span class="sxs-lookup"><span data-stu-id="7768f-138">**Create and validate emergency addresses.**</span></span> <span data-ttu-id="7768f-139">在 Teams系統管理中心，前往緊急>**位置以** 設定緊急位址。</span><span class="sxs-lookup"><span data-stu-id="7768f-139">In the Teams admin center, go to **Locations > Emergency addresses** to set up emergency addresses.</span></span> <span data-ttu-id="7768f-140">若要深入瞭解，請參閱 [新增、變更或移除貴組織的緊急位置](add-change-remove-emergency-location-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="7768f-140">To learn more, see [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md).</span></span>

4. <span data-ttu-id="7768f-141">**取得數位。**</span><span class="sxs-lookup"><span data-stu-id="7768f-141">**Acquire numbers.**</span></span> <span data-ttu-id="7768f-142">請前往您的接線員網站訂購及取得電話號碼。</span><span class="sxs-lookup"><span data-stu-id="7768f-142">Go to your operator's website to order and acquire phone numbers.</span></span> <span data-ttu-id="7768f-143">有關運算子網站的清單 [，請參閱運算子](#operators)。</span><span class="sxs-lookup"><span data-stu-id="7768f-143">For a list of operator websites, see [Operators](#operators).</span></span> <span data-ttu-id="7768f-144">您必須提供租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="7768f-144">You'll need to provide your tenant ID.</span></span> <span data-ttu-id="7768f-145">如果您不知道您的租使用者識別碼，請參閱尋找您的Microsoft 365[租使用者識別碼](/onedrive/find-your-office-365-tenant-id)以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="7768f-145">If you don't know your tenant ID, see [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id) for more information.</span></span>

5. <span data-ttu-id="7768f-146">**指派數位。**</span><span class="sxs-lookup"><span data-stu-id="7768f-146">**Assign numbers.**</span></span> <span data-ttu-id="7768f-147">您的運算子完成訂單後，就會將測試編號上傳至您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="7768f-147">Once your operator completes the order, they'll upload test numbers to your tenant.</span></span> <span data-ttu-id="7768f-148">您可以在系統管理中心查看號碼Teams提供者，> 電話 **號碼**。</span><span class="sxs-lookup"><span data-stu-id="7768f-148">You can view the numbers and the provider in the Teams admin center by going to **Voice > Phone numbers**.</span></span> <span data-ttu-id="7768f-149">使用系統管理中心或 powerShell Teams指派號碼給使用者。</span><span class="sxs-lookup"><span data-stu-id="7768f-149">Assign numbers to users by using the Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="7768f-150">詳細資訊，請參閱指派 [數位](#assign-numbers)。</span><span class="sxs-lookup"><span data-stu-id="7768f-150">For more information, see [Assign numbers](#assign-numbers).</span></span>
 

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a><span data-ttu-id="7768f-151">將號碼從通話方案移至運算子連線</span><span class="sxs-lookup"><span data-stu-id="7768f-151">Move numbers from Calling Plans to Operator Connect</span></span>

1. <span data-ttu-id="7768f-152">請與您的接線員聯繫，將號碼連線。</span><span class="sxs-lookup"><span data-stu-id="7768f-152">Contact your operator to port your numbers to Operator Connect.</span></span> <span data-ttu-id="7768f-153">請參閱 [運算子](#operators) 以尋找您的運算子網站。</span><span class="sxs-lookup"><span data-stu-id="7768f-153">See [Operators](#operators) to find your operator's website.</span></span>

2. <span data-ttu-id="7768f-154">您的接線員完成移移訂單之後，您可以取消為使用者的通話方案電話號碼進行分配，並移除通話方案授權。</span><span class="sxs-lookup"><span data-stu-id="7768f-154">After your operator completes the porting order, you can unassign your users' Calling Plan phone numbers, and remove the Calling Plan License.</span></span> <span data-ttu-id="7768f-155">然後，您的運算子可以將數位上傳到您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="7768f-155">Then, your operator can upload the numbers to your tenant.</span></span>

3. <span data-ttu-id="7768f-156">使用 連線系統管理中心或 PowerShell 將運算子Teams號碼指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="7768f-156">Assign Operator Connect numbers to users by using the Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="7768f-157">詳細資訊，請參閱指派 [數位](#assign-numbers)。</span><span class="sxs-lookup"><span data-stu-id="7768f-157">For more information, see [Assign numbers](#assign-numbers).</span></span>

 
### <a name="move-numbers-from-direct-routing-to-operator-connect"></a><span data-ttu-id="7768f-158">將數位從直接路由移至運算子連線</span><span class="sxs-lookup"><span data-stu-id="7768f-158">Move numbers from Direct Routing to Operator Connect</span></span>

1. <span data-ttu-id="7768f-159">從使用者移除現有電話號碼，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7768f-159">Remove the existing telephone number from the user as follows:</span></span>  

   <span data-ttu-id="7768f-160">執行下列 PowerShell 命令以取得現有的 On-prem Line URI：</span><span class="sxs-lookup"><span data-stu-id="7768f-160">Get the existing On-prem Line URI by running the following PowerShell command:</span></span>

   ```
   Get-CsOnlineUser -Identity <user> | select OnPremLineURI 
   ```

   <span data-ttu-id="7768f-161">執行下列 PowerShell 命令以移除 On-prem Line URI：</span><span class="sxs-lookup"><span data-stu-id="7768f-161">Remove the On-prem Line URI by running the following PowerShell command:</span></span>  

   ```
   Set-CsUser -identity <user> - OnPremLineURI $null 
   ```

2. <span data-ttu-id="7768f-162">移除任何與使用者相關聯的 PSTNUsage，否則通話會路由至 PSTN 使用量中指定的閘道。</span><span class="sxs-lookup"><span data-stu-id="7768f-162">Remove any PSTNUsage associated with your users, otherwise calls will be routed to the gateway specified in the PSTN Usage.</span></span> <span data-ttu-id="7768f-163">若要瞭解如何移除 PSTN 使用量，請參閱 [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="7768f-163">To learn how to remove PSTN usage, see [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps).</span></span>

3. <span data-ttu-id="7768f-164">請前往您的接線員網站訂購及取得電話號碼。</span><span class="sxs-lookup"><span data-stu-id="7768f-164">Go to your operator's website to order and acquire phone numbers.</span></span> <span data-ttu-id="7768f-165">有關運算子網站的清單 [，請參閱運算子](#operators)。</span><span class="sxs-lookup"><span data-stu-id="7768f-165">For a list of operator websites, see [Operators](#operators).</span></span> <span data-ttu-id="7768f-166">您必須提供租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="7768f-166">You'll need to provide your tenant ID.</span></span> <span data-ttu-id="7768f-167">如果您不知道您的租使用者識別碼，請參閱尋找您的Microsoft 365[租使用者識別碼](/onedrive/find-your-office-365-tenant-id)以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="7768f-167">If you don't know your tenant ID, see [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id) for more information.</span></span>

4. <span data-ttu-id="7768f-168">您的運算子完成訂單後，就會將測試編號上傳至您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="7768f-168">Once your operator completes the order, they'll upload test numbers to your tenant.</span></span> <span data-ttu-id="7768f-169">您可以在系統管理中心查看號碼Teams提供者，> 電話 **號碼**。</span><span class="sxs-lookup"><span data-stu-id="7768f-169">You can view the numbers and the provider in the Teams admin center by going to **Voice > Phone numbers**.</span></span> <span data-ttu-id="7768f-170">使用 連線系統管理中心或 PowerShell 將運算子Teams號碼指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="7768f-170">Assign Operator Connect numbers to users by using the Teams admin center or by using  PowerShell.</span></span> <span data-ttu-id="7768f-171">詳細資訊，請參閱指派 [數位](#assign-numbers)。</span><span class="sxs-lookup"><span data-stu-id="7768f-171">For more information, see [Assign numbers](#assign-numbers).</span></span>

   

### <a name="assign-numbers"></a><span data-ttu-id="7768f-172">指派數位</span><span class="sxs-lookup"><span data-stu-id="7768f-172">Assign numbers</span></span>

<span data-ttu-id="7768f-173">無論您是新增使用者Teams或將現有使用者移動到運算子連線，指派數位的步驟如下：</span><span class="sxs-lookup"><span data-stu-id="7768f-173">Whether you're adding new Teams users or moving existing users to Operator Connect, the steps for assigning numbers are as follows:</span></span>

<span data-ttu-id="7768f-174">若要使用系統管理中心Teams數位，請前往 電話 **數位**。</span><span class="sxs-lookup"><span data-stu-id="7768f-174">To assign numbers by using the Teams admin center, go to **Phone numbers**.</span></span> <span data-ttu-id="7768f-175">步驟與指派通話方案號碼的步驟相同。</span><span class="sxs-lookup"><span data-stu-id="7768f-175">The steps are the same as assigning numbers for Calling Plans.</span></span> <span data-ttu-id="7768f-176">詳細資訊，請參閱 [指派電話號碼給使用者](assign-change-or-remove-a-phone-number-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="7768f-176">For more information, see [Assign a phone number to a user](assign-change-or-remove-a-phone-number-for-a-user.md).</span></span>

<span data-ttu-id="7768f-177">若要使用 PowerShell 指派數位，請使用 Set-CsOnlineVoiceUser Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7768f-177">To assign numbers by using PowerShell, use the Set-CsOnlineVoiceUser cmdlet as follows:</span></span>

```
Set-CsOnlineVoiceUser -Identity <user>  -TelephoneNumber <phone number> 
```

<span data-ttu-id="7768f-178">例如：</span><span class="sxs-lookup"><span data-stu-id="7768f-178">For example:</span></span>

```
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

<span data-ttu-id="7768f-179">若要瞭解如何指派電話號碼給使用者，請參閱指派、變更或移除使用者 [的電話號碼](assign-change-or-remove-a-phone-number-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="7768f-179">For more information about how to assign phone numbers to your users, see [Assign, change, or remove a phone number for a user](assign-change-or-remove-a-phone-number-for-a-user.md).</span></span>



## <a name="manage-your-operators"></a><span data-ttu-id="7768f-180">管理運算子</span><span class="sxs-lookup"><span data-stu-id="7768f-180">Manage your operators</span></span>

<span data-ttu-id="7768f-181">在 "我的運算子" 選項卡中，您可以查看運算子及其狀態，並變更下列選取專案：</span><span class="sxs-lookup"><span data-stu-id="7768f-181">From the My operators tab, you can view your operators and their status and make the following changes to your selections:</span></span>  

- <span data-ttu-id="7768f-182">根據國家/地區管理運算子服務</span><span class="sxs-lookup"><span data-stu-id="7768f-182">Manage operator services by country</span></span>
- <span data-ttu-id="7768f-183">暫停運算子</span><span class="sxs-lookup"><span data-stu-id="7768f-183">Suspend an operator</span></span>
- <span data-ttu-id="7768f-184">移除運算子</span><span class="sxs-lookup"><span data-stu-id="7768f-184">Remove an operator</span></span>

> [!NOTE]
> <span data-ttu-id="7768f-185">在將接線員從貴組織或國家/地區移除之前，您必須移除指派給組織或國家/地區使用者的所有電話號碼，並請聯絡接線員以釋出號碼。</span><span class="sxs-lookup"><span data-stu-id="7768f-185">Before removing an operator from your organization or from a country, you must remove all phone numbers assigned to users in the organization or country and contact the operator to release the numbers.</span></span>

## <a name="operators"></a><span data-ttu-id="7768f-186">運算元</span><span class="sxs-lookup"><span data-stu-id="7768f-186">Operators</span></span>

<span data-ttu-id="7768f-187">您可以到此處連結的網站，從下列運算子取得電話號碼：</span><span class="sxs-lookup"><span data-stu-id="7768f-187">You can acquire phone numbers from the following operators by going to the websites linked here:</span></span>


|<span data-ttu-id="7768f-188">運算元</span><span class="sxs-lookup"><span data-stu-id="7768f-188">Operator</span></span>  |<span data-ttu-id="7768f-189">運算子網站</span><span class="sxs-lookup"><span data-stu-id="7768f-189">Operator website</span></span>  |
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

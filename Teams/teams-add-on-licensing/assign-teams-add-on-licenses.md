---
title: 指派Teams附加元件授權給使用者
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: 瞭解如何將附加Teams授權指派給使用者，以使用音訊會議、電話系統和通話方案等功能。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240672b125190492a036bc9dfa3f7a42070e8320
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116931"
---
# <a name="assign-teams-add-on-licenses-to-users"></a><span data-ttu-id="d4150-103">指派Teams附加元件授權給使用者</span><span class="sxs-lookup"><span data-stu-id="d4150-103">Assign Teams add-on licenses to users</span></span>

<span data-ttu-id="d4150-104">附加元件授權是特定功能Teams，例如音訊會議、電話系統和通話方案。</span><span class="sxs-lookup"><span data-stu-id="d4150-104">Add-on licenses are licenses for specific Teams features such as Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="d4150-105">本文將說明如何將附加元件授權指派給個別使用者和大量大型使用者。</span><span class="sxs-lookup"><span data-stu-id="d4150-105">This article describes how to assign add-on licenses to individual users and to large sets of users in bulk.</span></span>

> [!NOTE]
> <span data-ttu-id="d4150-106">請參閱[Teams附加元件授權](./microsoft-teams-add-on-licensing.md)Teams附加元件授權提供的功能。</span><span class="sxs-lookup"><span data-stu-id="d4150-106">See [Teams add-on licensing](./microsoft-teams-add-on-licensing.md) for Teams features that are available with add-on licenses.</span></span> <span data-ttu-id="d4150-107">您也可以根據您的方案) 找到您需要購買哪些授權以及如何購買授權的資訊 (以便使用者可以取得音訊會議、免付費號碼等功能，以及撥打組織外電話號碼的功能。</span><span class="sxs-lookup"><span data-stu-id="d4150-107">You'll also find information about what licenses you need to buy and how to buy them (depending on your plan), so users can get features such as Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your organization.</span></span> <span data-ttu-id="d4150-108">決定要為使用者提供哪些功能之後，請指派授權給他們。</span><span class="sxs-lookup"><span data-stu-id="d4150-108">After you decide  which features you want for your users, assign the licenses to them.</span></span>

<span data-ttu-id="d4150-109">您可以使用系統管理Microsoft 365 PowerShell 將授權指派給貴組織的使用者。</span><span class="sxs-lookup"><span data-stu-id="d4150-109">You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization.</span></span> <span data-ttu-id="d4150-110">您必須是全域系統管理員或使用者管理系統管理員，才能管理授權。</span><span class="sxs-lookup"><span data-stu-id="d4150-110">You must be a Global admin or User management admin to manage licenses.</span></span>

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a><span data-ttu-id="d4150-111">指派授權、通話方案電話系統通訊信用額度授權之前，您需要知道什麼</span><span class="sxs-lookup"><span data-stu-id="d4150-111">What you need to know before you assign Phone System, Calling Plan, and Communication Credits licenses</span></span>

<span data-ttu-id="d4150-112">在您開始使用之前，請先檢查下列需求：</span><span class="sxs-lookup"><span data-stu-id="d4150-112">Before you get started, review the following requirements:</span></span>

- <span data-ttu-id="d4150-113">如果您是使用內部部署公用交換電話網絡 (PSTN) 混合式使用者，則只需要指派電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="d4150-113">If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for hybrid users, you only need to assign a Phone System license.</span></span> <span data-ttu-id="d4150-114">請勿指派通話方案授權。</span><span class="sxs-lookup"><span data-stu-id="d4150-114">Do NOT assign a Calling Plan license.</span></span>

- <span data-ttu-id="d4150-115">由於 Microsoft 365 和 Microsoft Teams 之間的延遲，使用者最多可能需要 24 小時，才能在指派授權後指派通話方案。</span><span class="sxs-lookup"><span data-stu-id="d4150-115">Because of the latency between Microsoft 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="d4150-116">如果使用者在 24 小時後未指派通話方案，請聯絡商務產品 [支援人員 - 系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="d4150-116">If the user isn't assigned a Calling Plan after 24 hours, [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="d4150-117">如果您沒有購買正確的授權數量，就會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="d4150-117">You'll get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="d4150-118">如果您需要購買更多通話方案授權，請選擇購買更多方案的選項。</span><span class="sxs-lookup"><span data-stu-id="d4150-118">If you need to buy more Calling Plan licenses, choose the option to buy more.</span></span>

- <span data-ttu-id="d4150-119">即使您的使用者被指派Enterprise E5 授權，如果您想要撥打或接聽 PSTN[](../what-are-communications-credits.md)的通話，您仍然需要指派通訊信用額度授權給他們。</span><span class="sxs-lookup"><span data-stu-id="d4150-119">Even if your users are assigned Enterprise E5 licenses, you still need to assign [Communications Credits](../what-are-communications-credits.md) licenses to them if they want to make or receive calls from the PSTN.</span></span>

- <span data-ttu-id="d4150-120">將通話方案或通訊信用額度授權指派給使用者之後，您必須取得貴組織的電話號碼，然後將這些號碼指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="d4150-120">After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users.</span></span> <span data-ttu-id="d4150-121">有關逐步指示，請參閱 [設定通話方案](../set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="d4150-121">For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans.md).</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="d4150-122">使用 Microsoft 365系統管理中心</span><span class="sxs-lookup"><span data-stu-id="d4150-122">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="d4150-123">使用 Microsoft 365系統管理中心，一次指派授權給個別使用者或少數使用者。</span><span class="sxs-lookup"><span data-stu-id="d4150-123">Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.</span></span> <span data-ttu-id="d4150-124">您一次在 (或活動使用者頁面上，為最多 20) **指派** 授權。</span><span class="sxs-lookup"><span data-stu-id="d4150-124">You assign licenses on the **Licenses** page (for up to 20 users at a time) or the **Active users** page.</span></span> <span data-ttu-id="d4150-125">您選擇的方法取決於您要管理特定使用者的產品授權，或管理特定產品的使用者授權。</span><span class="sxs-lookup"><span data-stu-id="d4150-125">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="d4150-126">有關逐步指示，請參閱指派 [授權給使用者](/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="d4150-126">For step-by-step instructions, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="d4150-127">如果您需要為大量使用者指派授權 ，例如數百或數千個使用者，請使用[Azure Active Directory (Azure AD ](/azure/active-directory/users-groups-roles/licensing-groups-assign)Azure Active Directory (Powershell 或群組式授權) 。</span><span class="sxs-lookup"><span data-stu-id="d4150-127">If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use Powershell or [group-based licensing in Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

## <a name="using-powershell"></a><span data-ttu-id="d4150-128">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4150-128">Using PowerShell</span></span>

<span data-ttu-id="d4150-129">使用 PowerShell 大量指派授權給使用者。</span><span class="sxs-lookup"><span data-stu-id="d4150-129">Use PowerShell to assign licenses to users in bulk.</span></span>  <span data-ttu-id="d4150-130">若要深入瞭解，請參閱使用 [PowerShell 將授權指派給使用者帳戶](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d4150-130">To learn more, see [Assign licenses to user accounts with PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="example-script"></a><span data-ttu-id="d4150-131">範例腳本</span><span class="sxs-lookup"><span data-stu-id="d4150-131">Example script</span></span>

<span data-ttu-id="d4150-132">以下是如何使用腳本指派授權給使用者的範例。</span><span class="sxs-lookup"><span data-stu-id="d4150-132">Here's an example of how to use a script to assign licenses to your users.</span></span>

1. <span data-ttu-id="d4150-133">安裝適用于 IT 專業人員 RTW 的 Microsoft Online Services 登入 [小幫手的](/collaborate/connect-redirect?DownloadID=59185)64 位版本。</span><span class="sxs-lookup"><span data-stu-id="d4150-133">Install the 64-bit version of the [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](/collaborate/connect-redirect?DownloadID=59185).</span></span>
2. <span data-ttu-id="d4150-134">安裝 Microsoft Azure Active Directory 模組Windows PowerShell：</span><span class="sxs-lookup"><span data-stu-id="d4150-134">Install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    1. <span data-ttu-id="d4150-135">開啟提升Windows PowerShell命令提示 (以系統管理員Windows PowerShell執行) 。</span><span class="sxs-lookup"><span data-stu-id="d4150-135">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an admin).</span></span>
    2. <span data-ttu-id="d4150-136">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d4150-136">Run the following command:</span></span>
        ```powershell
        Install-Module MSOnline
        ```
    3. <span data-ttu-id="d4150-137">如果系統提示您安裝 NuGet，請輸入 **Y，** 然後按 Enter。</span><span class="sxs-lookup"><span data-stu-id="d4150-137">If you're prompted to install the NuGet provider, type **Y**, and then press Enter.</span></span>
    4. <span data-ttu-id="d4150-138">如果系統提示您從 PSGallery 安裝模組，請輸入 **Y，** 然後按 Enter。</span><span class="sxs-lookup"><span data-stu-id="d4150-138">If you're prompted to install the module from PSGallery, type **Y**, and then press Enter.</span></span>
3. <span data-ttu-id="d4150-139">在 Windows PowerShell命令提示字元中，執行下列腳本來指派授權給使用者，其中您的組織名稱和要指派之授權識別碼 \<CompanyName:License> 在哪裡。</span><span class="sxs-lookup"><span data-stu-id="d4150-139">At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where \<CompanyName:License> is your organization name and the identifier for the license that you want to assign.</span></span> <span data-ttu-id="d4150-140">例如，litwareinc：MCOMEETADV。</span><span class="sxs-lookup"><span data-stu-id="d4150-140">For example, litwareinc:MCOMEETADV.</span></span>

    <span data-ttu-id="d4150-141">識別碼與授權好用的名稱不同。</span><span class="sxs-lookup"><span data-stu-id="d4150-141">The identifier is different than the friendly name of the license.</span></span> <span data-ttu-id="d4150-142">例如，音訊會議識別碼為 MCOMEETADV。</span><span class="sxs-lookup"><span data-stu-id="d4150-142">For example, the identifier for Audio Conferencing is MCOMEETADV.</span></span> <span data-ttu-id="d4150-143">若要深入瞭解，請參閱 [授權的產品名稱和 SKU 識別碼](#product-names-and-sku-identifiers-for-licensing)。</span><span class="sxs-lookup"><span data-stu-id="d4150-143">To learn more, see [Product names and SKU identifiers for licensing](#product-names-and-sku-identifiers-for-licensing).</span></span>

    ```powershell
    #Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    #Example of text file:''
    #user1@domain.com
    #user2@domain.com

    #Import Module
    ipmo MSOnline

    #Authenticate to MSOLservice
    Connect-MSOLService
    #File prompt to select the userlist txt file
    [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
      $OFD = New-Object System.Windows.Forms.OpenFileDialog
      $OFD.filter = "text files (*.*)| *.txt"
      $OFD.ShowDialog() | Out-Null
      $OFD.filename

    If ($OFD.filename -eq '')
    {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
    }

    #Create a variable of all users
    $users = Get-Content $OFD.filename

    #License each user in the $users variable
    foreach ($user in $users)
        {
        Write-host "Assigning License: $user"
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        }
    ```

    <span data-ttu-id="d4150-144">例如，若要指派 Microsoft 365 企業版 1 和音訊會議授權，請使用腳本中的下列語法：</span><span class="sxs-lookup"><span data-stu-id="d4150-144">For example, to assign Microsoft 365 Enterprise 1 and Audio Conferencing licenses, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    <span data-ttu-id="d4150-145">若要指派不含通話方案 (的 Microsoft Business Voice) ，請使用腳本中的下列語法：</span><span class="sxs-lookup"><span data-stu-id="d4150-145">To assign a Microsoft Business Voice (without Calling Plan) license, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a><span data-ttu-id="d4150-146">授權的產品名稱和 SKU 識別碼</span><span class="sxs-lookup"><span data-stu-id="d4150-146">Product names and SKU identifiers for licensing</span></span>

<span data-ttu-id="d4150-147">以下是部分產品名稱及其對應的 SKU 零件名稱清單，當您使用 PowerShell 管理 Teams。</span><span class="sxs-lookup"><span data-stu-id="d4150-147">Here's a partial list of product names and their corresponding SKU part names that you can use as a reference when you use PowerShell to manage licenses in Teams.</span></span>

<span data-ttu-id="d4150-148">若要深入瞭解，請參閱 [使用 PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)來查看授權和服務、 [授權](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)的產品名稱和服務方案識別碼，以及 [教育版 SKU 參考](../sku-reference-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="d4150-148">To learn more, see [View licenses and services with PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu.md).</span></span>

| <span data-ttu-id="d4150-149">產品名稱</span><span class="sxs-lookup"><span data-stu-id="d4150-149">Product name</span></span>| <span data-ttu-id="d4150-150">SKU 零件名稱</span><span class="sxs-lookup"><span data-stu-id="d4150-150">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="d4150-151">Microsoft Enterprise E5 (電話系統) </span><span class="sxs-lookup"><span data-stu-id="d4150-151">Microsoft Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="d4150-152">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="d4150-152">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="d4150-153">Microsoft Enterprise E5 (沒有音訊會議) </span><span class="sxs-lookup"><span data-stu-id="d4150-153">Microsoft Enterprise E5 (without Audio Conferencing)</span></span> | <span data-ttu-id="d4150-154">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="d4150-154">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="d4150-155">Microsoft Enterprise E5 (音訊會議) </span><span class="sxs-lookup"><span data-stu-id="d4150-155">Microsoft Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="d4150-156">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="d4150-156">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="d4150-157">Microsoft Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="d4150-157">Microsoft Enterprise E3</span></span> | <span data-ttu-id="d4150-158">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="d4150-158">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="d4150-159">Microsoft Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="d4150-159">Microsoft Enterprise E1</span></span> | <span data-ttu-id="d4150-160">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="d4150-160">STANDARDPACK</span></span> |
| <span data-ttu-id="d4150-161">Microsoft 365 商務基本版</span><span class="sxs-lookup"><span data-stu-id="d4150-161">Microsoft 365 Business Basic</span></span> | <span data-ttu-id="d4150-162">O365_BUSINESS_ESSENTIALS</span><span class="sxs-lookup"><span data-stu-id="d4150-162">O365_BUSINESS_ESSENTIALS</span></span>|
| <span data-ttu-id="d4150-163">Microsoft 365 商務標準版</span><span class="sxs-lookup"><span data-stu-id="d4150-163">Microsoft 365 Business Standard</span></span> | <span data-ttu-id="d4150-164">O365_BUSINESS_PREMIUM</span><span class="sxs-lookup"><span data-stu-id="d4150-164">O365_BUSINESS_PREMIUM</span></span>|
| <span data-ttu-id="d4150-165">Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="d4150-165">Microsoft 365 Business</span></span> | <span data-ttu-id="d4150-166">SPB</span><span class="sxs-lookup"><span data-stu-id="d4150-166">SPB</span></span>|
| <span data-ttu-id="d4150-167">Microsoft Business Voice (加拿大) </span><span class="sxs-lookup"><span data-stu-id="d4150-167">Microsoft Business Voice (Canada)</span></span>| <span data-ttu-id="d4150-168">BUSINESS_VOICE_MED</span><span class="sxs-lookup"><span data-stu-id="d4150-168">BUSINESS_VOICE_MED</span></span>  |
| <span data-ttu-id="d4150-169">Microsoft Business Voice (英國) </span><span class="sxs-lookup"><span data-stu-id="d4150-169">Microsoft Business Voice (United Kingdom)</span></span> | <span data-ttu-id="d4150-170">BUSINESS_VOICE</span><span class="sxs-lookup"><span data-stu-id="d4150-170">BUSINESS_VOICE</span></span>  |
| <span data-ttu-id="d4150-171">Microsoft Business Voice (美國) </span><span class="sxs-lookup"><span data-stu-id="d4150-171">Microsoft Business Voice (United States)</span></span> | <span data-ttu-id="d4150-172">BUSINESS_VOICE_MED2</span><span class="sxs-lookup"><span data-stu-id="d4150-172">BUSINESS_VOICE_MED2</span></span>  |
| <span data-ttu-id="d4150-173">Microsoft Business Voice (通話方案) </span><span class="sxs-lookup"><span data-stu-id="d4150-173">Microsoft Business Voice (without Calling Plan)</span></span> | <span data-ttu-id="d4150-174">BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="d4150-174">BUSINESS_VOICE_DIRECTROUTING</span></span>  |
| <span data-ttu-id="d4150-175">Microsoft Business Voice (美國) 方案</span><span class="sxs-lookup"><span data-stu-id="d4150-175">Microsoft Business Voice (without Calling Plan) for the United States</span></span>| <span data-ttu-id="d4150-176">BUSINESS_VOICE_DIRECTROUTING _MED</span><span class="sxs-lookup"><span data-stu-id="d4150-176">BUSINESS_VOICE_DIRECTROUTING _MED</span></span> |
| <span data-ttu-id="d4150-177">音訊會議</span><span class="sxs-lookup"><span data-stu-id="d4150-177">Audio Conferencing</span></span> | <span data-ttu-id="d4150-178">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="d4150-178">MCOMEETADV</span></span> | 
| <span data-ttu-id="d4150-179">使用音訊會議時， (按分鐘付費) </span><span class="sxs-lookup"><span data-stu-id="d4150-179">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="d4150-180">*需要設定並啟用通訊信用額度。*</span><span class="sxs-lookup"><span data-stu-id="d4150-180">*Requires Communications Credits to be set up and enabled.*</span></span> | <span data-ttu-id="d4150-181">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="d4150-181">MCOMEETACPEA</span></span> |
| <span data-ttu-id="d4150-182">電話系統</span><span class="sxs-lookup"><span data-stu-id="d4150-182">Phone System</span></span> | <span data-ttu-id="d4150-183">MCOEV</span><span class="sxs-lookup"><span data-stu-id="d4150-183">MCOEV</span></span> |
| <span data-ttu-id="d4150-184">國內和國際通話方案</span><span class="sxs-lookup"><span data-stu-id="d4150-184">Domestic and International Calling Plan</span></span> | <span data-ttu-id="d4150-185">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="d4150-185">MCOPSTN2</span></span> |
| <span data-ttu-id="d4150-186">美國/ (/CA 的國內通話方案為每個使用者/月 3000 分鐘，歐盟國家/地區為每個使用者/月 1200 分鐘) </span><span class="sxs-lookup"><span data-stu-id="d4150-186">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="d4150-187">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="d4150-187">MCOPSTN1</span></span> |
| <span data-ttu-id="d4150-188">國內通話方案 (每個國家/地區/月 120 分鐘) </span><span class="sxs-lookup"><span data-stu-id="d4150-188">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="d4150-189">*此方案不適用於美國。*</span><span class="sxs-lookup"><span data-stu-id="d4150-189">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="d4150-190">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="d4150-190">MCOPSTN5</span></span> |
| <span data-ttu-id="d4150-191">國內通話方案 (每個國家/地區/月 240 分鐘) </span><span class="sxs-lookup"><span data-stu-id="d4150-191">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="d4150-192">*此方案不適用於美國。*</span><span class="sxs-lookup"><span data-stu-id="d4150-192">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="d4150-193">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="d4150-193">MCOPSTN6</span></span> |
| <span data-ttu-id="d4150-194">通訊點數</span><span class="sxs-lookup"><span data-stu-id="d4150-194">Communications Credits</span></span> | <span data-ttu-id="d4150-195">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="d4150-195">MCOPSTNPP</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d4150-196">相關主題</span><span class="sxs-lookup"><span data-stu-id="d4150-196">Related topics</span></span>

- [<span data-ttu-id="d4150-197">Teams 附加元件授權</span><span class="sxs-lookup"><span data-stu-id="d4150-197">Teams add-on licensing</span></span>](./microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="d4150-198">管理使用者對 Teams 的存取權</span><span class="sxs-lookup"><span data-stu-id="d4150-198">Manage user access to Teams</span></span>](../user-access.md)
- [<span data-ttu-id="d4150-199">使用 PowerShell 查看授權和服務</span><span class="sxs-lookup"><span data-stu-id="d4150-199">View licenses and services with PowerShell</span></span>](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="d4150-200">用於授權的產品名稱和服務方案識別碼</span><span class="sxs-lookup"><span data-stu-id="d4150-200">Product names and service plan identifiers for licensing</span></span>](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="d4150-201">教育用 SKU 參考</span><span class="sxs-lookup"><span data-stu-id="d4150-201">Education SKU reference</span></span>](../sku-reference-edu.md)
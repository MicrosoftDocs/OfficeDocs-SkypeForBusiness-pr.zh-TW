---
title: 指派 Teams 附加元件授權給使用者
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
description: 瞭解如何將 Teams 附加元件授權指派給使用者，以使用音訊會議、電話系統及通話方案等功能。
appliesto:
- Microsoft Teams
ms.openlocfilehash: f0b7a997525759741e35fa5450c9b8777519c6c7
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196927"
---
# <a name="assign-teams-add-on-licenses-to-users"></a><span data-ttu-id="b722c-103">指派 Teams 附加元件授權給使用者</span><span class="sxs-lookup"><span data-stu-id="b722c-103">Assign Teams add-on licenses to users</span></span>

<span data-ttu-id="b722c-104">附加元件授權是特定 Teams 功能授權，例如音訊會議、電話系統及通話方案。</span><span class="sxs-lookup"><span data-stu-id="b722c-104">Add-on licenses are licenses for specific Teams features such as Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="b722c-105">本文說明如何將附加元件授權指派給個別使用者，以及大量指派給大型使用者。</span><span class="sxs-lookup"><span data-stu-id="b722c-105">This article describes how to assign add-on licenses to individual users and to large sets of users in bulk.</span></span>

> [!NOTE]
> <span data-ttu-id="b722c-106">請參閱 [Teams 附加元件授權](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) ，以使用附加元件授權提供的 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="b722c-106">See [Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) for Teams features that are available with add-on licenses.</span></span> <span data-ttu-id="b722c-107">您也可以找到有關您需要購買哪些授權以及如何購買授權的資訊 (視您的方案) ，讓使用者可以取得音訊會議、免付費電話號碼，以及撥打組織外部電話號碼等功能。</span><span class="sxs-lookup"><span data-stu-id="b722c-107">You'll also find information about what licenses you need to buy and how to buy them (depending on your plan), so users can get features such as Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your organization.</span></span> <span data-ttu-id="b722c-108">決定要為使用者提供哪些功能之後，請指派授權給他們。</span><span class="sxs-lookup"><span data-stu-id="b722c-108">After you decide  which features you want for your users, assign the licenses to them.</span></span>

<span data-ttu-id="b722c-109">您可以使用 Microsoft 365 系統管理中心或 PowerShell，將授權指派給貴組織的使用者。</span><span class="sxs-lookup"><span data-stu-id="b722c-109">You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization.</span></span> <span data-ttu-id="b722c-110">您必須是全域系統管理員或使用者管理系統管理員，才能管理授權。</span><span class="sxs-lookup"><span data-stu-id="b722c-110">You must be a Global admin or User management admin to manage licenses.</span></span>

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a><span data-ttu-id="b722c-111">指派電話系統、通話方案及通訊信用額度授權前必須知道哪些資訊</span><span class="sxs-lookup"><span data-stu-id="b722c-111">What you need to know before you assign Phone System, Calling Plan, and Communication Credits licenses</span></span>

<span data-ttu-id="b722c-112">在您開始使用之前，請審查下列需求：</span><span class="sxs-lookup"><span data-stu-id="b722c-112">Before you get started, review the following requirements:</span></span>

- <span data-ttu-id="b722c-113">如果您是使用內部部署公用交換電話網路 (PSTN) 混合式使用者的) ，則只需要指派電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="b722c-113">If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for hybrid users, you only need to assign a Phone System license.</span></span> <span data-ttu-id="b722c-114">請勿指派通話方案授權。</span><span class="sxs-lookup"><span data-stu-id="b722c-114">Do NOT assign a Calling Plan license.</span></span>

- <span data-ttu-id="b722c-115">由於 Microsoft 365 和 Microsoft Teams 之間有延遲，指派授權後，使用者最多可能需要 24 小時才能獲得通話方案。</span><span class="sxs-lookup"><span data-stu-id="b722c-115">Because of the latency between Microsoft 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="b722c-116">如果 24 小時後未指派通話方案給使用者，請聯絡商務產品的支援 [人員 - 系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="b722c-116">If the user isn't assigned a Calling Plan after 24 hours, [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="b722c-117">如果您尚未購買正確的授權數量，就會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="b722c-117">You'll get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="b722c-118">如果您需要購買更多通話方案授權，請選擇購買更多方案的選項。</span><span class="sxs-lookup"><span data-stu-id="b722c-118">If you need to buy more Calling Plan licenses, choose the option to buy more.</span></span>

- <span data-ttu-id="b722c-119">即使您的使用者獲指派企業版 E5 授權，如果您希望從 PSTN[](../what-are-communications-credits.md)撥打或接聽來電，您仍然需要指派通訊信用額度授權給他們。</span><span class="sxs-lookup"><span data-stu-id="b722c-119">Even if your users are assigned Enterprise E5 licenses, you still need to assign [Communications Credits](../what-are-communications-credits.md) licenses to them if they want to make or receive calls from the PSTN.</span></span>

- <span data-ttu-id="b722c-120">將通話方案或通訊信用額度授權指派給使用者之後，您必須取得貴組織的電話號碼，然後將這些號碼指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="b722c-120">After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users.</span></span> <span data-ttu-id="b722c-121">有關逐步指示，請參閱設定 [通話方案](../set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="b722c-121">For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans.md).</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="b722c-122">使用 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="b722c-122">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="b722c-123">使用 Microsoft 365 系統管理中心一次指派授權給個別使用者或少數使用者。</span><span class="sxs-lookup"><span data-stu-id="b722c-123">Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.</span></span> <span data-ttu-id="b722c-124">您一次在授權頁面或 (頁面上指派授權給最多 20 個使用者) 授權。 </span><span class="sxs-lookup"><span data-stu-id="b722c-124">You assign licenses on the **Licenses** page (for up to 20 users at a time) or the **Active users** page.</span></span> <span data-ttu-id="b722c-125">您選擇的方法取決於您要管理特定使用者的產品授權，還是管理特定產品的使用者授權。</span><span class="sxs-lookup"><span data-stu-id="b722c-125">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="b722c-126">有關逐步指示，請參閱指派 [授權給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="b722c-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="b722c-127">如果您需要為大量使用者指派授權 ，例如數百或數千個使用者，請使用 Azure Active Directory (Azure AD) 中的 [Powershell 或群組型授權 ](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="b722c-127">If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use Powershell or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

## <a name="using-powershell"></a><span data-ttu-id="b722c-128">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b722c-128">Using PowerShell</span></span>

<span data-ttu-id="b722c-129">使用 PowerShell 大量指派授權給使用者。</span><span class="sxs-lookup"><span data-stu-id="b722c-129">Use PowerShell to assign licenses to users in bulk.</span></span>  <span data-ttu-id="b722c-130">若要深入瞭解，請參閱使用 [PowerShell 指派授權給使用者帳戶](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b722c-130">To learn more, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="example-script"></a><span data-ttu-id="b722c-131">範例腳本</span><span class="sxs-lookup"><span data-stu-id="b722c-131">Example script</span></span>

<span data-ttu-id="b722c-132">以下是如何使用腳本指派授權給使用者的範例。</span><span class="sxs-lookup"><span data-stu-id="b722c-132">Here's an example of how to use a script to assign licenses to your users.</span></span>

1. <span data-ttu-id="b722c-133">安裝適用于 IT 專業人員 [RTW](https://docs.microsoft.com/collaborate/connect-redirect?DownloadID=59185)的 64 位版本的 Microsoft Online Services 登入小幫手。</span><span class="sxs-lookup"><span data-stu-id="b722c-133">Install the 64-bit version of the [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://docs.microsoft.com/collaborate/connect-redirect?DownloadID=59185).</span></span>
2. <span data-ttu-id="b722c-134">安裝適用于 Windows PowerShell 的 Microsoft Azure Active Directory 模組：</span><span class="sxs-lookup"><span data-stu-id="b722c-134">Install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    1. <span data-ttu-id="b722c-135">開啟提升許可權的 Windows PowerShell 命令提示 (以系統管理員或系統管理員的) 。</span><span class="sxs-lookup"><span data-stu-id="b722c-135">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an admin).</span></span>
    2. <span data-ttu-id="b722c-136">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b722c-136">Run the following command:</span></span>
        ```powershell
        Install-Module MSOnline
        ```
    3. <span data-ttu-id="b722c-137">如果系統提示您安裝 NuGet 提供者，請輸入 **Y，** 然後按 Enter。</span><span class="sxs-lookup"><span data-stu-id="b722c-137">If you're prompted to install the NuGet provider, type **Y**, and then press Enter.</span></span>
    4. <span data-ttu-id="b722c-138">如果系統提示您從 PSGallery 安裝模組，請輸入 **Y，** 然後按 Enter。</span><span class="sxs-lookup"><span data-stu-id="b722c-138">If you're prompted to install the module from PSGallery, type **Y**, and then press Enter.</span></span>
3. <span data-ttu-id="b722c-139">在 Windows PowerShell 命令提示字元中，執行下列腳本以指派授權給使用者，其中會提供貴組織的名稱，以及您想要指派之授權識別碼 \<CompanyName:License> 。</span><span class="sxs-lookup"><span data-stu-id="b722c-139">At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where \<CompanyName:License> is your organization name and the identifier for the license that you want to assign.</span></span> <span data-ttu-id="b722c-140">例如，litwareinc：MCOMEETADV。</span><span class="sxs-lookup"><span data-stu-id="b722c-140">For example, litwareinc:MCOMEETADV.</span></span>

    <span data-ttu-id="b722c-141">識別碼與授權好用的名稱不同。</span><span class="sxs-lookup"><span data-stu-id="b722c-141">The identifier is different than the friendly name of the license.</span></span> <span data-ttu-id="b722c-142">例如，音訊會議識別碼為 MCOMEETADV。</span><span class="sxs-lookup"><span data-stu-id="b722c-142">For example, the identifier for Audio Conferencing is MCOMEETADV.</span></span> <span data-ttu-id="b722c-143">若要深入瞭解，請參閱 [授權的產品名稱和 SKU 識別碼](#product-names-and-sku-identifiers-for-licensing)。</span><span class="sxs-lookup"><span data-stu-id="b722c-143">To learn more, see [Product names and SKU identifiers for licensing](#product-names-and-sku-identifiers-for-licensing).</span></span>

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

    <span data-ttu-id="b722c-144">例如，若要指派 Microsoft 365 企業版 1 和音訊會議授權，請使用腳本中的下列語法：</span><span class="sxs-lookup"><span data-stu-id="b722c-144">For example, to assign Microsoft 365 Enterprise 1 and Audio Conferencing licenses, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    <span data-ttu-id="b722c-145">若要指派 Microsoft Business Voice (通話方案) 授權，請使用腳本中的下列語法：</span><span class="sxs-lookup"><span data-stu-id="b722c-145">To assign a Microsoft Business Voice (without Calling Plan) license, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a><span data-ttu-id="b722c-146">授權的產品名稱和 SKU 識別碼</span><span class="sxs-lookup"><span data-stu-id="b722c-146">Product names and SKU identifiers for licensing</span></span>

<span data-ttu-id="b722c-147">以下是部分產品名稱及其對應的 SKU 零件名稱清單，您可以在使用 PowerShell 管理 Teams 中的授權時做為參考。</span><span class="sxs-lookup"><span data-stu-id="b722c-147">Here's a partial list of product names and their corresponding SKU part names that you can use as a reference when you use PowerShell to manage licenses in Teams.</span></span>

<span data-ttu-id="b722c-148">若要深入瞭解，請參閱[使用 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)來查看授權和服務[](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)、授權的產品名稱與服務方案識別碼，以及[教育版 SKU 參考](../sku-reference-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="b722c-148">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu.md).</span></span>

| <span data-ttu-id="b722c-149">產品名稱</span><span class="sxs-lookup"><span data-stu-id="b722c-149">Product name</span></span>| <span data-ttu-id="b722c-150">SKU 零件名稱</span><span class="sxs-lookup"><span data-stu-id="b722c-150">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="b722c-151">Microsoft Enterprise E5 (Phone System) </span><span class="sxs-lookup"><span data-stu-id="b722c-151">Microsoft Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="b722c-152">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="b722c-152">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="b722c-153">Microsoft Enterprise E5 (音訊會議功能) </span><span class="sxs-lookup"><span data-stu-id="b722c-153">Microsoft Enterprise E5 (without Audio Conferencing)</span></span> | <span data-ttu-id="b722c-154">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="b722c-154">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="b722c-155">Microsoft Enterprise E5 (音訊會議功能) </span><span class="sxs-lookup"><span data-stu-id="b722c-155">Microsoft Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="b722c-156">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="b722c-156">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="b722c-157">Microsoft Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="b722c-157">Microsoft Enterprise E3</span></span> | <span data-ttu-id="b722c-158">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="b722c-158">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="b722c-159">Microsoft Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="b722c-159">Microsoft Enterprise E1</span></span> | <span data-ttu-id="b722c-160">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="b722c-160">STANDARDPACK</span></span> |
| <span data-ttu-id="b722c-161">Microsoft 365 商務基本版</span><span class="sxs-lookup"><span data-stu-id="b722c-161">Microsoft 365 Business Basic</span></span> | <span data-ttu-id="b722c-162">O365_BUSINESS_ESSENTIALS</span><span class="sxs-lookup"><span data-stu-id="b722c-162">O365_BUSINESS_ESSENTIALS</span></span>|
| <span data-ttu-id="b722c-163">Microsoft 365 商務標準版</span><span class="sxs-lookup"><span data-stu-id="b722c-163">Microsoft 365 Business Standard</span></span> | <span data-ttu-id="b722c-164">O365_BUSINESS_PREMIUM</span><span class="sxs-lookup"><span data-stu-id="b722c-164">O365_BUSINESS_PREMIUM</span></span>|
| <span data-ttu-id="b722c-165">Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="b722c-165">Microsoft 365 Business</span></span> | <span data-ttu-id="b722c-166">SPB</span><span class="sxs-lookup"><span data-stu-id="b722c-166">SPB</span></span>|
| <span data-ttu-id="b722c-167">Microsoft Business Voice (加拿大) </span><span class="sxs-lookup"><span data-stu-id="b722c-167">Microsoft Business Voice (Canada)</span></span>| <span data-ttu-id="b722c-168">BUSINESS_VOICE_MED</span><span class="sxs-lookup"><span data-stu-id="b722c-168">BUSINESS_VOICE_MED</span></span>  |
| <span data-ttu-id="b722c-169">Microsoft Business Voice (英國) </span><span class="sxs-lookup"><span data-stu-id="b722c-169">Microsoft Business Voice (United Kingdom)</span></span> | <span data-ttu-id="b722c-170">BUSINESS_VOICE</span><span class="sxs-lookup"><span data-stu-id="b722c-170">BUSINESS_VOICE</span></span>  |
| <span data-ttu-id="b722c-171">Microsoft Business Voice (美國) </span><span class="sxs-lookup"><span data-stu-id="b722c-171">Microsoft Business Voice (United States)</span></span> | <span data-ttu-id="b722c-172">BUSINESS_VOICE_MED2</span><span class="sxs-lookup"><span data-stu-id="b722c-172">BUSINESS_VOICE_MED2</span></span>  |
| <span data-ttu-id="b722c-173">不含通話 (的 Microsoft Business Voice) </span><span class="sxs-lookup"><span data-stu-id="b722c-173">Microsoft Business Voice (without Calling Plan)</span></span> | <span data-ttu-id="b722c-174">BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="b722c-174">BUSINESS_VOICE_DIRECTROUTING</span></span>  |
| <span data-ttu-id="b722c-175">Microsoft Business Voice (美國) 通話方案</span><span class="sxs-lookup"><span data-stu-id="b722c-175">Microsoft Business Voice (without Calling Plan) for the United States</span></span>| <span data-ttu-id="b722c-176">BUSINESS_VOICE_DIRECTROUTING _MED</span><span class="sxs-lookup"><span data-stu-id="b722c-176">BUSINESS_VOICE_DIRECTROUTING _MED</span></span> |
| <span data-ttu-id="b722c-177">音訊會議</span><span class="sxs-lookup"><span data-stu-id="b722c-177">Audio Conferencing</span></span> | <span data-ttu-id="b722c-178">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="b722c-178">MCOMEETADV</span></span> | 
| <span data-ttu-id="b722c-179">音訊會議每分鐘支付一 (，並隨著您的使用) </span><span class="sxs-lookup"><span data-stu-id="b722c-179">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="b722c-180">*需要設定及啟用通訊信用額度。*</span><span class="sxs-lookup"><span data-stu-id="b722c-180">*Requires Communications Credits to be set up and enabled.*</span></span> | <span data-ttu-id="b722c-181">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="b722c-181">MCOMEETACPEA</span></span> |
| <span data-ttu-id="b722c-182">電話系統</span><span class="sxs-lookup"><span data-stu-id="b722c-182">Phone System</span></span> | <span data-ttu-id="b722c-183">MCOEV</span><span class="sxs-lookup"><span data-stu-id="b722c-183">MCOEV</span></span> |
| <span data-ttu-id="b722c-184">國內及國際通話方案</span><span class="sxs-lookup"><span data-stu-id="b722c-184">Domestic and International Calling Plan</span></span> | <span data-ttu-id="b722c-185">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="b722c-185">MCOPSTN2</span></span> |
| <span data-ttu-id="b722c-186">國內通話方案 (美國/PR/CA/每個使用者每月 3000 分鐘，針對歐盟國家/地區，每個使用者/月 1200 分鐘) </span><span class="sxs-lookup"><span data-stu-id="b722c-186">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="b722c-187">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="b722c-187">MCOPSTN1</span></span> |
| <span data-ttu-id="b722c-188">每個國家/ (的國內通話方案每一個使用者/月需要 120) </span><span class="sxs-lookup"><span data-stu-id="b722c-188">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="b722c-189">*此方案不適用於美國。*</span><span class="sxs-lookup"><span data-stu-id="b722c-189">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="b722c-190">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="b722c-190">MCOPSTN5</span></span> |
| <span data-ttu-id="b722c-191">每個國家/ (的國內通話方案為每個使用者/月 240) </span><span class="sxs-lookup"><span data-stu-id="b722c-191">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="b722c-192">*此方案不適用於美國。*</span><span class="sxs-lookup"><span data-stu-id="b722c-192">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="b722c-193">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="b722c-193">MCOPSTN6</span></span> |
| <span data-ttu-id="b722c-194">通訊點數</span><span class="sxs-lookup"><span data-stu-id="b722c-194">Communications Credits</span></span> | <span data-ttu-id="b722c-195">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="b722c-195">MCOPSTNPP</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b722c-196">相關主題</span><span class="sxs-lookup"><span data-stu-id="b722c-196">Related topics</span></span>

- [<span data-ttu-id="b722c-197">Teams 附加元件授權</span><span class="sxs-lookup"><span data-stu-id="b722c-197">Teams add-on licensing</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
- [<span data-ttu-id="b722c-198">管理使用者對 Teams 的存取權</span><span class="sxs-lookup"><span data-stu-id="b722c-198">Manage user access to Teams</span></span>](../user-access.md)
- [<span data-ttu-id="b722c-199">使用 PowerShell 來查看授權和服務</span><span class="sxs-lookup"><span data-stu-id="b722c-199">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="b722c-200">用於授權的產品名稱和服務方案識別碼</span><span class="sxs-lookup"><span data-stu-id="b722c-200">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="b722c-201">教育用 SKU 參考</span><span class="sxs-lookup"><span data-stu-id="b722c-201">Education SKU reference</span></span>](../sku-reference-edu.md)
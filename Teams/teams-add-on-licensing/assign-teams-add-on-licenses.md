---
title: 指派團隊附加元件授權給使用者
author: LanaChin
ms.author: v-lanac
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
description: 瞭解如何將團隊附加元件授權指派給使用者，以取得音訊會議、電話系統和通話方案等功能。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c7faaf2e65330aafd809872ed19b5f2f16afc668
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868580"
---
# <a name="assign-teams-add-on-licenses-to-users"></a><span data-ttu-id="36716-103">指派團隊附加元件授權給使用者</span><span class="sxs-lookup"><span data-stu-id="36716-103">Assign Teams add-on licenses to users</span></span>

<span data-ttu-id="36716-104">附加元件授權是特定團隊功能（例如音訊會議、電話系統和通話方案）的授權。</span><span class="sxs-lookup"><span data-stu-id="36716-104">Add-on licenses are licenses for specific Teams features such as Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="36716-105">本文說明如何將附加元件授權指派給個別使用者，以及大量使用者。</span><span class="sxs-lookup"><span data-stu-id="36716-105">This article describes how to assign add-on licenses to individual users and to large sets of users in bulk.</span></span>

> [!NOTE]
> <span data-ttu-id="36716-106">請參閱[小組附加元件授權](microsoft-teams-add-on-licensing.md)，瞭解適用于附加元件授權的小組功能。</span><span class="sxs-lookup"><span data-stu-id="36716-106">See [Teams add-on licensing](microsoft-teams-add-on-licensing.md) for Teams features that are available with add-on licenses.</span></span> <span data-ttu-id="36716-107">您也可以找到需要購買哪些授權，以及如何購買（視您的方案而定）的相關資訊，讓使用者取得音訊會議、免付費電話號碼，以及撥打貴組織外部電話號碼的功能。</span><span class="sxs-lookup"><span data-stu-id="36716-107">You'll also find information about what licenses you need to buy and how to buy them (depending on your plan), so users can get features such as Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your organization.</span></span> <span data-ttu-id="36716-108">在您決定要為使用者提供哪些功能之後，請將授權指派給他們。</span><span class="sxs-lookup"><span data-stu-id="36716-108">After you decide  which features you want for your users, assign the licenses to them.</span></span>

<span data-ttu-id="36716-109">您可以使用 Microsoft 365 系統管理中心或 PowerShell，指派授權給貴組織中的使用者。</span><span class="sxs-lookup"><span data-stu-id="36716-109">You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization.</span></span> <span data-ttu-id="36716-110">您必須是全域系統管理員或使用者管理系統管理員，才能管理授權。</span><span class="sxs-lookup"><span data-stu-id="36716-110">You must be a Global admin or User management admin to manage licenses.</span></span>

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a><span data-ttu-id="36716-111">指派電話系統、通話方案和通訊信用授權前需要注意的事項</span><span class="sxs-lookup"><span data-stu-id="36716-111">What you need to know before you assign Phone System, Calling Plan, and Communication Credits licenses</span></span>

<span data-ttu-id="36716-112">在您開始之前，請先檢查下列專案：</span><span class="sxs-lookup"><span data-stu-id="36716-112">Before you get started, review the following:</span></span>

- <span data-ttu-id="36716-113">如果您是針對混合式使用者使用內部部署的公用交換電話網絡（PSTN）連線，則只需指派電話系統授權即可。</span><span class="sxs-lookup"><span data-stu-id="36716-113">If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for hybrid users, you only need to assign a Phone System license.</span></span> <span data-ttu-id="36716-114">請勿指派通話方案授權。</span><span class="sxs-lookup"><span data-stu-id="36716-114">Do NOT assign a Calling Plan license.</span></span>

- <span data-ttu-id="36716-115">由於 Microsoft 365 與 Microsoft 團隊之間的延遲，在指派授權之後，可能需要長達24小時的時間指派通話方案。</span><span class="sxs-lookup"><span data-stu-id="36716-115">Because of the latency between Microsoft 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="36716-116">如果使用者在24小時後未獲指派通話方案，[請聯絡商務產品支援-系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="36716-116">If the user isn't assigned a Calling Plan after 24 hours, [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="36716-117">如果您還沒有購買正確數量的授權，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="36716-117">You'll get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="36716-118">如果您需要購買更多通話方案授權，請選擇購買更多的選項。</span><span class="sxs-lookup"><span data-stu-id="36716-118">If you need to buy more Calling Plan licenses, choose the option to buy more.</span></span>

- <span data-ttu-id="36716-119">即使您的使用者已獲指派企業版 E5 授權，但如果他們想要從 PSTN 撥打或接聽電話，仍需將[通訊信用](../what-are-communications-credits.md)權指派給他們。</span><span class="sxs-lookup"><span data-stu-id="36716-119">Even if your users are assigned Enterprise E5 licenses, you still need to assign [Communications Credits](../what-are-communications-credits.md) licenses to them if they want make or receive calls from the PSTN.</span></span>

- <span data-ttu-id="36716-120">在您將通話方案或通訊信用授權指派給使用者之後，您必須取得貴組織的電話號碼，然後將這些號碼指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="36716-120">After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users.</span></span> <span data-ttu-id="36716-121">如需逐步指示，請參閱[設定通話方案](../set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="36716-121">For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans.md).</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="36716-122">使用 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="36716-122">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="36716-123">使用 Microsoft 365 系統管理中心，一次將授權指派給個別的使用者或一組小的使用者。</span><span class="sxs-lookup"><span data-stu-id="36716-123">Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.</span></span> <span data-ttu-id="36716-124">您可以在 [**授權**] 頁面上指派授權（一次最多20名使用者）或 [作用中的**使用者**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="36716-124">You can assign licenses on the **Licenses** page (for up to 20 users at a time) or the **Active users** page.</span></span> <span data-ttu-id="36716-125">您選擇的方法取決於您是否要管理特定使用者的產品授權，或管理特定產品的使用者授權。</span><span class="sxs-lookup"><span data-stu-id="36716-125">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="36716-126">如需逐步指示，請參閱[指派授權給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="36716-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="36716-127">如果您需要指派大量使用者（例如幾百或數千位使用者）的授權，請[在 Azure Active Directory （AZURE AD）中使用 Powershell 或群組式授權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="36716-127">If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use Powershell or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

## <a name="using-powershell"></a><span data-ttu-id="36716-128">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="36716-128">Using PowerShell</span></span>

<span data-ttu-id="36716-129">使用 PowerShell 來大量指派授權給使用者。</span><span class="sxs-lookup"><span data-stu-id="36716-129">Use PowerShell to assign licenses to users in bulk.</span></span>  <span data-ttu-id="36716-130">若要深入瞭解，請參閱[使用 PowerShell 指派授權給使用者帳戶](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="36716-130">To learn more, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="example-script"></a><span data-ttu-id="36716-131">範例腳本</span><span class="sxs-lookup"><span data-stu-id="36716-131">Example script</span></span>

<span data-ttu-id="36716-132">以下範例說明如何使用腳本來指派授權給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="36716-132">Here's an example of how to use a script to assign licenses to your users.</span></span>

1. <span data-ttu-id="36716-133">安裝[適用于 IT 專業人員](https://go.microsoft.com/fwlink/p/?LinkId=286152)的64位版本的 Microsoft Online Services 登入小幫手 RTW。</span><span class="sxs-lookup"><span data-stu-id="36716-133">Install the 64-bit version of the [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
2. <span data-ttu-id="36716-134">安裝適用于 Windows PowerShell 的 Microsoft Azure Active Directory 模組：</span><span class="sxs-lookup"><span data-stu-id="36716-134">Install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    1. <span data-ttu-id="36716-135">開啟提升許可權的 Windows PowerShell 命令提示字元（以系統管理員身分執行 Windows PowerShell）。</span><span class="sxs-lookup"><span data-stu-id="36716-135">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an admin).</span></span>
    2. <span data-ttu-id="36716-136">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="36716-136">Run the following command:</span></span>
        ```powershell
        Install-Module MSOnline
        ```
    3. <span data-ttu-id="36716-137">如果系統提示您安裝 NuGet 提供者，請輸入**Y**，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="36716-137">If you're prompted to install the NuGet provider, type **Y**, and then press Enter.</span></span>
    4. <span data-ttu-id="36716-138">如果系統提示您從 PSGallery 安裝模組，請輸入**Y**，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="36716-138">If you're prompted to install the module from PSGallery, type **Y**, and then press Enter.</span></span>
3. <span data-ttu-id="36716-139">在 Windows PowerShell 命令提示字元中，執行下列腳本來指派授權給您的使用者，其中 \<CompanyName:License> 是您的組織名稱，以及您要指派之授權的識別碼。</span><span class="sxs-lookup"><span data-stu-id="36716-139">At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where \<CompanyName:License> is your organization name and the identifier for the license that you want to assign.</span></span> <span data-ttu-id="36716-140">例如，litwareinc： MCOMEETADV。</span><span class="sxs-lookup"><span data-stu-id="36716-140">For example, litwareinc:MCOMEETADV.</span></span>

    <span data-ttu-id="36716-141">識別碼與授權的易記名稱不同。</span><span class="sxs-lookup"><span data-stu-id="36716-141">The identifier is different than the friendly name of the license.</span></span> <span data-ttu-id="36716-142">例如，音訊會議的識別碼是 MCOMEETADV。</span><span class="sxs-lookup"><span data-stu-id="36716-142">For example, the identifier for Audio Conferencing is MCOMEETADV.</span></span> <span data-ttu-id="36716-143">若要深入瞭解，請參閱[授權的產品名稱和 SKU 識別碼](#product-names-and-sku-identifiers-for-licensing)。</span><span class="sxs-lookup"><span data-stu-id="36716-143">To learn more, see [Product names and SKU identifiers for licensing](#product-names-and-sku-identifiers-for-licensing).</span></span>

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

    <span data-ttu-id="36716-144">例如，若要指派 Microsoft 365 企業版1和音訊會議授權，請在腳本中使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="36716-144">For example, to assign Microsoft 365 Enterprise 1 and Audio Conferencing licenses, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    <span data-ttu-id="36716-145">若要指派 Microsoft 商務語音（不含通話計畫）授權，請在腳本中使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="36716-145">To assign a Microsoft Business Voice (without Calling Plan) license, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a><span data-ttu-id="36716-146">授權的產品名稱和 SKU 識別碼</span><span class="sxs-lookup"><span data-stu-id="36716-146">Product names and SKU identifiers for licensing</span></span>

<span data-ttu-id="36716-147">以下是產品名稱的部分清單及其對應的 SKU 元件名稱，當您使用 PowerShell 管理團隊中的授權時，您可以使用這些名稱作為參考。</span><span class="sxs-lookup"><span data-stu-id="36716-147">Here's a partial list of product names and their corresponding SKU part names that you can use as a reference when you use PowerShell to manage licenses in Teams.</span></span>

<span data-ttu-id="36716-148">若要深入瞭解，請參閱[使用 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)、[產品名稱和服務方案識別碼來查看授權及服務，以取得授權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)及[教育 SKU 參考](../sku-reference-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="36716-148">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu.md).</span></span>

| <span data-ttu-id="36716-149">產品名稱</span><span class="sxs-lookup"><span data-stu-id="36716-149">Product name</span></span>| <span data-ttu-id="36716-150">SKU 元件名稱</span><span class="sxs-lookup"><span data-stu-id="36716-150">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="36716-151">Microsoft 企業版 E5 （含電話系統）</span><span class="sxs-lookup"><span data-stu-id="36716-151">Microsoft Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="36716-152">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="36716-152">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="36716-153">Microsoft 企業版 E5 （不含音訊會議）</span><span class="sxs-lookup"><span data-stu-id="36716-153">Microsoft Enterprise E5 (without Audio Conferencing)</span></span> | <span data-ttu-id="36716-154">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="36716-154">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="36716-155">Microsoft 企業版 E5 （含音訊會議）</span><span class="sxs-lookup"><span data-stu-id="36716-155">Microsoft Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="36716-156">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="36716-156">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="36716-157">Microsoft 企業版 E3</span><span class="sxs-lookup"><span data-stu-id="36716-157">Microsoft Enterprise E3</span></span> | <span data-ttu-id="36716-158">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="36716-158">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="36716-159">Microsoft 企業版 E1</span><span class="sxs-lookup"><span data-stu-id="36716-159">Microsoft Enterprise E1</span></span> | <span data-ttu-id="36716-160">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="36716-160">STANDARDPACK</span></span> |
| <span data-ttu-id="36716-161">Microsoft 365 商務基本版</span><span class="sxs-lookup"><span data-stu-id="36716-161">Microsoft 365 Business Basic</span></span> | <span data-ttu-id="36716-162">O365_BUSINESS_ESSENTIALS</span><span class="sxs-lookup"><span data-stu-id="36716-162">O365_BUSINESS_ESSENTIALS</span></span>|
| <span data-ttu-id="36716-163">Microsoft 365 商務標準版</span><span class="sxs-lookup"><span data-stu-id="36716-163">Microsoft 365 Business Standard</span></span> | <span data-ttu-id="36716-164">O365_BUSINESS_PREMIUM</span><span class="sxs-lookup"><span data-stu-id="36716-164">O365_BUSINESS_PREMIUM</span></span>|
| <span data-ttu-id="36716-165">Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="36716-165">Microsoft 365 Business</span></span> | <span data-ttu-id="36716-166">SPB</span><span class="sxs-lookup"><span data-stu-id="36716-166">SPB</span></span>|
| <span data-ttu-id="36716-167">Microsoft 商務語音（加拿大）</span><span class="sxs-lookup"><span data-stu-id="36716-167">Microsoft Business Voice (Canada)</span></span>| <span data-ttu-id="36716-168">BUSINESS_VOICE_MED</span><span class="sxs-lookup"><span data-stu-id="36716-168">BUSINESS_VOICE_MED</span></span>  |
| <span data-ttu-id="36716-169">Microsoft 商務語音（英國）</span><span class="sxs-lookup"><span data-stu-id="36716-169">Microsoft Business Voice (United Kingdom)</span></span> | <span data-ttu-id="36716-170">BUSINESS_VOICE</span><span class="sxs-lookup"><span data-stu-id="36716-170">BUSINESS_VOICE</span></span>  |
| <span data-ttu-id="36716-171">Microsoft 商務語音（美國）</span><span class="sxs-lookup"><span data-stu-id="36716-171">Microsoft Business Voice (United States)</span></span> | <span data-ttu-id="36716-172">BUSINESS_VOICE_MED2</span><span class="sxs-lookup"><span data-stu-id="36716-172">BUSINESS_VOICE_MED2</span></span>  |
| <span data-ttu-id="36716-173">Microsoft 商務語音（無需通話方案）</span><span class="sxs-lookup"><span data-stu-id="36716-173">Microsoft Business Voice (without Calling Plan)</span></span> | <span data-ttu-id="36716-174">BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="36716-174">BUSINESS_VOICE_DIRECTROUTING</span></span>  |
| <span data-ttu-id="36716-175">適用于美國的 Microsoft 商務語音（不含通話方案）</span><span class="sxs-lookup"><span data-stu-id="36716-175">Microsoft Business Voice (without Calling Plan) for the United States</span></span>| <span data-ttu-id="36716-176">BUSINESS_VOICE_DIRECTROUTING _MED</span><span class="sxs-lookup"><span data-stu-id="36716-176">BUSINESS_VOICE_DIRECTROUTING _MED</span></span> |
| <span data-ttu-id="36716-177">音訊會議</span><span class="sxs-lookup"><span data-stu-id="36716-177">Audio Conferencing</span></span> | <span data-ttu-id="36716-178">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="36716-178">MCOMEETADV</span></span> | 
| <span data-ttu-id="36716-179">每分鐘付費語音會議（隨您的付費）</span><span class="sxs-lookup"><span data-stu-id="36716-179">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="36716-180">*需要設定並啟用通訊信用額度。*</span><span class="sxs-lookup"><span data-stu-id="36716-180">*Requires Communications Credits to be set up and enabled.*</span></span> | <span data-ttu-id="36716-181">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="36716-181">MCOMEETACPEA</span></span> |
| <span data-ttu-id="36716-182">電話系統</span><span class="sxs-lookup"><span data-stu-id="36716-182">Phone System</span></span> | <span data-ttu-id="36716-183">MCOEV</span><span class="sxs-lookup"><span data-stu-id="36716-183">MCOEV</span></span> |
| <span data-ttu-id="36716-184">國內和國際通話方案</span><span class="sxs-lookup"><span data-stu-id="36716-184">Domestic and International Calling Plan</span></span> | <span data-ttu-id="36716-185">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="36716-185">MCOPSTN2</span></span> |
| <span data-ttu-id="36716-186">國內通話方案（每個使用者/每個月的每個使用者/每個月的每個月的3000分鐘1200，歐盟國家/地區的每個使用者/月份）</span><span class="sxs-lookup"><span data-stu-id="36716-186">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="36716-187">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="36716-187">MCOPSTN1</span></span> |
| <span data-ttu-id="36716-188">國內通話方案（每個國家/地區每個使用者/月的120分鐘）</span><span class="sxs-lookup"><span data-stu-id="36716-188">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="36716-189">*美國未提供此方案。*</span><span class="sxs-lookup"><span data-stu-id="36716-189">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="36716-190">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="36716-190">MCOPSTN5</span></span> |
| <span data-ttu-id="36716-191">國內通話方案（每個國家/地區每個使用者/月的240分鐘）</span><span class="sxs-lookup"><span data-stu-id="36716-191">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="36716-192">*美國未提供此方案。*</span><span class="sxs-lookup"><span data-stu-id="36716-192">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="36716-193">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="36716-193">MCOPSTN6</span></span> |
| <span data-ttu-id="36716-194">通訊點數</span><span class="sxs-lookup"><span data-stu-id="36716-194">Communications Credits</span></span> | <span data-ttu-id="36716-195">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="36716-195">MCOPSTNPP</span></span> |

## <a name="related-topics"></a><span data-ttu-id="36716-196">相關主題</span><span class="sxs-lookup"><span data-stu-id="36716-196">Related topics</span></span>

- [<span data-ttu-id="36716-197">Teams 附加元件授權</span><span class="sxs-lookup"><span data-stu-id="36716-197">Teams add-on licensing</span></span>](microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="36716-198">管理使用者對 Teams 的存取權</span><span class="sxs-lookup"><span data-stu-id="36716-198">Manage user access to Teams</span></span>](../user-access.md)
- [<span data-ttu-id="36716-199">使用 PowerShell 來查看授權與服務</span><span class="sxs-lookup"><span data-stu-id="36716-199">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="36716-200">用於授權的產品名稱和服務方案識別碼</span><span class="sxs-lookup"><span data-stu-id="36716-200">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="36716-201">教育版 SKU 參考</span><span class="sxs-lookup"><span data-stu-id="36716-201">Education SKU reference</span></span>](../sku-reference-edu.md)
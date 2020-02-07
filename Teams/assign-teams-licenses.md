---
title: 指派 Teams 授權
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: 瞭解如何指派音訊會議、電話系統和通話方案等功能的授權。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 967b67c1d8bc92009e1319260373c9b8abc52b99
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826311"
---
# <a name="assign-microsoft-teams-licenses"></a><span data-ttu-id="77471-103">指派 Microsoft 團隊授權</span><span class="sxs-lookup"><span data-stu-id="77471-103">Assign Microsoft Teams licenses</span></span>

<span data-ttu-id="77471-104">您可以將授權指派給使用者，以取得音訊會議、電話系統和通話方案等功能。</span><span class="sxs-lookup"><span data-stu-id="77471-104">You can assign licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="77471-105">本文說明如何大量為個別使用者新增這些授權。</span><span class="sxs-lookup"><span data-stu-id="77471-105">This article explains how to add these licenses in bulk and for an individual user.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="77471-106">請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)，以取得您需要購買哪些授權，以及如何購買它們（視您的 Office 365 方案而定），讓使用者可以取得音訊會議、免付費電話號碼，以及撥打電話給企業外部的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="77471-106">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and how to buy them, depending on your Office 365 plan, so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="77471-107">電話系統與通話方案：指派授權的秘訣與腳本</span><span class="sxs-lookup"><span data-stu-id="77471-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="77471-108">以下是在指派音訊會議、電話系統和通話方案授權前，您需要知道的事項。</span><span class="sxs-lookup"><span data-stu-id="77471-108">Here’s what you need to know before assigning Audio Conferencing, Phone System, and Calling Plan licenses.</span></span>

- <span data-ttu-id="77471-109">**針對混合式使用者使用內部部署 PSTN 連線能力？**</span><span class="sxs-lookup"><span data-stu-id="77471-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="77471-110">如果是這樣，您只需要指派電話系統授權即可。</span><span class="sxs-lookup"><span data-stu-id="77471-110">If so, you only need to assign a Phone System license.</span></span> <span data-ttu-id="77471-111">您不應該指派通話方案。</span><span class="sxs-lookup"><span data-stu-id="77471-111">You should NOT assign a Calling Plan.</span></span>

- <span data-ttu-id="77471-112">**指派授權之後的延遲**：由於 Office 365 與 Microsoft 團隊之間的延遲，在指派授權之後，可能需要長達24小時才能指派通話方案。</span><span class="sxs-lookup"><span data-stu-id="77471-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="77471-113">如果在24小時之後，使用者並未獲指派通話方案，請[與商務用支援人員聯繫，以取得系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="77471-113">If after 24 hours the user isn't assigned a Calling Plan, please [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="77471-114">**錯誤訊息**：如果您尚未購買正確數量的授權，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="77471-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="77471-115">如果您需要購買更多通話方案授權，請選擇 [**購買更多**]。</span><span class="sxs-lookup"><span data-stu-id="77471-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>

- <span data-ttu-id="77471-116">**後續步驟**：將通話方案授權指派給使用者之後，您將需要取得貴組織的電話號碼，然後將這些號碼指派給組織中的人員。</span><span class="sxs-lookup"><span data-stu-id="77471-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="77471-117">如需逐步指示，請參閱[設定通話方案](set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="77471-117">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="77471-118">指派電話系統和通話方案授權給一名使用者</span><span class="sxs-lookup"><span data-stu-id="77471-118">Assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="77471-119">這些步驟與指派 Office 365 授權是一樣的。</span><span class="sxs-lookup"><span data-stu-id="77471-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="77471-120">請參閱[指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="77471-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="77471-121">大量指派電話系統和通話方案授權</span><span class="sxs-lookup"><span data-stu-id="77471-121">Assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="77471-122">安裝適用于 IT 專業人員的 Microsoft Online Services 登入小幫手 RTW。</span><span class="sxs-lookup"><span data-stu-id="77471-122">Install the Microsoft Online Services Sign-In Assistant for IT Professionals RTW.</span></span> <span data-ttu-id="77471-123">沒有安裝該模組嗎？</span><span class="sxs-lookup"><span data-stu-id="77471-123">Don't have the module installed?</span></span> <span data-ttu-id="77471-124">請參閱[適用于 IT 專業人員的 Microsoft Online Services 登入](https://go.microsoft.com/fwlink/?LinkId=625123)小幫手 RTW 以下載它。</span><span class="sxs-lookup"><span data-stu-id="77471-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="77471-125">安裝 Windows Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="77471-125">Install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="77471-126">沒有安裝該模組嗎？</span><span class="sxs-lookup"><span data-stu-id="77471-126">Don't have the module installed?</span></span> <span data-ttu-id="77471-127">如需下載指示與 Cmdlet 語法，請參閱[使用 Windows PowerShell 管理 AZURE AD](https://go.microsoft.com/fwlink/p/?LinkId=320628) 。</span><span class="sxs-lookup"><span data-stu-id="77471-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="77471-128">安裝模組後，請使用 Windows PowerShell 命令提示字元及下列語法，將授權指派給您的使用者：</span><span class="sxs-lookup"><span data-stu-id="77471-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="77471-129">這個範例會指派企業版 E3 授權，以及手機系統和國內通話方案授權。</span><span class="sxs-lookup"><span data-stu-id="77471-129">This example assigns an Enterprise E3 license along with a Phone System and a Domestic Calling Plan license.</span></span>

<span data-ttu-id="77471-130">腳本中的授權或產品名稱的名稱會以斜體列出（請參閱在此範例之後，請參閱[電話系統和通話方案產品名稱或 sku 用於腳本](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting)）。</span><span class="sxs-lookup"><span data-stu-id="77471-130">The name of the licenses or product names in the script are listed in italics (see [Phone System and Calling Plans product names or SKUs used for scripting](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), after the example).</span></span>

```
#Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.

#Example of text file:
#user1@domain.com
#user2@domain.com

#Import Module
ipmo MSOnline
#Authenticate to MSOLservice.
Connect-MSOLService
#File prompt to select the userlist txt file.
[System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
$OFD = New-Object System.Windows.Forms.OpenFileDialog
$OFD.filter = "text files (*.*)| *.txt"
$OFD.ShowDialog() | Out-Null
$OFD.filename
If ($OFD.filename -eq '')
{
 Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
}
#Create a variable of all users.
$users = Get-Content $OFD.filename
#License each user in the $users variable.
#Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
International Calling.
for each ($user in $users)
 {
 Write-host "Assigning License: $user"
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
 }

```
## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="77471-131">用於腳本的電話系統和通話方案產品名稱或 Sku</span><span class="sxs-lookup"><span data-stu-id="77471-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

| <span data-ttu-id="77471-132">產品名稱</span><span class="sxs-lookup"><span data-stu-id="77471-132">Product name</span></span> | <span data-ttu-id="77471-133">SKU 元件名稱</span><span class="sxs-lookup"><span data-stu-id="77471-133">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="77471-134">企業版 E5 （含電話系統）</span><span class="sxs-lookup"><span data-stu-id="77471-134">Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="77471-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="77471-135">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="77471-136">企業版 E3</span><span class="sxs-lookup"><span data-stu-id="77471-136">Enterprise E3</span></span> | <span data-ttu-id="77471-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="77471-137">ENTERPRISEPACK</span></span> | 
| <span data-ttu-id="77471-138">企業版 E1</span><span class="sxs-lookup"><span data-stu-id="77471-138">Enterprise E1</span></span> | <span data-ttu-id="77471-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="77471-139">STANDARDPACK</span></span> | 
| <span data-ttu-id="77471-140">電話系統</span><span class="sxs-lookup"><span data-stu-id="77471-140">Phone System</span></span> | <span data-ttu-id="77471-141">MCOEV</span><span class="sxs-lookup"><span data-stu-id="77471-141">MCOEV</span></span> |
| <span data-ttu-id="77471-142">國內 & 國際通話方案</span><span class="sxs-lookup"><span data-stu-id="77471-142">Domestic & International Calling Plan</span></span> | <span data-ttu-id="77471-143">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="77471-143">MCOPSTN2</span></span> |
| <span data-ttu-id="77471-144">國內通話方案（每個使用者/每個月的每個使用者/每個月的每個月的3000分鐘1200，歐盟國家/地區的每個使用者/月份）</span><span class="sxs-lookup"><span data-stu-id="77471-144">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="77471-145">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="77471-145">MCOPSTN1</span></span> |
| <span data-ttu-id="77471-146">國內通話方案（每個國家/地區每個使用者/月的120分鐘）</span><span class="sxs-lookup"><span data-stu-id="77471-146">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="77471-147">*注意：此方案不適用於我們*。</span><span class="sxs-lookup"><span data-stu-id="77471-147">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="77471-148">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="77471-148">MCOPSTN5</span></span> |
| <span data-ttu-id="77471-149">國內通話方案（每個國家/地區每個使用者/月的240分鐘）</span><span class="sxs-lookup"><span data-stu-id="77471-149">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="77471-150">*注意：此方案不適用於我們*。</span><span class="sxs-lookup"><span data-stu-id="77471-150">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="77471-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="77471-151">MCOPSTN6</span></span> |
| <span data-ttu-id="77471-152">通訊點數</span><span class="sxs-lookup"><span data-stu-id="77471-152">Communications Credits</span></span> | <span data-ttu-id="77471-153">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="77471-153">MCOPSTNPP</span></span> | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="77471-154">音訊會議：指派授權的秘訣與腳本</span><span class="sxs-lookup"><span data-stu-id="77471-154">Audio Conferencing: tips and scripts for assigning licenses</span></span>

<span data-ttu-id="77471-155">以下是指派音訊會議授權前需要注意的事項。</span><span class="sxs-lookup"><span data-stu-id="77471-155">Here's what you need to know before assigning Audio Conferencing licenses.</span></span>

- <span data-ttu-id="77471-156">**協力廠商音訊會議提供者**：如果某人已設定為使用協力廠商音訊會議提供者，當您指派音訊會議授權時，系統會將其變更為使用 Microsoft 作為音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="77471-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an Audio Conferencing license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="77471-157">您可以將它們變更回協力廠商提供者。</span><span class="sxs-lookup"><span data-stu-id="77471-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="77471-158">**後續步驟**：指派音訊會議授權之後，您需要指派音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="77471-158">**Next steps**: After you assign Audio Conferencing licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="77471-159">請參閱[將 Microsoft 指派為音訊會議提供者](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。</span><span class="sxs-lookup"><span data-stu-id="77471-159">See [Assign Microsoft as the audio conferencing provider](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

## <a name="assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="77471-160">將音訊會議授權指派給一名使用者</span><span class="sxs-lookup"><span data-stu-id="77471-160">Assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="77471-161">這些步驟與指派 Office 365 授權是一樣的。</span><span class="sxs-lookup"><span data-stu-id="77471-161">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="77471-162">請參閱[指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="77471-162">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="77471-163">大量指派音訊會議授權</span><span class="sxs-lookup"><span data-stu-id="77471-163">Assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="77471-164">下載並安裝[適用于 IT 專業人員的 Microsoft Online Services 登入](https://go.microsoft.com/fwlink/?LinkId=625123)小幫手 RTW。</span><span class="sxs-lookup"><span data-stu-id="77471-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="77471-165">下載並安裝 Windows Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="77471-165">Download and install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="77471-166">如需下載指示與 Cmdlet 語法，請參閱[使用 Windows PowerShell 管理 AZURE AD](https://go.microsoft.com/fwlink/p/?LinkId=320628) 。</span><span class="sxs-lookup"><span data-stu-id="77471-166">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

<span data-ttu-id="77471-167">安裝模組後，請使用 Windows PowerShell 命令提示字元及下列語法，將授權指派給您的使用者：</span><span class="sxs-lookup"><span data-stu-id="77471-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="77471-168">腳本中授權或產品名稱的名稱會以斜體列出。</span><span class="sxs-lookup"><span data-stu-id="77471-168">The name of the licenses or product names in the script are listed in italics.</span></span> <span data-ttu-id="77471-169">請參閱[音訊會議產品名稱或 sku，以供](#audio-conferencing-product-names-or-skus-used-for-scripting)所有產品名稱的腳本使用。</span><span class="sxs-lookup"><span data-stu-id="77471-169">See [Audio Conferencing product names or SKUS used for scripting](#audio-conferencing-product-names-or-skus-used-for-scripting) for all of the product names.</span></span>

<span data-ttu-id="77471-170">這個範例會指派企業版 E3 授權以及音訊會議授權。</span><span class="sxs-lookup"><span data-stu-id="77471-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

```
#Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
#Example of text file:
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
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOMEETADV " -ErrorAction SilentlyContinue
    }
```
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="77471-171">用於腳本的音訊會議產品名稱或 SKU</span><span class="sxs-lookup"><span data-stu-id="77471-171">Audio Conferencing product names or SKUS used for scripting</span></span>

| <span data-ttu-id="77471-172">產品名稱</span><span class="sxs-lookup"><span data-stu-id="77471-172">Product name</span></span> | <span data-ttu-id="77471-173">SKU 元件名稱</span><span class="sxs-lookup"><span data-stu-id="77471-173">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="77471-174">音訊會議（訂閱）</span><span class="sxs-lookup"><span data-stu-id="77471-174">Audio Conferencing (subscription)</span></span> | <span data-ttu-id="77471-175">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="77471-175">MCOMEETADV</span></span> | 
| <span data-ttu-id="77471-176">每分鐘付費語音會議（隨您的付費）</span><span class="sxs-lookup"><span data-stu-id="77471-176">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="77471-177">*注意：需要設定並啟用通訊點數*。</span><span class="sxs-lookup"><span data-stu-id="77471-177">*Note: Requires Communications Credits to be set up and enabled*.</span></span> | <span data-ttu-id="77471-178">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="77471-178">MCOMEETACPEA</span></span> |
| <span data-ttu-id="77471-179">企業版 E1</span><span class="sxs-lookup"><span data-stu-id="77471-179">Enterprise E1</span></span> | <span data-ttu-id="77471-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="77471-180">STANDARDPACK</span></span> | 
| <span data-ttu-id="77471-181">企業版 E3</span><span class="sxs-lookup"><span data-stu-id="77471-181">Enterprise E3</span></span> | <span data-ttu-id="77471-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="77471-182">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="77471-183">企業版 E5 （不含音訊會議）</span><span class="sxs-lookup"><span data-stu-id="77471-183">Enterprise E5 (without Audio Conferencing)</span></span> |  <span data-ttu-id="77471-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="77471-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="77471-185">企業版 E5 （含音訊會議）</span><span class="sxs-lookup"><span data-stu-id="77471-185">Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="77471-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="77471-186">ENTERPRISEPREMIUM</span></span> |

##  <a name="communications-credits"></a><span data-ttu-id="77471-187">通訊點數</span><span class="sxs-lookup"><span data-stu-id="77471-187">Communications Credits</span></span>

<span data-ttu-id="77471-188">以下是在指派通訊信用權前，您需要知道的事項。</span><span class="sxs-lookup"><span data-stu-id="77471-188">Here's what you need to know before assigning Communications Credits licenses.</span></span>

- <span data-ttu-id="77471-189">**企業版 E5 客戶**：即使您的使用者已獲指派企業版 e5 授權，我們仍建議您指派其通訊信用額度授權。</span><span class="sxs-lookup"><span data-stu-id="77471-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them Communications Credits licenses.</span></span>

- <span data-ttu-id="77471-190">**後續步驟**：在您指派這些授權之後，您必須取得貴組織的電話號碼，然後將這些號碼指派給貴組織中的人員。</span><span class="sxs-lookup"><span data-stu-id="77471-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="77471-191">如需逐步指示，請參閱[設定通話方案](set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="77471-191">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="77471-192">指派通訊點數授權給一名使用者</span><span class="sxs-lookup"><span data-stu-id="77471-192">Assign a Communications Credits license to one user</span></span>

<span data-ttu-id="77471-193">這些步驟與指派 Office 365 授權是一樣的。</span><span class="sxs-lookup"><span data-stu-id="77471-193">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="77471-194">請參閱[指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="77471-194">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="77471-195">大量指派通訊點數授權</span><span class="sxs-lookup"><span data-stu-id="77471-195">Assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="77471-196">請參閱指派音訊會議授權的範例腳本。</span><span class="sxs-lookup"><span data-stu-id="77471-196">Take a look at the sample script for assigning Audio Conferencing licenses.</span></span> <span data-ttu-id="77471-197">使用指派通訊點數授權的資訊來更新它。</span><span class="sxs-lookup"><span data-stu-id="77471-197">Update it with the info for assigning Communications Credits licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="77471-198">相關主題</span><span class="sxs-lookup"><span data-stu-id="77471-198">Related topics</span></span>

[<span data-ttu-id="77471-199">設定通話方案</span><span class="sxs-lookup"><span data-stu-id="77471-199">Set up Calling Plans</span></span>](set-up-calling-plans.md)
</br>
[<span data-ttu-id="77471-200">加值和管理通訊點數</span><span class="sxs-lookup"><span data-stu-id="77471-200">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)

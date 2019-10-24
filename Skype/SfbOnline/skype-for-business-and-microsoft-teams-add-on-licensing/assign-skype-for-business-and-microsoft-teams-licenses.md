---
title: 指派商務用 Skype 授權
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: '瞭解如何為手機系統、音訊會議、通話方案和通訊點數指派商務用 Skype 授權。 '
ms.openlocfilehash: 997cffce5b98ed992371a0f43e701b2efc1ae128
ms.sourcegitcommit: 6d5f09acdcdc8d5a36f7ac785349209e7496f17d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/07/2019
ms.locfileid: "37642249"
---
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="3761b-103">指派商務用 Skype 授權</span><span class="sxs-lookup"><span data-stu-id="3761b-103">Assign Skype for Business licenses</span></span>

<span data-ttu-id="3761b-104">本文提供有關指派授權給使用者的秘訣，例如音訊會議、電話系統和通話方案等功能。</span><span class="sxs-lookup"><span data-stu-id="3761b-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="3761b-105">它也提供大量指派授權的腳本。</span><span class="sxs-lookup"><span data-stu-id="3761b-105">It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3761b-106">請參閱[商務用 Skype 附加元件授權](skype-for-business-and-microsoft-teams-add-on-licensing.md)，以取得您需要購買哪些授權，以及**如何購買**它們（視您的 Office 365 方案而定），讓使用者取得音訊會議、免付費電話號碼，以及撥打電話號碼以外的功能您的公司。</span><span class="sxs-lookup"><span data-stu-id="3761b-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="3761b-107">電話系統與通話方案：指派授權的秘訣與腳本</span><span class="sxs-lookup"><span data-stu-id="3761b-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="3761b-108">指派音訊會議、電話系統和通話方案授權前需要注意的事項</span><span class="sxs-lookup"><span data-stu-id="3761b-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="3761b-109">**針對混合式使用者使用內部部署 PSTN 連線能力？**</span><span class="sxs-lookup"><span data-stu-id="3761b-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="3761b-110">如果是這樣，您只需要指派**電話系統**授權即可。</span><span class="sxs-lookup"><span data-stu-id="3761b-110">If so, you only need to assign a **Phone System** license.</span></span> <span data-ttu-id="3761b-111">您**不**應該指派通話方案。</span><span class="sxs-lookup"><span data-stu-id="3761b-111">You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="3761b-112">**指派授權之後的延遲**：由於 Office 365 與商務用 Skype Online 之間的延遲，在指派授權之後，可能需要長達24小時才能獲指派通話方案。</span><span class="sxs-lookup"><span data-stu-id="3761b-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="3761b-113">如果在24小時之後，使用者並未獲指派通話方案，請[與商務用支援人員聯繫，以取得系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="3761b-113">If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="3761b-114">**錯誤訊息**：如果您尚未購買正確數量的授權，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="3761b-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="3761b-115">如果您需要購買更多通話方案授權，請選擇 [**購買更多**]。</span><span class="sxs-lookup"><span data-stu-id="3761b-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="3761b-116">**後續步驟**：將通話方案授權指派給使用者之後，您將需要取得貴組織的電話號碼，然後將這些號碼指派給組織中的人員。</span><span class="sxs-lookup"><span data-stu-id="3761b-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="3761b-117">如需逐步指示，請參閱[設定通話方案](/microsoftteams/set-up-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="3761b-117">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="3761b-118">如何將電話系統和通話方案授權指派給一個使用者</span><span class="sxs-lookup"><span data-stu-id="3761b-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="3761b-119">這些步驟與指派 Office 365 授權是一樣的。</span><span class="sxs-lookup"><span data-stu-id="3761b-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="3761b-120">請參閱[指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="3761b-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="3761b-121">如何大量指派電話系統和通話方案授權</span><span class="sxs-lookup"><span data-stu-id="3761b-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="3761b-122">安裝**適用于 IT 專業人員的 Microsoft Online Services 登入**小幫手 RTW。</span><span class="sxs-lookup"><span data-stu-id="3761b-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="3761b-123">沒有安裝該模組嗎？</span><span class="sxs-lookup"><span data-stu-id="3761b-123">Don't have the module installed?</span></span> <span data-ttu-id="3761b-124">請參閱[適用于 IT 專業人員的 Microsoft Online Services 登入](https://go.microsoft.com/fwlink/?LinkId=625123)小幫手 RTW 以下載它。</span><span class="sxs-lookup"><span data-stu-id="3761b-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="3761b-125">安裝**Windows Azure Active Directory 模組。**</span><span class="sxs-lookup"><span data-stu-id="3761b-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="3761b-126">沒有安裝該模組嗎？</span><span class="sxs-lookup"><span data-stu-id="3761b-126">Don't have the module installed?</span></span> <span data-ttu-id="3761b-127">如需下載指示與 Cmdlet 語法，請參閱[使用 Windows PowerShell 管理 AZURE AD](https://go.microsoft.com/fwlink/p/?LinkId=320628) 。</span><span class="sxs-lookup"><span data-stu-id="3761b-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="3761b-128">安裝模組後，請使用 Windows PowerShell 命令提示字元及下列語法，將授權指派給您的使用者：</span><span class="sxs-lookup"><span data-stu-id="3761b-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="3761b-129">這個範例會指派**企業版 E3 授權**，以及**手機系統**和**國內通話方案**授權。</span><span class="sxs-lookup"><span data-stu-id="3761b-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="3761b-130">腳本中的授權或產品名稱的名稱會以斜體文字列出（請參閱在這個範例之後，請參閱**電話系統和通話方案產品名稱或 sku 用於腳本**）。</span><span class="sxs-lookup"><span data-stu-id="3761b-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="3761b-131">用於腳本的電話系統和通話方案產品名稱或 Sku</span><span class="sxs-lookup"><span data-stu-id="3761b-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="3761b-132">**產品名稱**</span><span class="sxs-lookup"><span data-stu-id="3761b-132">**Product name**</span></span>|<span data-ttu-id="3761b-133">**SKU 元件名稱**</span><span class="sxs-lookup"><span data-stu-id="3761b-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3761b-134">企業版 E5 （含電話系統）</span><span class="sxs-lookup"><span data-stu-id="3761b-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="3761b-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="3761b-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="3761b-136">企業版 E3</span><span class="sxs-lookup"><span data-stu-id="3761b-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="3761b-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="3761b-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="3761b-138">企業版 E1</span><span class="sxs-lookup"><span data-stu-id="3761b-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="3761b-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="3761b-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="3761b-140">商務用 Skype Online 獨立方案2</span><span class="sxs-lookup"><span data-stu-id="3761b-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="3761b-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="3761b-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="3761b-142">電話系統</span><span class="sxs-lookup"><span data-stu-id="3761b-142">Phone System</span></span>  <br/> |<span data-ttu-id="3761b-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="3761b-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="3761b-144">國際通話方案</span><span class="sxs-lookup"><span data-stu-id="3761b-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="3761b-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="3761b-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="3761b-146">國內通話方案（3000美元/1200 分歐盟方案）</span><span class="sxs-lookup"><span data-stu-id="3761b-146">Domestic Calling Plan (3000 min US / 1200 min EU plans)</span></span>  <br/> |<span data-ttu-id="3761b-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="3761b-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="3761b-148">國內通話方案（120最小通話方案）</span><span class="sxs-lookup"><span data-stu-id="3761b-148">Domestic Calling Plan (120 min calling plan)</span></span>  <br/> |<span data-ttu-id="3761b-149">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="3761b-149">MCOPSTN5</span></span>  <br/> |
|<span data-ttu-id="3761b-150">國內通話方案（240最小通話方案）</span><span class="sxs-lookup"><span data-stu-id="3761b-150">Domestic Calling Plan (240 min calling plan)</span></span>  <br/> |<span data-ttu-id="3761b-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="3761b-151">MCOPSTN6</span></span>  <br/> |
|<span data-ttu-id="3761b-152">通訊點數</span><span class="sxs-lookup"><span data-stu-id="3761b-152">Communications Credits</span></span>  <br/> |<span data-ttu-id="3761b-153">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="3761b-153">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="3761b-154">音訊會議：指派授權的秘訣與腳本</span><span class="sxs-lookup"><span data-stu-id="3761b-154">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="3761b-155">指派音訊會議授權前需要注意的事項</span><span class="sxs-lookup"><span data-stu-id="3761b-155">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="3761b-156">**協力廠商音訊會議提供者**：如果某人已設定為使用協力廠商音訊會議提供者，當您指派**音訊會議**授權時，系統會將其變更為使用 Microsoft 作為音訊會議服務.</span><span class="sxs-lookup"><span data-stu-id="3761b-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="3761b-157">您可以將它們變更回協力廠商提供者。</span><span class="sxs-lookup"><span data-stu-id="3761b-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="3761b-158">後續步驟：指派**音訊會議**授權之後，您需要指派音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="3761b-158">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="3761b-159">請參閱 [將 Microsoft 指派為音訊會議提供者]。</span><span class="sxs-lookup"><span data-stu-id="3761b-159">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="3761b-160">如何將音訊會議授權指派給一名使用者</span><span class="sxs-lookup"><span data-stu-id="3761b-160">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="3761b-161">這些步驟與指派 Office 365 授權是一樣的。</span><span class="sxs-lookup"><span data-stu-id="3761b-161">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="3761b-162">請參閱[指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="3761b-162">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="3761b-163">如何大量指派音訊會議授權</span><span class="sxs-lookup"><span data-stu-id="3761b-163">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="3761b-164">下載並安裝[適用于 IT 專業人員的 Microsoft Online Services 登入](https://go.microsoft.com/fwlink/?LinkId=625123)小幫手 RTW。</span><span class="sxs-lookup"><span data-stu-id="3761b-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="3761b-165">下載並安裝**Windows Azure Active Directory 模組。**</span><span class="sxs-lookup"><span data-stu-id="3761b-165">Download and install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="3761b-166">如需下載指示與 Cmdlet 語法，請參閱[使用 Windows PowerShell 管理 AZURE AD](https://go.microsoft.com/fwlink/p/?LinkId=320628) 。</span><span class="sxs-lookup"><span data-stu-id="3761b-166">See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="3761b-167">安裝模組後，請使用 Windows PowerShell 命令提示字元及下列語法，將授權指派給您的使用者：</span><span class="sxs-lookup"><span data-stu-id="3761b-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="3761b-168">腳本中授權或產品名稱的名稱會以斜體文字列出。</span><span class="sxs-lookup"><span data-stu-id="3761b-168">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="3761b-169">請參閱[音訊會議產品名稱或 sku，以供](assign-skype-for-business-and-microsoft-teams-licenses.md#sku)所有產品名稱的腳本使用。</span><span class="sxs-lookup"><span data-stu-id="3761b-169">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="3761b-170">這個範例會指派企業版 E3 授權以及音訊會議授權。</span><span class="sxs-lookup"><span data-stu-id="3761b-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="3761b-171">用於腳本的音訊會議產品名稱或 Sku</span><span class="sxs-lookup"><span data-stu-id="3761b-171">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="3761b-172"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="3761b-172"></span></span>

|<span data-ttu-id="3761b-173">**產品名稱**</span><span class="sxs-lookup"><span data-stu-id="3761b-173">**Product name**</span></span>|<span data-ttu-id="3761b-174">**SKU 元件名稱**</span><span class="sxs-lookup"><span data-stu-id="3761b-174">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3761b-175">音訊會議</span><span class="sxs-lookup"><span data-stu-id="3761b-175">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="3761b-176">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="3761b-176">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="3761b-177">商務用 Skype Online 獨立方案2</span><span class="sxs-lookup"><span data-stu-id="3761b-177">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="3761b-178">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="3761b-178">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="3761b-179">企業版 E1</span><span class="sxs-lookup"><span data-stu-id="3761b-179">Enterprise E1</span></span>  <br/> |<span data-ttu-id="3761b-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="3761b-180">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="3761b-181">企業版 E3</span><span class="sxs-lookup"><span data-stu-id="3761b-181">Enterprise E3</span></span>  <br/> |<span data-ttu-id="3761b-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="3761b-182">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="3761b-183">企業版 E5 （不含音訊會議）</span><span class="sxs-lookup"><span data-stu-id="3761b-183">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="3761b-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="3761b-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="3761b-185">企業版 E5 （含音訊會議）</span><span class="sxs-lookup"><span data-stu-id="3761b-185">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="3761b-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="3761b-186">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="3761b-187">通訊點數</span><span class="sxs-lookup"><span data-stu-id="3761b-187">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="3761b-188">指派通訊點數授權前需要注意的事項</span><span class="sxs-lookup"><span data-stu-id="3761b-188">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="3761b-189">**企業版 E5 客戶**：即使您的使用者已獲指派企業版 e5 授權，我們仍建議您指派其**通訊信用額度**授權。</span><span class="sxs-lookup"><span data-stu-id="3761b-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="3761b-190">**後續步驟**：在您指派這些授權之後，您必須取得貴組織的電話號碼，然後將這些號碼指派給貴組織中的人員。</span><span class="sxs-lookup"><span data-stu-id="3761b-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="3761b-191">如需逐步指示，請參閱[設定通話方案](/microsoftteams/set-up-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="3761b-191">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="3761b-192">如何指派通訊點數授權給一名使用者</span><span class="sxs-lookup"><span data-stu-id="3761b-192">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="3761b-193">這些步驟與指派 Office 365 授權是一樣的。</span><span class="sxs-lookup"><span data-stu-id="3761b-193">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="3761b-194">請參閱[指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="3761b-194">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="3761b-195">如何大量指派通訊點數授權</span><span class="sxs-lookup"><span data-stu-id="3761b-195">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="3761b-196">請參閱指派**音訊會議**授權的範例腳本。</span><span class="sxs-lookup"><span data-stu-id="3761b-196">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="3761b-197">使用指派**通訊點數**授權的資訊來更新它。</span><span class="sxs-lookup"><span data-stu-id="3761b-197">Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3761b-198">相關主題</span><span class="sxs-lookup"><span data-stu-id="3761b-198">Related topics</span></span>
  
[<span data-ttu-id="3761b-199">設定通話方案</span><span class="sxs-lookup"><span data-stu-id="3761b-199">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="3761b-200">新增基金及管理通訊點數</span><span class="sxs-lookup"><span data-stu-id="3761b-200">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 

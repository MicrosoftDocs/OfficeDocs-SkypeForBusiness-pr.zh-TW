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
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: '瞭解如何為 商務用 Skype、音訊電話系統、通話方案及通訊信用額度指派授權。 '
ms.openlocfilehash: 41f1788e4c562f3b4cc1f43d7875b64805b19ed8
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237489"
---
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="9f066-103">指派商務用 Skype 授權</span><span class="sxs-lookup"><span data-stu-id="9f066-103">Assign Skype for Business licenses</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="9f066-104">本文提供如何指派授權給使用者的秘訣，讓您使用音訊會議、電話系統和通話方案等功能。</span><span class="sxs-lookup"><span data-stu-id="9f066-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="9f066-105">它也提供大量指派授權腳本。</span><span class="sxs-lookup"><span data-stu-id="9f066-105">It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f066-106">請參閱[商務用 Skype](skype-for-business-and-microsoft-teams-add-on-licensing.md)附加元件授權，瞭解您需要購買哪些授權，以及如何購買授權 ，視您的 Microsoft 365 或 Office 365 方案而不同，讓使用者取得音訊會議、免付費號碼，以及撥打公司外電話號碼的能力。</span><span class="sxs-lookup"><span data-stu-id="9f066-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Microsoft 365 or Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="9f066-107">電話系統和通話方案：提示授權之使用者和腳本</span><span class="sxs-lookup"><span data-stu-id="9f066-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="9f066-108">指派音訊會議、電話系統通話方案授權之前，您需要知道什麼</span><span class="sxs-lookup"><span data-stu-id="9f066-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="9f066-109">**使用混合式使用者內部部署 PSTN 連接嗎？**</span><span class="sxs-lookup"><span data-stu-id="9f066-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="9f066-110">如果是這樣，您只需要指派 **授權電話系統授權**。</span><span class="sxs-lookup"><span data-stu-id="9f066-110">If so, you only need to assign a **Phone System** license.</span></span> <span data-ttu-id="9f066-111">您不應該 **指派** 通話方案。</span><span class="sxs-lookup"><span data-stu-id="9f066-111">You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="9f066-112">指派授權後的延遲：由於 Microsoft 365 或 Office 365 與 商務用 Skype Online 之間的延遲，指派授權後，使用者最多可能需要 24 小時才能獲得通話方案。</span><span class="sxs-lookup"><span data-stu-id="9f066-112">**Latency after assigning licenses**: Because of the latency between Microsoft 365 or Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="9f066-113">如果 24 小時後未指派使用者通話方案，請聯絡商務產品 [支援人員 - 系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="9f066-113">If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="9f066-114">**錯誤訊息**：如果您沒有購買正確的授權數量，就會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="9f066-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="9f066-115">如果您需要購買更多通話方案授權，請選擇 購買 **更多**。</span><span class="sxs-lookup"><span data-stu-id="9f066-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="9f066-116">**下一** 個步驟：將通話方案授權指派給使用者之後，您必須取得貴組織的電話號碼，然後將那些號碼指派給貴組織的人。</span><span class="sxs-lookup"><span data-stu-id="9f066-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="9f066-117">有關逐步指示，請參閱 [設定通話方案](/microsoftteams/set-up-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="9f066-117">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="9f066-118">如何將通話和電話系統方案授權指派給一位使用者</span><span class="sxs-lookup"><span data-stu-id="9f066-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="9f066-119">步驟與指派授權或授權Microsoft 365 Office 365相同。</span><span class="sxs-lookup"><span data-stu-id="9f066-119">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="9f066-120">請參閱[指派或移除商務Microsoft 365授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="9f066-120">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="9f066-121">如何大量指派電話系統通話方案授權</span><span class="sxs-lookup"><span data-stu-id="9f066-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="9f066-122">安裝 **MICROSOFT Online Services Sign-In IT 專業人員 RTW 小幫手**。</span><span class="sxs-lookup"><span data-stu-id="9f066-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="9f066-123">沒有安裝模組嗎？</span><span class="sxs-lookup"><span data-stu-id="9f066-123">Don't have the module installed?</span></span> <span data-ttu-id="9f066-124">請參閱 [Microsoft Online Services Sign-In IT 專業人員 RTW](https://go.microsoft.com/fwlink/?LinkId=625123) 小幫手來下載。</span><span class="sxs-lookup"><span data-stu-id="9f066-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="9f066-125">安裝 Windows Azure Active Directory **模組。**</span><span class="sxs-lookup"><span data-stu-id="9f066-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="9f066-126">沒有安裝模組嗎？</span><span class="sxs-lookup"><span data-stu-id="9f066-126">Don't have the module installed?</span></span> <span data-ttu-id="9f066-127">請參閱[使用工具管理 Azure AD Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100))下載指示和 Cmdlet 語法。</span><span class="sxs-lookup"><span data-stu-id="9f066-127">See [Manage Azure AD using Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="9f066-128">安裝模組之後，請使用 Windows PowerShell命令提示和下列語法來指派授權給使用者：</span><span class="sxs-lookup"><span data-stu-id="9f066-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="9f066-129">此範例會指派一Enterprise **E3** 授權，以及 **電話系統和** 國內通話 **方案** 授權。</span><span class="sxs-lookup"><span data-stu-id="9f066-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="9f066-130">腳本中的授權或產品名稱名稱會以斜體文字列出 (請參閱 電話系統 和用於腳本的通話方案產品名稱或 **SKUs**，在範例) 之後。</span><span class="sxs-lookup"><span data-stu-id="9f066-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="9f066-131">電話系統通話方案產品名稱或用於腳本的 SKUs</span><span class="sxs-lookup"><span data-stu-id="9f066-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="9f066-132">**產品名稱**</span><span class="sxs-lookup"><span data-stu-id="9f066-132">**Product name**</span></span>|<span data-ttu-id="9f066-133">**SKU 零件名稱**</span><span class="sxs-lookup"><span data-stu-id="9f066-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9f066-134">EnterpriseE5 (電話系統) </span><span class="sxs-lookup"><span data-stu-id="9f066-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="9f066-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="9f066-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="9f066-136">EnterpriseE3</span><span class="sxs-lookup"><span data-stu-id="9f066-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="9f066-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="9f066-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="9f066-138">EnterpriseE1</span><span class="sxs-lookup"><span data-stu-id="9f066-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="9f066-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="9f066-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="9f066-140">商務用 Skype線上獨立方案 2</span><span class="sxs-lookup"><span data-stu-id="9f066-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="9f066-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="9f066-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="9f066-142">電話系統</span><span class="sxs-lookup"><span data-stu-id="9f066-142">Phone System</span></span>  <br/> |<span data-ttu-id="9f066-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="9f066-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="9f066-144">國際通話方案</span><span class="sxs-lookup"><span data-stu-id="9f066-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="9f066-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="9f066-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="9f066-146">國內通話方案 (3000 分鐘美國 / 1200 分鐘的歐盟方案) </span><span class="sxs-lookup"><span data-stu-id="9f066-146">Domestic Calling Plan (3000 min US / 1200 min EU plans)</span></span>  <br/> |<span data-ttu-id="9f066-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="9f066-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="9f066-148">國內通話方案 (120 分鐘的通話方案) </span><span class="sxs-lookup"><span data-stu-id="9f066-148">Domestic Calling Plan (120 min calling plan)</span></span>  <br/> |<span data-ttu-id="9f066-149">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="9f066-149">MCOPSTN5</span></span>  <br/> |
|<span data-ttu-id="9f066-150">國內通話方案 (240 分鐘的通話方案) </span><span class="sxs-lookup"><span data-stu-id="9f066-150">Domestic Calling Plan (240 min calling plan)</span></span>  <br/> |<span data-ttu-id="9f066-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="9f066-151">MCOPSTN6</span></span>  <br/> |
|<span data-ttu-id="9f066-152">通訊點數</span><span class="sxs-lookup"><span data-stu-id="9f066-152">Communications Credits</span></span>  <br/> |<span data-ttu-id="9f066-153">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="9f066-153">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="9f066-154">音訊會議：提示指派授權和腳本</span><span class="sxs-lookup"><span data-stu-id="9f066-154">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="9f066-155">指派音訊會議授權之前，您需要知道什麼</span><span class="sxs-lookup"><span data-stu-id="9f066-155">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="9f066-156">協力廠商音訊會議提供者：如果有人已設定使用協力廠商音訊會議提供者，當您指派音訊會議授權給他們時，他們將會變更為使用 Microsoft 作為音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="9f066-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="9f066-157">您可以將它們變更回協力廠商提供者。</span><span class="sxs-lookup"><span data-stu-id="9f066-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="9f066-158">下一個步驟：指派 **音訊會議授權** 之後，您需要指派音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="9f066-158">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="9f066-159">請參閱 [將 Microsoft 指派為音訊會議提供者]。</span><span class="sxs-lookup"><span data-stu-id="9f066-159">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="9f066-160">如何將音訊會議授權指派給一個使用者</span><span class="sxs-lookup"><span data-stu-id="9f066-160">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="9f066-161">步驟與指派授權或授權Microsoft 365 Office 365相同。</span><span class="sxs-lookup"><span data-stu-id="9f066-161">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="9f066-162">請參閱[指派或移除商務Microsoft 365授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="9f066-162">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="9f066-163">如何大量指派音訊會議授權</span><span class="sxs-lookup"><span data-stu-id="9f066-163">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="9f066-164">下載並安裝 [Microsoft Online Services Sign-In IT 專業人員 RTW 小幫手](https://go.microsoft.com/fwlink/?LinkId=625123)。</span><span class="sxs-lookup"><span data-stu-id="9f066-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="9f066-165">下載並安裝 Windows Azure Active Directory **模組。**</span><span class="sxs-lookup"><span data-stu-id="9f066-165">Download and install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="9f066-166">請參閱[使用帳戶管理 Azure AD Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100))下載指示和 Cmdlet 語法。</span><span class="sxs-lookup"><span data-stu-id="9f066-166">See[Manage Azure AD using Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="9f066-167">安裝模組之後，請使用 Windows PowerShell命令提示和下列語法來指派授權給使用者：</span><span class="sxs-lookup"><span data-stu-id="9f066-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="9f066-168">腳本中的授權或產品名稱名稱會以斜體文字列出。</span><span class="sxs-lookup"><span data-stu-id="9f066-168">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="9f066-169">請參閱 [音訊會議產品名稱或用於](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) 所有產品名稱之腳本的 SKUs。</span><span class="sxs-lookup"><span data-stu-id="9f066-169">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="9f066-170">此範例會指派一Enterprise E3 授權，以及音訊會議授權。</span><span class="sxs-lookup"><span data-stu-id="9f066-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

    ```powershell
    #Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="9f066-171">音訊會議產品名稱或用於腳本的 SKUs</span><span class="sxs-lookup"><span data-stu-id="9f066-171">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="9f066-172"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="9f066-172"><a name="sku"> </a></span></span>

|<span data-ttu-id="9f066-173">**產品名稱**</span><span class="sxs-lookup"><span data-stu-id="9f066-173">**Product name**</span></span>|<span data-ttu-id="9f066-174">**SKU 零件名稱**</span><span class="sxs-lookup"><span data-stu-id="9f066-174">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9f066-175">音訊會議</span><span class="sxs-lookup"><span data-stu-id="9f066-175">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="9f066-176">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="9f066-176">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="9f066-177">商務用 Skype線上獨立方案 2</span><span class="sxs-lookup"><span data-stu-id="9f066-177">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="9f066-178">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="9f066-178">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="9f066-179">EnterpriseE1</span><span class="sxs-lookup"><span data-stu-id="9f066-179">Enterprise E1</span></span>  <br/> |<span data-ttu-id="9f066-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="9f066-180">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="9f066-181">EnterpriseE3</span><span class="sxs-lookup"><span data-stu-id="9f066-181">Enterprise E3</span></span>  <br/> |<span data-ttu-id="9f066-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="9f066-182">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="9f066-183">EnterpriseE5 (沒有音訊會議) </span><span class="sxs-lookup"><span data-stu-id="9f066-183">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="9f066-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="9f066-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="9f066-185">EnterpriseE5 (音訊會議) </span><span class="sxs-lookup"><span data-stu-id="9f066-185">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="9f066-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="9f066-186">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="9f066-187">通訊點數</span><span class="sxs-lookup"><span data-stu-id="9f066-187">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="9f066-188">指派通訊信用額度授權之前，您需要知道什麼</span><span class="sxs-lookup"><span data-stu-id="9f066-188">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="9f066-189">**Enterprise E5 客戶**：即使您的使用者Enterprise E5 授權，我們還是建議您指派通訊信用 **額度** 授權給他們。</span><span class="sxs-lookup"><span data-stu-id="9f066-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="9f066-190">**下一** 個步驟：指派這些授權之後，您必須取得貴組織的電話號碼，然後將這些號碼指派給貴組織的人。</span><span class="sxs-lookup"><span data-stu-id="9f066-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="9f066-191">有關逐步指示，請參閱 [設定通話方案](/microsoftteams/set-up-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="9f066-191">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="9f066-192">如何將通訊信用額度授權指派給一個使用者</span><span class="sxs-lookup"><span data-stu-id="9f066-192">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="9f066-193">步驟與指派授權或授權Microsoft 365 Office 365相同。</span><span class="sxs-lookup"><span data-stu-id="9f066-193">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="9f066-194">請參閱[指派或移除商務Microsoft 365授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="9f066-194">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="9f066-195">如何大量指派通訊信用額度授權</span><span class="sxs-lookup"><span data-stu-id="9f066-195">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="9f066-196">查看指派音訊會議授權範例 **腳本** 。</span><span class="sxs-lookup"><span data-stu-id="9f066-196">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="9f066-197">使用指派通訊信用額度授權的資訊 **進行更新** 。</span><span class="sxs-lookup"><span data-stu-id="9f066-197">Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9f066-198">相關主題</span><span class="sxs-lookup"><span data-stu-id="9f066-198">Related topics</span></span>
  
[<span data-ttu-id="9f066-199">設定通話方案</span><span class="sxs-lookup"><span data-stu-id="9f066-199">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="9f066-200">加值和管理通訊點數</span><span class="sxs-lookup"><span data-stu-id="9f066-200">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  

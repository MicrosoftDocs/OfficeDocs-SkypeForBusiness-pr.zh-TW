---
title: 將 Microsoft 指派為音訊會議提供者
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 瞭解如何指派 Microsoft 電話撥入式會議提供者商務用 Skype。
ms.openlocfilehash: 74469a7686855d1bb17627282a9f2e5378a0d59e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237759"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="fa0a6-103">將 Microsoft 指派為音訊會議提供者</span><span class="sxs-lookup"><span data-stu-id="fa0a6-103">Assign Microsoft as the audio conferencing provider</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="fa0a6-104">若要在 Microsoft 365 或 Office 365 使用音訊會議商務用 Skype Microsoft Teams，貴組織的使用者必須指派音訊會議授權給他們。</span><span class="sxs-lookup"><span data-stu-id="fa0a6-104">To use Audio Conferencing in Microsoft 365 or Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="fa0a6-105">請參閱[在 Microsoft 365](try-or-purchase-audio-conferencing-in-office-365.md)或 Office 365中試用或購買音訊會議，以取得授權和費用詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="fa0a6-105">See [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="fa0a6-106">Microsoft 音訊會議提供撥入電話號碼、PIN 和會議編號，會議參與者可以使用這些號碼加入貴組織的會議。</span><span class="sxs-lookup"><span data-stu-id="fa0a6-106">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="fa0a6-107">您只需要將 Microsoft 指派為音訊會議提供者給打算排程或帶領會議商務用 Skype或Microsoft Teams提供者。</span><span class="sxs-lookup"><span data-stu-id="fa0a6-107">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="fa0a6-108">將 Microsoft 指派為音訊會議提供者</span><span class="sxs-lookup"><span data-stu-id="fa0a6-108">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="an-icon-showing-the-skype-for-business-logo-using-the-skype-for-business-admin-center"></a>![顯示標誌圖示商務用 Skype圖示](../images/sfb-logo-30x30.png) <span data-ttu-id="fa0a6-110">使用 商務用 Skype系統管理中心</span><span class="sxs-lookup"><span data-stu-id="fa0a6-110">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="fa0a6-111">前往系統管理 **Microsoft Teams**  >  **舊版入口網站**。</span><span class="sxs-lookup"><span data-stu-id="fa0a6-111">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
2. <span data-ttu-id="fa0a6-112">在 商務用 Skype **系統管理中心**，在左側流覽中，前往 **音訊會議**。</span><span class="sxs-lookup"><span data-stu-id="fa0a6-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="fa0a6-113">如果您看到橫幅，通知您有使用者已指派音訊會議授權，但尚未將Microsoft 設定為其音訊會議提供者，請按一下 [按一下這裡以移動 **他們**。</span><span class="sxs-lookup"><span data-stu-id="fa0a6-113">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="fa0a6-114">如果您沒看到橫幅，請在系統管理中心商務用 Skype  [使用者」，然後選取[準備好要移至音訊會議 **篩選的使用者**。</span><span class="sxs-lookup"><span data-stu-id="fa0a6-114">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="fa0a6-115">在使用者的屬性頁面上，在提供者 **名稱** 下，選取下拉式清單中的 **Microsoft。**</span><span class="sxs-lookup"><span data-stu-id="fa0a6-115">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fa0a6-116">由於您使用的是 Microsoft 作為音訊會議提供者，而且有多個電話號碼，因此您可以使用預設付費號碼下拉式清單來選取使用者的預設音訊號碼。</span><span class="sxs-lookup"><span data-stu-id="fa0a6-116">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="fa0a6-117">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="fa0a6-117">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="fa0a6-118">為Windows PowerShell使用腳本</span><span class="sxs-lookup"><span data-stu-id="fa0a6-118">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="fa0a6-119">若要節省時間或自動化這項功能，您可以使用下列 PowerShell 腳本將 Microsoft 設定為少數使用者的音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="fa0a6-119">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="fa0a6-120">當提供者從另一個提供者變更為 **Microsoft** 時，系統將會 (會議 ID、付費和免付費號碼) 使用者的音訊會議資訊。</span><span class="sxs-lookup"><span data-stu-id="fa0a6-120">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="fa0a6-121">在變更提供者之前，您應該先儲存此資訊。</span><span class="sxs-lookup"><span data-stu-id="fa0a6-121">You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="fa0a6-122">若要針對少數使用者將提供者變更為 Microsoft，您可以使用  [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fa0a6-122">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="fa0a6-123">為Windows PowerShell使用腳本</span><span class="sxs-lookup"><span data-stu-id="fa0a6-123">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="fa0a6-124">若要節省時間或自動化這項功能，您可以使用下列 PowerShell 腳本將 Microsoft 設定為大量使用者的音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="fa0a6-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="fa0a6-125">當提供者從另一個提供者變更為 **Microsoft** 時，系統將會 (會議 ID、付費和免付費號碼) 使用者的音訊會議資訊。</span><span class="sxs-lookup"><span data-stu-id="fa0a6-125">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="fa0a6-126">在變更提供者之前，您應該先儲存此資訊。</span><span class="sxs-lookup"><span data-stu-id="fa0a6-126">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="fa0a6-127">您可以將下列腳本儲存為 PowerShell 腳本檔案，然後使用任何輸入參數執行。</span><span class="sxs-lookup"><span data-stu-id="fa0a6-127">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="fa0a6-128">**範例 1：** 您可以提供您想要更新的使用者清單，以執行此腳本。</span><span class="sxs-lookup"><span data-stu-id="fa0a6-128">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="fa0a6-129">**範例 2：** 您可以執行此腳本，.csv包含電子郵件地址 (別名) 每個使用者的別名。</span><span class="sxs-lookup"><span data-stu-id="fa0a6-129">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="fa0a6-130">**範例 3：** 在此範例中，您可以使用此腳本，將音訊會議提供者從 Intercall (或其他提供者) 組織中大量使用者變更為 **Microsoft。**</span><span class="sxs-lookup"><span data-stu-id="fa0a6-130">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```PowerShell
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="fa0a6-131">以下是腳本：</span><span class="sxs-lookup"><span data-stu-id="fa0a6-131">Here is the script:</span></span>

  ```PowerShell
  <#
  .SYNOPSIS

  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.

  .DESCRIPTION
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.

  .EXAMPLE
  
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ./Script.ps1 -ACPProviderName ""Intercall""
  #>
  param (
  [Parameter(Mandatory = $true, ParameterSetName = "CsvFile")]
   [string]$CsvFile,
   [Parameter(Mandatory = $true, ParameterSetName = "UserList")]
   [string]$UserList,
   [Parameter(Mandatory = $true, ParameterSetName = "ACPProviderName")]
  [string]$ACPProviderName
  )
  if ($CsvFile)
  {
  if(!(Test-Path $CsvFile))
  {
  Write-Error "File does not exist."
  Exit
   }
  $users = Get-Content $CsvFile
  }
  if ($UserList)
  {
  $users = $UserList.Split(",")
  }
  if ($ACPProviderName)
  {
  $supportedACPProviders = Get-csAudioConferencingProvider
  $providerNameMatch = $supportedACPProviders | ?{$_.Identity -eq $ACPProviderName}
  if ($providerNameMatch -eq $null)
  {
  Write-Host "The provider name is not from a supported provider, please use any of the following values: "
  $supportedACPProviders      | %{$_.Identity}
  return
  }
  $allUsersInTenant = Get-csOnlineUser
  $users =  $allUsersInTenant | ?{$_.AcpInfo -ne $null -and $_.ACPInfo.Name -eq $ACPProviderName}
  }
  Write-Host "Number of users to have their audio conferencing provider set to Microsoft: " $users.count
  foreach ($user in $users)
  {
  if ($CsvFile -or $UserList)
  {
  try
  {
  $adUser = Get-csOnlineUser -Identity $user
  }
  catch
  {
  Write-Error "There was an exception while retrieving user: $user. "   $error[0].Exception.Message
  Continue
  }
  }
  else
  {
  $adUser = $user
  }
  if ($adUser -ne $null -and ($adUser.OnlineDialInConferencingPOlicy -ne $null))
  {
  if ($adUser.AcpInfo -eq $null -Or $adUser.AcpInfo.Name -ne "Microsoft")
  {
  try
  {
  $enableUser = Enable-CsOnlineDialInConferencingUser -Identity $adUser.ObjectId -Tenant $adUser.TenantId -ReplaceProvider
  Write-Host "The provider of $user has changed to Microsoft."
  $enableUser
  }
  catch
  {
  Write-Error "There was an exception while enabling user: $user. "  $error[0].Exception.Message
  continue;
  }
  }
   else
  {
  Write-Warning "The provider of $user is already set to Microsoft."
  }
  }
  else
              {
  Write-Error "$user does not have valid Audio Conferencing license assigned."
  }
  }
  ```
<span data-ttu-id="fa0a6-132">若要進一Windows PowerShell，請參閱Windows PowerShell[線上管理工作商務用 Skype一般。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="fa0a6-132">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="fa0a6-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="fa0a6-133">Related topics</span></span>
<span data-ttu-id="fa0a6-134">[嘗試或購買音訊會議Microsoft 365或Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 
[設定 商務用 Skype Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="fa0a6-134">[Try or purchase Audio Conferencing in Microsoft 365 or Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span></span>

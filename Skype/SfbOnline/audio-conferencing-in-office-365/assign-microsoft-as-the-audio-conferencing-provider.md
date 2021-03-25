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
description: 瞭解如何將商務用 Skype 電話撥入式會議提供者指派給 Microsoft。
ms.openlocfilehash: b0276b0f5ed50e3c287bc872de45d6c1c4c69157
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110039"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="f2a26-103">將 Microsoft 指派為音訊會議提供者</span><span class="sxs-lookup"><span data-stu-id="f2a26-103">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="f2a26-104">若要在 Microsoft 365 或 Office 365 中使用音訊會議與商務用 Skype 和 Microsoft Teams，貴組織的使用者必須指派音訊會議授權給他們。</span><span class="sxs-lookup"><span data-stu-id="f2a26-104">To use Audio Conferencing in Microsoft 365 or Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="f2a26-105">請參閱 [在 Microsoft 365 或 Office 365](try-or-purchase-audio-conferencing-in-office-365.md) 中試用或購買音訊會議，以取得授權和費用詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f2a26-105">See [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="f2a26-106">Microsoft 音訊會議提供撥入式電話號碼、PIN 和會議編號，會議參與者可用來加入貴組織的會議。</span><span class="sxs-lookup"><span data-stu-id="f2a26-106">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="f2a26-107">您只需要將 Microsoft 指派為音訊會議提供者給打算排程或主導商務用 Skype 或 Microsoft Teams 會議的人員。</span><span class="sxs-lookup"><span data-stu-id="f2a26-107">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="f2a26-108">將 Microsoft 指派為音訊會議提供者</span><span class="sxs-lookup"><span data-stu-id="f2a26-108">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="an-icon-showing-the-skype-for-business-logo-using-the-skype-for-business-admin-center"></a>![顯示商務用 Skype 標誌的圖示](../images/sfb-logo-30x30.png) <span data-ttu-id="f2a26-110">使用商務用 Skype 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="f2a26-110">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="f2a26-111">請前往 **Microsoft Teams 系統管理中心**  >  **舊版入口網站**。</span><span class="sxs-lookup"><span data-stu-id="f2a26-111">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
2. <span data-ttu-id="f2a26-112">在商務 **用 Skype 系統管理中心** 左側的流覽中，前往 **音訊會議**。</span><span class="sxs-lookup"><span data-stu-id="f2a26-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="f2a26-113">如果您看到橫幅，通知您有使用者已指派音訊會議授權，但尚未將Microsoft 設定為其音訊會議提供者，請按一下 [按一下這裡以移動 **他們**。</span><span class="sxs-lookup"><span data-stu-id="f2a26-113">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="f2a26-114">如果您沒看到橫幅，請在商務用 **Skype** 系統管理中心按一下 [使用者，然後選取準備好要移至 **音訊會議篩選的使用者**。</span><span class="sxs-lookup"><span data-stu-id="f2a26-114">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="f2a26-115">在使用者的屬性頁面上，在提供者 **名稱** 下，選取下拉式清單中的 **Microsoft。**</span><span class="sxs-lookup"><span data-stu-id="f2a26-115">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f2a26-116">由於您使用的是 Microsoft 作為音訊會議提供者，而且有多個電話號碼，因此您可以使用預設付費號碼下拉式清單來選取使用者的預設音訊號碼。</span><span class="sxs-lookup"><span data-stu-id="f2a26-116">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="f2a26-117">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="f2a26-117">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="f2a26-118">為少數使用者使用 Windows PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="f2a26-118">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="f2a26-119">若要節省時間或自動化這項功能，您可以使用下列 PowerShell 腳本將 Microsoft 設定為少數使用者的音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="f2a26-119">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="f2a26-120">當提供者從另一個提供者變更為 **Microsoft** 時，系統將會 (會議 ID、付費和免付費號碼) 使用者的音訊會議資訊。</span><span class="sxs-lookup"><span data-stu-id="f2a26-120">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="f2a26-121">在變更提供者之前，您應該先儲存此資訊。</span><span class="sxs-lookup"><span data-stu-id="f2a26-121">You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="f2a26-122">若要針對少數使用者將提供者變更為 Microsoft，您可以使用  [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f2a26-122">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="f2a26-123">為大量使用者使用 Windows PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="f2a26-123">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="f2a26-124">若要節省時間或將這項功能自動化，您可以使用下列 PowerShell 腳本，將 Microsoft 設定為大量使用者的音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="f2a26-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="f2a26-125">當提供者從另一個提供者變更為 **Microsoft** 時，系統將會 (會議 ID、付費和免付費號碼) 使用者的音訊會議資訊。</span><span class="sxs-lookup"><span data-stu-id="f2a26-125">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="f2a26-126">在變更提供者之前，您應該先儲存此資訊。</span><span class="sxs-lookup"><span data-stu-id="f2a26-126">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="f2a26-127">您可以將下列腳本儲存為 PowerShell 腳本檔案，然後使用任何輸入參數執行。</span><span class="sxs-lookup"><span data-stu-id="f2a26-127">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="f2a26-128">**範例 1：** 您可以提供您想要更新的使用者清單，以執行此腳本。</span><span class="sxs-lookup"><span data-stu-id="f2a26-128">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="f2a26-129">**範例 2：** 您可以提供包含電子郵件地址的 .csv 檔案， () 更新每個使用者的別名，以執行此腳本。</span><span class="sxs-lookup"><span data-stu-id="f2a26-129">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="f2a26-130">**範例 3：** 在此範例中，您可以使用此腳本，將音訊會議提供者從 Intercall (或另一) 提供者變更為 **Microsoft，** 供貴組織中大量使用者使用。</span><span class="sxs-lookup"><span data-stu-id="f2a26-130">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```PowerShell
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="f2a26-131">以下是腳本：</span><span class="sxs-lookup"><span data-stu-id="f2a26-131">Here is the script:</span></span>

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
<span data-ttu-id="f2a26-132">有關使用 Windows PowerShell 的資訊，請參閱使用 [Windows PowerShell 執行常見的商務](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)用 Skype Online 管理工作。</span><span class="sxs-lookup"><span data-stu-id="f2a26-132">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f2a26-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="f2a26-133">Related topics</span></span>
<span data-ttu-id="f2a26-134">[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 
[設定商務用 Skype Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="f2a26-134">[Try or purchase Audio Conferencing in Microsoft 365 or Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span></span>
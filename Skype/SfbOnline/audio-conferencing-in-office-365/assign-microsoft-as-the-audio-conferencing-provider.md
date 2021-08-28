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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 瞭解如何指派 Microsoft 電話撥入式會議提供者商務用 Skype。
ms.openlocfilehash: 982d0515468109d1adf8ac2d7f00cce36732faf7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620299"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>將 Microsoft 指派為音訊會議提供者

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

若要在 Microsoft 365 或 Office 365 使用音訊會議商務用 Skype Microsoft Teams，貴組織的使用者必須指派音訊會議授權給他們。 請參閱[在 Microsoft 365](try-or-purchase-audio-conferencing-in-office-365.md)或 Office 365中試用或購買音訊會議，以取得授權和費用詳細資訊。

Microsoft 音訊會議提供撥入電話號碼、PIN 和會議編號，會議參與者可以使用這些號碼加入貴組織的會議。 您只需要將 Microsoft 指派為音訊會議提供者給打算排程或商務用 Skype或Microsoft Teams會議。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>將 Microsoft 指派為音訊會議提供者

### <a name="an-icon-showing-the-skype-for-business-logo-using-the-skype-for-business-admin-center"></a>![顯示標誌圖示商務用 Skype圖示](../images/sfb-logo-30x30.png) 使用 商務用 Skype系統管理中心

1. 前往系統管理 **Microsoft Teams**  >  **舊版入口網站**。
    
2. 在 商務用 Skype **系統管理中心**，在左側流覽中，前往 **音訊會議**。
    
3. 如果您看到橫幅，通知您有使用者已指派音訊會議授權，但尚未將Microsoft 設定為其音訊會議提供者，請按一下 [按一下這裡以移動 **他們**。 如果您沒看到橫幅，請在系統管理中心商務用 Skype  [使用者」，然後選取[準備好要移至音訊會議 **篩選的使用者**。
    
4. 在使用者的屬性頁面上，在提供者 **名稱** 下，選取下拉式清單中的 **Microsoft。**
    
    > [!NOTE]
    > 由於您使用的是 Microsoft 作為音訊會議提供者，而且有多個電話號碼，因此您可以使用預設付費號碼下拉式清單來選取使用者的預設音訊號碼。
  
5. 按一下 [儲存]。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>為Windows PowerShell使用腳本

若要節省時間或自動化這項功能，您可以使用下列 PowerShell 腳本，將 Microsoft 設定為少數使用者的音訊會議提供者。

> [!NOTE]
> 當提供者從另一個提供者變更為 **Microsoft** 時，系統將會 (會議 ID、付費和免付費號碼) 使用者的音訊會議資訊。 在變更提供者之前，您應該先儲存此資訊。 

  
若要針對少數使用者將提供者變更為 Microsoft，您可以使用  [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser) Cmdlet。
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>為Windows PowerShell使用腳本
若要節省時間或自動化這項功能，您可以使用下列 PowerShell 腳本將 Microsoft 設定為大量使用者的音訊會議提供者。

當提供者從另一個提供者變更為 **Microsoft** 時，系統將會 (會議 ID、付費和免付費號碼) 使用者的音訊會議資訊。 在變更提供者之前，您應該先儲存此資訊。 
  
您可以將下列腳本儲存為 PowerShell 腳本檔案，然後使用任何輸入參數執行。

**範例 1：** 您可以提供您想要更新的使用者清單，以執行此腳本。
   
  ```PowerShell
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

**範例 2：** 您可以執行此腳本，.csv包含電子郵件地址 (別名) 更新每個使用者的別名。
   
  ```PowerShell
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

**範例 3：** 在此範例中，您可以使用此腳本，將貴組織中大量使用者的音訊會議提供者從 Intercall (或其他) 變更為 **Microsoft。**
    
  ```PowerShell
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  以下是腳本：

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
若要進一Windows PowerShell，請參閱使用 Windows PowerShell[執行商務用 Skype管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
  
## <a name="related-topics"></a>相關主題
[嘗試或購買音訊會議Microsoft 365或Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 
[設定 商務用 Skype Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

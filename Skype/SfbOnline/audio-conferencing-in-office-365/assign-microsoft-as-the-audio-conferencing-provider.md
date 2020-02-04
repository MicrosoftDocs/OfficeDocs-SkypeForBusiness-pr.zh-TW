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
description: 瞭解如何將 Microsoft 電話撥入式會議提供者指派給商務用 Skype。
ms.openlocfilehash: f0c3d1d667847e080b47f31bb1032ff4b8ac980d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695758"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>將 Microsoft 指派為音訊會議提供者

若要在 Office 365 中搭配商務用 Skype 和 Microsoft 團隊使用音訊會議，貴組織中的使用者必須具備指派音訊會議授權。 請參閱[在 Office 365 中試用或購買音訊會議](try-or-purchase-audio-conferencing-in-office-365.md)，以取得授權及成本的詳細資訊。

Microsoft 音訊會議提供撥入式電話號碼、Pin 及會議 Id，可供會議參與者加入貴組織的會議。 您只需將 Microsoft 作為音訊會議提供者指派給要排程或引導商務用 Skype 或 Microsoft 團隊會議的人員。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>將 Microsoft 指派為音訊會議提供者

### <a name="an-icon-showing-the-skype-for-business-logoimagessfb-logo-30x30png-using-the-skype-for-business-admin-center"></a>![顯示商務用 Skype 標誌的圖示](../images/sfb-logo-30x30.png) 使用商務用 Skype 系統管理中心

1. 移至**Microsoft [團隊管理中心** > ] 的**舊版入口網站**。
    
2. 在**商務用 Skype 系統管理中心**的左導覽中，前往 [**音訊會議**]。
    
3. 如果您看到橫幅通知您有指派**音訊會議**授權的使用者，但尚未將 Microsoft 設定為其音訊會議提供者，請按一下 [**按一下這裡以進行移動**]。 如果您沒有看到橫幅，請在 [**商務用 Skype 系統管理中心**] 中按一下 [**使用者**]，然後選取 [**準備好要移至音訊會議的使用者**] 篩選。
    
4. 在使用者的 [屬性] 頁面的 [**提供者名稱**] 底下，選取下拉式清單中的 [ **Microsoft** ]。
    
    > [!NOTE]
    > 由於您是使用 Microsoft 作為音訊會議提供者，而且有多個電話號碼，因此您可以使用 [**預設收費號碼**] 下拉式清單來選取使用者的預設音訊號碼。
  
5. 按一下 [**儲存**]。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>針對少數幾個使用者使用 Windows PowerShell 腳本

若要節省時間或將這項作業自動化，您可以使用下列 PowerShell 腳本，為少數使用者將 Microsoft 設定為音訊會議提供者。

> [!NOTE]
> 當提供者從另一個提供者變更為**Microsoft**時，使用者的音訊會議資訊（會議 ID、付費和免付費電話號碼）將會被取代。 變更提供者前，您應該先儲存此資訊。 

  
若要針對少數使用者將提供者變更為 Microsoft，您可以使用[Enable-get-csonlinedialinconferencinguser](https://technet.microsoft.com/library/mt243813.aspx) Cmdlet。
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>針對大量使用者使用 Windows PowerShell 腳本
若要節省時間或將這項作業自動化，您可以使用下列 PowerShell 腳本，將 Microsoft 設定為大量使用者的音訊會議提供者。

當提供者從另一個提供者變更為**Microsoft**時，使用者的音訊會議資訊（會議 ID、付費和免付費電話號碼）將會被取代。 變更提供者前，您應該先儲存此資訊。 
  
您可以將下列腳本儲存為 PowerShell 腳本檔案，然後使用其任何輸入參數執行。

**範例1：** 您可以提供您想要更新的使用者清單，以執行此腳本。
   
  ```PowerShell
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

**範例2：** 您可以提供一個 .csv 檔案，其中包含您要更新之每個使用者的電子郵件地址（別名），以執行此腳本。
   
  ```PowerShell
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

**範例3：** 在這個範例中，您可以使用此腳本，將音訊會議提供者從 Intercall （或另一個提供者）變更為適用于貴組織中大量使用者的**Microsoft** 。
    
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
如需使用 Windows PowerShell 的詳細資訊，請參閱[使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)。
  
## <a name="related-topics"></a>相關主題
[在 Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
中試用或購買音訊會議[設定商務用 Skype Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)


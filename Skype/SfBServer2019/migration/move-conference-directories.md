---
title: 移動會議目錄
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 在解除委任集區之前，必須對舊版集區中的每個會議目錄執行下列程式。
ms.openlocfilehash: 5d4333f74c1d45e57e45c66c8de6f3e279cee01f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596147"
---
# <a name="move-conference-directories"></a>移動會議目錄

在解除委任集區之前，必須對舊版集區中的每個會議目錄執行下列程式。
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>將會議目錄移至商務用 Skype Server 2019

1. 開啟 [商務用 Skype Server 管理命令介面]。
    
2. 若要取得組織中會議目錄的身分識別，請執行下列命令：
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    上述命令會傳回組織中的所有會議目錄。 因此，您可能會想要將結果限制在解除委任的集區。 例如，如果您要將集區的完整功能變數名稱解除委任 (FQDN) pool01.contoso.net，請使用下列命令，將傳回的資料限制為該集區的會議目錄：
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    該命令只會傳回 ServiceID 屬性包含 FQDN pool01.contoso.net 的會議目錄。
    
3. 若要移動會議目錄，請針對集區中的每個會議目錄執行下列命令：
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    例如，若要移動會議目錄3，請使用此命令，指定商務用 Skype Server 2019 集區做為 microsoft.rtc.management.writableconfig.settings.watchernode.targetpool：
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    如果您想要移動集區上的所有會議目錄，請使用類似下列的命令：
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

針對解除委任舊版集區的逐步指示，下載 [卸載 Microsoft 舊版及移除伺服器角色](https://go.microsoft.com/fwlink/p/?linkId=246227) 。
  
移動會議目錄時，您可能會遇到下列錯誤：
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

當商務用 Skype Server 管理命令介面需要一組已更新的 Active Directory 許可權，才能完成工作時，通常會發生此錯誤。 若要解決此問題，請關閉目前的管理命令介面實例，然後開啟命令介面的新實例，然後重新執行命令以移動會議目錄。
  


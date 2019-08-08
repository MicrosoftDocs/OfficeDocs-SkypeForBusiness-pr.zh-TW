---
title: 移動會議目錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在解除池的授權前, 您必須針對舊版池中的每個會議目錄執行下列程式。
ms.openlocfilehash: cc989e752e69db31f338b493c403b8b8d4c252cc
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238080"
---
# <a name="move-conference-directories"></a>移動會議目錄

在解除池的授權前, 您必須針對舊版池中的每個會議目錄執行下列程式。
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>將會議目錄移至商務用 Skype Server 2019

1. 開啟商務用 Skype Server 管理命令介面。
    
2. 若要取得貴組織中會議目錄的身分識別, 請執行下列命令:
    
   ```
   Get-CsConferenceDirectory
   ```

    上述命令會傳回貴組織中的所有會議目錄。 因此, 您可能會想要將結果限制在已解除授權的池中。 例如, 如果您是使用完整的功能變數名稱 (FQDN) pool01.contoso.net 來解除池, 請使用此命令, 將傳回的資料限制在該池中的會議目錄:
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    該命令只會傳回 ServiceID 屬性包含 FQDN pool01.contoso.net 的會議目錄。
    
3. 若要移動會議目錄, 請針對池中的每個會議目錄執行下列命令:
    
   ```
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    例如, 若要移動會議目錄 3, 請使用此命令, 將商務用 Skype Server 2019 池指定為 TargetPool:
    
   ```
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    如果您想要移動一個池上的所有會議目錄, 請使用類似下列的命令:
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

下載[Microsoft 舊版並移除伺服器角色](https://go.microsoft.com/fwlink/p/?linkId=246227), 以取得有關解除授權舊版池的完整逐步指示。
  
移動會議目錄時, 您可能會遇到下列錯誤:
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

如果商務用 Skype 伺服器管理命令介面需要更新的 Active Directory 許可權集才能完成工作, 通常會發生此錯誤。 若要解決此問題, 請關閉目前的管理命令介面實例, 然後開啟一個新的 Shell 實例, 然後重新執行該命令來移動會議目錄。
  


---
title: 診斷商務用 Skype Online 連接器的連線問題
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 疑難排解如何建立遠端 PowerShell 會話以連線至 商務用 Skype Online，包括 Import-Module、並行 shell、Live ID 和許可權錯誤。
ms.openlocfilehash: 9635d2a4ff8ecf17fd9d1bb4717fad98a9795292
ms.sourcegitcommit: 9fcd9a7ae78e04cef90415c2a0f30a98fbf8270f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/19/2021
ms.locfileid: "58407192"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>診斷商務用 Skype Online 連接器的連線問題

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本主題提供可協助診斷及解決當您嘗試建立連線至線上的遠端 Microsoft PowerShell 會話時商務用 Skype的資訊。 請參閱下列各節：
  
- [由於執行策略Windows PowerShell模組錯誤](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [錯誤版本錯誤所造成的 Import-module 錯誤Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [當 WinRM 基本驗證已停用時，新式驗證失敗](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [無法連接到 Live ID Server](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [載入 Live ID 模組失敗](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [使用者無法進行登錄](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [使用者沒有管理此租使用者的許可權](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [連線至租使用者的能力已在 商務用 Skype 中停用](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [已超出此使用者在 商務用 Skype 命令的上限](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [已超出此租使用者在 商務用 Skype 命令命令的並行命令數目上限](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> 根據預設，PowerShell 會話在六十分鐘後會結束。 若要重新連接，您必須關閉會話並啟動新的 PowerShell 會話。 新版 [商務用 Skype Online、Windows PowerShell 模組 (2046.123 - 已發佈 10/2/2019) 最近](https://www.microsoft.com/download/details.aspx?id=39366)推出，其中包含名為 **Enable-CsOnlineSessionForReconnection** 的新 Cmdlet，可減輕 60 分鐘的時空問題。
> PowerShell 會話會重新連接和驗證，以便重新使用，而不需要啟動新實例重新連接。



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Import-Module執行Windows PowerShell錯誤
<a name="BKMKPowerShellExecutionPolicy"> </a>

PowerShell 執行策略可協助判斷哪些組組檔案可以載入至 PowerShell 主控台，以及使用者可以從該主控台執行哪些腳本。 除非執行策略設定為 RemoteSigned，否則至少無法商務用 Skype線上連接器模組。 如果沒有，則當您嘗試輸入模組時，會收到下列錯誤訊息：
  
- 錯誤：Import-Module：檔案 C：無法載入程式檔案一般檔案<em>Microsoft Lync Server \\ \\ \\ 2013 \\ 模組 \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1，因為系統已停用執行中的腳本。詳細資訊，請參閱 在 https://go.microsoft.com/fwlink/?LinkID=135170 about_Execution_Policies。</em>

- **解析度** 若要解決此問題，請以系統管理員角色啟動 PowerShell，然後執行下列命令：
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    有關執行策略的詳細資訊，請參閱 [關於執行策略](/powershell/module/microsoft.powershell.core/about/about_execution_policies)。
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Import-Module錯誤由不正確的版本Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

商務用 Skype線上連接器模組只能在 3.0 Windows PowerShell下執行。 如果您嘗試在先前版本的 PowerShell 下輸入模組，則導入程式將會失敗，而錯誤訊息與以下訊息類似：
  
  - **錯誤***：Import-Module：載入的 PowerShell 版本為 '2.0'。模組 'D：程式檔案共同檔案 \\ \\ Microsoft Lync Server \\ 2013 \\ 模組 \\ LyncOnlineConnector \\LyncOnlineConnector.psd1' 需要執行的最低 PowerShell 版本為 '3.0' 。請確認 PowerShell 的安裝，然後再試一次。*

- **解決方法**：修正此問題的唯一方法，是安裝 3.0 Windows PowerShell 3.0，可從 Microsoft 下載中心在 [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) .
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>當 WinRM 基本驗證已停用時，新式驗證失敗
<a name="BKMKWinRMBasicAuth"> </a>

最新版本的 商務用 Skype Online Connector 模組使用新式驗證，但基礎 Windows 遠端系統管理 (WinRM) 用戶端必須配置為允許基本驗證。  新式驗證使用記名權杖，通常是在授權 *：Bearer 標頭中* 傳遞。 Windows PowerShell PowerShell 商務用 Skype建立之後，不允許操作此頁標題。  PowerShell 商務用 Skype使用 *授權：基本* 頁首來傳遞承載權杖。

請參閱[下載並安裝Windows PowerShell，](./download-and-install-windows-powershell-5-1.md)以取得如何啟用 WinRM for Basic 驗證的指示。

## <a name="failed-to-connect-to-live-id-server"></a>無法連接到 Live ID Server
<a name="BKMKFailedConnect"> </a>

> [!WARNING] 
> 商務用線上連接器已Skype即時識別碼驗證。 使用 powerShell Teams模組來管理線上租使用者。 管理混合式環境時，請升級至最新的累積更新或使用 oAuth 驗證。

您的連接嘗試失敗的原因通常有三種，原因如下：

  - **錯誤***：Get-CsWebTicket：無法連接即時識別碼伺服器。請確定 Proxy 已啟用，或電腦已與即時識別碼伺服器建立網路連接。*

- **解決** 方式：此錯誤通常表示 Microsoft Online Services 登入小幫手並未運作。 您可以從 PowerShell 提示執行下列命令，以驗證此服務的狀態： 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    如果服務未執行，請用此命令啟動服務：
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    如果服務執行中，您可能會遇到電腦與 Microsoft Live ID 驗證服務器之間的網路連接問題。 若要檢查這項功能，請開啟 Internet Explorer 並流覽至[ https://login.microsoftonline.com/ 。](https://login.microsoftonline.com/.) 請嘗試從Microsoft 365登Office 365或登Office 365登陸。 如果失敗，您可能遇到網路連接問題。
  
    較不常見的是，可能是 Microsoft Live ID 驗證服務器的連接 URI 已配置為錯誤的值。 如果您已經判斷系統Sign-In小幫手，而且您沒有遇到網路連接問題，這可能是問題。 在這種情況下，請聯絡 Microsoft 支援服務。
  
## <a name="failed-to-load-live-id-module"></a>載入 Live ID 模組失敗
<a name="BKMKFailedLoad"> </a>

使用 PowerShell 管理線上商務用 Skype其中一個先決條件是安裝 Microsoft Online Services 登入小幫手。 如果尚未安裝登錄小幫手，當您嘗試在線上建立遠端會話時，您會收到商務用 Skype訊息：

- **錯誤***：Get-CsWebTicket：無法載入 Live ID 模組。確認已安裝正確版本的 Live Id 登錄小幫手。*

- **解決** 方式：Microsoft Online Services 登入小幫手可在 Microsoft Online Services 的 Microsoft 下載中心Sign-In [IT 專業人員 RTW](https://www.microsoft.com/download/details.aspx?id=28177)小幫手

## <a name="logon-failed-for-the-user"></a>使用者登入失敗
<a name="BKMKLogonFailed"> </a>

當您嘗試進行遠端連線至 商務用 Skype線上時，您必須提供有效的線上使用者帳戶商務用 Skype使用者名稱和密碼。 如果沒有，登入會失敗，以及類似此訊息的錯誤訊息：

- **錯誤***：Get-CsWebTicket：登入失敗的使用者'kenmyer@litwareinc.com'。建立新的 PSCredential 物件，確定您所使用的使用者名稱和密碼正確無誤。*

- **解決方法**：如果您認為您使用的是有效的使用者帳戶，而且您擁有正確的密碼，請再次嘗試登陸。 如果失敗，請使用相同的認證，並嘗試在 中登錄 [https://login.microsoftonline.com/](https://login.microsoftonline.com/) 。 如果您無法在那裡登錄，請聯絡 Microsoft 支援服務。 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>使用者沒有管理此租使用者的許可權
<a name="BKMKUserPermission"> </a>

除非您是租使用者系統管理員群組的成員，否則您無法與商務用Skype Online 進行遠端 PowerShell 連線。 如果沒有，您的連接嘗試將會失敗，而且您會收到下列錯誤訊息：

- 錯誤：New-PSSession：[admin.vdomain.com] 從遠端伺服器 admin.vdomain.com 處理資料失敗，出現下列錯誤訊息：使用者 'user@foo.com' 沒有管理此租使用者的許可權 *。您可以將使用者指派給適當的 RBAC 角色，以授予許可權。詳細資訊，請參閱遠端 [疑難排解](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )。*

- **解決方法**：如果您認為自己是或應該是租使用者系統管理員群組的成員，您必須與 Microsoft 支援服務聯繫。
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>連線至租使用者的能力已在 商務用 Skype Online 中停用
<a name="BKMKAbilityConnect"> </a>

若要使用 PowerShell 商務用 Skype Online，您租使用者 PowerShell 策略的 EnableRemotePowerShellAccess 屬性必須設為 `True` 。 如果沒有，您的連接將會失敗，而且您會收到下列錯誤訊息：

- 錯誤：New-PSSession：[admin.vdomain.com] 從遠端伺服器 admin.vdomain.com 處理資料失敗，出現下列錯誤訊息：已停用使用遠端 PowerShell 會話連接到此租使用者的能力 *。請聯絡 Lync 協助以檢查此租使用者的租使用者 Powershell 政策。詳細資訊，請參閱遠端 [疑難排解](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )。*

- **解決方法**：如果您看到此錯誤訊息，您必須與 Microsoft 支援服務聯繫，並啟用遠端 PowerShell 存取。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>已超出此使用者在 商務用 Skype 命令的上限
<a name="BKMKMaxNumberShellsUser"> </a>

每個系統管理員最多可同時使用三個遠端連線商務用 Skype Online。 如果您有三個遠端 PowerShell 連接已啟動並執行，任何嘗試進行第四次同時連接都會失敗，並出現下列錯誤訊息： 

- **錯誤***：New-PSSession：[admin.vdomain.com] 無法連接到遠端伺服器 admin.vdomain.com 出現下列錯誤訊息：WS-Management服務無法處理要求。已超過此使用者並行命令命令的上限。關閉現有的 shell 或提高此使用者的配額。詳細資訊，請參閱遠端 [疑難排解](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )。*

- **解決方法**：解決此問題的唯一方法就是關閉一或多個先前的連接。 當您完成線上商務用 Skype時，建議您使用 **Remove-PSSession** Cmdlet 來終止會話。 這可協助避免此問題。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>已超出此租使用者在 商務用 Skype 命令命令的並行命令數目上限
<a name="BKMKMaxNumberShellsTenant"> </a>

雖然每個系統管理員可同時與 商務用 Skype 租使用者建立三個連線，但不允許單一租使用者同時連線超過 20 個。 例如，六個系統管理員可能各自有三個開啟的會話。 如果第四個系統管理員嘗試建立超過兩個 (導致總共 21 個同時) ，此嘗試將會失敗，並出現下列錯誤訊息：
  
- **錯誤***：New-PSSession：[admin.vdomain.com] 無法連接到遠端伺服器 admin.vdomain.com 出現下列錯誤訊息：WS-Management服務無法處理要求。已超出此租使用者並行命令命令的上限。關閉現有的 shell 或提高此租使用者的配額。詳細資訊，請參閱遠端 [疑難排解](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )。*

- **解決方法**：解決此問題的唯一方法就是關閉一或多個先前的連接。 當您完成線上商務用 Skype時，建議您使用 **Remove-PSSession** Cmdlet 來終止該會話。 這可協助避免此問題。  
 
## <a name="related-topics"></a>相關主題
[使用電腦設定商務用 skype 線上管理Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  

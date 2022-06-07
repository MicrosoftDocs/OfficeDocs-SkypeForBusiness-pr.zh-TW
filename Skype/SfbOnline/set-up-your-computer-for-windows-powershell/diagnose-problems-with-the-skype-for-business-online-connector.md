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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 疑難排解建立可連線到商務用 Skype Online 的遠端 PowerShell 會話，包括匯入模組、並行殼層、即時識別碼和許可權錯誤。
ms.openlocfilehash: c2092da0324a147b182ce7715e757f1ed039aa65
ms.sourcegitcommit: 1ac37cc27d4ccb3e1dae20ca1929214e17be2075
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/07/2022
ms.locfileid: "65913391"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>診斷商務用 Skype Online 連接器的連線問題

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本主題提供的資訊可協助您診斷並解決當您嘗試建立連線到商務用 Skype Online 的遠端 Microsoft PowerShell 會話時可能會發生的問題。 請參閱下列各節：
  
- [由 Windows PowerShell 執行原則造成的匯入模組錯誤](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [因 Windows PowerShell 版本不正確而造成的匯入模組錯誤](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [停用 WinRM 基本驗證時，新式驗證失敗](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [無法連線到 Live ID Server](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
      
- [使用者登入失敗](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [使用者沒有管理此租使用者的許可權](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [商務用 Skype Online 已停用連線到租使用者的功能](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [已超出商務用 Skype Online 中此使用者的並行殼層數上限](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [在商務用 Skype Online 中，此租使用者的並行殼層數目已超過上限](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>windows PowerShell 執行原則Import-Module錯誤
<a name="BKMKPowerShellExecutionPolicy"> </a>

PowerShell 執行原則可協助判斷哪些組態檔可以載入 PowerShell 主機，以及使用者可以從該主機執行哪些腳本。 除非執行原則設定為 RemoteSigned，否則您至少無法匯入商務用 Skype Online Connector 模組。 如果沒有，當您嘗試匯入模組時，您會收到下列錯誤訊息：
  
- **錯誤**：<em>匯入模組：檔案 C： \\ 程式檔案通用檔案 \\ \\ Microsoft Lync Server 2013 \\ 模組 \\ LyncOnlineConnector LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1 無法載入，因為此系統停用執行中的腳本。如需詳細資訊，請參閱about_Execution_Policies。 https://go.microsoft.com/fwlink/?LinkID=135170</em>

- **解析度** 若要解決此問題，請以系統管理員身分啟動 PowerShell，然後執行下列命令：
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    如需執行原則的詳細資訊，請參閱 [關於執行原則](/powershell/module/microsoft.powershell.core/about/about_execution_policies)。
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Import-Module錯誤
<a name="BKMKIncorrectVersion"> </a>

商務用 Skype Online 連接器模組只能在 Windows PowerShell 3.0 下執行。 如果您嘗試在舊版 PowerShell 下方匯入模組，匯入程式將會失敗，並出現類似此訊息的錯誤訊息：
  
  - **錯誤**： *匯入模組：載入的 PowerShell 版本為 '2.0'。「D： \\ 程式檔案通用檔案 \\ \\ Microsoft Lync Server 2013 \\ 模組 \\ LyncOnlineConnector LyncOnlineConnector \\ LyncOnlineConnector.psd1」模組需要執行最低 PowerShell 版本的 '3.0' 才能執行。請驗證 PowerShell 的安裝，然後再試一次。*

- **解決** 方式：修正此問題的唯一方法是安裝 Windows PowerShell 3.0，此版本可從 Microsoft 下載中心 [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) 取得。
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>停用 WinRM 基本驗證時，新式驗證失敗
<a name="BKMKWinRMBasicAuth"> </a>

最新版的商務用 Skype Online 連接器模組使用新式驗證，但必須設定基礎 Windows 遠端系統管理 (WinRM) 用戶端，才能允許基本驗證。  新式驗證使用記事權杖，通常會在 *授權：Bearer 標* 頭中傳遞。 建置商務用 Skype PowerShell 的 Windows PowerShell 不允許操作此頁首。  相反地，商務用 Skype PowerShell 會使用 *「授權：基本* 」標頭來傳遞持有者權杖。

如需如何啟用 WinRM for Basic 驗證的指示，請參閱 [下載並安裝 Windows PowerShell](./download-and-install-windows-powershell-5-1.md) 。

## <a name="failed-to-connect-to-live-id-server"></a>無法連線到 Live ID Server
<a name="BKMKFailedConnect"> </a>

> [!WARNING] 
> 商務用 Skype Online Connector 的 Live ID 驗證已遭取代。 使用 Teams PowerShell 模組來管理線上租使用者。 管理混合式環境時，請升級至最新的累積更新或使用 oAuth 驗證。

連線嘗試失敗的原因通常有下列三個原因：

  - **錯誤**： *Get-CsWebTicket：無法連線即時識別碼伺服器。確定 Proxy 已啟用，或電腦有網路連線到即時識別碼伺服器。*

- **解決方式**：此錯誤通常表示 Microsoft Online Services 登入小幫手並未執行。 您可以從 PowerShell 提示字元中執行下列命令，以確認此服務的狀態： 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    如果服務未執行，請使用下列命令啟動服務：
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    如果服務正在執行，您可能會遇到電腦與 Microsoft Live ID Authentication Server 之間的網路連線問題。 若要檢查此專案，請開啟 Internet Explorer 並流覽至[ https://login.microsoftonline.com/ 。](https://login.microsoftonline.com/.) 嘗試從該處登入 Microsoft 365 或 Office 365。 如果失敗，您可能遇到網路連線問題。
  
    較不常見的情況是，Microsoft Live ID Authentication Server 的連線 URI 已設定為錯誤的值。 如果您已經確定Sign-In小幫手正在執行，而且您沒有遇到網路連線問題，這可能是問題。 在此情況下，請連絡 Microsoft 支援服務。
  
## <a name="logon-failed-for-the-user"></a>使用者登入失敗
<a name="BKMKLogonFailed"> </a>

當您嘗試遠端連線到商務用 Skype Online 時，必須提供有效商務用 Skype Online 使用者帳戶的使用者名稱和密碼。 若未登入，登入會失敗，並出現類似此訊息的錯誤訊息：

- **錯誤**： *Get-CsWebTicket：登入失敗，表示使用者「kenmyer@litwareinc.com」。建立新的 PSCredential 物件，確定您已使用正確的使用者名稱和密碼。*

- **解決方式**：如果您認為使用的是有效的使用者帳戶，而且您擁有正確的密碼，請嘗試再次登入。 如果失敗，請使用相同的認證，並嘗試在 登入 [https://login.microsoftonline.com/](https://login.microsoftonline.com/) 。 如果您無法登入，請連絡 Microsoft 支援服務。 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>使用者沒有管理此租使用者的許可權
<a name="BKMKUserPermission"> </a>

您無法與商務用 Skype Online 進行遠端 PowerShell 連線，除非您是租使用者系統管理員群組的成員。 如果沒有，連線嘗試將會失敗，而且您會收到下列錯誤訊息：

- **錯誤**： *New-PSSession ： [admin.vdomain.com] 處理來自遠端伺服器 admin.vdomain.com 的資料失敗，並出現下列錯誤訊息：使用者'user@foo.com'沒有管理此租使用者的許可權。您可以將使用者指派給適當的 RBAC 角色，藉此授與許可權。如需詳細資訊，請參閱 [遠端疑難排解](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )。*

- **解決方式**：如果您認為您是或應該是租使用者系統管理員群組的成員，您必須連絡 Microsoft 支援服務。
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>商務用 Skype Online 已停用連線到租使用者的功能
<a name="BKMKAbilityConnect"> </a>

若要使用 PowerShell 管理商務用 Skype Online，您租使用者 PowerShell 原則的 EnableRemotePowerShellAccess 屬性必須設為  `True` 。 如果不是，您的連線將會失敗，而且您會收到下列錯誤訊息：

- **錯誤**： *New-PSSession ： [admin.vdomain.com] 處理來自遠端伺服器 admin.vdomain.com 的資料失敗，並出現下列錯誤訊息：已停用使用遠端 PowerShell 會話連線到此租使用者的功能。請連絡 Lync 說明以檢查此租使用者的租使用者 PowerShell 原則。如需詳細資訊，請參閱 [遠端疑難排解](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )。*

- **解決方式**：如果您看到此錯誤訊息，您必須連絡 Microsoft 支援服務，並啟用遠端 PowerShell 存取。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>已超出商務用 Skype Online 中此使用者的並行殼層數上限
<a name="BKMKMaxNumberShellsUser"> </a>

每位系統管理員最多可以同時三次遠端連線到商務用 Skype Online。 如果您已啟動並執行三個遠端 PowerShell 連線，任何同時進行第四個連線的嘗試都會失敗，並出現下列錯誤訊息： 

- **錯誤**： *New-PSSession ： [admin.vdomain.com] 連線到遠端伺服器 admin.vdomain.com 失敗，出現下列錯誤訊息：WS-Management服務無法處理要求。已超過此使用者的並行殼層數上限。關閉現有的殼層或提高此使用者的配額。如需詳細資訊，請參閱 [遠端疑難排解](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )。*

- **解決** 方式：解決此問題的唯一方法是關閉一或多個先前的連線。 當您完成商務用 Skype Online 會話時，建議您使用 **Remove-PSSession** Cmdlet 來終止會話。 這可協助您避免此問題。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>在商務用 Skype Online 中，此租使用者的並行殼層數目已超過上限
<a name="BKMKMaxNumberShellsTenant"> </a>

雖然每個系統管理員可以同時擁有多達三個同時連線到商務用 Skype Online 租使用者，但不允許單一租使用者同時擁有 20 個以上的同時連線。 例如，六位系統管理員可能各自有三個開啟的會話。 如果第四個系統管理員嘗試進行兩個以上的連線 (導致共 21 個同時連線) ，此嘗試將會失敗，並出現下列錯誤訊息：
  
- **錯誤**： *New-PSSession ： [admin.vdomain.com] 連線到遠端伺服器 admin.vdomain.com 失敗，出現下列錯誤訊息：WS-Management服務無法處理要求。已超出此租使用者的並行殼層數目上限。關閉現有的殼層或提高此租使用者的配額。如需詳細資訊，請參閱 [遠端疑難排解](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )。*

- **解決** 方式：解決此問題的唯一方法是關閉一或多個先前的連線。 當您完成商務用 Skype Online 會話時，建議您使用 **Remove-PSSession** Cmdlet 來終止該會話。 這可協助您避免此問題。  
 
## <a name="related-topics"></a>相關主題
[使用 Windows PowerShell 設定商務用 Skype 線上管理電腦](set-up-your-computer-for-windows-powershell.md)

  

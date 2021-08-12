---
title: 使用線上連接器診斷連線商務用 Skype問題
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
description: 疑難排解如何建立遠端 PowerShell 會話以連線至 商務用 Skype Online，包括 Import-Module、並行 shell、Live ID 和許可權問題。
ms.openlocfilehash: cb9268efc5e35ec5f25ed93314a77347b4a9363f038744c4de9a934528ae371f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295950"
---
# <a name="diagnose-connection-problems-using-skype-for-business-online-connector"></a>使用線上連接器診斷連線商務用 Skype問題

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本主題提供可協助診斷及解決當您嘗試建立連線至線上的遠端 Microsoft PowerShell 會話時商務用 Skype的資訊。 請參閱下列各節：
  
- [由於執行策略Windows PowerShell模組錯誤](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [錯誤版本錯誤所造成的 Import-module 錯誤Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [無法連接到 Live ID Server](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [載入 Live ID 模組失敗](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [使用者登入失敗](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [使用者沒有管理此租使用者的許可權](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [連線至租使用者的能力已在 商務用 Skype Online 中停用](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)

- [已超出此使用者在 商務用 Skype 命令命令的並行命令數目上限](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [已超出此租使用者在 商務用 Skype 的並行命令命令數目上限](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Import-Module執行Windows PowerShell錯誤
<a name="BKMKPowerShellExecutionPolicy"> </a>

PowerShell 執行策略可協助判斷哪些組組檔案可以載入至 PowerShell 主控台，以及使用者可以從該主控台執行哪些腳本。 除非執行政策設定為 RemoteSigned，否則您至少無法商務用 Skype線上連接器模組。 如果沒有，當您嘗試輸入模組時，會收到下列錯誤訊息：
  
- 錯誤：Import-Module：檔案 C：無法載入程式檔案一般檔案<em>Microsoft Lync Server \\ \\ \\ 2013 \\ 模組 \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1，因為系統已停用執行中的腳本。詳細資訊，請參閱在 https://go.microsoft.com/fwlink/?LinkID=135170 about_Execution_Policies。</em>

- **解決方法**：若要解決此問題，請以系統管理員的名次啟動 PowerShell，然後執行下列命令：
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    有關執行策略的詳細資訊，請參閱 [關於執行策略](/powershell/module/microsoft.powershell.core/about/about_execution_policies)。
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Import-Module錯誤由不正確的版本Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

商務用 Skype線上連接器模組只能在 3.0 Windows PowerShell下執行。 如果您嘗試在先前版本的 PowerShell 下輸入模組，則導入程式會失敗，而出現錯誤訊息，類似此錯誤訊息：
  
  - **錯誤***：Import-Module：載入的 PowerShell 版本為 '2.0'。模組 'D：程式檔案共同檔案 \\ \\ Microsoft Lync Server \\ 2013 \\ 模組 \\ LyncOnlineConnector \\LyncOnlineConnector.psd1' 需要執行的最低 PowerShell 版本為 '3.0' 。請確認 PowerShell 的安裝，然後再試一次。*

- **解決方法**：修正此問題的唯一方法，是安裝 3.0 Windows PowerShell 3.0，可從 Microsoft 下載中心在 [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) .
  
## <a name="failed-to-connect-to-live-id-server"></a>無法連接到 Live ID Server
<a name="BKMKFailedConnect"> </a>

您的連接嘗試失敗的原因通常有三種，原因如下：

  - **錯誤***：Get-CsWebTicket：無法連接即時識別碼伺服器。請確定 Proxy 已啟用，或電腦已與即時識別碼伺服器建立網路連接。*

- **解決** 方式：此錯誤通常表示 Microsoft Online Services 登入小幫手未進行。 您可以從 PowerShell 提示執行下列命令，以驗證此服務的狀態： 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    如果服務未執行，請用此命令啟動服務：
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    如果服務執行中，您可能會遇到電腦與 Microsoft Live ID 驗證服務器之間的網路連接問題。 若要檢查這項功能，請開啟 Internet Explorer 並流覽至[ https://login.microsoftonline.com/ 。](https://login.microsoftonline.com/.) 請嘗試從Microsoft 365登Office 365或登陸。 如果無法解決問題，可能遇到網路連接問題。
  
    較不常見的是，可能是 Microsoft Live ID 驗證服務器的連接 URI 已配置為錯誤的值。 如果您已經判斷系統正在Sign-In小幫手，而且您沒有遇到網路問題，則此組組可能是問題。 在這種情況下，請聯絡 Microsoft 支援服務。
  
## <a name="failed-to-load-live-id-module"></a>載入 Live ID 模組失敗
<a name="BKMKFailedLoad"> </a>

使用 PowerShell 管理線上版的先決條件之一商務用 Skype安裝 Microsoft Online 服務登錄小幫手。 如果尚未安裝登錄小幫手，當您嘗試在線上建立遠端會話時，您會收到商務用 Skype訊息：

- **錯誤***：Get-CsWebTicket：無法載入 Live Id 模組。確認已安裝正確版本的 Live Id 登錄小幫手。*

- **解決** 方式：Microsoft Online Services 登入小幫手可在 Microsoft Online Services 的 Microsoft 下載中心Sign-In [IT 專業人員 RTW 小幫手](https://www.microsoft.com/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>使用者登入失敗
<a name="BKMKLogonFailed"> </a>

當您嘗試遠端連線至 商務用 Skype連線時，您必須提供線上使用者帳戶中有效商務用 Skype使用者名稱和密碼。 如果沒有，登入將會失敗，以及類似以下的錯誤訊息：

- **錯誤***：Get-CsWebTicket：登入失敗的使用者'kenmyer@litwareinc.com'。請建立新的 PSCredential 物件，確認您所使用的使用者名稱和密碼正確無誤。*

- **解決方法**：如果您認為您使用的是有效的使用者帳戶，而且您擁有正確的密碼，請再次嘗試登陸。 如果失敗，請使用相同的認證，並嘗試登入 [https://login.microsoftonline.com/](https://login.microsoftonline.com/) 。 如果您無法登入，請聯絡 Microsoft 支援服務。 

  
## <a name="the-user-doesnt-have-permission-to-manage-this-tenant"></a>使用者沒有管理此租使用者的許可權
<a name="BKMKUserPermission"> </a>

除非您是租使用者系統管理員群組的成員，否則您無法與商務用Skype Online 進行遠端 PowerShell 連線。 如果沒有，您的連接嘗試將會失敗，而且您會收到下列錯誤訊息：

- 錯誤：New-PSSession：[admin.vdomain.com] 從遠端伺服器 admin.vdomain.com 處理資料失敗，出現下列錯誤訊息：使用者 'user@foo.com' 沒有管理此租使用者的許可權 *。您可以將使用者指派給適當的 RBAC 角色，以授予許可權。詳細資訊，請參閱遠端 [疑難排解](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting)。*

- **解決方法**：如果您認為自己是或應該是租使用者系統管理員群組的成員，請聯絡 Microsoft 支援服務。
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>連線至租使用者的能力已在 商務用 Skype Online 中停用
<a name="BKMKAbilityConnect"> </a>

若要使用 PowerShell 商務用 Skype Online，您租使用者 PowerShell 策略的 EnableRemotePowerShellAccess 屬性必須設為 `True` 。 如果沒有，您的連接將會失敗，而且您會收到下列錯誤訊息：

- 錯誤 *：New-PSSession：[admin vdomain.com] 從遠端伺服器系統管理員 vdomain.com 處理資料失敗，出現下列錯誤訊息：已停用使用遠端 \. PowerShell 會話連接到此租使用者的能力 \. 。請聯絡 Lync Help 以檢查此租使用者的租使用者 Powershell 政策。詳細資訊，請參閱遠端 [疑難排解](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting)。*

- **解決方法**：如果您看到此錯誤訊息，您必須與 Microsoft 支援服務聯繫，並啟用遠端 PowerShell 存取。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>已超出此使用者在 商務用 Skype 命令命令的並行命令數目上限
<a name="BKMKMaxNumberShellsUser"> </a>

每個系統管理員最多可同時使用三個遠端連線商務用 Skype Online。 如果您有三個遠端 PowerShell 連接已啟動並執行，任何嘗試進行第四次同時連接都會失敗，並出現下列錯誤訊息：

- **錯誤***：New-PSSession：[admin vdomain.com] 無法連接到遠端伺服器系統管理員 vdomain.com，出現下列錯誤訊息：WS-Management 服務無法處理 \. \. 要求。已超過此使用者並行命令命令的上限。關閉現有的命令命令或提高此使用者的配額。詳細資訊，請參閱遠端 [疑難排解](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting)*

- **解決方法**：解決此問題的唯一方法就是關閉一或多個先前的連接。 完成線上商務用 Skype後，建議您使用 **Remove-PSSession** Cmdlet 結束會話。 此動作可協助避免此問題。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>已超出此租使用者在 商務用 Skype 的並行命令命令數目上限
<a name="BKMKMaxNumberShellsTenant"> </a>

雖然每個系統管理員可以同時與線上租使用者商務用 Skype三個連線，但單一租使用者不能同時連線超過 20 個。 例如，六個系統管理員可能各自有三個開啟的會話。 如果第七個系統管理員嘗試開啟超過兩個 (導致總共 21 個同時) ，此嘗試將會失敗，並出現下列錯誤訊息：
  
- **錯誤***：New-PSSession：[admin.vdomain.com] 無法連接到遠端伺服器 admin.vdomain.com 出現下列錯誤訊息：WS-Management服務無法處理要求。已超過此租使用者並行命令命令的上限。關閉現有的命令命令或提高此租使用者的配額。詳細資訊，請參閱 [遠端疑難排解] (/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting？view=powershell-5.1*

- **解決方法**：解決此問題的唯一方法就是關閉一或多個先前的連接。 當您完成線上商務用 Skype時，建議您使用 **Remove-PSSession** Cmdlet 來終止該會話。 這可協助避免此問題。  
 
## <a name="related-topics"></a>相關主題
[使用電腦設定商務用 skype 線上管理Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  

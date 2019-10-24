---
title: 使用商務用 Skype Online 連接器診斷連線問題
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
f1keywords: None
ms.custom:
- PowerShell
description: 疑難排解建立用來連線到商務用 Skype Online 的遠端 PowerShell 會話，包括匯入模組、併發 shell、Live ID 和許可權錯誤。
ms.openlocfilehash: dac4e2007853b489345f8ea137423cbd71363d56
ms.sourcegitcommit: 0de27096ea3c9d6f210aeb4aad31c4255c3c0244
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2019
ms.locfileid: "37642813"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>使用商務用 Skype Online 連接器診斷連線問題

本主題提供的資訊可協助您診斷並解決當您嘗試建立連線到商務用 Skype Online 的遠端 Microsoft PowerShell 會話時，可能會發生的問題。 請參閱下列各節：
  
- [Import-Windows PowerShell 執行原則所導致的模組錯誤](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [匯入-由於不正確的 Windows PowerShell 版本所導致的模組錯誤](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [已停用 WinRM 基本驗證時，新式驗證失敗](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [無法連線至 [Live ID] 伺服器](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [無法載入 [實際 ID] 模組](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [使用者登入失敗](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [使用者沒有管理此租使用者的許可權](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [在商務用 Skype Online 中已停用連接至租使用者的能力](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [已超出此使用者在商務用 Skype Online 中的併發 shell 數目上限](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [已超出此租使用者在商務用 Skype Online 中的併發 shell 數上限](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> 根據預設，PowerShell 會話會在60分鐘後超時。 若要重新連接，您必須關閉會話，然後啟動新的 PowerShell 會話。 新版本的[商務用 Skype Online （Windows PowerShell 模組（2046.123-已發佈的10/2/2019））](https://www.microsoft.com/download/details.aspx?id=39366)最近已啟動，其中包含一個名為**Enable-CsOnlineSessionForReconnection**的新 Cmdlet，可減少60分鐘超時問題。
> PowerShell 會話會重新連線並進行驗證，讓它得以重複使用，而不需啟動要重新連接的新實例。



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Import-Windows PowerShell 執行原則所導致的模組錯誤
<a name="BKMKPowerShellExecutionPolicy"> </a>

PowerShell 執行原則可協助判斷哪些設定檔可以載入到 PowerShell 主控台，以及使用者可以從該主控台執行哪些腳本。 除非執行原則已設定為 RemoteSigned，否則在最低限度的情況下，無法匯入商務用 Skype Online 連接器模組。 如果沒有，當您嘗試匯入模組時，您會收到下列錯誤訊息：
  
- **錯誤**：<em>匯入-模組：檔案 C\\： Program\\files 常見\\檔案 Microsoft Lync Server\\2013\\模組\\LyncOnlineConnector LyncOnlineConnectorStartup。 psm1 無法載入，因為正在執行此系統已停用腳本。如需詳細資訊，請參閱https://go.microsoft.com/fwlink/?LinkID=135170about_Execution_Policies。</em>

- **解析度**若要解決此問題，請以系統管理員的身分啟動 PowerShell，然後執行下列命令：
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
    如需有關執行原則的詳細資訊，請參閱[關於執行](https://go.microsoft.com/fwlink/?LinkID=135170)原則。
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>匯入-由於不正確的 Windows PowerShell 版本所導致的模組錯誤
<a name="BKMKIncorrectVersion"> </a>

商務用 Skype Online 連接器模組只能在 Windows PowerShell 3.0 下執行。 如果您嘗試在舊版 PowerShell 中匯入模組，匯入程式將會失敗，並顯示類似以下的錯誤訊息：
  
  - **錯誤**：匯*入-模組：載入的 PowerShell 版本是 "2.0"。Module to\\： Program files\\常見檔案\\Microsoft Lync Server 2013\\模組\\LyncOnlineConnector\\LyncOnlineConnector，psd1 ' 需要最小3.0 的 PowerShell 版本才能執行。請確認已安裝 PowerShell，然後再試一次。*

- **解決**方式：修正這個問題的唯一方法是安裝 Windows PowerShell 3.0，此版本可從 Microsoft 下載中心取得[https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595)。
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>已停用 WinRM 基本驗證時，新式驗證失敗
<a name="BKMKWinRMBasicAuth"> </a>

最新版本的商務用 Skype Online 連接器模組使用新式驗證，但基礎 Windows 遠端系統管理（WinRM）用戶端必須設定為允許基本驗證。  新式驗證使用通常會在*授權：載荷*標頭中傳遞的載荷權杖。 Windows PowerShell （在此建立商務用 Skype PowerShell）不允許操作此標頭。  相反地，商務用 Skype PowerShell 會使用*授權：基本*報頭來傳送載荷權杖。

如需有關如何啟用 WinRM 進行基本驗證的指示，請參閱[下載並安裝 Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) 。

## <a name="failed-to-connect-to-live-id-server"></a>無法連線至 [Live ID] 伺服器
<a name="BKMKFailedConnect"> </a>

使用下列錯誤訊息時，連接嘗試可能會失敗的原因有三種：

  - **錯誤**： *CsWebTicket：無法連接即時 id 伺服器。請確定已啟用 proxy，或電腦有連線至 live id 伺服器的網路連線。*

- **解決**方式：此錯誤通常表示 Microsoft Online Services 登入小幫手未執行。 您可以從 PowerShell 提示執行下列命令，以驗證此服務的狀態： 
    ```
    Get-Service "msoidsvc"
    ```
    如果服務未執行，請使用此命令啟動服務：
    ```
    Start-Service "msoidsvc"
    ```

    如果服務正在執行，您可能會遇到您的電腦與 Microsoft Live ID 驗證服務器之間的網路連線問題。 若要檢查此情況，請開啟 Internet Explorer，然後流覽至[ https://login.microsoftonline.com/。](https://login.microsoftonline.com/.) 嘗試從該處登入 Office 365。 如果這種情況失敗，可能是遇到網路連線問題。
  
    不太常見，Microsoft Live ID 驗證服務器的連線 URI 可能已設定為錯誤的值。 如果您已確定登入小幫手正在執行，而且您沒有網路連線問題，這可能是問題所在。 在這種情況下，請與 Office 365 支援人員聯繫。
  
## <a name="failed-to-load-live-id-module"></a>無法載入 [實際 ID] 模組
<a name="BKMKFailedLoad"> </a>

使用 PowerShell 來管理商務用 Skype Online 的其中一個先決條件是安裝 Microsoft Online Services 登入小幫手。 如果未安裝登入小幫手，當您嘗試與商務用 Skype Online 建立遠端會話時，您會收到下列錯誤訊息：

- **錯誤**： *CsWebTicket：無法載入 [即時 Id] 模組。請確定已安裝 [正確版本的 Live Id 登入*小幫手]。

- **解析度**：適用于[IT 專業人員的 microsoft Online services 登入](https://www.microsoft.com/en-us/download/details.aspx?id=28177)小幫手，Microsoft 下載中心提供 microsoft online services 登入小幫手 RTW

## <a name="logon-failed-for-the-user"></a>使用者登入失敗
<a name="BKMKLogonFailed"> </a>

當您嘗試建立與商務用 Skype Online 的遠端連線時，您必須提供有效的商務用 Skype Online 使用者帳戶的使用者名稱和密碼。 如果您沒有這樣做，登入將會失敗，並會出現類似以下的錯誤訊息：

- **錯誤**： *CsWebTicket：使用者 ' kenmyer@litwareinc.com ' 登入失敗。請建立新的 PSCredential 物件，並確認您使用的是正確的使用者名稱和密碼。*

- **解決方案**：如果您認為您使用的是有效的使用者帳戶，且您有正確的密碼，請嘗試再次登入。 如果失敗，請使用相同的認證，然後嘗試登入[https://login.microsoftonline.com/](https://login.microsoftonline.com/)。 如果您無法登入，請與 Office 365 支援人員聯繫。 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>使用者沒有管理此租使用者的許可權
<a name="BKMKUserPermission"> </a>

除非您是租使用者管理員群組的成員，否則您無法建立商務用的遠端 PowerShell 連線 toSkype for Business Online。 如果您不是這樣，您的連線嘗試將會失敗，而且您會收到下列錯誤訊息：

- **錯誤**：*新的 PSSession： [admin.vdomain.com] 從遠端伺服器 admin.vdomain.com 處理資料失敗，並出現下列錯誤訊息：使用者 ' user@foo.com」沒有管理此租使用者的許可權。您可以將使用者指派給適當的 RBAC 角色，以授與許可權。如需詳細資訊，請參閱[遠端疑難排解](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*

- **解決**方式：如果您認為您是（或應該是租使用者管理員群組的成員），您必須與 Office 365 支援人員取得聯繫。
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>在商務用 Skype Online 中已停用連接至租使用者的能力
<a name="BKMKAbilityConnect"> </a>

若要使用 PowerShell 來管理商務用 Skype Online，您必須將租使用者 PowerShell 原則的 EnableRemotePowerShellAccess 屬性設定`True`為。 如果不是，您的連線將會失敗，而且您會收到下列錯誤訊息：

- **錯誤**：*新的 PSSession： [admin.vdomain.com] 從遠端伺服器 admin.vdomain.com 處理資料失敗，並出現下列錯誤訊息：使用遠端 PowerShell 會話連線到此租使用者的功能已停用。請聯絡 Lync 說明，以查看此租使用者的租使用者 Powershell 原則。如需詳細資訊，請參閱[遠端疑難排解](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*

- **解決**方式：如果您看到這則錯誤訊息，您必須與 Office 365 支援人員取得聯繫，並啟用遠端 PowerShell 存取。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>已超出此使用者在商務用 Skype Online 中的併發 shell 數目上限
<a name="BKMKMaxNumberShellsUser"> </a>

每個系統管理員都允許最多三個同時遠端連線到商務用 Skype Online。 如果您有三個遠端 PowerShell 連線且正在執行，則嘗試讓第四個同步連接的嘗試將會失敗，並出現下列錯誤訊息：

- **錯誤**：*新的 PSSession： [admin.vdomain.com] 連線到遠端伺服器 admin.vdomain.com 失敗，並出現下列錯誤訊息： ws-management 服務無法處理該要求。已超出此使用者的併發 shell 數目上限。關閉現有的程式外殼程式，或升高此使用者的配額。如需詳細資訊，請參閱 [遠端疑難排解]https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 （*

- **解決**方式：解決這個問題的唯一方法，就是關閉一或多個先前的連線。 當您完成商務用 Skype Online 會話時，建議您使用**移除-PSSession** Cmdlet 來終止會話。 這將協助您避免這個問題。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>已超出此租使用者在商務用 Skype Online 中的併發 shell 數上限
<a name="BKMKMaxNumberShellsTenant"> </a>

雖然每個系統管理員都允許有多達三個同時連線至商務用 Skype Online 租使用者，但不允許單一租使用者同時連接20個以上的連線。 例如，六個系統管理員可能會有三個開啟的會話。 如果第四個系統管理員嘗試進行超過2個連線（導致總共有21個同時連線），此嘗試將會失敗，並出現下列錯誤訊息：
  
- **錯誤**：*新的 PSSession： [admin.vdomain.com] 連線到遠端伺服器 admin.vdomain.com 失敗，並出現下列錯誤訊息： ws-management 服務無法處理該要求。已超出此租使用者的併發 shell 數上限。關閉現有的程式外殼程式，或升高此租使用者的配額。如需詳細資訊，請參閱 [遠端疑難排解]https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 （*

- **解決**方式：解決這個問題的唯一方法，就是關閉一或多個先前的連線。 當您完成商務用 Skype Online 會話時，建議您使用**移除-PSSession** Cmdlet 來終止該會話。 這將協助您避免這個問題。  
 
## <a name="related-topics"></a>相關主題
[使用 Windows PowerShell 設定商務用 skype online 管理電腦](set-up-your-computer-for-windows-powershell.md)

  
 

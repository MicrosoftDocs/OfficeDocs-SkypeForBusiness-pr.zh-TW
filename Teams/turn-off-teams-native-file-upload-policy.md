---
title: 關閉原生Teams檔Upload策略
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: 瞭解如何使用 PowerShell 建立、設定、指派及Teams檔案策略。
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64bd9d23527ef1a63df4f258e89de5e60862a878
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2022
ms.locfileid: "62192482"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>關閉原生Teams檔Upload策略

Microsoft Teams使用OneDrive ODSP SharePoint (ODSP) 來儲存和共用內容，但某些組織和使用者可能偏好使用協力廠商儲存提供者。  

如果貴組織選擇內容儲存的協力廠商，您必須關閉檔案Teams ``NativeFileEntryPoints`` 參數。 此參數預設為啟用，顯示將內容從 ODSP 上傳至Teams或頻道的選項。

本文將協助您使用 PowerShell 建立、設定、指派 ``NativeFileEntryPoints`` 及移除參數。

>[!NOTE]
>當 Teams 檔案政策關閉時，使用者不會在 Teams 中看到 OneDrive 和 SharePoint (ODSP) 的存取點，但新團隊和頻道的建立會繼續觸發符合 SharePoint 文件庫的產生。

## <a name="prepare-to-update-the-teams-files-policy"></a>準備更新檔案Teams策略

### <a name="set-up-microsoft-powershell"></a>設定 Microsoft PowerShell

目前，此政策無法于系統管理中心Teams變更。 貴組織的租Microsoft 365系統管理員必須使用本文稍後詳述的 PowerShell Cmdlet 進行變更。

瞭解如何使用 PowerShell 圖庫Teams PowerShell 模組安裝[PowerShell](teams-powershell-install.md)Microsoft Teams模組。

若要安裝或下載 PowerShell 模組Teams，請參閱[PowerShell 圖庫以Microsoft Teams。](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0)

若要瞭解如何設定 PowerShell 以管理Teams，請參閱使用 PowerShell Teams[管理Microsoft Teams。](teams-powershell-managing-teams.md)

### <a name="allow-third-party-apps-in-teams-admin-center"></a>在系統管理中心Teams協力廠商應用程式

此步驟不需要變更 Teams 策略，但當您準備好將協力廠商儲存空間提供者整合至使用者的使用體驗時，Teams必須執行此步驟。

您的Microsoft 365租使用者系統管理員必須啟用系統管理中心中的「允許協力廠商應用程式」Teams政策。

若要瞭解如何允許協力廠商或自訂應用程式，請參閱在系統管理中心管理您的應用程式中管理Microsoft Teams[應用程式設定](/microsoftteams/manage-apps#manage-org-wide-app-settings)。

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>關閉整個租使用者的 NativeFileEntryPoints

將 ``-Identity`` 參數設定 ``Global`` 為會將原則設定適用于貴組織的所有使用者。

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>整個租使用者的 PowerShell 策略 Cmdlet 範例

此範例 PowerShell 命令會 ``NativeFileEntryPoints`` 針對整個租使用者 ``Disabled`` 設定參數。

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>檢查租使用者的狀態  

若要查看租使用者檔案Teams目前狀態，請使用 ``Get-CsTeamsFilesPolicy`` Cmdlet。

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>開啟或關閉原生檔案上傳點

若要開啟或關閉整個租使用者原生檔案上傳點，請設定參數 ``NativeFileEntryPoints`` 為 或 ``Enabled`` ``Disabled`` 。

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>移除使用者的政策

若要移除Teams檔案策略，請使用 ``Remove-CsTeamsFilesPolicy`` Cmdlet。

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>關閉特定使用者的 NativeFileEntryPoints

您也可以為特定使用者Teams檔案策略，Teams檔案策略字串，並將新建立的策略指派 ``-Identity`` 給使用者。

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>適用于特定使用者的 PowerShell 策略 Cmdlet 範例

此範例 PowerShell 命令會建立一個名稱為 且參數 ``CsTeamsFilesPolicy`` ``-Identity`` 設為 ``UserPolicy`` ``NativeFileEntryPoints`` 的新 ``Disabled`` 命令。

當使用者被指派為 時， ``CsTeamsFilesPolicy`` 其原生檔案 ``-Identity UserPolicy`` 輸入點會關閉。

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>指派策略給使用者

建立新策略之後，您可以使用 Cmdlet 將該策略 ``Grant-CsTeamsFilesPolicy`` 指派給使用者。

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>更新策略

如果您需要變更新的檔案Teams設定 ``UserPolicy`` ，請使用 ``Set-CsTeamsFilePolicy`` Cmdlet。

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>移除完整使用者清單的政策

若要從指派給檔案策略的所有使用者移除 ``UserPolicy`` Teams，請使用 ``Remove-CsTeamsFilesPolicy`` Cmdlet。

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> 變更政策後，最多 12 小時，變更會顯示在使用者的用戶端Teams顯示。

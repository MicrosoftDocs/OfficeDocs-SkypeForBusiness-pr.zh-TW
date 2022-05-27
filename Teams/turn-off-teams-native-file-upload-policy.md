---
title: 關閉Teams原生檔案Upload原則
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: 瞭解如何使用 PowerShell 建立、設定、指派及調整Teams檔案原則。
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2b6089e93b4754fa35edaa9befb5cfa6bb176238
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681904"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>關閉Teams原生檔案Upload原則

Microsoft Teams使用OneDrive和SharePoint來儲存及共用內容，但某些組織和使用者可能會偏好使用協力廠商儲存空間提供者。  

如果貴組織選擇協力廠商來儲存內容，您必須關閉 `NativeFileEntryPoints` Teams檔案原則中的參數。 此參數預設為啟用，顯示從OneDrive或SharePoint上傳內容至Teams聊天或頻道的選項。

本文將協助您使用 PowerShell 建立、設定、指派及移除 `NativeFileEntryPoints` 參數。

>[!NOTE]
>關閉Teams檔案原則時，使用者不會在Teams中看到OneDrive和SharePoint的存取點，但新團隊和頻道的建立仍會持續觸發相符SharePoint庫的產生。

## <a name="prepare-to-update-the-teams-files-policy"></a>準備更新檔案Teams原則

### <a name="set-up-microsoft-powershell"></a>設定 Microsoft PowerShell

目前，Teams系統管理中心無法變更此原則。 貴組織的Microsoft 365租使用者系統管理員必須使用本文稍後詳述的 PowerShell Cmdlet 進行變更。

若要瞭解如何使用 PowerShell 資源庫 安裝 PowerShell Teams模組，請閱讀安裝[Microsoft Teams PowerShell 模組](teams-powershell-install.md)。

若要安裝或下載 Teams PowerShell 模組，請參閱[Microsoft Teams PowerShell 資源庫](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0)。

如需如何設定 Teams 管理用 PowerShell 的詳細資訊，請參閱使用[Microsoft Teams PowerShell 管理Teams](teams-powershell-managing-teams.md)。

### <a name="allow-third-party-apps-in-teams-admin-center"></a>在 Teams 管理員 中心允許協力廠商應用程式

此步驟不需要變更Teams檔案原則，但是當您準備好將協力廠商儲存空間提供者整合到使用者Teams體驗中時是必要的。

您的Microsoft 365租使用者系統管理員必須在Teams系統管理中心啟用「允許協力廠商應用程式」原則。

若要瞭解如何允許協力廠商或自訂應用程式，請參閱在系統管理中心管理您的應用程式中的管理整個組織應用程式[的設定Microsoft Teams](/microsoftteams/manage-apps#manage-org-wide-app-settings)。

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>針對整個租使用者關閉 NativeFileEntryPoints

`-Identity`將參數設定為 `Global` 會將原則設定套用至組織中的所有使用者。

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>適用于整個租使用者的 PowerShell 原則 Cmdlet 範例

此範例 PowerShell 命令會針對您的整個租使用者設定 `NativeFileEntryPoints` 參數 `Disabled` 。

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>檢查租使用者的狀態  

若要檢視租使用者Teams檔案原則的目前狀態，請使用 `Get-CsTeamsFilesPolicy` Cmdlet。

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>開啟或關閉原生檔案上傳點

若要開啟或關閉整個租使用者的原生檔案上傳點，請將參數設 `NativeFileEntryPoints` 為 `Enabled` `Disabled` 。

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>移除使用者的原則

若要移除使用者Teams檔案原則，請使用 `Remove-CsTeamsFilesPolicy` Cmdlet。

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>針對特定使用者關閉 NativeFileEntryPoints

您也可以建立新的Teams檔案原則字串，並將新建立的原則指派給使用者，藉此更新特定使用者Teams檔案 `-Identity` 原則。

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>特定使用者的 PowerShell 原則 Cmdlet 範例

此範例 PowerShell 命令會建立新的 `CsTeamsFilesPolicy` `-Identity` 名稱 `UserPolicy` 和 `NativeFileEntryPoints` 參數設定為 `Disabled` 。

當使用者獲得指派 `CsTeamsFilesPolicy` `-Identity UserPolicy` 時，他們的原生檔案專案點將會關閉。

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>指派原則給使用者

建立新原則後，您可以使用 `Grant-CsTeamsFilesPolicy` Cmdlet 將該原則指派給使用者。

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>更新原則

如果您需要變更新Teams檔案 `UserPolicy` 原則的設定，請使用 `Set-CsTeamsFilePolicy` Cmdlet。

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>移除使用者完整清單的原則

若要從指派給Teams檔案 `UserPolicy` 原則的所有使用者中移除原則，請使用 `Remove-CsTeamsFilesPolicy` Cmdlet。

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> 變更原則之後，最多可在 12 小時之內讓變更顯示在使用者Teams用戶端中。

---
title: 設定Microsoft Teams工作區的會議附加元件
author: HowlinWolf-92
ms.author: v-mahoffman
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: 瞭解如何設定 Google workspace Microsoft Teams會議附加元件。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c5b3d873dd327be4cbc28d4d979ad06cb6f9c9ea
ms.sourcegitcommit: 9ed5aecbf671accae93ac5084ad7875e82e3858b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/31/2021
ms.locfileid: "61648881"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>設定Microsoft Teams工作區的會議附加元件

使用 Microsoft Teams可讓 Google 日曆使用者直接從 Google 工作區排程Microsoft Teams加入會議。 使用者可以存取會議Teams和音訊會議、螢幕分享、會議聊天、數位白板等。 保持聯繫並井井有條，以在公司、學校及生活中共同完成更多工作。

Microsoft Teams管理員必須啟用 Google Workspace 的會議附加元件，Teams使用者才能存取應用程式。

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>啟用或Microsoft Teams Azure 入口網站中的 Google Workspace 會議附加元件

做為租使用者系統管理員，您可以使用 Azure 入口網站Microsoft Teams，從組織的系統管理員帳戶啟用或停用 Google Workspace 的會議附加元件。

附加元件預設為啟用。

1. 請登錄 Azure 入口網站。

2. 選取 **Enterprise 應用程式**  >  **所有應用程式**。

3. 搜尋 **Microsoft Teams工作區的會議附加元件**。

   ![顯示所有應用程式的 Azure 入口網站。](media/aad-add-google-workspace.png)

4. 選取 **是**。

   ![顯示 Google 工作區屬性的 Azure 入口網站。](media/google-workspace-properties.png)

5.  (選擇性) 若要停用附加元件， **請選取步驟** 4 中的否，而不是 **是** 。

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>停用Microsoft Teams PowerShell 的 Google 工作區會議附加元件

```powershell
Connect-AzureAD

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-AzureADServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already, disable it
    Set-AzureADServicePrincipal -ObjectId $servicePrincipal.ObjectId -AccountEnabled $false
    Write-Host "Disabled existing Service Principal \n"
} else {
    # Service principal does not yet exist, create it and disable it at the same time
    New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName
    Get-AzureADServicePrincipal -Filter "appId eq '$appId'" | Set-AzureADServicePrincipal -AccountEnabled:$false
    Write-Host "Created and disabled the Service Principal \n"
}
```

詳細資訊，請參閱使用 Azure PowerShell[建立 Azure 服務主體](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)。

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>刪除 Microsoft Teams工作區的會議附加元件

請參閱 Google 檔 [刪除 Google Workspace Marketplace 應用程式](https://support.google.com/a/answer/6216211?hl=en) 以尋找相關指示。

## <a name="create-the-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>使用 PowerShell Microsoft Teams Google Workspace 的會議附加元件

如果您的租Microsoft Teams沒有會議附加元件，您可以使用 PowerShell 建立： 

```powershell
Connect-AzureAD

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-AzureADServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already
    Write-Host "The Service principal already exists"
} else {
    # Service principal does not yet exist, create it
    New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName
    Write-Host "Created the Service Principal"
}
```

---
title: 針對 Google Workspace 設定 Microsoft 團隊會議附加元件
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: 瞭解如何設定 Google Workspace 的 Microsoft 團隊會議附加元件。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c86d707a4298d88d3ae0cff389bda73490390e4
ms.sourcegitcommit: 380cd74c08cd34e1c3f73f5c0f51da4ae2674f6f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2021
ms.locfileid: "49880868"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>針對 Google Workspace 設定 Microsoft 團隊會議附加元件

使用 Microsoft 團隊會議附加元件可讓 Google 行事曆使用者從 Google Workspace 直接排程並加入 Microsoft 團隊會議。 使用者將能夠存取團隊會議功能，包括影片和音訊會議、螢幕共用、會議聊天、數位白板等。 保持連線與組織，以便在公司、學校和生活中共同完成工作。

您必須先由小組管理員啟用 Google Workspace 的 Microsoft 團隊會議附加元件，才能讓租使用者存取 app。

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>在 Azure 入口網站中啟用或停用 Google Workspace 的 Microsoft 團隊會議附加元件

作為租使用者管理員，您可以使用 Azure 入口網站從貴組織的管理員帳戶啟用或停用 Google Workspace 的 Microsoft 團隊會議附加元件。

預設會啟用附加元件。

1. 登入 Azure 入口網站。

2. 選取 [**企業應用程式**]  >  ****。

3. 搜尋 **Google Workspace 的 Microsoft 團隊會議附加** 元件。

   ![顯示所有應用程式的 Azure 入口網站](media/aad-add-google-workspace.png)

4. 選取 **[是]**。

   ![顯示 google workspace 屬性的 Azure 入口網站](media/google-workspace-properties.png)

5.  ([選用]) 停用附加元件，請在步驟4中選取 [ **否** ] 而不是 **[是]** 。

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>使用 PowerShell 針對 Google Workspace 停用 Microsoft 團隊會議附加元件

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
    $servicePrincipal = New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName -AccountEnabled $false
    Write-Host "Created and disabled the Service Principal \n"
}
```

如需詳細資訊，請參閱 [使用 Azure PowerShell 建立 azure 服務主體](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)。

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>刪除 Google Workspace 的 Microsoft 團隊會議附加元件

如需相關指示，請參閱 Google 檔 [刪除 Google Workspace Marketplace 應用程式](https://support.google.com/a/answer/6216211?hl=en) 。

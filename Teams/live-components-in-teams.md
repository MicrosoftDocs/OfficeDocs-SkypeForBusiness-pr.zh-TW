---
title: 管理即時元件Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何在 Teams 中管理即時Teams。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6be8db0fdde7509f5721277b4ee631f7a814171d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830217"
---
# <a name="manage-live-components-in-teams"></a>管理即時元件Teams

聊天中的即時Teams提供一種全新的構想、建立及共同決策的方式。 傳送元件 ，例如表格、工作清單或段落，讓聊天中的每個人都能在線上編輯，並查看變更。 這表示您可以收集小組的想法和意見，同時減少會議次數，並盡可能減少長時間聊天對話的需要。

**一起更快速地完成工作。** 群組來源議程、追蹤群組的動作專案，或共同記錄筆記。 這些只是讓即時元件更容易的一些案例。

**共用元件。** 在這個版本中，您可以將即時元件共用至不同的聊天Teams聊天。 收件者無論身在何處都可以編輯，而且無論變更在何處，都可以立即看到更新。 在未來版本中，即時元件Teams會議筆記和頻道、Outlook，以及最終在所有Microsoft 365支援。

**從聊天開始，從該開始建立。** 您從聊天Teams建立的每一個元件都會自動儲存到 OneDrive。 因此，您可能會開始在聊天中共同合作，然後再移至檔案，因為檔案的視覺空間較大，可以視需要新增更多元件。

## <a name="clients-and-platforms"></a>用戶端和平臺

適用于 Teams、Mac Windows Linux、iOS 和 Android 上的應用程式。

從 9 月初開始，將在全球提供即時元件。 9 月底的 Mod 政府社群雲端提供 (GCC) 。

## <a name="settings-management"></a>設定管理

即時元件是由整個套件Microsoft 流體架構支援Microsoft 365，且從 SharePoint Online 而非系統管理中心Teams控制。

您需要最新版本的 Online [PowerShell](/office365/enterprise/powershell/manage-sharepoint-online-with-office-365-powershell)模組SharePoint啟用或停用整個租使用者的所有流暢體驗Office 365體驗。 Microsoft 流體架構所有目標發行租使用者的預設為 ON。 由於即時元件是專為共同操作所設計，因此元件一直以可編輯方式共用給其他人，即使您的租使用者已設為預設為僅供其他檔案類型使用，也一樣。 如需詳細 **資料** ，請參閱設定旁的深入瞭解連結。

## <a name="checking-if-the-fluid-framework-is-enabled-through-the-sharepoint-online-powershell-cmdlet"></a>檢查是否透過 流體架構 PowerShell Cmdlet SharePoint啟用

1. [連線至 SharePoint PowerShell。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. 在沒有任何流體架構的情況下，Get-SPOTenant Cmdlet 來檢查是否已啟用此參數。

3. 確認 IsFluidEnabled 的值 **為 True。**

## <a name="enabling-the-fluid-framework-through-the-sharepoint-online-powershell-cmdlet"></a>透過 流體架構 PowerShell Cmdlet SharePoint功能 

1. [連線至 SharePoint PowerShell。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. 使用 Cmdlet Set-SPOTenant -IsFluidEnabled $true 
   
   這項變更需要一些時間，以適用于您的租使用者。 

這項功能將在電腦版、mac 版、iOS Teams Windows Android 版上提供。 啟用時，使用者會看到一個新選項，可針對這些用戶端在郵件撰寫體驗中插入即時元件。

## <a name="disabling-fluid-framework-through-sharepoint-online-powershell-cmdlet"></a>透過 流體架構 PowerShell Cmdlet SharePoint停用

1. [連線至 SharePoint PowerShell。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

2. 使用 Cmdlet Set-SPOTenant 停用Set-SPOTenant -IsFluidEnabled $false。 

   這項變更需要一些時間，以適用于您的租使用者。 

如果您需要重新啟用此功能，您可以使用線上 PowerShell Cmdlet SharePoint PowerShell Cmdlet。

```powershell
C:\\WINDOWS\\system32&gt; Connect-SPOService
cmdlet Connect-SPOService at command pipeline position 1

Supply values for the following parameters:
Url: <https://a830edad9050849822e21011208-admin.sharepoint.com/>
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $false
PS C:\\WINDOWS\\system32&gt;
```

## <a name="known-limitations"></a>已知限制

- 重新開機應用程式之後，將表格或工作清單建立為第一Teams可能需要一些時間。

- 當在 (@) 提及時，其他聊天成員會收到電子郵件通知。  (活動資訊Teams中的提醒通知即將推出。) 

- 在搜尋中搜尋即時Teams會返回連結至 office.com 中的元件，而不是聊天訊息本身。

- 在聯合聊天中停用即時元件，並啟用使用 Azure B2B 與來賓帳戶進行一般聊天。

- 雖然您可以在頻道和其他應用程式Teams元件Microsoft 365，但收件者目前可在大部分的地方取得連結。 內嵌編輯計畫在未來提供更多體驗。

## <a name="storage-of-fluid-files"></a>儲存體 `.fluid` 檔案

**如何 `.fluid` 儲存？**

在 Teams中建立即時元件會以儲存在建立者檔案庫的檔案 `.fluid` 商務用 OneDrive。 成為檔案商務用 OneDrive表示使用者可以建立、探索和管理即時元件， (檔案) 任何檔Office `.fluid` 元件。

使用者可以從 `.fluid` Office.com 和 商務用 OneDrive 中搜尋商務用 OneDrive。
`.fluid` 檔案可處理電子檔探索、稽核、報告和法律保留等資料監管功能。

`.fluid`檔案現在會顯示在 Office.com 和 商務用 OneDrive，例如位於最近和建議的區域。
`.fluid`檔案可以從 商務用 OneDrive 還原到商務用 OneDrive。

聊天參與者必須擁有OneDrive帳戶，以建立即時元件。 如果沒有有效的OneDrive帳戶，聊天參與者仍可在其他使用者所建立的元件上共同OneDrive帳戶，但無法建立自己的元件。

[將](https://support.microsoft.com/en-us/office/move-files-and-folders-between-onedrive-and-sharepoint-5916f90d-f58a-4bf9-b135-10853f516d0b)檔案從OneDrive移動到SharePoint，會導致即時元件無法載入 `.fluid` 至Teams聊天。

**如果檔案擁有者離開公司，會發生什麼情況？**

[OneDrive保留原則](/microsoft-365/compliance/retention-policies-sharepoint?view=o365-worldwide#when-a-user-leaves-the-organization)適用于檔案，就像適用于使用者建立 `.fluid` 的其他內容一樣。

**如何 `.fluid` 共用檔案？**

即時元件可以在聊天中插入Teams，或從一個聊天複製到另一個聊天。  (頻道中尚未支援 Live 元件。) 它們預設為租使用者的現有許可權，但使用者可以在傳送前變更許可權，以確保每個人都能存取。

在 Teams.com 中開啟Office聊天的元件，提供視窗頂端的共用功能，類似其他檔Office選項。

**如果檔案 `.fluid` 損毀或損毀呢？**

版本歷程記錄可讓您從檔案的先前版本進行審閱和複製。

**哪些應用程式可以開啟和編輯 `.fluid` 檔案？**

`.fluid`檔案只能在瀏覽器中以連結開啟，例如 Office.com，以及聊天中的即時Teams元件。 下載後，若未先將檔上傳回線上或線上，商務用 OneDrive SharePoint開啟。

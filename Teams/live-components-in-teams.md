---
title: 在 Teams 中管理即時元件
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何在 Teams 中管理即時元件。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb472822f7d55636bfd5ee4c48e7c962a705f6e05fd65b263952895040d69f7c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305015"
---
# <a name="manage-live-components-in-teams"></a>在 Teams 中管理即時元件

Teams 聊天中的即時元件提供一種新的方式，ideate、建立及進行決策。 傳送元件（如資料表、工作清單或段落），讓您聊天中的每個人都可以進行內嵌編輯，並在進行變更時看到變更。 這表示您可以從小組那裡收集創意和意見，同時保留較少的會議，並最小化對長聊天線程的需求。

**更快速地取得任務。** 對等-來源議程、追蹤群組的動作專案，或共同記下記事。 這只是許多使用 live 元件所做的案例。

**共用元件。** 在此版本中，您可以在不同的 Teams 聊天中共用即時元件。 收件者可以從任何位置進行編輯，不論在何處進行變更，都可以立即查看更新。 在未來的版本中，會支援 Teams 會議筆記和頻道、Outlook，最後跨所有 Microsoft 365 應用程式的即時元件。

**開始交談，組建來源。** 您從 Teams 聊天建立的每個元件都會自動儲存至 OneDrive 中的檔案。 因此，您可能會在聊天中開始進行共同作業，然後再移至檔案，在此檔案中，您有較大的視覺空間可供編輯，而且可以視需要新增任意數目的元件。

## <a name="clients-and-platforms"></a>用戶端和平臺

適用于 Windows、Mac、Linux、iOS 和 Android 上的 Teams 應用程式。

從九月份開始，live 元件將會全域可用。 在9月晚些時候，它將可用於政府社群雲端 Mod (GCC) 。

## <a name="settings-management"></a>設定管理

Live 元件是以支援 Microsoft 365 套件 Microsoft 流體架構的方式所建立，並由 SharePoint 線上控制，而不是從 Teams 系統管理中心。

您將需要最新版的[SharePoint Online PowerShell 模組](/office365/enterprise/powershell/manage-sharepoint-online-with-office-365-powershell)，以啟用或停用整個 Office 365 租使用者的所有流體體驗。 針對所有目標發行承租人的 Microsoft 流體架構預設值為 **ON** 。 因為 live 元件是專為共同作業而設計，即使您的租使用者設定為預設值為僅供查看其他檔案類型，您也可以在其他檔案類型的情況下，將元件視為預設為可編輯。 如需詳細資訊，請參閱設定旁的「 **深入瞭解** 」連結。

## <a name="checking-if-the-fluid-framework-is-enabled-through-the-sharepoint-online-powershell-cmdlet"></a>檢查是否已透過 SharePoint 線上 PowerShell Cmdlet 來啟用流體架構

1. [連線 SharePoint 線上 PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password)。 

2. 執行沒有任何引數的 Get-SPOTenant Cmdlet，檢查是否已啟用流體架構。

3. 確認 IsFluidEnabled 的值為 **true**。

## <a name="enabling-the-fluid-framework-through-the-sharepoint-online-powershell-cmdlet"></a>透過 SharePoint 線上 PowerShell Cmdlet 啟用流體架構 

1. [連線 SharePoint 線上 PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password)。 

2. 使用 Cmdlet Set-SPOTenant-IsFluidEnabled $true 來啟用流體 
   
   變更將需要很短的時間來套用整個租用。 

在 Teams Windows 的桌面、Mac、iOS、Android 上都可以使用此功能。 啟用時，使用者會看到新的選項，可在這些用戶端的郵件撰寫體驗中插入即時元件。

## <a name="disabling-fluid-framework-through-sharepoint-online-powershell-cmdlet"></a>透過 SharePoint 線上 PowerShell Cmdlet 停用流體架構

1. [連線 SharePoint 線上 PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。

2. 使用 Set-SPOTenant Cmdlet 停用流體 Set-SPOTenant-IsFluidEnabled $false 的流體。 

   變更將需要很短的時間來套用整個租用。 

如果您需要重新啟用這項功能，您可以使用 SharePoint 線上 PowerShell Cmdlet。

```powershell
C:\\WINDOWS\\system32&gt; Connect-SPOService
cmdlet Connect-SPOService at command pipeline position 1

Supply values for the following parameters:
Url: <https://a830edad9050849822e21011208-admin.sharepoint.com/>
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $false
PS C:\\WINDOWS\\system32&gt;
```

## <a name="known-limitations"></a>已知限制

- 在 Teams 應用程式重新開機之後建立資料表或工作清單做為第一個元件，可能需要一些額外的時間。

- 其他聊天成員會在出現 ( @ ) 符號的情況時收到電子郵件通知。 Teams 活動摘要中的 (At 提及通知將會很快提供。 ) 

- 在 Teams 搜尋內搜尋即時元件會傳回連結至 office.com 中的元件，而非聊天訊息本身。

- 使用 Azure B2B，可在同盟聊天中停用即時元件，並以來賓帳戶為一般聊天啟用。

- 雖然您可以在 Teams 通道和其他 Microsoft 365 應用程式中共用元件，收件者此時會在大多數位置取得連結。 現場編輯已計畫于未來獲得更多體驗。

## <a name="storage-of-fluid-files"></a>檔儲存體 `.fluid`

**如何 `.fluid` 儲存？**

在 Teams 中建立的即時元件會以建立者商務用 OneDrive 中儲存的檔案來備份 `.fluid` 。 做為商務用 OneDrive 的檔案，意味著使用者可以像在 `.fluid` 任何 Office) 檔一樣輕鬆地建立、探索及管理即時元件 (檔案。

使用者可以 `.fluid` 從 Office .com 和商務用 OneDrive 搜尋檔案中的內容。
`.fluid` 檔案可搭配 eDiscovery、審核、報告和法律封存等資料管理功能運作。

`.fluid`檔案現在會出現在 Office .com 和商務用 OneDrive 上，例如最近及建議的區域。
`.fluid`檔案可以從商務用 OneDrive 還原至先前的版本。

聊天室參與者必須具有 OneDrive 帳戶，才能建立即時元件。 若沒有有效的 OneDrive 帳戶，聊天參與者仍可在其他具有有效 OneDrive 帳戶之使用者所建立的元件上進行共同作業，但無法自行建立。

[](https://support.microsoft.com/en-us/office/move-files-and-folders-between-onedrive-and-sharepoint-5916f90d-f58a-4bf9-b135-10853f516d0b)將檔案 `.fluid` 從 OneDrive 移至 SharePoint 網站，會導致即時元件無法在 Teams 聊天中載入。

**如果檔案擁有者離開公司，會發生什麼情況？**

[OneDrive 保留原則](/microsoft-365/compliance/retention-policies-sharepoint?view=o365-worldwide#when-a-user-leaves-the-organization)會套用至檔案， `.fluid` 就像是使用者所建立的其他內容一樣。

**共用檔案的方式為何 `.fluid` ？**

您可以在 Teams 聊天或從一部聊天到另一張聊天中插入即時元件。  (不支援在通道中使用 Live 元件。 ) 它們會預設為租使用者的現有許可權，但使用者可以在傳送之前變更許可權，以確保每個人都可以存取。

Office .com 中的 Teams 聊天室中開啟元件，可在視窗頂端提供共用功能，類似于其他 Office 檔所提供的共用選項。

**如果檔案遭到 `.fluid` 損毀或損毀，該怎麼辦？**

版本史可讓您複查及複製先前版本的檔案。

**哪些應用程式可以開啟和編輯檔案 `.fluid` ？**

`.fluid`檔案只可以在瀏覽器中開啟為連結，例如 Office .com，以及 Teams 聊天中的即時元件。 若下載後，就無法再將其上傳回商務用 OneDrive 或 SharePoint 線上中開啟。

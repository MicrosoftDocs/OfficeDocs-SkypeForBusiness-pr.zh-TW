---
title: 在 Teams
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
ms.openlocfilehash: b54ccf83aadcec724d8e54a791770578ef147bbd
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2022
ms.locfileid: "62191854"
---
# <a name="manage-live-components-in-teams"></a>在 Teams

聊天中的即時Teams提供一種共同構思、建立及做出決策的新方式。 傳送元件 ，例如表格、工作清單或段落，讓聊天中的每個人都能在線上編輯，並查看變更。 這表示您可以收集小組的想法和意見，同時減少會議次數，並盡可能減少長時間聊天對話的需要。
> [!Note]
> 即時元件是[Microsoft Loop](https://www.microsoft.com/en-us/microsoft-loop)應用程式的第一項功能，可在 Teams。 請注意，「即時元件」將于 2022 年初重新命名為「迴圈元件」。

**一起更快速地完成工作。** 群組來源議程、追蹤群組的動作專案，或共同記錄筆記。 這些只是讓即時元件更容易的一些案例。

**共用元件。** 在這個版本中，您可以將即時元件共用至不同的Teams聊天。 收件者無論身在何處都可以編輯，而且無論變更在何處，都可以立即看到更新。 在未來版本中，即時元件Teams會議筆記和頻道、Outlook，以及最終在所有Microsoft 365支援。

**從聊天開始，從該開始建立。** 您從聊天Teams建立的每一個元件都會自動儲存到 OneDrive。 因此，您可能會開始在聊天中共同合作，然後再移至檔案，因為檔案的視覺空間較大，可以視需要新增更多元件。

## <a name="clients-and-platforms"></a>用戶端和平臺

適用于 Teams、Mac Windows Linux、iOS 和 Android 上的應用程式。

## <a name="settings-management"></a>設定管理

即時元件是由整個套件Microsoft 流體架構支援Microsoft 365，且從 SharePoint Online 而非系統管理中心控制Teams元件。

您需要最新版本的 SharePoint Online [PowerShell 模組](/office365/enterprise/powershell/manage-sharepoint-online-with-office-365-powershell)，才能啟用或停用整個租使用者Office 365體驗。 Microsoft 流體架構所有目標發行租使用者的預設為 ON。 由於即時元件是專為共同操作所設計，因此元件一直以可編輯方式共用給其他人，即使您的租使用者已設為預設為僅供其他檔案類型使用，也一樣。 如需詳細 **資料** ，請參閱設定旁的深入瞭解連結。

## <a name="checking-if-the-fluid-framework-is-enabled-through-the-sharepoint-online-powershell-cmdlet"></a>檢查是否透過 流體架構 PowerShell Cmdlet SharePoint啟用

1. [連線至 SharePoint PowerShell。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. 在沒有任何流體架構的情況下，Get-SPOTenant Cmdlet 來檢查是否已啟用此功能。

3. 確認 IsFluidEnabled 的值 **為 True。**

## <a name="enabling-the-fluid-framework-through-the-sharepoint-online-powershell-cmdlet"></a>透過 流體架構 PowerShell Cmdlet SharePoint功能

1. [連線至 SharePoint PowerShell。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. 使用 Cmdlet Set-SPOTenant -IsFluidEnabled $true 
   
   這項變更需要一些時間，以適用于您的租使用者。 

這項功能將在電腦版、mac 版、iOS Teams Windows Android 版上提供。 啟用時，使用者會看到一個新選項，可針對這些用戶端在郵件撰寫體驗中插入即時元件。

## <a name="disabling-fluid-framework-through-sharepoint-online-powershell-cmdlet"></a>透過 流體架構 PowerShell Cmdlet SharePoint停用

1. [連線至 SharePoint PowerShell。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

2. 使用 Cmdlet Set-SPOTenant停用Set-SPOTenant -IsFluidEnabled $false。 

   這項變更需要一些時間，以適用于您的租使用者。 

如果您需要重新啟用此功能，您可以使用線上 PowerShell Cmdlet SharePoint PowerShell Cmdlet。

```powershell
C:\\WINDOWS\\system32&gt; Connect-SPOService
cmdlet Connect-SPOService at command pipeline position 1

Supply values for the following parameters:
Url: <https://a830edad9050849822e21011208-admin.sharepoint.com/>
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $true
PS C:\\WINDOWS\\system32&gt;
```
## <a name="known-issues"></a>已知問題

- 在 Android 上使用聊天功能時Office 應用程式聊天Teams元件。

- 如果租使用者的預設檔案許可權設定為 [特定人員 (只有使用者指定的 **人員) ，** 而寄件者在建立元件時，會從許可權對話方塊中的 [特定人員清單> 移除部分使用者，則這些使用者可能仍可存取內容。 此問題是許可權對話方塊的存取管理限制所導致，將會在未來版本中修正。

- 如果租使用者的條件式 Access 策略設定禁止用戶端網路連接到，即時元件無法如預期方式使用，無法為服務即時變更 `https://pushchannel.1drv.ms` 進行節省。

## <a name="known-limitations"></a>已知限制

- 在搜尋中搜尋即時Teams會返回連結至 office.com 中的元件，而不是聊天訊息本身。

- 在聯合聊天中停用即時元件。

- 除非租使用者設定外部存取選項，允許 B2B 來賓擁有與租使用者成員相同的存取層級，否則 B2B 來賓將無法在透過公司共用連結共用之即時元件上共同合作。 詳細資訊，請參閱設定 [B2B 外部共同合作設定](/azure/active-directory/external-identities/delegate-invitations#configure-b2b-external-collaboration-settings)。

- Teams即將推出即時元件的完整 Web 用戶端支援。

- 目前尚未在Teams支援即時元件，但計畫在頻道中進行內嵌編輯，以在未來獲得更多體驗。

- 將租使用者預設檔案許可權設定為 [特定人員 (只有使用者指定的 **人員) ，** 複製連結至即時元件，並在另一個聊天中加上，則寄件者需要使用許可權對話方塊，並新增 [特定人員」 選項中的收件者，以正確授予存取權。

- 將租使用者預設檔案許可權設定為特定人員 (只有使用者指定的 **人員) ，** 在超過 20 個成員的群組聊天中建立即時元件時，寄件者必須手動選取元件的許可權選項。

- 只有當檔案移至不同的文件庫時，聊天中的即時元件才能載入。 如果檔案移至不同的資料夾，檔案會繼續在聊天中載入。

## <a name="how-to-check-your-tenants-default-file-permissions"></a>如何檢查租使用者的預設檔案許可權

1. 請[前往](https://admin.microsoft.com/)Microsoft 365 系統管理中心。

2. 在左側的系統 **管理中心** 下 **，選取** SharePoint。

3. 選取 **策略**  >  **共用**，然後于檔案 **和資料夾連結下**，查看您的租使用者的預設檔案許可權。

## <a name="storage-of-fluid-files"></a>儲存體 `.fluid` 檔案

**如何 `.fluid` 儲存？**

在 Teams 中建立即時元件會以儲存在建立者檔案庫的檔案 `.fluid` 商務用 OneDrive。 成為檔案商務用 OneDrive表示使用者可以建立、探索及管理即時元件， (檔案) 檔一樣Office `.fluid` 元件。

使用者可以從 `.fluid` Office.com 和 商務用 OneDrive 中搜尋商務用 OneDrive。
`.fluid` 檔案可處理電子檔探索、稽核、報告和法律保留等資料監管功能。

`.fluid`檔案現在會顯示在 Office.com 和 商務用 OneDrive，例如 ，在最近和建議的區域。
`.fluid`檔案可以從 商務用 OneDrive 還原到商務用 OneDrive。

聊天參與者必須擁有OneDrive帳戶，以建立即時元件。 如果沒有有效的OneDrive帳戶，聊天參與者可能仍然可以在其他使用者所建立的元件上共同OneDrive帳戶，但無法建立自己的元件。

[將](https://support.microsoft.com/en-us/office/move-files-and-folders-between-onedrive-and-sharepoint-5916f90d-f58a-4bf9-b135-10853f516d0b)檔案從OneDrive移動到SharePoint，會導致即時元件無法載入 `.fluid` 至Teams聊天。

**如果檔案擁有者離開公司，會發生什麼情況？**

[OneDrive保留原則](/microsoft-365/compliance/retention-policies-sharepoint?view=o365-worldwide#when-a-user-leaves-the-organization)適用于檔案，就像適用于使用者建立 `.fluid` 的其他內容一樣。

**如何 `.fluid` 共用檔案？**

即時元件可以在聊天中插入Teams，或從一個聊天複製到另一個聊天。  (頻道中尚未支援 Live 元件。) 這些元件預設為租使用者的現有許可權，但使用者可以在傳送前變更許可權，以確保每個人都能存取。

在 Teams.com 中開啟Office聊天的元件，提供視窗頂端的共用功能，類似其他檔Office選項。

**如果檔案 `.fluid` 損毀或損毀呢？**

版本歷程記錄可讓您從檔案的先前版本進行審閱和複製。

**哪些應用程式可以開啟和編輯 `.fluid` 檔案？**

`.fluid`檔案只能在瀏覽器中以連結開啟，例如 Office.com，以及聊天中的即時Teams元件。 下載後，若未先將檔上傳回線上或線上商務用 OneDrive SharePoint開啟。

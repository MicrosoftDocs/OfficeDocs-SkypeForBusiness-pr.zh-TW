---
title: 使用 OneDrive 和 SharePoint 進行會議錄製
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何從 Microsoft 團隊中的 [資料流程] 切換至 [商務用 OneDrive] 和 [SharePoint 會議錄製儲存空間]。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b31972ed662b6752286fa2ff33b80150496cfb0f
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361333"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>在會議錄製中使用商務用 OneDrive 和 SharePoint 或串流

> [!Note]
> 從使用 Microsoft Stream 到變更為使用商務用 OneDrive 和 OneDrive 來進行會議錄製，將會採取階段性的方式。 在啟動時，租使用者系統管理員可以在10月2020中選擇這個新的工作流程選項，並開始查看錄製自動上傳至商務用 OneDrive 和 SharePoint 的功能。 在11月，如果您想要繼續使用串流，且在早期的2021中還有一些時間，我們會要求所有客戶使用商務用 OneDrive 和 SharePoint 來進行新的會議錄製。

Microsoft 團隊有一個儲存會議錄製的新方法。 從資料流程出發，此方法會在 Microsoft 365 中使用 Microsoft OneDrive 和 SharePoint，並提供許多好處。

使用商務用 OneDrive 和 SharePoint 儲存錄製的好處包括：

- 團隊會議錄製 (TMR)  (S + C E5 autoretention 標籤的保留原則) 
- 從商務用 OneDrive 和 SharePoint 資訊管理獲益
- 輕鬆設定許可權和共用
- 在只有明確共用的情況 (外部使用者) 與來賓共用錄製
- 要求存取流程
- 供應商務用 OneDrive 和 SharePoint 共用連結
- 增加配額
- 更快速地提供會議錄製
- **開始提供本機** 租使用者支援
- 多地區支援–錄製會儲存在該使用者專用的區域中
- 提供您自己的金鑰 (BYOK) 支援
- 改良的記錄品質與演講者歸屬

以下是一些需要考慮的限制：

- 系統會提供英文版隱藏式輔助字幕和記錄。
- 您將無法搜尋 [腳本] 或其內容。
- 您無法編輯這些記錄，但您可以開啟/關閉 [標題]。
- 您可以控制您共用錄製的物件，但無法封鎖有共用存取權的人員下載錄製。
- 錄製完成後，您將不會收到電子郵件，但錄製會在會議完成後出現在會議聊天中。 這將會比先前在資料流程中的速度更快

如需詳細資訊，請觀看「會議錄製」。

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>設定商務用 OneDrive 和 SharePoint 的會議錄製選項

1. 安裝商務用 Skype Online PowerShell 管理主控台。

    a. 下載 [商務用 Skype Online Powershell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide)。

    b. 依照提示進行安裝。

    c-clip. 重新開機您的電腦。

2. 以系統管理員身分啟動 PowerShell

3. 匯入 SkypeOnline 連接器，然後以團隊管理員身分登入。

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. 使用 [ [設定] csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) ，將 [團隊會議原則] 轉換為 [從資料流程儲存轉換為 ODSP]。

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>退出商務用 OneDrive 和 SharePoint 以繼續使用資料流程

即使原則將它設定為 [ **資料流程**]，也可能不會設定。 通常，如果原則沒有設定，則預設設定為 [ **資料流程**]。 不過，如果您想要選擇不使用 SharePoint 或 OneDrive，請使用這項新的變更，您必須將原則重設為 **串流** ，以確保它是預設值。

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a>常見問題集

**會議錄製將儲存在哪裡？**

- 對於非頻道會議，錄製會儲存在名為的資料夾中。 [錄製 * *] 位於 OneDrive 的最上層，且屬於開始會議錄製的人員。 範例

  <i>錄影機的商務</i> / 用 OneDrive**錄製**

- 對於頻道會議，錄製會儲存在名為 [ **錄製**] 資料夾的 [小組網站] 文件庫中。 範例

  <i>團隊名稱-頻道名稱</i> /**檔** /**錄製**

**誰有權查看會議錄製？**

- 如果是非頻道會議，除了外部使用者以外的所有會議受邀者，都將自動取得個人共用的連結。 外部使用者必須透過會議召集人或開始會議錄製的人員，將其明確新增至共用清單中。

- 對於頻道會議，許可權是從頻道中的 [擁有人] 和 [成員] 清單繼承而來。

**我要如何管理腳本？**

客戶加入宣告此預覽並不會在其小組會議錄製中提供隱藏式輔助字幕，且已遷移至 OneDrive 和 SharePoint。我們正致力於將隱藏式輔助字幕從英文新增至2020年10月的會議錄製。

小組會議錄製會提供隱藏式輔助字幕，供已自願加入在[小組雲端錄製](cloud-recording.md)中描述的客戶使用。

[標題] 可協助為所有功能的檢視器建立包含內容。 在擁有者中，您可以隱藏標題，但除非您刪除小組中的標題，否則仍可在團隊中使用這些記錄。 瞭解 [如何開啟或關閉會議錄製](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

錄製會議時，小組會議錄製支援的60天是隱藏式輔助字幕。

**我的儲存空間配額受影響的方式**

小組會議會在商務用 OneDrive 和 SharePoint 中即時錄製檔案，並包含在這些服務的配額中。 請參閱 [SharePoint 配額](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) 和 [商務用 OneDrive 配額] (https://docs.microsoft.com/onedrive/set-default-storage-space) 。

**如何播放團隊會議錄製？**

您的影片將會在商務用 OneDrive 或 SharePoint 的影片播放機上播放，視您存取該檔案的位置而定。

**如果您打算 deprecating 新增至串流，現有的影片會持續保持不變嗎？**

在不久的將來，不會棄用作為平臺的資料流程。 目前在資料流程中的影片會一直留在這裡，直到我們開始進行遷移為止。 遷移時，這些影片也會同時遷移至 ODSP。 若要瞭解詳細資訊，請參閱 [這裡](https://docs.microsoft.com/stream/streamnew/classic-migration) 。

---
title: 使用商務用 OneDrive 和 SharePoint 進行會議錄製
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
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0e9fcc4475b7f06b427dbc73de4b00b09b08755a
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085547"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>在會議錄製中使用商務用 OneDrive 和 SharePoint 或串流

> [!Note]
> 使用 Microsoft Stream to 商務用 OneDrive 和 Microsoft SharePoint for meeting 錄製所做的變更將是一種分階段的方法。

|<div style="width:290px">為止&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |引發&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|2020年10月5日 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| 您可以讓團隊會議原則將會議錄製儲存到商務用 OneDrive 和 SharePoint，而不是 Microsoft Stream (傳統) |
|從2021年1月11日開始推出 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|所有新團隊會議錄製將會儲存到商務用 OneDrive 和 SharePoint，除非您修改組織的團隊會議原則，並明確將其設定為 [ **串流**]，否則您需要延遲此變更。 看不到原則報告的資料流程是不夠的。 您必須將原則值明確設定為 [ **資料流程**]。|
|從2021年3月1日開始推出 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**企業客戶**<br>無法將新會議錄製儲存至 Microsoft Stream (傳統) ;所有客戶都會自動將會議錄製儲存到商務用 OneDrive 和 SharePoint，即使他們已將其小組會議原則變更為 [ **串流**]。 我們建議客戶將此功能放在這個日期之前，讓他們能夠控制發行的時間。 |
|開始推出2021年7月7日 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**教育客戶**<br>無法將新會議錄製儲存至 Microsoft Stream (傳統) ;所有客戶都會自動將會議錄製儲存到商務用 OneDrive 和 SharePoint，即使他們已將其小組會議原則變更為 [ **串流**]。 我們建議客戶將此功能放在這個日期之前，讓他們能夠控制發行的時間。 我們已更新此排程，提供教育客戶完成進行中的學期的能力。 |

> [!Note]
> 我們建議企業與教育客戶在您的組織中更容易控制變更，只要您熟悉變更，就可以選擇 [不是等]。

Microsoft 團隊有一個儲存會議錄製的新方法。 作為從傳統 Microsoft Stream 轉換到 [新串流](https://docs.microsoft.com/stream/streamnew/new-stream)的第一個階段，此方法會將錄製儲存在 microsoft 365 的商務用 OneDrive 和 SharePoint 中，並提供許多好處。

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

> [!Note]
> [會議錄製] 選項是 [小組原則] 層級的設定。 下列範例顯示如何設定全域原則。 請務必針對您指派給使用者的原則或原則，設定 [會議錄製] 選項。
> 團隊會議原則變更需要一段時間才能傳播。 在幾個小時後再次查看，然後登出並再次登入。

1. 安裝商務用 Skype Online PowerShell。
**注意**：商務用 Skype Online 連接器目前是最新團隊 PowerShell 模組的一部分。 如果您使用的是最新的團隊 PowerShell 公開發行，就不需要安裝商務用 Skype Online 連接器。 請參閱 [使用 PowerShell 管理商務用 Skype Online](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)。

    a. 下載 [商務用 Skype Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)。

    b. 依照提示進行安裝。

    c-clip. 重新開機您的電腦。

2. 以系統管理員身分啟動 PowerShell

3. 匯入 SkypeOnline 連接器，並以團隊管理員身分登入。

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. 使用 [ [設定 csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps&preserve-view=true) ] 將 [團隊會議原則] 設定為從資料流程儲存轉換為商務用 OneDrive 和 SharePoint。

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>退出商務用 OneDrive 和 SharePoint 以繼續使用資料流程

即使原則將它設定為 [ **資料流程**]，也可能不會設定。 通常，如果原則沒有設定，則預設設定為 [ **資料流程**]。 不過，如果您想要選擇不使用 SharePoint 或商務用 OneDrive，您必須將原則重設為 [ **資料流程** ]，以確保它是預設值。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>許可權或以角色為基礎的存取權

|會議類型                               | 按一下 [記錄] 的人員| 錄製的土地在哪裡？                               |誰有存取權？ R/W、R 或共用                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|與內部合作夥伴的1:1 通話             |呼叫                 |來電者的商務用 OneDrive 帳戶                        |來電者為擁有者，且擁有完整許可權。 <br /><br />被呼叫方 (if) 中都有唯讀存取權。 沒有共用存取權。 <br /><br /> 如果在不同的租使用者) 中沒有存取權，則被呼叫者 (。 來電者必須將它共用給被叫方。|
|與內部合作夥伴的1:1 通話             |方                 |被呼叫者的商務用 OneDrive 帳戶                        |被呼叫者為擁有者，且擁有完整許可權。 <br /><br />在同一租使用者中，來電者 (if 擁有唯讀存取權。 沒有共用存取權。 <br /><br />如果在不同的租使用者) 沒有存取權，則呼叫者 (。 被呼叫方必須將它共用給被呼叫方。|
|使用外部通話的1:1 通話             |呼叫                 |來電者的商務用 OneDrive 帳戶                        |來電者為擁有者，且擁有完整許可權。<br /> <br />被呼叫者沒有存取權。 來電者必須將它共用給被叫方。|
|使用外部通話的1:1 通話             |方                 |被呼叫者的商務用 OneDrive 帳戶                        |被呼叫者為擁有者，且擁有完整許可權。<br /><br />來電者沒有存取權。 被叫方必須將它共用給來電者。|
|群組通話                                 |通話的任何成員 |按一下記錄的商務用 OneDrive 帳戶的成員  |按一下 [記錄] 的成員具有 [完全] 許可權。 <br /><br /> 來自相同租使用者的其他成員具有 [讀取] 許可權。 <br /><br /> 來自不同租使用者的其他成員沒有許可權。|
|即席/排程會議                    |召集人              |召集人的商務用 OneDrive 帳戶                     |召集人擁有錄製的完整許可權。 <br /><br /> 所有其他會議成員都有 [讀取] 存取權。|
|即席/排程會議                    |其他會議成員   |按一下 [記錄] 的成員                                  |按一下 [記錄] 的成員擁有錄製的完整許可權。 <br /><br />召集人擁有編輯許可權，而且可以共用。<br /><br /> 所有其他成員都有讀取存取權。|
|與外部使用者進行即席/排程的會議|召集人              |召集人的商務用 OneDrive 帳戶                     |召集人擁有錄製的完整許可權。<br /> <br /> 與召集人相同租使用者的所有其他會議成員都有讀取權限。 <br /><br /> 所有其他的外部成員都沒有存取權，而且召集人必須將它共用給他們。|
|與外部使用者進行即席/排程的會議|其他會議成員   |按一下 [記錄] 的成員                                  |按一下 [記錄] 的成員擁有錄製的完整許可權。 召集人擁有編輯許可權，而且可以共用。 <br /><br /> 與召集人相同租使用者的所有其他會議成員都有讀取權限。 <br /><br />所有其他的外部成員都沒有存取權，而且召集人必須將它共用給他們。|
|頻道會議                            |頻道成員         |團隊在該頻道中的 SharePoint 位置                   |按一下 [記錄] 的成員擁有錄製的編輯權力。 <br /> <br />每個其他成員的許可權都是依據頻道 SharePoint 許可權所組成。|

## <a name="frequently-asked-questions"></a>常見問題集

**會議錄製將儲存在哪裡？**

- 對於非頻道會議，錄製會儲存在屬於開始會議錄製之 **Recordings** 人員之商務用 OneDrive 的最上層的資料夾中。 範例

  <i>錄影機的商務</i> / 用 OneDrive **錄製**

- 對於頻道會議，錄製會儲存在名為 [ **錄製**] 資料夾的 [小組網站] 文件庫中。 範例

  <i>團隊名稱-頻道名稱</i> /**檔** /**錄製**

**我要如何處理來自離職員工的錄製？**

因為影片與商務用 OneDrive 和 SharePoint 中的任何其他檔案一樣，所以在員工離職之後，處理擁有權及保留期將遵循正常的 [商務用 OneDrive 和 SharePoint 程式]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)。

**誰有權查看會議錄製？**

- 如果是非頻道會議，除了外部使用者以外的所有會議受邀者，都將自動取得個人共用的連結。 外部使用者必須透過會議召集人或開始會議錄製的人員，將其明確新增至共用清單中。

- 對於頻道會議，許可權是從頻道中的 [擁有人] 和 [成員] 清單繼承而來。

**我要如何管理腳本？**

如果客戶加入宣告此預覽，小組會議錄製將不會提供隱藏式輔助字幕，且已遷移至商務用 OneDrive 和 SharePoint。我們正致力於將隱藏式輔助字幕從英文新增至2020年10月的會議錄製。

小組會議錄製會提供隱藏式輔助字幕，供已自願加入在[小組雲端錄製](cloud-recording.md)中描述的客戶使用。

[標題] 可協助為所有功能的檢視器建立包含內容。 在擁有者中，您可以隱藏標題，但除非您刪除小組中的標題，否則仍可在團隊中使用這些記錄。 瞭解 [如何開啟或關閉會議錄製](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

錄製會議時，小組會議錄製支援的60天是隱藏式輔助字幕。

如果將小組會議錄製從其在商務用 OneDrive 或 SharePoint 上的原始位置移動或複製，就不會完全支援隱藏式輔助字幕。

**我的儲存空間配額會受到影響？**

小組會議會在商務用 OneDrive 和 SharePoint 中即時錄製檔案，並包含在這些服務的配額中。 請參閱 [SharePoint 配額](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) 和 [商務用 OneDrive 配額](https://docs.microsoft.com/onedrive/set-default-storage-space)。

使用 [商務用 OneDrive 來](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) 取得更多儲存空間，與使用 SharePoint 的資料流程及更 fungible 儲存空間進行比較。

**如何播放團隊會議錄製？**

您的影片將會在商務用 OneDrive 或 SharePoint 的影片播放機上播放，視您存取該檔案的位置而定。

**如果您打算 deprecating 新增至串流，現有的影片會持續保持不變嗎？**

在不久的將來，不會棄用作為平臺的資料流程。 目前在資料流程中的影片會一直留在這裡，直到我們開始進行遷移為止。 遷移時，這些影片也會遷移到商務用 OneDrive 或 SharePoint。 若要瞭解詳細資訊，請參閱 [這裡](https://docs.microsoft.com/stream/streamnew/classic-migration) 。

**如何套用保留標籤？**

瞭解 [如何自動套用保留標籤](https://docs.microsoft.com/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)。

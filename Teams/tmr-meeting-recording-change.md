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
description: 瞭解如何在 Microsoft Teams 中從 Stream 切換到商務用 OneDrive 和 SharePoint 會議錄製儲存空間。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0431b7ebd385f2ad17d659e238f54b4ebb1ab20a
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569089"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>使用商務用 OneDrive 和 SharePoint 或 Stream 進行會議錄製

> [!Note]
> 從使用 Microsoft Stream 變更為商務用 OneDrive，以及將 Microsoft SharePoint 用於會議錄製，將採用階段性方法。

|<div style="width:290px">日期&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |事件&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|2020 年 10 月 5 日<br> <br>*(完成)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| 您可以啟用 Teams 會議政策，將會議錄製儲存到商務用 OneDrive 和 SharePoint，而不是將 Microsoft Stream (傳統) |
|自 2021 年 1 月 7 日開始推出<br> <br>*(完成)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|所有新的 Teams 會議錄製都會儲存到商務用 OneDrive 和 SharePoint，除非您修改組織的 Teams 會議政策，並明確地將其設定為 Stream 來延遲這項 **變更**。 將政策報告視為 Stream 並不夠。 您必須明確地將策略值設定為 **Stream。**|
|自 2021 年 1 月 11 日開始推出<br> <br>*(完成)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**僅 GCC**<br> 雖然 GCC 客戶可以從 10 月 5 日起退出宣告，但您將無法加入宣告。 這項功能將于 2021 年 1 月 11 日起推出給所有 GCC 客戶，除非您退出宣告。<br>  <br>從 2021 年 1 月 11 日開始，所有 GCC 客戶的新 Teams 會議錄製都會儲存到商務用 OneDrive 和 SharePoint，除非您修改組織的 Teams 會議政策，並明確將其設定為 Stream 來延遲這項變更。 <br><br>如果您退出宣告，但準備好開啟此功能，您可以明確地將 Teams 會議政策設定為商務用 **OneDrive。** |
|自 2021 年 3 月 1 日推出 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC-High 和 DoD 僅**<br> 客戶現在可以第一次在 Microsoft Teams 中啟用雲端會議錄製。 這些錄製內容預設會儲存在 OneDrive 和 SharePoint 上播放。 |
|從 2021 年 7 月 7 日開始逐步推出 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**所有客戶 (企業版、教育版和 GCC)**<br>新的會議錄製內容無法儲存到 Microsoft Stream (傳統) ;所有客戶都會自動將會議錄製儲存到商務用 OneDrive 和 **SharePoint，** 即使他們將 Teams 會議政策變更為 Stream。<br><br> 我們建議客戶在此日期之前推出這項功能，以便控制發行時間。 |

> [!Note]
> 我們建議企業版和教育版客戶，為了進一控制貴組織的變更，只要熟悉變更，就加入宣告，而不是等待變更發生。

Microsoft Teams 有一種新方法可以保存會議錄製內容。 做為從傳統 Microsoft Stream 轉換到新[](https://docs.microsoft.com/stream/streamnew/new-stream)Stream 的第一階段，這個方法將錄製儲存在 Microsoft 365 中的商務用 Microsoft OneDrive 和 SharePoint 上，並提供許多優點。

使用商務用 OneDrive 和 SharePoint 儲存錄製的好處包括：

- 適用于 Teams 會議錄製的保留 (S+C E5)  (自動執行功能標籤) 
- 商務用 OneDrive 和 SharePoint 資訊管理的好處
- 輕鬆設定許可權和共用
- 與來賓共用錄製 (外部) 只以明確共用
- 要求存取流程
- 供應商務用 OneDrive 和 SharePoint 共用連結
- 更快速地提供會議錄製
- **前往當地租** 使用者支援
- 多重地理位置支援 – 錄製會儲存在該使用者的特定地區
- 將您自己的金鑰 (BYOK) 支援

有一些限制需要考慮：

- 將會有僅提供英文的隱藏式字幕，而且您可以關閉/開啟標題。
- 您 *一開始無法* 查看、編輯及搜尋完整的文字記錄 (，不過我們正努力在) 。
- 您無法編輯文字記錄，但您可以關閉/開啟標題。
- 您可以控制與誰共用錄製內容，但無法封鎖具有共用存取權的人無法下載錄製內容。
- 錄製完成後，您不會收到電子郵件，但錄製完成之後，就會顯示在會議聊天中。 這會比之前在 Stream 中更快發生

請觀看「會議錄製」以瞭解更多資訊。

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>設定商務用 OneDrive 和 SharePoint 的會議錄製選項

會議錄製選項是 Teams 策略層級的設定。 下列範例顯示如何設定全域原則。 請確定您為指派給使用者的一或多個政策設定了會議錄製選項。

> [!Note]
> Teams 會議政策變更需要一段時間才能傳播。 設定數小時之後再回來查看，然後登出並再次重新登錄。

1. 安裝 Teams PowerShell PowerShell。

   > [!NOTE]
   > 商務用 Skype Online Connector 目前是最新 Teams PowerShell 模組的一部分。 如果您使用的是最新的 Teams PowerShell 公開發行，則不需要安裝商務用 Skype Online Connector。 請參閱[使用 PowerShell 管理商務用 Skype Online。](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)

1. 以系統管理員的名啟動 PowerShell。

2. 安裝 [Teams PowerShell 模組](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。

3. 將 MicrosoftTeams 模組導入並以 Teams 系統管理員的認證登登。


```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

4. 使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) 設定 Teams 會議策略，以從 Stream 儲存空間轉換到商務用 OneDrive 和 SharePoint。

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> 如果您的部分使用者已指派每一位或每個使用者的策略，如果您希望他們同時將會議錄製儲存在商務用 OneDrive 和 SharePoint 中，就必須在此策略上設定此設定。 詳細資訊請參閱在 [Teams 中管理會議政策](meeting-policies-in-teams.md)。

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>退出宣告商務用 OneDrive 和 SharePoint 以繼續使用 Stream

即使有一個策略指出已設定為 **Stream，** 它可能不會設定。 一般來說，如果未設定該策略，則預設設定為 **Stream。** 不過，在這個新的變更中，如果您想要退出宣告使用 SharePoint 或商務用 OneDrive，則必須將策略重設為 **Stream，** 以確保 **Stream** 為預設值。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>許可權或角色型存取

> [!Note]
> 我們建議您共用 Teams 會議錄製時，收件者必須是登入使用者。 當您在 **SharePoint 檔案或)** 中共用檔案時，請選取貴組織 (中的人員 [選項](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US)。 外部共用並非針對大型檔案或大量檔案的發佈所設計。 為了避免詐騙和濫用案例，當您與外部使用者共用大量資料時，可能會遇到問題。

|會議類型                               | 誰按一下 [記錄？| 錄製內容會在哪裡？                               |誰可以存取？ R/W、R 或共用                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|與內部各方進行一對一通話             |來電                 |來電者的商務用 OneDrive 帳戶                        |來電者為擁有者且擁有完整許可權。 <br /><br />如果 (租使用者中具有唯讀) ，受通話者會進行此工作。 沒有共用存取權。 <br /><br /> 如果在不同 (租使用者中，受) 者無法存取。 來電者必須分享給受通話者。|
|與內部各方進行一對一通話             |受通話者                 |受通話者商務用 OneDrive 帳戶                        |受通話者為擁有者，且擁有完整許可權。 <br /><br />如果 (租使用者中具有唯讀存取權，來電者會進行呼叫。 沒有共用存取權。 <br /><br />如果 (租使用者，來電) 無法存取。 受通話者必須分享給來電者。|
|使用外部通話進行一對一通話             |來電                 |來電者的商務用 OneDrive 帳戶                        |來電者為擁有者且擁有完整許可權。<br /> <br />受通話者無法存取。 來電者必須分享給受通話者。|
|使用外部通話進行一對一通話             |受通話者                 |受通話者商務用 OneDrive 帳戶                        |受通話者為擁有者，且擁有完整許可權。<br /><br />來電者無法存取。 受通話者必須分享給來電者。|
|群組通話                                 |通話的任何成員 |按一下記錄商務用 OneDrive 帳戶的群組成員  |按一下記錄的成員擁有完整許可權。 <br /><br /> 同一租使用者的其他 fr 具有讀取權限。 <br /><br /> 不同租使用者的其他群組成員沒有許可權。|
|Adhoc/Scheduled meeting                    |召集人              |召集人的商務用 OneDrive 帳戶                     |召集人擁有錄製的完整許可權。 <br /><br /> 會議的其他所有成員都有讀取存取權。|
|Adhoc/Scheduled meeting                    |其他會議成員   |按一下記錄的會議成員                                  |按一下錄製的成員擁有錄製的完整許可權。 <br /><br />召集人具有編輯許可權，而且可以共用。<br /><br /> 所有其他會議成員都有讀取存取權。|
|與外部使用者的 Adhoc/Scheduled 會議|召集人              |召集人的商務用 OneDrive 帳戶                     |召集人擁有錄製的完整許可權。<br /> <br /> 會議的其他所有成員，都來自與會議召集人相同的租使用者，具有讀取存取權。 <br /><br /> 所有其他外部成員沒有存取權，而召集人必須將其共用給他們。|
|與外部使用者的 Adhoc/Scheduled 會議|其他會議成員   |按一下記錄的成員                                  |按一下錄製的成員擁有錄製的完整許可權。 召集人具有編輯許可權，而且可以共用。 <br /><br /> 會議的其他所有成員，都來自與會議召集人相同的租使用者，具有讀取存取權。 <br /><br />所有其他外部成員沒有存取權，而召集人必須將其共用給他們。|
|頻道會議                            |頻道成員         |該頻道的 Teams SharePoint 位置                   |按一下錄製的成員擁有錄製的編輯許可權。 <br /> <br />每個其他成員的許可權都是以 Channel SharePoint 許可權為基礎。|

## <a name="frequently-asked-questions"></a>常見問題集

**會議錄製內容會儲存在哪裡？**

- 針對非頻道會議，錄製內容會儲存在位於商務用 OneDrive最上方層級的名為[錄製」的資料夾，該資料夾屬於開始會議錄製的人。 範例：

  <i>錄製器的商務用 OneDrive</i> /**錄製**

- 針對頻道會議，錄製內容會儲存在 Teams 網站文件庫中名為錄製 **的資料夾**。 範例：

  <i>Teams 名稱 - 頻道名稱</i> /**檔** /**錄製**

**當串流檔案 (例如錄製) 儲存在 SharePoint/OneDrive 中時，要如何決定檔案的儲存位置？系統管理員是否能夠變更其位置？**

根據預設，所有錄製檔案都會進入選取記錄之使用者的 OneDrive **帳戶**。 針對頻道會議，錄製內容一定會前往頻道的 SharePoint 網站。 系統管理員無法變更錄製的儲存位置。

**如何處理前員工的錄製？**

由於影片和商務用 OneDrive 和 SharePoint 中任何其他檔案一樣，因此員工離職後處理擁有權和保留會遵循一般商務用 OneDrive 和 [SharePoint 程式]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)。

**誰有權查看會議錄製內容？**

- 對於非頻道會議，除了外部使用者之外，所有會議受邀者都會自動取得個人共用的連結。 外部使用者必須由會議召集人或開始會議錄製的人明確新加入共用清單。

- 對於頻道會議，許可權會繼承自頻道中的擁有者和成員清單。

**如何管理文字記錄？**

加入宣告此預覽的客戶，其 Teams 會議錄製中不會提供移入商務用 OneDrive 和 SharePoint 的隱藏式字幕。我們正努力在 Q4 CY2020 的會議錄製中新增標題 ，從英文隱藏式字幕開始。

在 Teams 會議錄製中，將可針對選擇允許字幕的客戶使用隱藏式字幕，如 Teams 雲端錄製 [中所述](cloud-recording.md)。

標題可協助為所有能力的人建立含納性的內容。 做為擁有者，您可以隱藏標題，但除非您從 Teams 刪除標題，否則 Teams 上仍然可以使用文字記錄。 瞭解如何 [開啟或關閉會議錄製](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)。

錄製會議後 60 天內，Teams 會議錄製都支援隱藏式字幕。

如果 Teams 會議錄製從商務用 OneDrive 或 SharePoint 的原始位置移動或複製，則不支援隱藏式字幕。

**我的儲存配額會如何受到影響？**

Teams 會議錄製檔案會即時在商務用 OneDrive 和 SharePoint 中，並包含在這些服務的配額中。 請參閱 [SharePoint 配額](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) 和 [商務用 OneDrive 配額](https://docs.microsoft.com/onedrive/set-default-storage-space)。

相較于 Stream，您可以取得更多商務用 [OneDrive](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) 的儲存空間，以及 SharePoint 的更多可操作儲存空間。

**如何播放 Teams 會議錄製內容？**

視您存取檔案的位置，視音訊會播放于商務用 OneDrive 或 SharePoint 的影片播放機上。

**如果您打算要取消新增到 Stream，現有的影片會維持現有並維持多久？**

在近期內，串流作為平臺不會被使用。 目前 Stream 中的影片會留在這裡，直到我們開始移移。 移改之後，這些影片也會移至商務用 OneDrive 或 SharePoint。 請查看 [Stream 傳統移移](https://docs.microsoft.com/stream/streamnew/classic-migration) 以瞭解更多資訊。

**如何貼上保留標籤？**

瞭解如何 [自動貼上保留標籤](https://docs.microsoft.com/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)。

**如何在 Microsoft Teams 中指派規則給使用者，以及優先處理哪些政策？**

查看[哪一個優先？](https://docs.microsoft.com/MicrosoftTeams/assign-policies#which-policy-takes-precedence)

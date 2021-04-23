---
title: 使用商務用 OneDrive 和 SharePoint 進行會議錄製
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
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
ms.openlocfilehash: d0de88cd3295e1e04681cf6ff63bccab80e4b4a8
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948659"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>使用商務用 OneDrive 和 SharePoint 或 Stream 進行會議錄製

> [!Note]
> 從使用 Microsoft Stream 到商務用 OneDrive 和 Microsoft SharePoint 進行會議錄製的變更，將會是階段性的做法。

|<div style="width:290px">日期&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |事件&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|2020 年 10 月 5 日<br> *(完成)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| 您可以啟用 Teams 會議政策，將會議錄製儲存到商務用 OneDrive 和 SharePoint，而不是 Microsoft Stream (傳統) |
|從 2021 年 1 月 7 日開始推出<br> *(完成)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|所有新的 Teams 會議錄製內容都會儲存到商務用 OneDrive 和 SharePoint，除非您修改組織的 Teams 會議政策，並明確將其設定為 Stream 來延遲這項 **變更**。 將策略報告視為 Stream 是不夠的。 您必須明確地將策略值設定為 **Stream。**|
|從 2021 年 1 月 11 日開始推出<br> *(完成)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**僅適用于 GCC**<br> 雖然 GCC 客戶可以從 10 月 5 日起退出宣告，但您將無法加入宣告。 這項功能將于 2021 年 1 月 11 日起推出給所有 GCC 客戶，除非您退出宣告。<br>  <br>自 2021 年 1 月 11 日起，所有 GCC 客戶的新 Teams 會議錄製內容都會儲存到商務用 OneDrive 和 SharePoint，除非您修改組織的 Teams 會議政策並明確將其設定為 Stream 來延遲這項 **變更。** <br><br>如果您已經退出宣告，但已準備好開啟這項功能，您可以明確地將 Teams 會議政策設定為商務用 **OneDrive** 來開啟此功能。 |
|自 2021 年 3 月 1 日推出<br> *(完成)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC-High 和 DoD 僅**<br> 客戶現在可以第一次在 Microsoft Teams 中啟用雲端會議錄製。 根據預設，這些錄製內容會儲存在 OneDrive 和 SharePoint 上並播放。 |
|從 2021 年 7 月 7 日開始逐步推出 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**所有客戶 (企業版、教育版和 GCC)**<br>無法將新的會議錄製儲存到 Microsoft Stream (傳統) ;所有客戶都會自動將會議錄製儲存到商務用 OneDrive 和 SharePoint，即使他們已經將 Teams 會議政策變更為 Stream。<br><br> 我們建議客戶，為了更好的控制貴組織的變更，只要您習慣變更，就加入宣告，而不是等待變更發生。 |

Microsoft Teams 有一種保存會議錄製的新方法。 這是從傳統 Microsoft Stream 轉換到新 Stream[](/stream/streamnew/new-stream)的第一個階段，此方法會儲存 Microsoft 365 商務用 Microsoft OneDrive 和 SharePoint 上的錄製內容，並提供許多優點。

> [!NOTE]
> 如果 Teams 會議錄製無法成功上傳到 OneDrive/SharePoint，錄製內容會暫時儲存至 Azure Media Services (AMS) 。 儲存于 AMS 後，系統不會嘗試嘗試將錄製內容自動上傳到 OneDrive/SharePoint 或 Stream。

儲存在 AMS 中的會議錄製可在自動刪除前 21 天使用。 如果需要保留副本，使用者可以從 AMS 下載影片。

使用商務用 OneDrive 和 SharePoint 儲存錄製的權益包括：

- 在 S+C E5 (S+C E5)  (記錄 Teams 會議錄製的保留) 
- 受益于商務用 OneDrive 和 SharePoint 資訊監管
- 輕鬆設定許可權和共用
- 僅以明確共用 (外部) 共用錄製內容
- 要求存取流程
- 供應商務用 OneDrive 和 SharePoint 共用連結
- 會議錄製速度較快
- **前往當地** 租使用者支援
- 多地理位置支援 – 錄製會儲存在該使用者特定的區域
- 將您自己的金鑰 (BYOK) 支援

查看今天可用的 [功能的完整清單，以及一段時間後預期的結果](https://docs.microsoft.com/stream/streamnew/features-new-version-stream)。 

請觀看「Microsoft Teams 會議錄製的新增功能」以瞭解更多資訊。

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>設定商務用 OneDrive 和 SharePoint 的會議錄製選項

會議錄製選項是 Teams 策略層級的設定。 下列範例顯示如何設定全域原則。 請確定您為指派給使用者的政策或政策設定會議錄製選項。

> [!Note]
> Teams 會議策略變更需要一段時間才能傳播。 設定數小時之後再回來查看，然後登出並再次登錄 Teams 桌面應用程式，或重新開機電腦。

1. 安裝 Teams PowerShell PowerShell。

   > [!NOTE]
   > 商務用 Skype Online Connector 目前是 Teams PowerShell 最新模組的一部分。 如果您使用的是最新的 Teams PowerShell 公開發行，則不需要安裝商務用 Skype Online 連接器。 請參閱 [使用 PowerShell 管理商務](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide)用 Skype Online 。

2. 以系統管理員角色啟動 PowerShell。

3. 安裝 [Teams PowerShell 模組](./teams-powershell-install.md)。

4. 輸入 MicrosoftTeams 模組，然後以 Teams 系統管理員的登錄。


   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

5. 使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) 設定 Teams 會議策略，以從 Stream 儲存空間轉換為商務用 OneDrive 和 SharePoint。

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> 如果您的部分使用者已指派每個召集人或每個使用者的政策，如果您希望他們同時將會議錄製儲存在商務用 OneDrive 和 SharePoint 中，您必須在此策略上設定此設定。 詳細資訊，請參閱在 [Teams 中管理會議策略](meeting-policies-in-teams.md)。

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>退出宣告商務用 OneDrive 和 SharePoint 以繼續使用 Stream

即使有一個策略指出已設定為 **Stream，** 它可能不會設定。 一般來說，如果未設定該策略，則預設設定為 **Stream**。 不過，有了這個新變更，如果您想要退出宣告使用 SharePoint 或商務用 OneDrive，則必須將策略重設為 **Stream，** 以確保 **Stream** 為預設值。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>許可權或角色式存取

> [!Note]
> 我們建議您共用 Teams 會議錄製時，收件者必須是登入使用者。 當您在 **SharePoint 檔案 (** 或資料夾中) 檔案時，請選取您組織中的人員 [選項](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US)。 外部共用並非專為發佈大型檔案或大量檔案所設計。 為了防止詐騙和濫用案例，當您與外部使用者共用大量資料時，可能會遇到問題。

|會議類型                               | 誰按一下 [記錄？| 錄製位置在哪裡？                               |誰可以存取？ R/W、R 或共用                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|與內部各方進行 1：1 通話             |來電                 |來電者的商務用 OneDrive 帳戶                        |來電者為擁有者，且擁有完整許可權。 <br /><br />如果 (同一個租使用者) 唯讀存取權，受叫) 會進行通話。 沒有共用存取權。 <br /><br /> 如果不同的 (使用者沒有存取權，) 通話者會進行通話。 來電者必須共用給通話者。|
|與內部各方進行 1：1 通話             |通話者                 |Callee 的商務用 OneDrive 帳戶                        |Callee 是擁有者，並擁有完整權利。 <br /><br />如果 (租使用者具有唯讀存取權，則來電者會進行通話。 沒有共用存取權。 <br /><br />如果 (租使用者中，) 無法存取來電。 通話者必須共用給來電者。|
|使用外部通話進行 1：1 通話             |來電                 |來電者的商務用 OneDrive 帳戶                        |來電者為擁有者，且擁有完整許可權。<br /> <br />通話者無法存取。 來電者必須共用給通話者。|
|使用外部通話進行 1：1 通話             |通話者                 |Callee 的商務用 OneDrive 帳戶                        |受叫者為擁有者，並擁有完整權利。<br /><br />來電者無法存取。 通話者必須共用給來電者。|
|群組通話                                 |通話的任何成員 |按一下 Record 的商務用 OneDrive 帳戶的群組成員  |按一下 Record 的成員擁有完整許可權。 <br /><br /> 同一租使用者的其他 fr 具有讀取權限。 <br /><br /> 不同租使用者的其他群組成員沒有許可權。|
|Adhoc/Scheduled 會議                    |召集人              |召集人的商務用 OneDrive 帳戶                     |召集人擁有錄製的完整許可權。 <br /><br /> 會議中的所有其他成員都有讀取存取權。|
|Adhoc/Scheduled 會議                    |其他會議成員   |按一下 [記錄》 的會議成員                                  |按一下 [錄製> 的成員擁有錄製的完整許可權。 <br /><br />召集人具有編輯許可權，可以共用。<br /><br /> 所有其他會議成員都有讀取存取權。|
|與外部使用者的 Adhoc/Scheduled 會議|召集人              |召集人的商務用 OneDrive 帳戶                     |召集人擁有錄製的完整許可權。<br /> <br /> 會議的所有其他成員與召集人來自同一個租使用者，都有讀取存取權。 <br /><br /> 所有其他外部成員都無存取權，且召集人必須將其共用給他們。|
|與外部使用者的 Adhoc/Scheduled 會議|其他會議成員   |按一下 [記錄》 的成員                                  |按一下 [錄製> 的成員擁有錄製的完整許可權。 召集人具有編輯許可權，可以共用。 <br /><br /> 會議的所有其他成員與召集人來自同一個租使用者，都有讀取存取權。 <br /><br />所有其他外部成員都無存取權，且召集人必須將其共用給他們。|
|頻道會議                            |頻道成員         |該頻道的 Teams SharePoint 位置                   |按一下 [錄製> 的成員擁有錄製的編輯許可權。 <br /> <br />每個其他成員的許可權都是以 Channel SharePoint 許可權為基礎。|

## <a name="frequently-asked-questions"></a>常見問題集

**會議錄製內容會儲存在何處？**

- 對於非頻道會議，錄製會儲存在名為 [錄製的錄製>資料夾中，該資料夾位於商務用 OneDrive 的頂層，屬於開始會議錄製的人。 範例：

  <i>錄製器的商務用</i> / OneDrive **錄製**

- 針對頻道會議，錄製會儲存在 Teams 網站文件庫中的名為錄製 **的資料夾**。 範例：

  <i>Teams 名稱 - 頻道名稱</i> /**檔** /**錄製**

**當 [串流 (例如錄製) 儲存在 SharePoint/OneDrive 中時，如何決定它們的位置？系統管理員是否能夠變更其位置？**

根據預設，所有錄製檔案都會前往選取 [錄製> 的使用者的 OneDrive **帳戶**。 對於頻道會議，錄製內容一定會前往頻道的 SharePoint 網站。 系統管理員無法變更錄製的儲存位置。

**如何處理來自前員工的錄製？**

由於影片與商務用 OneDrive 和 SharePoint 中任何其他檔案一樣，因此員工離職後處理擁有權和保留會遵循一般商務用 OneDrive 和 [SharePoint 程式]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)。

**誰有權查看會議錄製？**

- 對於非通道會議，除了外部使用者之外，所有會議受邀者都會自動取得個人共用連結。 會議召集人或會議錄製者必須明確將外部使用者新加入共用清單。

- 對於頻道會議，許可權會從頻道中的擁有者和成員清單中繼承。

> [!NOTE]
> 錄製完成時，您不會收到電子郵件，但錄製完成後，該錄製內容會顯示在會議聊天中。 這會比先前在 Stream 中更快發生。
> 您可以控制與誰共用錄製內容，但無法封鎖具有共用存取權的人下載錄製內容。  

**如何管理標題？**

只有當使用者在錄製時已開啟轉錄功能時，Teams 會議錄製的隱藏式字幕才能在播放期間使用。 系統管理員必須 [透過策略]( https://docs.microsoft.com/microsoftteams/cloud-recording#turn-on-or-turn-off-recording-transcription) 開啟錄製文字記錄，以確保其使用者有使用文字記錄錄製會議的選項。

標題可協助建立包含所有功能之檢視器的內容。 作為擁有者，您可以在會議錄製中隱藏標題，不過會議記錄仍然可在 Teams 上使用，除非您在 Teams 中將其刪除。 

從錄製會議起 60 天內，Teams 會議錄製支援隱藏式字幕。

如果 Teams 會議錄製從商務用 OneDrive 或 SharePoint 的原始位置移動或複製，則不支援隱藏式字幕。

> [!NOTE]
> GCC (中尚未提供會議文字記錄時，將會有僅提供英文的隱藏式) 。

**我的儲存空間配額會如何影響？**

Teams 會議錄製檔案會即時在商務用 OneDrive 和 SharePoint 中，並包含在這些服務的配額中。 請參閱[SharePoint 配額](/sharepoint/sites/plan-site-maintenance-and-management#quotas)[和商務用 OneDrive 配額](/onedrive/set-default-storage-space)。

與 Stream 相比， [商務用 OneDrive](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) 的儲存空間更多，而 SharePoint 的儲存空間也更多。

**如何播放 Teams 會議錄製？**

視您存取檔案的位置，您的視音訊會于商務用 OneDrive 或 SharePoint 的視音訊播放機上播放。

**如果您打算將新增到 Stream 中，現有的影片會維持目前和多久？**

在近期內不會將 Stream 當做平臺被棄用。 目前住在 Stream 中的影片會一直留在這裡，直到我們開始移移。 移移之後，這些影片也會移至商務用 OneDrive 或 SharePoint。 請查看 [Stream 傳統移移](/stream/streamnew/classic-migration) 以瞭解更多資訊。

**如何貼上保留標籤？**

請參閱 [如何自動貼上保留標籤](/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)。

**如何在 Microsoft Teams 中指派策略給使用者，以及優先使用哪些政策？**

請參閱 [哪個策略優先？](./assign-policies.md#which-policy-takes-precedence)。

**如果使用者沒有商務用 OneDrive 或 SharePoint，錄製會在哪裡？**

錄製內容會位於我們的暫時儲存位置，該位置將保存 21 天。 在此期間，召集人必須下載錄製內容。 如果未在 21 天內下載，錄製內容會被刪除。


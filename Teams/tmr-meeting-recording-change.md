---
title: 使用商務用 OneDrive SharePoint錄製
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中從 Stream 切換至商務用 OneDrive 和 SharePoint 會議錄製儲存空間。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d8f04eebbd1123bf753c221e49a2b523d91ff43
ms.sourcegitcommit: cf2f96dbd485ac4cc822c5a591ccce6b47f12cc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2021
ms.locfileid: "59456393"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>使用商務用 OneDrive或SharePoint串流進行會議錄製

> [!NOTE]
> 從傳統Teams到 OneDrive SharePoint (ODSP) 會議錄製的儲存變更已經完成，截至 2021 年 8 月 30 日。 所有錄製現在都儲存在 ODSP 中。 此變更會取代錄製StorageMode政策，而修改 PowerShell 中的設定將不再有任何影響。

|日期&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|事件&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|2020 年 10 月 5 日<br> *(已完成)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| 您可以啟用會議Teams將會議錄製儲存為商務用 OneDrive SharePoint而非Microsoft Stream (傳統版) |
|2021 年 1 月 7 日開始推出<br> *(已完成)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Teams 除非您修改組織的 Teams 會議Teams，並明確將其設定為 Stream，否則所有新的會議錄製內容都會儲存至 商務用 OneDrive 和 **SharePoint。** 僅看到原則報告為 Stream 是不够的。 您需要明確地將原則值設定為 **Stream**。|
|2021 年 1 月 11 日開始推出<br> *(已完成)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**僅 GCC**<br> 雖然 GCC 客戶可以從 10 月 5 日開始選擇退出，但您不能選擇加入。 此功能將從 2021 年 1月 11 日開始向所有 GCC 客戶推出，除非您已選擇退出。<br>  <br>自 2021 年 1 月 11 日起，GCC 客戶的所有新 Teams 會議錄製都會儲存至 商務用 OneDrive 和 SharePoint，除非您修改組織的 Teams 會議政策並明確將其設定為 Stream 來延遲這項變更。 <br><br>如果您已選擇退出，但準備好啟用此功能，則可以透過將 Teams 會議原則明確設定為 **商務用 OneDrive** 來實現。 |
|2021 年 3 月 1 日開始推出<br> *(已完成)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**進 GCC-High 和 DoD**<br> 客戶現在可以在其 Microsoft Teams 中首次啟用雲端會議錄製。 這些錄製內容預設會儲存並OneDrive SharePoint播放。 |
|從 2021 年 8 月 16 日開始逐步推出<br> *(已完成)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**所有客戶 (企業、教育和 GCC)**<br>無法將新的會議錄製儲存到Microsoft Stream (傳統版) ;所有客戶都會自動將會議錄製儲存到商務用 OneDrive SharePoint，即使他們已經將會議Teams變更為 Stream。<br><br> 我們建議客戶，在您對變更感到滿意選擇加入，而非等待變更生效，以便更好地控制組織中的變更。 |

Microsoft Teams 有用於儲存會議錄製的新方法。 這是從傳統 Microsoft Stream 轉換到新 Stream[](/stream/streamnew/new-stream)的第一個階段，此方法會儲存 Microsoft OneDrive 商務用和 SharePoint Microsoft 365 中的錄製內容，並提供許多優點。

> [!NOTE]
> 如果Teams錄製無法成功上傳到 OneDrive/SharePoint，就會出現「錄製未預期結束」錯誤訊息，而錄製將會暫時儲存至 Azure 媒體服務 (AMS) 。 儲存于 AMS 後，系統不會嘗試嘗試自動將錄製上傳到 OneDrive/SharePoint串流。

儲存在 AMS 中的會議錄製内容在自動删除前可使用 21 天。 若使用者需要保留複本，可從 AMS 下載影片。

使用錄音和商務用 OneDrive SharePoint錄製的權益包括：

- Teams 會議錄製內容 (TMR) 的保留原則 (S+C E5 自動偵測標籤)
- 受益于商務用 OneDrive SharePoint管理
- 易於設定權限和共用
- 僅透過明確共用與來賓 (外部使用者) 共用錄製内容
- 要求存取流程
- 供應商務用 OneDrive SharePoint連結
- 可更快取得會議錄製内容
- **移至本地** 租用戶支援
- 多地理位置支援 – 錄製内容儲存在特定於該使用者的地區
- 攜帶您自己的金鑰 (BYOK) 支援

查看[當前可用功能以及一段時間后的預期功能](/stream/streamnew/features-new-version-stream)的完整清單。

如需詳細資訊，請觀看「Microsoft Teams 會議錄製新功能」。

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>設定會議錄製選項商務用 OneDrive SharePoint

會議錄製選項是 Teams 原則層級的設定。 下列範例顯示如何設定全域原則。 請確定為已指派給使用者的一個或多個原則設定了會議錄製選項。

> [!Note]
> Teams 會議原則變更需要一段時間來傳播。設定完成的幾小時後再返回檢查，然後登出並再次登入至 Teams 桌面版應用程式，或僅是重新啟動電腦。

1. 安裝 Teams PowerShell PowerShell。

   > [!NOTE]
   > 商務用 Skype Online 連接器目前是最新 Teams PowerShell 模組的一部分。 如果您使用的是最新的 Teams PowerShell 公開發行版本，則不需要安裝商務用 Skype Online 連接器。 請參閲[使用 PowerShell 管理商務用 Skype Online](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide)。

2. 以系統管理員身分啟動 PowerShell。

3. 安裝[Teams PowerShell 模組](./teams-powershell-install.md)。

4. 匯入 MicrosoftTeams 模組並以 Teams 系統管理員身分登入。

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

5. 使用[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)設定 Teams 會議策略，以從 Stream 儲存空間轉換商務用 OneDrive SharePoint。

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> 如果您的部分使用者已指派每個召集人或每個使用者的策略，如果您希望他們同時將會議錄製儲存在 商務用 OneDrive 和 SharePoint 中，您必須在此策略上設定此設定。 如需詳細資訊，請參閱[在 Teams 中管理會議原則](meeting-policies-in-teams.md)。

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>退出宣告 商務用 OneDrive SharePoint繼續使用 Stream

即使有一個策略指出已設定為 **Stream，** 它可能不會設定。 一般來說，如果未設定該策略，則預設設定為 **Stream**。 不過，有了這個新變更，如果您想要退出宣告使用 SharePoint 或 商務用 OneDrive，則必須將策略重設為 Stream，以確保 **Stream** 為預設值。 

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>許可權或角色式存取

> [!Note]
> 我們建議您在共用會議錄製內容時，收件者必須Teams登入使用者。 當您在共用 **檔案 (** 或資料夾中) 檔案時，請選取您組織SharePoint [中的人員選項](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US)。 外部共用並非專為發佈大型檔案或大量檔案所設計。 為了防止詐騙和濫用案例，當您與外部使用者共用大量資料時，可能會遇到問題。

|會議類型                               | 是誰按了一下 [錄製]？| 錄製內容在哪裡？                               |誰可以存取？ R/W、R 或共用                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|與內部派對進行一對一通話             |呼叫者                 |呼叫者的商務用 OneDrive 帳戶                        |呼叫者為擁有者，且擁有完整權限。 <br /><br />被呼叫者 (如果在同一個租用戶中) 擁有唯讀存取權。沒有共用存取權。 <br /><br /> 被呼叫者 (如果在其他租用戶中) 沒有存取權。 呼叫者必須將它分享給被呼叫者。|
|與內部派對進行一對一通話             |被呼叫者                 |被呼叫者的商務用 OneDrive 帳戶                        |被呼叫者為擁有者，且擁有完整權限。 <br /><br />呼叫者 (如果在同一個租用戶中) 擁有唯讀存取權。沒有共用存取權。 <br /><br />呼叫者 (如果在其他租用戶中) 沒有存取權。 被呼叫者必須將它分享給呼叫者。|
|與外部通話進行一對一通話             |呼叫者                 |呼叫者的商務用 OneDrive 帳戶                        |呼叫者為擁有者，且擁有完整權限。<br /> <br />被呼叫者沒有存取權。 呼叫者必須將它分享給被呼叫者。|
|與外部通話進行一對一通話             |被呼叫者                 |被呼叫者的商務用 OneDrive 帳戶                        |被呼叫者為擁有者，且擁有完整權限。<br /><br />呼叫者沒有存取權。 被呼叫者必須將它分享給呼叫者。|
|群組通話                                 |通話的任何成員 |按一下 [錄製] 之商務用 OneDrive 帳戶的群組成員  |按一下 [錄製] 的成員擁有完整的權限。 <br /><br /> 同一租使用者的其他群組成員具有讀取權限。 <br /><br /> 不同租使用者的其他群組成員沒有許可權。|
|Adhoc/Scheduled 會議                    |召集人              |召集人的商務用 OneDrive 帳戶                     |召集人擁有完整的錄製權限。 <br /><br /> 會議所有其他成員都有讀取存取權。|
|Adhoc/Scheduled 會議                    |其他會議成員   |按一下 [錄製] 的會議成員                                  |按一下 [錄製] 的成員擁有完整的錄製權限。 <br /><br />召集人有編輯權限並可以共用。<br /><br /> 所有其他會議成員都有讀取存取權。|
|與外部使用者的 Adhoc/Scheduled 會議|召集人              |召集人的商務用 OneDrive 帳戶                     |召集人擁有完整的錄製權限。<br /> <br /> 會議的所有其他成員與召集人來自同一個租使用者，都有讀取存取權。 <br /><br /> 所有其他外部成員皆沒有存取權，而召集人必須與他們公用。|
|與外部使用者的 Adhoc/Scheduled 會議|其他會議成員   |按一下 [錄製] 的成員                                  |按一下 [錄製] 的成員擁有完整的錄製權限。 召集人有編輯權限並可以共用。 <br /><br /> 會議的所有其他成員與召集人來自同一個租使用者，都有讀取存取權。 <br /><br />所有其他外部成員皆沒有存取權，而召集人必須與他們公用。|
|頻道會議                            |頻道成員         |Teams SharePoint該頻道的位置。 **注意**：基於 IP 的限制不支援SharePoint錄製上傳到您的頻道會議。 我們建議您使用 [Azure 條件式存取](/azure/active-directory/conditional-access/overview)。 |按一下 [錄製> 的成員擁有錄製的編輯許可權。 <br /> <br />每個其他成員的許可權都是根據通道SharePoint許可權。|

## <a name="frequently-asked-questions"></a>常見問題集

**會議錄製內容會儲存在何處？**

- 對於非頻道會議，錄製會儲存在名為錄製的資料夾，該資料夾位於會議商務用 OneDrive會議錄製者所屬的最頂層。 範例：

  <i>答錄機商務用 OneDrive</i> /**錄製**

- 針對頻道會議，錄製會儲存在名為 Teams 的資料夾中的 Teams網站文檔 **庫中**。 範例：

  <i>Teams名稱 - 頻道名稱</i> /**檔** /**錄製**

**當串流 (例如錄製) 儲存于 SharePoint/OneDrive 中時，如何決定它們的位置？系統管理員是否能夠變更其位置？**

根據預設，所有錄製檔案都會OneDrive記錄使用者 **的帳戶。** 對於頻道會議，錄製內容會一SharePoint到頻道的網址。 系統管理員無法變更錄製的儲存位置。

**如何處理來自前員工的錄製？**

由於影片就像其他檔案一樣，商務用 OneDrive SharePoint員工離職後處理擁有權和保留，會遵循一般商務用 OneDrive SharePoint[程式](/onedrive/retention-and-deletion#the-onedrive-deletion-process)。

**神秘會議錄製的許可權嗎？**

- 對於非通道會議，除了外部使用者之外，所有會議受邀者都會自動取得個人共用連結。 會議召集人或會議錄製者必須明確將外部使用者新加入共用清單。

- 對於頻道會議，許可權會從頻道中的擁有者和成員清單中繼承。

> [!NOTE]
> 錄製完成後，您不會收到電子郵件，但錄製完成之後，就會顯示在會議聊天中。 這會比先前在 Stream 中更快發生。

**如何管理標題？**

只有當使用者在錄製時已開啟謄寫功能，才能在播放期間使用 Teams 會議錄製的隱藏式輔助字幕。 系統管理員必須 [經由原則將錄製謄寫功能開啟](/microsoftteams/cloud-recording#turn-on-or-turn-off-recording-transcription)，以確保他們的使用者可以選擇錄製會議及謄寫功能。

字幕可協助建立適用於所有能力之觀眾的包容性內容。作為擁有者，您可以在會議錄製中隱藏字幕，不過除非您在 Teams 中刪除會議文字記錄，否則會議文字記錄仍可使用。

從錄製會議起Teams 60 天內，會議錄製都支援隱藏式字幕。

如果會議錄製內容從原始位置移動Teams或複製，則隱藏式商務用 OneDrive SharePoint。

> [!NOTE]
> 將會提供僅英文的即時輔助字幕 (會議謄寫功能尚無法在 GCC 中使用)。

**我的儲存空間配額會如何影響？**

Teams錄製的檔案會商務用 OneDrive SharePoint，並包含在這些服務的配額中。 請參閱[SharePoint配額](/sharepoint/sites/plan-site-maintenance-and-management#quotas)和[商務用 OneDrive配額](/onedrive/set-default-storage-space)。

與 Stream 相比[](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)，您商務用 OneDrive更多的儲存空間，以及更多可SharePoint。

**如何播放會議Teams錄製？**

視您存取檔案的位置商務用 OneDrive視SharePoint播放影片。

**如果您打算取消新增到 Stream，現有的影片會維持目前和多久？**

在近期內不會將 Stream 當做平臺被棄用。 目前住在 Stream 中的影片會一直留在這裡，直到我們開始移移。 移移之後，這些視商務用 OneDrive或SharePoint移。 請查看 [Stream 傳統移移](/stream/streamnew/classic-migration) 以瞭解更多資訊。

**如何將保留標籤Microsoft Teams錄製？**

請參閱 [如何自動貼上保留標籤](/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)。

**如何指派政策給使用者，Microsoft Teams哪些政策為優先？**

請參閱 [哪個策略優先？](./assign-policies.md#which-policy-takes-precedence)。

**如果使用者沒有儲存空間或商務用 OneDrive，或儲存SharePoint已滿，錄製會在哪裡？**

錄製內容會位於我們的暫時儲存位置，該儲存位置將保存 21 天。 在此期間，召集人必須下載錄製內容。 如果未在 21 天內下載，錄製內容會被刪除。

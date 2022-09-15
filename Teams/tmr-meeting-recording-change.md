---
title: 使用 商務用 OneDrive 和 SharePoint 進行會議錄製
ms.author: mabond
author: mkbond007
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
ms.openlocfilehash: 1c6dbcbe57694273d1e74a4d1a60a3df8cc8ace4
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706700"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>使用 商務用 OneDrive 和 SharePoint 或 Stream 來錄製會議

> [!NOTE]
> 自 2021 年 8 月 30 日起，已完成將 Teams 會議錄製從傳統串流儲存到 OneDrive 和 SharePoint (ODSP) 的變更。 所有錄製現在都儲存在 ODSP 中。 這項變更會覆寫 RecordingStorageMode 原則，而修改 PowerShell 中的設定則不再有任何影響。

|日期&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|事件&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|2020 年 10 月 5 日<br> *(已完成)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| 您可以啟用 Teams 會議原則，將會議錄製儲存至 商務用 OneDrive 和 SharePoint，而不是Microsoft Stream (傳統版) |
|2021 年 1 月 7 日開始推出<br> *(已完成)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|除非您修改貴組織的 Teams 會議原則並明確設定為 Stream，藉此延遲這項變更，否則所有新的 Teams 會議錄製都會 **儲存到 商務用 OneDrive** 和 SharePoint。 僅看到原則報告為 Stream 是不够的。 您需要明確地將原則值設定為 **Stream**。|
|2021 年 1 月 11 日開始推出<br> *(已完成)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**僅 GCC**<br> 雖然 GCC 客戶可以從 10 月 5 日開始選擇退出，但您不能選擇加入。 此功能將從 2021 年 1月 11 日開始向所有 GCC 客戶推出，除非您已選擇退出。<br>  <br>自 2021 年 1 月 11 日起，所有 GCC 客戶的新 Teams 會議錄製內容都會儲存到 商務用 OneDrive 和 SharePoint，除非您修改貴組織的 Teams 會議原則並明確設定為 **Stream** 來延遲此變更。 <br><br>如果您已選擇退出，但準備好啟用此功能，則可以透過將 Teams 會議原則明確設定為 **商務用 OneDrive** 來實現。 |
|2021 年 3 月 1 日開始推出<br> *(已完成)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**進 GCC-High 和 DoD**<br> 客戶現在可以在其 Microsoft Teams 中首次啟用雲端會議錄製。 根據預設，這些錄製內容會儲存在 OneDrive 和 SharePoint 上並播放。 |
|從 2021 年 8 月 16 日開始逐步推出<br> *(已完成)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**所有客戶 (企業、教育和 GCC)**<br>無法將新的會議錄製儲存至Microsoft Stream (傳統版) ;即使所有客戶已將 Teams 會議原則變更為 Stream，也會自動將會議錄製儲存至 商務用 OneDrive 和 SharePoint。<br><br> 我們建議客戶，在您對變更感到滿意選擇加入，而非等待變更生效，以便更好地控制組織中的變更。 |

Microsoft Teams 有用於儲存會議錄製的新方法。 從傳統Microsoft Stream轉換到[新 Stream](/stream/streamnew/new-stream)的第一個階段，此方法會將錄製內容儲存在 Microsoft 365 中的 Microsoft 商務用 OneDrive 和 SharePoint，並提供許多優點。

> [!NOTE]
> 如果 Teams 會議錄製無法成功上傳到 OneDrive/SharePoint，將會出現「錄製意外結束」錯誤訊息，而錄製內容會暫時儲存至 Azure Media Services (AMS) 。 儲存在 AMS 後，不會嘗試自動將錄製內容上傳到 OneDrive/SharePoint 或 Stream。

儲存在 AMS 中的會議錄製内容在自動删除前可使用 21 天。 若使用者需要保留複本，可從 AMS 下載影片。

使用 商務用 OneDrive 和 SharePoint 儲存錄製的優點包括：

- Teams 會議錄製內容 (TMR) 的保留原則 (S+C E5 自動偵測標籤)
- 受惠于商務用 OneDrive與 SharePoint 資訊控管
- 易於設定權限和共用
- 僅以明確共用方式與來賓共用錄製內容
- 要求存取流程
- 供應商務用 OneDrive和 SharePoint 共用連結
- 可更快取得會議錄製内容
- **移至本地** 租用戶支援
- 多地理位置支援 – 錄製内容儲存在特定於該使用者的地區
- 攜帶您自己的金鑰 (BYOK) 支援

查看[當前可用功能以及一段時間后的預期功能](/stream/streamnew/features-new-version-stream)的完整清單。

如需詳細資訊，請觀看「Microsoft Teams 會議錄製新功能」。

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>設定 商務用 OneDrive 和 SharePoint 的會議錄製選項

會議錄製選項是 Teams 原則層級的設定。 下列範例顯示如何設定全域原則。 請確定為已指派給使用者的一個或多個原則設定了會議錄製選項。

> [!NOTE]
> Teams 會議原則變更需要一段時間來傳播。設定完成的幾小時後再返回檢查，然後登出並再次登入至 Teams 桌面版應用程式，或僅是重新啟動電腦。

1. 安裝 Teams PowerShell。

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

5. 使用[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)來設定 Teams 會議原則，從 Stream 儲存空間轉換到 商務用 OneDrive 和 SharePoint。

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!NOTE]
> 如果您的某些使用者已指派每位召集人或個別使用者的原則，如果您希望他們同時將會議錄製儲存在 商務用 OneDrive 和 SharePoint 中，您必須在此原則上設定此設定。 如需詳細資訊，請參閱[在 Teams 中管理會議原則](meeting-policies-overview.md)。

## <a name="permissions-or-role-based-access"></a>許可權或角色型存取

> [!NOTE]
> 我們建議收件者必須是共用 Teams 會議錄製內容時的登入使用者。 當您在 [SharePoint 檔案或資料夾](https://support.microsoft.com/office/1fe37332-0f9a-4719-970e-d2578da4941c)中共用檔案時，選取 **[ (貴組織])** 中的 [人員] 選項。 外部共用並非專為發佈大型檔案或大量檔案所設計。

|會議類型                               | 是誰按了一下 [錄製]？| 錄製內容在哪裡？                               |誰可以存取？ R/W、R 或共用                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|與內部派對進行一對一通話             |呼叫者                 |呼叫者的商務用 OneDrive 帳戶                        |呼叫者為擁有者，且擁有完整權限。 <br /><br />被呼叫者 (如果在同一個租用戶中) 擁有唯讀存取權。沒有共用存取權。 <br /><br /> 被呼叫者 (如果在其他租用戶中) 沒有存取權。 呼叫者必須將它分享給被呼叫者。|
|與內部派對進行一對一通話             |被呼叫者                 |被呼叫者的商務用 OneDrive 帳戶                        |被呼叫者為擁有者，且擁有完整權限。 <br /><br />呼叫者 (如果在同一個租用戶中) 擁有唯讀存取權。沒有共用存取權。 <br /><br />呼叫者 (如果在其他租用戶中) 沒有存取權。 被呼叫者必須將它分享給呼叫者。|
|與外部通話進行一對一通話             |呼叫者                 |呼叫者的商務用 OneDrive 帳戶                        |呼叫者為擁有者，且擁有完整權限。<br /> <br />被呼叫者沒有存取權。 呼叫者必須將它分享給被呼叫者。|
|與外部通話進行一對一通話             |被呼叫者                 |被呼叫者的商務用 OneDrive 帳戶                        |被呼叫者為擁有者，且擁有完整權限。<br /><br />呼叫者沒有存取權。 被呼叫者必須將它分享給呼叫者。|
|群組通話                                 |通話的任何成員 |按一下 [錄製] 之商務用 OneDrive 帳戶的群組成員  |按一下 [錄製] 的成員擁有完整的權限。 <br /><br /> 來自相同租使用者的其他群組成員具有讀取權限。 <br /><br /> 其他來自不同租使用者的群組成員沒有該群組成員的許可權。|
|Adhoc/Scheduled 會議                    |召集人              |召集人的商務用 OneDrive 帳戶                     |召集人擁有完整的錄製權限。 <br /><br /> 會議的其他所有成員都具有讀取權限。|
|Adhoc/Scheduled 會議                    |其他會議成員   |按一下 [錄製] 的會議成員                                  |按一下 [錄製] 的成員擁有完整的錄製權限。 <br /><br />召集人有編輯權限並可以共用。<br /><br /> 所有其他會議成員都有讀取權。|
|與外部參與者的 Adhoc/Scheduled 會議|召集人              |召集人的商務用 OneDrive 帳戶                     |召集人擁有完整的錄製權限。<br /> <br /> 來自與召集人同一租使用者的會議其他所有成員都具有讀取權限。 <br /><br /> 所有其他外部參與者都無法存取，而召集人必須將它分享給他們。|
|與外部參與者的 Adhoc/Scheduled 會議|其他會議成員   |按一下 [錄製] 的成員                                  |按一下 [錄製] 的成員擁有完整的錄製權限。 召集人有編輯權限並可以共用。 <br /><br /> 來自與召集人同一租使用者的會議其他所有成員都具有讀取權限。 <br /><br />所有其他外部參與者都無法存取，而召集人必須將它分享給他們。|
|頻道會議                            |頻道成員         |該頻道的 Teams SharePoint 位置。 **注意**：IP 限制不支援將通道會議錄製上傳到 SharePoint。 建議您使用 [Azure 條件式存取](/azure/active-directory/conditional-access/overview)。 |按一下 [錄製] 的成員擁有錄製的編輯許可權。 <br /> <br />每個其他成員的權限都是以 Channel SharePoint 權限為基礎。|

## <a name="frequently-asked-questions"></a>常見問題集

**會議錄製內容會儲存在何處？**

- 對於非通道會議，錄製內容會儲存在名為 [**錄製**] 的資料夾中，該資料夾位於啟動會議錄製人員所屬的商務用 OneDrive最上層。 範例：

  *錄製器的商務用 OneDrive* / **記錄**

- 針對頻道會議，錄製內容會儲存在 Teams 網站文件庫中名為 [ **錄製] 的資料夾中**。 範例：

  *團隊名稱 - 頻道名稱* /**檔** /**錄音**

**當串流檔案 (例如錄製) 儲存在 SharePoint/OneDrive 中時，該如何決定它們的所在位置？系統管理員是否能夠變更移至何處？**

根據預設，所有錄製檔案都會移至選取 [ **錄製**] 之使用者的 OneDrive 帳戶。 針對頻道會議，錄製內容一律會移至頻道的 SharePoint 網站。 系統管理員無法變更儲存錄製的位置。

**如何?處理離職員工的錄音嗎？**

由於影片與 商務用 OneDrive 和 SharePoint 中的任何其他檔案一樣，在員工離職後處理擁有權和保留權將遵循一般[商務用 OneDrive和 SharePoint 程式](/onedrive/retention-and-deletion)。

**誰有權檢視會議錄製內容？**

- 針對非頻道的會議，除了外部參與者以外，所有會議受邀者都會自動取得個人共用連結。 外部參與者必須由會議召集人或開始錄製會議的人員明確新增到共用清單。

- 針對頻道會議，許可權是從頻道中的擁有者和成員清單繼承而來。

> [!NOTE]
> 錄製完成後，您不會收到電子郵件，但錄製完成後會出現在會議聊天中。 這會比之前在 Stream 中執行的快得多。

**如何管理輔助字幕？**

只有當使用者在錄製時已開啟謄寫功能，才能在播放期間使用 Teams 會議錄製的隱藏式輔助字幕。 系統管理員必須 [開啟錄製轉譯](meetings-policies-recording-and-transcription.md#transcription) ，以確保其使用者可以選擇使用轉譯來錄製會議。

字幕可協助建立適用於所有能力之觀眾的包容性內容。作為擁有者，您可以在會議錄製中隱藏字幕，不過除非您在 Teams 中刪除會議文字記錄，否則會議文字記錄仍可使用。

在錄製會議後 60 天內，Teams 會議錄製會支援隱藏式輔助字幕。

如果 Teams 會議錄製是從其在 商務用 OneDrive 或 SharePoint 上的原始位置移動或複製，則隱藏式輔助字幕就無法完全支援。

> [!NOTE]
> 將會提供僅英文的即時輔助字幕 (會議謄寫功能尚無法在 GCC 中使用)。

**我的儲存配額會如何受到影響？**

Teams 會議記錄檔案會以 商務用 OneDrive 和 SharePoint 為即時記錄，並包含在這些服務的配額中。 請參閱[SharePoint 配額](/sharepoint/sites/plan-site-maintenance-and-management#quotas)和[商務用 OneDrive配額](/onedrive/set-default-storage-space)。

相較于 Stream，您會獲得更多含[商務用 OneDrive](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)的儲存空間，以及更多的 SharePoint 可用儲存空間。

**如何播放 Teams 會議錄製內容？**

視您存取檔案的位置而定，視訊會在 商務用 OneDrive 或 SharePoint 的視訊播放程式上播放。

**如果您打算取代新增至 Stream 的功能，現有的視訊會維持現狀並持續多久嗎？**

平臺串流在不久的將來不會遭取代。 在我們開始移轉之前，目前存在於 Stream 中的影片會一直保留在那裡。 移轉時，這些影片也會移轉到 商務用 OneDrive 或 SharePoint。 如需詳細資訊，請參閱 [移轉詳細](/stream/streamnew/migration-details) 資料。

**如何?將保留標籤套用至 Microsoft Teams 會議錄製？**

請參閱 [如何自動套用保留標籤](/microsoft-365/compliance/apply-retention-labels-automatically)。

**如何?在 Microsoft Teams 中將原則指派給我的使用者，哪些原則優先？**

請參閱 [哪個原則優先？](./policy-assignment-overview.md#which-policy-takes-precedence)。

**如果使用者沒有 商務用 OneDrive 或 SharePoint，或儲存配額已滿，錄製會移至何處？**

錄製內容會移至我們的臨時儲存位置，並保留 21 天。 在此期間，召集人必須下載錄製內容。 如果未在 21 天內下載，則會刪除錄製內容。

---
title: 使用 商務用 OneDrive 和 SharePoint Online 進行會議錄製
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何從 Stream 切換到 商務用 OneDrive，SharePoint線上會議錄製儲存Microsoft Teams。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: e00ccbf9ade9b1fae3dde64033fe82b502e2366b
ms.sourcegitcommit: 79d20fa2c45173d5a990551e79571caff06d7f82
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/20/2021
ms.locfileid: "53486133"
---
# <a name="use-onedrive-for-business-and-sharepoint-online-or-stream-for-meeting-recordings"></a>使用 商務用 OneDrive 或 SharePoint Online 或 Stream 進行會議錄製

> [!Note]
> 從使用 Microsoft Stream 變更為商務用 OneDrive Microsoft Office SharePoint Online錄製的錄製內容，將採用階段式方法。

|<div style="width:290px">日期&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |事件&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
|:--------------|:----------------------|
|2020 年 10 月 5 日<br> *(完成)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| 您可以啟用 Teams 會議政策，將會議錄製儲存到 商務用 OneDrive SharePoint，而不是 Microsoft Stream (傳統) |
|從 2021 年 1 月 7 日開始推出<br> *(完成)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|所有Teams會議錄製內容都會儲存至 商務用 OneDrive 和 SharePoint Online，除非您修改組織的 Teams 會議政策，並明確將其設定為 Stream 來延遲這項 **變更。** 將策略報告視為 Stream 是不夠的。 您必須明確地將策略值設定為 **Stream。**|
|從 2021 年 1 月 11 日開始推出<br> *(完成)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC只**<br> 雖然GCC客戶可以從 10 月 5 日起退出宣告，但您將無法加入宣告。 這項功能將于 2021 GCC 2021 年 1 月 11 日開始推出給所有客戶，除非您退出宣告。<br>  <br>自 2021 年 1 月 11 日起，GCC 客戶的所有新 Teams 會議錄製內容都會儲存至 商務用 OneDrive 和 SharePoint Online，除非您修改組織的 Teams 會議政策並明確將其設定為 Stream 來延遲這項變更。 <br><br>如果您已經退出宣告，但已準備好開啟此功能，您可以將會議Teams明確設定為 **商務用 OneDrive。** |
|自 2021 年 3 月 1 日推出<br> *(完成)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC -High 和 DoD**<br> 客戶現在可以第一次在Microsoft Teams中啟用雲端會議錄製。 這些錄製內容預設會儲存並OneDrive SharePoint線上播放。 |
|自 2021 年 7 月 7 日開始推出<br> *(完成)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**所有客戶 (Enterprise、教育及GCC)**<br> 對於Teams錄製至 OneDrive 和 SharePoint Online 且在會議期間也即時轉譯的會議，現在您可以在 Microsoft 搜尋 中搜尋，以根據記錄尋找會議錄製檔案。 |
|從 2021 年 8 月 16 日逐步推出 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**所有客戶 (Enterprise、教育及GCC)**<br>無法將新的會議錄製儲存至 Microsoft Stream (傳統) ;所有客戶都會自動將會議錄製儲存商務用 OneDrive並SharePoint線上，即使他們已經將會議Teams變更為 Stream。<br><br> 我們建議您客戶，為了更好的控制貴組織的變更，只要您習慣變更，就加入宣告，而不是等待變更發生。 |

Microsoft Teams有一種用於保存會議錄製的新方法。 這是從傳統 Microsoft Stream 轉換到新 Stream[](/stream/streamnew/new-stream)的第一個階段，此方法會儲存 Microsoft OneDrive 商務用和 SharePoint Online 中的錄製內容Microsoft 365並提供許多優點。

stream (傳統) 平臺不會在近期內被棄用。 目前位於 Stream (傳統) 中的影片會一直存在，直到日後可以使用移轉工具將影片移至 OneDrive SharePoint Online。 請查看 [Stream 傳統移移](/stream/streamnew/classic-migration) ，以進一步瞭解我們未來的方案。

> [!NOTE]
> 如果Teams會議錄製無法成功上傳到 OneDrive/SharePoint Online，錄製內容會暫時儲存至 Azure 媒體服務 (AMS) 。 儲存于 AMS 後，系統不會嘗試嘗試自動將錄製上傳到 OneDrive/SharePoint或 Stream。

儲存在 AMS 中的會議錄製可在自動刪除前 21 天使用。 如果需要保留副本，使用者可以從 AMS 下載影片。

使用 商務用 OneDrive 和 SharePoint 線上儲存錄製的權益包括：

- 使用 TMR Teams S+C E5 (自動執行)  (錄製的保留) 
- 受益于線上商務用 OneDrive SharePoint管理
- 輕鬆設定許可權和共用
- 僅以明確共用 (外部) 共用錄製內容
- 要求存取流程
- 供應商務用 OneDrive和SharePoint線上共用連結
- 會議錄製功能更快速
- 搜尋會議記錄的基礎文字記錄
- **前往當地** 租使用者支援
- 多地理位置支援 – 錄製會儲存在該使用者特定的區域
- 將您自己的金鑰 (BYOK) 支援

查看今天可用的 [功能的完整清單，以及一段時間後預期的結果](/stream/streamnew/features-new-version-stream)。

請觀看「會議Microsoft Teams的新增功能」以瞭解更多資訊。

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint-online"></a>設定線上和線上商務用 OneDrive SharePoint選項

會議錄製選項是一項設定，Teams層級。 下列範例顯示如何設定全域原則。 請確定您為指派給使用者的政策或政策設定會議錄製選項。

> [!Note]
> Teams策略變更需要一段時間才能傳播。 設定好幾個小時之後再回來查看，然後登出並再次Teams桌面應用程式，或重新開機電腦。

1. 安裝 Teams PowerShell PowerShell。

   > [!NOTE]
   > 商務用 Skype線上連接器是目前 PowerShell 模組Teams的一部分。 如果您使用的是最新版 PowerShell Teams版本，則不需要安裝 商務用 Skype 連接器。 請參閱[使用 powerShell 商務用 Skype管理線上版](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide)。

2. 以系統管理員角色啟動 PowerShell。

3. 安裝[Teams PowerShell 模組](./teams-powershell-install.md)。

4. 輸入 MicrosoftTeams 模組，然後以系統管理員Teams登。

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

5. 使用[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)設定 Teams 會議策略，以從 Stream 儲存空間轉換至 商務用 OneDrive SharePoint Online。

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> 如果您的部分使用者已指派每個召集人或每個使用者的政策，如果您希望他們同時將會議錄製儲存在 商務用 OneDrive 和 SharePoint Online 中，您必須在此策略上設定此設定。 詳細資訊，請參閱在 Teams 中[管理會議Teams。](meeting-policies-in-teams.md)

## <a name="learn-more"></a>深入了解

若要深入瞭解雲端Teams錄製，請參閱Teams[會議錄製。](cloud-recording.md) 您可以在該文章中深入瞭解錄製設定、管理、管理、許可權和儲存空間。

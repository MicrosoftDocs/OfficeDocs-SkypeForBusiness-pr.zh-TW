---
title: 使用商務用 OneDrive 和 SharePoint Online 進行會議錄製
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中從 Stream 切換至商務用 OneDrive 和 SharePoint 會議錄製儲存空間。
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c53cc427c1db87a2d0296384d5d0c67e7e7996a
ms.sourcegitcommit: d34dbdc2f71f3d024cb7f1856fc0f8bbc701f66d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2021
ms.locfileid: "53506322"
---
# <a name="use-onedrive-for-business-and-sharepoint-online-or-stream-for-meeting-recordings"></a>使用商務用 OneDrive 和 SharePoint Online 或 Stream 進行會議錄製

> [!Note]
> 從使用 Microsoft Stream 到變更為使用商務用 OneDrive 和 Microsoft SharePoint Online 來進行會議錄製，將會採取階段性的方式。

|<div style="width:290px">日期&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |事件&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
|:--------------|:----------------------|
|2020 年 10 月 5 日<br> *(已完成)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| 您允許 Teams 會議原則將會議錄製儲存至商務用 OneDrive 和 SharePoint Online，而非 Microsoft Stream (傳統版)|
|2021 年 1 月 7 日開始推出<br> *(已完成)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|所有新 Teams 會議錄製都將儲存至商務用 OneDrive 和 SharePoint Online，除非您修改組織的 Teams 會議原則並將其明確設定為 **Stream** 來延遲此變更。 僅看到原則報告為 Stream 是不够的。 您需要明確地將原則值設定為 **Stream**。|
|2021 年 1 月 11 日開始推出<br> *(已完成)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**僅 GCC**<br> 雖然 GCC 客戶可以從 10 月 5 日開始選擇退出，但您不能選擇加入。 此功能將從 2021 年 1月 11 日開始向所有 GCC 客戶推出，除非您已選擇退出。<br>  <br>從 2021 年 1 月 11 開始，GCC 客戶的所有新 Teams 會議錄製都將儲存至商務用 OneDrive 和 SharePoint Online，除非您修改組織的 Teams 會議原則並將其明確設定為 **Stream** 來延遲此變更。 <br><br>如果您已選擇退出，但準備好啟用此功能，則可以透過將 Teams 會議原則明確設定為 **商務用 OneDrive** 來實現。 |
|2021 年 3 月 1 日開始推出<br> *(已完成)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**進 GCC-High 和 DoD**<br> 客戶現在可以在其 Microsoft Teams 中首次啟用雲端會議錄製。 根據預設，這些錄製將在 OneDrive 和 SharePoint Online 上儲存和播放。 |
|2021 年 7 月 7 日開始推出<br> *(已完成)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**所有客戶 (企業、教育和 GCC)**<br> 對於錄製至 OneDrive 和 SharePoint Online 並在會議期間即時轉錄的 Teams 會議，您現在可以在 Microsoft 搜尋中根據會議記錄尋找會議錄製檔案。 |
|從 2021 年 8 月 16 日開始逐步推出&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**所有客戶 (企業、教育和 GCC)**<br>不能將新會議錄製儲存至 Microsoft Stream (傳統)；所有客戶將自動將會議錄製儲存至商務用 OneDrive 和 SharePoint Online，即使他們已將其 Teams 會議原則變更為 Stream。<br><br> 我們建議客戶，在您對變更感到滿意選擇加入，而非等待變更生效，以便更好地控制組織中的變更。 |

Microsoft Teams 有用於儲存會議錄製的新方法。 做為從傳統 Microsoft Stream 轉換為[新 Stream](/stream/streamnew/new-stream)的第一階段，此方法會將錄製檔儲存在 Microsoft 商務用 OneDrive 和 Microsoft 365 的 SharePoint Online 中，並提供許多優點。

Stream (傳統版) 平台不會在近期被弃用。 在未來的移轉工具可用於將影片移動至 OneDrive 和 SharePoint Online 之前，目前儲存在 Stream (傳統版) 中的影片將一直保留在該處。 有關我們未來計畫的更多資訊，請查看 [Stream 傳統版移轉](/stream/streamnew/classic-migration)。

> [!NOTE]
> 如果 Teams 會議錄製未能成功上傳至 OneDrive/SharePoint Online，則錄製內容將暫時儲存至 Azure 媒體服務 (AMS)。 儲存至 AMS 中後，系統不會重試將錄製內容自動上傳至 OneDrive/SharePoint Online 或 Stream。

儲存在 AMS 中的會議錄製内容在自動删除前可使用 21 天。 若使用者需要保留複本，可從 AMS 下載影片。

使用商務用 OneDrive 和 SharePoint Online 儲存錄製内容的好處包括：

- Teams 會議錄製內容 (TMR) 的保留原則 (S+C E5 自動偵測標籤)
- 受益於商務用 OneDrive 和SharePoint Online 資訊控管
- 易於設定權限和共用
- 僅透過明確共用與來賓 (外部使用者) 共用錄製内容
- 要求存取流程
- 提供商務用 OneDrive 和 SharePoint Online 共用連結
- 可更快取得會議錄製内容
- 搜尋會議中錄製的基礎文字記錄
- **移至本地** 租用戶支援
- 多地理位置支援 – 錄製内容儲存在特定於該使用者的地區
- 攜帶您自己的金鑰 (BYOK) 支援

查看[當前可用功能以及一段時間后的預期功能](/stream/streamnew/features-new-version-stream)的完整清單。

如需詳細資訊，請觀看「Microsoft Teams 會議錄製新功能」。

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint-online"></a>設定商務用 OneDrive 和 SharePoint Online 的會議錄製選項

會議錄製選項是 Teams 原則層級的設定。 下列範例顯示如何設定全域原則。 請確定為已指派給使用者的一個或多個原則設定了會議錄製選項。

> [!Note]
> Teams 會議原則變更需要一段時間來傳播。 設定完成的幾小時後再返回檢查，然後登出並再次登入至 Teams 桌面版應用程式，或僅是重新啟動電腦。

1. 安裝 Teams PowerShell PowerShell。

   > [!NOTE]
   > 商務用 Skype Online 連接器目前是最新 Teams PowerShell 模組的一部分。 如果您使用的是最新的 Teams PowerShell 公開發行版本，則不需要安裝商務用 Skype Online 連接器。 請參閲[使用 PowerShell 管理商務用 Skype Online](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide)。

2. 以系統管理員身分啟動 PowerShell。

3. 安裝[Teams PowerShell 模組](./teams-powershell-install.md)。

4. 匯入 MicrosoftTeams 模組並以 Teams 系統管理員身分登入。

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

5. 使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) 設定 Teams 會議原則，以從 Stream 儲存空間轉換至商務用 OneDrive 和 SharePoint Online。

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> 如果您的某些使用者已指派了「每一召集人」或「每一使用者」原則，那麽若您希望他們也將會議錄製儲存在商務用 OneDrive 和 SharePoint Online 中，則您必須在此原則上設定此設定。 如需詳細資訊，請參閱[在 Teams 中管理會議原則](meeting-policies-in-teams.md)。

## <a name="learn-more"></a>深入了解

若要深入了解 Teams 雲端會議錄製，請參閱 [Teams 雲端會議錄製](cloud-recording.md)。 在這篇文章中，您可以深入了解錄製設定、管理、控管、權限和儲存空間。

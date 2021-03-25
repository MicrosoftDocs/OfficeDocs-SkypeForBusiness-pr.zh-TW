---
title: '使用會議移 (MMS) '
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 會議移 (MMS) 是一項在背景中執行的服務，並自動更新商務用 Skype 和 Microsoft Teams 會議給使用者。 MMS 是專為使用者執行會議移移工具以更新其商務用 Skype 和 Microsoft Teams 會議所設計。
ms.openlocfilehash: 18a36425e842e0c24c5cf6c2837535043e7967a8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111949"
---
# <a name="using-the-meeting-migration-service-mms"></a>使用會議移 (MMS) 

會議移 (MMS) 是一項服務，可更新使用者在下列情況下的現有會議：

- 當使用者從內部部署移至雲端時， (商務用 Skype Online 或 TeamsOnly) 。
- 當系統管理員變更使用者的音訊會議設定時 
- 當線上使用者僅升級至 Teams 時，或在 TeamsUpgradePolicy 中的使用者模式設為 SfBwithTeamsCollabAndMeetings 時
- 當您使用 PowerShell 時 


根據預設，MMS 會在每一種情況下自動觸發，不過系統管理員可以在租使用者層級停用 MMS。 此外，系統管理員可以使用 PowerShell Cmdlet 為給定使用者手動觸發會議移轉。


**限制**：如果適用下列任何一項，就無法使用會議移移服務：

- 使用者的信箱是託管在 Exchange 內部部署中。
- 使用者正從雲端移至內部部署商務用 Skype Server。

在這些情況下，使用者可以改為使用會議移移 [工具](https://www.microsoft.com/download/details.aspx?id=51659) 移移自己的會議。

## <a name="how-mms-works"></a>MMS 運作方式

當為給定使用者觸發 MMS 時，該使用者的移入要求會置於佇列中。 為了避免任何競賽條件，排入佇列的要求至少 90 分鐘之後才會刻意處理。 MMS 處理要求後，會執行下列工作：

1. 它會搜尋該使用者的信箱，以搜尋該使用者組織並在未來排程的所有現有會議。
2. 根據使用者信箱中的資訊，它會根據確切案例，更新或排程該使用者在 Teams 或商務用 Skype Online 中的新會議。
3. 在電子郵件訊息中，它會取代會議詳細資料中的線上會議區塊。
4. 它會代表會議召集人，將會議的更新版本傳送給所有會議收件者。 會議受邀者會收到一份會議更新，其電子郵件中會包含更新的會議座標。 

    ![由 MMS 更新的會議區塊](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

從 MMS 觸發起，一般需要大約 2 小時，直到使用者的會議移移。 不過，如果使用者的會議數量很多，可能需要較長的時間。 如果 MMS 在移移使用者的一或多個會議時發生錯誤，它會在 24 小時內定期重試 9 次。

**附注：**

- 當會議移移時，MMS 會取代線上會議資訊區塊中的所有專案。 因此，如果使用者已編輯該區塊，其變更將會被覆蓋。 他們在線上會議資訊區塊以外的會議詳細資料中擁有的任何內容都不受影響。 這表示附加至會議邀請的任何檔案仍然會包含在內。 
- 只有按一下 Outlook 網頁中的新增 Skype 會議按鈕，或是使用Outlook 的 Skype 會議附加元件來排程的商務用 Skype 或 Microsoft Teams 會議，才能移移。 如果使用者將 Skype 線上會議資訊從一個會議複製並印至新會議，由於原始服務中沒有任何會議，因此無法更新新會議。
- 建立或附加至會議的會議內容 (白板、投票等內容) MMS 執行之後不會保留。 如果您的會議召集人事先將內容附加至會議，則 MMS 執行之後，必須重新重新組織內容。
- 在日曆專案以及 Skype 會議內，共用會議筆記的連結也會被覆蓋。 請注意，儲存在 OneNote 中的實際會議筆記仍然會存在;只有已覆蓋之共用筆記的連結。
- 超過 250 位出席者的會議 (包括) 將不會移移。
- 邀請內文中的某些 UNICODE 字元可能無法正確更新為下列其中一個特殊字元：1、1/2、。

## <a name="triggering-mms-for-a-user"></a>觸發使用者的 MMS

本節說明在下列每一種情況下觸發 MMS 時會發生什麼情況：

- 當使用者從內部部署移向雲端時
- 當系統管理員變更使用者的音訊會議設定時 
- 當使用者在 TeamsUpgradePolicy 中的模式設定為 TeamsOnly 或 SfBWithTeamsCollabAndMeetings (使用 Powershell 或 Teams 系統管理入口網站) 
- 當您使用 PowerShell Cmdlet 時，請Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>將內部部署使用者移至雲端時更新會議

這是最常見的案例，MMS 可協助使用者建立更順暢的轉場效果。 若沒有會議移轉，使用者在商務用 Skype Server 內部部署中組織的現有會議，一旦使用者移至線上，就無法再使用。 因此，當您使用內部部署管理工具 (系統管理控制台) 將使用者移至雲端時，現有的會議會自動移至雲端， `Move-CsUser` 如下所示：

- 如果 `MoveToTeams` 已指定切換 `Move-CsUser` ，會議會直接移轉至 Teams，而使用者將進入 TeamsOnly 模式。 使用此開關時，需要使用 CU8 或更新版商務用 Skype Server 2015。 這些使用者仍可使用商務用 Skype 用戶端或 Skype 會議應用程式，加入他們可能會受邀參加的任何商務用 Skype 會議。
- 否則會議會移至商務用 Skype Online。

在這兩種情況下，如果使用者在移至雲端之前已指派音訊會議授權，會議會以撥入座標建立。 如果您將使用者從內部部署移至雲端，而且想要該使用者使用音訊會議，建議您先指派音訊會議，然後再移動使用者，這樣只會觸發 1 個會議移轉。


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>當使用者的音訊會議設定變更時更新會議

在下列情況下，MMS 會更新現有的商務用 Skype 和 Microsoft Teams 會議，以新增、移除或修改撥入座標：

- 當您指派或移除 Microsoft Audio 會議服務授權給使用者時，且該使用者並未為協力廠商音訊會議提供者啟用。
- 當您將使用者的音訊會議提供者從任何其他提供者變更為 Microsoft 時，只要該使用者獲得 Microsoft 音訊會議授權。 詳細資訊，請參閱指派 [Microsoft 做為音訊會議提供者](./assign-microsoft-as-the-audio-conferencing-provider.md)。 另請注意，如先前宣佈的，協力廠商音訊會議提供者 [ACP] 的支援計畫在 2019 年 4 月 1 日[結束。](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md)
- 當您為使用者啟用或停用音訊會議時。
- 當您變更或重設已設定為使用公用會議之使用者的會議 ID 時。
- 當您將使用者移至新的音訊會議橋接器時。
- 當音訊會議橋接器的電話號碼未指定時。 這是需要額外步驟的複雜案例。 詳細資訊，請參閱 [變更音訊會議橋接器上的電話號碼](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。

並非所有使用者的音訊會議設定變更都觸發 MMS。 具體來說，下列兩項變更不會導致 MMS 更新會議：

- 當您變更會議召集人的 SIP 位址時 (SIP 使用者名稱或 SIP 網域) 
- 當您使用命令變更貴組織的會議 `Update-CsTenantMeetingUrl` URL 時。


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>指派 TeamsUpgradePolicy 時更新會議

根據預設，當使用者獲與 或 的實例時，會自動觸發會議 `TeamsUpgradePolicy` `mode=TeamsOnly` 移移 `mode= SfBWithTeamsCollabAndMeetings` 。 如果您在授予上述任一模式時不想遷移會議，請于 (中指定使用 PowerShell) ，或取消勾選方塊以在設定使用者的並存模式時 (如果使用 Teams 系統管理入口網站 `MigrateMeetingsToTeams $false` `Grant-CsTeamsUpgradePolicy`) 。

另請注意下列事項：

- 只有在您授予特定使用者時，才能 `TeamsUpgradePolicy` 啟用會議移移。 如果您以 `TeamsUpgradePolicy` 租使用者為基礎或以租使用者為基礎授予，則會議 `mode=TeamsOnly` 移移 `mode=SfBWithTeamsCollabAndMeetings` 不會被援用。 
- 使用者只能在使用者位於線上時獲得 TeamsOnly 模式。 內部部署使用者必須使用先前所述 `Move-CsUser` 移動。
- 授予 TeamsOnly 或 SfBWithTeamsCollabAndMeetings 模式不會將現有的 Teams 會議轉換成商務用 Skype 會議。

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>透過 PowerShell Cmdlet 手動觸發會議移轉

除了自動會議移轉之外，系統管理員也可以執行 Cmdlet，手動觸發使用者的會議移轉 `Start-CsExMeetingMigration` 。 此 Cmdlet 會為指定的使用者排排移轉要求佇列。  除了必要的參數之外，它需要兩個選擇性參數，以及 ，這允許您 `Identity` `SourceMeetingType` `TargetMeetingType` 指定如何遷移會議：

**TargetMeetingType：**

- 使用 `TargetMeetingType Current` 指定商務用 Skype 會議仍然是商務用 Skype 會議，而 Teams 會議仍然是 Teams 會議。 不過，音訊會議座標可能會變更，而且任何內部部署商務用 Skype 會議都會移入商務用 Skype Online。 這是 TargetMeetingType 的預設值。
- 使用 指定任何現有的會議都必須移入 Teams，無論會議是託管于商務用 Skype 線上或內部部署，也不論是否需要任何音訊會議 `TargetMeetingType Teams` 更新。 

**SourceMeetingType：**
- 使用表示只有商務用 Skype 會議 (內部部署或線上) `SourceMeetingType SfB` 更新。
- 使用 `SourceMeetingType Teams` 表示應該只更新 Teams 會議。
- 使用 `SourceMeetingType All` 表示商務用 Skype 會議和 Teams 會議都應該更新。 這是 SourceMeetingType 的預設值。
    

下列範例顯示如何針對使用者啟動會議移 ashaw@contoso.com，讓所有會議移至 Teams：

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>管理 MMS

使用 Windows PowerShell，您可以檢查進行中的移移狀態、手動觸發會議移移，以及完全停用移移。 

### <a name="check-the-status-of-meeting-migrations"></a>檢查會議移移的狀態

您可以使用 `Get-CsMeetingMigrationStatus` Cmdlet 檢查會議移轉的狀態。 以下是一些範例。

- 若要取得所有 MMS 移移的摘要狀態，請執行下列命令，提供所有移移狀態的表格式視圖：

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- 若要取得特定時段內所有移移的完整詳細資料，請使用 和 `StartTime` `EndTime` 參數。 例如，下列命令會針對 2018 年 10 月 1 日到 2018 年 10 月 8 日進行的所有移移，返回完整詳細資料。

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- 若要檢查特定使用者的移移狀態，請使用 `Identity` 參數。 例如，下列命令會返回使用者 ashaw@contoso.com：

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
如果您看到任何移轉失敗，請採取動作，儘快解決這些問題，因為使用者無法撥入這些使用者組織的會議，直到您解決它們。 如果 `Get-CsMeetingMigrationStatus` 顯示失敗狀態的任何移移，請執行下列步驟：
 
1. 判斷受影響的使用者。 執行下列命令以取得受影響的使用者清單，以及報告的特定錯誤：

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. 針對每個受影響的使用者，執行會議移移工具，以手動移移其會議。

3. 如果移移仍然無法與會議移移工具一起使用，則有兩個選項：

    - 讓使用者建立新的 Skype 會議。
    - [請與支援人員聯繫](/microsoft-365/Admin/contact-support-for-business-products)。


### <a name="enabling-and-disabling-mms"></a>啟用及停用 MMS

MMS 預設會針對所有組織啟用，但可以停用，如下所示：

- 完全停用租使用者。 
- 僅針對與音訊會議相關的變更停用。 在這種情況下，當使用者從內部部署移遷移到雲端，或當您在 中授予 TeamsOnly 模式或 SfBWithTeamsCollabAndMeetings 模式時，MMS 仍然會執行 `TeamsUpgradePolicy` 。

例如，您可能會想要手動遷移所有會議，或暫時停用 MMS，同時大幅變更貴組織的音訊會議設定

若要查看貴組織是否已啟用 MMS，請執行下列命令。 如果參數為 ，MMS `MeetingMigrationEnabled` 即會啟用 `$true` 。
```PowerShell
Get-CsTenantMigrationConfiguration
```
若要完全啟用或停用 MMS，請使用 `Set-CsTenantMigrationConfiguration` 命令。 例如，若要停用 MMS，請執行下列命令：

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
如果組織中已啟用 MMS，而且您想要檢查音訊會議更新是否已啟用 MMS，請檢查 輸出中的 `AutomaticallyMigrateUserMeetings` 參數值 `Get-CsOnlineDialInConferencingTenantSettings` 。 若要啟用或停用音訊會議用 MMS，請使用 `Set-CsOnlineDialInConferencingTenantSettings` 。 例如，若要停用音訊會議用 MMS，請執行下列命令：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>相關主題

[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[在內部部署和雲端之間移動使用者](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)
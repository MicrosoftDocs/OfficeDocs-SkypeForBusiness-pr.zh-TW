---
title: 使用會議遷移服務（MMS）
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: '[會議遷移服務（MMS）] 是在背景執行的服務，會自動更新使用者的商務用 Skype 和 Microsoft 團隊會議。 MMS 的設計目的是要讓使用者不需要執行會議遷移工具來更新其商務用 Skype 和 Microsoft 團隊會議。'
ms.openlocfilehash: 91fcc1b95e107f36a55516e7f459eb8fae581bbe
ms.sourcegitcommit: 0f2024740e03af303efc62e7f54aa918a61ca51b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/06/2019
ms.locfileid: "39890527"
---
# <a name="using-the-meeting-migration-service-mms"></a>使用會議遷移服務（MMS）

會議遷移服務（MMS）是在下列案例中更新使用者現有會議的服務：

- 當使用者從內部部署到雲端時（無論是商務用 Skype Online 或 TeamsOnly）。
- 當系統管理員變更使用者的 [音訊會議] 設定時 
- 線上使用者只升級至小組，或 TeamsUpgradePolicy 中的使用者模式設定為 SfBwithTeamsCollabAndMeetings
- 當您使用 PowerShell 時 


根據預設，雖然系統管理員可以在租使用者層級停用 MMS，但會在每個情況下自動觸發 MMS。 此外，管理員可以使用 PowerShell Cmdlet 來針對特定使用者手動觸發會議遷移。


**限制**：如果下列任何一項適用，則無法使用會議遷移服務：

- 使用者的信箱託管于 Exchange 內部部署中。
- 使用者正從雲端遷移到商務用 Skype Server 內部部署。

在這些情況下，最終使用者可以使用[會議遷移工具](https://www.microsoft.com/en-us/download/details.aspx?id=51659)來遷移自己的會議。

## <a name="how-mms-works"></a>彩信的運作方式

針對特定使用者觸發 MMS 時，該使用者的遷移要求會放在佇列中。 若要避免任何爭用情況，必須在至少90分鐘之後，才會有意處理排隊的要求。 當 MMS 處理要求之後，它會執行下列任務：

1. 它會在該使用者的信箱中搜尋該使用者所組織的所有現有會議，並在將來進行排程。
2. 根據使用者信箱中的資訊，在小組或商務用 Skype Online 中，您可以根據確切的案例，更新或排程新的會議。
3. 在電子郵件訊息中，它會取代會議詳細資料中的 [線上會議] 封鎖。
4. 它會代表會議召集人傳送該會議的更新版本給所有會議收件者。 會議受邀者會收到會議更新，且其電子郵件中有更新的會議座標。 

    ![由 MMS 更新的會議區塊](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

從 MMS 觸發時，通常會花大約2小時的時間，直到使用者的會議被遷移為止。 不過，如果使用者有許多會議，可能需要較長的時間。 如果 MMS 在針對使用者遷移一或多個會議時遇到錯誤，系統會在24小時內定期重試最多9次。

**附注**：

- 當您遷移會議時，MMS 會取代線上會議資訊區塊中的所有專案。 因此，如果使用者已編輯該區塊，就會覆寫他們的變更。 他們在線上會議資訊區塊以外的會議詳細資料中所擁有的任何內容不會受到影響。
- 只要按一下 Outlook 網頁版中的 [**新增 skype 會議**] 按鈕，或使用 Outlook 的 skype 會議增益集，就能遷移已排程的商務用 Skype 或 Microsoft 團隊會議。 如果使用者將 Skype online 會議資訊從一個會議複製並貼到新的會議中，新的會議將無法更新，因為原始服務中沒有會議。
- 已建立或附加至會議的會議內容（白板、投票等）不會在 MMS 執行後保留。 如果您的會議召集人已提前將內容附加到會議，則在 MMS 執行之後，就必須重新建立內容。
- [行事曆] 專案中的共用會議筆記連結以及來自 Skype 會議的連結也會覆寫。 請注意，儲存在 OneNote 中的實際會議筆記仍會保留在其中;只會覆蓋共用筆記的連結。
- 超過250個出席者（包括召集人）的會議將不會被遷移。
- 邀請內文中的部分 UNICODE 字元可能會不正確地更新為下列其中一個特殊字元：ï、¿、1/2。

## <a name="triggering-mms-for-a-user"></a>觸發彩信給使用者

本節說明當您在下列每個情況下會觸發 MMS 時，會發生什麼情況：

- 當使用者從內部部署遷移到雲端時
- 當系統管理員變更使用者的 [音訊會議] 設定時 
- 當 TeamsUpgradePolicy 中的使用者模式設定為 TeamsOnly 或 SfBWithTeamsCollabAndMeetings 時（使用 Powershell 或團隊管理入口網站）
- 當您使用 PowerShell Cmdlet 時，啟動-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>當您將內部部署使用者移至雲端時更新會議

這是最常見的情況，在這種情況下，MMS 可協助為您的使用者建立更順暢的轉場 若沒有會議遷移，當使用者在線上移動時，在商務用 Skype Server 內部網路中由使用者組織的現有會議將無法再運作。 因此，當您使用內部部署系統管理工具（ `Move-CsUser`或 [系統管理] 控制台）將使用者移至雲端時，現有的會議會自動移至雲端，如下所示：

- 如果指定`MoveToTeams`了 [ `Move-CsUser`切換]，會議會直接遷移至 [小組]，而使用者將處於 TeamsOnly 模式。 使用此開關需要使用商務用 Skype Server 2015 搭配 CU8 或更新版本。 這些使用者仍然可以使用商務用 Skype 用戶端或 Skype 會議應用程式，加入他們可能受邀的任何商務用 Skype 會議。
- 否則，會議會遷移到商務用 Skype Online。

在任何一種情況下，如果使用者已獲指派音訊會議授權，然後才移至雲端，則會使用撥入座標建立會議。 如果您將使用者從內部部署移至雲端，而您想要讓該使用者使用音訊會議，建議您先指派音訊會議，然後才會觸發1個會議遷移。


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>在使用者的音訊會議設定變更時更新會議

在下列情況下，MMS 會更新現有的商務用 Skype 和 Microsoft 團隊會議，以新增、移除或修改撥入座標：

- 當您指派或移除 Microsoft 音訊會議服務授權給使用者時，該使用者並未啟用協力廠商音訊會議提供者。
- 當您將使用者的音訊會議提供者從任何其他提供者變更為 Microsoft 時，前提是該使用者已獲指派 Microsoft 音訊會議授權。 如需詳細資訊，請參閱[將 Microsoft 指派為音訊會議提供者](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。 另請注意，對於協力廠商音訊會議提供者 [ACP] 的支援，在2019年4月1日（如前所述）[推出](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers)。
- 當您啟用或停用使用者的音訊會議時。
- 變更或重設已設定為使用公用會議之使用者的會議 ID。
- 當您將使用者移至新的音訊會議橋接器時。
- 從音訊會議橋中取消指派電話號碼時。 這是一個需要額外步驟的複雜情況。 如需詳細資訊，請參閱[在音訊會議橋中變更電話號碼](https://docs.microsoft.com/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。

並非對使用者的音訊會議設定所做的所有變更都會觸發 MMS。 具體說來，下列兩項變更不會導致 MMS 更新會議：

- 當您變更會議召集人的 SIP 位址時（即其 SIP 使用者名稱或 SIP 網域）
- 當您使用`Update-CsTenantMeetingUrl`命令變更組織的會議 URL 時。


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>指派 TeamsUpgradePolicy 時更新會議

根據預設，當使用者被授`TeamsUpgradePolicy`與`mode=TeamsOnly`或`mode= SfBWithTeamsCollabAndMeetings`的情況下，系統會自動觸發會議遷移。 如果您不想要在授與授與會議中的任何一種模式`MigrateMeetingsToTeams $false`時`Grant-CsTeamsUpgradePolicy`遷移會議，請指定 In （如果使用 PowerShell）或取消核取在設定使用者的共存模式時（如果使用 [團隊管理員入口網站]）來遷移會議的方塊。

另請注意下列事項：

- 只有在您授`TeamsUpgradePolicy`與特定使用者時，才會呼叫會議轉移。 如果您是`TeamsUpgradePolicy`在`mode=TeamsOnly` `mode=SfBWithTeamsCollabAndMeetings` *整個租*使用者處授與，則不會呼叫會議遷移。
- 如果使用者是在線上，則只能將 TeamsOnly 模式授與使用者。 您必須使用`Move-CsUser`前面所述的方式來移動駐留內部部署的使用者。
- 授與 TeamsOnly 或 SfBWithTeamsCollabAndMeetings 以外的模式，不會將現有的團隊會議轉換成商務用 Skype 會議。

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>透過 PowerShell Cmdlet 手動觸發會議遷移

除了自動會議遷移之外，系統管理員還可以執行 Cmdlet `Start-CsExMeetingMigration`，手動觸發使用者的會議遷移。 這個 Cmdlet 會將指定使用者的遷移要求排隊。  除了所需`Identity`的參數之外，它還會採用兩個`SourceMeetingType`選擇性`TargetMeetingType`參數，讓您指定如何遷移會議：

**TargetMeetingType:**

- 使用`TargetMeetingType Current` [指定商務用 skype 會議] 會維持商務用 skype 會議，而團隊會議仍保持團隊會議。 不過音訊會議座標可能會變更，且任何內部部署商務用 Skype 會議都會遷移到商務用 Skype Online。 這是 TargetMeetingType 的預設值。
- 使用`TargetMeetingType Teams` [指定無論是否要在商務用 Skype online 或內部部署] 中託管會議，無論是否需要進行任何音訊會議更新，都必須將任何現有的會議遷移至團隊。 

**SourceMeetingType:**
- [ `SourceMeetingType SfB`使用] 表示只需要更新商務用 Skype 會議（無論是內部部署或線上）。
- [ `SourceMeetingType Teams`使用] 表示只應更新團隊會議。
- 使用`SourceMeetingType All`指示必須更新商務用 Skype 會議和團隊會議。 這是 SourceMeetingType 的預設值。
    

下列範例示範如何為使用者 ashaw@contoso.com 啟動會議遷移，以便將所有會議都遷移至團隊：

```
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>管理 MMS

使用 Windows PowerShell，您可以檢查正在進行的遷移狀態、手動觸發會議遷移，以及完全停用遷移。 

### <a name="check-the-status-of-meeting-migrations"></a>檢查會議遷移的狀態

您可以使用`Get-CsMeetingMigrationStatus` Cmdlet 來檢查會議遷移的狀態。 以下是一些範例。

- 若要取得所有 MMS 遷移的摘要狀態，請執行下列命令，以提供所有遷移狀態的表格式視圖：

    ```
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- 若要取得特定時段內所有遷移的完整詳細資料，請使用`StartTime` and `EndTime`參數。 例如，下列命令會傳回從2018年10月1日到2018年10月8日的所有遷移所產生的完整詳細資料。

    ```
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- 若要查看特定使用者的遷移狀態，請使用`Identity`參數。 例如，下列命令會傳回使用者 ashaw@contoso.com 的狀態：

    ```
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
如果您看到任何失敗的遷移，請採取動作來儘快解決這些問題，因為使用者不能撥入由這些使用者組織的會議，直到您解決它們為止。 如果`Get-CsMeetingMigrationStatus`顯示在失敗狀態中的任何遷移，請執行下列步驟：
 
1. 判斷哪些使用者受到影響。 執行下列命令以取得受影響的使用者清單，以及所報告的特定錯誤：

    ```
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. 針對每個受影響的使用者，請執行會議遷移工具以手動遷移其會議。

3. 如果遷移仍無法與會議遷移工具搭配使用，您有兩個選項：

    - 讓使用者建立新的 Skype 會議。
    - [聯絡支援人員](https://go.microsoft.com/fwlink/p/?LinkID=518322)。


### <a name="enabling-and-disabling-mms"></a>啟用及停用彩信

預設會為所有組織啟用 MMS，但您可以將它停用，如下所示：

- 完全停用租使用者。 
- 僅針對與音訊會議相關的變更停用。 在這種情況下，當使用者從內部部署到雲端時，或是當您在中`TeamsUpgradePolicy`授與 TeamsOnly 模式或 SfBWithTeamsCollabAndMeetings 模式時，MMS 仍會執行。

例如，您可能會想要手動遷移所有會議，或暫時停用 MMS，同時對您組織的音訊會議設定進行大量的變更。

若要查看您的組織是否已啟用 MMS，請執行下列命令。 如果`MeetingMigrationEnabled`參數是`$true`，則會啟用 MMS。
```
Get-CsTenantMigrationConfiguration
```
若要完全啟用或停用 MMS， `Set-CsTenantMigrationConfiguration`請使用命令。 例如，若要停用 MMS，請執行下列命令：

```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
如果在組織中啟用 MMS，且您想要檢查是否已啟用音訊會議更新，請核取 [輸出] 中`AutomaticallyMigrateUserMeetings`的參數值`Get-CsOnlineDialInConferencingTenantSettings`。 若要啟用或停用 MMS 以進行音訊`Set-CsOnlineDialInConferencingTenantSettings`會議，請使用。 例如，若要停用 MMS 以進行音訊會議，請執行下列命令：

```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>相關主題

[試用或購買 Office 365 的音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[在內部部署和雲端之間移動使用者](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

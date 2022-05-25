---
title: '使用會議移轉服務 (MMS) '
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 會議移轉服務 (MMS) 是在背景執行，並自動更新使用者商務用 Skype和Microsoft Teams會議的服務。
ms.openlocfilehash: a7e917a5b579c60ff84c3e1a5e6468a28f75faff
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671639"
---
# <a name="using-the-meeting-migration-service-mms"></a>使用會議移轉服務 (MMS) 

會議移轉服務 (MMS) 是在下列案例中更新使用者現有會議的服務：

- 當使用者從內部部署移轉到雲端時。
- 當系統管理員變更使用者的音訊會議設定時
- 當線上使用者升級到僅Teams，或當 Teams 中的使用者模式設定為 SfBwithTeamsCollabAndMeetings 時
- 當您使用 PowerShell 時

根據預設，會在每個案例中自動觸發多媒體簡訊。 此外，系統管理員可以使用 PowerShell Cmdlet 手動觸發特定使用者的會議移轉。

**限制**：如果適用下列任一項，就無法使用會議移轉服務：

- 使用者的信箱裝載于內部部署Exchange。
- 使用者正從雲端移轉到內部部署商務用 Skype Server。

## <a name="how-mms-works"></a>多媒體簡訊的運作方式

當特定使用者觸發多媒體簡訊時，該使用者的移轉要求會列在佇列中。 為了避免任何比賽條件，佇列要求在至少 90 分鐘後才會被刻意處理。 多媒體簡訊處理要求後，便會執行下列工作：

1. 它會搜尋該使用者的信箱，以尋找該使用者召集且未來排程的所有現有會議。
2. 根據使用者信箱中找到的資訊，它會根據確切案例更新或排程該使用者在Teams中的新會議。
3. 在電子郵件訊息中，它會取代會議詳細資料中的線上會議區塊。
4. 它會代表會議召集人將該會議的更新版本傳送給所有會議收件者。 會議受邀者會在電子郵件中收到已更新會議座標的會議更新。

    ![透過多媒體簡訊更新的會議區塊。](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

從觸發多媒體簡訊的時間起，通常需要大約 2 小時，直到移轉使用者的會議為止。 不過，如果使用者有大量會議，可能需要較長的時間。 如果多媒體簡訊遇到移轉使用者一或多個會議的錯誤，則會在 24 小時內定期重試 9 次。

**附注**：

- 移轉會議時，多媒體簡訊會取代線上會議資訊區塊中的所有專案。 因此，如果使用者已編輯該區塊，則會覆寫其變更。 他們在線上會議資訊區塊以外的會議詳細資料中擁有的任何內容都不會受到影響。 這表示附加至會議邀請的任何檔案仍會包含在內。
- 只有按一下網頁Outlook中的 [**新增Skype會議**] 按鈕或使用Outlook Skype 會議增益集來排程的商務用 Skype或Microsoft Teams會議會移轉。 如果使用者將Skype線上會議資訊從一個會議複製並貼到新會議中，則該新會議將不會更新，因為原始服務中沒有會議。
- 在執行多媒體簡訊後，系統將不會保留建立或附加至會議 (白板、投票等) 的會議內容。 如果您的會議召集人事先將內容附加到會議，則必須在 MMS 執行後重新建立內容。
- 行事曆專案中以及Skype會議內的共用會議記錄連結也會被覆寫。 請注意，儲存在OneNote的實際會議記錄仍會存在;它只是覆寫共用記事的連結。
- 超過 250 位出席者的會議 (包括召集人) 將不會移轉。
- 邀請本文中的某些 UNICODE 字元可能會不正確地更新為下列其中一個特殊字元：zh-TW、¿、1/2。

## <a name="triggering-mms-for-a-user"></a>觸發使用者的多媒體簡訊

本節說明在下列每個案例中觸發多媒體簡訊時會發生什麼情況：

- 當使用者從內部部署移轉到雲端時
- 當系統管理員變更使用者的音訊會議設定時
- 當 Teams 中的使用者模式設定為 TeamsOnly 或 SfBWithTeamsCollabAndMeetings (使用 Powershell 或 Teams 管理員 入口網站) 
- 當您使用 PowerShell Cmdlet 時，Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>將內部部署使用者移至雲端時更新會議

這是多媒體簡訊有助於為使用者建立更順暢轉換的最常見案例。 如果沒有會議移轉，使用者在商務用 Skype Server內部部署中召集的現有會議，一旦使用者移至線上，就無法再運作。 因此，當您使用內部部署系統管理工具 (`Move-CsUser` 或管理員 主控台) 將使用者移至雲端時，現有的會議會自動移至雲端並轉換成 TeamsOnly。

如果使用者在移至雲端之前已獲指派音訊會議授權，則會使用撥入座標建立會議。 如果您將使用者從內部部署移至雲端，而您打算讓該使用者使用音訊會議，建議您先指派音訊會議，再移動使用者，這樣只會觸發 1 個會議移轉。

### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>當使用者的音訊會議設定變更時更新會議

在下列情況下，多媒體簡訊會更新現有的商務用 Skype和Microsoft Teams會議以新增、移除或修改撥入座標：

- 當您指派或移除 Microsoft 音訊會議 服務授權給使用者，且該使用者無法使用協力廠商音訊會議提供者時。
- 當您將使用者的音訊會議提供者從任何其他提供者變更為 Microsoft 時，只要使用者獲派 Microsoft 音訊會議授權。 如需詳細資訊，請參閱 [指派 Microsoft 作為音訊會議提供者](./assign-microsoft-as-the-audio-conferencing-provider.md)。 另請注意，協力廠商音訊會議提供者 [ACP] 的支援排定于 2019 年 4 月 1 日結束，如 [先前所宣佈](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md)。
- 當您為使用者啟用或停用音訊會議時。
- 當您變更或重設設定為使用公開會議的使用者的會議 ID 時。
- 當您將使用者移至新的音訊會議橋接器時。
- 未指派音訊會議橋接器的電話號碼時。 這是需要額外步驟的複雜案例。 如需詳細資訊，請參閱 [變更音訊會議橋接器上的電話號碼](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。

並非使用者音訊會議設定的所有變更都會觸發多媒體簡訊。 具體來說，下列兩項變更不會導致多媒體簡訊更新會議：

- 當您變更會議召集人的 SIP 位址時， (他們的 SIP 使用者名稱或 SIP 網域) 
- 當您使用 `Update-CsTenantMeetingUrl` 命令變更組織的會議 URL 時。

### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>在指派 Teams 時更新會議更新 TeamsUpgradePolicy

根據預設，當使用者獲授與或 `mode= SfBWithTeamsCollabAndMeetings` . 的 `TeamsUpgradePolicy` `mode=TeamsOnly` 實例時，會議移轉會自動觸發。 如果您在授與上述任一模式時不想要移轉會議，請在 (中 `Grant-CsTeamsUpgradePolicy` 指定 `MigrateMeetingsToTeams $false` 使用 PowerShell) 或取消核取在設定使用者共存模式時移轉會議的方塊， (使用Teams系統管理入口網站) 。

另請注意下列事項：

- 只有當您授與 `TeamsUpgradePolicy` 特定使用者時，才會叫用會議移轉。 如果您以 `mode=TeamsOnly` 租使用者或 `mode=SfBWithTeamsCollabAndMeetings` *整個租使用者* 為基礎授與 `TeamsUpgradePolicy` ，會議移轉並不會叫用。
- 使用者必須先在線上使用，才能授與 TeamsOnly 模式。 內部部署的使用者必須使用先前所述的使用 `Move-CsUser` 方式移動。
- 授與 TeamsOnly 或 SfBWithTeamsCollabAndMeetings 以外的模式，並不會將現有的Teams會議轉換為商務用 Skype會議。

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>透過 PowerShell Cmdlet 手動觸發會議移轉

除了自動移轉會議之外，系統管理員還可以執行 Cmdlet `Start-CsExMeetingMigration` ，手動觸發使用者的會議移轉。 此 Cmdlet 會為指定的使用者排入移轉要求佇列。  除了必要的 `Identity` 參數以外，還需要兩個選擇性參數， `SourceMeetingType` 以及 `TargetMeetingType` 可讓您指定移轉會議的方式：

**TargetMeetingType：**

- 使用 `TargetMeetingType Current` 指定商務用 Skype會議會保留商務用 Skype會議，而Teams會議會保留Teams會議。 不過，音訊會議座標可能會變更，且任何內部部署商務用 Skype會議都會移轉到 商務用 Skype Online。 這是 TargetMeetingType 的預設值。
- 使用 `TargetMeetingType Teams` 指定任何現有的會議都必須移轉到Teams，不論會議是在線上或內部部署商務用 Skype託管，以及是否需要任何音訊會議更新。

**SourceMeetingType：**

- 使用 `SourceMeetingType SfB` 時表示只商務用 Skype (內部部署或線上) 的會議應該更新。
- 使用 `SourceMeetingType Teams` 表示只應更新Teams會議。
- 使用 `SourceMeetingType All` 表示應該更新商務用 Skype會議和Teams會議。 這是 SourceMeetingType 的預設值。

以下範例示範如何針對使用者 ashaw@contoso.com 起始會議移轉，以便將所有會議移轉到Teams：

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```

## <a name="managing-mms"></a>管理多媒體簡訊

您可以使用Windows PowerShell檢查進行中的移轉狀態、手動觸發會議移轉，以及完全停用移轉。

### <a name="check-the-status-of-meeting-migrations"></a>檢查會議移轉的狀態

您可以使用 `Get-CsMeetingMigrationStatus` Cmdlet 來檢查會議移轉的狀態。 以下是一些範例。

- 若要取得所有 MMS 移轉的摘要狀態，請執行下列命令，提供所有移轉狀態的表格式檢視：

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed        2
    Succeeded   131
    ```

- 若要取得特定時段內所有移轉的完整詳細資料，請使用和 `StartTime` `EndTime` 參數。 例如，下列命令會傳回從 2018 年 10 月 1 日移轉到 2018 年 10 月 8 日的所有移轉的完整詳細資料。

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```

- 若要檢查特定使用者的移轉狀態，請使用參數 `Identity` 。 例如，下列命令會傳回使用者 ashaw@contoso.com 的狀態：

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```

如果您看到任何已失敗的移轉，請採取行動以儘快解決這些問題，因為在您解決之前，其他人將無法撥入這些使用者召集的會議。 如果 `Get-CsMeetingMigrationStatus` 在失敗的狀態下顯示任何移轉，請執行下列步驟：

1. 判斷哪些使用者受到影響。 執行下列命令以取得受影響使用者的清單，以及回報的特定錯誤：

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```

2. 針對每個受影響的使用者，檢閱 LastMessage 屬性的值，以判斷會議移轉失敗的原因，以及要採取的修正動作。 採取矯正動作後，請使用 `Start-CsExMeetingMigration` 上述 PowerShell Cmldet 重新觸發受影響使用者的會議移轉。

3. 如果移轉仍然無法運作，您有兩個選項：

    - 讓使用者建立新的Skype會議。
    - [連絡客戶支援](/microsoft-365/Admin/contact-support-for-business-products)。

Cmdlet `Get-CsMeetingMigrationStatus` 可用來擷取過去 150 天內觸發的移轉狀態。 系統會清除超過 150 天之移轉的記錄。

### <a name="enabling-and-disabling-mms"></a>啟用和停用多媒體簡訊

根據預設，所有組織都會啟用多媒體簡訊，但可以如下所示停用：

- 完全停用租使用者。
- 僅停用音訊會議的相關變更。 在此情況下，當使用者從內部部署移轉到雲端，或當您在 `TeamsUpgradePolicy` 中授與 TeamsOnly 模式或 SfBWithTeamsCollabAndMeetings 模式時，MMS 仍會執行。

例如，您可能會想要手動移轉所有會議或暫時停用多媒體簡訊，同時對貴組織的音訊會議設定進行重大變更。

若要查看您的組織是否已啟用多媒體簡訊，請執行下列命令。 如果參數是 `$true` ， `MeetingMigrationEnabled` 則會啟用多媒體簡訊。

```PowerShell
Get-CsTenantMigrationConfiguration
```

如果在組織中已啟用多媒體簡訊，而您想要檢查是否已啟用音訊會議更新，請檢查輸出 `Get-CsOnlineDialInConferencingTenantSettings` 來源中參數的 `AutomaticallyMigrateUserMeetings` 值。 若要啟用或停用音訊會議的多媒體簡訊，請使用 `Set-CsOnlineDialInConferencingTenantSettings` 。 例如，若要停用音訊會議的 MMS，請執行下列命令：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>相關主題

[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[在內部部署和雲端之間移動使用者](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)

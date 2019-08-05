---
title: 團隊用戶端體驗與共存模式的一致性
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: 團隊用戶端經驗及 comformance 共存模式
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08bc09ac316a41dfe7ff39bc741dbaa514f30044
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2019
ms.locfileid: "36183924"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>團隊用戶端體驗與共存模式的一致性

> [!NOTE]
> 此頁面說明團隊用戶端在任何商務用 Skype 模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 行為中的重要、最近發佈的變更。


共存模式的用途是提供一種簡單且可預測的方式, 讓使用者在公司從商務用 Skype 轉換為小組時, 提供一種簡單且可預知的體驗。  針對組織移至 [團隊], TeamsOnly 模式是每個使用者的最終目的地, 但並非所有使用者都需要同時指派 TeamsOnly (或任何其他模式)。  在使用者進入 TeamsOnly 模式之前, 組織可以使用任何商務用 Skype 模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings), 以確保 TeamsOnly 的使用者和尚不在他們的使用者可以預期地進行通訊。 

當使用者處於任何商務用 Skype 模式時, 所有傳入聊天和通話會傳送到使用者的商務用 Skype 用戶端。 若要避免使用者混淆並確保正確地進行路由, 小組用戶端中的呼叫及聊天功能會在使用者處於任何商務用 Skype 模式時停用。 同樣地, 在使用者處於 SfBOnly 或 SfBWithTeamsCollab 模式時, 小組中的會議排程會明確停用, 且在使用者處於 SfBWithTeamsCollabAndMeetings 模式時明確啟用。   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>團隊用戶端中的可用功能如何根據模式變更
團隊中的可用功能, 取決於使用者的共存模式 (由 TeamsUpgradePolicy 設定)。 下表摘要說明行為:

|使用者的有效模式|團隊用戶端中的體驗|
|---|---|
|任何商務用 Skype 模式|通話和聊天功能已停用。|
|SfBWithTeamsCollabAndMeetings|提供會議排程|
|SfBWithTeamsCollab 或 SfBOnly<sup>1</sup>|無法使用會議排程|
|||

下列螢幕擷取畫面說明 TeamsOnly 或孤島模式與所有其他模式之間的差異。 請注意, [聊天] 和 [呼叫] 圖示可使用 TeamsOnly 或孤島模式 (左螢幕擷取畫面), 但不適用於其他模式 (右側螢幕擷取畫面):

![團隊模式的並排比較](media/teams-mode-comparison.png)


 
**注意:**
<sup></sup>現在, SfBwithTeamsCollab 和 SfBOnly 的行為相同, 但在 SfBOnly 模式中也會停用團隊中的頻道與檔案功能;不過, 目前沒有任何設定可讓團隊中的此項功能停用。


## <a name="impact-of-mode-on-other-policy-settings"></a>模式對其他原則設定的影響
如上所述, 使用者的共存模式會影響使用者的團隊用戶端提供的功能。 這表示 mode 的值可能會優先于其他原則設定的值, 視模式而定。 具體說來, 共存模式會影響是否會遵守下列原則設定:

|**模態 (應用程式)**|**原則。設定**|
|---|---|
|交流|TeamsMessagingPolicy.AllowUserChat|
|通話|TeamsCallingPolicy.AllowPrivateCalling|
|會議排程|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

當您使用 [共存] 模式時, 系統管理員*不*需要明確設定這些原則設定, 但請務必瞭解這些設定在特定模式下的行為方式如下。 

|下|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly 或孤島|後|後|後|後|
|SfBWithTeamsCollabAndMeetings|禁止|禁止|後|後|
|SfBWithTeamsCollab 或 SfBOnly|禁止|禁止|禁止|禁止|
||||||

使用 PowerShell 時, 此`Grant-CsTeamsUpgradePolicy` Cmdlet 會檢查 TeamsMessagingPolicy、TeamsCallingPolicy 和 TeamsMeetingPolicy 中對應設定的設定, 以判斷是否會將這些設定取代 TeamsUpgradePolicy, 如果是,PowerShell 中提供了資訊性訊息。  如上所述, 不需要再設定其他原則設定。 以下是 PowerShell 警告外觀的範例:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a>相關主題

[與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)





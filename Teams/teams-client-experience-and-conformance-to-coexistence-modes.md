---
title: Teams 用戶端體驗和遵從共存模式
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: 瞭解 Teams 用戶端體驗與共存模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e07d33b8aa1b379823ffa3aaa605dc26c31604c5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119252"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Teams 用戶端體驗和遵從共存模式

<a name="about-upgrade-basic"></a>

商務用 Skype 共存模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 的目的是在組織從商務用 Skype 轉換至 Teams 時，為使用者提供簡單且可預測的體驗。  對於移入 Teams 的組織，只有 **Teams** 模式是每個使用者的最終目的地，但並非所有使用者都需要同時指派 **Teams** (或其他) 模式。  在使用者到達 TeamsOnly 模式之前，組織可以使用任何商務用 Skype 共存模式，以確保只有 **Teams** 的使用者與尚未加入團隊的使用者之間可以預測地通訊。 

當使用者使用任何商務用 Skype 模式時，所有傳入的聊天和通話會路由至使用者的商務用 Skype 用戶端。 為了避免使用者混淆並確保適當的路由，當使用者處於任何商務用 Skype 模式時，Teams 用戶端中的通話和聊天功能會停用。 同樣地，當使用者處於 SfBOnly 或 SfBWithTeamsCollab 模式時，Teams 中的會議排程會明確停用，且當使用者處於 SfBWithTeamsCollabAndMeetings 模式時，明確啟用。

由於目前狀態是透過聊天和通話的可及性表示，當聊天和通話停用時，Teams (中的自我目前狀態，也就是說，在使用者圖片的 Teams 用戶端中顯示自己的目前狀態) 也會隱藏。 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Teams 用戶端中的可用功能如何根據模式變更

Teams 中的可用功能取決於使用者的共存模式，如 TeamsUpgradePolicy 所設定。 下表摘要列出行為：

|使用者的有效模式|Teams 用戶端的體驗|
|---|---|
|任何商務用 Skype 模式|通話、聊天和自我目前狀態已停用。|
|SfBWithTeamsCollabAndMeetings|會議排程可供使用|
|SfBWithTeamsCollab 或 SfBOnly<sup>1</sup>|會議排程不可用|
|||

下列螢幕擷取畫面說明 **Teams Only** 或 **Islands** 模式與其他所有模式的差異。 請注意，聊天和通話圖示預設可以使用 **Teams Only** 或Islands 模式 (左側螢幕擷取畫面) ，但不適用於其他模式 (螢幕擷取畫面) ：

![Teams 模式的並排比較](media/teams-mode-comparison.png)

此外，無法在其他模式中使用自我目前狀態，如下所示。

![會議第一次中的自我目前狀態螢幕擷取畫面](media/meetings-first-no-self-presence-general.png)
 
**注意：** 
<sup>1</sup>目前，SfBwithTeamsCollab 和 SfBOnly 的行為相同，但目的在 SfBOnly 模式也會停用 Teams 中的頻道和檔案功能。 在期間，您可以使用應用程式許可權政策隱藏頻道。


## <a name="impact-of-mode-on-other-policy-settings"></a>模式對其他策略設定的影響
如上所述，使用者的並存模式會影響使用者的 Teams 用戶端中可用的功能。 這表示模式的值可能會優先于其他策略設定的值 ，視模式而不同。 具體來說，共存模式會影響是否遵循下列原則設定：

|**應用程式 (模式)**|**Policy.setting**|
|---|---|
|聊天|TeamsMessagingPolicy.AllowUserChat|
|通話|TeamsCallingPolicy.AllowPrivateCalling|
|會議排程|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

系統管理員在使用 *共存* 模式時不需要明確設定這些策略設定，但必須瞭解這些設定在指定模式中的行為方式如下。 

|模式|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly 或 Islands|啟用|啟用|啟用|啟用|
|SfBWithTeamsCollabAndMeetings|禁用|禁用|啟用|啟用|
|SfBWithTeamsCollab 或 SfBOnly|禁用|禁用|禁用|禁用|
||||||

使用 PowerShell 時 `Grant-CsTeamsUpgradePolicy` ，Cmdlet 會檢查 TeamsMessagingPolicy、TeamsCallingPolicy 和 TeamsMeetingPolicy 中的對應設定設定，以判斷這些設定是否由 TeamsUpgradePolicy 取代，若是如此，PowerShell 中會提供資訊訊息。  如上所述，不再需要設定這些其他策略設定。 以下是 PowerShell 警告外觀的範例：

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>相關主題

[使用 Teams 與商務用 Skype 的組織移移和互通性指南](./migration-interop-guidance-for-teams-with-skype.md)
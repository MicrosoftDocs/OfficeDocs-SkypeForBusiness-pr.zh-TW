---
title: Teams 用戶端體驗和遵從共存模式
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: " (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 瞭解 Teams 用戶端體驗和共存模式的一致性。"
ms.localizationpriority: medium
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
ms.openlocfilehash: 91ea07d74bf9b08f627d86191ea08fc0eda1ac4c
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605832"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Teams 用戶端體驗和遵從共存模式

<a name="about-upgrade-basic"></a>

商務用 Skype共存模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 的目的是在組織從商務用 Skype轉換到 Teams 時，為使用者提供簡單且可預測的體驗。  對於移至 Teams 的組織，[ **僅限 Teams** ] 模式是每個使用者的最終目的地，但並非所有使用者都必須 **同時獲指** 派 Teams (或任何其他模式) 。  在使用者進入 TeamsOnly 模式之前，組織可以使用任何商務用 Skype共存模式，以確保 **僅限 Teams** 的使用者與尚未加入 Teams 的使用者之間可預測的通訊。 

當使用者處於任何商務用 Skype模式時，所有傳入的聊天和通話都會路由至使用者的商務用 Skype用戶端。 為了避免使用者混淆，並確保當使用者處於任何商務用 Skype模式時，Teams 用戶端中的正確路由、通話和聊天功能會停用。 同樣地，當使用者處於 SfBOnly 或 SfBWithTeamsCollab 模式，且使用者處於 SfBWithTeamsCollabAndMeetings 模式時，Teams 中的會議排程會明確停用。

由於目前狀態是透過聊天和通話顯示可連線的狀態，當聊天和通話停用時，Teams 中的自我目前狀態 (，使用者圖片中也會隱藏在 Teams 用戶端中顯示自己的目前狀態) 。 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Teams 用戶端中的可用功能如何根據模式變更

Teams 中的可用功能取決於使用者的共存模式，如 TeamsUpgradePolicy 所設定。 下表摘要列出此行為：

|使用者的有效模式|Teams 用戶端的體驗|
|---|---|
|任何商務用 Skype模式|通話、聊天和自我目前狀態會停用。|
|SfBWithTeamsCollabAndMeetings|有可用的會議排程|
|SfBWithTeamsCollab 或 SfBOnly<sup>1</sup>|無法使用會議排程|
|||

下列螢幕擷取畫面說明 **Teams [僅** ] 或 [ **島嶼** ] 模式與所有其他模式之間的差異。 請注意，聊天和通話圖示預設為僅限 **Teams** 或 **群島** 模式使用， (左螢幕擷取畫面) ，但無法使用其他模式 (右螢幕擷取畫面) ：

![Teams 模式的並排比較。](media/teams-mode-comparison.png)

此外，在其他模式中無法使用自我目前狀態，如下所示。

![[會議第一] 中自我目前狀態的螢幕擷取畫面。](media/meetings-first-no-self-presence-general.png)
 
**注意：** 
<sup>1</sup>目前，SfBwithTeamsCollab 和 SfBOnly 的行為相同，但目的在於 SfBOnly 模式也會停用 Teams 中的頻道和檔案功能。 在過渡期中，您可以使用應用程式許可權原則隱藏頻道。


## <a name="impact-of-mode-on-other-policy-settings"></a>模式對其他原則設定的影響
如上所述，使用者的共存模式會影響使用者 Teams 用戶端中可用的功能。 這表示模式的值會優先于其他原則設定的值，視模式而定。 具體來說，共存模式會影響是否遵守下列原則設定：

|**模式 (應用程式)**|**原則。設定**|
|---|---|
|聊天|TeamsMessagingPolicy.AllowUserChat|
|通話|TeamsCallingPolicy.AllowPrivateCalling|
|會議排程|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

系統管理員在使用共存模式時 *，不需要* 明確地設定這些原則設定，但請務必瞭解這些設定在指定模式下的有效行為如下。 

|模式|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly 或群島|Enabled|Enabled|Enabled|Enabled|
|SfBWithTeamsCollabAndMeetings|已停用|已停用|Enabled|Enabled|
|SfBWithTeamsCollab 或 SfBOnly|已停用|已停用|已停用|已停用|
||||||

使用 PowerShell 時， `Grant-CsTeamsUpgradePolicy` Cmdlet 會檢查 TeamsMessagingPolicy、TeamsCallingPolicy 和 TeamsMeetingPolicy 中對應設定的設定，以判斷這些設定是否會由 TeamsUpgradePolicy 取代，如果有的話，PowerShell 會提供資訊訊息。  如上所述，不再需要設定這些其他原則設定。 以下是 PowerShell 警告的外觀範例：

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>相關主題

[搭配使用 Teams 的組織移轉和互通性指導方針商務用 Skype](./migration-interop-guidance-for-teams-with-skype.md)
---
title: 管理參與者和來賓的會議政策
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: 瞭解如何在 Teams 中管理參與者和來賓的會議策略設定。
ms.openlocfilehash: 51d121ab9c537e6ba304045e47b6e875cd98afd6
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598706"
---
# <a name="meeting-policy-settings---participants--guests"></a>會議政策設定 - 參與者&來賓

<a name="bkmeetingparticipants"> </a>

這些設定會控制哪些會議參與者在大廳等候，才能獲准加入會議，以及允許他們參與會議的水準。

- [讓匿名人員開始會議](#let-anonymous-people-start-a-meeting)
- [自動允許人員](#automatically-admit-people)
- [允許撥入使用者跳過大廳](#allow-dial-in-users-to-bypass-the-lobby)
- [啟用即時字幕](#enable-live-captions)
- [允許在會議中聊天](#allow-chat-in-meetings)

> [!NOTE]
>加入會議的選項會因每個 Teams 群組的設定和連接方法而異。 如果您的群組有音訊會議，並使用音訊會議進行連接，請參閱 [音訊會議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。 如果您的 Teams 群組沒有音訊會議，請參閱在 Teams [中加入會議](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。

## <a name="let-anonymous-people-start-a-meeting"></a>讓匿名人員開始會議

此設定是每個召集人的策略，可讓無主席電話撥入式會議。 此設定可控制撥入使用者是否可以加入會議，而組織沒有經過驗證的使用者出席。 根據預設，此設定會關閉，這表示撥入使用者會等候在大廳中，直到組織經過驗證的使用者加入會議。

> [!NOTE]
> 如果這項設定已關閉，且撥入使用者會先加入會議，並置於大廳中，組織使用者必須使用 Teams 用戶端加入會議，以從大廳准許使用者加入會議。 電話撥入的使用者沒有可用的大廳控制項。

## <a name="automatically-admit-people"></a>自動允許人員

這是每個召集人的政策。 此設定可控制人員是直接加入會議，還是等候在大廳中，直到經過驗證的使用者獲准加入會議。 此設定不適用於撥入使用者。

![顯示與大廳使用者開會的螢幕擷取畫面](media/meeting-policies-lobby.png)

 會議召集人可以按一下 **會議** 邀請中的 [會議選項>，針對他們排定的每一個會議變更此設定。

> [!NOTE]
> 在會議選項中，設定標示為「誰可以跳過大廳」。 如果您變更任何使用者的預設設定，它會適用于該使用者組織的所有新會議，以及使用者未修改會議選項的任何先前會議。
  
|設定值  |加入行為 |
|---------|---------|
|**任何人**   |所有會議參與者都直接加入會議，而不需要在大廳等候。 這包括經過驗證的使用者、來自信任組織的外部使用者 (、) 、來賓和匿名使用者。     |
|**貴組織與聯盟組織中的每個人**     |組織中經過驗證的使用者 ，包括來賓使用者和信任組織的使用者，可以直接加入會議，而不需要在大廳等候。  匿名使用者會等候在大廳。   |
|**貴組織中所有人**    |組織內部經過驗證的使用者 ，包括來賓使用者，可以直接加入會議，而不需要在大廳等候。  信任組織的使用者和匿名使用者會等候在大廳。 這是預設設定。           |
|**僅召集人**    |只有會議召集人可以直接加入會議，而不需要在大廳等候。 其他人，包括組織中經過驗證的使用者、來賓使用者、信任組織的使用者和匿名使用者，都必須在大廳等候。           |

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a>允許撥入使用者跳過大廳

這是每個召集人的政策。 此設定可控制以電話撥入的人是直接加入會議，還是等候在大廳中，而不考慮 **自動允許人員** 設定。 根據預設，此設定會關閉。 當這項設定關閉時，撥入使用者會等候在大廳，直到組織使用者與 Teams 用戶端加入會議並准許他們加入會議。 開啟此設定後，撥入使用者會在組織使用者加入會議時自動加入會議。

> [!NOTE]
> 如果撥入使用者在組織使用者加入會議之前加入會議，他們將會放在大廳，直到組織使用者使用 Teams 用戶端加入會議並准許他們加入會議。 如果您變更任何使用者的預設設定，它會適用于該使用者組織的所有新會議，以及使用者未修改會議選項的任何先前會議。

## <a name="enable-live-captions"></a>啟用即時字幕

此設定是每個使用者原則，並適用于會議期間。 此設定可控制使用者是否可以使用開啟即時字幕選項，並關閉使用者參與會議中即時字幕。  

![顯示開啟即時字幕選項的螢幕擷取畫面](media/meeting-policies-live-captions.png)

|設定值 |行為  |
|---------|---------|
|**已停用，但使用者可以重寫**     | 在會議期間，使用者不會自動開啟即時字幕。 使用者會看到溢位區域 **中的** (...) **開啟** 即時字幕選項。 這是預設設定。 |
|**禁用**     | 在會議期間，使用者會停用即時字幕。 使用者沒有開啟的選項。          |

<a name="bkcontentsharing"> </a>

## <a name="allow-chat-in-meetings"></a>允許在會議中聊天

此設定是每個參與者的設定。 此設定可控制使用者會議是否允許會議聊天。

<a name="bkparticipantsandguests"> </a>






## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [將原則指派給 Teams 中的使用者](assign-policies.md)
- [從使用者移除 RestrictedAnonymousAccess Teams 會議政策](meeting-policies-restricted-anonymous-access.md)

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
description: 瞭解如何在會議Teams中管理會議策略設定。
ms.openlocfilehash: 12b5690a39df5081960dce22a335c24673ee8780
ms.sourcegitcommit: b17e5acadcca0261eaccc64e1b4ee457348f975c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/17/2021
ms.locfileid: "58365600"
---
# <a name="meeting-policy-settings---participants--guests"></a>會議原則設定 - 參與者與來賓

<a name="bkmeetingparticipants"> </a>

這些設定可控制哪些會議參與者在獲准加入會議之前在大廳等候，以及允許他們在會議中允許的參與層級。

- [讓匿名人員開始會議](#let-anonymous-people-start-a-meeting)
- [自動准許人員](#automatically-admit-people)
- [允許撥入使用者無需先在大廳等候](#allow-dial-in-users-to-bypass-the-lobby)
- [啟用即時輔助字幕](#enable-live-captions)
- [允許在會議中聊天](#allow-chat-in-meetings)

> [!NOTE]
>加入會議的選項會因每個 Teams 群組的設定和連線方法而有所不同。 如果您的群組有音訊會議，並且使用它來連線，請參閱[音訊會議](/microsoftteams/audio-conferencing-in-office-365)。 如果您的 Teams 群組沒有音訊會議，請參閱[在 Teams 中加入會議](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。

## <a name="let-anonymous-people-start-a-meeting"></a>讓匿名人員開始會議

此設定是每個召集人的策略，可讓無主席電話撥入式會議。 此設定可控制撥入使用者是否可以加入會議，而組織沒有經過驗證的使用者出席。 根據預設，此設定會關閉，這表示撥入使用者會等候在大廳中，直到組織經過驗證的使用者加入會議。

> [!NOTE]
> 如果這項設定已關閉，且撥入使用者會先加入會議，並置於大廳中，組織使用者必須使用 Teams 用戶端加入會議，以從大廳准許使用者加入會議。 撥入的使用者沒有可用的大廳控制項。

## <a name="automatically-admit-people"></a>自動准許人員

這是每一召集人原則。 此設定可控制人員是直接加入會議，還是在大廳中等候，直到由已驗證的使用者准許其加入會議為止。 此設定不適用撥入使用者。

![螢幕擷取畫面顯示有使用者在大廳中的會議](media/meeting-policies-lobby.png)

 會議召集人可以按一下 **會議** 邀請中的 [會議選項>，變更其排程的每一個會議的此設定。

> [!NOTE]
> 在會議選項中，設定會標示為「誰無需先在大廳等候」。如果您變更任何使用者的預設設定，它將會套用至該使用者召集的所有新會議，以及使用者未修改會議選項的任何先前會議。
  
|設定值  |加入行為 |
|---------|---------|
|**每個人**   |所有會議參與者會直接加入會議，而不需在大廳等候。 這包括已驗證的使用者、來自信任組織 (同盟) 的外部使用者、來賓和匿名使用者。     |
|**組織中的人員和來賓**     |組織中經過驗證的使用者 ，包括來賓使用者，可以直接加入會議，而不需要在大廳等候。 信任組織的使用者和匿名使用者在大廳等候。 這是預設設定。    |
|**組織中的人員、信任的組織和來賓**     |組織內已驗證的使用者 (包括來賓使用者和來自信任組織的使用者) 可直接加入會議，而不需在大廳等候。  匿名使用者在大廳中等候。   |
|**組織中的人員**    |組織中經過驗證的使用者直接加入會議，而不需要在大廳等候。  來自信任組織、來賓使用者和匿名使用者的使用者在大廳等候。          |
|**僅限召集人**    |只有會議召集人可直接加入會議，而不需在大廳等候。 其他人，包括組織中經過驗證的使用者、來賓使用者、信任組織的使用者，以及匿名使用者，都必須在大廳等候。 在 Teams會議選項頁面上，會顯示為「僅自己」。          |
|**僅受邀使用者**    |只有受邀的使用者和會議召集人可以直接加入會議，而不必在大廳等候。 其他人，包括組織中經過驗證的使用者、來賓使用者、信任組織的使用者，以及匿名使用者，都必須在大廳等候。 在 Teams會議選項頁面上，會顯示為「我邀請的人」。          |

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a>允許撥入使用者無需先在大廳等候

這是每一召集人原則。 此設定可控制透過電話撥入的人員是否直接加入會議，或是在大廳中等候，而不論 [自動准許人員 **]** 的設定為何。 此設定預設會關閉。 關閉此設定時，撥入使用者將在大廳中等候，直到組織使用者使用 Teams 用戶端加入會議並准許他們加入為止。 開啟此設定時，撥入使用者會在組織使用者加入會議時自動加入會議。

> [!NOTE]
> 如果撥入使用者在組織使用者加入會議之前加入會議，他們將會停留在大廳，直到組織使用者使用 Teams 用戶端加入會議並准許他們加入會議為止。 如果您變更任何使用者的預設設定，它將會套用至該使用者召集的所有新會議，以及使用者未修改會議選項的任何先前會議。

## <a name="enable-live-captions"></a>啟用即時輔助字幕

此設定是每個使用者原則，並適用于會議期間。 此設定可控制使用者是否可使用 [開啟即時輔助字幕 **]** 選項，以在使用者出席的會議中開啟和關閉即時輔助字幕。  

![顯示開啟即時輔助字幕選項的螢幕擷取畫面](media/meeting-policies-live-captions.png)

|設定值 |行為  |
|---------|---------|
|**已停用，但使用者可以覆寫**     | 在會議期間不會自動為使用者開啟即時輔助字幕。 使用者會在溢位 **(...)** 功能表中看到 [開啟即時輔助字幕 **]** 選項，以將其開啟。 這是預設設定。 |
|**已停用**     | 在會議期間會為使用者停用即時輔助字幕。 使用者沒有開啟它們的選項。          |

<a name="bkcontentsharing"> </a>

## <a name="allow-chat-in-meetings"></a>允許在會議中聊天

此設定是每個參與者的設定。 此設定可控制是否在使用者的會議中允許會議聊天。

<a name="bkparticipantsandguests"> </a>






## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [將原則指派給 Teams 中的使用者](assign-policies.md)
- [從使用者移除 RestrictedAnonymousAccess Teams 會議原則](meeting-policies-restricted-anonymous-access.md)

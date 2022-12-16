---
title: 管理參與者和來賓的會議原則
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
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
description: 瞭解如何在 Teams 中管理參與者和來賓的會議原則設定。
ms.openlocfilehash: 42321eb1edadeda928ab0cb9e78e166478b73ed9
ms.sourcegitcommit: 00a526c5b9829302f7c4e0631d0c2dac50b7d004
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2022
ms.locfileid: "69436669"
---
# <a name="meeting-policy-settings---participants--guests"></a>會議原則設定 - 參與者與來賓

<a name="bkmeetingparticipants"> </a>

這些設定可控制哪些會議參與者准許他們進入會議之前在大廳等候，以及允許他們參與會議的程度。

- [讓匿名人員加入會議](#let-anonymous-people-join-a-meeting)
- [讓匿名人員開始會議](#let-anonymous-people-start-a-meeting)
- [誰可以在會議中簡報](#who-can-present-in-meetings)
- [自動准許人員](#automatically-admit-people)
- [撥入式使用者可以略過大廳](#dial-in-users-can-bypass-the-lobby)
- [立即在私人會議中開會](#meet-now-in-private-meetings)
- [即時輔助字幕](#live-captions)
- [在會議中聊天](#chat-in-meetings)
- [Teams Q&A](#teams-qa)
- [會議圖釋](#meeting-reactions)

這些設定位於 Teams 系統管理中心，位於 [**參與者&來賓**] 區段的 [**會議**  >  **會議** 原則] 底下。

> [!NOTE]
> 加入會議的選項會因每個 Teams 群組的設定和連線方法而有所不同。 如果您的群組有音訊會議，並且使用它來連線，請參閱[音訊會議](/microsoftteams/audio-conferencing-in-office-365)。 如果您的 Teams 群組沒有音訊會議，請參閱[在 Teams 中加入會議](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。

## <a name="let-anonymous-people-join-a-meeting"></a>讓匿名人員加入會議

此每個召集人設定可讓任何人以匿名使用者的身分加入會議，方法是選取會議邀請中的連結。 若要深入了解，請參閱[在沒有 Teams 帳戶的情況下加入會議](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508)。 匿名使用者加入會議的能力也會受到貴組織層級的控制，而較嚴格的設定將會有效。 若要深入瞭解，請參[閱使用 Microsoft Teams 系統管理中心來設定整個組織的原則](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)。

## <a name="let-anonymous-people-start-a-meeting"></a>讓匿名人員開始會議

此設定是每個召集人的原則，可召開無前置字元電話撥入式會議。 此設定會控制匿名使用者和撥入式來電者是否可以在未由組織已驗證的使用者出席的情況下加入會議。 根據預設，此設定為關閉，這表示匿名使用者和撥入式來電者會在大廳等候，直到組織中經過驗證的使用者加入會議為止。

> [!NOTE]
> 如果關閉此設定，且撥入式使用者會先加入會議並置於大廳，則組織使用者必須使用 Teams 用戶端加入會議，才能允許使用者進入大廳。 撥入的使用者沒有可用的大廳控制項。

## <a name="who-can-present-in-meetings"></a>誰可以在會議中簡報

這是每一使用者原則。 此設定可讓您變更 Teams 用戶端的 [會議選項 **]** 中 [誰可以簡報?**]** 設定的預設值。 此原則設定會影響所有會議，包括「立即開會」會議。

[誰可以簡報?**]** 設定可讓會議召集人選擇可以成為會議簡報者的人員。 若要深入了解，請參閱[變更 Teams 會議的參與者設定](https://support.microsoft.com/office/53261366-dbd5-45f9-aae9-a70e6354f88e)和 [Teams 會議中的角色](https://support.microsoft.com/office/c16fa7d0-1666-4dde-8686-0a0bfe16e019)。

若要在 Teams 中指定 [ **誰可以簡報？** ] 設定的預設值，請設定為原則中的下列其中一個設定：

- **召集人，但使用者可以覆寫**：只有會議召集人可以是簡報者，所有會議參與者都指定為出席者。 此參數會與 Teams 中的 [只有我 **]** 設定對應。
- **組織中的每個人都可以覆寫，但使用者可以覆寫**：組織中已驗證的使用者，包括來賓使用者，都可以是簡報者。 此設定會對應到 **Teams 中組織設定中的人員**。
- **所有人，但使用者可以覆寫**：所有會議參與者都可以是簡報者。 這是預設值。 此設定會對應到 Teams 中的 [ **所有人** ] 設定。

請記住，在您設定預設值之後，會議召集人仍然可以在 Teams 中變更此設定，並選擇誰可以在其排程的會議中簡報。

## <a name="automatically-admit-people"></a>自動准許人員

這是每一召集人原則。 此設定會控制人員是否直接加入會議，或是在大廳等候，直到經過驗證的使用者准准參加為止。 此設定不適用於撥入式使用者。

![螢幕擷取畫面顯示有使用者在大廳中的會議。](media/meeting-policies-lobby.png)

 會議召集人可以按一下會議邀請中的 [ **會議選項** ]，針對他們排程的每個會議變更此設定。

> [!NOTE]
> In the meeting options the setting is labeled "Who can bypass the lobby". If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.
  
|設定值  |加入行為 |
|---------|---------|
|**每個人**   |所有會議參與者會直接加入會議，而不需在大廳等候。 這包括已驗證的使用者、來自信任組織的使用者、來賓和匿名使用者。     |
|**組織中的人員和來賓**     |組織內經過驗證的使用者，包括來賓，無需在大廳等候即可直接加入會議。 來自信任組織的使用者和匿名使用者會在大廳等候。 這是預設設定。    |
|**組織中的人員、信任的組織和來賓**     |組織內經過驗證的使用者，包括來賓和受信任組織的使用者，無需在大廳等候即可直接加入會議。  匿名使用者在大廳中等候。   |
|**組織中的人員**    |組織內經過驗證的使用者無需在大廳等候，即可直接加入會議。  來自信任組織、來賓和匿名使用者的使用者在大廳等候。          |
|**僅限召集人**    |只有會議召集人可直接加入會議，而不需在大廳等候。 其他人，包括組織內已驗證的使用者、來賓、受信任組織的使用者，以及匿名使用者，都必須在大廳等候。 在 Teams 用戶端會議選項頁面上，它會顯示為「僅自己」。          |
|**僅邀請的使用者**    |只有受邀的使用者和會議召集人可以直接加入會議，而不必在大廳等候。 其他人，包括組織內已驗證的使用者、來賓、受信任組織的使用者，以及匿名使用者，都必須在大廳等候。 在 Teams 用戶端會議選項頁面上，它會顯示為「人員我邀請」。 新增為通訊群組一部分的使用者必須經過大廳。      |

 > [!NOTE]
> 信任的組織是您在 Teams 中允許同盟通訊的網域。 如果您在 Teams 系統管理中心啟用 **[允許外部存取的所有外部網域** ]，任何 Teams 組織內已驗證的使用者都會受到信任。 如果您選擇指定允許並封鎖所有其他的外部網域，則允許的網域會變成信任的組織。 任何封鎖的網域都被視為不是信任的組織。

## <a name="dial-in-users-can-bypass-the-lobby"></a>撥入式使用者可以略過大廳

這是每一召集人原則。 此設定可控制透過電話撥入的人員是否直接加入會議，或是在大廳中等候，而不論 [自動准許人員 **]** 的設定為何。 此設定預設會關閉。 關閉此設定時，撥入使用者將在大廳中等候，直到組織使用者使用 Teams 用戶端加入會議並准許他們加入為止。 開啟此設定時，當組織使用者使用 Teams 用戶端加入會議時，撥入式使用者會自動加入會議。

> [!NOTE]
> 如果撥入使用者在組織使用者加入會議之前加入會議，他們將會停留在大廳，直到組織使用者使用 Teams 用戶端加入會議並准許他們加入會議為止。 如果您變更任何使用者的預設設定，它將會套用至該使用者召集的所有新會議，以及使用者未修改會議選項的任何先前會議。

## <a name="meet-now-in-private-meetings"></a>立即在私人會議中開會

這是每一使用者原則，且會在會議開始之前套用。 此設定可控制使用者是否可以開始非計畫的私人會議。 此設定預設會開啟。

## <a name="live-captions"></a>即時輔助字幕

此設定是個別使用者的原則，會在會議期間套用。 此設定可控制使用者是否可使用 [開啟即時輔助字幕 **]** 選項，以在使用者出席的會議中開啟和關閉即時輔助字幕。  

![顯示開啟即時輔助字幕選項的螢幕擷取畫面。](media/meeting-policies-live-captions.png)

|設定值 |行為  |
|---------|---------|
|**尚未啟用，但使用者可以覆寫**     | 在會議期間不會自動為使用者開啟即時輔助字幕。 使用者會在溢位 **(...)** 功能表中看到 [開啟即時輔助字幕 **]** 選項，以將其開啟。 這是預設設定。 |
|**未啟用**     | 在會議期間會為使用者停用即時輔助字幕。 使用者沒有開啟它們的選項。          |

如需使用者如何開啟 **即時輔助字幕的** 詳細資訊，請參閱 [在 Teams 會議中使用即時輔助字幕](https://support.microsoft.com/office/4be2d304-f675-4b57-8347-cbd000a21260)。

### <a name="live-translated-captions"></a>即時翻譯的輔助字幕

> [!NOTE]
> 這項功能暫時在公開預覽中提供。 預覽之後，會議召集人必須擁有 Teams 進階版授權，出席者才能使用即時翻譯的輔助字幕。

根據預設， **即時輔助字幕** 會以會議期間說出的語言顯示。 **即時翻譯的輔助字幕** 可讓您的使用者看到輔助字幕翻譯成他們最喜歡的語言。

若要啟用 **即時翻譯字幕**， **即時輔助字幕** 必須設定為 **[未啟用]，但使用者可以在** Teams 系統管理中心覆寫。 若要關閉 **即時翻譯字幕**，請將此設定設為 **[未啟用]**。

<a name="bkcontentsharing"> </a>

## <a name="chat-in-meetings"></a>在會議中聊天

這是每個使用者和每個召集人的原則。 此設定可控制是否在使用者的會議中允許會議聊天。 此設定不適用於頻道會議。

|設定值 |行為  |
|---------|---------|
|**為所有人開啟它**     | 所有參與者都可以撰寫和檢視聊天訊息。 |
|**為所有人關閉此功能**     | 所有參與者的會議聊天都已關閉。  |
|**針對除了匿名使用者以外的所有人開啟此功能**     | 匿名參與者的會議聊天寫入存取權僅關閉。  |

一旦 **將會議中的聊天** 原則套用到使用者，召集人就無法透過 **會議選項** 覆寫此原則。

套用至會議召集人的原則可能會影響會議中的其他使用者。 例如：

- 如果召集人將 **[會議中的聊天** ] 設 **為 [為所有人開啟]** ，或是 **針對除了匿名使用者以外的所有人開啟該** 聊天，則會套用使用者的個別原則，而設定 [ **為所有人關閉** 聊天] 的任何使用者將無法在會議中聊天。
- 如果召集人將 **會議中的 [聊天** ] 設 **為 [為所有人關閉]**，則會套用召集人的原則，且沒有人能在會議中聊天。

<a name="bkparticipantsandguests"> </a>

## <a name="teams-qa"></a>Teams Q&A

這是每一召集人原則。 此設定會開啟或關閉 Q&A)  (問題&解答體驗。

此設定會在會議建立或召集人更新時強制執行。 此設定預設會關閉。 深入瞭解 [Teams 會議中的 Q&A](/manage-qna-for-teams)。

參數 QnAEngagementMode 會在 PowerShell 中控制此原則。 Q&A 也可以在 Teams 系統管理中心內進行調整。

|設定值 |行為  |
|---------|---------|
|**開啟**     | 召集人在建立會議時可以新增 Q&A。 |
|**關閉**     | 召集人無法在建立會議時選擇新增 Q&A。  |

## <a name="meeting-reactions"></a>會議圖釋

會議圖釋預設為開啟。 關閉使用者的反應並不表示使用者無法在他們排程的會議中使用反應。 無論預設設定如何，會議召集人仍可從會議選項頁面開啟回應。

## <a name="enable-meeting-policy-settings"></a>啟用會議原則設定

若要啟用會議原則設定，您可以使用 [Teams 系統管理中心](https://admin.teams.microsoft.com/policies/meetings) (**會議原則**  >  **編輯**  >  原則 **參與者&來賓)** 或 Teams PowerShell 中的 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet。 

在此範例中，我們使用 PowerShell 來修改全域會議原則，允許任何人開始或加入會議。

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AutoAdmittedUsers "Everyone" -AllowAnonymousUsersToStartMeeting $True -AllowPSTNUsersToBypassLobby $True
```

設定原則之後，您必須將原則套用至使用者。 如果您修改了全域 (組織的預設) 原則，它會自動套用至使用者。 您必須等候至少 4 小時，任何原則變更才會生效，但最多可能需要 24 小時。


## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [將原則指派給 Teams 中的使用者](policy-assignment-overview.md)
- [從使用者移除 RestrictedAnonymousAccess Teams 會議原則](meeting-policies-restricted-anonymous-access.md)

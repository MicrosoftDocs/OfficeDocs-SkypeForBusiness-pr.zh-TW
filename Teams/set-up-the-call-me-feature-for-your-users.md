---
title: 為您的使用者設定語音來電功能
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何在團隊中設定 [呼叫我] 功能，讓使用者可以透過電話在使用電腦音訊時加入音訊部分。
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d29a517b8df194fe19b9e16554f7c57964177c90
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138013"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>為您的使用者設定語音來電功能

在 Microsoft 團隊中，[**撥號給我**] 功能可讓使用者透過電話加入會議的音訊部分。 這在使用音訊電腦的情況下可能很方便。 使用者透過其手機或土地線，以及會議的內容部分 &mdash; （例如當其他會議參與者分享其螢幕或透過其電腦播放影片），來取得會議的音訊部分 &mdash; 。

> [!IMPORTANT]
> 
> 在大量會議（我們已與 COVID-19 的病毒發作）期間，我們建議使用者按一下 [<strong>加入團隊會議</strong>] 按鈕，而不是使用 PSTN 會議號碼撥入，或使用 [<strong>呼叫我</strong>] 來加入會議。 這有助於在大量會議造成 PSTN 網路擁塞時確保音訊品質。 

> [!IMPORTANT]
> 在 COVID-19 疫情爆發期間，我們建議使用者按一下 [加入 Teams 會議]**** 按鈕，而不要使用 PSTN 會議號碼或使用 [撥號給我]****</strong> 來加入會議。 這主要是因為受到 COVID-19 影響的國家/地區電話語音架構擁塞。 藉由避免 PSTN 通話，您可能會體驗到更好的音質。 

## <a name="the-user-experience"></a>使用者體驗

### <a name="join-a-meeting-by-using-phone-for-audio"></a>使用電話進行音訊加入會議

按一下 [**加入**] 以加入會議，然後按一下 [**選擇您的音訊和影片設定**] 畫面上的 [**電話語音**]。 使用者可以從這裡進行會議呼叫並加入會議，或將其手動撥入會議。

![[電話語音] 選項的螢幕擷取畫面](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**讓小組會議通話**

在 [**使用電話語音通話**] 畫面上，使用者輸入他們的電話號碼，然後按一下 [**呼叫我**]。 會議會呼叫使用者並將他們加入會議。

![[使用電話語音] 畫面上的 [撥號給我] 選項的螢幕擷取畫面](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**手動撥入**

加入的另一種方式是直接撥入會議。 在 [**使用電話語音通話**] 畫面上，按一下 [**手動撥**入]，取得電話號碼的清單，以供撥入會議。

![[手動撥號] 選項的螢幕擷取畫面](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>在會議期間音訊出現問題時，進行回撥

如果使用者在會議期間使用電腦時遇到音訊問題，使用者可以輕鬆地切換到使用電話進行音訊。 團隊會偵測到發生音訊或設備問題的時間，並將使用者重新導向以使用其手機，只要顯示 [**呼叫給我**] 選項即可。

以下是當小組無法偵測到麥克風時，顯示的訊息和 [**撥號給我**] 選項的範例。

![[向我回電] 選項的螢幕擷取畫面](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

使用者按一下 [**回電給我**]，這會顯示 [**使用電話語音**播放] 畫面。 您可以從這裡輸入他們的電話號碼，並讓團隊會議通話，然後將他們加入會議或手動撥入會議。

## <a name="set-up-the-call-me-feature"></a>設定 [撥號給我] 功能

若要為貴組織中的使用者啟用 [撥號給我] 功能，必須進行下列設定：

- 針對組織中排程會議的使用者（會議召集人）啟用音訊會議。 若要深入瞭解，請參閱在小組中[設定音訊會議](set-up-audio-conferencing-in-teams.md)，以及[管理團隊使用者的音訊會議設定](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。

- 使用者可以從會議撥出。 若要深入瞭解，請參閱[管理團隊使用者的音訊會議設定](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。

如果使用者沒有啟用 [從會議撥出]，則無法使用 [撥號**給我**] 選項，而且使用者將不會收到邀請加入會議的電話。 相反地，使用者會在 [**使用電話語音**] 畫面上看到電話號碼清單，讓他們可以用來在手機上手動撥入會議。

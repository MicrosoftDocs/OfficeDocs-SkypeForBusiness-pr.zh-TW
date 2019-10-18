---
title: 為您的使用者設定 [撥號給我] 功能
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何在團隊中設定 [呼叫我] 功能，讓使用者可以在無法使用電腦音訊的情況下，透過電話加入音訊部分。
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8bd9ca9b73d3d2e60b707d0f40ebb1797d4e1a00
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571543"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>為您的使用者設定 [撥號給我] 功能

在 Microsoft 團隊中，[**撥號給我**] 功能可讓使用者透過電話加入會議的音訊部分。 這在使用音訊電腦的情況下可能很方便。 使用者透過其手機或土地線，以及會議&mdash;的內容部分（例如其他會議參與者共用螢幕或透過電腦播放影片&mdash;），取得會議的音訊部分。

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

---
title: 為您的使用者設定語音來電功能
author: cichur
ms.author: v-cichur
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何在 Teams 中設定呼叫我功能，讓使用者在使用電腦進行音訊時，使用電話加入音訊部分。
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 04510a827e9343010c756b14590e9800354c71e9
ms.sourcegitcommit: f979c491af5210e6ceb1d1c00e000767f1a8311d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2021
ms.locfileid: "51623128"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>為您的使用者設定語音來電功能

在 Microsoft Teams 中，呼叫 **我** 功能可讓使用者以電話加入會議的音訊部分。 在可能無法使用音訊電腦的情況下，這項功能非常實用。 使用者透過行動電話或陸上線路取得會議的音訊部分，以及會議的內容部分，例如當另一個會議參與者共用其螢幕或透過電腦播放 &mdash; &mdash; 影片時。

> [!IMPORTANT]
> 
> 在會議密集的時段 (隨著 COVID-19 爆發以來，我們正在經歷的事)，建議使用者按一下 [加入 Teams 會議]<strong></strong> 按鈕，而不要使用 PSTN 會議號碼或使用 [撥號給我]<strong></strong> 來加入會議。 這有助於在會議密集造成 PSTN 網路擁塞時確保音訊品質。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a>使用者體驗

### <a name="join-a-meeting-by-using-phone-for-audio"></a>使用電話進行音訊加入會議

按一下 **[** 加入以加入會議，**然後在**[選擇視音訊和音訊選項畫面上撥打電話音訊，然後按一下 [**立即加入**> 。 使用者可以在這裡進行會議通話並加入會議，或手動撥入會議。

![電話音訊選項的螢幕擷取畫面](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**讓 Teams 會議通話**

在使用 **電話進行音訊** 畫面上，使用者輸入其電話號碼，然後按一下 會議會打電話給使用者，並讓他們加入會議。

![在音訊畫面上使用電話的通話選項的螢幕擷取畫面](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**手動撥入**

另一個加入的方式是直接撥入會議。 在 **[使用電話進行音訊** 播放的畫面上，按一下 [手動撥入以取得要撥入會議的電話號碼清單。

![手動撥入選項的螢幕擷取畫面](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>會議期間音訊發生問題時，請回電

如果使用者在會議期間使用電腦時遇到音訊問題，使用者可以輕鬆地切換到使用手機進行音訊。 Teams 會偵測音訊或裝置問題何時發生，並顯示回電選項，重新導向使用者以使用 **他們的電話。**

以下是當 Teams 未偵測到麥克風時所顯示的訊息和回電選項範例。

![返回選項的螢幕擷取畫面](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

使用者按一下 **呼叫我，** 這可顯示使用 **電話進行音訊** 畫面。 在這裡，他們可以輸入其電話號碼，並撥打 Teams 會議電話，然後加入會議，或手動撥入會議。

## <a name="set-up-the-call-me-feature"></a>設定呼叫我功能

若要為貴組織的使用者啟用呼叫我功能，必須配置下列專案：

- 貴組織中排程會議的使用者會啟用音訊會議 (會議) 。 若要深入瞭解，請參閱 [設定 Teams](set-up-audio-conferencing-in-teams.md) 的音訊會議，以及管理 Teams 中的使用者的音訊會議 [設定](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。

- 會議召集人可以從會議撥出。 若要深入瞭解，請參閱 [在 Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)中管理使用者的音訊會議設定。

如果會議召集人未啟用會議撥出功能，則任何人都無法使用選擇視像和音訊選項畫面上的電話音訊選項，而且其他使用者無法接聽電話加入會議。 對於已啟用撥出功能的使用者，一旦他們加入會議，就可以加入其他人，從顯示參與者圖示撥打 **他們的** 號碼。

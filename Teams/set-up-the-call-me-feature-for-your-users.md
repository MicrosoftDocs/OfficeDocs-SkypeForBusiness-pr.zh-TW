---
title: 為您的使用者設定語音來電功能
author: CarolynRowe
ms.author: crowe
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何在 Teams 中設定 [撥號給我] 功能，讓使用者在無法使用電腦進行音訊時，可以透過電話加入音訊部分。
ms.localizationpriority: medium
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a144e6a751f44ff520ee0317dbbcb390f30abbfd
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794531"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>為您的使用者設定語音來電功能

在 Microsoft Teams 中， **[撥號給我** ] 功能可讓使用者透過電話加入會議的音訊部分。 在可能無法使用電腦處理音訊的情況下，這會派上用場。 使用者可透過行動電話或有線電話取得會議的音訊部分，以及會議 &mdash; 內容部分，例如其他會議參與者共用螢幕或透過電腦播放視 &mdash; 訊時。

> [!IMPORTANT]
> 
> 在會議密集的時段 (隨著 COVID-19 爆發以來，我們正在經歷的事)，建議使用者按一下 [加入 Teams 會議]<strong></strong> 按鈕，而不要使用 PSTN 會議號碼或使用 [撥號給我]<strong></strong> 來加入會議。 這有助於在會議密集造成 PSTN 網路擁塞時確保音訊品質。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a>使用者體驗

### <a name="join-a-meeting-by-using-phone-for-audio"></a>使用電話加入會議的音訊

按一下 **[加入**] 加入會議，然後按一下 [**選擇您的視訊和音訊選項**] 畫面上的 [**電話音訊**]，然後按一下 [**立即加入]**。 使用者可以從這裡撥打會議電話並加入會議，或手動撥入會議。

![[手機音訊] 選項的螢幕擷取畫面。](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**讓 Teams 會議通話**

在 [ **將電話用於音訊** ] 畫面上，使用者輸入其電話號碼，然後按一下 [ **撥號給我]**。 會議會打電話給使用者並加入會議。

![[將電話用於音訊] 畫面上 [撥號給我] 選項的螢幕擷取畫面。](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**手動撥入**

另一個加入方式是直接撥入會議。 在 [ **使用電話進行音訊** ] 畫面上，按一下 **[手動撥入** ]，取得用來撥入會議的電話號碼清單。

![[手動撥入] 選項的螢幕擷取畫面。](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>在會議期間音訊發生問題時取回回電

如果使用者在會議期間使用電腦時遇到音訊問題，使用者可以輕鬆切換到使用手機進行音訊。 Teams 會偵測音訊或裝置何時發生問題，並顯示 [ **回電** ] 選項，將使用者重新導向至使用其手機。

以下是當 Teams 偵測不到麥克風時所顯示的訊息和 [ **回撥號** ] 選項的範例。

![[回電] 選項的螢幕擷取畫面。](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

使用者按一下 **[回撥電話給我**]，顯示 [ **將電話用於音訊** ] 畫面。 從這裡，他們可以輸入電話號碼，並讓 Teams 會議通話加入會議，或手動撥入會議。

## <a name="set-up-the-call-me-feature"></a>設定 [撥號給我] 功能

若要為貴組織中的使用者啟用 [撥號給我] 功能，必須設定下列專案：

- 組織中排程會議的使用者可使用音訊會議 (會議召集人) 。 若要深入瞭解，請參閱 [設定 Teams 的音訊會議](set-up-audio-conferencing-in-teams.md) 和 [管理 Teams 中使用者的音訊會議設定](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。

- 會議召集人可以從會議撥出電話。 若要深入瞭解，請參閱 [在 Teams 中管理使用者的音訊會議設定](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)。

如果會議召集人未啟用會議撥出，則任何人無法使用 [**選擇您的視訊和音訊選項**] 畫面上的 [**電話音訊**] 選項，其他使用者也無法接聽來電加入會議。 對於已啟用撥出功能的使用者，一旦加入會議，他們就可以從 [ **顯示參與者** ] 圖示加入其他人撥打他們的號碼。

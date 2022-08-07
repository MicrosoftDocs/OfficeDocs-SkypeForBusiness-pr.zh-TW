---
title: 記錄管理和轉譯的會議原則
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark
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
- ms.teamsadmincenter.meetingpolicies.recordingandtranscription
description: 瞭解如何在 Teams 中管理會議原則設定，以進行錄製和轉譯。
ms.openlocfilehash: 12f8be910c713a9ce023ac17c956ef50f5889792
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268978"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>記錄&轉錄的會議原則設定

本文將說明錄製和轉譯專用的會議原則設定，包括下列專案：

- [允許轉錄](#allow-transcription)
- [允許雲端錄製](#allow-cloud-recording)
- [儲存您國家或地區以外的錄製內容](#store-recordings-outside-of-your-country-or-region)

## <a name="allow-transcription"></a>允許轉錄

這是每個召集人和個別使用者原則的組合。 此設定可控制在播放會議錄製內容期間是否提供字幕和謄寫功能。 開始錄製的人需要開啟此設定，才能使用這些功能進行錄製。

開啟此設定將建立與會議錄製內容一起儲存的文字記錄，從而在會議錄製內容中啟用 **[搜尋]**、**[CC]** 和 **[文字記錄]**。

錄製會議的轉譯目前僅支援在 Teams 會議中設定語言或說英文的使用者。

## <a name="allow-cloud-recording"></a>允許雲端錄製

此設定結合了每個召集人及個別使用者的原則，並控制是否可以錄製會議。 如果參與者的原則設定已開啟，且對方是來自同一個組織的已驗證使用者，則會議召集人或另一個會議參與者就可以開始錄製。

組織外部人員 (例如，同盟和匿名使用者) 無法開始錄製。 來賓使用者無法開始或停止錄製。

![顯示錄製選項的螢幕擷取畫面](media/meeting-policies-recording.png)

讓我們看看下列範例。

|使用者 |會議原則  |允許雲端錄製 |
|---------|---------|---------|
|Daniela | 全域   | 關閉 |
|Amanda | Location1MeetingPolicy | 開啟|
|John (外部使用者) | 不適用 | 不適用|

- 您無法錄製由 Daniela 召集的會議。
- 拉格無法錄製由 Daniela 召集的會議。
- 您可以錄製由「小組」召集的會議。
- Daniela 無法錄製由 10 月 2 日召集的會議。
- John 無法錄製由[匯入] 召集的會議。

若要深入了解雲端會議錄製，請參閱 [Teams 雲端會議錄製](cloud-recording.md)。

## <a name="store-recordings-outside-of-your-country-or-region"></a>儲存您國家或地區以外的錄製內容

此原則會控制會議記錄是否可以永久儲存在其他國家或地區。 如果已啟用，則無法移轉錄製內容。 如需有關雲端會議以及儲存錄製內容的詳細資訊，請參閱 [Teams 雲端會議錄製](cloud-recording.md)。

## <a name="related-topics"></a>相關主題

- [在 Teams 中指派原則給使用者](policy-assignment-overview.md)
- [雲端會議錄製](cloud-recording.md)
- [Microsoft Teams 中的會議原則和會議到期日](meeting-expiration.md)

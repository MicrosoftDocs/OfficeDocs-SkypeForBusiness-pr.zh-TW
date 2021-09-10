---
title: 管理錄製和文字記錄的會議政策
author: KarliStites
ms.author: kastites
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
description: 瞭解如何在錄製和Teams中管理會議策略設定。
ms.openlocfilehash: c89fc88c46ae8b614021417ab2aa02832f64fce1
ms.sourcegitcommit: 69a5d4994ef75b9c16efa99554fb7f2ee1ccf52a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2021
ms.locfileid: "58973190"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>錄製文字翻譯的會議&設定

本文將說明錄製和文字記錄特有的會議策略設定，包括下列專案：

- [允許轉錄](#allow-transcription)
- [允許雲端錄製](#allow-cloud-recording)
- [儲存您國家/地區以外的錄製內容](#store-recordings-outside-of-your-country-or-region)

## <a name="allow-transcription"></a>允許轉錄

這是每個召集人和每個使用者策略的組合。 此設定可控制在播放會議錄製內容期間是否提供字幕和謄寫功能。 如果您關閉此設定，在播放會議錄製期間，將無法使用搜尋和 **CC** 選項。 開始錄製的人員需要開啟此設定，讓錄製也包含謄寫。

錄製的會議記錄目前僅支援將語言設定為英文或在會議中Teams字幕。

## <a name="allow-cloud-recording"></a>允許雲端錄製

此設定是每個召集人和每個使用者策略的組合，並控制是否可以錄製會議。 如果參與者已開啟策略設定，且他們是來自同一個組織的已驗證使用者，會議召集人或其他會議參與者可以開始錄製。

組織外部人員 (例如，同盟和匿名使用者) 無法開始錄製。 來賓使用者無法開始或停止錄製。

![顯示錄製選項的螢幕擷取畫面](media/meeting-policies-recording.png)

讓我們看看下列範例。

|使用者 |會議原則  |允許雲端錄製 |
|---------|---------|---------|
|Daniela | 全域   | 關閉 |
|Amanda | Location1MeetingPolicy | 開啟|
|John (外部使用者) | 不適用 | 不適用|

- 無法錄製由 Daniela 組織的會議。
- Amanda 無法錄製由 Daniela 組織的會議。
- 您可以錄製由 Amanda 組織的會議。
- Daniela 無法錄製由 Amanda 組織的會議。
- John 無法錄製由 Amanda 組織的會議。

若要深入了解雲端會議錄製，請參閱 [Teams 雲端會議錄製](cloud-recording.md)。

## <a name="store-recordings-outside-of-your-country-or-region"></a>儲存您國家/地區以外的錄製內容

此政策會控制會議記錄是否可以永久儲存在另一個國家/地區。 如果已啟用此功能，則無法移移錄製。 有關雲端會議及錄製儲存位置的資訊，請參閱Teams[會議錄製。](cloud-recording.md)

## <a name="related-topics"></a>相關主題

- [為使用者指派Teams](policy-assignment-overview.md)
- [雲端會議錄製](cloud-recording.md)
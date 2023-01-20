---
title: 無線對講機使用方式與效能報告
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: admin
ms.topic: article
ms.service: microsoft-365-frontline
ms.reviewer: prastogi
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
- tier2
description: 瞭解如何在 Microsoft Teams 系統管理中心使用無線對講機使用方式和效能報告，以取得組織中的無線對講機使用方式概觀。
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 85f92e715efe2b9608691151a08d006816658095
ms.sourcegitcommit: 776820a6c927fafabdfad9f50654fe7648d77bf3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/20/2023
ms.locfileid: "69846046"
---
# <a name="walkie-talkie-usage-and-performance-report"></a>無線對講機使用方式與效能報告

Microsoft Teams 系統管理中心的 [無線對講機使用方式與效能] 報告可讓您概略瞭解組織中的無線 [對講機](../walkie-talkie.md) 活動。 報告提供的資訊包括 (PTT) 傳輸、頻道活動、傳輸持續時間，以及裝置和參與者詳細資料等資訊。

使用此報告以深入瞭解您組織中的無線對講機使用趨勢和效能。 若要存取報表，您必須是全域系統管理員、Teams 系統管理員、全域助讀程式或報表讀者。

## <a name="download-and-view-the-report"></a>下載並檢視報表

1. 在 Microsoft Teams 系統管理中心的左側導覽中，選擇 **[分析&報告**  >  **使用方式報告**。 在 [ **檢視報表]** 索引標籤的 [ **報表**] 底下，選取 [ **無線對講機使用量]**。
1. 在 **[日期範圍]** 底下，選取 7 天或 30 天的日期範圍。 然後，選擇 [ **執行報表]**。
1. 選 **取 [產生報表]**。
1. 在 [ **下載] 索引標籤的** [ **狀態]** 底下，選擇 [ **下載** ] 以下載 CSV 格式的報告。

## <a name="interpret-the-report"></a>解讀報表

報告會提供您在所選取日期範圍內所進行的每個傳輸明細。 以下是報表中包含的資訊。

|欄名稱 |描述 |
|---------|---------|
|TenantId|租使用者識別碼。|
|UserId|使用者識別碼。|
|DeviceId|[裝置識別碼]。|
|ChannelId|進行通訊的無線對講機頻道。|
|clientCallStatus | 表示裝置是否能夠接收傳輸，沒有任何問題。|
|ConversationId|每個 PTT 傳輸的識別碼。|
|TeamId|與使用者連線的無線對講機頻道對應的團隊識別碼。|
|UnreachableParticipantsCount|因為無法接收最近五次傳輸的任何一次，因此被標示為無法連結且隱藏在名冊中的參與者數目。|
|TransmissionDuration| (毫秒內的時間持續時間，) 在服務收到通知時，即有一位參與者即將開始傳輸至服務傳遞最後一個傳輸套件時。|
|TotalParticipantsCount|連線到無線對講機頻道的參與者總數。|
|PacketCount|用來傳送音訊廣播的封包數目。|
|NotifiedParticipants|開始傳輸時傳送推播通知的參與者。 如果裝置與服務之間的連線中斷，系統會傳送通知給裝置，以儘快重新建立連線，因為傳輸即將進行。|
|AudioDurationMilliseconds|傳輸的持續時間為毫秒。|
|ConnectionId|裝置所建立之無線對講機通道的每個連線識別碼。|
|TransmissionStartTime |服務收到第一個音訊封包的日期和時間。
|TransmissionEndTime|服務收到最後一個音訊封包的日期和時間。|
|ParticipantList|傳送傳輸時，連線至通道之裝置的分號分隔清單。|
|CallTimedOut|傳輸是否超過持續時間限制。 這是布林值。|
|平台|裝置作業系統。|
|ParticipantType|無論參與者是傳輸器或傳輸的接收器。|
|WebSocketState|裝置與服務之間的線上狀態是否已在傳輸開始時建立。|
|AppVersion|裝置上安裝的 Teams 應用程式版本。|

## <a name="related-articles"></a>相關文章

- [Teams 中的無線對講機應用程式](../walkie-talkie.md)
- [開始使用無線對講機](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
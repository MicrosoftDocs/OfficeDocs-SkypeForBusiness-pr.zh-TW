---
title: 在 Microsoft Teams 中建立串流
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: 本文將逐步說明建立 Microsoft Teams 串流事件的串流。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: b7ff5d15a08f186ae59ccef65fcd8280d84237d1
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767930"
---
# <a name="create-a-live-event-in-microsoft-teams"></a>在 Microsoft Teams 中建立即時活動

> [!IMPORTANT]
> **中國**：目前，沒有 IT 系統管理員的協助，位於中國的使用者將無法設定或參加 Microsoft Teams 或 Yammer 即時活動或檢視視訊。
>
> 開始之前，請先洽詢您的系統管理員，確認他們是否需要設定 VPN 來連線您的公司網路，讓這些應用程式能在貴組織中順暢地運作。

> [!IMPORTANT]
> 設定即時活動時，建議您在活動開始前 24 小時設定視訊、社群和使用者許可權，以獲得最佳體驗。 這包括新增使用者、更新視訊許可權，以及將社群從私人變更為公開等設定。 特定變更可能需要長達兩 (2) 小時，才會散佈到Microsoft Stream、Microsoft Teams 和 Microsoft Yammer。 允許 24 小時或更久的時間可在需要時提供測試和調整的時間。

## <a name="schedule-the-live-event"></a>排程即時活動

1. 開啟 Microsoft Teams 用戶端並移至行事曆。
1. 使用 [ **新增會議]** 下拉式清單。
1. 選取 **[即時活動]** 選項。
1. 在 [ **新增即時活動** ] 快捷視窗中，將活動詳細資料輸入左 (**[標題**]、[ **位置**]、[ **開始**]、[ **結束**]、[ **時區**]，以及 [ **詳細** 資料]) 。
1. 在同一個頁面右側， **邀請簡報者** 以個別或透過群組新增簡報者和製作人。
1. 輸入所有專案後，選取 **[下一步]**。
1. 在 **即時活動權** 限下，選 **取 [人員和群組**]、[**整個組織**] 或 [**公開**]，指定誰可以觀看即時活動。
1. 選 **取 [Teams Encoder (預覽)** 在 **[您如何產生即時活動？**
1. 在 [活動選項] 底下設定必要的選項 **，例如 Q&A**、 **字幕** 及其他 **選項**。
1. 選 **取 [排程** ] 以完成即時活動的排程。

## <a name="stream-the-live-event"></a>串流即時活動

1. 排程即時活動後，您可以擷取行事曆邀請 [**RTMP In 詳細** 資料] 區段底下的 **RTMP 伺服器擷取 URL** 和 **RTMP 鍵**，以便透過 RTMP Ingest 從 Encoder 推送內容。
1. 若要設定您的編碼器，請將 RTMP 內置 URL 和 RTMP 鍵複製到您的編碼器中，以開始傳送即時編碼器摘要給 Team。 在 Microsoft Teams 中使用編碼器進行即時串流有更多資訊。
1. 使用 Microsoft Teams 用戶端，以製作人身分加入即時活動。 您也可以從更多 ->會議選項找到 RTMP In 詳細資料。
1. 當您開始將內容從編碼器推送到伺服器記憶體點時，您應該會看到製作人預覽更新。
1. 在您滿意您的設定並可在製作人 UI 中查看預覽之後，請從來源選取 **RTMP 摘** 要並 **傳送 Live**。
1. 選 **取 [開始] 活動** 以開始即時活動，張貼哪些觀眾可以看到該活動的文章。
1. 當您完成活動時，請選取製作人 UI 上的 [ **結束活動** ]。 這會結束活動，並讓內容立即可供視訊隨選使用。

如需有關串流即時活動的詳細資訊，請 [檢閱使用 Teams 編碼器產生即時活動](https://support.microsoft.com/office/produce-a-teams-live-event-using-teams-encoder-b0026c9d-fd37-4bb3-bffc-6961f221fbe9)。

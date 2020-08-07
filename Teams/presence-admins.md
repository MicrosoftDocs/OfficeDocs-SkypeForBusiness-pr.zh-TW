---
title: Teams 中使用者的目前狀態
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 瞭解 [團隊] 中的目前狀態，以及目前狀態功能的管理設定。
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2629ef2fd378744647aa7ed158e7128dfbaeba8a
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581204"
---
# <a name="user-presence-in-teams"></a>Teams 中使用者的目前狀態

[目前狀態] 是 Microsoft 團隊中的使用者設定檔的一部分 (與整個 Microsoft 365 或 Office 365) ，可指出使用者目前的可用性與其他使用者的狀態。 依預設，貴組織中任何有使用 Teams 的人都可以 (幾乎即時) 查看其他使用者是否在線上。

Outlook 2013 傳統型應用程式和更新版本支援在 Outlook 中的 Teams 目前狀態。

## <a name="presence-states-in-teams"></a>Teams 中的目前狀態

|使用者設定|應用程式設定|
|:--- |:---|
| ![實心圓圈綠色核取記號，表示目前狀態為有空](media/Presence_Available.png) 有空|![實心圓圈綠色核取記號，表示目前狀態為有空](media/Presence_Available.png) 有空|
|| ![空心圓圈綠色核取記號，表示外出並有空](media/Presence_Available_OOF.png) 有空，外出 |
|  ![紅色實心圓圈，表示忙碌](media/Presence_Busy.png) 忙碌 |  ![紅色實心圓圈，表示忙碌](media/Presence_Busy.png) 忙碌  |
|| ![紅色實心圓圈，表示通話中忙碌](media/Presence_Busy.png) 通話中|
|| ![紅色實心圓圈，表示會議中忙碌](media/Presence_Busy.png) 會議中 |
|| ![紅色空心圓圈，表示忙碌](media/Presence_Busy_OOF.png) 通話中，外出|
|  ![紅色圓圈加白線，表示請勿打擾](media/Presence_DND.png) 請勿打擾 ||
|| ![紅色圓圈加白線，表示簡報中](media/Presence_DND.png) 簡報中|
|| ![紅色圓圈加白線，表示專注](media/Presence_DND.png) 專注|
| ![黃色時鐘圖示，表示離開](media/Presence_Away.png) 離開| ![黃色時鐘圖示，表示離開](media/Presence_Away.png) 離開|
|| ![黃色時鐘圖示，表示離開](media/Presence_Away.png)上次看到的*時間*|
|![黃色時鐘圖示，表示離開，馬上回來](media/Presence_Away.png) 馬上回來| |
|| ![黃色時鐘圖示，表示離開，下班](media/Presence_Away.png)  下班|
|| ![灰色圓圈帶 x，表示離線](media/Presence_Offline.png) 離線 |
|| ![空心灰色圓圈，表示狀態不明](media/Presence_Unknown.png) 狀態不明|
||![空心紅色圓圈加對角斜線，表示已封鎖](media/Presence_Blocked.png) 已封鎖 |
|| ![紫色圓圈加箭號，表示外出](media/Presence_OOF.png) 外出|
|||

App 設定的目前狀態是以使用者活動 (提供，離開) ，Outlook 行事曆狀態 (在會議) 中，或團隊 app 的狀態 (在通話中，提出) 。 請注意，當您是以您的行事曆為基礎的焦點模式時，焦點會是連絡人在 Teans 中看到的狀態，但會在其他產品中顯示為 [請勿打擾]。

當您鎖定電腦或進入 [空閒] 或 [睡眠] 模式時，您的目前狀態會變更為 [離開]。 在行動裝置上，當團隊 app 位於背景時，您的目前狀態會變更為 [離開]。

不管使用者目前狀態為何，都會收到所有在 Teams 中傳送給他們的聊天訊息。 如果他人傳送郵件給使用者時使用者已離線，聊天訊息會在使用者下次上線時顯示在 Teams 中。 如果使用者在 [請勿打擾] 中，使用者仍會收到聊天訊息，但不會顯示橫幅通知。

使用者會在除了 [請勿打擾] 以外的所有目前狀態狀態中接收來電，讓來電移至語音信箱。 如果受話方封鎖來電者，通話將不會傳送，且來電者看到的受話方目前狀態是「離線」。

使用者可以到 Teams 的 [設定]****  >  [隱私權]****，將人員新增至其優先存取清單。 即使使用者在 [請勿打擾] 時，擁有優先順序存取權的人員也可以與使用者取得聯繫。

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>比較商務用 Skype 與 Teams 中的管理設定

下列的商務用 Skype 管理設定與 Teams 不同：

- 在 Teams 中，組織的使用者一律啟用目前狀態共用。 Teams 沒有「隱私權」設定 (您定義誰可查看目前狀態) 。
- Teams 中的使用者一律啟用與所有人 (包括同盟服務) 共用目前狀態。 他們的連絡人清單 (如果他們在商務用 Skype 中有此清單) 會顯示在 [聊天] > [連絡人]**** 底下或在 [通話] > [連絡人]**** 底下。
- Teams 中的使用者一律啟用用戶端的「請勿打擾」和「突破」功能。
- 當 Teams 與 Outlook 整合時，一律為使用者啟用行事曆 (包括外出和其他行事曆資訊) 整合。
- 如果組織也使用商務用 Skype，Teams 中的使用者一律啟用 [上次看到]** 或 [離開時間]**。

> [!NOTE]
> 目前不支援 Teams 系統管理員自訂這些設定的功能。

## <a name="coexistence-with-skype-for-business"></a>與商務用 Skype 共存

請參閱[與商務用 Skype 共存](coexistence-chat-calls-presence.md)，以取得貴組織使用商務用 Skype 時 Teams的運作方式詳細資料。

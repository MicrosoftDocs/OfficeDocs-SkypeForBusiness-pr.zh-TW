---
title: Teams 中的使用者目前狀態
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 有關團隊中目前狀態的管理員資訊。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e0d7ef2fa7ae12f660bf6b77ba7c45a8c49ab10
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863194"
---
# <a name="user-presence-in-teams"></a>Teams 中的使用者目前狀態

目前狀態是 Microsoft 團隊（以及整個 Office 365）中使用者設定檔的一部分，可指出使用者目前的可用性與其他使用者的狀態。 根據預設，您組織中的任何人都可以在線上看到其他使用者（幾乎即時）。

> [!IMPORTANT]
> 如果您在將使用者移至 [僅 Teams]**** 模式之後解除安裝商務用 Skype 用戶端，則 Outlook 和其他 Office應用程式中的目前狀態將會停止運作。 目前狀態在 Teams 中可正常運作。 因應措施：若要在 Outlook （以及其他 Office app）中查看目前狀態，您必須安裝商務用 Skype，即使您是在 [**僅限團隊**] 模式中執行團隊也一樣。 Microsoft 已發現此問題，正在努力解決中。

Outlook 2013 傳統型應用程式和更新版本支援在 Outlook 中的 Teams 目前狀態。

## <a name="presence-states-in-teams"></a>團隊中的目前狀態

團隊中提供的使用者目前狀態為：

|已設定使用者|App 已設定|
|:--- |:---|
| ![穩定綠色核取記號，表示目前狀態為可用](media/Presence_Available.png) 離線|![穩定綠色核取記號，表示目前狀態為可用](media/Presence_Available.png) 離線|
|| ![開啟綠色核取記號，表示有空的 oof](media/Presence_Available_OOF.png) 可用、不在辦公室 |
|  ![實心紅圈，表示忙碌](media/Presence_Busy.png) 狀況 |  ![實心紅圈，表示忙碌](media/Presence_Busy.png) 狀況  |
|| ![實心紅圈，表示通話中的占線](media/Presence_Busy.png) 通話中|
|| ![實心紅圈，表示會議中的忙](media/Presence_Busy.png) 在會議中 |
|| ![開啟紅色圓圈，表示忙碌](media/Presence_Busy_OOF.png) 在通話中，外出|
|  ![紅色圓圈（含白色線條）表示 [請勿打擾]](media/Presence_DND.png) 請勿打擾 ||
|| ![紅色圓圈（含白色線條）表示呈現](media/Presence_DND.png) 介紹|
|| ![紅色圓圈（含白色線條）代表焦點](media/Presence_DND.png) 致力|
| ![黃色時鐘圖示，表示離開](media/Presence_Away.png) 擺脫| ![黃色時鐘圖示，表示離開](media/Presence_Away.png) 擺脫|
|| ![黃色時鐘圖示，表示離開](media/Presence_Away.png)上次查看的*時間*|
|![黃色時鐘圖示，表示離開，立即返回](media/Presence_Away.png) 馬上回來| |
|| ![黃色時鐘圖示，表示 [離開]、[下班中]](media/Presence_Away.png)  關閉工作|
|| ![X 的灰色圓圈表示離線](media/Presence_Offline.png) 處於 |
|| ![開啟灰色圓圈，表示狀態未知](media/Presence_Unknown.png) 狀態未知|
||![以對角線開啟紅色圓圈，表示封鎖](media/Presence_Blocked.png) 受阻 |
|| ![含箭號的紫色圓圈表示不在辦公室](media/Presence_OOF.png) 不在辦公室|
|||
 
使用者可以將目前的目前狀態狀態手動設定為某些選項，而其狀態會反映給所有其他使用者。 更多使用者目前狀態詳細資料也會自動更新。 變更是以使用者活動（可用、離開）、Outlook 行事曆狀態（在會議中），或團隊 app 狀態（在進行中的通話中）來表示，在清單中縮排的狀態。 有15分鐘的非使用中超時，在這段時間之後，目前的目前狀態將會重設為 [離開]。

使用者會收到所有在小組中傳送給他們的聊天訊息，而不管他們的目前狀態為何。 如果使用者是在某人傳送訊息時離線，就會在使用者下次線上時，在小組中出現聊天訊息。 如果使用者處於 [請勿打擾] 狀態，使用者仍會收到聊天訊息，但不會顯示橫幅通知。

使用者會在除了 [請勿打擾] 狀態以外的所有目前狀態狀態中接收來電，讓來電傳送至其語音信箱。 如果收件者封鎖來電者，通話就不會傳送，而且來電者會看到收件者的目前狀態為 [離線]。

使用者可以移至 [小組] 中的 [**設定** > **隱私權**]，將人員新增至他們的優先順序存取清單中。 即使使用者處於 [請勿打擾] 狀態，擁有優先順序存取權的人員也可以與使用者取得聯繫。

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>團隊中與商務用 Skype 相比的系統管理設定

下列系統管理員設定商務用 Skype 在小組中有所不同：

- 在團隊中，組織中的使用者永遠都能啟用目前狀態共用。 隱私權（您定義誰可以查看目前狀態）設定在團隊中無法使用。
- [目前狀態] 與所有人共用（包括同盟服務），將會針對小組中的使用者永遠啟用。 連絡人清單（如果他們在商務用 Skype 中有一個）會顯示在 [**聊天] > 連絡人**] 底下，或 [**通話 > 連絡人**] 下。
- 用戶端的 [請勿打擾] 和 [突破性] 功能永遠都可供團隊中的使用者啟用。
- [行事曆] （包括 [不在辦公室] 和 [其他行事曆資訊]），當團隊與 Outlook 整合時，就會為使用者啟用整合。
- 如果組織也使用商務用 Skype，則 [*上次看到*] 或 [*離開*] 時，會針對小組中的使用者永遠啟用指標。

> [!NOTE]
> 團隊系統管理員自訂這些設定的能力目前不受支援。

## <a name="coexistence-with-skype-for-business"></a>與商務用 Skype 共存

請參閱[與商務用 Skype 共存](coexistence-chat-calls-presence.md)，以取得貴組織也使用商務用 skype 時，小組目前狀態如何運作的詳細資料。

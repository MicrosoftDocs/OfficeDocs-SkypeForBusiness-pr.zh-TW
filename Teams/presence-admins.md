---
title: 團隊中的使用者目前狀態
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 有關團隊中目前狀態的管理員資訊。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0bd57165cbb88df135827ae72fa3952dd8ddd452
ms.sourcegitcommit: 299f854bbb73887ba315b09b9adf9ea9ff91e8ec
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37062958"
---
# <a name="user-presence-in-teams"></a>團隊中的使用者目前狀態

目前狀態是 Microsoft 團隊（以及整個 Office 365）中使用者設定檔的一部分，可指出使用者目前的可用性與其他使用者的狀態。 根據預設，您組織中的任何人都可以在線上看到其他使用者（幾乎即時）。

> [!IMPORTANT]
> 如果您在將使用者移至 [**僅限團隊**] 模式之後卸載商務用 Skype 用戶端，目前狀態將會在 Outlook 和其他 Office app 中停止運作。 [目前狀態] 在小組中可以正常運作。 因應措施：若要在 Outlook （以及其他 Office app）中查看目前狀態，您必須安裝商務用 Skype，即使您是在 [**僅限團隊**] 模式中執行團隊也一樣。 Microsoft 已注意到這個問題，正在努力解決問題。

## <a name="presence-states-in-teams"></a>團隊中的目前狀態

團隊中提供的使用者目前狀態為：

|已設定使用者|App 已設定|
|:--- |:---|
| ![穩定綠色核取記號，表示目前狀態為可用](media/Presence_Available.png) 離線|![穩定綠色核取記號，表示目前狀態為可用](media/Presence_Available.png) 離線|
|| ![開啟綠色核取記號，表示有空的 oof](media/Presence_Available_OOF.png) 可用、不在辦公室 |
|  ![實心紅圈，表示忙碌](media/Presence_Busy.png) 狀況 |  ![實心紅圈，表示忙碌](media/Presence_Busy.png) 狀況  |
|| ![實心紅圈，表示通話中的占線](media/Presence_Busy.png) 在通話中|
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
 
使用者可以將目前的目前狀態狀態手動設定為某些選項，而其狀態會反映給所有其他使用者。 更多使用者目前狀態詳細資料也會自動更新。 變更是以使用者活動（可用、離開）、Outlook 行事曆狀態（在會議中），或團隊 app 狀態（在進行中的通話中）來表示，在清單中縮排的狀態。

有15分鐘的非使用中超時，在這段時間之後，目前的目前狀態將會重設為 [離開]。

使用者可以指定誰可以中斷流覽（無論 [請勿打擾] 狀態，也表示與他們聯絡）。 [團隊用戶端] 提供這些設定。

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>團隊中與商務用 Skype 相比的系統管理設定

下列系統管理員設定商務用 Skype 在小組中有所不同：

- 在團隊中，組織中的使用者永遠都能啟用目前狀態共用。 隱私權（您定義誰可以查看目前狀態）設定在團隊中無法使用。
- [目前狀態] 與所有人共用（包括同盟服務），將會針對小組中的使用者永遠啟用。 連絡人清單（如果他們在商務用 Skype 中有一個）會顯示在 [**聊天] > 連絡人**] 底下，或 [**通話 > 連絡人**] 下。
- 用戶端的 [請勿打擾] 和 [突破性] 功能永遠都可供團隊中的使用者啟用。
- [行事曆] （包括 [不在辦公室] 和 [其他行事曆資訊]），當團隊與 Outlook 整合時，就會為使用者啟用整合。
- 如果組織也使用商務用 Skype，則 [*上次看到*] 或 [*離開*] 時，會針對小組中的使用者永遠啟用指標。

> [!NOTE]
> 團隊系統管理員自訂這些設定的能力目前不受支援。

## <a name="coexistence-with-skype-for-business"></a>在商務用 Skype 中共存

請參閱[與商務用 Skype 共存](coexistence-chat-calls-presence.md)，以取得貴組織也使用商務用 skype 時，小組目前狀態如何運作的詳細資料。

---
title: 郵件委派
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: 使用者可以將另一個使用者明確地設定為其狀態訊息中的代理人。
ms.openlocfilehash: 451577ce033f9a67bbc13ebbe2361083ab035e48
ms.sourcegitcommit: 66213b972920b4e09faf7d7e732c4bfe7b322ac4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/21/2019
ms.locfileid: "36184173"
---
# <a name="message-delegation"></a>郵件委派

使用者可以已明確將其狀態設為 [離開] 或 [請勿打擾], 並提供自訂文字。 郵件委派功能的運作方式如下:

1. 使用者 @username 在部分文字狀態訊息中提及另一個使用者, 建議您在他們無法使用的人, 請與 @username 提及的使用者聯繫。
2. 獲指派為代理人的人員會收到通知, 告知他們已指定為代理人。
3. 嘗試與第一個使用者聯繫的人, 可以將游標暫留在已命名的代理人上, 並輕鬆地以訊息傳送給代理人。  

這是用戶端中的使用者啟動的程式, 且不需要系統管理員參與即可啟用該功能。 

## <a name="delegation-use-scenario-in-healthcare"></a>醫療保健中的委派使用案例

*使用範例, 不需設定代理人:* Franco Piccio 是在放射式部門撥打。 他會收到一則緊急的個人通話, 且必須移出幾個小時的時間。 他在放射科中要求一位對等的人, 即 Lena Ehrle, 以在他離開時掩蓋給對方。 他非正式地將呼叫器移至 Ehrle, 他們會在呼叫器上接聽緊急訊息和 ping, 並在她的目前職責中代表 Piccio 回復。 小組中的其他人可能無法實現非正式的委派, 且 ensues 患者的護理。

*設定代理人的用法範例:* Franco Piccio 是在放射式部門撥打。 他會收到一則緊急的個人通話, 且必須移出幾個小時的時間。 他在放射科中要求一位對等人, Lena Ehrle, 以在他離開時掩蓋給對方。 他將自己的自訂狀態訊息變更為「無法在未來數小時內取得的內容。 請聯絡 @DrEhrle 以取得任何緊急情況。  小組中的其他人在嘗試聯絡 Piccio 時, 就會立即取得委派, 所以他們現在知道要與 Dr. Ehrle。 Ensues 患者的護理, 幾乎無任何混淆。

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>團隊用戶端中使用者狀態的共存模式的影響

系統管理員應注意, 狀態筆記和委派提及的行為會部分依賴于使用者的共存模式。 這個矩陣顯示的可能性如下:

|共存模式 | 預期行為|
|---|---|
|TeamsOnly |使用者只能從小組設定記事。 <br> 在團隊 & SfB 中會顯示使用者的小組記事。 |
|索羅門群島 | 小組中的使用者記事集只能在 [團隊] 中看到。 <br> SfB 中的使用者記事集只能在 SfB 中看到 |
|SfB * 模式 | 使用者只能從 SfB 設定記事。 <br> 使用者的 SfB 附注會顯示在 [SfB & 的小組中。  |
|||

如果使用者的模式是 TeamsOnly 或孤島, 就只能在團隊中設定記事。  

### <a name="displaying-notes-set-in-skype-for-business"></a>在商務用 Skype 中顯示 [備忘稿] 設定
  
沒有從商務用 Skype 設定記事的視覺指示。

商務用 Skype 不會對狀態筆記強制進行字元限制。 Microsoft 團隊只會從商務用 Skype 顯示記事集的前280個字元。 筆記結尾的省略號 (...) 會指出截斷。
  
商務用 Skype 不支援記錄的到期時間。

當使用者升級至 TeamsOnly 模式時, 不支援從商務用 Skype 將筆記遷移至團隊。

## <a name="related-topics"></a>相關主題

[在商務用 Skype 中共存](../../coexistence-chat-calls-presence.md)

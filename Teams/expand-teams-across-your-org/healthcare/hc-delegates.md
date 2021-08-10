---
title: 訊息委派
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: 了解狀態為 [離開] 或 [請勿打擾] 的使用者如何在狀態訊息中明確地將另一個使用者設定為代理人。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 967ed83f89d991ad001dbac9001d4d20b412efec80f0edb5bf4caca77e487a87
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276528"
---
# <a name="message-delegation"></a>訊息委派

使用者可以明確將狀態設定為 [離開] 或 [請勿打擾] ，並提供自訂文字。 郵件委派功能運作方式如下：

1. 使用者透過「@使用者名稱」在文字狀態訊息的一部分提及另一位使用者，表示當使用者無法連絡到他們時，請改為聯絡「@使用者名稱」所提及的使用者。
2. 獲指派為代理人的人會收到通知，告知他們已被指定為代理人。
3. 接著，嘗試連絡第一位使用者的使用者可以將游標停留在指定的代理人上方，並輕鬆地改為以訊息通知代理人。  

這是一項使用者自行在用戶端中啟動的進程，而不需要系統管理員介入來啟用此功能。 

## <a name="delegation-use-scenario-in-healthcare"></a>醫療保健中的委派使用案例

*未設定代理人的使用範例：* Franco Piccio 醫生在放射學部門值班。 他接到緊急個人電話，必須離開幾小時。 他要求放射學部門的其中一位同僚 Lena Ehrle 醫生在離開時為他代班。 他非正式地將自己的呼叫器給 Ehrle 醫生，後者在她目前的職責之外，還負責聆聽緊急訊息和在呼叫器上偵測，並代表 Piccio 醫生回應他們。 團隊中的其他人可能不知道這項非正式委派，而在病患的照護上造成混淆。

*設定代理人的使用範例：* Franco Piccio 醫生在放射學部門值班。 他接到緊急個人電話，必須離開幾小時。 他要求放射學部門的其中一位同僚 Lena Ehrle 醫生在離開時為他代班。 他變更了自訂狀態訊息，內容類似於「我接下來幾個小時人不在。 如有任何緊急狀況，請聯絡 @DrEhrle。」  團隊中的其他人在嘗試與 Piccio 醫生聯繫時，得知這項委派，因此他們現在知道要與 Ehrle 醫生聯繫。 對於病患的照護，幾乎未造成混淆。

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>共存模式對 Teams 用戶端中使用者狀態的影響

系統管理員應注意，狀態備註和委派提及行為會部分取決於使用者的共存模式。 此矩陣顯示可能性：

|共存模式 | 預期的結果|
|---|---|
|TeamsOnly |使用者只能從 Teams 設定備註。 <br> 使用者的 Teams 備註可在 Teams 和 SfB 中看見。 |
|Islands | 在 Teams 中設定的使用者備註只能在 Teams 中顯示。 <br> 在 SfB 中設定的使用者備註只能在 SfB 中顯示 |
|SfB* 模式 | 使用者只能從 SfB 設定備註。 <br> 使用者的 SfB 備註可在 SfB 和 Teams 中看見。  |
|||

使用者只有在其模式為 TeamsOnly 或 Islands 時，才能在 Teams 中設定備註。  

### <a name="displaying-notes-set-in-skype-for-business"></a>顯示在商務用 Skype 中設定的備註
  
並無視覺效果可表示備註是在商務用 Skype 中所設定。

商務用 Skype 不會在狀態資訊上強制執行字元限制。 Microsoft Teams 只會顯示在商務用 Skype 中所備註的前 280 個字元。 備註結尾的省略號 (...) 表示截斷。
  
商務用 Skype 不支援備註的到期時間。

當使用者升級至 TeamsOnly 模式時，不支援將備註從商務用 Skype 移轉至 Teams。

## <a name="related-topics"></a>相關主題

[與商務用 Skype 共存](../../coexistence-chat-calls-presence.md)

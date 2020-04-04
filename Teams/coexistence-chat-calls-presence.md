---
title: 與商務用 Skype 共存
author: kenwith
ms.author: kenwith
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
description: 團隊 & 商務用 Skype 的共存行為，包括路線參數、聊天 & 通話路由、聊天 & 來自預先存在的執行緒的通話，& 目前狀態。
ms.openlocfilehash: ff5e94b16cd55374ec0aeb45aaffdda41fbe0498
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137303"
---
# <a name="coexistence-with-skype-for-business"></a>與商務用 Skype 共存

商務用 Skype 與團隊用戶端與使用者之間的共存與互通性是由 TeamsUpgrade 模式所定義，且[與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南](migration-interop-guidance-for-teams-with-skype.md)中所述。

任何指定的使用者，都會依預設或由系統管理員明確指派 TeamsUpgrade 模式。 預設值為 [*孤島*]。 已升級至團隊的使用者具有*TeamsOnly*模式。 *SfBOnly*、 *SfBWithTeamsCollab*和*SfBWithTeamsCollabAndMeetings*也是可能的模式。


## <a name="routing-parameters"></a>路由參數

收件者的 TeamsUpgrade 模式是在租使用者內和同盟租使用者之間，決定聊天、通話和目前狀態的行為的關鍵。

如果寄件者是使用小組，則在建立新的交談線索時會進行路由決定。 團隊中的現有交談執行緒總是保留在建立執行緒時所決定的路由方法：團隊支援持久性執行緒。

 執行緒路由方法包括：  

- 團隊在租使用者中的*原生*小組交談
- 團隊在租使用者中進行商務用 Skype 交談的*交互操作*性
- *針對租使用者進行聯盟交談*的同盟

決定執行緒路由方法的參數如下：

- 收件者的 TeamsUpgrade 模式
- 寄件者所用的用戶端
- 交談為新的或現有的執行緒的一部分
- 交談是否為租使用者或同盟
- 是否可以進行交談
    - *在租*使用者互通性要求租使用者是純線上或商務用 Skype 混合式。 純粹內部部署承租人不能有租使用者互通性。
    - *跨租使用者同盟*總是需要正確的商務用 Skype 同盟設定，以及來自兩個承租人的正確團隊同盟設定。 在任何一種租使用者中都不需要商務用 Skype 混合式。
    - 如果始發者的商務用 Skype 帳戶是駐留在內部部署的，該使用者就無法使用 [團隊用戶端] 來進行租使用者互通性或同盟。 該使用者只能使用商務用 Skype 用戶端進行互通性與同盟。
    - 團隊若要在租使用者中進行團隊溝通，請務必這樣做。

> [!NOTE]
> 如果收件者和寄件者都在 TeamsOnly 升級模式中，則交談將是一個固有的聊天體驗，包括所有豐富的訊息和呼叫功能。 若要深入瞭解，請閱讀[小組外部（同盟）使用者的原生聊天體驗](native-chat-for-external-users.md)。 如果其中一個交談參與者不在 TeamsOnly 升級模式中，則交談仍會有純文字訊息的交互操作體驗。

## <a name="chat-and-call-routing"></a>聊天和通話路由

### <a name="in-tenant-routing-for-new-chats-or-calls"></a>新聊天或通話的租使用者內路由 

下表會捕獲受租使用者的聊天和通話的路由，而且對於不是從預先存在的執行緒開始的新通話或聊天而言，都是有效的。 它描述哪個用戶端會收到新的通話或聊天（如果左側的使用者產生）至右側的租使用者收件者。

傳送給 TeamsOnly 使用者的郵件將永遠會傳送給團隊。 傳送給 SfB\*使用者的郵件將會一直路由到商務用 Skype （如果有的話），如上述所述。 傳送給孤島使用者的訊息，永遠會傳送到傳送給他們的同一個用戶端。

下表顯示在指定模式中，哪個用戶端會收到來自始發者的呼叫（三個最左邊的欄），這取決於始發者的模式、用戶端，以及其商務用 Skype 用戶端（在內部部署或線上）的駐留位置。

在下列資料表中： 
- **SfB\* **代表下列任何一種模式： *SfBOnly*、 *SfBWithTeamsCollab*、 *SfBWithTeamsCollabAndMeetings*。

- *斜體文字*會醒目提示交互操作交談。

- **無法**代表無法進行聊天或通話的情況。 發信方必須使用商務用 Skype，而不是在這些情況下。 這是 Microsoft 對內部部署/混合式客戶的規範性指導方針的其中一個原因，就是使用孤島以外的模式（通常是 SfBWithTeamsCollab）做為小組的升級歷程起點。

**資料表1a：租使用者新聊天或呼叫路由至孤島模式收件者**

| <br/><br/> 下 | 觸發器 <br/><br/> 用戶端 | <br/><br/> SfB&nbsp;宿主 | | 人 <br/><br/> 離島  |
|--- |--- |--- |--- |--- |
| 離島 | Teams <br/> 商務用 Skype<br/> Teams<br/> 商務用 Skype| Online<br/> Online<br/> 內部部署<br/>內部部署| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Teams <br/> 商務用 Skype<br/> Teams<br/> 商務用 Skype|
|SfB\* <br/> | 商務用 Skype<br/>商務用 Skype<br/> | Online<br/> 內部部署<br/> |&boxv;<br/>&boxv;|商務用 Skype<br/>商務用 Skype<br/>|
|TeamsOnly |Teams| Online<br/>|&boxv;<br/>|Teams|
| | | | | |

**資料表1b：在租使用者的新聊天中，或以 SfB\*模式呼叫路由至收件者**

| <br/><br/> 下   | 觸發器 <br/><br/> 用戶端 | <br/><br/> SfB&nbsp;宿主 | |   人 <br/><br/> SfB\*   |
|--- |--- |--- |---   |--- |
| 離島 |Teams<br/>商務用 Skype<br/>Teams <br/>商務用 Skype  |Online<br/> Online<br/> 內部部署<br/> 內部部署<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *商務用 Skype* <br/> 商務用 Skype<br/> **無法進行** <br/>商務用 Skype<br/> |
|SfB\* <br/> | 商務用 Skype<br/>商務用 Skype<br/> | Online<br/> 內部部署<br/> |&boxv;<br/>&boxv; |  商務用 Skype<br/>商務用 Skype<br/> |
|TeamsOnly |Teams| Online<br/>|&boxv;<br/> |  *商務用 Skype* <br/>| 
| | | | | |

**資料表1c：租使用者新聊天或呼叫路由至 TeamsOnly 模式收件者**

| <br/><br/> 下   | 觸發器 <br/><br/> 用戶端 | <br/><br/> SfB&nbsp;宿主 | |   人 <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| 離島   |Teams<br/>商務用 Skype<br/>Teams <br/>商務用 Skype<br/>|Online<br/> Online<br/> 內部部署<br/> 內部部署<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Teams <br/>*團隊* <br/>Teams <br/>*團隊*  |
|SfB\*  | 商務用 Skype<br/>商務用 Skype<br/> | Online<br/> 內部部署<br/> | &boxv;<br/>&boxv; | *團隊*  <br/>*團隊*   |
|TeamsOnly  | Teams | Online |  &boxv; |Teams   |
|  |  |  | | |

### <a name="federated-routing-for-new-chats-or-calls"></a>新聊天或通話的聯盟路由
  
下表會捕獲同盟通話與聊天的路由，且適用于新的通話或聊天。 它們說明哪個用戶端會收到新的通話或聊天（如果是由左邊的使用者發起）到右側的聯盟目標使用者。

在摘要中，如果可以如上所述進行交談，傳送給 TeamsOnly 使用者的訊息將永遠位於小組中;傳送給 SfB\*使用者的郵件將永遠居住在商務用 Skype 中;傳送給孤島使用者的訊息，無論傳送給您的客戶，都永遠會在商務用 Skype 中進行土地。 聯盟聊天和通話的路由與在該孤島中的租使用者內路由不同，在商務用 Skype 中，將永遠會收到聯盟通訊。

這是因為我們無法假設聯合商務用 Skype 合作夥伴已在使用孤島模式時使用團隊。 [孤島] 是預設模式，但我們無法假設所有孤島使用者都執行團隊。 透過傳送到商務用 Skype，我們可以確保沒有孤島的通訊失敗。 如果我們路由至團隊，如果目標不是使用小組，就可能會錯過該通訊。 [路由到商務用 Skype] 可確保郵件永遠收到。  

> [!NOTE]
> 目前的團隊同盟實現是以商務用 Skype 同盟為基礎，因此它會利用互通性基礎結構（需要始發者的租使用者是純線上或商務用 Skype 混合式），並提供一組與原生執行緒較少的功能。 我們預期會在將來為團隊同盟提供原生團隊，此時，該執行緒就會成為原生，並提供完整功能。

下表說明哪個用戶端會接收來自始發者的呼叫（三個最左邊的欄），這取決於發信方的模式、用戶端，以及其商務用 Skype 用戶端的駐留位置（內部部署或線上）。

**表格2a：同盟新聊天或通話路由至孤島收件者**

| <br/><br/>下   | 觸發器<br/><br/> 用戶端| <br/><br/>SfB 宿主| | 人<br/><br/> 離島 |
|--- |--- |--- |--- |--- |
| 離島 |Teams<br/>商務用 Skype <br/>Teams <br/>商務用 Skype  |Online<br/> Online<br/> 內部部署<br/> 內部部署<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *商務用 Skype* <br/> 商務用 Skype <br/> **無法進行**   <br/> 商務用 Skype |
| SfB\* |商務用 Skype <br/>商務用 Skype |Online<br/> 內部部署<br/> | &boxv;<br/>&boxv;|商務用 Skype <br/>商務用 Skype |
| TeamsOnly |Teams |Online| &boxv;|*商務用 Skype* |
|  | | | | 

**表格2b：同盟新聊天或通話以 SfB\*模式傳送給收件者**

| <br/><br/>下   | 觸發器<br/><br/> 用戶端| <br/><br/>SfB 宿主| |  人<br/><br/> SfB\* |  
|--- |--- |--- |--- |--- |
| 離島 |Teams<br/>商務用 Skype <br/>Teams <br/>商務用 Skype <br/>|Online<br/> Online<br/> 內部部署<br/> 內部部署<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *商務用 Skype* <br/> 商務用 Skype <br/> **無法進行** <br/>商務用 Skype <br/> |  
| SfB\* |商務用 Skype <br/>商務用 Skype  |Online<br/> 內部部署<br/>  |&boxv;<br/>&boxv; | 商務用 Skype <br/>商務用 Skype  |
| TeamsOnly | Teams|Online |&boxv; |*商務用 Skype*  |
|  | | | | |

**表格2c：同盟新聊天或呼叫路由至 TeamsOnly 模式收件者**

| <br/><br/>下 | 觸發器<br/><br/> 用戶端| <br/><br/>SfB 宿主| |  人<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| 離島  |Teams<br/>商務用 Skype <br/>Teams <br/>商務用 Skype <br/>|Online<br/> Online<br/> 內部部署<br/> 內部部署<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Teams <br/>*團隊* <br/>**無法進行** <br/>*團隊* |
| SfB\* |商務用 Skype <br/>商務用 Skype  | Online<br/> 內部部署| &boxv;<br/>&boxv;|*團隊* <br/>*團隊*   |
| TeamsOnly |Teams |Online |&boxv; |Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>來自預先存在的執行緒的聊天與通話

### <a name="from-teams"></a>從團隊

在小組中預先存在的持久性執行緒開始的通話或聊天，會以與該執行緒相同的方式進行路由（如果該 [路由] 選項仍可使用）。

如果團隊中預先存在的持久性執行緒是原生執行緒（亦即路由至團隊），則其他聊天訊息和來自該執行緒的呼叫將會移至團隊。 如果它是交互操作執行緒（亦即路由到商務用 Skype），則其他聊天訊息和通話會移至商務用 Skype （也可以再次假設路由選項提供）。

> [!NOTE]
> 小組中的預先存在的執行緒可能無法再進行路由，例如當執行緒是交互操作執行緒給現在已升級至團隊的使用者時。 由於它是以交互操作執行緒的方式建立，所以該執行緒會傳送到商務用 skype，但該使用者不再可以使用商務用 Skype 聊天和通話。 在這種情況下，該執行緒將停用，而不會允許進一步的通訊。

### <a name="from-skype-for-business"></a>從商務用 Skype

商務用 Skype 執行緒不會保留在10分鐘的 SIP 會話超時以外。 在 SIP 會話到期前，在商務用 Skype 中，來自現有線程的聊天和呼叫將會以與執行緒相同的方式進行路由。 除了 SIP 會話超時之外，在商務用 Skype 中，來自現有的執行緒的通話和聊天，都將路由到遠端參與方的商務用 Skype，不論原始執行緒是來自其他人的那一方。

### <a name="availability"></a>供應

上述所述的租使用者與同盟行為都提供，且有下列限制：

- 租使用者位於不同 GoLocal 部署或地理位置的外部參與者在「同盟」會議中不會看到 IM 聊天
- 不支援多租戶 O365 與主權雲彩之間的同盟與互通性

## <a name="presence"></a>目前狀態

當您有部分使用者使用團隊用戶端，而其他使用者仍在使用商務用 Skype 用戶端時，您可能會有許多使用這兩個用戶端的使用者。 您仍想要與所有使用者共用目前狀態狀態，而不需考慮個別使用者所擁有的用戶端。 在組織中共用這種情況時，使用者可以更好地判斷是否適合啟動聊天或撥打通話。

例如，如果始發者的聊天或通話應該位於目標的商務用 Skype 用戶端上，那麼就是商務用 Skype 用戶端的目前狀態，應該顯示給始發者。 如果它應該位於目標的團隊用戶端，則是團隊用戶端的目前狀態。

若要瞭解預期的行為，您必須瞭解目前狀態是根據使用者的共存模式進行共用：

* 如果使用者是 TeamsOnly 模式，則其他任何使用者（無論是在團隊或商務用 Skype 中），都會看到 TeamsOnly 使用者的小組目前狀態
* 如果使用者使用的是任何 SfB\*模式（SfbOnly、SfbWithTeamsCollab、SfbWithTeamsCollabAndMeetings），則其他任何使用者（無論是在團隊或商務用 skype 中），都會看到 SfB\*使用者的商務用 skype 目前狀態
* 如果使用者使用的是孤島（或舊版）模式，則團隊中的目前狀態與商務用 Skype 中的目前狀態是獨立的（不需要符合的值），而其他使用者會看到孤島使用者的一或其他存在性，這取決於它們是位於相同的租使用者中，還是在聯盟租使用者中使用的用戶端。
    * 從團隊來看，同一租使用者中的任何其他使用者都會看到孤島使用者的小組目前狀態。這與上述的租使用者路由表對齊
    * 從團隊來看，同盟租使用者中的任何其他使用者都會看到孤島使用者的商務用 Skype 目前狀態;這與上述聯盟路由表對齊
    * 在商務用 Skype 中，任何其他使用者都會看到孤島使用者的商務用 Skype 目前狀態（在租使用者與同盟中）;這與上述路由表對齊


### <a name="in-tenant-presence"></a>租使用者狀態

傳送給 TeamsOnly 使用者的郵件將永遠位於小組中。 傳送給 SfB\*使用者的郵件永遠會在商務用 Skype 中保持居住，如果可以進行交談，如上述所述。 傳送給孤島使用者的訊息將永遠位於其起源的用戶端。

此表格說明發行者所看到的發行商目前狀態，視發行者和觀察程式的用戶端（針對新的執行緒）而定。

**資料表3：租使用者內的目前狀態（新執行緒）**

|監視器 <br/><br/>用戶端| |<br/><br/>離島 |Publisher <br/><br/>SfB\* |<br/>僅限團隊|
|--- |--- |--- |--- |---|
|商務用 Skype |&boxv;|商務用 Skype | 商務用 Skype | Teams|
|Teams |&boxv; |Teams |商務用 Skype |Teams |
| | | | |

### <a name="federated-presence"></a>同盟目前狀態

同盟目前狀態是以表格2所示的同盟可存取性為基礎。

下表說明發行者所看到的發行商目前狀態，視發行者的模式和觀察程式的用戶端（針對新的執行緒）而定。 在實踐中，觀察程式的用戶端在此階段不會有任何不同之處。

**資料表4：同盟目前狀態（新執行緒）**

|監視器 <br/><br/> 用戶端 | |<br/><br/> 離島  |Publisher <br/><br/> SfB\* |<br/><br/> 僅限團隊 |
|--- |--- |--- |--- |---|
|商務用 Skype |&boxv; |商務用 Skype  | 商務用 Skype  | Teams  |
|Teams | &boxv;|商務用 Skype |商務用 Skype |Teams|
| | | | ||

### <a name="presence-in-pre-existing-threads"></a>在預先存在的執行緒中的目前狀態

為了在預先存在的執行緒中對齊目前狀態和可存取性，該執行緒中公開的目前狀態必須與執行緒路由（假設路由可能）對齊。

特別是，如果收件者先前已升級至團隊的持續性互通性交談執行緒，該執行緒就不會再反映精確的目前狀態，而且將無法再進行路由。 您應該開始新的執行緒。

## <a name="related-links"></a>相關連結
[與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[影片：管理 SfB 與團隊之間的共存與互通性](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

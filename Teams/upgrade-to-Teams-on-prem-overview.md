---
title: 從商務用 Skype 內部部署（Microsoft 團隊）升級至團隊
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 從商務用 Skype 升級至團隊
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2b801f9dfe27aec4cb35dc6d28b80e9dfbf55390
ms.sourcegitcommit: b9710149ad0bb321929139118b7df0bc4cca08de
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/06/2019
ms.locfileid: "38010626"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>從商務用 Skype 升級至適用&mdash;于 IT 系統管理員的小組

## <a name="overview"></a>概觀

當您從商務用 Skype 升級至小組時，某些組織必須逐步推出由其 IT 部門規劃和管理的漸進式推出。 本文主要針對大型內部部署組織中的 IT 系統管理員，但也可能適用于某些商務用 Skype Online 組織。  閱讀本文之前，請務必閱讀[您的小組升級](upgrade-start-here.md)和[升級架構](upgrade-framework.md)的快速入門。

>[!NOTE]
>本文使用 [商務用 Skype Online]、[商務用 skype 內部部署] 和 [商務用 Skype] 這一詞。  後一詞指的是線上和內部部署版本。

已遷移至團隊的使用者將不再使用商務用 Skype 用戶端，除非加入在商務用 Skype 中託管的會議。  無論寄件者是使用小組或商務用 Skype，所有傳入聊天和呼叫使用者團隊用戶端中的土地。 由遷移使用者組織的任何新會議，都會排程為團隊會議。 如果使用者嘗試使用商務用 Skype 用戶端，就會封鎖聊天和通話的啟動。  不過，使用者可以（且必須）使用商務用 Skype 用戶端加入其受邀的會議。 （在2017之前隨附的舊版商務用 Skype 用戶端，不會提供 TeamsUpgradePolicy。 請確定您使用的是最新的商務用 Skype 用戶端。
 
系統管理員會使用[模式](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes)的概念（ [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)的屬性）來管理其轉場的小組。 如上述所述，已遷移至團隊的使用者，請參閱「TeamsOnly」模式。  對於遷移至團隊的組織而言，最終目標是將所有使用者移至 TeamsOnly 模式。

有兩種方法可以將現有的組織從商務用 Skype （無論是線上或內部部署）遷移至團隊：

- **並列方法**（使用孤島模式）：將現有商務用 Skype 組織中的使用者引入團隊，讓他們可以在過渡階段中並排使用這兩個用戶端。 在此期間，您可以使用大部分的團隊功能，但不是所有功能。 此設定的模式稱為 [孤島]，這是任何擁有商務用 Skype 之現有組織的預設模式。 組織就緒之後，系統管理員會將使用者移至 TeamsOnly 模式。

- **受管理的方法**（使用一或多個商務用 skype 模式）：系統管理員會針對組織中的使用者管理聊天、通話及會議排程功能的轉場（從商務用 skype 移至團隊）。  您可以在商務用 Skype 或團隊中使用這些功能，但不能同時在這兩者中找到。 系統管理員使用 TeamsUpgradePolicy 控制何時將此功能移至團隊中的使用者。 尚未處於 TeamsOnly 模式的使用者會繼續使用商務用 Skype 進行聊天和通話，而這兩組使用者可以透過交互操作功能進行通訊。 系統管理員會透過逐漸將更多使用者遷移至 TeamsOnly 模式，來管理轉換。  

本文將說明這兩種方法，並提供每個方法的優缺點，協助您為您的組織選擇正確的方法。 

## <a name="side-by-side-method-using-islands-mode"></a>並列方法（使用孤島模式）

透過並行方法，使用者可以使用小組與商務用 Skype 用戶端進行聊天、VoIP 通話及會議。 此狀態稱為「孤島」模式，因為商務用 Skype 和團隊的通訊流量會保持不變（即使是相同的使用者），而兩個不同的用戶端彼此之間都不會相互通訊（針對同一個組織中的使用者）。 例如，假設收件者使用者 A 處於孤島模式：

- 從另一個使用者的商務用 Skype 用戶端發起的通訊，將永遠位於使用者 A 的商務用 Skype 用戶端。
- 從另一個使用者的團隊用戶端發起的通訊，在使用者 A 的團隊用戶端中，*如果其他使用者位於同一個組織中*，就會永遠居住在該使用者。 
- 從另一個使用者的團隊用戶端發起的通訊，在使用者 A 的商務用 Skype 用戶端（*如果其他使用者位於同盟組織中*）中，將永遠居住在該使用者。

[孤島模式] 是尚未 TeamsOnly 之任何現有組織的預設 TeamsUpgradePolicy 模式。 當您指派 Office 365 授權時，系統會預設指派 [小組] 和 [商務用 Skype Online] 授權。 （即使使用者是在商務用 Skype 伺服器中託管內部部署，也是如此。 無論使用者是駐留在內部部署還是線上，都可以讓商務用 Skype Online 授權保持啟用，因為這是完整的小組功能目前所需要的。事實上，如果您未採取任何步驟來變更預設設定，您的組織可能已有大量的小組使用量。  這是並列方法的其中一個優點之一。 它可讓組織內的快速、使用者導向採用。

為了讓這個方法有效運作，它需要所有使用者同時執行這兩個用戶端。 您可以在商務用 Skype 或團隊用戶端中，將組織內部的內送聊天和組織中的電話撥入至使用者，而不是收件者的控制權。 這取決於寄件者用來啟動通訊的用戶端。 如果寄件者和收件者是在不同的組織中，在 [孤島] 模式中的來電與聊天，在商務用 Skype 用戶端中，將永遠居住在該使用者。  

例如，如果孤島模式的收件者執行的是商務用 Skype，而不是團隊，而其他人則是從小組傳送訊息，則 [孤島模式收件者] 不會看到該郵件（但最終會收到電子郵件，告知他們在小組中漏掉了郵件）。 同樣地，如果使用者執行的是小組，而不是商務用 Skype，而某人是從商務用 Skype 傳送給使用者的訊息，使用者就不會看到該聊天。  他們會收到一封電子郵件，指出遺失的訊息。 上述每個案例中的行為都與通話類似。 如果使用者不同時執行這兩個用戶端，可能很容易導致不滿。

當使用者 A 處於孤島模式時，小組和商務用 Skype 中的其他使用者看到的使用者 A 目前狀態是獨立的：

- 其他使用者在使用團隊時，會根據使用者在團隊中的活動來查看目前狀態。 
- 其他使用者在使用商務用 Skype 時，會根據商務用 Skype 中的使用者 A 活動，查看目前狀態。 

這代表使用者 A 的其他使用者可能會看到不同的目前狀態，視它們所使用的用戶端而定。 如需詳細資訊，請參閱目前[狀態](#presence)。

當您準備好要將使用者升級至 TeamsOnly 模式之後，您可以個別升級使用者，或者您可以使用租使用者的原則一次升級整個租使用者。 一旦使用者升級至 TeamsOnly 模式，就會在團隊中收到所有傳入聊天和通話。 （請注意，只有當您將 TeamsUpgradePolicy 套用至個別使用者，而不是每個租使用者時，才會觸發將商務用 Skype 會議遷移至團隊會議。 請參閱[會議遷移](#meeting-migration)以取得詳細資料。）

不過，在孤島模式中未升級的收件者，可能會繼續在其商務用 Skype 或團隊用戶端的 TeamsOnly 使用者中接收聊天和通話。  這是因為小組用戶端會針對小組與團隊成員以及商務用 Skype 通訊（即使是針對相同的使用者），為小組對等小組的交談進行單獨的交談執行緒。  （請參閱[團隊交談-互通性與原生執行緒](#teams-conversations---interop-versus-native-threads)）。 例如，假設 [Islands 使用者] 是使用團隊來 TeamsOnly 使用者 B 的訊息。當使用者 B 回復該聊天時，該通訊將會集中在使用者 A 的團隊用戶端中。 現在假設使用者 A 使用其商務用 Skype 用戶端到郵件 TeamsOnly 使用者 B。使用者 B 將會在團隊中收到聊天，但這將是與其他交談相比，在使用者 B 的團隊用戶端中相互獨立的交談。 如果使用者 B 與使用者 A 回復此交談，則會將它集中在使用者 A 的商務用 Skype 用戶端。 

下表摘要列出了孤島模式與 TeamsOnly 模式的團隊體驗：  

| 團隊經驗 | 在孤島模式中 | 在 TeamsOnly 模式中 |
|:------------------ | :------------------- | :------------------ |
| 傳入聊天與接聽的通話：|  團隊或商務用 Skype | 團隊 |
| 在下列情況中接收 PSTN 通話： | 商務用 Skype <br>（在 [孤島] 模式中不支援使用團隊中的 PSTN 功能。）    | 團隊 |   
 |平臺  | 商務用 Skype 和團隊中的目前狀態是獨立的。 針對相同的孤島使用者，使用者可能會看到不同的狀態，視它們所使用的用戶端而定。 | 目前狀態僅根據使用者在團隊中的活動而定。 所有其他使用者（無論他們使用的用戶端），請參閱目前狀態。 | 
 | 會議排程   | 使用者可以在小組或商務用 Skype 中排程會議。 它們會在 Outlook 中看到兩個增益集。 |   使用者只會在團隊中排程會議。 只有 [團隊] 增益集可在 Outlook 中使用。 | 

下表摘要列出使用並列方法將您的組織遷移至團隊的優點與缺點。

| 專業人員     |       利弊 |
| :------------------ | :---------------- |
| 可在組織內快速採用。| 因為有兩個用戶端具有相似的功能，但使用者介面不同，所以可能造成使用者混淆。 此外，他們也無法控制傳入聊天/呼叫居住在哪個用戶端。 |
| 允許使用者在仍擁有商務用 Skype 的完整存取權的情況下，瞭解並熟悉團隊。 | 如果使用者不是同時執行這兩個用戶端，可能會造成使用者不滿意的可能性。 使用者可能會抱怨沒有收到訊息。|
| 在團隊中開始使用最少的管理工作量。 | 如果不是組織中的所有人都使用團隊，則可以使用「使用孤島」模式並移至 TeamsOnly 模式，特別是在團隊中的所有使用者都不是使用中時。 例如，當使用者子集升級為 TeamsOnly 模式之後，這些使用者就只能在小組中傳送。 針對 [孤島] 模式中的其他人口，這些訊息將永遠位於小組中。 但如果其中一些總體不是執行團隊，他們將會認為這些訊息是未接的。 |
|  | 在使用團隊時，在商務用 Skype 伺服器中擁有內部部署帳戶的使用者，沒有互通性或同盟支援。  如果您有混合式的孤島使用者，這可能會造成混淆，因為有些人是駐留在商務用 Skype Online 中，還有一些是在商務用 Skype 內部部署中。   |

## <a name="managed-transition-method-using-skype-for-business-modes"></a>受管理的轉換方法（使用商務用 Skype 模式）

有些組織可能想要讓使用者在組織從商務用 Skype 轉換為小組時，為他們的使用者提供更簡單且更具預見性的體驗。 在這個模型中，IT 系統管理員會在 TeamsUpgradePolicy 中使用其中一個商務用 Skype 模式，以明確指定哪些使用者在遷移到 TeamsOnly 模式之前仍在商務用 Skype 中。 當他們準備好將選取的使用者移至 TeamsOnly 模式時，系統管理員會更新這些使用者的 TeamsOnly 模式。  隨著部署的進展，越來越多的使用者會從商務用 Skype 轉換成 TeamsOnly 模式。  在此轉換期間：

- 無論是來自其他使用者的小組或商務用 Skype 用戶端，仍在商務用 Skype 中的使用者都會收到其商務用 Skype 用戶端的所有傳入聊天和通話。 此外，對於這些商務用 Skype 使用者，小組用戶端中的 [通話與聊天] 功能已停用，以協助避免使用者混淆，並確保正確地進行路由。 

- 在 TeamsOnly 模式中的使用者會收到其團隊用戶端中的所有傳入聊天和通話，而不管通訊來自何處：團隊、商務用 Skype 或任何類型的同盟使用者。 

與孤島方法不同的是，在受管理的轉換方法中，商務用 Skype 使用者和 TeamsOnly 使用者可以彼此通訊。 商務用 Skype 使用者與團隊使用者之間的通訊稱為互通性或 "互通性"。 （請參閱[互通性](#interoperability)。）在商務用 Skype 和小組中的另一個使用者之間，互通性通訊可能是一對一的。 此外，受邀的使用者永遠都可以加入商務用 Skype 或團隊會議，但是他們必須使用與會議類型相對應的用戶端。 如需詳細資訊，請參閱[會議](#meetings)。

因為受管理轉換中的使用者通常不是孤島模式，所以無論其他使用者使用哪一個用戶端，使用者的目前狀態都是一致的。 如果使用者使用的是其中一種商務用 Skype 模式，所有其他使用者都會在商務用 Skype 中根據該使用者的活動查看目前狀態。 同樣地，如果使用者處於 TeamsOnly 模式，則所有其他使用者會根據團隊中該使用者的活動查看目前狀態。 如需詳細資訊，請參閱目前[狀態](#presence)。

對於尚未使用小組開始的組織，系統管理員應該將全租使用者的模式從孤島變更為 SfbWithTeamsCollab。 （適用于已有一些團隊使用的組織，系統管理員應該「grandfather」小組中已開啟的使用者，以確保此變更不適用於他們。 如需詳細資訊，請參閱[已在孤島模式中使用團隊之組織的受管理升級](#a-managed-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)。

當模式從孤島變更為 SfbWithTeamsCollab 時，如果使用者使用的是商務用 Skype，就不會有任何差異。 不過，如果使用者要開始使用小組，就只會對功能（例如團隊 & 頻道和檔案）公開。 小組中不提供聊天、通話和會議排程，因為系統管理員擁有（適用于目前）指派商務用 Skype 作為這些功能的所需用戶端。  

注意：當使用者從孤島變更為其中一個商務用 Skype 模式時，任何其他與使用者進行通訊的使用者的小組用戶端，都需要知道使用者 A 的模式已變更，以便讓使用者 A 將通訊傳送給適當的用戶端。 對於已建立與使用者 A 的原生團隊與團隊聊天的任何使用者，可能需要長達36小時，這些使用者的小組用戶端才能知道從孤島變更為任何商務用 Skype 模式的模式。   相反地，現有使用者對 TeamsOnly 模式所做的變更會在兩個小時內由其他用戶端發現。

當系統管理員準備好時，他們可以將使用者的模式更新為 TeamsOnly，將指定使用者的聊天、通話及會議排程一次性移至團隊。  

或者，管理員只能將會議排程轉移至團隊，同時使用 SfBWithTeamsCollabAndMeetings 模式在商務用 Skype 中離開交談和通話功能。 此模式可讓組織轉換為會議小組，如果使用者尚未準備好移至 TeamsOnly 模式（通常是因為遷移現有的 PSTN 功能可能需要較多的時間）。 此過渡案例會[先稱為會議](meetings-first.md)。


下表摘要列出使用商務用 Skype 模式做為 TeamsOnly 模式的過渡階段的優點與缺點。


| 專業人員     |       利弊 |
| :------------------ | :---------------- |
| 可預測的最終使用者路由。  根據系統管理員的選取，在商務用 Skype 或團隊（但不是兩者）中，所有通話和聊天都是居住的。  | 互通性交談缺少豐富文字、檔案共用及螢幕共用的支援。  這可以與點播會議進行合作，但這並不是無縫的。  |
| 消除對使用者造成的混亂，因為只有一位用戶端提供所提供的功能。  | 使用者不能同時針對相同的一組功能嘗試並行兩個用戶端。 如果使用者認為從商務用 Skype 移至團隊，做為主要模式班次，這可能特別是一個因數。 |
| 可讓團隊增加簡介。  |  | |
| 系統管理員完全控制從商務用 Skype 到團隊的轉場。 |  | | 
| 允許組織使用團隊進行會議，即使尚未準備好將其完全移至 TeamsOnly 模式。 |  | |
| 依其他人查看指定使用者的狀態，不論他們使用的是哪一個用戶端，都是一樣的。  |  | |

## <a name="summary-of-upgrade-methods"></a>升級方法摘要

下表摘要列出升級的方法：

| 並排（使用孤島模式）     |      管理（使用商務用 Skype 模式） |
| :------------------ | :---------------- |
| 在升級到 TeamsOnly 之前，使用者必須同時執行這兩個用戶端，因為傳入聊天和通話可能會在其中一個用戶端中進行。   | [聊天] 只會根據收件者的模式，在一個用戶端中呼叫土地。 未升級的使用者可以同時執行這兩個用戶端，但不存在任何正常的重迭（在小組中不提供通話與聊天）。  系統管理員也可以控制使用者是否要在小組或商務用 Skype 中排程會議。   |
| 使用者可以並排使用商務用 Skype 和團隊來提供相同的功能。   | 可讓系統管理員將小組的網路新功能引入使用者（團隊和頻道），但不提供在商務用 Skype 中也存在的相同功能。   |
|在商務用 Skype 與團隊之間的互通性，在兩個使用者都是孤島模式時不存在。 在將某些使用者升級至 TeamsOnly 之後，這些使用者和其他使用者可能會在仍在孤島模式中的互通性交談。 不過，孤島使用者可以選擇使用團隊並避免互通性交談。 | 商務用 Skype 與團隊使用者之間的通訊需要互通性。   |

## <a name="tools-for-managing-the-upgrade"></a>管理升級的工具

針對上述其中一種方法，系統管理員會使用[TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)（控制使用者的共存模式）來管理轉換為 TeamsOnly。 如需每個模式的詳細資訊，請參閱[共存模式](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes)。

無論系統管理員是使用商務用 Skype 模式執行受管理的轉場，或是從預設孤島設定直接升級至 TeamsOnly 模式，TeamsUpgradePolicy 是主要工具。  就像團隊中的任何其他原則一樣，TeamsUpgradePolicy 可以直接指派給使用者，也可以設定為租使用者範圍的預設值。 針對使用者的任何指派，都優先于租使用者預設設定。  它可以在團隊管理員主控台和 PowerShell 中進行管理。

系統管理員可以將任何 TeamsUpgradePolicy 模式指派給使用者，不論該使用者是駐留在商務用 Skype Online 或內部部署中，除了只能將 TeamsOnly 模式指派給已駐留在商務用 Skype Online 的使用者外。 這是因為，只有當使用者駐留在商務用 Skype Online 中，才可以使用商務用 Skype 使用者和同盟進行交互操作。

擁有商務用 Skype 帳戶的使用者，必須使用商務用 Skype 內部部署工具組，在線上（無論是商務用 Skype Online 或直接在小組中）[移動](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)move-csuser。 在1或2個步驟中，您可以將這些使用者移至 TeamsOnly：

-   1步驟：在 Move-csuser 中指定-MoveToTeams 開關。 這需要商務用 Skype Server 2019 或商務用 Skype Server 2015 與 CU8。

-   2個步驟：執行移動 Move-csuser 之後，使用 TeamsUpgradePolicy 將 TeamsOnly 模式授與使用者。

與其他原則不同，您無法在 Office 365 中建立新的 TeamsUpgradePolicy 實例。 所有現有的實例都會內嵌在服務中。  （請注意，mode 是 TeamsUpgradePolicy 內的屬性，而不是原則實例的名稱）。在部分（但非全部）情況下，原則實例的名稱與模式相同。 特別是，若要將 TeamsOnly 模式指派給使用者，您會將 TeamsUpgradePolicy 的「UpgradeToTeams」實例授與該使用者。 若要查看所有實例的清單，您可以執行下列命令：

```
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

若要將線上使用者升級為 TeamsOnly 模式，請指派「UpgradeToTeams」實例： 

```
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

若要將內部部署商務用 Skype 使用者升級到 TeamsOnly 模式，請在內部部署工具集中使用 Move-csuser：

```
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

若要變更租使用者中所有使用者的模式，除了擁有明確的每個使用者授與許可權的人員之外，請執行下列命令：

```
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>如果您擁有內部部署商務用 Skype 帳戶的任何使用者，則不應在租使用者層級指派 TeamsOnly 模式，除非您明確地將部分其他模式指派給使用內部部署商務用 Skype 帳戶的所有使用者。


### <a name="using-notifications-in-skype-for-business-clients"></a>在商務用 Skype 用戶端中使用通知

系統管理員可以選擇在商務用 Skype 用戶端中提供使用者通知，以通知使用者即將升級至團隊，如下圖所示。 例如，管理員將一周的時間升級為 TeamsOnly 模式，系統管理員可能會想要針對該使用者群組開啟這些通知。 使用 TeamsUpgradePolicy 與 NotifySfbUsers = true 的實例啟用這些通知。  針對除 TeamsOnly 以外的所有模式，實際會有兩個模式的實例，對應到兩個 NotifySfbUsers 值。  針對除 TeamsOnly 以外的所有模式，實際會有兩個模式的實例，對應到兩個 NotifySfbUsers 值。 

![顯示通知的圖表](media/teams-upgrade-sfb-with-notifications.png)

如果您的使用者是駐留在商務用 Skype Online，只要指派的原則實例與使用者的模式相同，但 NotifySfbUsers = true。 

如果您的使用者是駐留在內部部署的商務用 Skype 伺服器，您必須使用內部部署工具集，且需要商務用 Skype server 2019 或 CU8 （適用于商務用 skype Server 2015）。 在 [內部部署] PowerShell 視窗中，使用 NotifySfbUsers = true 建立新的 TeamsUpgradePolicy 實例：

```
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

接著，使用相同的內部部署 PowerShell 視窗，將該新原則指派給所需的使用者：

```
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

### <a name="meeting-migration"></a>會議遷移

當使用者被遷移至 TeamsOnly 模式時，預設會將他們所組織的現有商務用 Skype 會議轉換成小組。 您也可以選擇在指派 TeamsOnly 模式給使用者時，停用預設行為。 從內部部署移動使用者時，必須將會議遷移到雲端，才能與線上使用者帳戶共同作業，但如果您沒有指定-MoveToTeams，會議將會以商務用 Skype 會議進行遷移，而不是轉換成團隊。 

在租使用者層級指派 TeamsOnly 模式時，不會觸發會議遷移給任何使用者。 如果您想要在租使用者層級指派 TeamsOnly 模式和遷移會議，您可以使用 PowerShell 來取得租使用者的清單（例如，在需要的任何篩選器中使用 CsOnlineUser），然後遍歷這些使用者，以觸發會議使用開始-CsExMeetingMigration 的遷移。 如需詳細資訊，請參閱[使用會議遷移服務（MMS）](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。


### <a name="additional-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>使用商務用 Skype Server 內部部署之組織的其他考慮事項

- 設定商務用 Skype 混合式版是遷移至 TeamsOnly 模式的先決條件。 雖然您可以在沒有混合式的孤島模式下使用小組，但在使用者從商務用 Skype 內部部署移至商務用 Skype Online （使用 [[移動-move-csuser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)]）之前，無法進行 [轉至 TeamsOnly] 模式。 如需詳細資訊，請參閱[設定混合式連線性](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)。

- 擁有商務用 Skype 帳戶（也就是使用移動流覽 Move-csuser）的小組使用者，無法與任何商務用 Skype 使用者進行交互操作，也無法與外部使用者進行聯盟。 只有在使用者移至雲端（在孤島模式或 TeamsOnly 使用者）後，才能使用此功能。 

- 如果您擁有內部部署商務用 Skype 帳戶的任何使用者，則不應在租使用者層級指派 TeamsOnly 模式，除非您明確地將部分其他模式指派給使用內部部署商務用 Skype 帳戶的所有使用者。 

- 您必須確保您的使用者能以正確的商務用 Skype 屬性正確地同步處理到 Azure AD。 這些屬性都是含 "msRTCSIP-" 的所有首碼。 如果使用者未正確地同步處理到 Azure AD，小組中的管理工具將無法管理這些使用者。 如需詳細資訊，請參閱[設定團隊與商務用 Skype 的 AZURE AD Connect](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)。

- 若要在混合式組織中建立新的 TeamsOnly 或商務用 Skype Online 使用者，*您必須先在內部部署中啟用商務用 Skype Server 中的使用者*，然後使用 move-csuser 將使用者從內部部署移至雲端。  首先，在內部部署中建立使用者，以確保任何其他剩餘的內部部署商務用 Skype 使用者都能傳送給新建立的使用者。 當所有使用者都在線上移動之後，就不再需要先在內部部署中啟用使用者。

- 當使用者從內部部署移至雲端時，由該使用者組織的會議會遷移到商務用 Skype Online 或團隊中，視是否已指定-MoveToTeams 開關而定。

- 如果您想要在內部部署使用者的商務用 Skype 用戶端中顯示通知，您必須在內部部署工具集中使用 TeamsUpgradePolicy。 只有 NotifySfbUsers 參數與內部部署使用者有關。  內部部署使用者從 TeamsUpgradePolicy 的線上實例接收它們的模式。 請參閱授與[授與 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)中的筆記。 

>[!NOTE]
> 在2019年9月3日之後建立的任何新租使用者，都會建立為 TeamsOnly 租使用者，而不需要系統管理員進行降級的功能。 使用商務用 Skype Server 內部部署的組織（在9月 3 2019 日之前從未安裝 Office 365 訂閱），在使用者取得 Office 365 的訂閱之後，就必須與 Microsoft 支援人員聯繫，才能將其租使用者。 


## <a name="perform-the-upgrade-for-your-organization"></a>針對您的組織執行升級

本節將說明下列升級選項：

- 並行升級（使用孤島模式）
- 尚未使用團隊開始的組織的受管理升級
- 已在孤島模式中使用團隊之組織的受管理升級

### <a name="side-by-side-upgrade-using-islands-mode"></a>並行升級（使用孤島模式）

若要並排升級選項：

- 如果您可以為整體組織執行快速升級，請考慮此選項。  由於同時執行這兩個用戶端有潛在的風險，因此最好將此時段最小化。 您應該確保您的使用者知道同時執行這兩個用戶端。

- 此選項是現成的模型，而且不需要系統管理員指令即可開始使用小組，除非指派 Office 365 授權。 如果您的使用者已經有商務用 Skype Online，您可能已經在這個模型中了。

- 這可能會讓人感挑戰性，並移至 TeamsOnly。 由於升級的使用者只透過團隊進行通訊，組織中與該使用者進行通訊的任何其他使用者都必須使用團隊。  如果您有尚未開始使用小組的使用者，他們會面臨遺失的郵件。 此外，他們在商務用 Skype 中不會看到 TeamsOnly 使用者的線上狀態。 有些組織會選擇使用租使用者全域原則來執行租使用者範圍的升級，以避免這種情況，但需要等到所有使用者都準備好進行升級。


### <a name="a-managed-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>尚未使用團隊開始的組織的受管理升級

如果您的組織在團隊中還沒有任何作用中的使用者，第一個步驟是將 TeamsUpgradePolicy 的預設租使用者範圍原則設定為其中一個商務用 Skype 模式，例如 SfbWithTeamsCollab。  尚未開始使用團隊的使用者，將不會注意到行為的任何差異。 不過，在租使用者層級設定此原則，就可以開始將使用者升級至 TeamsOnly 模式，並確保升級後的使用者仍可與未升級的使用者通訊。  一旦您發現您的試驗使用者，您就可以將其升級至 TeamsOnly。  如果他們是內部部署，請使用 Move-csuser。 如果它們是線上的，只要使用 TeamsUpgradePolicy 就能指派 TeamsOnly 模式。  根據預設，由這些使用者排程的任何商務用 Skype 會議都會遷移至團隊。

下列是按鍵命令：

1. 將 [租使用者範圍] 的預設值設定為 mode SfbWithTeamsCollab，如下所示：

   ```
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. 將使用者升級成 TeamsOnly，如下所示：

   - 如果使用者已經在線上：

     ```
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - 如果使用者是內部部署：

     ```
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

筆記
 
- 您可以將整個租使用者的原則設定為 SfbWithTeamsCollabAndMeetings，而不是將它設定為 SfbWithTeamsCollab。 這會讓所有使用者排程團隊中的所有新會議。
- Move-csuser 是內部部署工具中的一個 Cmdlet。 MoveToTeams 開關需要使用 CU8 的商務用 Skype Server 2019 或商務用 Skype Server 2015。 如果您使用的是先前的版本，您可以先將使用者移至商務用 Skype Online，然後將 TeamsOnly 模式授與該使用者。
- 根據預設，當您升級至 TeamsOnly 模式或指派 SfbWithTeamsCollabAndMeetings 模式時，商務用 Skype 會議會遷移至團隊。  

下圖顯示的是組織的受管理升級的概念性階段，不含預先使用的團隊。 橫條圖的高度代表使用者數目。 在升級的任何階段中，所有使用者都可以彼此通訊。  商務用 Skype 使用者使用互通性與 TeamsOnly 使用者進行通訊，反之亦然。

![顯示未預先使用團隊之受管理升級的圖表](media/teams-upgrade-1.png)


### <a name="a-managed-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>已在孤島模式中使用團隊之組織的受管理升級

如果貴組織中的部分使用者積極地在孤島模式中使用團隊，您可能不想移除現有使用者的功能。 因此，您必須先執行額外步驟，才能變更租使用者範圍的原則。 解決方案是在將租使用者範圍的原則設定為 SfbWithTeamsCollab 之前，將這些現有的活動團隊使用者「grandfather」成孤島模式。  完成之後，您就可以繼續進行部署，不過，您將會有兩個使用者群組會移至 TeamsOnly：在團隊中使用中的使用者將會處於孤島模式，其餘的使用者將處於 SfbWithTeamsCollab 模式。 您可以逐步將這些使用者移至 TeamsOnly 模式。

1. 在團隊中尋找活躍的使用者，如下所示：

   1. 從 Office 365 系統管理入口網站的左側導覽中，移至 [報表]，然後移至 [使用方式]。 
   2. 在 [選取報表] 下拉式清單中，選擇 [Microsoft 團隊]，然後選擇 [使用者活動]。 這將提供已在團隊中使用中的使用者可匯出的資料表。 
   3. 按一下 [匯出]、[開啟 Excel] 和 [篩選]，只顯示在團隊中作用中的使用者。

2. 針對在步驟1中找到的每個作用中團隊使用者，在遠端 PowerShell 中指派其孤島模式。 這可讓您移至下一個步驟，並確保您不會變更使用者體驗。  

   ```
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. 將租使用者的原則設定為 SfbWithTeamsCollab：

   ```
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. 將選取的使用者升級至 TeamsOnly 模式。 您可以選擇在 [孤島模式] 或 [SfbWithTeamsCollab] 模式中升級使用者，不過，您可能會想要優先處理在 [孤島] 模式中升級使用者的優先順序，以便將使用者處於 [孤島] 模式時所發生的混淆可能性降至最低。   

   針對駐留在商務用 Skype Online 的使用者：  

   ```
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   針對駐留在內部部署的商務用 Skype 伺服器的使用者：  

   ```
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

下圖顯示的是受管理轉換的概念性階段，在開始時，會有活躍的孤島使用者。 橫條圖的高度代表使用者數目。 在升級的任何階段中，所有使用者都可以彼此通訊。  商務用 Skype 使用者使用互通性與 TeamsOnly 使用者進行通訊，反之亦然。


![顯示在孤島模式中使用作用中使用者進行的 managed 升級的圖表](media/teams-upgrade-2.png)

   

## <a name="considerations-for-pstn-calling"></a>PSTN 通話的考慮

如果涉及 PSTN 通話功能，當您移至 TeamsOnly 模式時，可能會發生四種情況：

- *商務用 Skype Online 中的使用者，包含 Microsoft 通話方案*。 升級時，此使用者將會繼續進行 Microsoft 通話計畫。

- *商務用 Skype Online 中的使用者，* 可透過商務用 skype 內部部署或雲端連接器版本使用內部部署語音功能。 使用者在小組中的升級需要與使用者遷移以直接傳送路由，以確保 TeamsOnly 使用者有 PSTN 功能。

- *在商務用 Skype 內部部署中使用企業語音的使用者，他們將會移至線上並保留內部部署 PSTN 連線*。  將此使用者遷移至團隊需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並將使用者的遷移轉移至直接傳送路線。 

- *在商務用 Skype 內部部署中使用企業語音的使用者*，他們將會移至線上並使用 Microsoft 通話方案。  將此使用者遷移至團隊需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並將該使用者電話號碼的埠與 A 進行協調）指派新的訂閱者號碼可用區域。

本文僅提供高層次的概覽。  如需詳細資訊，請參閱[手機系統 Direct 路由](direct-routing-landing-page.md)與[通話方案](calling-plan-landing-page.md)。 此外，請注意，只有當使用者處於 TeamsOnly 模式時，才會支援使用電話系統與團隊。  如果使用者使用的是孤島模式，則只有商務用 Skype 支援電話系統。 

### <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>使用 Microsoft 通話方案從商務用 Skype Online 

這是包括語音在內的最簡單的升級案例。 

1. 請確定使用者已獲指派團隊授權。 根據預設，當您指派 Office 365 授權時，系統會啟用團隊，所以除非您先前已停用團隊授權，否則不需要採取任何動作。

2.  如果使用者已有電話號碼的 Microsoft 通話方案，唯一的必要變更是在 TeamsUpgradePolicy 中指派使用者 TeamsOnly 模式。  在指派 TeamsOnly 模式之前，傳入的 PSTN 呼叫將會居住在使用者的商務用 Skype 用戶端。 升級至 TeamsOnly 模式之後，傳入的 PSTN 呼叫會集中在使用者的團隊用戶端中。  

### <a name="from-skype-for-business-online-with-on-premises-voice"></a>從商務用 Skype Online （含內部部署語音）

在這種情況下，使用者已經在商務用 Skype Online 中，但其 PSTN 連線是內部部署的，在混合模式或雲端連接器版本中使用商務用 Skype 伺服器。 透過 PSTN 功能將這些使用者遷移至 TeamsOnly 模式，就是透過您的內部部署會話邊界控制器（SBC），將 PSTN trunks 直接連線到雲端中的直接路由服務。

下列基本步驟如下所示。  步驟1-4 會列在建議的順序中，但它們可以以任何順序完成。 金鑰是所有這些都應該在步驟5之前完成。

1. 如果您要將租使用者的原則設定為其中一個商務用 Skype 模式，請務必透過明確指派 grandfather 任何現有的孤島使用者，如前面所述。

2. 針對直接路由設定您的租使用者。 請參閱[直接路由的每個租使用者配置摘要](#summary-of-per-tenant-configuration-of-direct-routing)。

3. 如有需要，請針對這些使用者設定各種小組原則（例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等）。 您可以隨時完成這項作業，但如果您想要確保使用者在升級時有正確的設定，最好在將使用者升級至 TeamsOnly 模式前執行此動作。

4. 準備選取要語音遷移的使用者： 
   - 如有需要，請指派 [團隊授權]。  假設使用者已在商務用 Skype Online 內部部署語音中運作，則使用者已經有商務用 Skype 方案2以及 Microsoft 手機系統。 讓這些方案保持啟用，包括商務用 Skype Online 方案2授權。  
   - 指派所需的 OnlineVoiceRoutingPolicy。 

5. 升級使用者：必須協調這些步驟。 

   - 在 Office 365 中，將使用者升級至 TeamsOnly 模式（授與 CsTeamsUpgradePolicy）。
   - 在 SBC 中，將語音路由設定為直接路由（而不是內部部署的中繼伺服器）傳送呼叫來啟用撥入通話。


### <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>從商務用 Skype Server 內部部署（含企業語音）到直接路由

在這種情況下，使用者仍然是在商務用 Skype 內部部署中，而且其 PSTN 連線也是內部部署。 使用 PSTN 功能將這些使用者遷移至 TeamsOnly 模式，可以讓他們直接路由，然後將使用者移至雲端。 
 
下列基本步驟如下所示。  步驟1-5 會列在建議的順序中，但它們可以以任何順序完成。 金鑰是所有這些都應該在步驟6之前完成。

1. 如果您要將租使用者的原則設定為其中一個商務用 Skype 模式，請務必 grandfather 現有的孤島使用者，方法是將其明確指派給其孤島模式（如前面所述）。

2. 如果您尚未這麼做，請[針對商務用 Skype 混合式設定組織](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。

3. 針對直接路由設定您的租使用者。 請參閱[直接路由的每個租使用者配置摘要](#summary-of-per-tenant-configuration-of-direct-routing)。

4. 如有需要，請針對這些使用者設定各種小組原則（例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等）。 您可以隨時完成這項作業，但如果您想要確保使用者在升級時有正確的設定，最好在將使用者升級至 TeamsOnly 前進行。

5. 如有需要，請指派 Office 365 授權。  使用者應該同時擁有 [小組] 和 [商務用 Skype Online 方案 2]，以及 [電話系統]。 如果商務用 Skype Online 方案2已停用，請重新啟用它。  

6. 升級使用者：必須協調這些步驟。 

   - 使用內部部署商務用 Skype 工具，以-MoveToTeams 開關執行移動 Move-csuser。 如果您使用的是不支援-MoveToTeams 開關的商務用 Skype Server 版本，請先執行 Move-Move-csuser，然後在租使用者遠端 PowerShell 或團隊管理主控台中指派 TeamsOnly 模式。

   - 在 SBC 中，將語音路由設定為直接路由（而不是內部部署的中繼伺服器）傳送呼叫來啟用撥入通話。 

   - 在 Office 365 中：指派相關的 OnlineVoiceRoutingPolicy 來啟用撥出通話。 


### <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>從商務用 Skype Server 內部部署（含企業語音）到 Microsoft 通話方案

在這種情況下，使用者仍然是在商務用 Skype 內部部署中，而且其 PSTN 連線也是內部部署。 透過 PSTN 功能將這些使用者遷移至 TeamsOnly 模式，意味著將使用者移至雲端，並將其號碼從舊的運營商移植到 Microsoft 通話方案，或為使用者指派新的號碼。 

下列基本步驟如下所示。步驟1-5 會列在建議的順序中，但它們可以以任何順序完成。 金鑰是所有這些都應該在步驟6之前完成。 

1. 如果您要將租使用者的原則設定為其中一個商務用 Skype 模式，請務必 grandfather 現有的孤島使用者，方法是將其明確指派給其孤島模式（如前面所述）。 

2. 如果您尚未這麼做，請[針對商務用 Skype 混合式設定組織](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。 

3. 如有需要，請針對這些使用者設定各種小組原則（例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等）。 您可以隨時完成這項作業，但如果您想要確保使用者在升級時有正確的設定，最好在將使用者升級至 TeamsOnly 前進行。 

4. 如有需要，請指派 Office 365 授權。使用者應該同時擁有 [小組] 和 [商務用 Skype Online 方案 2]，以及 [電話系統]。 如果商務用 Skype Online 方案2已停用，請重新啟用它。  

5. 為您的使用者取得電話號碼。 （如需詳細資訊，請參閱[管理貴組織的電話號碼](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)。）

   - 如果您要重複使用這些號碼，請將移植要求提交給您的運營商。  
   - 或者，您也可以直接從 Microsoft 取得新號碼。 

6. 升級使用者。 使用內部部署商務用 Skype 工具，以-MoveToTeams 開關執行移動 Move-csuser。  

    - 如果您要將號碼移植到 Microsoft，您應該將這個作業的時間調整為在埠出現時進行。 

    - 如果您使用的是 Microsoft 的新號碼，您需要變更該使用者的 LineUri。這應該在內部部署工具中完成，然後透過 Azure AD Connect 同步處理到雲端。 您應該在 Azure AD Connect 同步處理變更時，與 Move-csuser 作業同時進行。 

### <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>直接路由的每個租使用者配置摘要 

1. 透過查看[此清單](direct-routing-border-controllers.md)，確定您的會話邊界控制器（SBC）支援直接路由。 您也必須確定您的固件版本正確。  

2. 將您的內部部署 SBC 與團隊直向路由服務配對。 如需詳細資訊，請參閱將[SBC 與電話系統的直接路由服務](direct-routing-configure.md#pair-the-sbc-to-the-direct-routing-service-of-phone-system)。 

3. 此設定實質上是內部部署設定的鏡像。 線上配置包括： 
   - OnlineVoiceRoutingPolicy （根據內部部署 VoiceRoutingPolicy，如果您是從商務用 Skype Online 來遷移使用者，而如果是透過企業語音從內部部署遷移使用者，則根據 VoicePolicy）。
   - OnlinePSTNUsage 物件（根據內部部署的 PSTN 使用量）。 
   - OnlineVoiceRoute 物件（根據內部部署 VoiceRoute）。 

如需詳細資訊，請參閱[設定直接路由](direct-routing-configure.md)。 

### <a name="manage-enterprisevoiceenabled-property-during-migration"></a>在遷移期間管理 EnterpriseVoiceEnabled 屬性 

無論是使用直接路由或 Microsoft 通話方案，使用者在 Azure AD 中都必須有 EnterpriseVoiceEnabled = true，才能讓使用者擁有 PSTN 功能。  EnterpriseVoiceEnabled （"EV-enabled"）是在內部部署目錄和雲端中都存在的屬性（不是原則）。 雲端中的值是對團隊而言重要的。  如何將 EV 啟用的確切邏輯設定為 true，視下列情況而定： 

- 如果使用者在內部部署商務用 Skype 伺服器中啟用 EV，且在將使用者移至雲端且使用 Move-csuser 時，系統會為使用者指派電話系統授權，則會使用 EV-enabled = true 來預配線上使用者。 

- 如果現有的 TeamsOnly 或商務用 Skype Online 使用者已獲指派電話系統授權，則 EV-enabled 預設不會設定為 true。  如果在指派電話系統授權之前，將內部部署使用者移至雲端，也會發生這種情況。 不論是哪一種情況，管理員都必須指定下列 Cmdlet： 

  ```
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="coexistence-of-teams-with-skype-for-business"></a>使用商務用 Skype 的團隊共存

本節摘要說明在同一個組織中執行兩個小組和商務用 Skype 用戶端時可能會遇到的行為，無論使用何種模式和使用何種升級方法：

- [舉行](#meetings)
- [互通性](#interoperability)
- [團隊交談-互通性與原生執行緒](#teams-conversations---interop-versus-native-threads)
- [平臺](#presence)
- [聯盟](#federation)
- [連絡人](#contacts)

### <a name="meetings"></a>舉行

無論其模式為何，使用者都可以加入受邀者（無論是商務用 Skype 或團隊）所邀請的任何類型的會議。  不過，使用者必須以符合會議類型的對應用戶端加入會議：

- 如果會議是團隊會議，所有參與者（無論是 TeamsOnly、孤島或商務用 Skype 使用者）都可以使用團隊用戶端加入會議。 如果未安裝團隊，則在試圖加入會議時，該使用者會被導向網頁。

- 如果會議是商務用 Skype 會議，所有參與者（無論是 TeamsOnly、孤島或商務用 Skype 使用者），請使用商務用 Skype 用戶端加入會議。 如果未安裝商務用 Skype 用戶端，使用者將會透過 Skype 會議應用程式導向網頁進行加入。

組織會議時，排程的會議類型是以召集人的模式為基礎，如下表所示：

| 召集人模式    |      行為 |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    安排在團隊中的所有會議。 Outlook 中無法使用商務用 Skype 增益集。 | 
| SfbWithTeamsCollab, SfbOnly   | 在商務用 Skype 中排程的所有會議。 Outlook 中無法使用 [團隊] 增益集。 | 
| 索羅門群島 |     您可以在商務用 Skype 或團隊中排程會議。 您可以在 Outlook 中使用這兩個增益集。 | 


### <a name="interoperability"></a>互通性

在某些情況下，小組支援互通性（"互通性"）與商務用 Skype。 互通性通訊指的是商務用 Skype 使用者與團隊使用者之間的交談或通話。  交互操作通訊只可以在兩個使用者之間取得;不支援多方聊天/通話或新增其他使用者。

當下列各項都成立時，就會建立兩個使用者之間的互通性聊天或通話：

- 一位使用者使用的是 [商務用 Skype]。

- 初始通訊的收件者模式不是孤島（否則，通訊會在相同的用戶端內），如果兩個使用者都在同一個組織中。 在聯盟案例中，傳送使用者使用的是 [小組]，而收件者則不是 TeamsOnly 模式。 

- 團隊使用者也不會將商務用 Skype 帳戶駐留在內部部署中。 

在交互操作通訊中，聊天只是純文字。 此外，在*交互操作聊天本身中*不可能進行檔案共用和螢幕共用。 不過，交互操作交談中的使用者可以從互通性聊天中建立點播會議，輕鬆地達到檔案和/或螢幕共用，如下所述：

- 如果小組使用者嘗試共用其畫面，系統會自動建立一個點播團隊會議，而該會議的邀請連結會傳送到商務用 Skype 使用者的用戶端。 按一下連結時，商務用 Skype 使用者將會開啟團隊並加入會議。 兩個使用者現在都在團隊會議中，而且可以視需要共用。

- 如果商務用 Skype 使用者使用的是2018或更新版本的用戶端，且試圖共用任何內容，則會自動建立點播商務用 Skype 會議，而該會議的邀請連結會傳送給團隊使用者的用戶端。 當您按一下連結時，小組使用者會嘗試加入商務用 Skype 會議。 如果團隊使用者已安裝商務用 Skype 用戶端，則會開啟並提示使用者登入（若尚未登入）。  如果團隊使用者沒有安裝商務用 Skype 用戶端，系統會提示使用者使用 web 版本。 這兩個使用者登入之後，他們就在商務用 Skype 會議中，而且可以視需要共用。

### <a name="teams-conversations---interop-versus-native-threads"></a>團隊交談-互通性與原生執行緒

因為互通性通訊不支援原生團隊交談的所有功能，所以團隊用戶端會為小組對團隊以及商務用 Skype 通訊提供獨立的交談執行緒。 這些交談在使用者介面中會以不同的方式呈現：互通性執行緒可以與一般原生團隊執行緒區別：

- 不需要豐富的文字、檔案/螢幕共用、無法新增使用者的控制項。
- 針對目標使用者的圖示所做的修改，顯示商務用 Skype 的「S」。

下列螢幕擷取畫面顯示這些差異：

與使用者 G3 測試的原生團隊與團隊交談

![顯示原生團隊與團隊交談的圖表](media/teams-upgrade-native-thread.png)

具有相同使用者 G3 測試的互通性交談

![顯示互通性團隊與團隊交談的圖表](media/teams-upgrade-interop-thread.png)

建立交談執行緒之後，其類型就不會變更。 建立後，小組中的互通性執行緒將永遠會傳送給目標使用者的商務用 Skype 用戶端。 原生執行緒永遠會傳送給目標使用者的團隊用戶端。  如果收件者使用者的模式變更，現有的團隊執行緒將無法正常運作，而且會在該聊天上顯示一則筆記，其中包含開始新的原生交談的連結，如下列螢幕擷取畫面所示。 如需詳細資訊，請參閱[聊天和來自預先存在的執行緒的通話](coexistence-chat-calls-presence.md#chats-and-calls-from-pre-existing-threads)。


![顯示已升級的商務用 Skype 使用者聊天的圖表](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>平臺

指定使用者的「目前狀態」是依據客戶在服務中的活動。 隨後便會發佈目前狀態，供其他使用者查看。  商務用 Skype 與團隊是獨立用戶端的個別服務，所以每個服務都有自己的狀態供使用者使用。   在團隊與商務用 Skype Online 中的目前狀態服務之間也有同步處理。  這可讓一個服務視需要從其他服務發佈使用者的目前狀態。 

目前狀態發佈行為是以使用者的模式為基礎。 以下是三種基本案例：

- 如果使用者處於 TeamsOnly 模式，則所有其他使用者都會看到該使用者的小組目前狀態，不論他們使用的是哪一個用戶端。

- 如果使用者是在任何商務用 Skype 模式中，所有其他使用者都會看到該使用者的商務用 Skype 目前狀態，不論他們使用的是哪一種用戶端。

- 如果使用者使用的是孤島模式，在商務用 Skype 中發佈的目前狀態就是獨立的，因此同一個組織中的使用者所顯示的目前狀態將視其他使用者的用戶端而定。 同盟組織中的使用者會根據商務用 Skype 活動查看該使用者的目前狀態，因為在商務用 Skype 中，來自孤島模式使用者的聯盟流量。

例如，假設使用者 A 處於孤島模式。 如果使用者 A 在小組中使用中，但尚未登入商務用 Skype，其他使用者就會看到使用者 A 從其小組用戶端使用，但在其商務用 Skype 用戶端中，他們會看到使用者 A 為離線狀態。 這是由於設計，因為使用者 A 不在執行用戶端，所以無法到達。 

如需其他資訊，請參閱目前[狀態](coexistence-chat-calls-presence.md#presence)。

### <a name="federation"></a>聯盟

從小組聯盟到另一個使用商務用 Skype 的使用者，必須讓團隊使用者在商務用 Skype 中駐留在線上。 TeamsUpgradePolicy 會控制傳入的同盟聊天和通話的路由。 同盟路由行為與與相同租使用者案例相同，但在孤島模式除外。 當收件者處於孤島模式時：

- 如果收件者是聯盟租使用者，則會從商務用 Skype 中的 [小組] 土地開始聊天和通話。
- 如果收件者在相同的租使用者中，就會從團隊中的團隊土地開始聊天和通話。
- 從商務用 Skype 發起的聊天和通話，在商務用 Skype 中永遠不間斷。

小組使用者與商務用 Skype 之間的同盟聊天是交互操作執行緒，所以無法進行 rtf 與共享。 使用者介面會以與同一個租使用者交互操作執行緒相似的方式公開同盟聊天，但有一個指示使用者是外部的筆記。

當團隊第一次推出同盟時，兩個團隊使用者之間的同盟聊天也是交互操作執行緒，但將來，系統會推出原生團隊同盟，提供在 TeamsOnly 模式的使用者之間進行交談的完整功能。 . 

如需詳細資訊，請參閱[聯盟路由以取得新的聊天或通話](coexistence-chat-calls-presence.md#federated-routing-for-new-chats-or-calls)。

### <a name="contacts"></a>連絡人

[小組] 和 [商務用 Skype] 有不同的連絡人清單。 這表示在單一系統中所做的連絡人新增、移除及修改，不會與其他系統同步處理。 不過，當兩個特定事件發生時，商務用 Skype 的連絡人會自動複製到小組中： 

- 針對任何商務用 Skype Online 使用者，第一次登入小組時，商務用 Skype 的連絡人將會複製到小組。  在商務用 Skype Server 中擁有內部部署帳戶的使用者無法使用此行為。  

- 在使用者升級至 TeamsOnly （透過指派 TeamsUpgradePolicy 或透過移動 Move-csuser-MoveToTeams）之後，下次使用者登入小組時，商務用 Skype 中現有的連絡人將會與已存在於團隊中的現有連絡人合併。 不論使用者的商務用 Skype 帳戶是駐留在內部部署還是線上，都會發生此行為。 

在這兩種情況下，從商務用 Skype 將連絡人轉移至團隊是非同步，因此可能需要幾分鐘的時間，才會在團隊中顯示連絡人。 上述兩個事件會觸發複本。  

## <a name="related-links"></a>相關連結

[與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南](migration-interop-guidance-for-teams-with-skype.md) 

[在商務用 Skype Server 和 Office 365 之間設定混合式連接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存與升級設定](setting-your-coexistence-and-upgrade-settings.md)

[授與 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用會議遷移服務（MMS）](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)


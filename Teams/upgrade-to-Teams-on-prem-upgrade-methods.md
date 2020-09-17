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
description: 從商務用 Skype 升級至 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80a7071cf6adbfa423e4c0fa12ac21a5bc777268
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940652"
---
# <a name="upgrade-methods-mdash-for-it-administrators"></a>&mdash;IT 系統管理員的升級方法

本文將說明遷移至團隊的升級方法。 本文是幾個描述 IT 系統管理員升級概念與實現的第二個專案。  

- [概觀](upgrade-to-teams-on-prem-overview.md)
- 本文 (**升級方法**) 
- [管理升級的工具](upgrade-to-teams-on-prem-tools.md)
- [使用商務用 Skype 內部部署之組織的其他考慮事項](upgrade-to-teams-on-prem-considerations.md)
- [實施升級](upgrade-to-teams-on-prem-implement.md)
- [公用交換電話網絡 (PSTN) 考慮](upgrade-to-teams-on-prem-pstn-considerations.md)

此外，下列文章說明重要的升級概念與共存行為：

- [團隊與商務用 Skype 的共存](upgrade-to-teams-on-prem-coexistence.md)
- [共存模式-參考](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 用戶端體驗和遵從共存模式](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="upgrade-methods"></a>升級方法

有兩種方法可升級現有的組織與商務用 Skype (無論是線上或內部部署) 至團隊：重迭的功能方法，以及 [選取功能] 方法。  本文將說明這兩種方法，並提供每個方法的優缺點，協助您為您的組織選擇正確的方法。 

- [使用孤島模式 (重迭的功能方法) ](#overlapping-capabilities-method-using-islands-mode)

   現有商務用 Skype 組織中的使用者會被引入小組，讓他們可以在過渡階段中使用這兩個用戶端。 在此期間，您可以使用大部分的團隊功能，但不是所有功能。 此設定的模式稱為 [孤島]，這是任何擁有商務用 Skype 之現有組織的預設模式。 組織就緒之後，系統管理員會將使用者移至 TeamsOnly 模式。

- [使用一或多個商務用 Skype 模式 (選取功能方法) ](#select-capabilities-method-using-skype-for-business-modes)

   系統管理員會管理從商務用 Skype (到組織中的使用者聊天、通話及會議排程功能的小組) 。  您可以在商務用 Skype 或團隊中使用這些功能，但不能同時在這兩者中找到。 系統管理員使用 TeamsUpgradePolicy 控制何時將此功能移至團隊中的使用者。 尚未處於 TeamsOnly 模式的使用者會繼續使用商務用 Skype 進行聊天和通話，而這兩組使用者可以透過交互操作功能進行通訊。 系統管理員會透過逐漸將更多使用者遷移至 TeamsOnly 模式，來管理轉換。  

瞭解並選擇您的升級方法之後，您可以瞭解 [管理組織升級至團隊的工具](upgrade-to-teams-on-prem-tools.md)。

## <a name="overlapping-capabilities-method-using-islands-mode"></a>使用孤島模式 (重迭的功能方法) 

使用重迭的功能方法，使用者可以使用小組和商務用 Skype 用戶端來進行聊天、VoIP 通話和會議。 此狀態稱為「孤島」模式，因為商務用 Skype 和小組的通訊流量會保持不變的 (，即使是同一位使用者) ，而兩個不同的用戶端彼此都無法與同一個組織中的使用者相互通訊 () 。 例如，假設收件者使用者 A 處於孤島模式：

- 從另一個使用者的商務用 Skype 用戶端發起的通訊，將永遠位於使用者 A 的商務用 Skype 用戶端。

- 從另一個使用者的團隊用戶端發起的通訊，在使用者 A 的團隊用戶端中， *如果其他使用者位於同一個組織中*，就會永遠居住在該使用者。 

- 從另一個使用者的團隊用戶端發起的通訊，在使用者 A 的商務用 Skype 用戶端（ *如果其他使用者位於同盟組織中*）中，將永遠居住在該使用者。

[孤島模式] 是任何尚未升級至 TeamsOnly 的現有組織的預設 TeamsUpgradePolicy 模式。 當您指派 Microsoft 365 或 Office 365 授權時，系統會預設指派 [小組] 和 [商務用 Skype Online 授權]。  (即使使用者是在商務用 Skype 伺服器中託管內部部署，也是如此。 無論使用者是駐留在內部部署還是線上，都能讓商務用 Skype Online 授權保持啟用，因為這是完整的小組功能目前所需要的。 ) 事實上，如果您未採取任何步驟來變更預設設定，您的組織中可能已有大量的小組使用量。  這是重迭功能方法的其中一個優點之一。 它可讓組織內的快速、使用者導向採用。

為了讓這個方法有效運作，它需要所有使用者同時執行這兩個用戶端。 您可以在商務用 Skype 或團隊用戶端中，將組織內部的內送聊天和組織中的電話撥入至使用者，而不是收件者的控制權。 如果寄件者和收件者位於同一個組織中，則取決於寄件者用來啟動通訊的用戶端。 如果寄件者和收件者是在不同的組織中，在 [孤島] 模式中的來電與聊天，在商務用 Skype 用戶端中，將永遠居住在該使用者。  

例如，如果孤島模式的收件者執行的是商務用 Skype，而不是團隊，而且同一位組織中的某人是來自小組的人員，則孤島模式收件者將不會看到該郵件 (，但最終會收到一封電子郵件，指出他們在團隊) 中錯過了訊息。 同樣地，如果使用者執行的是小組，而不是商務用 Skype，而某人是從商務用 Skype 傳送給使用者的訊息，使用者就不會看到該聊天。  他們會收到一封電子郵件，指出遺失的訊息。 上述每個案例中的行為都與通話類似。 如果使用者不同時執行這兩個用戶端，可能很容易導致不滿。

當使用者 A 處於孤島模式時，小組和商務用 Skype 中的其他使用者看到的使用者 A 目前狀態是獨立的：

- 其他使用者在使用團隊時，會根據使用者在團隊中的活動來查看目前狀態。 
- 其他使用者在使用商務用 Skype 時，會根據商務用 Skype 中的使用者 A 活動，查看目前狀態。 

這代表使用者 A 的其他使用者可能會看到不同的目前狀態，視它們所使用的用戶端而定。 如需詳細資訊，請參閱目前 [狀態](upgrade-to-teams-on-prem-coexistence.md#presence)。

當您準備好要將使用者升級至 TeamsOnly 模式之後，您可以個別升級使用者，或者您可以使用租使用者的原則一次升級整個租使用者。 一旦使用者升級至 TeamsOnly 模式，就會在團隊中收到所有傳入聊天和通話。  (請注意，只有當您將 TeamsUpgradePolicy 套用至個別使用者，而不是每個租使用者時，才會觸發將商務用 Skype 會議遷移至團隊會議。 請參閱 [會議遷移](upgrade-to-teams-on-prem-tools.md#meeting-migration) 以取得詳細資料。 ) 

不過，在孤島模式中未升級的收件者，可能會繼續在其商務用 Skype 或團隊用戶端的 TeamsOnly 使用者中接收聊天和通話。  這是因為小組用戶端會針對小組與團隊成員以及商務用 Skype 通訊（即使是針對相同的使用者），為小組對等小組的交談進行單獨的交談執行緒。   (查看 [團隊交談-互通性與原生執行緒](upgrade-to-teams-on-prem-coexistence.md#teams-conversations---interop-versus-native-threads)。 ) 例如，假設 Islands 使用者 A 使用團隊來 TeamsOnly 使用者 B 的訊息。當使用者 B 回復該聊天時，該通訊將會集中在使用者 A 的團隊用戶端中。 現在假設使用者 A 使用其商務用 Skype 用戶端到郵件 TeamsOnly 使用者 B。使用者 B 將會在團隊中收到聊天，但這將是與其他交談相比，在使用者 B 的團隊用戶端中相互獨立的交談。 如果使用者 B 與使用者 A 回復此交談，則會將它集中在使用者 A 的商務用 Skype 用戶端。 

下表摘要列出了孤島模式與 TeamsOnly 模式的團隊體驗：  

| 團隊經驗 | 在孤島模式中 | 在 TeamsOnly 模式中 |
|:------------------ | :------------------- | :------------------ |
| 傳入聊天與接聽的通話：|  團隊或商務用 Skype | Teams |
| 在下列情況中接收 PSTN 通話： | 商務用 Skype <br>在 Islands 模式下，不支援在團隊中使用 PSTN 功能的 (。 )     | Teams |   
 |目前狀態  | 商務用 Skype 和團隊中的目前狀態是獨立的。 針對相同的孤島使用者，使用者可能會看到不同的狀態，視它們所使用的用戶端而定。 | 目前狀態僅根據使用者在團隊中的活動而定。 所有其他使用者（無論他們使用的用戶端），請參閱目前狀態。 | 
 | 會議排程   | 根據預設，使用者可以在小組或商務用 Skype 中排程會議。 它們會在 Outlook 中看到兩個增益集。 |   使用者只會在團隊中排程會議。 只有 [團隊] 增益集可在 Outlook 中使用。 | 

下表摘要列出使用重迭的功能方法將您的組織遷移至團隊的優點與缺點。

| 專業人員     |       利弊 |
| :------------------ | :---------------- |
| 可在組織內快速採用。| 因為有兩個用戶端具有相似的功能，但使用者介面不同，所以可能造成使用者混淆。 此外，他們也無法控制傳入聊天/呼叫居住在哪個用戶端。 |
| 允許使用者在仍擁有商務用 Skype 的完整存取權的情況下，瞭解並熟悉團隊。 | 如果使用者不是同時執行這兩個用戶端，可能會造成使用者不滿意的可能性。 使用者可能會抱怨沒有收到訊息。|
| 在團隊中開始使用最少的管理工作量。 | 如果不是組織中的所有人都使用團隊，則可以使用「使用孤島」模式並移至 TeamsOnly 模式，特別是在團隊中的所有使用者都不是使用中時。 例如，當使用者子集升級為 TeamsOnly 模式之後，這些使用者就只能在小組中傳送。 針對 [孤島] 模式中的其他人口，這些訊息將永遠位於小組中。 但如果其中一些總體不是執行團隊，他們將會認為這些訊息是未接的。 |
|  | 在使用團隊時，在商務用 Skype 伺服器中擁有內部部署帳戶的使用者，沒有互通性或同盟支援。  如果您有混合式的孤島使用者，這可能會造成混淆，因為有些人是駐留在商務用 Skype Online 中，還有一些是在商務用 Skype 內部部署中。   |

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>使用商務用 Skype 模式 (選取功能方法) 

有些組織可能想要讓使用者在組織從商務用 Skype 轉換為小組時，為他們的使用者提供更簡單且更具預見性的體驗。 在這個模型中，IT 系統管理員會在 TeamsUpgradePolicy 中使用其中一個商務用 Skype 模式，以明確指定哪些使用者在遷移到 TeamsOnly 模式之前仍在商務用 Skype 中。 當他們準備好將選取的使用者移至 TeamsOnly 模式時，系統管理員會更新這些使用者的 TeamsOnly 模式。 隨著部署的進展，越來越多的使用者會從商務用 Skype 轉換成 TeamsOnly 模式。  在此轉換期間：

- 無論是來自其他使用者的小組或商務用 Skype 用戶端，仍在商務用 Skype 中的使用者都會收到其商務用 Skype 用戶端的所有傳入聊天和通話。 此外，對於這些商務用 Skype 使用者，小組用戶端中的 [通話與聊天] 功能已停用，以協助避免使用者混淆，並確保正確地進行路由。 

- 在 TeamsOnly 模式中的使用者會收到其團隊用戶端中的所有傳入聊天和通話，而不管通訊來自何處：團隊、商務用 Skype 或任何類型的同盟使用者。 

與孤島方法不同的是，在 [選取功能] 方法中，商務用 Skype 使用者和 TeamsOnly 使用者可以彼此通訊。 商務用 Skype 使用者與團隊使用者之間的通訊稱為互通性或 "互通性"。 在商務用 Skype 和小組中的另一個使用者之間，互通性通訊可在一對一的情況中進行交談和通話;不過，某些高級功能可能無法使用。  (請參閱 [互通性](upgrade-to-teams-on-prem-coexistence.md#interoperability)。 ) 此外，受邀的使用者永遠都可以加入商務用 Skype 或團隊會議，但是他們必須使用與會議類型相對應的用戶端。 如需詳細資訊，請參閱 [會議](upgrade-to-teams-on-prem-coexistence.md#meetings)。

因為在選取功能轉換中的使用者通常不會使用孤島模式，所以無論其他使用者使用哪個用戶端，使用者的目前狀態都是一致的。 如果使用者使用的是其中一種商務用 Skype 模式，所有其他使用者都會在商務用 Skype 中根據該使用者的活動查看目前狀態。 同樣地，如果使用者處於 TeamsOnly 模式，則所有其他使用者會根據團隊中該使用者的活動查看目前狀態。 如需詳細資訊，請參閱目前 [狀態](upgrade-to-teams-on-prem-coexistence.md#presence)。

對於尚未使用小組開始的組織，系統管理員應該將全租使用者的模式從孤島變更為 SfbWithTeamsCollab。  (對於已經有一些團隊使用量的組織而言，系統管理員應該「grandfather」已在小組中開啟的使用者，以確保此變更不適用於他們。 如需詳細資訊，請參閱 [已在孤島模式中使用團隊之組織的 [選取功能] 方法](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)。 ) 

當模式從孤島變更為 SfbWithTeamsCollab 時，如果使用者使用的是商務用 Skype，就不會有任何差異。 不過，如果使用者要開始使用小組，就只會對功能（例如團隊 & 頻道和檔案）公開。 在小組中不提供聊天、通話和會議排程，因為系統管理員) 現在已 (指派商務用 Skype 做為這些函式所需的用戶端。  

注意：當使用者從孤島變更為其中一個商務用 Skype 模式時，任何其他與使用者進行通訊的使用者的小組用戶端，都需要知道使用者 A 的模式已變更，以便讓使用者 A 將通訊傳送給適當的用戶端。 對於已建立與使用者 A 的原生團隊與團隊聊天的任何使用者，可能需要長達36小時，這些使用者的小組用戶端才能知道從孤島變更為任何商務用 Skype 模式的模式。   相反地，現有使用者對 TeamsOnly 模式所做的變更會在兩個小時內由其他用戶端發現。

當系統管理員準備好時，他們可以將使用者的模式更新為 TeamsOnly，將指定使用者的聊天、通話及會議排程一次性移至團隊。  

或者，管理員只能將會議排程轉移至團隊，同時使用 SfBWithTeamsCollabAndMeetings 模式在商務用 Skype 中離開交談和通話功能。 此模式可讓組織轉換成會議小組（如果使用者尚未準備好移至 TeamsOnly 模式）， (通常是因為可能需要較多的時間來遷移現有的 PSTN 功能) 。 此過渡案例會 [先稱為會議](meetings-first.md)。

下表摘要列出使用商務用 Skype 模式做為 TeamsOnly 模式的過渡階段的優點與缺點。


| 專業人員     |       利弊 |
| :------------------ | :---------------- |
| 可預測的最終使用者路由。  在商務用 Skype 或團隊中，所有通話和聊天都 (，但不是以系統管理員的選擇來) 。  | 互通性交談缺少豐富文字、檔案共用及螢幕共用的支援。  這可以與點播會議進行合作，但這並不是無縫的。  |
| 消除對使用者造成的混亂，因為只有一位用戶端提供所提供的功能。  | 使用者不能同時嘗試兩個用戶端的同一組功能。 如果使用者認為從商務用 Skype 移至團隊，做為主要模式班次，這可能特別是一個因數。 |
| 可讓團隊增加簡介。  |  | |
| 系統管理員完全控制從商務用 Skype 到團隊的轉場。 |  | | 
| 允許組織使用團隊進行會議，即使尚未準備好將其完全移至 TeamsOnly 模式。 |  | |
| 依其他人查看指定使用者的狀態，不論他們使用的是哪一個用戶端，都是一樣的。  |  | |

## <a name="summary-of-upgrade-methods"></a>升級方法摘要

下表摘要列出升級的方法：

| 使用孤島模式 (重迭的功能)      |      使用商務用 Skype 模式 (選取功能)  |
| :------------------ | :---------------- |
| 在升級到 TeamsOnly 之前，使用者必須同時執行這兩個用戶端，因為傳入聊天和通話可能會在其中一個用戶端中進行。   | [聊天] 只會根據收件者的模式，在一個用戶端中呼叫土地。 未升級的使用者可能會同時執行這兩個用戶端，但無法在團隊) 中使用 (通話與聊天的功能重迭。  系統管理員也可以控制使用者是否要在小組或商務用 Skype 中排程會議。   |
| 使用者可以並排使用商務用 Skype 和團隊來提供相同的功能。   | 可讓系統管理員將小組的網路新功能引入 (團隊和頻道) ，但不提供也存在於商務用 Skype 中的相同功能。   |
|在商務用 Skype 與團隊之間的互通性，在兩個使用者都是孤島模式時不存在。 在將某些使用者升級至 TeamsOnly 之後，這些使用者和其他使用者可能會在仍在孤島模式中的互通性交談。 不過，孤島使用者可以選擇使用團隊並避免互通性交談。 | 商務用 Skype 與團隊使用者之間的通訊需要互通性。   |


## <a name="related-links"></a>相關連結

[與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南](migration-interop-guidance-for-teams-with-skype.md) 

[在商務用 Skype Server 與 Microsoft 365 或 Office 365 之間設定混合式連接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存與升級設定](setting-your-coexistence-and-upgrade-settings.md)

[授與 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用會議遷移服務 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)


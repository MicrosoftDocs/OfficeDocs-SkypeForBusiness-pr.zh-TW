---
title: Microsoft 團隊從商務用 Skype 升級 |模式、共存
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl, bjwhalen
description: 商務用 Skype 和 Microsoft 團隊共存選項與模式的詳細資料，以及從商務用 Skype 將 journeys 升級至小組，並提供範例案例。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 548b1f9adbd964737c664baab108201412b6e90f
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "44522776"
---
# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>選擇從商務用 Skype 升級到團隊的升級歷程

![升級歷程圖表，強調專案定義階段](media/upgrade-banner-project-definition.png "升級歷程階段，重點放在專案定義階段")

本文是升級歷程專案定義階段的一部分。 繼續之前，請確認您已完成下列活動：

- [已登記您的專案干係人](upgrade-enlist-stakeholders.md)
- [已定義您的專案範圍](https://aka.ms/SkypetoTeams-Scope)
- [已瞭解商務用 Skype 與團隊的共存與互通性](https://aka.ms/SkypeToTeams-Coexist)

在現有的商務用 Skype 客戶中，您對團隊的完整轉場可能需要一些時間。 不過，您現在可以讓您的使用者在商務用 Skype 中使用團隊，來開始實現團隊的價值。 如果兩個應用程式之間有一些重迭的功能，建議您查看可用的共存和升級模式，以協助判斷哪一個路徑適合您的組織。 例如，您可以選擇在兩個解決方案中都啟用所有工作負荷，而不需要互通性。 或者，您也可以決定是否要管理使用者體驗，只要逐步引入小組功能，或以使用者的目標群組為選取功能，直到貴組織準備好將所有人升級至團隊為止。 使用試驗的結果，協助您評估貴組織的正確升級歷程。

> [!IMPORTANT]
> 商務用 Skype Online 將於 2021 年 7 月 31 日淘汰，之後將無法再存取也不再受支援。 若要最大限度取得效益並確保貴組織有適當的時間來實施升級，我們鼓勵您立即開始將您的遷移到 Microsoft 團隊。

本文將說明各種模式，讓您管理使用者可以使用商務用 Skype 和團隊的形式。 就像任何部署一樣，我們強烈建議您在將組織升級至團隊之前，先在選取的使用者群組中試驗您的[預定方案](pilot-essentials.md)。 請記住，新技術對於使用者來說可能會造成中斷。 在執行此處所述的任何模式之前，請花一些時間來評估使用者準備狀況，並實施通訊與訓練方案。

> [!TIP]
> 加入即時、互動式研討會，我們將分享指導方針、最佳做法，以及專為開始升級規劃與實施方案而設計的資源。
>
>首先加入[升級會話方案](https://aka.ms/SkypeToTeamsPlanning)，以開始使用。


## <a name="upgrade-journey-building-blocks"></a>升級歷程組建區塊

若要正式準備貴組織進行團隊的旅程，您必須開始規劃升級案例，以讓您的組織完全接納團隊作為您的唯一溝通與共同作業解決方案。

若要協助引導您的決策過程，請熟悉從商務用 Skype 升級至團隊的各種模式、概念及術語。 如需詳細資訊，請參閱[Microsoft 團隊及商務用 Skype 共存與互通性](https://aka.ms/SkypeToTeams-Coexist)

已遷移至團隊的使用者將不再使用商務用 Skype 用戶端，除非加入在商務用 Skype 中託管的會議。 無論寄件者是使用小組或商務用 Skype，所有傳入聊天和呼叫使用者團隊用戶端中的土地。 任何由升級的使用者組織的新會議，都會排程為團隊會議。 如果使用者嘗試使用商務用 Skype 用戶端，啟動聊天和通話會封鎖<sup>1</sup>。 不過，使用者可以（且必須）使用商務用 Skype 用戶端加入其受邀的會議。

系統管理員會使用[模式](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes)的概念（ [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)的屬性）來管理其轉場的小組。 如上述所述，已遷移至團隊的使用者，請參閱「TeamsOnly」模式。 對於遷移至團隊的組織而言，最終目標是將所有使用者移至 TeamsOnly 模式。

有兩種方法可以將現有的組織從商務用 Skype （無論是線上或內部部署）遷移至團隊：

- 重**迭的功能方法**（使用 [安全島] 模式）：現有的商務用 Skype 組織中的使用者會被引入至團隊，讓他們可以在轉換階段中並排使用這兩個用戶端。 在此期間，您可以使用大部分的團隊功能，但不是所有功能。 此設定的模式稱為 [孤島]，這是任何擁有商務用 Skype 之現有組織的預設模式。 組織就緒之後，系統管理員會將使用者移至 TeamsOnly 模式。
- **選取功能方法**（使用一或多個商務用 skype 模式）：系統管理員會管理組織中使用者的聊天、通話及會議排程功能的轉場（從商務用 skype 移至團隊）。 您可以在商務用 Skype 或團隊中使用這些功能，但不能同時在這兩者中找到。 系統管理員使用 TeamsUpgradePolicy 控制何時將此功能移至團隊中的使用者。 尚未處於 TeamsOnly 模式的使用者會繼續使用商務用 Skype 進行聊天和通話，而這兩組使用者可以透過交互操作功能進行通訊。 系統管理員會透過逐漸將更多使用者遷移至 TeamsOnly 模式，來管理轉換。

<sup>1</sup>在2017之前隨附的舊版商務用 Skype 用戶端不會提供 TeamsUpgradePolicy。 請確定您使用的是 Office 頻道中最新的商務用 Skype 用戶端。

以下是協助您為您的組織決定適當路徑的主要因素。 

## <a name="overlapping-capabilities-method-using-islands-mode"></a>重迭的功能方法（使用孤島模式）

使用重迭的功能方法，使用者可以使用小組和商務用 Skype 用戶端來進行聊天、VoIP 通話和會議。 在這個方法中，小組中的聊天與 VOIP 通話是組織內的焦點，而商務用 Skype 則可與外部組織（如果有設定）啟用聊天與 VOIP/PSTN 通話。 您可以在兩個產品中排程和參與會議。

使用 [重迭功能] 方法時，商務用 Skype 和團隊的通訊流量會保持不變（即使是相同的使用者），而兩個不同的用戶端彼此互不通訊（針對同一個組織中的使用者）。 使用者體驗是以收件者的設定為基礎。 例如，假設收件者使用者 A 使用這個升級方法：

- 從另一個使用者的商務用 Skype 用戶端發起的通訊，將永遠位於使用者 A 的商務用 Skype 用戶端。
- 從*同一個組織中的使用者*在小組用戶端發起的通訊，將永遠位於使用者 a 的小組用戶端。
- 從*外部組織*中的使用者在團隊用戶端發起的通訊將永遠位於使用者 a 的商務用 Skype 用戶端。

如果您已將 Office 365 授權指派給您的使用者，這將是貴組織的預設升級體驗。 當您指派 Office 365 授權時，系統會預設指派 [小組] 和 [商務用 Skype Online] 授權。<sup>2</sup>

為了讓這個方法有效運作，所有使用者都必須同時執行這兩個用戶端。 您可以在商務用 Skype 或團隊用戶端中，將組織內部的內送聊天和組織中的電話撥入至使用者，而不是收件者的控制權。 這取決於寄件者用來啟動通訊的用戶端。 如果寄件者和收件者是在不同的組織中，在 [孤島] 模式中的來電與聊天，在商務用 Skype 用戶端中，將永遠居住在該使用者。

例如，如果您已登入商務用 Skype 而不是 [團隊]，而是由某人從小組中取得訊息，則 [孤島模式收件者] 不會看到該郵件（但最終會收到電子郵件，告知他們在小組中漏掉了郵件）。 同樣地，如果使用者執行的是小組，而不是商務用 Skype，而某人是從商務用 Skype 傳送給使用者的訊息，使用者就不會看到該聊天。 上述每個案例中的行為都與通話類似。 如果使用者不同時執行這兩個用戶端，可能很容易導致不滿。

使用此升級方法，目前狀態也獨立于團隊和商務用 Skype。 這代表使用者 A 的其他使用者可能會看到不同的目前狀態，視它們所使用的用戶端而定。 如需詳細資訊，請參閱目前[狀態](upgrade-to-Teams-on-prem-overview.md#presence)。

- 其他使用者在使用團隊時，會根據使用者在團隊中的活動來查看目前狀態。
- 其他使用者在使用商務用 Skype 時，會根據商務用 Skype 中的使用者 A 活動，查看目前狀態。

當您準備好將使用者升級至 TeamsOnly 模式之後，您可以個別升級使用者，或者您可以使用租使用者原則<sup>3</sup>一次升級整個租使用者。 一旦使用者升級至 TeamsOnly 模式，就會在團隊中收到所有傳入聊天和通話。

不過，在孤島模式中未升級的收件者，可能會繼續在其商務用 Skype 或團隊用戶端的 TeamsOnly 使用者中接收聊天和通話。 在現有的交談中，TeamsOnly 使用者將會回復寄件者啟動聊天或通話的客戶。 

從 TeamsOnly 使用者的觀點來看，聊天或通話會一直移至 [孤島] 模式的 [使用者小組用戶端]。 這是因為小組用戶端會針對小組與團隊成員以及商務用 Skype 通訊（即使是針對相同的使用者），為小組對等小組的交談進行單獨的交談執行緒。 若要深入瞭解，請參閱[團隊交談-互通性與原生執行緒](upgrade-to-Teams-on-prem-overview.md#teams-conversations---interop-versus-native-threads)。

下表摘要列出了孤島模式與 TeamsOnly 模式的團隊體驗：

| 團隊經驗 | 在孤島模式中 | 在 TeamsOnly 模式中 |
|:------------------ | :------------------- | :------------------ |
| 傳入聊天與接聽的通話：|  團隊或商務用 Skype | Teams |
| 在下列情況中接收 PSTN 通話： | 商務用 Skype <br>（在 [孤島] 模式中不支援使用團隊中的 PSTN 功能。）     | Teams |   
 |目前狀態    | 商務用 Skype 和團隊中的目前狀態是獨立的。 針對相同的孤島使用者，使用者可能會看到不同的狀態，視它們所使用的用戶端而定。 | 目前狀態僅根據使用者在團隊中的活動而定。 所有其他使用者（無論他們使用的用戶端），請參閱目前狀態。 | 
 | 會議排程    | 使用者可以在小組或商務用 Skype 中排程會議。 根據預設，他們會在 Outlook 中看到兩個增益集。 您可以設定團隊會議原則，以控制使用者是否只能使用 [團隊會議] 增益集，或是同時使用團隊會議增益集和商務用 Skype 會議增益集（**即將推出**）。 若要深入瞭解，請參閱[以孤島模式設定使用者的會議提供者](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode)。 |     使用者只會在團隊中排程會議。 只有 [團隊] 增益集可在 Outlook 中使用。 | 

下表摘要列出使用重迭的功能方法將您的組織遷移至團隊的優點與缺點。

| 專業人員     |       利弊 |
| :------------------ | :---------------- |
| 可在組織內快速採用。| 因為有兩個用戶端具有相似的功能，但使用者介面不同，所以可能造成使用者混淆。 此外，他們也無法控制傳入聊天/呼叫居住在哪個用戶端。 |
| 允許使用者在仍擁有商務用 Skype 的完整存取權的情況下，瞭解並熟悉團隊。 | 如果使用者不是同時執行這兩個用戶端，可能會造成使用者不滿意的可能性。|
| 在團隊中開始使用最少的管理工作量。 | 在「使用孤島」模式時，如果使用者與他們經常與之通訊的使用者不是使用小組，就能成為 TeamsOnly 模式的挑戰。|
|讓使用者能夠利用功能來增強商務用 Skype 中不提供的小組合作。| 在內部部署與團隊使用商務用 Skype 的使用者，將無法與使用商務用 Skype 內部部署的其他使用者通訊，但也沒有團隊。  |

<sup>2</sup>即使使用者是在商務用 Skype 伺服器中託管內部部署，也是如此。 無論使用者是駐留在內部部署還是線上，都可以讓商務用 Skype Online 授權保持啟用，因為這是完整的小組功能目前所需要的。

<sup>3</sup>請注意，只有當您將 TeamsUpgradePolicy 套用至個別使用者，而不是每個租使用者時，才會觸發將商務用 Skype 會議遷移至團隊會議。 請參閱[會議遷移](upgrade-to-Teams-on-prem-overview.md#meeting-migration)以取得詳細資料。

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>選取功能方法（使用商務用 Skype 模式）

有些組織可能想要讓他們的使用者在組織從商務用 Skype 轉換為團隊時更能預知的體驗。 在這個模型中，IT 系統管理員會在 TeamsUpgradePolicy 中使用其中一個商務用 Skype 模式，明確指定在遷移至 TeamsOnly 模式前，在商務用 Skype 中保留哪些功能。 當他們準備好將選取的功能移至 TeamsOnly 模式時，系統管理員會更新這些使用者的 TeamsOnly 模式。 在此轉換期間：

- 系統管理員有選項可讓使用者啟用特定團隊功能，同時在使用者移至 TeamsOnly 體驗之前，在商務用 Skype 中保持聊天和通話功能。 系統管理可讓團隊共同作業功能或團隊會議 + 共同作業功能。
- 無論是來自其他使用者的小組或商務用 Skype 用戶端，仍在商務用 Skype 中的使用者都會收到其商務用 Skype 用戶端的所有傳入聊天和通話。 此外，對於這些商務用 Skype 使用者，小組用戶端中的通話與聊天功能已停用，以協助避免使用者混淆，並確保正確地進行路由與目前狀態。
- 在 TeamsOnly 模式中的使用者會在其團隊用戶端中接收所有內送聊天和來電，而不管通訊源自何處：團隊、商務用 Skype 或任何類型的同盟使用者。

與重迭的功能方法不同，在 [選取功能] 方法中，使用商務用 Skype 的使用者可以與 TeamsOnly 中的使用者進行通訊。 商務用 Skype 使用者與團隊使用者之間的通訊稱為[互通性](upgrade-to-Teams-on-prem-overview.md#interoperability)或 "互通性"。 在商務用 Skype 和小組中的另一個使用者之間，互通性通訊可能是一對一的。 此外，受邀的使用者永遠都可以加入商務用 Skype 或團隊會議，但是他們必須使用與會議類型相對應的用戶端。 如需詳細資訊，請參閱[會議](upgrade-to-Teams-on-prem-overview.md#meetings)。

針對 [選取功能] 方法中的使用者，無論其他使用者使用哪一個用戶端，使用者的目前狀態都是一致的。 如果使用者使用的是其中一種商務用 Skype 模式，所有其他使用者都會在商務用 Skype 中根據該使用者的活動查看目前狀態。 同樣地，如果使用者處於 TeamsOnly 模式，則所有其他使用者會根據團隊中該使用者的活動查看目前狀態。 如需詳細資訊，請參閱目前[狀態](upgrade-to-Teams-on-prem-overview.md#presence)。

針對已選擇追蹤 [選取功能] 方法的組織，系統管理員應該將租使用者範圍的模式從孤島變更為適當的商務用 Skype 共存模式（SfbWithTeamsCollab 或 SfBWithTeamsCollabAndMeetings）。  

來賓使用者體驗會遵循指派給租使用者的共存模式。 如果您在租使用者層級設定商務用 Skype 模式，來賓就無法聊天、通話或顯示其目前狀態。 若要深入了解，請閱讀 [Teams 中的來賓存取](guest-access.md) (英文)。

當模式從孤島變更為 SfbWithTeamsCollab 時，如果使用者使用的是商務用 Skype，就不會有任何差異。 不過，如果使用者要開始使用小組，就只會對功能（例如團隊 & 頻道和檔案）公開。 小組中不提供聊天、通話和會議排程，因為系統管理員擁有（適用于目前）指派商務用 Skype 作為這些功能的所需用戶端。

> [!NOTE]
> 當使用者從孤島變更為其中一個商務用 Skype 模式時，與使用者進行通訊的任何其他使用者的小組用戶端都需要知道使用者 A 的模式已變更，讓使用者 A 將通訊路由到適當的用戶端。對於已建立與使用者 A 的原生團隊與團隊聊天的任何使用者，可能需要花時間讓這些其他使用者的小組用戶端知道從孤島變更為任何商務用 Skype 模式的模式。 當系統管理員準備好時，他們可以將使用者的模式更新為 TeamsOnly，將指定使用者的聊天、通話及會議排程一次性移至團隊。

或者，管理員只能將會議排程轉移至團隊，同時使用 SfBWithTeamsCollabAndMeetings 模式在商務用 Skype 中離開交談和通話功能。 此模式可讓組織轉換成會議小組，如果使用者尚未準備好移至 TeamsOnly 模式（例如，您還沒有準備好要遷移現有的 PSTN 功能）。 此過渡案例會[先稱為會議](meetings-first.md)。


|團隊經驗  |在 SfBWithTeamsCollab 模式中 |在 SfBWithTeamsCollabAndMeetings 模式中 |在 TeamsOnly 模式中  |
|---------|---------|---------|---------|
|貴組織中的使用者傳入聊天和 VOIP 通話的方式如下：     | 商務用 Skype        | 商務用 Skype       | Teams        |
|在下列情況中接收 PSTN 通話：     | 商務用 Skype        |商務用 Skype         | Teams        |
|目前狀態     | 商務用 Skype        |商務用 Skype         | Teams        |
|會議排程     | 商務用 Skype         | Teams        | Teams        |


下表摘要列出使用商務用 Skype 模式做為 TeamsOnly 模式的過渡階段的優點與缺點。

| 專業人員     |       利弊 |
| :------------------ | :---------------- |
| 可預測的最終使用者路由。 根據系統管理員的選取，在商務用 Skype 或團隊（但不是兩者）中，所有通話和聊天都是居住的。|互通性交談缺少豐富文字、檔案共用及螢幕共用的支援。 這可以在利用 [立即開會] 功能來啟動會議中解決。 |
|可能會降低使用者的混亂，因為只有一位用戶端提供指定的功能。 | 使用者無法在商務用 Skype 中執行常見活動（例如聊天及呼叫升級至 TeamsOnly），而讓使用者無法存取小組。|
|系統管理員已進一步控制從商務用 Skype 轉換至團隊時可供使用者使用的一組功能。 | |
| 允許組織使用團隊進行會議，即使尚未準備好將其完全移至 TeamsOnly 模式。||
|依其他人查看指定使用者的狀態，不論他們使用的是哪一個用戶端，都是一樣的。||

## <a name="summary-of-upgrade-methods"></a>升級方法摘要
下表摘要列出升級的方法：


|重迭的功能（使用孤島模式）  |選取的功能（使用商務用 Skype 模式）  |
|---------|---------|
|在升級到 TeamsOnly 之前，使用者必須同時執行這兩個用戶端，因為傳入聊天和通話可能會在其中一個用戶端中進行。     | [聊天] 只會根據收件者的模式，在一個用戶端中呼叫土地。 未升級的使用者可以同時執行這兩個用戶端，但不存在任何正常的重迭（在小組中不提供通話與聊天）。         |
|可讓系統管理員在商務用 Skype 和小組中，在小組中引入重迭的功能（聊天、會議、VOIP 通話），以及團隊中的新功能（團隊和頻道）。     | 允許系統管理員將團隊的選取功能引入至使用者（團隊和頻道），但不提供與商務用 Skype 中同樣存在的功能。        |
|在商務用 Skype 與團隊之間的互通性，在兩個使用者都是孤島模式時不存在。      |商務用 Skype 與團隊使用者之間的通訊需要互通性。         |

> [!NOTE]
> 如果您無法追蹤將商務用 Skype 伺服器使用者遷移至小組所支援的方法，您可以在 Active Directory 中移除商務用 Skype Server 及所有相關的使用者屬性，將您的使用者轉成小組。 一旦使用者的 Azure Active Directory 屬性已清除商務用 Skype Server 屬性，且 DNS 記錄已重新指向 Office 365，就可以授權 Office 365 中的使用者，並將其升級至團隊。 

> [!IMPORTANT]
> 透過轉移的遷移，就不會將連絡人資料和會議資料從內部部署環境遷移至 Microsoft 團隊。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>決策點</td><td><ul> 哪些升級旅程適合貴組織的業務需求？<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>後續步驟</td><td><ul> 找出您目前的部署模型、使用案例案例，以及貴組織的重要考慮，將會通知您的小組最適合您的組織。<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>決策點</td><td><ul> 哪些升級案例適用于您的組織？<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul> 根據訊息、會議和通話業務需求，決定貴組織的升級歷程時間軸。<br><br> 決定完成升級歷程所需的其他工作。<br><br></ul></td></tr>
</table>

為您的組織選擇最佳升級歷程後，請[執行您的團隊升級](https://aka.ms/SkypeToTeams-Upgrade)。

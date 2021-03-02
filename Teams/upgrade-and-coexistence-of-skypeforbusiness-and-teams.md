---
title: 選擇從商務用 Skype 到 Microsoft Teams 的升級旅程
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl, bjwhalen
description: 商務用 Skype 和 Microsoft Teams 共存選項詳細資料，以及 Teams 可能的升級程式，以及範例案例。
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
ms.openlocfilehash: a81b34bb028d81e7a79d771db7f0f406af364011
ms.sourcegitcommit: 79b19b326ef40bf04af03021a7c6506fdd9417ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2021
ms.locfileid: "50397418"
---
# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>選擇從商務用 Skype 到 Teams 的升級旅程

![升級歷程圖，強調專案定義階段](media/upgrade-banner-project-definition.png "升級階段，強調專案定義階段")

本文是升級過程中專案定義階段的一部分。 繼續進行之前，請確認您已完成下列活動：

- [已招募專案專案關係人](upgrade-enlist-stakeholders.md)
- [已定義您的專案範圍](https://aka.ms/SkypetoTeams-Scope)
- [瞭解商務用 Skype 和 Teams 的共存和互通性](https://aka.ms/SkypeToTeams-Coexist)

做為現有的商務用 Skype 客戶，您完全轉換到 Teams 可能需要一些時間。 不過，您可以讓使用者在商務用 Skype 中使用 Teams，立即開始實現 Teams 的價值。 由於這兩個 App 之間有些重迭的功能，建議您查看可用的共存和升級模式，協助判斷哪一個路徑適合您的組織。 例如，您可以選擇在兩種解決方案上啟用所有工作負載，而不需要互通性。 或者，您可以決定管理使用者體驗，方法包括逐步引進 Teams 功能，或將特定功能的目標使用者群組鎖定在一起，直到您的組織準備好將所有人升級至 Teams。 使用您的試驗結果，協助評估貴組織的正確升級歷程。

> [!IMPORTANT]
> 商務用 Skype Online 將於 2021 年 7 月 31 日淘汰，之後將無法再存取也不再受支援。 為了最大化權益的最大化並確保貴組織有適當的時間來實做升級，我們建議您立即開始使用 Microsoft Teams。

本文概述各種模式，以便管理商務用 Skype 和 Teams 中的哪些形式可供使用者使用。 就像任何部署一樣，我們強烈建議您先與[](pilot-essentials.md)選取的使用者群組試驗您的預定計劃，再將貴組織升級至 Teams。 請記住，引進新的技術可能會干擾使用者。 在執行本文所述的任何模式之前，請花一些時間評估使用者的備戰能力，並實行通訊和訓練計畫。

> [!TIP]
> 與我們一起參與即時互動式研討會，我們將分享指導、最佳做法和資源，這些工作旨在開始規劃及實作升級。
>
>首先 [加入規劃升級](https://aka.ms/SkypeToTeamsPlanning) 會話以開始使用。


## <a name="upgrade-journey-building-blocks"></a>升級過程中建組塊

若要為貴組織進行 Teams 之旅的正式準備，您需要開始規劃升級案例，最終讓貴組織完全採用 Teams 做為您唯一的通訊和共同合作解決方案。

若要協助引導您的決策程式，請熟悉從商務用 Skype 升級至 Teams 的相關各種模式、概念和術語。 詳細資訊請參閱 Microsoft [Teams 和商務用 Skype 共存和互通性](https://aka.ms/SkypeToTeams-Coexist)。

> [!NOTE]
> 您也需要考慮語音移移案例。 電話系統是 Microsoft 在 Microsoft 365 或 Office 365 雲端中啟用呼叫控制和私人分支 Exchange (PBX) 功能的技術。 若要將電話系統連接到公用交換電話網路 (PSTN) ，讓使用者可以撥打全球電話，您可以根據您的業務需求選擇選項。 有關電話系統和 PSTN 連接選項的詳細資訊，請參閱 [語音 - 電話系統和 PSTN 連接](cloud-voice-landing-page.md)。

已移入 Teams 的使用者除了加入商務用 Skype 所主持的會議之外，不會再使用商務用 Skype 用戶端。 不論寄件者是使用 Teams 還是商務用 Skype，所有傳入的聊天和通話都會進入使用者的 Teams 用戶端。 升級後的使用者所組織的任何新會議都會排程為 Teams 會議。 如果使用者嘗試使用商務用 Skype 用戶端，初始化聊天和通話會<sup>封鎖 1。</sup> 不過，使用者可以 (，) 商務用 Skype 用戶端加入受邀的會議。

系統管理員使用[TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)的屬性[](migration-interop-guidance-for-teams-with-skype.md)模式概念來管理轉換到 Teams 的概念。 如上述所述，已移移至 Teams 的使用者為「TeamsOnly」模式。 針對移轉至 Teams 的組織，最終的目標是將所有使用者移至 TeamsOnly 模式。

使用商務用 Skype 將現有組織移 (兩種方法，無論是線上或內部部署) Teams：

- **使用** 群島模式 (的重迭功能方法) ：現有商務用 Skype 組織的使用者會加入 Teams，這樣他們才能在移置階段同時使用兩個用戶端。 在這期間，Teams 的多數功能 ，但並非全部，可供他們使用。 此配置的模式稱為群島，且這是任何使用商務用 Skype 的現有組織的預設模式。 組織準備就緒後，系統管理員會將使用者移至 TeamsOnly 模式。

- 選取功能 **方法 (使用** 一或多個商務用 Skype 模式) ：系統管理員管理從商務用 Skype 轉換 (到 Teams) 的聊天、通話和會議排程功能，供其組織的使用者使用。 這些函數分別可在商務用 Skype 或 Teams 中使用，但不能同時提供。 系統管理員使用 TeamsUpgradePolicy 來控制何時將這項功能移轉至其使用者的 Teams。 尚未使用 TeamsOnly 模式的使用者會繼續使用商務用 Skype 進行聊天和通話，而這兩組使用者可以透過交互操作功能進行通訊。 系統管理員會逐步將更多使用者移入 TeamsOnly 模式來管理轉換。

<sup>1</sup> 2017 之前出貨的舊版商務用 Skype 用戶端未遵守 TeamsUpgradePolicy。 請確定您使用的是 Office 頻道中的最新商務用 Skype 用戶端。

瞭解並選擇升級方法之後，您可以瞭解管理貴組織升級至 [Teams 的工具](upgrade-to-teams-on-prem-tools.md)。

以下是可協助決定貴組織適用路徑的關鍵要素。

## <a name="overlapping-capabilities-method-using-islands-mode"></a>使用群島模式 (重迭功能) 

使用者可以使用重迭的功能方法，同時使用 Teams 和商務用 Skype 用戶端進行聊天、VoIP 通話和會議。 在這個方法中，Teams 中的聊天和 VOIP 通話是專注于組織內部，而商務用 Skype 可與外部組織進行聊天和 VOIP/PSTN 通話 (如果已) 。 這兩種產品都可以排程和參加會議。

使用重迭功能的方法時，商務用 Skype 和 Teams 的通訊流量會保持獨立 (即使對相同的使用者) ，兩個不同的用戶端也永遠不會與同一組織內部 (使用者彼此通訊) 。 使用者體驗是根據收件者的組配置。 例如，假設收件者使用者 A 是在群島模式：

- 從其他使用者的商務用 Skype 用戶端啟動的通訊一定會位於 User A 的商務用 Skype 用戶端。

- 從同一個組織中使用者啟動的Teams 用戶端通訊一定會位於 User A 的 Teams 用戶端。

- 由外部組織使用者從 Teams用戶端啟動的通訊一定會位於 User A 的商務用 Skype 用戶端。

如果您已指派 Microsoft 365 或 Office 365 授權給使用者，這會是貴組織的預設升級體驗。 當您指派 Microsoft 365 或 Office 365 授權時，系統預設會同時指派 Teams 和商務用 Skype Online 授權。<sup>2</sup>

若要讓這個方法有效運作，所有使用者都必須同時執行這兩個用戶端。 在群島模式中，組織內部的來電和來電可登入商務用 Skype 或 Teams 用戶端，且收件者不在此控管。 這取決於寄件者用來啟動通訊的用戶端。 如果寄件者和收件者位於不同的組織，在群島模式中，使用者的來電和聊天一定位於商務用 Skype 用戶端。

例如，如果群島模式收件者已登錄商務用 Skype 而非 Teams，而某人從 Teams 收到訊息，則群島模式收件者將不會看到訊息 (但最後會收到一封電子郵件，指出他們在 Teams) 中錯過訊息。 同樣地，如果使用者執行的是 Teams，但並未執行商務用 Skype，以及有人從商務用 Skype 執行使用者訊息，使用者將不會看到該聊天。 上述每一種情況的行為在通話時都是類似的。 如果使用者不同時執行這兩個用戶端，很容易會導致挫折。

當您使用此升級方法時，Teams 和商務用 Skype 之間的目前狀態也會獨立地作用。 這表示其他使用者可能會看到使用者 A 不同的目前狀態，視他們使用的用戶端不同。 詳情請參閱目前 [狀態](teams-and-skypeforbusiness-coexistence-and-interoperability.md#presence)。

- 其他使用者在使用 Teams 時，將會根據 Teams 中的使用者 A 活動來查看目前狀態。

- 其他使用者在使用商務用 Skype 時，將會根據商務用 Skype 中的使用者 A 活動來查看目前狀態。

準備好將使用者升級至 TeamsOnly 模式後，您可以個別升級使用者，或者您可以使用全租使用者政策<sup>3</sup>一次升級整個租使用者。 一旦使用者升級至 TeamsOnly 模式，他們會收到 Teams 中所有傳入的聊天和通話。  (請注意，只有在將 TeamsUpgradePolicy 適用于個別使用者時，才能觸發將商務用 Skype 會議移至 Teams 會議，而不是每個租使用者。 請參閱 [會議移移](upgrade-to-teams-on-prem-tools.md#meeting-migration) 以瞭解詳細資料。) 

不過，在群島模式中未升級的收件者可能會繼續在商務用 Skype 或 Teams 用戶端中接收 TeamsOnly 使用者的聊天和通話。 對於現有的交談，TeamsOnly 使用者將回復寄件者啟動聊天或通話的用戶端。 

對於 TeamsOnly 使用者觀點的新交談，聊天或通話一定會前往 Islands 模式使用者 Teams 用戶端。 這是因為 Teams 用戶端會針對 Teams-to-Teams 和 Teams-to-Skype 商務用通訊維護個別的交談對話，即使同一個使用者也一樣。 若要深入瞭解，請參閱 [Teams 交談 - 交互操作與原生對話](teams-and-skypeforbusiness-coexistence-and-interoperability.md#interoperability)。

下表摘要列出群島模式和 TeamsOnly 模式的 Teams 體驗：

| Teams 體驗 | 在群島模式中 | 在 TeamsOnly 模式中 |
|:------------------ | :------------------- | :------------------ |
| 在 ：|  Teams 或商務用 Skype | Teams |
| PSTN 通話接收方式為： | 商務用 Skype <br> (在 Teams 中使用 PSTN 功能在群島模式中不受支援。)      | Teams |   
 |目前狀態    | 商務用 Skype 和 Teams 中的目前狀態是獨立的。 使用者可能會看到同一個群島使用者的不同狀態，視他們使用的用戶端而不同。 | 目前狀態僅根據使用者在 Teams 中的活動。 所有其他使用者 ，無論他們使用哪個用戶端，都會看到該目前狀態。 | 
 | 會議排程    | 使用者可以在 Teams 或商務用 Skype 中排程會議。 根據預設，他們會在 Outlook 中同時看到這兩個附加元件。 您可以設定 Teams 會議政策，以控制使用者是否只能使用 Teams 會議附加元件，或同時使用 Teams 會議與商務用 Skype 會議附加元件。若要深入瞭解，請參閱 [設定以群島模式為使用者設定會議提供者](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode)。 |     使用者只會在 Teams 中排程會議。 Outlook 中僅提供 Teams 附加元件。 | 

下表摘要列出使用重迭功能方法將貴組織遷移到 Teams 的優缺點。

| 專業人員     |       缺點 |
| :------------------ | :---------------- |
| 允許在組織中快速採用。| 使用者可能會因為有兩個功能相似，但使用者介面不同而造成混淆的用戶端。 此外，他們無法控制傳入聊天/通話的進入用戶端。 |
| 允許使用者學習並熟悉 Teams，同時仍擁有商務用 Skype 的完整存取權。 | 如果使用者未執行這兩個用戶端，使用者可能會因為錯過的郵件而不滿意。|
| 在 Teams 中開始進行管理的工作最少。 | 如果使用者和經常通訊的使用者並未主動使用 Teams，可能難以進入「離開群島」模式並移至 TeamsOnly 模式。 例如，一旦將一部分使用者升級至 TeamsOnly 模式，這些使用者只會在 Teams 中傳送。 對於以群島模式其餘的人口，這些訊息一定會在 Teams 中登陸。 但如果其中一部分人口沒有在 Teams 中運作，他們會認為這些訊息未接。|
|讓使用者能夠運用功能，強化商務用 Skype 中未提供的團隊合作。| 在內部部署和 Teams 使用商務用 Skype 的使用者無法與在內部部署使用商務用 Skype 但沒有 Teams 的另一個使用者通訊。  |
|  | 使用 Teams 時，在商務用 Skype Server 中擁有內部部署帳戶的使用者沒有交互操作或聯盟支援。  如果您混合使用群島使用者 ，其中一些使用者位於商務用 Skype Online，有些則位於內部部署商務用 Skype，這可能會導致混淆。   |

<sup>2</sup> 即使使用者位於商務用 Skype Server 內部部署，也一樣。 不論使用者位於內部部署或線上，請保持啟用商務用 Skype Online 授權，因為目前需要該授權才能使用完整的 Teams 功能。

<sup>3</sup> 請注意，只有在將 TeamsUpgradePolicy 適用于個別使用者時，才能觸發將商務用 Skype 會議移至 Teams 會議，而不是每個租使用者。 請參閱 [會議移移](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms) 以瞭解詳細資料。

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>使用商務用 Skype (的選取功能方法) 

當組織從商務用 Skype 轉換到 Teams 時，有些組織可能會偏好為使用者提供更可預測的體驗。 在此模型中，IT 系統管理員使用 TeamsUpgradePolicy 中的其中一種商務用 Skype 模式，在移為 TeamsOnly 模式之前，明確指定哪些功能保留在商務用 Skype 中。 當他們準備好將選取的功能移轉至 TeamsOnly 模式時，系統管理員會更新這些使用者的模式至 TeamsOnly。 在此轉換期間：

- 系統管理員有選項可讓使用者啟用特定 Teams 功能，同時在使用者移至 TeamsOnly 體驗之前，同時保留商務用 Skype 中的聊天和通話功能。 系統管理可以啟用 Teams 共同合作功能或 Teams 會議 + 共同合作功能。

- 仍在商務用 Skype 上的使用者，無論通訊是否來自其他使用者的 Teams 或商務用 Skype 用戶端，都能在商務用 Skype 用戶端中接收所有傳入的聊天和通話。 此外，針對這些商務用 Skype 使用者，Teams 用戶端中的通話和聊天功能會停用，以防止使用者混淆並確保正確的路由和目前狀態。

- TeamsOnly 模式的使用者會以 Teams 用戶端接收所有傳入的聊天和通話，而不論通訊來自何處，Teams 都會提供目前狀態：Teams、商務用 Skype 或任何一種聯盟使用者。

與群島 (重迭) 不同，在選取功能方法中，使用商務用 Skype 的使用者可以與 TeamsOnly 中的使用者通訊。 商務用 Skype 使用者與 Teams 使用者之間的通訊稱為 [互通性或「](teams-and-skypeforbusiness-coexistence-and-interoperability.md#interoperability) 交互操作」。 在商務用 Skype 中的使用者與 Teams 中的另一個使用者之間，可以一對一進行交談和通話的交互操作通訊。 此外，受邀的使用者可以一直加入商務用 Skype 或 Teams 會議，不過，他們必須使用與會議類型對應的用戶端。 詳細資訊請參閱 [會議](teams-and-skypeforbusiness-coexistence-and-interoperability.md#meetings)。

對於採用特定功能轉換方法的使用者，無論其他使用者使用哪一個用戶端，使用者的目前狀態都是一致的。 如果使用者使用其中一種商務用 Skype 模式，則所有其他使用者在商務用 Skype 中的活動都能看到目前狀態。 同樣地，如果使用者是在 TeamsOnly 模式中，所有其他使用者會根據該使用者在 Teams 中的活動，看到目前狀態。 詳情請參閱目前 [狀態](teams-and-skypeforbusiness-coexistence-and-interoperability.md#presence)。

對於尚未開始使用 Teams 的組織，系統管理員應該將全租使用者模式從群島變更為 SfbWithTeamsCollab。  (對於已經有一些 Teams 使用方式的組織，系統管理員應「管理」已在 Teams 中作用中的使用者，以確保這項變更不適用於他們。 詳細資料請參閱已在群島模式中使用 [Teams](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)的組織選取功能方法。)  

來賓使用者體驗會遵循指派給租使用者的共存模式。 如果您在租使用者層級設定商務用 Skype 模式，來賓無法聊天、通話或顯示其目前狀態。 若要深入了解，請閱讀 [Teams 中的來賓存取](guest-access.md) (英文)。

當模式從群島變更為 SfbWithTeamsCollab 時，從未使用 Teams 的使用者將看不到他們使用商務用 Skype 的方式差異。 不過，如果使用者開始使用 Teams，他們只會公開 Teams &和檔案等功能。 在 Teams 中無法進行聊天、通話和會議排程，因為系統管理員 () 指定商務用 Skype 做為這些功能所需的用戶端。

> [!NOTE]
> 當使用者 A 從群島變更為其中一個商務用 Skype 模式時，任何與使用者 A 通訊的其他使用者的 Teams 用戶端必須知道使用者 A 的模式已變更，因此可以將通訊路由至適用于 User A 的用戶端。對於已經與使用者 A 建立原生 Teams 對 Teams 聊天的任何使用者，這些其他使用者的 Teams 用戶端最多可能需要 36 小時，才能知道模式從群島變更為任何商務用 Skype 模式。 相反地，其他用戶端在 2 小時內發現現有使用者對 TeamsOnly 模式的變更。<br>
> 當系統管理員準備好時，他們可以將使用者的模式更新為 TeamsOnly，將使用者的聊天、通話和會議排程一次全部移到 Teams。

或者，系統管理員可以先將會議排程移至 Teams，同時使用 SfBWithTeamsCollabAndMeetings 模式離開商務用 Skype 中的聊天和通話功能。 此模式可讓組織轉換到 Teams 進行會議，如果使用者尚未準備好移至 TeamsOnly 模式 (例如，如果您尚未準備好移轉現有的 PSTN 功能) 。 此部署案例稱為會議 [第一](meetings-first.md)。


|Teams 體驗  |在 SfBWithTeamsCollab 模式中 |在 SfBWithTeamsCollabAndMeetings 模式中 |在 TeamsOnly 模式中  |
|---------|---------|---------|---------|
|在貴組織中收到來自使用者的傳入聊天和 VOIP 通話：     | 商務用 Skype        | 商務用 Skype       | Teams        |
|PSTN 通話接收方式為：     | 商務用 Skype        |商務用 Skype         | Teams        |
|目前狀態     | 商務用 Skype        |商務用 Skype         | Teams        |
|會議排程     | 商務用 Skype         | Teams        | Teams        |


下表摘要列出使用商務用 Skype 模式做為 TeamsOnly 模式的一項退利措施的優缺點。

| 專業人員     |       缺點 |
| :------------------ | :---------------- |
| 使用者可預測的路由。 所有通話和聊天都位於商務用 Skype 或 Teams (，但無法同時) 管理員選擇。|交互操作交談不支援豐富的文字、檔案共用和螢幕共用。 您可以運用立即開會功能來啟動會議。 |
|可能會減少使用者混淆，因為只有一個用戶端才能使用某一項功能。 | 在使用者升級到 TeamsOnly 之前，他們無法存取在商務用 Skype 中執行的一般活動 ，例如聊天和通話。 也就是說，沒有並排功能。|
|系統管理員在從商務用 Skype 轉換到 Teams 時，可控制提供給使用者的一組功能。 此控制項包含以增量方式引入 Teams 功能的功能。 | |
| 允許組織使用 Teams 進行會議，即使尚未準備好完全移至 TeamsOnly 模式。||
|不論使用者使用哪一個用戶端，其他人所查看的一個使用者的目前狀態都是一樣的。||

## <a name="summary-of-upgrade-methods"></a>升級方法摘要
下表摘要列出升級方法：


|使用群島模式 (重迭)   |已選取 (商務用 Skype 模式)   |
|---------|---------|
|在升級到 TeamsOnly 之前，使用者必須同時執行這兩個用戶端，因為傳入聊天和通話可能會進入任一用戶端。     | 根據收件者的模式，聊天和通話只能在一個用戶端上進行。 未升級的使用者可以同時執行這兩個用戶端，但通話和聊天 (Teams) 。 系統管理員也可以控制使用者是否要在 Teams 或商務用 Skype 中排程會議。         |
|允許系統管理員在商務用 Skype 和 Teams 中向使用者介紹重迭的功能 (聊天、會議、VOIP 通話)  (讓使用者) 以及 Teams 中的新功能 (Teams 和頻道) 。     | 允許系統管理員向 Teams 和頻道 (的 (使用者介紹 Teams 的選取功能) 但不供應商務用 Skype 中同樣存在的功能。        |
|商務用 Skype 和 Teams 之間不存在，而兩個使用者都位於群島模式。 一旦部分使用者升級至 TeamsOnly 交互操作交談後，這些使用者和仍在群島模式的其他使用者之間可能會發生。 不過，群島使用者可以選擇使用 Teams 並避免交互操作交談。      |商務用 Skype 和 Teams 使用者之間的通訊需要交互操作。         |

> [!NOTE]
> 如果您無法遵循支援的方法將商務用 Skype Server 使用者移轉至 Teams，可能會移除 Active Directory 中的商務用 Skype Server 和所有相關的使用者屬性，將使用者移轉至 Teams。 一旦使用者 Azure Active Directory 屬性已清除商務用 Skype Server 屬性，且 DNS 記錄已重新指向 Microsoft 365 或 Office 365，則有可能授權 Microsoft 365 或 Office 365 中的使用者，並升級至 Teams。 

> [!IMPORTANT]
> 完全移移後，連絡人資料和會議資料不會從內部部署環境移移至 Microsoft Teams。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>決策點</td><td><ul> 哪一個升級歷程適合貴組織的商務需求？<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>後續步驟</td><td><ul> 識別您目前的部署模型、使用案例，以及貴組織的重要考慮，有助於瞭解使用最適合貴組織之 Teams 的歷程。<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>決策點</td><td><ul> 貴組織適用哪一種升級案例？<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul> 根據訊息、會議和通話商務需求，決定貴組織升級歷程的時程表。<br><br> 決定完成升級旅程所需的額外工作。<br><br></ul></td></tr>
</table>

為貴組織選擇最佳的升級旅程之後，請[執行升級至 Teams。](https://aka.ms/SkypeToTeams-Upgrade)

## <a name="related-links"></a>相關連結

[適用于將 Teams 與商務用 Skype 一起使用的組織之移移和互通性指南](migration-interop-guidance-for-teams-with-skype.md) 

[設定商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用會議移 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)


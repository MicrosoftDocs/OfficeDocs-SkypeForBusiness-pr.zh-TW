---
title: 選擇從 商務用 Skype 到 Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl, bjwhalen
description: 詳細資料商務用 Skype Microsoft Teams共存選項，以及可能的升級Teams範例案例。
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
ms.openlocfilehash: 425083bacb5664915f66485cae6f5a86f780aa7a
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282310"
---
# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>選擇從 商務用 Skype 到 Teams

![升級歷程圖，強調定義Project階段](media/upgrade-banner-project-definition.png "升級歷程的階段，強調定義Project階段")

本文是升級過程中Project定義階段的一部分。 繼續進行之前，請確認您已完成下列活動：

- [已招募專案專案關係人](upgrade-enlist-stakeholders.md)
- [已定義專案範圍](./upgrade-define-project-scope.md)
- [瞭解共同使用和商務用 Skype互通性Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)

做為現有的商務用 Skype，您完全轉換Teams可能需要一些時間。 不過，您可以讓使用者與 Teams一起使用Teams，開始商務用 Skype。 由於這兩個 App 之間有些重迭的功能，建議您查看可用的共存和升級模式，協助判斷適合貴組織的路徑。 例如，您可以選擇在兩個解決方案上啟用所有工作負載，而不需要互通性。 或者，您可以決定管理使用者體驗，方法可以是逐步引進 Teams 功能，或將使用者群組作為選取功能的目標，直到您的組織準備好將每個人升級為 Teams。 使用您的試驗結果，協助評估貴組織正確的升級歷程。

> [!IMPORTANT]
> 商務用 Skype Online 將於 2021 年 7 月 31 日淘汰，之後將無法再存取也不再受支援。 為了最大化效益的實現，並確保貴組織有適當的時間實做您的升級，我們鼓勵您立即開始Microsoft Teams旅程。

本文概述各種模式，可讓使用者管理哪些商務用 Skype Teams模式可供使用者使用。 和任何部署一樣，我們強烈建議您先與[](pilot-essentials.md)選取的使用者群組試驗您的預定計劃，然後再將貴組織升級為Teams。 請記住，引進新技術會對使用者造成干擾。 在執行本文所述的任何模式之前，請花一些時間評估使用者的準備狀態，並實行通訊和訓練計畫。

> [!TIP]
> 與我們一起參與即時互動式研討會，我們將在這裡分享指導、最佳做法和資源，以啟動升級規劃與實作。
>
>首先 [加入規劃升級](./upgrade-workshops-landing-page.yml) 會話以開始使用。


## <a name="upgrade-journey-building-blocks"></a>升級旅程建組塊

若要正式準備貴組織Teams，您必須開始規劃升級案例，最終讓貴組織完全接受 Teams 做為您唯一的通訊和共同合作解決方案。

若要協助引導您的決策程式，請熟悉各種模式、概念和術語，以便從商務用 Skype升級Teams。 詳細資訊，請參閱[Microsoft Teams商務用 Skype和互通性。](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)

> [!NOTE]
> 您也需要考慮語音移移案例。 電話系統 Microsoft 在雲端或雲端中啟用通話控制與私人分支 Exchange (PBX) 功能Microsoft 365 Office 365技術。 若要電話系統公用交換電話網絡 (PSTN) ，讓使用者可以撥打全球電話，您可以根據您的業務需求選擇選項。 如要進一電話系統 PSTN 連接選項，請參閱語音[- 電話系統和 PSTN 連接](cloud-voice-landing-page.md)。

已移入至 Teams 的使用者，商務用 Skype用戶端，除非加入以 商務用 Skype。 所有傳入的聊天和通話都會在使用者的用戶端Teams，無論寄件者是使用Teams或商務用 Skype。 升級後的使用者所組織的任何新會議，都會排定為Teams會議。 如果使用者嘗試使用用戶端，商務用 Skype開始聊天和通話<sup>會封鎖 1。</sup> 不過，使用者可以 (，) 用戶端商務用 Skype加入受邀的會議。

系統管理員會使用模式的概念管理Teams模式的概念 ，這是[](migration-interop-guidance-for-teams-with-skype.md) [TeamsUpgradePolicy 的屬性](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps&preserve-view=true)。 如上述所述，已移Teams使用者為 「TeamsOnly」模式。 針對要移轉至 Teams 的組織，最終的目標是將所有使用者移至 TeamsOnly 模式。

有兩種方法可移用線上或內部部署商務用 Skype (現有組織) Teams：

- 使用 (模式) 重迭功能的方法：現有 商務用 Skype 組織的使用者會介紹至 Teams，以便他們在轉換階段期間同時使用這兩個用戶端。 在此期間，他們可以使用大部分功能，但並非全部Teams功能。 此組配置的模式稱為群島，這是任何擁有此帳戶的現有組織的預設商務用 Skype。 組織準備就緒後，系統管理員會將使用者移至 TeamsOnly 模式。

- 選取功能 (使用一或多個 商務用 Skype 模式) ：系統管理員會管理組織中使用者的聊天、通話和會議排程功能 (從 商務用 Skype 到 Teams) 的轉換。 這些函數分別可在 商務用 Skype 或 Teams使用，但兩者均無法同時使用。 系統管理員使用 TeamsUpgradePolicy 控制何時將此功能移Teams使用者使用。 尚未使用 TeamsOnly 模式的使用者商務用 Skype聊天和通話，這兩組使用者可以透過交互操作功能通訊。 系統管理員會逐步將更多使用者移轉至 TeamsOnly 模式來管理轉換。

<sup>1</sup> 2017 商務用 Skype之前出貨的舊版用戶端不會遵守 TeamsUpgradePolicy。 請確定您使用的是您頻道商務用 Skype用戶端Office用戶端。

瞭解並選擇升級方法之後，您可以瞭解管理貴組織升級至[Teams。](upgrade-to-teams-on-prem-tools.md)

以下是可協助決定貴組織適用路徑的關鍵要素。

## <a name="overlapping-capabilities-method-using-islands-mode"></a>使用群島模式 (重迭功能) 

使用重迭功能方法，使用者可以同時Teams用戶端商務用 Skype聊天、VoIP 通話和會議。 在這個方法中，Teams 中的聊天和 VOIP 通話是組織內部的焦點，而 商務用 Skype 則啟用與外部組織聊天和 VOIP/PSTN 通話 (如果已) 。 這兩種產品都可以排程和參加會議。

使用重迭功能方法時，商務用 Skype 和 Teams 的通訊流量會保持 (即使對同一個使用者) ，而且兩個不同的用戶端永遠不會與同一組織 (使用者彼此通訊) 。 使用者體驗是根據收件者的組配置。 例如，假設收件者使用者 A 在群島模式中：

- 從其他使用者的用戶端商務用 Skype通訊一定會在 User A 的用戶端商務用 Skype登陸。

- 從同一Teams使用者從用戶端發起的 *通訊*，一定會在 User A Teams用戶端。

- 從外部Teams使用者從用戶端發起的 *通訊*，一定會在 User A 的用戶端商務用 Skype登陸。

如果您已指派授權Microsoft 365或Office 365授權給使用者，這是貴組織的預設升級體驗。 當您指派授權或授權Microsoft 365 Office 365，系統預設會Teams商務用 Skype線上授權。<sup>2</sup>

若要讓這個方法有效運作，所有使用者都必須同時執行這兩個用戶端。 從組織內傳入的聊天和來電到以群島模式的使用者，可以登入 商務用 Skype 或 Teams 用戶端，而且這不在收件者控制之下。 這取決於寄件者用來啟動通訊的用戶端。 如果寄件者和收件者位於不同的組織中，以 Islands 模式傳入來電和聊天給使用者，一商務用 Skype用戶端。

例如，如果群島模式收件者已登錄 商務用 Skype 但並未 Teams，且有人從 Teams 接收郵件，則群島模式收件者不會看到郵件 (但他們最終會收到一封電子郵件，指出他們錯過 Teams) 中的郵件。 同樣地，如果使用者執行的是Teams，商務用 Skype，以及使用者來自 商務用 Skype 的郵件，使用者將不會看到該聊天。 上述每一種情況的行為在通話時都類似。 如果使用者不同時執行這兩個用戶端，很容易造成挫折感。

當您使用此升級方法時，Teams和商務用 Skype狀態也會獨立地工作。 這表示其他使用者可能會看到使用者 A 不同的目前狀態，視他們使用的用戶端而不同。 有關詳細資料，請參閱目前 [狀態](teams-and-skypeforbusiness-coexistence-and-interoperability.md#presence)。

- 其他使用者在使用 Teams時，將會根據使用者 A 在 Teams 中的活動來查看Teams。

- 其他使用者在使用 商務用 Skype，將會根據使用者 A 在 商務用 Skype 中的活動來查看商務用 Skype。

準備好將使用者升級至 TeamsOnly 模式後，您可以個別升級使用者，或者您可以使用整個租使用者政策<sup>3</sup>一次升級整個租使用者。 一旦使用者升級至 TeamsOnly 模式，他們會收到所有傳入的聊天和通話，Teams。  (請注意，將商務用 Skype會議移Teams只會在將 TeamsUpgradePolicy 適用于個別使用者時觸發，而不是以每個租使用者為基礎。 請參閱[會議移) ](upgrade-to-teams-on-prem-tools.md#meeting-migration)

不過，在群島模式中未升級的收件者可能會繼續收到 TeamsOnly 使用者的聊天和通話，包括他們的商務用 Skype或Teams通話。 對於現有的交談，TeamsOnly 使用者將回復寄件者從用戶端啟動聊天或通話。 

對於 TeamsOnly 使用者觀點的新交談，聊天或通話一定會在用戶端上Teams使用者。 這是因為用戶端Teams維護Teams對Teams和Teams對商務用 Skype通訊的個別交談執行緒，即使同一個使用者也一樣。 若要深入瞭解，請參閱[Teams交談 - Interop 與原生執行緒](teams-and-skypeforbusiness-coexistence-and-interoperability.md#interoperability)。

下表摘要列出Teams群島模式和 TeamsOnly 模式的使用體驗：

| Teams體驗 | 在群島模式中 | 在 TeamsOnly 模式中 |
|:------------------ | :------------------- | :------------------ |
| 在中接收的傳入聊天和通話：|  Teams或商務用 Skype | Teams |
| 接收的 PSTN 通話： | 商務用 Skype <br> (在群島模式中Teams PSTN 功能。)      | Teams |   
 |目前狀態    | 在 商務用 Skype 和 Teams中是獨立的。 使用者可能會看到同一個群島使用者的不同狀態，視他們使用的用戶端而不同。 | 目前狀態僅根據使用者在 Teams 中Teams。 所有其他使用者 ，無論他們使用哪個用戶端，都會看到該目前狀態。 | 
 | 會議排程    | 使用者可以在會議或會議Teams商務用 Skype。 根據預設，他們會看到兩個Outlook。 您可以設定Teams，以控制使用者是否只能使用 Teams 會議附加元件，或同時使用 Teams 會議商務用 Skype。若要深入瞭解，請參閱[在群島模式中為使用者設定會議提供者](meeting-policies-in-teams-general.md#meeting-provider-for-islands-mode)。 |     使用者只會在 Teams 中排程Teams。 只有Teams中才能使用Outlook。 | 

下表摘要列出使用重迭功能方法將貴組織遷移到 Teams。

| 專業版     |       缺點 |
| :------------------ | :---------------- |
| 允許在組織中快速採用。| 使用者可能會因為有兩個具有類似功能但使用者介面不同的用戶端而造成使用者混淆。 此外，他們無法控制傳入的聊天/通話會進入哪個用戶端。 |
| 允許使用者學習並熟悉Teams，同時仍可完全存取商務用 Skype。 | 如果使用者未同時執行這兩個用戶端，使用者可能會因為未接郵件而不滿意。|
| 將系統管理投入最少，以開始使用 Teams。 | 如果使用者和經常通訊的使用者並未主動使用「離開島嶼」模式，並移至 TeamsOnly 模式，可能Teams。 例如，一旦將部分使用者升級至 TeamsOnly 模式，這些使用者只會以 Teams。 對於群島模式的其他人口，這些訊息一定會在 Teams。 但如果部分人口並未Teams，他們會認為這些訊息未接。|
|讓使用者能夠運用功能來強化團隊協作，而這些功能在 商務用 Skype。| 在內部商務用 Skype使用 Teams 的使用者將無法從 Teams 與在內部部署使用 商務用 Skype 但沒有Teams 的使用者通訊。  |
|  | 使用Teams時，在 商務用 Skype Server中擁有內部部署帳戶的使用者沒有交互操作或聯盟支援。  如果您混合使用群島使用者 ，其中一些使用者位於 商務用 Skype Online 中，有些則位於內部部署商務用 Skype可能會造成混淆。   |

<sup>2</sup>即使使用者位於內部部署，商務用 Skype Server。 無論使用者是內部部署還是線上，請保持啟用 商務用 Skype Online 授權，因為目前需要它才能Teams功能。

<sup>3</sup>請注意 商務用 Skype，只有在將 TeamsUpgradePolicy Teams個別使用者時，才能觸發將會議移至 Teams 會議，而不是個別租使用者。 請參閱 [會議移移](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms) 以瞭解詳細資料。

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>選取使用 (模式商務用 Skype功能) 

有些組織可能偏好在組織從公司轉換到商務用 Skype時，為Teams。 在此模型中，IT 系統管理員使用 TeamsUpgradePolicy 中的其中一個 商務用 Skype 模式，明確指定哪些功能會保留在 商務用 Skype，才能移至 TeamsOnly 模式。 當他們準備好將選取的功能移轉至 TeamsOnly 模式時，系統管理員會更新這些使用者的模式至 TeamsOnly。 在此轉換期間：

- 系統管理員有選項可讓使用者Teams特定通話功能，同時在使用者移至 TeamsOnly 體驗商務用 Skype保持聊天和通話功能。 系統管理可以Teams共同功能，或Teams會議 + 共同合作功能。

- 仍在商務用 Skype使用者會收到 商務用 Skype 用戶端中所有傳入的聊天和通話，無論通訊是否來自其他使用者的Teams或商務用 Skype用戶端。 此外，針對這些商務用 Skype，Teams 用戶端中的通話和聊天功能會停用，以防止使用者混淆，並確保正確的路由和目前狀態。

- TeamsOnly 模式中的使用者會接收 Teams 用戶端中所有傳入的聊天和通話，而目前狀態是由 Teams 提供，無論通訊來自何處：Teams、商務用 Skype 或任何一種聯盟使用者。

與群島 (方法) 重迭功能不同，在選取功能方法中，商務用 Skype使用者可以與 TeamsOnly 中的使用者通訊。 使用者與商務用 Skype之間的Teams[稱為互通性或](teams-and-skypeforbusiness-coexistence-and-interoperability.md#interoperability)「交交互操作」。 在 商務用 Skype 中與另一個使用者之間的聊天和通話，可以一對一進行互Teams。 此外，受邀使用者隨時都可以加入會議商務用 Skype或Teams會議，不過，他們必須使用對應到會議類型的用戶端。 詳細資訊，請參閱 [會議](teams-and-skypeforbusiness-coexistence-and-interoperability.md#meetings)。

對於使用選取功能轉換方法的使用者，無論其他使用者使用哪一個用戶端，使用者的目前狀態都是一致的。 如果使用者位於其中一個商務用 Skype模式中，則所有其他使用者會根據該使用者在 商務用 Skype 中的活動來查看目前商務用 Skype。 同樣地，如果使用者是在 TeamsOnly 模式中，則所有其他使用者會根據該使用者在 Teams 中的活動，看到目前狀態。 詳細資料請參閱目前 [狀態](teams-and-skypeforbusiness-coexistence-and-interoperability.md#presence)。

對於尚未開始使用此Teams，系統管理員應該將租使用者範圍模式從群島變更為 SfbWithTeamsCollab。  (對於已經有一些使用Teams的組織，系統管理員應「」」Teams使用者」，以確保這項變更不適用於他們。 詳細資料請參閱已在群島模式中使用Teams[的](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)組織的選取功能)  

來賓使用者體驗會遵循指派給租使用者的共存模式。 如果您在租使用者層級商務用 Skype模式，來賓無法聊天、通話或顯示其目前狀態。 若要深入了解，請閱讀 [Teams 中的來賓存取](guest-access.md) (英文)。

當模式從群島變更為 SfbWithTeamsCollab 時，從未使用 Teams 的使用者不會看到其使用商務用 Skype。 不過，如果使用者開始使用該Teams，則只會公開功能，Teams &通道和檔案。 Teams 中無法進行聊天、通話和會議排程，因為系統管理員 () 指定 商務用 Skype 做為這些函數所需的用戶端。

> [!NOTE]
> 當使用者 A 從群島變更為其中一個 商務用 Skype 模式時，與使用者 A 通訊的其他使用者的 Teams 用戶端必須知道使用者 A 的模式已變更，以便將通訊路由至使用者 A 的適當用戶端。對於已經與使用者 A 建立原生 Teams 到 Teams 聊天的任何使用者，這些其他使用者的 Teams 用戶端最多可能需要 36 小時，才能知道模式會從群島變更為任何 商務用 Skype 模式。 相反地，其他用戶端在 2 小時內發現現有使用者對 TeamsOnly 模式的變更。<br>
> 當系統管理員準備好時，他們可以將使用者的聊天、通話和會議排程Teams將使用者的模式更新至 TeamsOnly，以一次完成所有作業。

或者，系統管理員可以先將會議排程Teams，而使用 SfBWithTeamsCollabAndMeetings 模式將聊天和通話功能留在 商務用 Skype 中。 此模式可讓組織轉換至 Teams 會議 ，如果使用者尚未準備好移至 TeamsOnly 模式 (例如，如果您尚未準備好移轉現有的 PSTN 功能) 。 此轉場案例稱為會議 [第一個](meetings-first.md)。


|Teams體驗  |在 SfBWithTeamsCollab 模式中 |在 SfBWithTeamsCollabAndMeetings 模式中 |在 TeamsOnly 模式中  |
|---------|---------|---------|---------|
|您組織中收到使用者的傳入聊天和 VOIP 通話：     | 商務用 Skype        | 商務用 Skype       | Teams        |
|接收的 PSTN 通話：     | 商務用 Skype        |商務用 Skype         | Teams        |
|目前狀態     | 商務用 Skype        |商務用 Skype         | Teams        |
|會議排程     | 商務用 Skype         | Teams        | Teams        |


下表摘要說明使用模式做為商務用 Skype TeamsOnly 模式的轉換步驟的優缺點。

| 專業版     |       缺點 |
| :------------------ | :---------------- |
| 使用者可預測的路由。 所有通話和聊天都位於 商務用 Skype 或 Teams (，但無法同時) 管理員選擇。|交互操作交談不支援豐富的文字、檔案共用和螢幕共用。 您可以利用立即開會功能來啟動會議。 |
|可能會減少使用者混淆，因為只有一個用戶端提供某一個功能。 | 在將使用者升級至 TeamsOnly 之前，他們無法存取Teams聊天和通話等商務用 Skype中執行的一般活動。 也就是說，沒有並排功能。|
|系統管理員可控制一組可供使用者使用的功能，同時從 商務用 Skype 轉換Teams。 此控制項包含逐步引入Teams功能的功能。 | |
| 允許組織使用Teams，即使尚未準備好完全移至 TeamsOnly 模式。||
|無論使用者使用哪一個用戶端，其他人所查看的給定使用者目前狀態都是一樣的。||

## <a name="summary-of-upgrade-methods"></a>升級方法摘要
下表摘要列出升級方法：


|使用群島模式 (功能重迭)   |選取的功能 (使用商務用 Skype模式)   |
|---------|---------|
|升級至 TeamsOnly 之前，使用者必須同時執行這兩個用戶端，因為傳入的聊天和通話可能會進入任一用戶端。     | 根據收件者的模式，聊天和通話只會在一個用戶端中登陸。 未升級的使用者可能會同時執行這兩個用戶端，但是 (通話和聊天功能沒有重迭Teams) 。 系統管理員也可以控制使用者是否要在 Teams 或 商務用 Skype。         |
|可讓系統管理員在 商務用 Skype 和 Teams 中向使用者介紹重迭功能 (聊天、會議、VOIP 通話)  (，以在 Teams 中提供並排功能) ，以及新功能 (Teams 和通道) 。     | 允許系統管理員將 Teams 的選取功能 (Teams頻道) ，而不提供存在於 商務用 Skype 中的相同功能。        |
|當兩商務用 Skype Teams群島模式時，Teams和兩者之間的交互操作不存在。 一旦部分使用者升級至 TeamsOnly 交互操作交談時，這些使用者與仍在群島模式中的其他使用者之間可能會發生。 不過，群島使用者可以選擇使用Teams，並避免交互操作交談。      |使用者與使用者之間的通訊商務用 Skype互Teams交互操作。         |

> [!NOTE]
> 如果您無法遵循支援的方法將 商務用 Skype Server 使用者移轉至 Teams，可以在 Active Directory 中移除 商務用 Skype Server 和所有相關的使用者屬性，將使用者轉換為 Teams。 一旦使用者 Azure Active Directory 屬性被清除掉 商務用 Skype Server 屬性，DNS 記錄已重新指向 Microsoft 365 或 Office 365，則有可能授權 Microsoft 365 或 Office 365 中的使用者，然後將他們升級至 Teams。 

> [!IMPORTANT]
> 完全移移之後，連絡人資料和會議資料將不會從內部部署環境移Microsoft Teams。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>決策點</td><td><ul> 哪一個升級歷程適合貴組織的商業需求？<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>後續步驟</td><td><ul> 識別您目前的部署模型、使用案例案例，以及貴組織的重要考慮，有助於Teams最適合貴組織的工作。<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>決策點</td><td><ul> 貴組織適用哪一種升級案例？<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul> 根據訊息、會議和通話業務需求，決定貴組織的升級歷程時程表。<br><br> 決定完成升級旅程所需的額外工作。<br><br></ul></td></tr>
</table>

選擇貴組織的最佳升級歷程之後，請執行升級至[Teams。](./upgrade-to-teams.md)

## <a name="related-links"></a>相關連結

[適用于與應用程式一起使用Teams的移商務用 Skype](migration-interop-guidance-for-teams-with-skype.md) 

[設定商務用 Skype Server或Microsoft 365之間的Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps&preserve-view=true)

[使用會議移 (MMS) ](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
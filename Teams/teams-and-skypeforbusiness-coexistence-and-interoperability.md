---
title: 瞭解 Microsoft Teams 和商務用 Skype共存與互通性
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 商務用 Skype和 Microsoft Teams 共存選項的詳細資料，以及商務用 Skype和 Teams 之間的互通性。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f91297a0b2fa5178195b10b61817cc11a30acfbc
ms.sourcegitcommit: 303579b3ecd4e0af43710d4b078610f63e9d0eca
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2022
ms.locfileid: "68853361"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>瞭解 Microsoft Teams 和商務用 Skype共存與互通性

![升級旅程圖，強調 Project 定義階段。](media/upgrade-banner-project-definition.png "升級旅程的階段，強調專案定義階段")

本文是升級旅程中 Project 定義階段的一部分。 在建立贊助贊助專案和專案小組，並定義專案的範圍、目標和計畫之後完成。 繼續進行之前，請確認您已完成下列活動：

- [呼叫專案專案專案關係人](upgrade-enlist-stakeholders.md)
- [定義您的專案範圍](./upgrade-define-project-scope.md)

如果您的組織目前使用 商務用 Skype，而您正開始與商務用 Skype一起使用 Teams，或者您正開始升級至 Teams，請務必瞭解兩個應用程式如何共存、何時和如何交互操作，以及如何管理使用者從 商務用 Skype升級到 Teams 的升級。

> [!Tip]
> 請觀看下列會話以瞭解 [共存和互通性](https://aka.ms/teams-upgrade-coexistence-interop)。
>
> 此外，您可以加入我們參加即時的互動式研討會，我們會在此分享指導方針、最佳做法，以及專為開始升級規劃與實作所設計的資源。
>
> 先加入 [[規劃升級](./upgrade-workshops-landing-page.yml) 會話] 以開始使用。

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Teams 共存和商務用 Skype概觀

自從 商務用 Skype Online 淘汰之後，純線上組織中的所有使用者 (也就是，沒有內部部署的組織 商務用 Skype) 擁有 TeamsOnly 的共同存在模式。 TeamsOnly 模式可確保使用者擁有 Teams 的完整功能。 不過，具有內部部署商務用 Skype Server的組織可能會有仍在內部部署的使用者;這些使用者不能是 TeamsOnly。 擁有內部部署商務用 Skype Server帳戶的使用者可能擁有 *TeamsOnly 以外的* 任何共存模式。 下列各節說明在您決定將內部部署商務用 Skype使用者升級到 TeamsOnly 之前可用的共存模式，以及每個模式所提供的功能。 此外，各節說明商務用 Skype用戶端的使用者和 Teams 用戶端上的使用者之間所發生的交互操作 (互) ，以及所選共存模式會如何影響互連。

Teams 提供共同作業功能、聊天、通話和會議功能。  商務用 Skype中也提供聊天、通話和會議功能。 根據您在提供 Teams 時選擇的設定而定，這些功能可能會與商務用 Skype為特定使用者提供的功能重迭。 內部部署使用者的預設共存模式是 Islands。 群島模式可讓使用者同時執行 Teams 與商務用 Skype同時使用兩個用戶端提供的類似功能;也就是功能重迭。 不過，可以為使用者指派其他共存模式，以防止此功能與使用者重迭，在這種情況下，Teams 和 商務用 Skype 之間便可使用互通性。 例如，如果您擁有大量商務用 Skype Server內部部署資產且部署企業語音複雜，但想讓使用者儘快享受新式會議，建議您評估搭配 Teams 共同作業和會議模式使用商務用 Skype，也稱為「[會議優先」](meetings-first.md)。

建議您檢閱下列共存模式，以協助判斷適合貴組織的路徑。

> [!Important]
> 商務用 Skype Online 淘汰之後，共存模式仍繼續存在，但是在線上的使用者只能有 TeamsOnly 模式。 TeamsOnly 以外的任何模式都無法再指派給線上的使用者。  如同 商務用 Skype Online 淘汰之前的情況，內部部署的使用者可以指派 *TeamsOnly 以外的* 任何模式。


### <a name="teams-only"></a>僅限 Teams

**只有 Teams** 是唯一適用于純線上使用者的模式。 過去 **只有 Teams** 使用者 (，有時稱為 *升級* 的使用者) 可以存取 Teams 中的所有功能，而且可以繼續與任何其他使用者通訊， (無論是在同一個或外部組織中，) 如果商務用 Skype使用者 **不在群島** 模式) ，那些仍然使用商務用 Skype (的使用者。 **Teams 僅** 限使用者在 Teams 中接收來電聊天和通話，並且在 Teams 中排程會議。 他們無法在商務用 Skype中啟動聊天、通話或排程會議。 

**Teams 只有** 使用者可以保留商務用 Skype用戶端，以加入他們在未來 (中既有的或可能收到的任何商務用 Skype會議，也就是來自外部人員，或可能來自內部部署商務用 Skype Server自己組織) 的使用者。 *不過，在 Microsoft 移除特定 Teams 使用者商務用 Skype線上基礎結構之後，僅限 Teams 使用者只能匿名加入商務用 Skype會議。* 2022 年 6 月 30 日之後，新建立的 TeamsOnly 使用者將不再與 商務用 Skype Online 基礎結構一起布建。 如果這些使用者受邀參加商務用 Skype會議，就必須匿名加入。 2022 年 10 月之後，使用者從內部部署移至雲端 (，使用者即會變成 TeamsOnly) 將不再與 商務用 Skype Online 基礎結構一起布建。  如果這些使用者受邀參加商務用 Skype會議，他們也必須匿名加入。

當貴組織準備好讓部分或所有使用者使用 Teams 做為他們唯一的通訊和共同作業工具時，請將這些使用者升級至 **[僅限 Teams]** 模式。 如果您是從 **群島** 模式升級，我們建議您在開始升級程式之前，先將整個組織的 Teams 採用設定為飽和度。 由於 **群島** 模式無法提供互通性，這種採用方式可避免通訊中斷的情況。

在 **[僅限 Teams** ] 模式中，Teams 是 SIP/Tel 通訊協定的預設應用程式。 Teams 會處理使用者連絡人卡片中用於通話或聊天的連結。

如需移至 **[僅限 Teams** ] 模式的額外考慮，請參閱 [Teams 只有模式考慮](teams-only-mode-considerations.md)。

![Teams 確認訊息的螢幕擷取畫面。](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "商務用 Skype使用者升級為僅限 Teams 使用者之後，用戶端會以特殊模式執行")


### <a name="islands-mode"></a>群島模式

在 **群島** 模式中，使用者可以與商務用 Skype一起執行 Teams，做為兩種提供類似與重迭功能的個別解決方案。 這些功能包括目前狀態、聊天、通話和會議。 Teams 使用者也可以利用新的共同作業功能，例如團隊和頻道、存取 Microsoft 365 中的檔案和應用程式。

在這個共存模式中，每一個用戶端應用程式都會以個別的島嶼運作。 商務用 Skype與商務用 Skype交談，且 Teams 會與 Teams 交談。 使用者預期會一直同時執行這兩個用戶端，而且可以在開始通訊的用戶端中以原生方式進行通訊。 因此，在 **群島** 模式中不需要互通性。

為了避免造成混淆或回歸商務用 Skype體驗，商務用 Skype處理下列不在 Teams **Islands** 模式中處理的整合：

- 外部 (同盟) 通訊。
- PSTN 語音服務與語音應用程式、Office 整合。
- USB 裝置的 HID 控制項。
- 其他幾個整合。

Microsoft Teams 電話 **群島模式的** Teams 不支援系統。 

> [!Important]
>  - 在 **群島** 模式中，所有來自同盟使用者 (組織外部人員) 的訊息和通話都會傳送給商務用 Skype。 升級至 **[僅限 Teams** ] 模式之後，組織外的所有訊息和通話都會傳送到 Teams。
>  - 您可能會想要要求群島使用者一律在 Teams 中排程會議，方法是將 TeamsMeetingPolicy 實例指派給 PreferredMeetingProviderForIslandsMode=Teams。 這可確保所有使用者都使用 Teams 排程會議，Teams 支援組織中任何使用者的已驗證登入和會議加入，無論使用者是 TeamsOnly 還是仍在使用 商務用 Skype Server。 相反地，自 2022 年 10 月起，Microsoft 淘汰混合式組織的舊版 商務用 Skype Online 基礎結構之後，TeamsOnly 使用者只能匿名加入商務用 Skype會議。


### <a name="skype-for-business-only"></a>僅商務用 Skype

在此共存模式中，使用者會維持在聊天、會議和通話功能商務用 Skype，而非 Teams，而且不會將 Teams 用於團隊和頻道。 此模式目前已推出;不過，在目前的實作中，使用者的團隊和頻道並不會自動關閉。 您可以使用應用程式設定原則來隱藏團隊和檔案，藉此達到此目的。

您可以在開始 Teams 的受管理部署之前使用此模式，以防止使用者在建置整備之前開始使用 Teams。 只要使用者獲得 Teams 授權，此模式也能為商務用 Skype使用者啟用已驗證的 Teams 會議參與。

### <a name="skype-for-business-with-teams-collaboration"></a>使用 Teams 共同作業商務用 Skype

使用此模式在您的環境仲介紹 Teams，同時繼續使用您在 商務用 Skype 中的現有投資。 聊天、通話和會議功能的商務用 Skype維持不變。 新增 Teams 共同作業功能：

- 團隊和頻道。
- 存取 Microsoft 365 或 Office 365 中的檔案。
- 應用。 Teams 通訊功能：私人聊天、通話和排程會議。

在這種模式中，Teams 私人聊天、通話和排程會議預設為關閉。

從內部部署商務用 Skype Server開始的組織，如果想要在移轉期間為其通訊提供互通性與可預測性，則會將此模式取代為 **Islands** 模式。 此模式也提供可預測的時程表來升級至 Teams (，而非在 **群島模式)** 中依賴採用飽和度。

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>商務用 Skype Teams 共同作業和會議，也稱為會議第一

在這個模式中，私人聊天和通話功能會保留在商務用 Skype，而 Teams 則用於排程和召開會議，以及使用頻道式交談進行共同作業。  此共存模式可協助加快貴組織中 Teams 會議和共同作業功能的可用性，並讓您的使用者充分利用優質的 Teams 會議體驗：

- 品質很好。
- 轉譯和翻譯。
- 背景模糊。
- 跨所有平臺的卓越使用者體驗，包括行動裝置和瀏覽器。

Teams 和 商務用 Skype受益于一系列「更好的共聚」功能，例如目前狀態對帳、自動保留/取消保留，以及跨兩個應用程式的 HID 裝置支援。 如有需要，您可以使用 Teams 應用程式設定原則來隱藏團隊和頻道。

這種共存模式對於擁有商務用 Skype內部部署企業語音的組織特別有用。 這些組織可能需要一些時間來升級至 Teams，並希望儘快從優質的 Teams 會議中獲益。

> [!NOTE]
> 自 2022 年 10 月起，建議所有先前獲指派 [**僅商務用 Skype**] 或 [僅 **商務用 Skype Teams 共同** 作業模式] 的內部部署使用者使用此模式。 除了使用者排程的新會議是 Teams 會議，而不是商務用 Skype會議之外，此模式提供的功能與其他兩者相同。 這可確保使用者將會議排程為 Teams 會議，支援組織中任何使用者的已驗證登入和會議加入，無論使用者是 TeamsOnly 還是仍在使用 商務用 Skype Server。  相反地，當 Microsoft 淘汰舊版 商務用 Skype Online 基礎結構時，TeamsOnly 使用者在加入商務用 Skype會議時將無法再進行驗證，不過他們仍然可以匿名加入。 如需詳細資料，請參閱 [淘汰後會發生什麼事](skype-for-business-online-retirement.md#what-to-expect-post-retirement)。

> [!TIP]
> 若要在商務用 Skype仍在使用中時，根據您想要在 Teams 中啟用的功能來協助識別建議的升級模式，請利用[Skype 升級精靈](https://aka.ms/SkypeToTeamsWizard)。

如需共存模式、必要條件和管理的詳細資訊，請參閱[使用 Teams 與 商務用 Skype 的組織移轉和互通性指導方針](./migration-interop-guidance-for-teams-with-skype.md)和[設定您的共存與升級設定](./setting-your-coexistence-and-upgrade-settings.md)。

|決策點圖示 |圖示定義 |描述 |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|決策點|<ul><li>哪些共存模式 (最符合貴組織和使用者的需求) ？</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|後續步驟|<ul><li>選擇升級旅程的最佳方式。</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Teams 和 商務用 Skype 的互通性

互通性是讓同一組織中的 Teams 和商務用 Skype使用者跨 Teams 和商務用 Skype通訊的功能。

互通性是由共存模式 (也稱為接收器的升級模式) 所規範。 接收器處於 **群島** 模式時沒有互通性。

> [!Note]
> 在 **群島** 以外的任何共存模式中部署時，Teams 和 商務用 Skype 可以 [相交互操作](#interoperability-of-teams-and-skype-for-business)、讓使用者彼此聊天和通話，並確保在升級至 Teams 的過程中，貴組織的通訊保持流暢。 共存模式規範互通性。 接收器的共存模式會決定是否可使用互通性。 例如，如果接收器處於只有一個用戶端才能使用聊天的模式 (例如 Teams) ，在這種情況下，如果初始器使用另一個用戶端 (，商務用 Skype) 啟動聊天，通常就會提供聊天互通性。 另一方面，如果接收器處於兩個用戶端都可使用聊天的模式， (群島模式) ，則無法在聊天中使用互通性。 收件者會在初始者開始聊天的同一個用戶端收到訊息。 因此，在 **群島** 模式中適當的通訊需要 Teams 採用飽和度;也就是說，所有使用者都會主動使用及監控這兩個用戶端。

> [!Note]
> **若要擁有最新的共存體驗，用戶端版本必須是使用者 Office 部署通道中最新的可用用戶端。**

#### <a name="native-interop-and-interop-escalation"></a>原生 interop 和 interop 升級

有兩種類型的內建體驗：原生和內建升級。

- 使用者目前使用的用戶端中會發生 _原生互通_ 體驗。 其中一位使用者會在商務用 Skype用戶端，另一位位於 Teams 中。 原生互通體驗不會帶他們到其他用戶端進行通訊。 使用者將能夠在目前使用的用戶端中進行交談。 原生互通的體驗是一對一聊天和通話。
- _交互升級_ 體驗表示用戶端在協助使用者執行進階動作 (，例如共用桌面) 時，有助於建立一個使用者可以加入的會議，以繼續在該會議中繼續體驗。 會議是在動作初始者的平臺上建立。 不在該平臺的使用者或使用者會收到會議加入連結。 當他們按一下這個連結時，會以相容的用戶端 (瀏覽器、Web 應用程式或完整用戶端加入會議，視設定) 而定。 從商務用 Skype內升級需要最新的用戶端。 現在可以使用 Teams 的 Interop 升級。 這兩者在租使用者中的互通性體驗以及同盟的跨租使用者通訊中都受到支援。

#### <a name="native-interop-experiences"></a>原生互通體驗

根據指派給 (使用者的共存模式，如) 所述，下列原生互通體驗可供使用：

商務用 Skype使用者可以與 Teams 使用者進行一對一交談，反之亦然。 聊天間需要透過屬於 Teams 雲端服務一部分的交互閘道 (，因此僅存在線上) 。 聊天間是純文字：不支援 RTF 文字和圖釋。 Teams 和 商務用 Skype 中的使用者會收到交談為交談間交談的通知。

<!--![Screen shot of Interop chat experience from Teams.](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

商務用 Skype使用者可以對 Teams 使用者進行一對一語音和視訊通話，而 Teams 使用者也可以執行相同的動作。

<!--![Screen shot of Interop calling experience from Teams.](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> 在內部部署和 Teams 使用者混合的組織中，與內部部署使用者進行交互體驗，要求內部部署環境與 Teams 處於混合模式。 如需詳細資料，[請設定商務用 Skype Server與 Microsoft 365 或 Office 365 之間的混合式聯](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)機。

這些互動式體驗可供指派下列其中一種共存模式的使用者使用：**使用 Teams** 共同作業商務用 Skype、**使用 Teams 共同作業和會議商務用 Skype**、**僅商務用 Skype** 或 **僅限 Teams**。 在 **群島** 模式中，使用者沒有互通性。

#### <a name="native-interop-experience-limitations"></a>原生互通體驗限制

由於通訊協定與技術的差異，因此無法原生支援所有功能。 具體來說，下列功能無法使用：

- Teams 或 商務用 Skype 不支援 Markdown、RTF 和完整圖釋集。 不支援 Teams 聊天中撰寫方塊的其他原生功能。
- 在 Teams 和 商務用 Skype 之間 (桌面或應用程式共用) 的螢幕畫面分享不受原生支援。 不過，這會透過交互升級來提供支援。
- 在 Teams 中 (多方交談) 的群組聊天只能包含使用 Teams 的參與者。
- 商務用 Skype中)  (群組聊天中的多方 IM 交談只能包含使用商務用 Skype的參與者。 不過，商務用 Skype提供向多方升級的訊息。
- 將持續對等語音或視訊通話升級為涉及 Teams 和商務用 Skype使用者的多方通話。
- 不支援從 Teams 到 商務用 Skype 的兩方聊天或群組聊天中的檔案附件檔案傳輸，反之亦然。
- 商務用 Skype常設聊天室沒有互通性。

針對常設聊天) 以外的所有限制 (，其中一個可能的因應措施是讓一個使用者召開會議並邀請另一個使用者加入會議。

此因應措施是交互升級的基礎。 特別是，螢幕畫面分享和升級到多方是無法原生實現的，但是會透過內部升級來支援。

#### <a name="interop-escalation-experiences"></a>Interop 上傳體驗

Interop 升級包含以受管理的升級到會議來補充原生 Interop 功能。 無論任何人擁有哪一個客戶，會議都能提供豐富的體驗。

當 Teams 使用者觸發內部升級時，即會建立 Teams 會議。 當商務用 Skype使用者觸發該會議時，會建立商務用 Skype會議。 在這兩種情況下，建立的會議都是 [ **立即開會** ] 會議，不會反映在使用者的行事曆上。

另一方會透過聊天間收到會議加入連結，並按一下該連結來加入。 如果商務用 Skype使用者有 Teams 帳戶，並受到 Teams 使用者的邀請，他們將會加入已驗證的會議。 否則，他們會以匿名參與者的身分加入。 Teams 使用者幾乎一律擁有商務用 Skype帳戶和商務用 Skype用戶端，他們能以已驗證的參與者身分加入商務用 Skype會議，但也可能以匿名參與者的身分加入，例如使用 Skype 會議 應用程式。

當對方加入會議後，他們就可以進行會議中支援的任何活動，例如桌面或內容共用、檔案共用或傳輸、新增其他參與者等等。

#### <a name="interop-escalation-from-skype-for-business"></a>從商務用 Skype內升級

在每月 C2R 的 2019 年 7 月組建中，已更新來自商務用 Skype的 Interop 和交集升級。 之前商務用 Skype對遠端派對使用 Teams 沒有事先通知。 它只會從建立會話後收到的訊號進行猜測。

當訊號指出回應來自 (或透過) 的內部閘道時，它會顯示黃色的商務列 (橫幅) 指出另一方並未使用商務用 Skype。 隨著我們服務的演進，導致誤判，商務用 Skype使用者在連線至雲端語音信箱服務或其他雲端語音服務時，會看到商務列，而不是實際的 **Teams 僅** 使用者。

為防止誤判，目前狀態服務現在會通知商務用 Skype用戶端，當另一方是 **Teams 僅** 實際使用者時。 這可讓商務用 Skype建立一個交談，而交談視窗則是特定的交互。

![Teams 訊息的螢幕擷取畫面，以建立與商務用 Skype使用者的交談。](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

例如，如果商務用 Skype使用者想要共用桌面，系統會通知我們將開始會議，並引導您完成這些步驟。

![Teams 訊息開始與 Teams 使用者開會的螢幕擷取畫面。](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

同時，Teams 使用者會收到含有會議連結的傳入聊天訊息，並引導他們加入會議。

這種升級至商務用 Skype會議的功能適用于租使用者內部會議和跨租使用者同盟通話和聊天。 此設定預設為開啟，系統管理員不需要布建任何設定。

#### <a name="interop-escalation-from-teams"></a>從 Teams 間升級

當 Teams 使用者在與商務用 Skype使用者的租使用者間討論串中選取桌面共用按鈕，或在跨租使用者的 interop 同盟對話中選取桌面共用按鈕時，現在可以使用從 Teams 內升級至 Teams 會議的功能。 1 對 1 聊天交談或 1 對 1 通話支援互連升級。

Windows 版 Teams 桌面用戶端、Mac 版 Teams 桌面用戶端，以及支援內容共用的瀏覽器上的 Teams Web 用戶端，以及與任何商務用 Skype用戶端版本進行通訊時，都支援此功能。

在互通性對話和同盟互通性執行緒中，Teams 使用者現在有可開始內容共用的控制項 (按鈕) 。 當 Teams 使用者選取該按鈕時，系統會提供一個額外的功能表，通知他們共用內容時，必須啟動 Teams 會議。

如果使用者正在通話中，功能表會警告他們 Teams 和 商務用 Skype 之間的目前通話將會在加入 Teams 會議時終止。 如果他們選擇的話，可以在接受之前警告商務用 Skype使用者。

![Teams 訊息與商務用 Skype使用者共用會議的螢幕擷取畫面。](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

接受邀請時，他們會加入 Teams 會議;他們必須從會議中的共用匣開始共用。

同時，商務用 Skype使用者會收到含有會議連結的傳入聊天訊息，並引導他們加入會議。

Teams 會議的升級適用于租使用者內部部署和跨租使用者同盟通話和聊天。 此設定預設為開啟，系統管理員不需要布建任何設定。 不過，如果系統管理員設 ``-AllowPrivateMeetNow`` ``CsTeamsMeetingPolicy`` ``$false`` 為 ， 使用者會關閉此功能。

檢閱本文之後，請參閱[選擇您的升級旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)、[移轉與互通性指引](./migration-interop-guidance-for-teams-with-skype.md)、[與商務用 Skype共存](coexistence-chat-calls-presence.md)，以及[設定共存與升級設定](./setting-your-coexistence-and-upgrade-settings.md)以取得實作詳細資料。 我們也建議使用下列影片： [影片：管理 SfB 與 Teams 之間的共存和互通性](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Teams 與商務用 Skype共存的技術詳細資料

下列各節摘要列出在同一個組織中執行 Teams 和商務用 Skype用戶端時，無論使用何種模式和升級方法：

- [會議](#meetings)
- [互 操作 性](#interoperability)
- [Interop 與原生交談對話](#interop-versus-native-conversation-threads)
- [目前狀態](#presence)
- [同盟](#federation)
- [連絡人](#contacts)

### <a name="meetings"></a>會議

無論他們的模式為何，使用者隨時都可以加入任何受邀參加的會議類型，無論是商務用 Skype或 Teams。  不過，使用者必須以符合會議類型的對應用戶端加入會議：

- 如果會議是 Teams 會議，則所有參與者 (是否為 TeamsOnly、Islands 或商務用 Skype使用者，) 使用 Teams 用戶端加入會議。 如果未安裝 Teams，使用者在嘗試加入會議時會被導向至網路。

- 如果會議是商務用 Skype會議，則所有參與者 (是 TeamsOnly、Islands 或商務用 Skype使用者，) 使用商務用 Skype用戶端加入會議。 如果尚未安裝商務用 Skype用戶端，系統會將使用者導向至網路，透過 Skype 會議 應用程式加入。 

  在某些情況下，TeamsOnly 模式中的參與者只能以匿名使用者的身分，使用 商務用 Skype Web 應用程式 或 Skype 會議應用程式加入商務用 Skype會議。 在 TeamsOnly 模式中，此案例最終適用于所有使用者。 如需詳細資訊，請[參閱線上商務用 Skype淘汰](skype-for-business-online-retirement.md#what-to-expect-post-retirement)。

組織會議時，排程的會議類型是根據召集人的模式，如下表所示：

| 召集人模式    |      行為 |
| :------------------ | :---------------- |
| TeamsOnly、SfbWithTeamsCollabAndMeetings | 在 Teams 中排程的所有會議。 商務用 Skype無法在 Outlook 中使用增益集。 |
| SfbWithTeamsCollab， SfbOnly | 在 商務用 Skype 中排程的所有會議。 Teams 增益集無法在 Outlook 中使用。 考慮改用 SfbWithTeamsCollabAndMeetings，讓所有使用者無論是內部部署或 TeamsOnly 都能使用 Teams 進行會議。|
| 離島 | 根據預設，會議可在 商務用 Skype 或 Teams 中排程。 這兩個增益集均可在 Outlook 中使用。 不過，您可以選擇性地要求群島中的使用者一律在 Teams 中排程會議，方法是將 TeamsMeetingPolicy 的實例指派給 PreferredMeetingProviderForIslandsMode=Teams。|

### <a name="interoperability"></a>互 操作 性

如上述 Teams[和 商務用 Skype 互通性](#interoperability-of-teams-and-skype-for-business)中所述，Teams 在某些情況下支援與商務用 Skype搭配使用。 Interop 通訊是指商務用 Skype使用者和 Teams 使用者之間的聊天或通話。 只有兩個使用者之間才能進行 Interop 通訊;不支援多方聊天/通話或新增其他使用者。

當下列每一項皆為 True 時，會建立兩個使用者之間的聊天或通話：

- 一個使用者正在使用 Teams，而另一個使用者正在使用 商務用 Skype。

- 初始通訊收件者的模式並非群島 (否則如果兩個使用者都在同一個組織中，通訊會連線到相同的用戶端) 。 在同盟案例中，傳送的使用者使用 Teams，且收件者不在 TeamsOnly 模式中。

- Teams 使用者並沒有內部部署商務用 Skype帳戶。

在內部溝通中，聊天僅提供純文字。 此外，無法 *在聊天間進行* 檔案共用和螢幕畫面共用。 不過，在交談間的使用者可以透過在聊天間建立隨選會議，輕鬆達成檔案和/或螢幕共用，如下所述：

- 如果 Teams 使用者嘗試共用螢幕畫面，系統會自動建立隨選 Teams 會議，並將該會議的邀請連結傳送給商務用 Skype使用者的用戶端。 按一下連結後，商務用 Skype使用者會開啟 Teams 並加入會議。 這兩個使用者現在都已在 Teams 會議中，並可視需要共用。

- 如果商務用 Skype使用者使用 2018 年或更新版本的用戶端，並嘗試共用任何內容，系統會自動建立隨選商務用 Skype會議，並傳送該會議的邀請連結至 Teams 使用者的用戶端。 按一下連結後，Teams 使用者會嘗試加入商務用 Skype會議。 如果 Teams 使用者已安裝商務用 Skype用戶端，它會開啟，如果尚未登入) ，系統會提示使用者登入 (。  如果 Teams 使用者未安裝商務用 Skype用戶端，系統會提示使用者使用 Web 版本。 一旦兩個使用者登入後，就會加入商務用 Skype會議，並可視需要共用。

### <a name="interop-versus-native-conversation-threads"></a>Interop 與原生交談對話

由於 Interop 通訊不支援原生 Teams 交談的所有功能，Teams 用戶端會針對 Teams 對 Teams 和 Teams 對商務用 Skype通訊維護個別的交談對話。 這些交談在使用者介面中會以不同的方式呈現：Interop 對話可以與一般原生 Teams 對話區隔如下：

- 缺少 RTF 文字、檔案/螢幕共用、無法新增使用者的控制項。
- 對目標使用者圖示進行修改，其中顯示商務用 Skype的 「S」。

這些差異會顯示在下列螢幕擷取畫面中：

使用使用者 G3 測試進行原生 Teams 對 Teams 交談

![顯示原生 Teams 對 Teams 交談的圖表。](media/teams-upgrade-native-thread.png)

同一個使用者 G3 測試的交談

![顯示 Teams 對 Teams 交談的圖表。](media/teams-upgrade-interop-thread.png)

建立交談對話後，其類型永遠不會變更。 建立之後，Teams 中的交互對話一律會路由至目標使用者的商務用 Skype用戶端。 原生執行緒一律會路由至目標使用者的 Teams 用戶端。  如果收件者使用者的模式變更，該使用者的現有 Teams 對話將無法再運作，且該聊天中會顯示附注與連結，以啟動新的原生交談，如下列螢幕擷取畫面所示。

![顯示與已升級商務用 Skype使用者聊天的圖表。](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>目前狀態

指定使用者的目前狀態是根據使用者透過用戶端在服務中的活動。 系統會隨即發佈目前狀態，讓其他使用者查看。  商務用 Skype和 Teams 是具有個別用戶端的個別服務，因此每個服務都有自己的使用者目前狀態。   Teams 和 商務用 Skype Online 中的目前狀態服務之間也會同步處理。  這可讓一個服務在需要時，從另一個服務發佈該使用者的目前狀態。

目前狀態發佈行為是以使用者的模式為基礎。 有三種基本情況：

- 如果使用者處於 TeamsOnly 模式，則無論使用者使用哪個用戶端，所有其他使用者都會看到該使用者的 Teams 目前狀態。

- 如果使用者處於任何商務用 Skype模式，所有其他使用者都會看到該使用者商務用 Skype目前狀態，無論他們使用哪個用戶端。

- 如果使用者處於群島模式，則在 商務用 Skype 和 Teams 中發佈的目前狀態是獨立的，因此向同一組織內的使用者顯示的目前狀態將取決於另一個使用者的用戶端。 同盟組織中的使用者會根據其商務用 Skype活動看到該使用者的目前狀態，因為前往群島模式的同盟流量已登入商務用 Skype。

例如，假設使用者 A 是在群島模式。 如果 [使用者 A] 在 Teams 中為使用中，但並未登入商務用 Skype，其他使用者會從他們的 Teams 用戶端看到 User A 為作用中，但在商務用 Skype用戶端中，他們會將 User A 視為離線。 這是根據設計，因為如果沒有執行用戶端，就無法連絡使用者 A。


### <a name="federation"></a>同盟

Teams 與其他使用 商務用 Skype 使用者的同盟要求 Teams 使用者在 商務用 Skype 中連線上網。 TeamsUpgradePolicy 會管理傳入同盟聊天和通話的路由。 同盟路由行為與相同租使用者案例相同，但在群島模式中除外。 收件者處於群島模式時：

- 如果收件者是同盟租使用者，則從 Teams 啟動的聊天和通話會進入商務用 Skype。
- 如果收件者在同一個租使用者中，從 Teams 啟動的聊天和通話會進入 Teams。
- 從商務用 Skype啟動的聊天和通話一律會進入商務用 Skype。

同盟聊天可以是原生對話或對話間串。 請參閱 [Interop 與原生交談對話](#interop-versus-native-conversation-threads)。

- 如果接收器和寄件者都處於 TeamsOnly 升級模式，則交談將會是原生聊天體驗，其中包含所有豐富的訊息和通話功能。 若要深入瞭解，請閱讀 [Teams 中外部 (同盟) 使用者的原生聊天體驗](native-chat-for-external-users.md)。

- 如果有任一交談參與者未處於 TeamsOnly 升級模式，則交談仍會以僅文字訊息提供交互體驗。 使用者介面會以類似相同租使用者內部討論串的方式公開同盟聊天，但有一則附注指出該使用者是外部使用者。

如需詳細資料，請參閱 [管理 Microsoft Teams 中的外部存取](manage-external-access.md) 和 [Teams 中外部 (同盟) 使用者的原生聊天體驗](native-chat-for-external-users.md)。

### <a name="contacts"></a>連絡人

Teams 和商務用 Skype有個別的連絡人清單。 這表示在一個系統中新增、移除和修改的連絡人未同步處理到另一個系統。 不過，當發生兩個特定事件之一時，系統會自動將來自商務用 Skype的連絡人複製到 Teams：

- 對於任何商務用 Skype Online 使用者，第一次登入 Teams 時，商務用 Skype的連絡人都會複製到 Teams。 在 商務用 Skype Server 中使用內部部署帳戶的使用者無法使用此行為。

- 使用者升級至 Teams 之後，透過指派 TeamsUpgradePolicy 或透過 Move-CsUser -MoveToTeams) ，在下次使用者登入 (Teams 時，商務用 Skype 中的現有連絡人將會與 Teams 中既有的連絡人合併。 無論使用者是從內部部署或線上移至 TeamsOnly，都會發生此行為。

在這兩種情況下，將連絡人從商務用 Skype移轉到 Teams 是非同步，因此可能要過幾分鐘，連絡人才會出現在 Teams 中。 上述兩個事件就是觸發複本的原因。

### <a name="related-links"></a>相關連結

[搭配使用 Teams 的組織移轉和互通性指導方針商務用 Skype](migration-interop-guidance-for-teams-with-skype.md)

[設定 商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連線](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存與升級設定](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[使用會議移轉服務 (MMS) ](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

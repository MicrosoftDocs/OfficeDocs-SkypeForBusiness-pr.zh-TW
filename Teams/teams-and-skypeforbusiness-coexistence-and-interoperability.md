---
title: Microsoft 團隊 |升級、孤島模式、交互操作原則（僅限）
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 商務用 Skype 和 Microsoft 團隊共存選項與商務用 Skype 與團隊之間的互通性的詳細資料。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef1c9d8fd9d30101fdd40dba5946dfefb324742c
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706653"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>瞭解 Microsoft 團隊及商務用 Skype 的共存與互通性

![升級歷程圖表，強調專案定義階段](media/upgrade-banner-project-definition.png "升級歷程階段，重點放在專案定義階段")

本文是您在升級歷程的專案定義階段的一部分，您可以在建立贊助聯盟及專案小組，並定義專案的範圍、目標及願景之後，完成這個活動。 繼續之前，請確認您已完成下列活動：

- [已登記您的專案干係人](upgrade-enlist-stakeholders.md)
- [已定義您的專案範圍](https://aka.ms/SkypetoTeams-Scope)

如果您的組織目前使用商務用 Skype，且您開始將團隊與商務用 Skype 搭配使用，或是您開始升級至小組，請務必瞭解這兩個應用程式如何共存、何時以及其交互操作方式，以及如何管理從商務用 Skype 到團隊的最終升級，一直到使用者的遷移。

> [!Tip]
> 請觀看下列會話，瞭解[共存與互通性](https://aka.ms/teams-upgrade-coexistence-interop)。
>
> 此外，您還可以加入即時、互動式討論會，我們將會分享指導方針、最佳做法，以及專為開始升級規劃與實施的資源。
>
> 首先加入[升級會話方案](https://aka.ms/SkypeToTeamsPlanning)，以開始使用。

## <a name="coexistence-of-teams-and-skype-for-business"></a>團隊與商務用 Skype 的共存

除了共同作業功能之外，小組還提供聊天、通話和會議功能。 視您選擇部署團隊的方式而定，這些功能可能會與商務用 Skype 針對特定使用者所提供的功能重迭。 預設模式是在商務用 Skype 中使用功能重迭來執行團隊;不過，使用者可以指派幾種共存模式（也稱為升級模式），以確保這些功能不會與該使用者重疊（在這種情況下，小組與商務用 Skype 之間提供互通性）。 例如，如果您的商務用 Skype 伺服器內部部署資產有複雜的企業語音部署，但想要讓您的使用者儘快享有新式會議，您可能會想要先以備用路徑來評估[會議](meetings-first.md)。

我們建議您查看下列共存模式，以協助判斷哪個路徑適合您的組織。

> [!Important]
> 提供新的技術，或變更您現有、熟悉的商務用 Skype 環境，同時為使用者帶來巨大的新商業效益。 在執行本文中所述的任何變更之前，請花時間來評估使用者準備狀況，並實施通訊與訓練方案。 此外，我們強烈建議您在組織中執行您的方案之前，先在選取的使用者群組中進行測試。

### <a name="islands-mode"></a>孤島模式

根據預設，使用者可以在商務用 Skype 中執行團隊做為兩個獨立的解決方案，以提供類似及重迭的功能，例如目前狀態、聊天、通話及會議。 團隊使用者也可以利用新的共同作業功能（例如團隊和頻道）、在 Office 365 中存取檔案，以及應用程式。

在此共存模式（稱為**孤島**）中，每個用戶端應用程式都是以個別的孤島運作。 商務用 skype 會與商務用 Skype 進行交談，而團隊則會與團隊進行交談。 使用者應該隨時執行這兩個用戶端，而且可以在啟動通訊的用戶端中以本機方式進行通訊。 如此一來，就不需要在**孤島**模式中進行互通性。

若要避免令人混淆或 regressed 的商務用 Skype 體驗、外部（同盟）通訊、PSTN 語音服務及語音應用程式、Office 整合、USB 裝置的 HID 控制項，以及其他幾個整合，都繼續由商務用 Skype 來處理，且不能在使用**孤島**模式的小組中取得。 在**孤島**模式中，在小組中不支援手機系統;在此模式中，只有企業語音用戶端是商務用 Skype。

> [!Important]
> 在**孤島**模式中，來自同盟使用者（組織外部人員）的所有訊息和呼叫都會傳送到商務用 Skype。 升級至 [**僅限團隊**] 模式之後，組織外的所有訊息和呼叫都會傳送給小組。

> [!Tip]
> 商務用 Skype Online 客戶建議的路徑是從預設的**孤島**模式開始，將組織中的 [推動團隊採用] 飽和度，然後快速移至 [**僅限團隊**] 模式。 在內部部署與混合式客戶（尤其是複雜的客戶）中，您可以從使用團隊共同作業模式將**商務用 skype**部署為起點而不是**孤島**模式，並在組織準備好要採用團隊時，在**商務用 skype 中使用**團隊共同作業與會議模式（也就是會議優先）和 [**僅限小組**]。

### <a name="skype-for-business-only"></a>僅商務用 Skype

在此共存模式中，使用者會保持在商務用 Skype （而非小組）中，以進行聊天、會議和通話功能，而且不會將小組用於小組和頻道。 此模式目前可供使用。不過，在目前的實施中，使用者不會自動關閉團隊和頻道。 您可以使用應用程式許可權原則來隱藏小組和頻道，以達到此目的。

此模式可以在開始受管理的小組部署之前使用，以防止使用者開始使用「建立準備就緒」等小組，或作為在商務用 Skype 使用者的小組會議中啟用驗證參與的方式（前提是使用者是已授權給小組。

### <a name="teams-only"></a>僅限團隊


> [!IMPORTANT]
> 如果您在將使用者移至 [僅 Teams]**** 模式之後解除安裝商務用 Skype 用戶端，則 Outlook 和其他 Office應用程式中的目前狀態將會停止運作。 目前狀態在 Teams 中可正常運作。 因應措施：若要在 Outlook （以及其他 Office app）中查看目前狀態，您必須安裝商務用 Skype，即使您是在 [**僅限團隊**] 模式中執行團隊也一樣。 Microsoft 已發現此問題，正在努力解決中。


**團隊只有**使用者（也稱為已*升級*的使用者）可以存取團隊中的所有功能。 他們可能會保留商務用 Skype 用戶端，以在已由未升級的使用者或外部合作夥伴組織的商務用 Skype 上加入會議。 已升級的使用者可以使用小組與商務用 Skype 之間的互通性功能，繼續與組織中的其他使用者進行通訊（前提是這些商務用 Skype 使用者不是以**孤島**模式提供）。 不過，升級後的使用者無法啟動商務用 Skype 聊天、通話或會議。

只要您的組織準備好讓部分或所有使用者使用團隊作為其唯一的通訊與共同作業工具，您就可以將這些使用者升級至 [**僅限團隊**] 模式。 如果您是從**孤島**模式升級，我們建議您先將團隊在整個組織中採納，然後再開始升級程式。 這可避免由於**孤島**模式無法提供互通性而造成的通訊案例中斷。

若要進一步考慮移至 [**僅限團隊**] 模式，請參閱[僅限團隊模式考慮](teams-only-mode-considerations.md)。

![小組確認訊息的螢幕擷取畫面](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "在使用者升級為僅供團隊使用的使用者之後，在特殊模式下執行的商務用 Skype 用戶端")

### <a name="skype-for-business-with-teams-collaboration"></a>商務用 Skype 與團隊共同作業

您可以使用此模式在您的環境中引入小組，在您繼續利用商務用 Skype 中的現有投資。 在此模式中，您可以讓商務用 Skype 保持不變的狀態，以進行聊天、通話和會議功能，並新增小組共同作業功能（團隊和頻道）、在 Office 365 中存取檔案，以及應用程式。 團隊通訊功能（私人聊天、通話及排程會議）預設會在此模式中關閉。

在內部部署或混合使用商務用 Skype 伺服器起點的組織，如果他們想要為其使用者提供互通性與可預見性，以及將其升級至小組所需的預期時程表（而不是以**孤島**模式來依賴採用飽和），請考慮使用這**種模式。**

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>商務用 Skype 與團隊共同作業與會議（也稱為會議）

您也可以使用此共存模式，加速團隊在您組織中的會議能力，以及其共同作業功能，讓您的使用者能夠充分利用卓越團隊會議體驗-優質的品質。新穎的功能（例如，工具化與翻譯或背景模糊），以及跨所有平臺的卓越使用者體驗，包括行動裝置和瀏覽器。

在此模式中，您也可以在小組和頻道交談中使用小組，使用者將會使用團隊來排程及召開會議。 私人聊天和通話會保留在商務用 Skype 中。 團隊和商務用 Skype 的好處，在這兩個應用程式中，都有一個「更好搭配」功能的範圍，例如目前狀態調解、自動保留/unhold，以及 HID 裝置支援。 請注意，如果您需要使用應用程式許可權原則，可以隱藏團隊和頻道。

此共存模式對於使用商務用 Skype 內部部署的組織而言，可能需要一些時間才能升級至小組，且想要儘快從優質團隊會議中獲益。

> [!Note]
> 當您在任何共存模式（除了**孤島**、團隊和商務用 Skype）中部署時，可進行[交互操作](#interoperability-of-teams-and-skype-for-business)，讓使用者與他人互動並相互通話，並確保您的通訊在您的整個組織期間都能在您的小組中持續流動。 共存模式控制互通性。 接收器的共存模式決定是否可使用互通性。 例如，如果收件者處於只能在一位用戶端（假設、團隊）中提供聊天的模式，則在發起者使用其他用戶端（在此案例中為商務用 Skype）開始聊天時，通常會提供聊天互通性。 另一方面，如果收件者處於兩個用戶端（孤島模式）中都有聊天功能的模式，就不會對聊天提供互通性。 該訊息將由接收器在發起者開始聊天的同一個用戶端中接收。 因此，在**孤島**模式中適當的通訊需要團隊採用飽和功能;也就是說，所有使用者都積極使用及監視兩個用戶端。

> [!TIP]
> 若要協助根據您想要在小組中啟用的功能，在商務用 Skype 仍在使用中時，找出建議的升級模式，請利用[Skype 與團隊升級嚮導](https://aka.ms/SkypeToTeamsWizard)。

如需共存模式、先決條件及管理的詳細資訊，請參閱與商務用 Skype 搭配使用團隊以及[設定您的共存與升級設定](https://aka.ms/SkypeToTeams-SetCoexistence)[的組織的遷移與互通性指導](https://aka.ms/SkypeToTeams-Interop)方針。

| | | |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|決策點|<ul><li>最符合貴組織和使用者需求的共存模式是哪一種？</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|後續步驟|<ul><li>選擇升級歷程的最佳方式。</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>團隊與商務用 Skype 的互通性

互通性是同一個組織中的小組與商務用 Skype 使用者在小組和商務用 Skype 間溝通的能力。

互通性是由收件者的共存模式（也稱為升級模式）所控制。 當接收器處於**孤島**模式時，沒有互通性。

### <a name="native-interop-and-interop-escalation"></a>原生互通性與互通性升級

互通性體驗有兩種類型：原生和互通性升級。

- _原生交互操作_體驗會出現在使用者目前正在使用的用戶端中。 一位使用者會在商務用 Skype 用戶端中，另一個則在團隊中。 原生交互操作體驗不會將它們引導給另一個用戶端來進行通訊，使用者就能在他們目前使用的用戶端中進行交談。 原生交互操作體驗是一對一的聊天與通話。
- _互通性升級_體驗代表，在協助使用者執行高級動作（例如共用其桌面）時，用戶端可協助您建立使用者可以加入的會議，以便在該會議中繼續進行體驗。 該會議是在動作發起者的平臺上建立。 不在該平臺的使用者會收到會議加入連結。 當他們按一下此連結時，會將它們加入至相容用戶端（瀏覽器、web 應用程式或完整用戶端中的會議，視設定而定）。 商務用 Skype 的互通性升級需要最近的用戶端。 來自團隊的互通性升級現已推出。 兩者都支援在租使用者中進行互通性體驗，以及聯盟通訊交叉租使用者。

### <a name="native-interop-experiences"></a>原生交互操作體驗

根據指派給使用者的共存模式（如先前所述），提供下列原生交互操作體驗：

商務用 Skype 使用者可以與團隊使用者進行一對一聊天，反之亦然。 互通性聊天需要經過一個交互操作閘道，這是團隊雲端服務的一部分（因此只有線上存在）。 交互操作聊天是純文字：不支援 rtf 和圖釋。 小組和商務用 Skype 中的使用者會收到交談是互通性交談的通知。

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

商務用 Skype 使用者可以對團隊使用者進行一對一語音與視頻通話，反之亦然。

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> 在內部部署商務用 Skype 的交互操作體驗中，您需要在內部部署環境中使用 Office 365 商務用 Skype 的混合模式。 如需詳細資訊，請參閱[遷移和互通性指導](https://aka.ms/SkypeToTeams-Interop)方針。

在已指派下列其中一個共存模式的使用者中，也可以使用這些交互操作體驗：**商務用 skype 與團隊**共同作業、**商務用 skype 與團隊**共同作業、會議、**商務用 skype**或**僅限團隊**。 在**孤島**模式中，沒有使用者互通性。

### <a name="native-interop-experience-limitations"></a>原生交互操作體驗限制

因為通訊協定和技術有差異，所以無法在本機支援所有功能。 具體說來，不提供下列功能：

- [小組] 或 [商務用 Skype] 不支援 Markdown、rtf 及完整的圖釋集。 不支援 [團隊聊天] 中 [撰寫] 方塊的其他原生功能。
- 團隊與商務用 Skype 之間的螢幕共用（桌面或應用程式共用）不會受到本機支援。 不過，它是透過互通性升級來支援。
- 小組中的群組聊天（多方交談）只能包含使用團隊的參與者。
- 商務用 Skype 中的多方 IM 交談（群組聊天），只能包含使用商務用 Skype 的參與者。 不過，商務用 Skype 提供對多方的互通性升級。
- 不支援進行對等語音或視頻通話，以進行與團隊和商務用 Skype 使用者有關的多方通話。
- [群組聊天] 中的兩方聊天或檔案附件（從團隊到商務用 Skype，反之亦然）不受支援的檔案傳輸。
- 商務用 Skype 持久聊天沒有互通性。

針對所有這些限制式（除了永久聊天之外），一種可能的因應措施是讓一位使用者開始會議並邀請其他使用者加入會議。

此解決方法是互通性升級的基礎。 特別是，不會在本機中實現螢幕共用和升級，但它們是透過互通性升級來支援。

### <a name="interop-escalation-experiences"></a>互通性升級體驗

互通性升級所包含的原始交互操作功能與會議的受管理升級有關。 無論他們有哪些客戶，會議都能提供豐富的體驗供任何人使用。

當團隊使用者觸發互通性升級時，就會建立小組會議。 當商務用 Skype 使用者觸發時，就會建立商務用 Skype 會議。 在這兩種情況下，建立的會議都是 [**立即開會**] 會議，不會反映在使用者的行事曆中。
 
對方會透過按一下該連結，透過交互操作聊天與連接來接收會議加入連結。 如果商務用 Skype 使用者擁有小群組帳戶，且受到團隊使用者的邀請，他們將會加入經過驗證的會議。 否則，它們會以匿名參與者的身分加入。 相反地，小組使用者幾乎總是有商務用 Skype 帳戶和商務用 Skype 用戶端，他們可以用來將商務用 skype 會議加入為已驗證的參與者，但他們也可能以匿名參與者的身分加入，例如使用 Skype會議 App。

當雙方加入會議之後，他們就可以在會議中執行任何支援的活動，例如桌面或內容共用、檔案共用或傳送、新增其他參與者等。

#### <a name="interop-escalation-from-skype-for-business"></a>從商務用 Skype 進行互通性升級

從商務用 Skype 的互通性和互通性升級已在2019年7月的每月 C2R 組建中更新。 先前，商務用 Skype 並未預先意識到遠端方使用的是小組。 它只會從建立會話之後收到的信號 surmised。

當 [寄件者] 指示回應來自 [互通性閘道] （或透過） [interop] 閘道時，它會顯示黃色的 [橫條圖] （橫幅），指出其他人不是使用商務用 Skype。 隨著服務的演變，這會產生誤報，在商務用 Skype 使用者連線至雲端語音信箱服務或其他雲端語音服務時，會看到該業務列，而不是**僅限**實際的小組使用者。
 
若要避免這些誤報，目前狀態服務現在會在其他參與方為**小組只有**實際使用者的情況下，通知商務用 Skype 用戶端。 這可讓商務用 Skype 知道它需要在已建立互通性交談的情況下建立，並將交談視窗專門提供給互通性。

![使用商務用 Skype 使用者建立交互操作交談的 [小組] 訊息螢幕擷取畫面](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

如果商務用 Skype 使用者想要共用桌面，例如，他們會收到會議，並引導您完成步驟。

![[小組] 訊息的螢幕擷取畫面，以與團隊使用者開始會議](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

同時，小組使用者會收到包含會議連結的傳入聊天訊息，並引導您加入會議。

此升級至商務用 Skype 會議適用于租使用者互通性和跨租使用者的同盟通話和聊天。 此選項預設為開啟狀態，且系統管理員沒有提供任何設定。

#### <a name="interop-escalation-from-teams"></a>來自團隊的互通性升級

當小組使用者在包含商務用 Skype 使用者或跨租使用者互通性同盟執行緒中的內提供者交互操作執行緒中選取 [桌面共用] 按鈕時，就可以使用來自團隊的互通性升級至團隊會議。 從1:1 聊天交談或從1:1 通話支援互通性升級。

Windows 版小組桌面用戶端、Mac 版小組桌面用戶端及支援內容共用的瀏覽器上的小組網頁用戶端（在與任何商務用 Skype 用戶端版本進行通訊時）都支援這項功能。

在互通性的執行緒中，以及在同盟互通性的執行緒中，小組使用者現在有了控制項（按鈕）來開始內容共用。 當團隊使用者選取按鈕時，系統會顯示一個額外的功能表，通知他們共用內容，他們必須啟動團隊會議。

如果使用者是在通話中，功能表也會警告他們在團隊和商務用 Skype 之間的目前通話將在他們加入團隊會議時終止。 如果他們如此選擇，就可以在接受前提醒商務用 Skype 使用者。

![[小組] 訊息的螢幕擷取畫面，可與商務用 Skype 使用者共用會議](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

一旦接受，就會將它們放在團隊會議中;他們必須從會議中的共用紙盒開始分享。
 
同時，商務用 Skype 使用者會收到與會議連結的傳入聊天訊息，並引導您加入會議。

在租使用者互通性和跨租使用者的共同通話和聊天中，都有提供團隊會議的這項升級。 此選項預設為開啟狀態，且系統管理員沒有提供任何設定。 不過，如果系統管理員已設定``-AllowPrivateMeetNow`` ``CsTeamsMeetingPolicy``為``$false``，就會關閉該使用者。

在您複習本文之後，請參閱[選擇您的升級歷程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)、[移植與互通性指導](https://aka.ms/SkypeToTeams-Interop)方針、[與商務用 Skype 共存](coexistence-chat-calls-presence.md)，以及[設定您的共存與升級設定](https://aka.ms/SkypeToTeams-SetCoexistence)以取得詳細資料。

## <a name="related-links"></a>相關連結

[影片：管理 SfB 與團隊之間的共存與互通性](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

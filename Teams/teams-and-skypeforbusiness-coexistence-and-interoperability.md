---
title: 瞭解Microsoft Teams與商務用 Skype共存與互通性
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 商務用 Skype與Microsoft Teams共存選項的詳細資料，以及商務用 Skype與Teams之間的互通性。
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
ms.openlocfilehash: 60ed33e1bbafe7fe5600edfa85c9f9d5a13432db
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681424"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>瞭解Microsoft Teams與商務用 Skype共存與互通性

![升級旅程圖，強調Project定義階段。](media/upgrade-banner-project-definition.png "升級旅程的階段，強調Project定義階段")

本文是升級旅程中Project定義階段的一部分。 在建立贊助贊助專案和專案小組，並定義專案的範圍、目標和計畫之後完成。 繼續進行之前，請確認您已完成下列活動：

- [呼叫專案專案專案關係人](upgrade-enlist-stakeholders.md)
- [定義您的專案範圍](./upgrade-define-project-scope.md)

如果您的組織目前使用 商務用 Skype，而您開始與商務用 Skype一起使用Teams，或是您正開始升級至Teams，請務必瞭解兩個應用程式如何共存、何時和如何交互操作，以及如何管理使用者的移轉，並從其升級升級至從商務用 Skype Teams。

> [!Tip]
> 請觀看下列會話以瞭解 [共存和互通性](https://aka.ms/teams-upgrade-coexistence-interop)。
>
> 此外，您可以加入我們參加即時的互動式研討會，我們會在此分享指導方針、最佳做法，以及專為開始升級規劃與實作所設計的資源。
>
> 先加入 [[規劃升級](./upgrade-workshops-landing-page.yml) 會話] 以開始使用。

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Teams與商務用 Skype共存概觀

下列各節說明當您決定升級至 Teams 時可用的共存模式，以及每個模式所提供的功能。 此外，我們描述Skype-for-Business 用戶端的使用者與Teams用戶端上的使用者之間所發生的互通性 (互) ，以及所選共存模式會如何影響互連。

Teams提供共同作業功能、聊天、通話和會議功能。 根據您選擇部署Teams的方式而定，這些功能可能會與商務用 Skype為特定使用者提供的功能重迭。 預設模式是與功能重迭的商務用 Skype一起執行Teams。 不過，您可以將數種共存模式的其中一種指派給使用者， (也稱為升級模式) ，其設計目的是確保這些功能不會與該使用者重迭， (在此情況下，Teams和商務用 Skype之間的互通性) 。 例如，如果您擁有具有複雜企業語音部署的大量商務用 Skype Server內部部署資產，但想讓使用者儘快享受新式會議，您可能會想要評估 [[會議優先](meetings-first.md)] 做為替代路徑。

建議您檢閱下列共存模式，以協助判斷適合貴組織的路徑。

> [!Important]
> 商務用 Skype Online 淘汰之後，共存模式仍繼續存在，但是在線上的使用者只能有 TeamsOnly 模式。 TeamsOnly 以外的任何模式都無法再指派給線上的使用者。  如同 商務用 Skype Online 淘汰之前的情況，內部部署的使用者可以指派 *TeamsOnly 以外的* 任何模式。

### <a name="islands-mode"></a>群島模式

根據預設，使用者可以將Teams與商務用 Skype一起執行，做為兩種可提供類似及重迭功能的個別解決方案。 這些功能包括目前狀態、聊天、通話和會議。 Teams使用者也可以利用新的共同作業功能，例如團隊和頻道、存取Microsoft 365中的檔案，以及應用程式。

在這個稱為 **「群島**」的共存模式中，每一個用戶端應用程式都會以獨立島嶼的方式運作。 商務用 Skype與商務用 Skype進行商談，並Teams Teams。 使用者預期會一直同時執行這兩個用戶端，而且可以在開始通訊的用戶端中以原生方式進行通訊。 因此，在 **群島** 模式中不需要互通性。

為了避免造成混淆或回歸商務用 Skype體驗，商務用 Skype處理下列不在Teams **群島** 模式中處理的整合：

- 外部 (同盟) 通訊。
- PSTN 語音服務與語音應用程式，Office整合。
- USB 裝置的 HID 控制項。
- 其他幾個整合。

在Teams的 **群島** 模式中不支援電話系統。 **群島** 模式不支援用戶端企業語音商務用 Skype。

> [!Important]
> 在 **群島** 模式中，所有來自同盟使用者 (組織外部人員) 的訊息和通話都會傳送給商務用 Skype。 升級為 **Teams只有** 模式之後，組織外部的所有訊息和通話都會傳送到Teams。

### <a name="teams-only"></a>僅Teams

**Teams只有** 使用者 (也稱為 *升級* 的使用者，) 可以存取Teams中的所有功能。 他們可能會保留商務用 Skype用戶端，以加入由非升級的使用者或外部人士召集的商務用 Skype會議。 升級的使用者可以使用Teams與商務用 Skype (之間的互通性功能，繼續與組織中仍在使用商務用 Skype的其他使用者通訊，前提是商務用 Skype使用者不在 **群島** 模式) 。 不過，升級的使用者無法啟動商務用 Skype聊天、通話或會議。

當貴組織準備好讓部分或所有使用者使用Teams作為他們唯一的通訊和共同作業工具時，請將這些使用者升級 **為僅Teams** 模式。 如果您是從 **群島** 模式升級，建議您先使整個組織Teams採用飽和度，再開始升級程式。 由於 **群島** 模式無法提供互通性，這種採用方式可避免通訊中斷的情況。

在 **Teams** 模式中，Teams是 SIP/Tel 通訊協定的預設應用程式。 Outlook中，使用者連絡人卡片中用於通話或聊天的連結將由Teams處理。

如需移至 **僅限Teams模式的** 額外考慮，請 [參閱Teams只有模式考慮](teams-only-mode-considerations.md)。

![確認訊息Teams螢幕擷取畫面。](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "商務用 Skype使用者升級為Teams使用者之後，用戶端會以特殊模式執行")

### <a name="skype-for-business-only"></a>僅商務用 Skype

在此共存模式中，使用者在聊天、會議和通話功能上會維持商務用 Skype而非Teams，而且不會將Teams用於團隊和頻道。 此模式目前已推出;不過，在目前的實作中，使用者的團隊和頻道並不會自動關閉。 您可以使用應用程式設定原則來隱藏團隊和檔案，藉此達到此目的。

您可以在開始受管理的Teams部署之前使用此模式，以防止使用者在建置整備之前開始使用Teams。 只要使用者獲授權Teams，此模式也能為商務用 Skype使用者啟用已驗證的參與Teams會議。

### <a name="skype-for-business-with-teams-collaboration"></a>使用Teams共同作業商務用 Skype

使用此模式在您繼續使用現有投資商務用 Skype的同時，在您的環境中引進Teams。 聊天、通話和會議功能的商務用 Skype維持不變。 新增Teams共同作業功能：

- Teams和頻道。
- 存取Microsoft 365或Office 365中的檔案。
- 應用。 Teams通訊功能：私人聊天、通話和排程會議。

Teams在此模式中，預設會關閉私人聊天、通話和排程會議。

具有內部部署或混合式商務用 Skype Server起始點的組織，如果想要為使用者提供通訊的互通性與可預測性，以及其升級至Teams (的可預測時程表，而非依賴在 **群島** 模式) 採用飽和度，則應將此模式視為「**群島**」模式的替代方案。

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>商務用 Skype Teams共同作業和會議，也稱為會議第一

使用此共存模式可加快貴組織中Teams會議和共同作業功能的可用性。 共存模式可讓您的使用者利用絕佳的Teams會議體驗：

- 品質很好。
- 轉譯和翻譯。
- 背景模糊。
- 跨所有平臺的卓越使用者體驗，包括行動裝置和瀏覽器。

在這種模式下，除了使用團隊和頻道Teams交談，使用者還會使用Teams來排程和進行會議。 私人聊天和通話仍保留在商務用 Skype。 Teams和商務用 Skype受益于一系列「更好的共聚」功能，例如目前狀態對帳、自動保留/取消保留，以及跨兩個應用程式的 HID 裝置支援。 如有需要，您可以使用應用程式設定原則來隱藏團隊和頻道。

這種共存模式對於擁有商務用 Skype內部部署企業語音的組織特別有用。 這些組織可能需要一些時間來升級至Teams，並希望儘快從優質Teams會議中獲益。

> [!TIP]
> 若要在商務用 Skype仍在使用中時，根據您想要在Teams啟用的功能來協助識別建議的升級模式，請利用[Skype Teams升級精靈](https://aka.ms/SkypeToTeamsWizard)。

如需共存模式、必要條件和管理的詳細資訊，請參閱[搭配使用Teams與商務用 Skype的組織移轉和互通性指導方針](./migration-interop-guidance-for-teams-with-skype.md)和[設定您的共存與升級設定](./setting-your-coexistence-and-upgrade-settings.md)。

|決策點圖示 |圖示定義 |描述 |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|決策點|<ul><li>哪些共存模式 (最符合貴組織和使用者的需求) ？</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|後續步驟|<ul><li>選擇升級旅程的最佳方式。</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Teams與商務用 Skype的互通性

互通性是讓同一組織中的Teams和商務用 Skype使用者跨Teams和商務用 Skype通訊的功能。

互通性是由共存模式 (也稱為接收器的升級模式) 所規範。 接收器處於 **群島** 模式時沒有互通性。

> [!Note]
> 在 **群島** 以外的任何共存模式中部署時，Teams和商務用 Skype可以 [相交互操作](#interoperability-of-teams-and-skype-for-business)、讓使用者彼此交談和通話，並確保在升級到Teams的過程中，貴組織之間的通訊保持流暢。 共存模式規範互通性。 接收器的共存模式會決定是否可使用互通性。 例如，如果接收器處於只有一個用戶端才能使用聊天的模式 (例如Teams) ，在這種情況下，如果初始器使用另一個用戶端 (，商務用 Skype) 啟動聊天，通常就會提供聊天互通性。 另一方面，如果接收器處於兩個用戶端都可使用聊天的模式， (群島模式) ，則無法在聊天中使用互通性。 收件者會在初始者開始聊天的同一個用戶端收到訊息。 因此，在 **群島** 模式中適當的通訊需要Teams採用飽和度;也就是說，所有使用者都會主動使用及監控這兩個用戶端。

> [!Note]
> **若要擁有最新的共存體驗，用戶端版本必須是使用者Office部署通道中最新的可用用戶端。**

#### <a name="native-interop-and-interop-escalation"></a>原生 interop 和 interop 升級

有兩種類型的內建體驗：原生和內建升級。

- 使用者目前使用的用戶端中會發生 _原生互通_ 體驗。 其中一位使用者會在商務用 Skype用戶端，另一位位於Teams中。 原生互通體驗不會帶他們到其他用戶端進行通訊。 使用者將能夠在目前使用的用戶端中進行交談。 原生互通的體驗是一對一聊天和通話。
- _交互升級_ 體驗表示用戶端在協助使用者執行進階動作 (，例如共用桌面) 時，有助於建立一個使用者可以加入的會議，以繼續在該會議中繼續體驗。 會議是在動作初始者的平臺上建立。 不在該平臺的使用者或使用者會收到會議加入連結。 當他們按一下這個連結時，會根據設定) ，以相容的用戶端 (瀏覽器、Web App 或完整用戶端加入會議。 從商務用 Skype內升級需要最新的用戶端。 現在可以從Teams傳交上報。 這兩者在租使用者中的互通性體驗以及同盟的跨租使用者通訊中都受到支援。

#### <a name="native-interop-experiences"></a>原生互通體驗

根據指派給 (使用者的共存模式，如) 所述，下列原生互通體驗可供使用：

商務用 Skype使用者可以與Teams使用者進行一對一交談，反之亦然。 互動式聊天需要透過屬於Teams雲端服務一部分的交互閘道 (，因此僅存在線上) 。 聊天間是純文字：不支援 RTF 文字和圖釋。 Teams和商務用 Skype中的使用者會收到交談為交談間交談的通知。

<!--![Screen shot of Interop chat experience from Teams.](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

商務用 Skype使用者可以對Teams使用者進行一對一語音和視訊通話，Teams使用者也可以執行相同的動作。

<!--![Screen shot of Interop calling experience from Teams.](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> 內部部署商務用 Skype的內部部署體驗需要內部部署環境處於混合式模式與Teams。 如需詳細資料，[請設定商務用 Skype Server與Microsoft 365或Office 365之間的混合式連線](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。

下列其中一種共存模式的使用者可使用這些互動式體驗：**商務用 Skype使用Teams共同作業**、商務用 Skype Teams共同作業 **和會議**、**僅商務用 Skype** 或 **僅Teams**. 在 **群島** 模式中，使用者無法交互操作。

#### <a name="native-interop-experience-limitations"></a>原生互通體驗限制

由於通訊協定和技術差異，因此無法原生支援所有功能。 具體來說，下列功能無法使用：

- Teams或商務用 Skype不支援 Markdown、RTF 和完整圖釋集。 不支援Teams聊天中撰寫方塊的其他原生功能。
- 螢幕畫面分享 (桌面或應用程式在Teams和商務用 Skype之間共用) 。 不過，這會透過交互升級來提供支援。
- 群組聊天 (Teams中的多方交談) 只能包含使用Teams的參與者。
- 商務用 Skype中)  (群組聊天中的多方 IM 交談只能包含使用商務用 Skype的參與者。 不過，商務用 Skype提供向多方升級的訊息。
- 將持續對等語音或視訊通話升級為涉及Teams和商務用 Skype使用者的多方通話。
- 不支援兩方聊天或群組聊天中檔案附件的檔案傳輸，從Teams到商務用 Skype，反之亦然。
- 商務用 Skype常設聊天室沒有互通性。

針對常設聊天) 以外的所有限制 (，其中一個可能的因應措施是讓一個使用者召開會議並邀請另一個使用者加入會議。

此因應措施是交互升級的基礎。 特別是，螢幕畫面分享和升級到多方是無法原生實現的，但是會透過內部部署升級來提供支援。

#### <a name="interop-escalation-experiences"></a>Interop 上傳體驗

Interop 升級包含以受管理的升級到會議來補充原生 Interop 功能。 無論任何人擁有哪一個客戶，會議都能提供豐富的體驗。

當Teams使用者觸發內部升級時，會建立Teams會議。 當商務用 Skype使用者觸發該會議時，會建立商務用 Skype會議。 在這兩種情況下，建立的會議都是 [ **立即開會** ] 會議，不會反映在使用者的行事曆上。

另一方會透過聊天間收到會議加入連結，並按一下該連結來加入。 如果商務用 Skype使用者有Teams帳戶，並受Teams使用者的邀請，他們將會加入已驗證的會議。 否則，他們會以匿名參與者的身分加入。 相反地，Teams使用者幾乎一律擁有商務用 Skype帳戶和商務用 Skype用戶端，他們能以已驗證的參與者身分加入商務用 Skype會議，但也可能以匿名參與者的身分加入，例如使用 Skype 會議 App。

當對方加入會議後，他們就可以進行會議中支援的任何活動，例如桌面或內容共用、檔案共用或傳輸、新增其他參與者等等。

#### <a name="interop-escalation-from-skype-for-business"></a>從商務用 Skype內升級

在每月 C2R 的 2019 年 7 月組建中，已更新來自商務用 Skype的 Interop 和交集升級。 之前，商務用 Skype對遠端一方使用Teams沒有事先通知。 它只會從建立會話後收到的訊號進行猜測。

當訊號指出回應來自 (或透過) 閘道時，它會顯示黃色的商務列 (橫幅) 指出另一方並未使用商務用 Skype。 隨著我們服務的演進，導致誤判，商務用 Skype使用者在連線至雲端語音信箱服務或其他雲端語音服務時，會看到商務列，而非實際 **的僅限Teams** 使用者。

為防止這些誤判，目前狀態服務現在會在對方是Teams僅實際使用者時通知 **商務用 Skype** 用戶端。 這可讓商務用 Skype注意，在建立交談之前，必須先建立一個交談，而交談視窗是特定的交互。

![Teams訊息與商務用 Skype使用者建立交談的螢幕擷取畫面。](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

例如，如果商務用 Skype使用者想要共用桌面，系統會通知我們將開始會議並引導您完成步驟。

![Teams訊息開始與Teams使用者開會的螢幕擷取畫面。](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

同時，Teams使用者會收到含有會議連結的傳入聊天訊息，並引導他們加入會議。

這種升級至商務用 Skype會議的功能適用于租使用者內部會議和跨租使用者同盟通話和聊天。 此設定預設為開啟，系統管理員不必布建任何設定。

#### <a name="interop-escalation-from-teams"></a>從 Teams 間升級

當Teams使用者在與商務用 Skype使用者的租使用者間討論串中選取桌面共用按鈕，或在跨租使用者間的同盟對話中選取桌面共用按鈕時，即可從Teams升級至Teams會議。 1 對 1 聊天交談或 1 對 1 通話支援互連升級。

Windows的Teams桌面用戶端、適用于 Mac 的Teams桌面用戶端，以及支援內容共用的瀏覽器上的Teams Web 用戶端，以及與任何商務用 Skype用戶端版本通訊時，都支援此功能。

在互通性執行緒和同盟互通性執行緒中，Teams使用者現在有可開始內容共用的控制項 (按鈕) 。 當Teams使用者選取該按鈕時，會顯示一個額外的功能表，通知他們共用內容，他們必須啟動Teams會議。

如果使用者正在通話中，功能表也會警告他們，他們目前Teams和商務用 Skype之間的通話將會在進入Teams會議時終止。 如果他們選擇的話，可以在接受之前警告商務用 Skype使用者。

![Teams訊息與商務用 Skype使用者共用會議的螢幕擷取畫面。](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

接受邀請時，他們會加入Teams會議;他們必須從會議中的共用匣開始共用。

同時，商務用 Skype使用者會收到含有會議連結的傳入聊天訊息，並引導他們加入會議。

這種升級至Teams會議的功能適用于租使用者內部會議和跨租使用者同盟通話和聊天。 此設定預設為開啟，系統管理員不必布建任何設定。 不過，如果系統管理員設 ``-AllowPrivateMeetNow`` ``CsTeamsMeetingPolicy`` ``$false`` 為 ， 使用者會關閉此功能。

檢閱本文之後，請參閱[選擇您的升級旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)、[移轉與互通性指引](./migration-interop-guidance-for-teams-with-skype.md)、[與商務用 Skype共存](coexistence-chat-calls-presence.md)，以及[設定共存與升級設定](./setting-your-coexistence-and-upgrade-settings.md)以取得實作詳細資料。 我們也建議使用下列影片：[影片：管理 SfB 與 Teams 之間的共存和互通性](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Teams與共存商務用 Skype的技術詳細資料

下列各節摘要列出在同一個組織中執行Teams和商務用 Skype用戶端時，無論使用何種模式和升級方法：

- [會議](#meetings)
- [互 操作 性](#interoperability)
- [Interop 與原生交談對話](#interop-versus-native-conversation-threads)
- [目前狀態](#presence)
- [同盟](#federation)
- [連絡人](#contacts)

### <a name="meetings"></a>會議

無論其模式為何，使用者隨時都可以加入受邀參加的任何會議類型，不論會議是商務用 Skype或Teams。  不過，使用者必須以符合會議類型的對應用戶端加入會議：

- 如果會議是Teams會議，則所有參與者 (是 TeamsOnly、Islands 或商務用 Skype使用者，) 使用Teams用戶端加入會議。 如果沒有安裝Teams，使用者會在嘗試加入會議時導向至網路。

- 如果會議是商務用 Skype會議，則所有參與者 (是 TeamsOnly、Islands 或商務用 Skype使用者，) 使用商務用 Skype用戶端加入會議。 如果尚未安裝商務用 Skype用戶端，系統會將使用者導向至網路，透過 Skype 會議 應用程式加入。

組織會議時，排程的會議類型是根據召集人的模式，如下表所示：

| 召集人模式    |      行為 |
| :------------------ | :---------------- |
| TeamsOnly、SfbWithTeamsCollabAndMeetings | 在 Teams 中排程的所有會議。 Outlook不供應商務用 Skype增益集。 |
| SfbWithTeamsCollab， SfbOnly | 在 商務用 Skype 中排程的所有會議。 Teams增益集不適用於 Outlook。 |
| 離島 | 根據預設，會議可以排程在商務用 Skype或Teams。 這兩個增益集都可在 Outlook 中使用。 不過，您可以選擇性地要求群島中的使用者一律在Teams中排程會議，方法是將 TeamsMeetingPolicy 實例指派給 PreferredMeetingProviderForIslandsMode=Teams。|

### <a name="interoperability"></a>互 操作 性

如上文所述[，Teams與商務用 Skype的互通性](#interoperability-of-teams-and-skype-for-business)，Teams在某些情況下支援與商務用 Skype交互。 Interop 通訊是指商務用 Skype使用者與Teams使用者之間的聊天或通話。  只有兩個使用者之間才能進行 Interop 通訊;不支援多方聊天/通話或新增其他使用者。

當下列每一項皆為 True 時，會建立兩個使用者之間的聊天或通話：

- 一個使用者正在使用 Teams，而另一個使用者正在使用 商務用 Skype。

- 初始通訊收件者的模式為 NOT Islands (否則如果兩個使用者都在同一個組織中，通訊會連線到相同的用戶端) 。 在同盟案例中，傳送使用者使用的是 Teams，而收件者不是 TeamsOnly 模式。

- Teams使用者沒有內部部署商務用 Skype帳戶。

在內部溝通中，聊天僅提供純文字。 此外，無法 *在聊天間* 共用檔案和螢幕畫面共用。 不過，在交談間的使用者可以透過在聊天間建立隨選會議，輕鬆達成檔案和/或螢幕共用，如下所述：

- 如果Teams使用者嘗試共用螢幕，系統會自動建立隨選Teams會議，並將該會議的邀請連結傳送給商務用 Skype使用者的用戶端。 按一下連結後，商務用 Skype使用者就會開啟Teams並加入會議。 這兩個使用者現在都參加Teams會議，並可視需要共用。

- 如果商務用 Skype使用者使用 2018 年或更新版本的用戶端，並嘗試共用任何內容，系統會自動建立隨選商務用 Skype會議，並將該會議的邀請連結傳送給Teams使用者的用戶端。 按一下連結後，Teams使用者會嘗試加入商務用 Skype會議。 如果Teams使用者已安裝商務用 Skype用戶端，該商務用 Skype就會開啟，如果尚未登入) ，系統會提示使用者登入 (。  如果Teams使用者未安裝商務用 Skype用戶端，系統會提示使用者使用 Web 版本。 一旦兩個使用者登入後，就會加入商務用 Skype會議，並可視需要共用。

### <a name="interop-versus-native-conversation-threads"></a>Interop 與原生交談對話

由於 interop 通訊並不支援原生Teams交談的所有功能，因此Teams用戶端會針對Teams對Teams和Teams對商務用 Skype通訊維護個別的交談對話。 這些交談會在使用者介面中以不同的方式呈現：Interop 對話可以與一般原生Teams對話區隔如下：

- 缺少 RTF 文字、檔案/螢幕共用、無法新增使用者的控制項。
- 對目標使用者圖示進行修改，其中顯示商務用 Skype的 「S」。

這些差異會顯示在下列螢幕擷取畫面中：

使用者 G3 測試的原生Teams對Teams交談

![顯示原生Teams對Teams交談的圖表。](media/teams-upgrade-native-thread.png)

同一個使用者 G3 測試的交談

![顯示Teams對Teams交談的圖表。](media/teams-upgrade-interop-thread.png)

建立交談對話後，其類型永遠不會變更。 建立之後，Teams中的交互對話一律會路由至目標使用者的商務用 Skype用戶端。 原生對話一律會路由至目標使用者Teams用戶端。  如果收件者使用者的模式變更，該使用者現有的Teams對話將無法再運作，且該聊天中會顯示附注與連結，以啟動新的原生交談，如下列螢幕擷取畫面所示。

![顯示與已升級商務用 Skype使用者聊天的圖表。](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>目前狀態

指定使用者的目前狀態是根據使用者透過用戶端在服務中的活動。 系統會隨即發佈目前狀態，讓其他使用者查看。  商務用 Skype和Teams是具有個別用戶端的個別服務，因此每個服務都有自己的使用者目前狀態。   在 Teams 和 商務用 Skype Online 中的目前狀態服務之間也會同步處理。  這可讓一個服務在需要時，從另一個服務發佈該使用者的目前狀態。

目前狀態發佈行為是以使用者的模式為基礎。 有三種基本情況：

- 如果使用者處於 TeamsOnly 模式，所有其他使用者會看到該使用者Teams目前狀態，無論他們使用哪個用戶端。

- 如果使用者處於任何商務用 Skype模式，所有其他使用者都會看到該使用者商務用 Skype目前狀態，無論他們使用哪個用戶端。

- 如果使用者處於群島模式，則以商務用 Skype和Teams發佈的目前狀態是獨立的，因此向相同組織內的使用者顯示的目前狀態將取決於另一個使用者的用戶端。 同盟組織中的使用者會根據其商務用 Skype活動看到該使用者的目前狀態，因為前往群島模式的同盟流量已登入商務用 Skype。

例如，假設使用者 A 是在群島模式。 如果 User A 在 Teams 中有效，但並未登入商務用 Skype，其他使用者會從他們的Teams用戶端看到 User A 為作用中，但在商務用 Skype用戶端中，他們會將 User A 視為離線。 這是根據設計，因為如果沒有執行用戶端，就無法連絡使用者 A。


### <a name="federation"></a>同盟

Teams與其他使用 商務用 Skype 的使用者建立同盟，Teams使用者必須連線到商務用 Skype。 TeamsUpgradePolicy 會管理傳入同盟聊天和通話的路由。 同盟路由行為與相同租使用者案例相同，但在群島模式中除外。 收件者處於群島模式時：

- 如果收件者是同盟租使用者，從Teams啟動的聊天和通話會進入商務用 Skype。
- 如果收件者在同一個租使用者中，從Teams啟動的聊天和通話會進入Teams。
- 從商務用 Skype啟動的聊天和通話一律會進入商務用 Skype。

同盟聊天可以是原生對話或對話間串。 請參閱 [Interop 與原生交談對話](#interop-versus-native-conversation-threads)。

- 如果接收器和寄件者都處於 TeamsOnly 升級模式，則交談將會是包含所有豐富訊息和通話功能的原生聊天體驗。 若要深入瞭解，請閱讀Teams[中外部 (同盟) 使用者的原生聊天體驗](native-chat-for-external-users.md)。

- 如果有任一交談參與者未處於 TeamsOnly 升級模式，則交談仍會以僅文字訊息提供交互體驗。 使用者介面會以類似相同租使用者內部討論串的方式公開同盟聊天，除了有指出使用者為外部使用者的附注。

如需詳細資料，請參閱[管理外部 (同盟) 使用者在](manage-external-access.md) [Teams 中的Microsoft Teams和原生聊天體驗中的](native-chat-for-external-users.md)外部存取。

### <a name="contacts"></a>連絡人

Teams和商務用 Skype有個別的連絡人清單。 這表示在一個系統中新增、移除和修改的連絡人不會同步處理到另一個系統。 不過，當發生兩個特定事件的其中一個時，系統會自動將來自商務用 Skype的連絡人複製到Teams：

- 對於任何商務用 Skype Online 使用者，第一次登入Teams時，商務用 Skype的連絡人將會複製到Teams。  在 商務用 Skype Server 中使用內部部署帳戶的使用者無法使用此行為。

- 使用者升級至 (Teams 之後：透過指派 TeamsUpgradePolicy 或透過 Move-CsUser -MoveToTeams) ，在下次使用者登入Teams時，商務用 Skype中的現有連絡人將會與Teams中的現有連絡人合併。 無論使用者是從內部部署或線上移至 TeamsOnly，都會發生此行為。

在這兩種情況下，將連絡人從商務用 Skype移轉到Teams是非同步，因此可能要過幾分鐘，連絡人才會出現在Teams中。 上述兩個事件就是觸發複本的原因。

### <a name="related-links"></a>相關連結

[搭配使用Teams的組織移轉和互通性指導方針商務用 Skype](migration-interop-guidance-for-teams-with-skype.md)

[設定商務用 Skype Server與Microsoft 365或Office 365之間的混合式連線](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存與升級設定](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[使用會議移轉服務 (MMS) ](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

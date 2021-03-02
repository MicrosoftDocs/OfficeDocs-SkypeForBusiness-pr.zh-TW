---
title: 瞭解 Microsoft Teams 和商務用 Skype 共存與互通性
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 商務用 Skype 和 Microsoft Teams 共存選項的詳細資訊，以及商務用 Skype 和 Teams 之間產生的互通性。
localization_priority: Normal
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
ms.openlocfilehash: 430c64fed77412ca555048adf3cf5e323fa20856
ms.sourcegitcommit: 79b19b326ef40bf04af03021a7c6506fdd9417ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2021
ms.locfileid: "50397588"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>瞭解 Microsoft Teams 和商務用 Skype 共存與互通性

![升級歷程圖，強調專案定義階段](media/upgrade-banner-project-definition.png "升級階段，強調專案定義階段")

本文是升級過程中專案定義階段的一部分。 建立贊助贊助小組和專案小組，並定義專案的範圍、目標及計畫之後，就完成。 繼續進行之前，請確認您已完成下列活動：

- [已招募專案專案關係人](upgrade-enlist-stakeholders.md)
- [已定義您的專案範圍](https://aka.ms/SkypetoTeams-Scope)

如果貴組織今天使用商務用 Skype，而您正開始將 Teams 與商務用 Skype 同時使用，或者您正開始升級至 Teams，瞭解這兩個應用程式如何並存、何時及如何交互操作，以及如何管理使用者的移移，一路從商務用 Skype 升級至 Teams，這一點非常重要。

> [!Tip]
> 觀看下列會話以瞭解 [共存和互通性](https://aka.ms/teams-upgrade-coexistence-interop)。
>
> 此外，您可以與我們一起參與即時互動式研討會，我們會在這裡分享指導、最佳做法和資源，這些工作旨在開始規劃及實作升級。
>
> 首先 [加入規劃升級](https://aka.ms/SkypeToTeamsPlanning) 會話以開始使用。

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Teams 和商務用 Skype 的共存概觀

下列各節說明當您決定升級 Teams 時可用的共存模式，以及每個模式提供的功能。 此外，我們描述在商務用 Skype 用戶端與 Teams 用戶端使用者之間 (交互操作) 的互通性，以及所選共存模式對交互操作的影響。

 Teams 提供共同合作功能、聊天、通話和會議功能。 視您選擇部署 Teams 的方式不同，這些功能可能會與商務用 Skype 為使用者提供的功能重迭。 預設模式是同時使用功能重迭的商務用 Skype 來執行 Teams。 不過，使用者可以被指派幾個共存模式之一 (也稱為升級模式) ，其設計目的是確保這些功能不會與該使用者重迭 (在這種情況下，可以使用 Teams 和商務用 Skype 之間的互通性) 。 例如，如果您的商務用 Skype Server 內部部署具有複雜的企業語音部署，但希望使用者儘快享受新式會議，您可能會想要評估會議為替代路徑。 [](meetings-first.md)

建議您查看下列共存模式，協助判斷適合貴組織的路徑。

> [!Important]
> 引進新的技術或變更您現有、熟悉的商務用 Skype 環境，同時提供全新的商業優點，可能會干擾使用者。 在您執行本文所述的任何變更之前，請花一些時間評估使用者的備戰能力，並實行通訊和訓練計畫。 此外，我們強烈建議您先與選取的使用者群組試驗您的計畫，再在整個組織中執行。

### <a name="islands-mode"></a>群島模式

根據預設，使用者可以將 Teams 與商務用 Skype 同時執行，做為提供類似和重迭功能的兩種獨立解決方案。 這些功能包括目前狀態、聊天、通話和會議。 Teams 使用者也可以利用新的共同合作功能，例如團隊和頻道、存取 Microsoft 365 或 Office 365 中的檔案，以及應用程式。

在這個稱為群島的共存模式中，每個用戶端應用程式會以個別的島嶼方式運作。 商務用 Skype 與商務用 Skype 交談，Teams 與 Teams 交談。 使用者預期會一併執行這兩個用戶端，而且可以在開始進行通訊的用戶端內進行原生通訊。 因此，在群島模式中 **不需要互通性。**

為了避免造成混淆或倒退的商務用 Skype 體驗，商務用 Skype 會處理下列在 Teams **Islands** 模式中未處理的整合：

- 外部 (的) 通訊。
- PSTN 語音服務與語音應用程式、Office 整合。
- USB 裝置用 HID 控制項。
- 數個其他整合。  

在群島模式中，Teams 不支援 **電話** 系統。 **群島** 模式不支援企業語音用戶端是商務用 Skype。

> [!Important]
> 在 **群島** 模式中，所有來自貴組織外部 (使用者的訊息和通話) 傳送到商務用 Skype。 升級到 Teams **模式** 後，組織外部的所有訊息和通話會傳送至 Teams。

> [!Tip]
> 商務用 Skype Online 客戶建議的路徑是，從預設 **群島** 模式開始、推動 Teams 在組織中採用飽和度，然後快速移至 **Teams 僅** 模式。 內部部署和混合式客戶 ，尤其是複雜的客戶，可能從部署商務用 Skype 與 **Teams** 共同合作模式做為起點，而不是以群島模式為起點，從該模式進入商務用 Skype 與 **Teams** 共同合作與會議模式 (即會議第一) ，以及當組織準備好採用 Teams 時，則採用 **Teams** 模式。

### <a name="teams-only"></a>僅 Teams

Teams **使用者** (*升級的使用者* ，) Teams 中所有功能的存取權限。 他們可以保留商務用 Skype 用戶端，以加入由未升級的使用者或外部方所組織的商務用 Skype 會議。 升級的使用者可以使用 Teams 和商務用 Skype (之間的互通性功能，繼續與組織中仍在使用商務用 Skype 的其他使用者通訊 (但商務用 Skype 使用者不處於 **群島** 模式) 。 不過，升級的使用者無法啟動商務用 Skype 聊天、通話或會議。

當貴組織準備好讓部分或所有使用者使用 Teams 作為他們唯一的通訊和共同處理工具時，請將這些使用者升級至 **Teams 僅模式** 。 如果您是從群島模式升級，建議您在開始升級程式之前，先將 Teams 的採用時間飽和至整個組織。 這項採用可避免因群島模式未提供互通性而中斷通訊案例。

在 Teams **模式** 時，Teams 是 SIP/Tel 通訊協定的預設應用程式。 Teams 會處理 Outlook 中使用者連絡人卡片中用於通話或聊天的連結。

有關移往 **Teams** 模式的額外考慮，請參閱 [Teams 僅模式考慮](teams-only-mode-considerations.md)。

![Teams 確認訊息的螢幕擷取畫面](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "在使用者升級為 Teams 專用使用者之後，以特殊模式執行商務用 Skype 用戶端")

### <a name="skype-for-business-only"></a>僅商務用 Skype

在這個共存模式中，使用者會保留在商務用 Skype 中，而非 Teams 中，以用於聊天、會議及通話功能，而且不會將 Teams 用於團隊和頻道。 此模式目前提供;不過，在目前的執行中，使用者不會自動關閉團隊和頻道。 若要達成此目標，可以使用應用程式設定政策來隱藏團隊和檔案。

在開始 Teams 受管理部署之前，可以使用此模式，以防止使用者先開始使用 Teams，再進行內建的備修。 此模式也是一種啟用已驗證參與商務用 Skype 使用者的 Teams 會議的方式，但使用者必須獲得 Teams 授權。

### <a name="skype-for-business-with-teams-collaboration"></a>使用 Teams 共同處理商務用 Skype

使用此模式在繼續使用商務用 Skype 的現有投資的同時，在環境中引進 Teams。 讓商務用 Skype 在聊天、通話和會議功能上維持不變。 新增 Teams 共同合作功能：

- 團隊和頻道。
- 存取 Microsoft 365 或 Office 365 中的檔案。
- 應用。 Teams 通訊功能—私人聊天、通話和排程會議。

在此模式中，Teams 私人聊天、通話和排程會議預設為關閉。

從內部部署或混合式商務用 Skype Server 開始著手的組織，若想讓使用者在通訊方面具備互通性和可預測性，以及擁有可預測的升級到 Teams (的時程表，而非仰賴在群島模式) 中的採用飽和度，則應考慮此模式作為群島模式的替代模式。 

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>商務用 Skype 與 Teams 共同合作與會議，也稱為會議第一

使用此共存模式可加速組織中 Teams 會議與共同合作功能的可用性。 共存模式可讓您的使用者利用超強的 Teams 會議體驗：

- 品質好。
- 文字抄寫和翻譯。
- 背景模糊。
- 跨所有平臺的優質使用者體驗，包括行動裝置和瀏覽器。

除了在此模式中使用 Teams 進行團隊和頻道型交談，使用者將使用 Teams 排程和召開會議。 私人聊天和通話會保留在商務用 Skype 上。 Teams 和商務用 Skype 受益于各種「一起改善」功能，例如目前狀態對帳、自動保留/取消保留，以及跨兩個應用程式的 HID 裝置支援。 如果需要，可以隱藏團隊和頻道，使用應用程式設定政策。

這個共存模式對於使用企業語音進行商務用 Skype 內部部署的組織特別有用。 這些組織可能需要一些時間升級至 Teams，並想要儘快受益于高超的 Teams 會議。

> [!TIP]
> 若要在商務用 Skype 仍在使用中時，根據您想要在 Teams 中啟用的功能，協助識別建議的升級模式，請使用 [Skype 到 Teams](https://aka.ms/SkypeToTeamsWizard)升級精靈。

有關共存模式、先決條件及管理等詳細資訊，請參閱使用 Teams 與商務用 [Skype](https://aka.ms/SkypeToTeams-Interop) 的組織移移和互通性指南，以及設定 [您的共存與升級設定](https://aka.ms/SkypeToTeams-SetCoexistence)。

|決策點圖示 |圖示定義 |說明 |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|決策點|<ul><li>哪一種 () 最適合貴組織及使用者的需求？</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|後續步驟|<ul><li>選擇升級過程的最佳方式。</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Teams 和商務用 Skype 的互通性

互通性是同一個組織中 Teams 和商務用 Skype 使用者跨 Teams 和商務用 Skype 進行通訊的能力。

互通性是由共存模式 (，也稱為收) 的升級模式。 當接收者位於群島模式時，沒有 **互通性** 。

> [!Note]
> 當部署在群島以外的任何共存模式中時，Teams 和商務用 Skype[](#interoperability-of-teams-and-skype-for-business)可以交互操作，讓使用者可以彼此聊天和通話，並確保在升級 Teams 過程中，整個組織的通訊保持流暢。 共存模式可規範互通性。 收受者共存模式會決定是否提供互通性。 例如，如果接收者是在一個用戶端中僅提供聊天的模式中 (例如 Teams) ，當啟動程式使用另一個用戶端 (在此案例中，商務用 Skype) 啟動聊天時，一般會提供聊天互通性。 另一方面，如果收受者是在兩個用戶端 (Islands 模式) 中均提供聊天的模式，則聊天將無法提供互通性。 在啟動器開始聊天的同一個用戶端中，接收者將會收到訊息。 因此，在群島模式中進行 **適當的** 通訊需要 Teams 採用飽和度;也就是說，所有使用者都是主動使用及監控這兩個用戶端。

> [!Note]
> **若要擁有最新的共存體驗，用戶端版本必須是使用者 Office 部署通道中的最新可用用戶端。**

#### <a name="native-interop-and-interop-escalation"></a>原生交互操作和交互操作升級

有兩種類型的交互操作體驗：原生和交互操作升級。

- 使用者 _目前_ 使用的用戶端會發生原生的交互操作體驗。 其中一個使用者會使用商務用 Skype 用戶端，另一個使用者則位在 Teams 中。 原生的交互操作體驗不會帶他們到另一個用戶端進行通訊。 使用者將能夠在他們目前使用的用戶端中進行交談。 原生的交互操作體驗是一對一聊天和通話。
- 相互 _升級_ 體驗表示，做為協助使用者執行進一步動作 (例如共用桌面) 的一部分，用戶端可協助建立一個使用者可以加入的會議，以在會議中繼續體驗。 會議是在動作啟動者平臺上建立。 不在該平臺的使用者會收到會議加入連結。 當他們按一下這個連結時，他們會在相容的用戶端 (瀏覽器、Web App 或完整用戶端加入會議，視組) 。 商務用 Skype 的相互升級需要最近使用的客戶。 Teams 的相互升級現已提供。 兩者在租使用者中的互通性體驗以及跨租使用者之間的聯合通訊都受到支援。

#### <a name="native-interop-experiences"></a>原生交互操作體驗

根據先前所述指派給使用者的共存模式 (，) 提供下列原生交互操作體驗：

商務用 Skype 使用者可以與 Teams 使用者進行一對一交談，反之亦然。 交互操作聊天需要透過 Teams 雲端服務所建立之一部分的交互操作閘道 (因此僅存在線上) 。 交互操作聊天是純文字：不支援豐富的文字和圖釋。 Teams 和商務用 Skype 中的使用者會收到交談是交互操作交談的通知。

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

商務用 Skype 使用者可以對 Teams 使用者進行一對一語音和視音訊通話，而 Teams 使用者也可以這麼做。

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> 內部部署商務用 Skype 的交互操作體驗需要內部部署環境與 Microsoft 365 或 Office 365 商務用 Skype 採用混合模式。 有關詳細資料，請參閱 [移移和互通性指南](https://aka.ms/SkypeToTeams-Interop)。

這些交互操作體驗可供指派下列其中一種共存模式的使用者之間使用：商務用 **Skype with Teams 共同** 合作、商務用 Skype with Teams 共同合作和 **會議**、商務用 **Skype** 或 **Teams。** 在群島模式中，使用者 **之間沒有互通性** 。

#### <a name="native-interop-experience-limitations"></a>原生交互操作體驗限制

由於通訊協定與技術的差異，因此無法原生支援所有功能。 具體來說，下列功能無法提供：

- Teams 或商務用 Skype 不支援 Markdown、豐富文字和完整的圖釋集。 不支援 Teams 聊天中撰寫方塊的其他原生功能。
- 在 Teams (商務用 Skype 之間) 桌面或應用程式的螢幕畫面分享功能不受原生支援。 不過，透過相互升級支援。
- 群組聊天 (Teams 中的) 交談只能包含使用 Teams 的參與者。
- 商務用 Skype (群組聊天) 方 IM 交談只能包含使用商務用 Skype 的參與者。 不過，商務用 Skype 提供多方服務升級功能。
- 不支援將進行中的對等語音或視音訊通話升級為涉及 Teams 和商務用 Skype 使用者的多方通話。
- 不支援雙方聊天的檔案傳輸，或群組聊天中的檔案附件，從 Teams 傳輸至商務用 Skype，反之亦然。
- 商務用 Skype 的持續性聊天沒有互通性。

針對這些限制 (長聊天) ，其中一個可能的解決方法是讓一個使用者啟動會議並邀請其他使用者加入會議。

此解決方法是相互升級的基礎。 特別是，螢幕畫面分享和向多方升級無法原生地達成，但會透過相互升級支援。

#### <a name="interop-escalation-experiences"></a>相互升級體驗

交互操作升級包含以受管理的升級至會議來補充原生交互操作功能。 會議提供豐富的體驗給任何人，無論他們擁有哪一個用戶端。

當 Teams 使用者觸發交互操作升級時，即會建立 Teams 會議。 當商務用 Skype 使用者觸發會議時，即會建立商務用 Skype 會議。 在這兩種情況下，所建立的會議都是一場即開會的會議，不會反映在使用者的日曆上。

另一方會透過交互操作聊天收到會議加入連結，然後按一下該連結即可加入。 如果商務用 Skype 使用者有 Teams 帳戶，且由 Teams 使用者邀請，他們將加入已驗證的會議。 否則，他們將以匿名參與者的加入。 相反地，Teams 使用者幾乎一定都有商務用 Skype 帳戶和商務用 Skype 用戶端，他們可以使用經驗證的參與者加入商務用 Skype 會議，但他們也可能以匿名參與者的名加入，例如使用 Skype 會議應用程式。

當各方加入會議後，他們可以進行會議支援的任何活動，例如桌面或內容共用、檔案共用或傳輸、新增其他參與者等等。

#### <a name="interop-escalation-from-skype-for-business"></a>商務用 Skype 的相互升級

在 2019 年 7 月每月 C2R 的建立中更新了商務用 Skype 的交互操作和交互操作升級。 之前，商務用 Skype 並未事先知道遠端派對正在使用 Teams。 它只能從會話建立後收到的訊號中猜測。

當訊號指出回應來自 (或透過) 交互操作閘道時，它會顯示黃色商業橫條 (橫幅) 表示另一方並未使用商務用 Skype。 隨著我們的服務變革，這導致誤認為商務用 Skype 使用者在連接至雲端語音信箱服務或其他雲端語音服務時，會看到商務用 Skype 的商務欄，而不是實際只有 **Teams 的使用者** 。

為了避免這些誤誤，當另一方是 Teams 實際使用者時，目前狀態服務現在會通知商務用Skype 用戶端。 這可讓商務用 Skype 在建立前先建立交互操作交談，而且交談視窗必須特別針對交互操作進行。

![Teams 訊息與商務用 Skype 使用者建立交互操作交談的螢幕擷取畫面](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

例如，如果商務用 Skype 使用者想要共用桌面，會通知他們我們將開始會議，並引導您完成這些步驟。

![Teams 訊息開始與 Teams 使用者開會的螢幕擷取畫面](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

同時，Teams 使用者會收到包含會議連結的傳入聊天訊息，並引導您加入。

這種升級為商務用 Skype 會議，適用于租使用者間交互操作和跨租使用者聯盟通話和聊天。 此設定預設為啟用，且系統管理員無需進行任何設定。

#### <a name="interop-escalation-from-teams"></a>Teams 的相互升級

Teams 使用者現在可在租使用者間交互操作對話中選取桌面共用按鈕時，從 Teams 升級至 Teams 會議，或是跨租使用者交互操作聯盟執行緒。 1 對 1 聊天交談或 1 對 1 通話支援交互操作升級。

此功能支援 Windows 版 Teams 桌面用戶端、Mac 版 Teams 桌面用戶端，以及支援內容共用的瀏覽器上的 Teams Web 用戶端，同時可與商務用 Skype 用戶端版本進行通訊。

在互通性執行緒和聯合互通性執行緒中，Teams 使用者現在擁有 (按鈕) 開始內容共用。 當 Teams 使用者選取按鈕時，他們看到一個額外的功能表，通知他們若要共用內容，他們需要啟動 Teams 會議。

如果使用者在通話中，功能表也會警告使用者，當他們進入 Teams 會議時，他們目前在 Teams 和商務用 Skype 之間的通話將會終止。 如果他們選擇的話，可以在接受之前警告商務用 Skype 使用者。

![與商務用 Skype 使用者共用會議之 Teams 訊息的螢幕擷取畫面](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

接受之後，這些會議會進入 Teams 會議;他們必須從會議中的共用系統系統開始共用。

同時，商務用 Skype 使用者會收到包含會議連結的傳入聊天訊息，並引導您加入。

此 Teams 會議升級為租使用者間交互操作和跨租使用者聯盟通話和聊天。 此設定預設為啟用，且系統管理員無需進行任何設定。 不過，如果系統管理員設定為 .，則使用者已關閉 ``-AllowPrivateMeetNow`` ``CsTeamsMeetingPolicy`` ``$false`` 此設定。

在您閱讀本文之後，請參閱選擇[](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)您的升級旅程、移移和互通性[指引](https://aka.ms/SkypeToTeams-Interop)、與商務用[Skype](coexistence-chat-calls-presence.md)共存，以及設定您的共存和[升級](https://aka.ms/SkypeToTeams-SetCoexistence)設定來瞭解詳細資料。 我們也建議使用下列影片：[影片：管理 SfB](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)和 Teams 之間的共存和互通性

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Teams 和商務用 Skype 共存的技術詳細資料

下列各節摘要在同一組織中同時執行 Teams 和商務用 Skype 用戶端時可能遇到的行為，不論使用何種模式和升級方法：

- [會議](#meetings)
- [互 操作 性](#interoperability)
- [Teams 交談對話-Interop 與原生對話](#teams-conversations---interop-versus-native-threads)
- [目前狀態](#presence)
- [同盟](#federation)
- [連絡人](#contacts)



### <a name="meetings"></a>會議

無論使用者以何種模式，都能隨時加入他們受邀參與的任何類型會議，無論是商務用 Skype 或 Teams。  不過，使用者必須使用符合會議類型的對應用戶端加入會議：

- 如果會議是 Teams 會議，所有參與者 (TeamsOnly、Islands 或商務用 Skype 使用者，) 使用 Teams 用戶端加入會議。 如果未安裝 Teams，使用者嘗試加入會議時，會導向至網路。

- 如果會議是商務用 Skype 會議，則所有參與者 (無論是 TeamsOnly、Islands 或商務用 Skype 使用者) 請使用商務用 Skype 用戶端加入會議。 如果尚未安裝商務用 Skype 用戶端，使用者會透過 Skype 會議應用程式被導向至網路以加入。

組織會議時，排程的會議類型是根據召集人的模式，如下表所示：

| 召集人模式    |      行為 |
| :------------------ | :---------------- |
| TeamsOnly、SfbWithTeamsCollabAndMeetings |    在 Teams 中排程的所有會議。 Outlook 中未供應商務用 Skype 附加元件。 | 
| SfbWithTeamsCollab， SfbOnly   | 在商務用 Skype 中排程的所有會議。 Teams 外掛程式在 Outlook 中無法使用。 | 
| 離島 | 根據預設，會議可以在商務用 Skype 或 Teams 中排程。 這兩個附加元件在 Outlook 中都可用。 不過，您可以選擇性地要求群島中的使用者一直在 Teams 中排程會議，方法為他們指派一個使用 PreferredMeetingProviderForislandsMode=Teams 的 TeamsMeetingPolicy 實例。| 


### <a name="interoperability"></a>互 操作 性

如上述 Teams 和商務用 [Skype](#interoperability-of-teams-and-skype-for-business)的互通性所述，Teams 支援在某些情況下與商務用 Skype 進行互動。 交互操作通訊是指商務用 Skype 使用者與 Teams 使用者之間的聊天或通話。  只有兩個使用者之間才能進行交互操作通訊;不支援多方聊天/通話或新增其他使用者。

當下列各為 True 時，會建立兩個使用者之間的交互操作聊天或通話：

- 一個使用者正在使用 Teams，另一個使用者則使用商務用 Skype。

- 初始通訊的收件者模式為 NOT Islands (否則如果兩個使用者都在同一個組織中，該通訊會位於同一個用戶端) 。 在聯盟情況下，傳送使用者使用的是 Teams，而收件者不是在 TeamsOnly 模式。 

- Teams 使用者沒有內部部署商務用 Skype 帳戶。

在交互操作通訊中，聊天為純文字。 此外，在交互操作聊天本身中無法共用檔案 *和螢幕畫面*。 不過，在交互操作交談中的使用者，只要在交互操作聊天中建立會議，就可以輕鬆達成檔案和/或螢幕畫面共用，如下所述：

- 如果 Teams 使用者嘗試共用其螢幕畫面，系統會自動建立一個 Teams 邀請會議，然後該會議的邀請連結會送到商務用 Skype 使用者的用戶端。 按一下連結後，商務用 Skype 使用者就會開啟 Teams 並加入會議。 這兩個使用者現在都參與 Teams 會議，而且可以根據需要共用。

- 如果商務用 Skype 使用者使用的是 2018 或更新的用戶端，並嘗試共用任何內容，系統會自動建立商務用 Skype 會議，並且會向 Teams 使用者的用戶端發送該會議的邀請連結。 按一下連結後，Teams 使用者將嘗試加入商務用 Skype 會議。 如果 Teams 使用者已安裝商務用 Skype 用戶端，系統會開啟該用戶端，並提示使用者 (尚未) 。  如果 Teams 使用者未安裝商務用 Skype 用戶端，系統會提示使用者使用網頁版。 兩個使用者一旦都一旦簽署後，即會參與商務用 Skype 會議，並可以根據需要共用。

### <a name="teams-conversation-threads---interop-versus-native-threads"></a>Teams 交談對話 - 交互操作與原生對話

由於交互操作通訊並不支援原生 Teams 交談的所有功能，因此 Teams 用戶端會針對 Teams-to-Teams 和 Teams-to-Skype 商務用通訊維護個別的交談對話。 這些交談在使用者介面中的呈現方式不同：Interop 執行緒可以與一般原生 Teams 執行緒區別：：

- 對豐富的文字、檔案/螢幕畫面分享沒有控制，無法新增使用者。
- 對目標使用者的圖示進行修改，顯示商務用 Skype 的 「S」。

這些差異會顯示在下列螢幕擷取畫面中：

使用使用者 G3 測試進行原生 Teams 對 Teams 交談

![顯示原生 Teams 對 Teams 交談的圖表](media/teams-upgrade-native-thread.png)

使用相同使用者 G3 測試的交互操作交談

![顯示 Teams 對 Teams 交談的圖表](media/teams-upgrade-interop-thread.png)

交談對話建立後，其類型永遠不會變更。 建立之後，Teams 中的交互操作執行緒一定會路由到目標使用者的商務用 Skype 用戶端。 原生執行緒一定會路由至目標使用者的 Teams 用戶端。  如果收件者使用者的模式變更，該使用者的現有 Teams 對話將不再運作，該聊天上會顯示記事，並包含開始新原生交談的連結，如下列螢幕擷取畫面所示。

![顯示已升級商務用 Skype 使用者的聊天圖表](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>目前狀態

使用者目前狀態是根據使用者透過用戶端在服務中的活動。 接著會發佈目前狀態，讓其他使用者看到。  商務用 Skype 和 Teams 是具有個別用戶端的個別服務，因此每一項服務都有使用者自己的目前狀態。   Teams 和商務用 Skype Online 中的目前狀態服務也有同步處理。  這可讓一個服務可能于需要時發佈來自另一個服務之使用者的目前狀態。 

目前狀態發佈行為是根據使用者的模式。 有三種基本案例：

- 如果使用者使用 TeamsOnly 模式，無論該使用者使用哪個用戶端，所有其他使用者都會看到該使用者的 Teams 目前狀態。

- 如果使用者在任何商務用 Skype 模式中，所有其他使用者都會看到該使用者的商務用 Skype 目前狀態，無論該使用者使用哪個用戶端。

- 如果使用者是在群島模式，在商務用 Skype 和 Teams 中發佈的目前狀態是獨立的，因此向同一組織的使用者顯示目前狀態取決於其他使用者的用戶端。 由於以群島模式使用者為聯盟流量的群島使用者位於商務用 Skype 中，因此，在聯盟組織中使用者會看到該使用者的目前狀態，其狀態取決於他們的商務用 Skype 活動。

例如，假設使用者 A 為群島模式。 如果使用者 A 在 Teams 中為使用中狀態，但並未使用商務用 Skype，其他使用者會看到使用者 A 從 Teams 用戶端處於使用中狀態，但在商務用 Skype 用戶端中，會看到使用者 A 處於離線狀態。 這是根據設計，因為如果沒有執行用戶端，就無法與使用者 A 聯繫。 


### <a name="federation"></a>同盟

使用商務用 Skype 將 Teams 與其他使用者進行連線時，Teams 使用者必須連線到商務用 Skype。 TeamsUpgradePolicy 會控制內聯聊天和通話的路由。 除了在群島模式中，聯合路由行為與同一租使用者案例相同。 當收件者位於群島模式時：

- 如果收件者位於聯盟租使用者中，則從 Teams 啟動的聊天和通話會位於商務用 Skype 中。
- 如果收件者位於相同的租使用者中，則從 Teams 啟動的聊天和通話會位於 Teams 中。
- 從商務用 Skype 啟動的聊天和通話一直位於商務用 Skype 中。

聯盟聊天可以是原生對話或交互操作對話。 請參閱 [Teams 交談---對原生對話](#teams-conversations---interop-versus-native-threads)。

- 如果收件者與寄件者都同時在 TeamsOnly 升級模式中，交談就會是包含所有豐富訊息和通話功能的原生聊天體驗。 若要深入瞭解，請閱讀 Teams 中外部 [ (的原生) 聊天體驗](native-chat-for-external-users.md)。 

- 如果任一交談參與者未處於 TeamsOnly 升級模式，交談會維持純文字訊息的交互操作體驗。 使用者介面會以類似相同租使用者交互操作執行緒的方式公開聯合聊天，只是有附注指出使用者是外部使用者。

詳情請參閱在 Teams 中管理 [Microsoft Teams](manage-external-access.md) 中的外部存取和外部 ([的原生) 體驗](native-chat-for-external-users.md)。

### <a name="contacts"></a>連絡人

Teams 和商務用 Skype 有個別的連絡人清單。 這表示在一個系統中新增、移除和修改的連絡人不會同步處理至另一個系統。 不過，當發生兩種特定事件之一時，商務用 Skype 的連絡人會自動複製到 Teams： 

- 對於任何商務用 Skype Online 使用者，他們第一次登入 Teams 時，會從商務用 Skype 將連絡人複製到 Teams。  在商務用 Skype Server 中擁有內部部署帳戶的使用者無法執行此行為。  

- 使用者升級至 TeamsOnly (後，無論是透過指派 TeamsUpgradePolicy 或透過 Move-CsUser -MoveToTeams) ，下次使用者登入 Teams 時，商務用 Skype 中的現有連絡人將會與 Teams 中現有的連絡人合併。 不論使用者的商務用 Skype 帳戶位於內部部署或線上，都會發生此行為。 

在這兩種情況下，將連絡人從商務用 Skype 移轉至 Teams 是非同步，因此連絡人可能需要幾分鐘的時間，才能出現在 Teams 中。 上述兩個事件會觸發複製。  

### <a name="related-links"></a>相關連結

[適用于將 Teams 與商務用 Skype 一起使用的組織之移移和互通性指南](migration-interop-guidance-for-teams-with-skype.md) 

[設定商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用會議移 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

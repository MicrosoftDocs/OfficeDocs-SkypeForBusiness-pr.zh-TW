---
title: 商務用 Skype 與 Microsoft Teams 之間的互通性
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
ms.openlocfilehash: ea8c313d74829c00532fa3310657879f94dc2e5d
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196427"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>瞭解 Microsoft Teams 和商務用 Skype 共存與互通性

![升級歷程圖，強調專案定義階段](media/upgrade-banner-project-definition.png "升級階段，強調專案定義階段")

本文是升級過程中專案定義階段的一部分，此階段是在建立贊助贊助小組和專案小組，並定義專案的範圍、目標及願景後完成的活動。 繼續進行之前，請確認您已完成下列活動：

- [已招募專案專案關係人](upgrade-enlist-stakeholders.md)
- [已定義您的專案範圍](https://aka.ms/SkypetoTeams-Scope)

如果貴組織今天使用商務用 Skype，而您正開始將 Teams 與商務用 Skype 同時使用，或者您正開始升級至 Teams，瞭解這兩個應用程式如何並存、何時及如何交互操作，以及如何管理使用者的移移，從商務用 Skype 升級至 Teams，非常重要。

> [!Tip]
> 觀看下列會話以瞭解 [共存和互通性](https://aka.ms/teams-upgrade-coexistence-interop)。
>
> 此外，您可以與我們一起參與即時互動式研討會，我們會在這裡分享指導、最佳做法和資源，這些工作旨在開始規劃及實作升級。
>
> 首先 [加入規劃升級](https://aka.ms/SkypeToTeamsPlanning) 會話以開始使用。

## <a name="coexistence-of-teams-and-skype-for-business"></a>Teams 和商務用 Skype 共存

除了共同合作功能之外，Teams 也提供聊天、通話和會議功能。 視您選擇部署 Teams 的方式不同，這些功能可能會與商務用 Skype 為使用者提供的功能重迭。 預設模式是同時使用功能重迭的商務用 Skype 來執行 Teams;不過，使用者可以被指派幾個共存模式 (又稱為升級模式) 之一，其設計目的是確保這些功能不會與該使用者重迭 (在這種情況下，可以使用 Teams 和商務用 Skype 之間的互通性) 。 例如，如果您的商務用 Skype Server 內部部署具有複雜的企業語音部署，但希望使用者儘快享受新式會議，您可能會想要評估會議為替代路徑。 [](meetings-first.md)

建議您查看下列共存模式，協助判斷適合貴組織的路徑。

> [!Important]
> 引進新的技術或變更您現有、熟悉的商務用 Skype 環境，同時提供全新的商業優點，可能會干擾使用者。 在您執行本文所述的任何變更之前，請花一些時間評估使用者的備戰能力，並實行通訊和訓練計畫。 此外，我們強烈建議您先與選取的使用者群組試驗您的計畫，再在整個組織中執行。

### <a name="islands-mode"></a>群島模式

根據預設，使用者可以將 Teams 與商務用 Skype 同時執行，做為兩個獨立的解決方案，提供類似和重迭的功能，例如目前狀態、聊天、通話和會議。 Teams 使用者也可以利用新的共同合作功能，例如團隊和頻道、存取 Microsoft 365 或 Office 365 中的檔案，以及應用程式。

在這個稱為 **群島** 的共存模式中，每個用戶端應用程式會以個別的島嶼方式運作。 商務用 Skype 與商務用 Skype 交談，Teams 與 Teams 交談。 使用者預期會一併執行這兩個用戶端，而且可以在啟動通訊的用戶端內進行原生通訊。 因此，在群島模式中 **不需要互通性。**

為了避免造成混淆或倒退的商務用 Skype 體驗，外部 (聯盟) 通訊、PSTN 語音服務和語音應用程式、Office 整合、USB 裝置之 HID 控制項，以及數個其他整合，繼續由商務用 Skype 處理，且在 Teams 中不適用於 **群島** 模式。 在群島模式中，Teams **不支援電話系統** ;在此模式中，唯一的企業語音用戶端是商務用 Skype。

> [!Important]
> 在 **群島** 模式中，所有來自貴組織外部 (使用者的訊息和通話) 傳送到商務用 Skype。 升級到 Teams **模式** 之後，組織外部的所有訊息和通話會傳送至 Teams。

> [!Tip]
> 商務用 Skype Online 客戶的建議路徑是，從預設 **群島** 模式開始、推動 Teams 在組織中採用飽和度，然後快速移至 **Teams 僅** 模式。 內部部署和混合式客戶 ，尤其是複雜的客戶，可能從部署商務用 Skype 與 **Teams** 共同合作模式做為起點，而不是以群島模式為起點，以及從該模式到商務用 Skype 與 **Teams** 共同合作與會議模式 (也就是說，會議第一) ，以及當組織準備好採用 Teams 時，則採用 **Teams** 模式。。

### <a name="teams-only"></a>僅 Teams

Teams **使用者** (升級 *的使用者，)* Teams 中所有功能的存取權限。 他們可以保留商務用 Skype 用戶端，以加入由未升級的使用者或外部方所組織的商務用 Skype 會議。 升級的使用者可以使用 Teams 和商務用 Skype (之間的互通性功能，繼續與組織中仍在使用商務用 Skype 的其他使用者通訊 (但這些商務用 Skype 使用者不處於 **群島** 模式) 。 不過，升級的使用者無法啟動商務用 Skype 聊天、通話或會議。

一旦貴組織準備好讓部分或所有使用者使用 Teams 作為他們唯一的通訊和共同處理工具，您可以將這些使用者升級至 **Teams 僅模式** 。 如果您是從群島模式升級，建議您在開始升級程式之前，先將 Teams 的採用時間飽和至整個組織。 這可避免因群島模式未提供互通性而中斷通訊案例。

在 Teams **模式** 時，Teams 是 SIP/Tel 通訊協定的預設應用程式。 這表示在 Outlook 中，使用者連絡人卡片中用於通話或聊天的連結將由 Teams 處理。

有關移往 **Teams** 模式的其他考慮，請參閱 [Teams 僅模式考慮](teams-only-mode-considerations.md)。

![Teams 確認訊息的螢幕擷取畫面](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "在使用者升級為 Teams 專用使用者之後，以特殊模式執行商務用 Skype 用戶端")

### <a name="skype-for-business-only"></a>僅商務用 Skype

在這個共存模式中，使用者會保留在商務用 Skype 中，而非 Teams 中，以用於聊天、會議及通話功能，而且不會將 Teams 用於團隊和頻道。 此模式目前提供;不過，在目前的執行中，使用者不會自動關閉團隊和頻道。 若要達成此目標，可以使用應用程式設定政策來隱藏團隊和檔案。

在開始 Teams 受管理部署之前，可以使用此模式來防止使用者先使用 Teams，再進行內建的備修，或讓使用者獲得 Teams 授權，以啟用已驗證參與商務用 Skype 使用者的 Teams 會議。

### <a name="skype-for-business-with-teams-collaboration"></a>使用 Teams 共同處理商務用 Skype

使用此模式在繼續運用您現有的商務用 Skype 投資的同時，在環境中引進 Teams。 在這個模式中，商務用 Skype 在聊天、通話和會議功能上維持不變，並新增 Teams 共同合作功能 —團隊和頻道、存取 Microsoft 365 或 Office 365 中的檔案，以及應用程式。 在此模式中，Teams 通訊功能 -私人聊天、通話和排程會議預設為關閉。

從內部部署或混合式商務用 Skype Server 開始著手的組織，若想讓使用者在通訊方面具備互通性和可預測性，以及擁有可預測的升級到 Teams (的時程表，而非仰賴在群島模式) 中的採用飽和度，則應考慮此模式作為群島模式的替代模式。 

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>商務用 Skype 與 Teams 共同合作與會議，也稱為會議第一

使用此共存模式可加速貴組織中 Teams 會議功能的可用性，除了其共同合作功能之外，還能夠讓使用者充分利用超強的 Teams 會議體驗，品質超好、創新功能 ，例如文字抄寫和翻譯或背景模糊，以及跨所有平臺的超強使用者體驗，包括行動裝置和瀏覽器。

除了在此模式中使用 Teams 進行團隊和頻道型交談，使用者將使用 Teams 排程和召開會議。 私人聊天和通話保留在商務用 Skype 上。 Teams 和商務用 Skype 受益于各種「一起改善」功能，例如目前狀態對帳、自動保留/取消保留，以及這兩種應用程式的 HID 裝置支援。 請注意，如果需要，使用應用程式設定政策可以隱藏團隊和頻道。

這個共存模式對於使用企業語音進行商務用 Skype 內部部署的組織特別有用，因為組織可能需要一些時間升級至 Teams，並想要儘快從高超的 Teams 會議獲益。

> [!TIP]
> 若要在商務用 Skype 仍在使用中時，根據您想要在 Teams 中啟用的功能，協助識別建議的升級模式，請使用 [Skype 到 Teams](https://aka.ms/SkypeToTeamsWizard)升級精靈。

有關共存模式、先決條件和管理的更多詳細資料，請參閱使用 Teams 與商務用 [Skype](https://aka.ms/SkypeToTeams-Interop) 以及設定您的共存和升級設定的組織移移和互通性 [指南](https://aka.ms/SkypeToTeams-SetCoexistence)。

| | | |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|決策點|<ul><li>哪一種 () 最適合貴組織及使用者的需求？</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|後續步驟|<ul><li>選擇升級過程的最佳方式。</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>Teams 和商務用 Skype 的互通性

互通性是同一個組織中 Teams 和商務用 Skype 使用者跨 Teams 和商務用 Skype 進行通訊的能力。

互通性是由共存模式 (，也稱為收) 的升級模式。 當收聽者位於群島模式時，沒有 **互通性** 。

> [!Note]
> 當部署在群島以外的任何共存模式中時，Teams 和商務用 Skype[](#interoperability-of-teams-and-skype-for-business)可以交互操作，讓使用者可以彼此聊天和通話，並確保在升級 Teams 過程中，整個組織的通訊保持流暢。 共存模式可規範互通性。 收受者共存模式會決定是否提供互通性。 例如，如果接收者是在一個用戶端中僅提供聊天的模式中 (例如 Teams) ，當啟動程式使用另一個用戶端 (在此案例中，商務用 Skype) 啟動聊天時，一般會提供聊天互通性。 另一方面，如果收受者是在兩個用戶端 (Islands 模式) 中均提供聊天的模式，則聊天將無法提供互通性。 在啟動器開始聊天的同一個用戶端中，接收者將會收到訊息。 因此，在群島模式中進行 **適當的** 通訊需要 Teams 採用飽和度;也就是說，所有使用者都是主動使用及監控這兩個用戶端。

> [!Note]
> **若要擁有最新的共存體驗，用戶端版本必須是使用者 Office 部署通道中的最新可用用戶端。**

### <a name="native-interop-and-interop-escalation"></a>原生交互操作和交互操作升級

交互操作體驗有兩種類型：原生和交互操作升級。

- 使用者 _目前_ 使用的用戶端會發生原生的交互操作體驗。 其中一個使用者會使用商務用 Skype 用戶端，另一個使用者則位在 Teams 中。 原生的交互操作體驗不會帶他們到另一個用戶端進行通訊，使用者將能夠在他們目前使用的用戶端中進行交談。 原生的交互操作體驗是一對一聊天和通話。
- 相互 _升級_ 體驗表示，做為協助使用者執行進一步動作 (例如共用桌面) 的一部分，用戶端可協助建立一個使用者可以加入的會議，以在會議中繼續體驗。 會議是在動作啟動者平臺上建立。 不在該平臺的使用者會收到會議加入連結。 當他們按一下這個連結時，他們會在相容的用戶端 (瀏覽器、Web App 或完整用戶端加入會議，視組) 。 商務用 Skype 的相互升級需要最近使用的客戶。 Teams 的相互升級現已提供。 兩者在租使用者中的互通性體驗以及跨租使用者之間的聯合通訊都受到支援。

### <a name="native-interop-experiences"></a>原生交互操作體驗

根據先前所述指派給使用者的共存模式 (，) 提供下列原生交互操作體驗：

商務用 Skype 使用者可以與 Teams 使用者進行一對一交談，反之亦然。 交互操作聊天需要透過 Teams 雲端服務網內一部分的交互操作閘道 (因此僅存在於線上) 。 交互操作聊天是純文字：不支援豐富的文字和圖釋。 Teams 和商務用 Skype 中的使用者會收到交談是交互操作交談的通知。

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

商務用 Skype 使用者可以對 Teams 使用者進行一對一語音和視音訊通話，反之亦然。

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> 內部部署商務用 Skype 的交互操作體驗需要內部部署環境與 Microsoft 365 或 Office 365 商務用 Skype 採用混合模式。 有關詳細資料，請參閱 [移移和互通性指南](https://aka.ms/SkypeToTeams-Interop)。

這些交互操作體驗可供指派下列其中一種共存模式的使用者之間使用：商務用 **Skype with Teams 共同** 合作、商務用 Skype with Teams **共同** 合作和會議、商務用 **Skype** 或 **Teams。** 在群島模式中，使用者 **之間沒有互通性** 。

### <a name="native-interop-experience-limitations"></a>原生交互操作體驗限制

由於通訊協定與技術的差異，因此無法原生支援所有功能。 具體來說，下列功能無法提供：

- Teams 或商務用 Skype 不支援 Markdown、豐富文字和完整的圖釋集。 不支援 Teams 聊天中撰寫方塊的其他原生功能。
- 在 Teams (商務用 Skype 之間) 桌面或應用程式的螢幕畫面分享功能並不支援。 不過，透過相互升級支援。
- 群組聊天 (Teams 中的) 交談只能包含使用 Teams 的參與者。
- 商務用 Skype (群組聊天) 方 IM 交談只能包含使用商務用 Skype 的參與者。 不過，商務用 Skype 提供多方服務升級功能。
- 不支援將進行中的對等語音或視音訊通話升級為涉及 Teams 和商務用 Skype 使用者的多方通話。
- 不支援雙方聊天的檔案傳輸，或群組聊天中的檔案附件，從 Teams 傳輸至商務用 Skype，反之亦然。
- 商務用 Skype 的持續性聊天沒有互通性。

針對這些限制 (長聊天) ，其中一個可能的解決方法是讓一個使用者啟動會議並邀請其他使用者加入會議。

此解決方法是相互升級的基礎。 特別是，螢幕畫面分享和向多方升級無法原生地達成，但會透過相互升級支援。

### <a name="interop-escalation-experiences"></a>相互升級體驗

交互操作升級包含以受管理的升級至會議來補充原生交互操作功能。 會議提供豐富的體驗給任何人，無論他們擁有哪一個用戶端。

當 Teams 使用者觸發交互操作升級時，即會建立 Teams 會議。 當商務用 Skype 使用者觸發會議時，會建立商務用 Skype 會議。 在這兩種情況下，所建立的會議都是一場即開會的會議，不會反映在使用者的日曆上。
 
另一方會透過交互操作聊天收到會議加入連結，然後按一下該連結即可加入。 如果商務用 Skype 使用者有 Teams 帳戶，且由 Teams 使用者邀請，他們將加入已驗證的會議。 否則，他們將以匿名參與者的加入。 相反地，Teams 使用者幾乎一定都有商務用 Skype 帳戶和商務用 Skype 用戶端，他們可以使用經驗證的參與者加入商務用 Skype 會議，但他們也可能以匿名參與者的名加入，例如使用 Skype 會議應用程式。

當各方加入會議後，他們可以進行會議支援的任何活動，例如桌面或內容共用、檔案共用或傳輸、新增其他參與者等等。

#### <a name="interop-escalation-from-skype-for-business"></a>商務用 Skype 的相互升級

在 2019 年 7 月每月 C2R 的建立中更新了商務用 Skype 的交互操作和交互操作升級。 之前，商務用 Skype 並未事先知道遠端派對正在使用 Teams。 它只能從會話建立後收到的訊號中猜測。

當訊號指出回應來自 (或透過) 交互操作閘道時，它會顯示黃色商業橫條 (橫幅) 表示另一方並未使用商務用 Skype。 隨著我們的服務變革，這導致誤誤，商務用 Skype 使用者在連接至雲端語音信箱服務或其他雲端語音服務時，會看到商務用 Skype，而不是實際 **只有 Teams 的使用者** 。
 
為了避免這些誤誤，當另一方是 Teams 實際使用者時，目前狀態服務現在會通知商務用Skype 用戶端。 這可讓商務用 Skype 在建立前先建立交互操作交談，而且交談視窗必須特別針對交互操作進行。

![Teams 訊息與商務用 Skype 使用者建立交互操作交談的螢幕擷取畫面](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

例如，如果商務用 Skype 使用者想要共用桌面，會通知他們我們將開始會議，並引導您完成步驟。

![Teams 訊息開始與 Teams 使用者開會的螢幕擷取畫面](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

同時，Teams 使用者會收到包含會議連結的傳入聊天訊息，並引導您加入。

這種升級為商務用 Skype 會議，適用于租使用者內交互操作和跨租使用者聯盟通話和聊天。 此設定預設為啟用，且系統管理員無需進行任何設定。

#### <a name="interop-escalation-from-teams"></a>Teams 的相互升級

Teams 使用者現在可在租使用者間交互操作對話中選取桌面共用按鈕時，從 Teams 升級至 Teams 會議，或是跨租使用者交互操作聯盟執行緒。 1 對 1 聊天交談或 1 對 1 通話支援交互操作升級。

此功能支援 Windows 版 Teams 桌面用戶端、Mac 版 Teams 桌面用戶端，以及支援內容共用的瀏覽器上的 Teams Web 用戶端，同時可與任何商務用 Skype 用戶端版本進行通訊。

在互通性執行緒和聯合互通性執行緒中，Teams 使用者現在擁有 (按鈕) 開始內容共用。 當 Teams 使用者選取按鈕時，他們看到一個額外的功能表，通知他們若要共用內容，他們需要啟動 Teams 會議。

如果使用者在通話中，功能表也會警告使用者，當他們進入 Teams 會議時，他們目前在 Teams 和商務用 Skype 之間的通話將會終止。 如果他們選擇這麼做，可以在接受之前警告商務用 Skype 使用者。

![與商務用 Skype 使用者共用會議之 Teams 訊息的螢幕擷取畫面](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

接受之後，這些會議會進入 Teams 會議;他們必須從會議中的共用系統系統開始共用。
 
同時，商務用 Skype 使用者會收到包含會議連結的傳入聊天訊息，並引導您加入。

此 Teams 會議升級為租使用者間交互操作和跨租使用者聯盟通話和聊天。 此設定預設為啟用，且系統管理員無需進行任何設定。 不過，如果系統管理員設定為 .，則使用者已關閉 ``-AllowPrivateMeetNow`` ``CsTeamsMeetingPolicy`` ``$false`` 此設定。

在您閱讀本文之後，請參閱選擇[](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)您的升級旅程、移移和互通性[指引](https://aka.ms/SkypeToTeams-Interop)、與商務用[Skype](coexistence-chat-calls-presence.md)共存，以及設定您的共存和[升級](https://aka.ms/SkypeToTeams-SetCoexistence)設定來瞭解詳細資料。

## <a name="related-links"></a>相關連結

[影片：管理 SfB 和 Teams 之間的共存和互通性](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

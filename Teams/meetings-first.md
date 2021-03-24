---
title: 會議第一次 - Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: lsomi
description: 瞭解會議第一步，使用者可以在 Teams 中建立會議，同時繼續使用商務用 Skype 聊天、通話和目前狀態。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b691a9d722a82e68384f8937479c5f71d3f4c11d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096167"
---
# <a name="meetings-first"></a>會議優先

「會議第一」是專為商務用 Skype Server 組織所設計，並針對想要儘快開始使用 Teams 會議的企業語音內部部署組織優化。 對於這類組織，會議優先是使用 **以 Teams** 會議體驗為優先順序的群島模式的替代方式。

## <a name="what-is-meetings-first"></a>什麼是會議第一個？

會議第一個是以 **SfBWithTeamsCollabAndMeetings** 共存模式為基礎。 會議第一步不是產品或功能，而是使用 Teams 和商務用 Skype 的功能與功能來提供唯一量身打造的共存體驗的組組。

在會議第一部中，使用者在 Teams 中建立會議，同時繼續使用商務用 Skype 進行聊天、通話和目前狀態。 Teams 與商務用 Skype 之間的模式沒有重迭。 商務用 Skype 中的聊天、通話和目前狀態均在 Teams 中，而 Teams 則為關閉狀態。 這可讓商務用 Skype 和 Teams 之間獨特的「共同合作」案例，提升使用者在共存期間的體驗，以及與 **Teams Only** 使用者的互通性案例。

![Teams 和商務用 Skype 的更好結合案例的螢幕擷取畫面](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> 會議 第一個比對沒有或幾個作用中 Teams 聊天使用者的組織。 使用中的 Teams 聊天使用者不應該切換到會議第一模式，因為他們會失去在 Teams 中聊天及存取其聊天記錄的能力。 這些使用者應該改為以 **群島** 模式進行，而會議第一次只授予尚未在 Teams 中聊天的使用者。

## <a name="who-should-consider-meetings-first"></a>誰應該先考慮會議？

會議第一次是專為使用商務用 Skype Server 與企業語音的組織所設計，這些組織想要加速移至 Teams 會議，尤其是具有強大 IT 規範的組織，想要以受管理、確定式升級路徑的方式移至 Teams。

對於複雜或大型組織，語音移移通常是以網站為基礎進行，而且可能需要很長的時間，可能花上數年的時間，導致延長共存案例。 如果該共存是在 **群島** 模式中，使用者一定會選擇兩種會議解決方案 ， (商務用 Skype 和 Teams) ，這可能會導致混淆或次優狀況。 與語音移移不同的是，會議移移通常可以在很短的時間內完成整個公司。 想要儘快完全切換到 Teams 會議 (且不需要等待語音移轉完成，) 應考慮會議。

會議第一個可能對於沒有企業語音使用者的組織沒有説明。 這些組織一旦能夠採用 **Teams** 會議，就應能升級至 Teams。 他們應該考慮先略過會議。

此外，「會議第一」對於其範圍為純播放會議解決方案的組織而言，例如發行「僅會議」RFP 時，會很有用。

## <a name="capabilities-in-meetings-first"></a>會議第一個功能

會議第一次將下列功能彙集在一起：

- [使用 Teams 音訊會議](./tutorial-audio-conferencing.yml?tutorial-step=3) (內部) 商務用[Skype Server。](tutorial-audio-conferencing.yml)
- [會議移轉服務](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)：使用者組織的會議會移轉至雲端，並轉換成 Teams 會議，因為使用者升級為會議 (需要 Exchange Online) 。
- 在 Teams 中簡化使用者體驗，以 Teams 會議和團隊和頻道為中心 (選擇使用 [應用程式](teams-app-permission-policies.md) 許可權政策選項隱藏這些) ; [Teams 私人聊天、通話](teams-client-experience-and-conformance-to-coexistence-modes.md) 和自我目前狀態不會在會議第一次中公開，因此部署和採用工作可以完全專注于會議。
- 高 [超 Teams 會議體驗](tutorial-meetings-in-teams.yml)。
- Teams 與商務用 Skype 之間的「共同合作」： 
  - 自動保留：在 Teams 中開會時，在商務用 Skype 中加入通話會保留 Teams 會議，反之亦然。 這可防止使用者被會議參與者聽到他們的私人通話。
    ![Teams 和商務用 Skype 的更好結合案例的螢幕擷取畫面](media/meetings-first-better-together-hold.png)
  - 目前狀態對帳：Teams 中的活動會反映在使用者的目前狀態中，即商務用 Skype 目前狀態，因為聊天和通話是在商務用 Skype 中。 具體來說，當會議第一位使用者參與 Teams 會議時，其目前狀態將會更新以反映這一點。 當他們展示螢幕時，他們的目前狀態將會更新， (商務用 Skype 中的設定來顯示請勿打擾) 。
  - MAC (也提供 USB 裝置 HID 控制項對帳) ：Teams 在 Teams 會議中以及商務用 Skype 在所有其他情況下，均會遵守 HID 控制項。
  - 除非另有提及，否則更好的共同功能目前需要最新的 Windows 桌面用戶端。

## <a name="prerequisites-for-meetings-first"></a>會議第一個先決條件

會議第一次的唯一硬性需求與擁有內部部署 Active Directory 和商務用 Skype 內部部署之 Teams 的需求相同：

- [Teams 的一般先決條件](upgrade-plan-journey-prerequisites.md)，包括
- [Teams 和中的身分](identify-models-authentication.md) 識別與驗證
- [設定 Teams 和商務用 Skype 的 Azure Active Directory](/skypeforbusiness/hybrid/configure-azure-ad-connect)。

不需要 [商務用 Skype 混合](/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) 式拓撲，但建議使用。 某些功能 ，例如會議移移服務和互通性，仰賴該拓撲。

會議第一版支援任何版本的商務用 Skype Server (且已知可與不再支援的 Lync Server) 。 任何支援的商務用 Skype 用戶端都支援此功能，不過更好的共同功能需要最近的用戶端。

一旦符合這些 (且未事先) ，使用者就可以獲得 [Microsoft 365 或 Office 365](/office365/enterprise/assign-licenses-to-user-accounts)和 Teams 授權。

為了獲得最佳的會議第一體驗，使用者應啟用 [Exchange Online、SharePoint](exchange-teams-interact.md)Online 和商務用 [OneDrive，](sharepoint-onedrive-interact.md)以及 Microsoft 365 群組建立。 對於信箱位於 Exchange 內部部署，或沒有 SharePoint Online 或商務用 OneDrive，或 Microsoft 365 群組建立的使用者，支援 [會議第一個）。 不過，他們的體驗會不太完整。 特別是對於使用 Exchange Server 內部部署的組織，根據 Exchange Server) 版本，從 Teams 用戶端建立和檢視會議，以及合規性功能方面，可能有 (個限制。

使用者至少必須獲得 [Teams 授權](/microsoft-365/admin/manage/assign-licenses-to-users)。 此外，如有必要，他們可以獲得音訊 [會議](set-up-audio-conferencing-in-teams.md)授權。

我們建議您在授權使用者時，將 [**SfBOnly** 或 **SfBWithTeamsCollab**](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)模式作為租使用者預設模式。 這可確保在準備好啟動會議前，使用者不會在預設 **群島** 模式中自行開始使用 Teams。

Windows 和 Mac (、瀏覽器用戶端) 行動用戶端上支援會議第一個。 它也與 Microsoft [Teams 會議室相容](/microsoftteams/room-systems/)。 "共同改善」需要完整的桌面用戶端。

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>在會議中先準備 Teams 會議

若要讓使用者在 Teams 會議中獲得最佳體驗，您應該：

- 請特別按照 [Microsoft Teams](deploy-meetings-microsoft-teams-landing-page.md)的會議和會議中的步驟進行。
- [評估您的環境](3-envision-evaluate-my-environment.md)。
- [準備貴組織的 Microsoft Teams 網路](prepare-network.md)。
- 使用 Teams 的會議室裝置[](/skypeforbusiness/certification/devices-meeting-rooms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)和解決方案升級您的會議室，或使用[Microsoft Teams](cloud-video-interop.md)的雲端視像交互操作功能，讓現有的協力廠商會議室和裝置加入 Teams 會議。
- 為您的使用者配備 [經過認證的 USB 音訊和視音訊裝置](/skypeforbusiness/certification/devices-usb-devices?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)。
- 準備 [提高 Teams 會議認知度及採用度](adopt-microsoft-teams-landing-page.md)。
- [規劃您的服務管理](4-envision-plan-my-service-management.md)。
- 熟悉豐富的通話分析報告，以 [疑難排解通話品質不佳的問題](use-call-analytics-to-troubleshoot-poor-call-quality.md)。

您可以在此階段考慮進行適量量生產準備試驗。

## <a name="configure-users-for-meetings-first"></a>先設定會議使用者

一旦授權使用者，並準備組織進行 Teams 會議，現在該是讓使用者先開會的時間。 我們已輕鬆操作：單一設定可以全部執行！

會議第一中的所有功能和使用者體驗 ，包括 Teams 用戶端組組[](teams-client-experience-and-conformance-to-coexistence-modes.md)和使用者體驗的自動一致性、會議移移服務，以及更好的一起功能，都是在[Microsoft Teams](manage-teams-in-modern-portal.md)系統管理中心或[PowerShell](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)中授予使用者 (或使用者群組，[](setting-your-coexistence-and-upgrade-settings.md)或租使用者預設) 來加以配置。

![啟用會議第一個的系統管理員設定螢幕擷取畫面](media/teams-meeting-admin-settings.png)

您也可以選擇將 Teams 和 Channels 應用程式隱藏在使用者 Teams 用戶端的左側流覽中，以進一步將經驗集中到會議上，而使用應用程式權限原則可以 [達到此目的](teams-app-permission-policies.md)。

## <a name="reporting-and-call-analytics"></a>報告和通話分析

會議第一個會議中的 Teams 會議報告和通話分析與其他模式不同。

## <a name="related-links"></a>相關連結

在您閱讀本文之後，您可能會想要參閱選擇升級歷程[](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)、移移和互通性[](migration-interop-guidance-for-teams-with-skype.md)指南，以及與商務用[Skype](coexistence-chat-calls-presence.md)共存以進一步詳細資料。
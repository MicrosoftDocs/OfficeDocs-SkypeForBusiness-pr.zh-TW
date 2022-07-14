---
title: 會議第一次 - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: lsomi
description: 先瞭解會議：使用者可以在 Teams 中建立會議，同時繼續使用商務用 Skype進行聊天、通話和目前狀態。
ms.localizationpriority: medium
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
ms.openlocfilehash: 149a5a3e22a633ec4c889b68a91ac9c6db8e9f4b
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789778"
---
# <a name="meetings-first"></a>會議優先

「會議第一次」是針對商務用 Skype Server想要儘快開始使用 Teams 會議的內部部署企業語音組織進行優化。 針對這些組織，[會議優先] 是使用優先順序 Teams 會議體驗的 **島嶼** 模式的替代方案。

## <a name="what-is-meetings-first"></a>什麼是會議第一？

會議第一次是以 **SfBWithTeamsCollabAndMeetings** 共存模式為基礎。 會議首先不是產品或功能，它是使用 Teams 和 商務用 Skype 功能的設定，提供專為您量身打造的共存體驗。

在 [會議第一] 中，使用者會在 Teams 中建立會議，同時繼續使用商務用 Skype進行聊天、通話和目前狀態。 Teams 和 商務用 Skype 之間沒有重迭的模式。 在 Teams 中商務用 Skype和關閉聊天、通話和目前狀態。 這可在商務用 Skype和 Teams 之間啟用獨特的「更好」案例，以增強使用者在共存期間的體驗，以及與 **僅限 Teams** 使用者的互通性案例。

![使用 Teams 和 商務用 Skype 更好搭配案例的螢幕擷取畫面。](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> [會議第一] 比較適合沒有或少數作用中 Teams 聊天使用者的組織。 作用中的 Teams 聊天使用者不應該切換到 [會議第一] 模式，因為他們會失去在 Teams 中聊天和存取其聊天記錄的能力。 這些使用者應改為以 **群島** 模式行事，而 [會議第一] 僅授與尚未在 Teams 聊天中的使用者。

## <a name="who-should-consider-meetings-first"></a>誰應該先考慮會議？

會議第一個設計是專為使用商務用 Skype Server與企業語音想要加快移轉至 Teams 會議的組織所設計，尤其是具有強大 IT 分派且想要有管理、確定性升級路徑至 Teams 的組織。

對於複雜或大型組織而言，語音移轉通常是以網站為基礎完成，而且可能需要很長的時間，可能長達數年，因此會產生延伸共存案例。 如果共存是在 **群島** 模式中，使用者一律可以選擇兩個會議解決方案 (商務用 Skype和 Teams) ，這可能會造成混淆或小情況。 與語音移轉不同的是，整個公司的會議移轉通常可以在一小段時間內完成。 想要儘快完全切換到 Teams 會議的組織， (而不等待語音移轉完成，) 應考慮先開會。

[會議第一] 對於沒有企業語音使用者的組織可能沒有用處。 這些組織應該能夠在能夠採用 Teams 會議時立即升級至 **Teams** 。 他們應考慮先略過會議。

此外，如果組織的範圍純屬會議解決方案，例如發行「僅限會議」RFP 的組織，[會議第一] 也很有用。

## <a name="capabilities-in-meetings-first"></a>會議中的功能

會議第一次將下列功能結合在一起：

- 使用[Teams 音訊](tutorial-audio-conferencing.yml)[會議布建商務用 Skype Server (內部部署) 使用者](./tutorial-audio-conferencing.yml?tutorial-step=3)。
- [會議移轉服務](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)：由使用者召集的會議將會移轉到雲端，並在使用者升級為 [會議] 時轉換為 Teams 會議， (需要Exchange Online) 。
- 在 Teams 中簡化的使用者體驗，以 Teams 會議和團隊和頻道為中心， (使用 [[應用程式](teams-app-permission-policies.md) 許可權] 原則) 隱藏; [Teams 私人聊天、通話和自我目前狀態](teams-client-experience-and-conformance-to-coexistence-modes.md) 不會顯示在 [會議第一] 中，讓部署和採用工作能夠完全專注于會議。
- [超強 Teams 會議體驗](tutorial-meetings-in-teams.yml)。
- 在 Teams 和 商務用 Skype 之間「共同改進」： 
  - 自動保留：在 Teams 的會議中，在 商務用 Skype 中接聽電話會將 Teams 會議設為保留狀態，反之亦然。 這可防止會議參與者聽到他們的私人通話。
    ![使用 Teams 和 商務用 Skype 更好搭配案例的螢幕擷取畫面。](media/meetings-first-better-together-hold.png)
  - 目前狀態對帳：Teams 中的活動會反映在使用者的目前狀態中，這是聊天和通話商務用 Skype商務用 Skype目前狀態。 具體來說，當 「會議第一」使用者在 Teams 會議中時，他們的目前狀態將會更新以反映這一點。 當他們展示螢幕畫面時，他們的目前狀態會根據他們在 商務用 Skype) 中的設定更新為顯示 [請勿打擾 (]。
  - Mac) 也提供 USB 裝置 HID 控制項對帳 (：Teams 在 Teams 會議和在所有其他情況下商務用 Skype都可使用 HID 控制項。
  - 除非另有提及，否則目前需要較佳的 Windows 桌面用戶端功能。

## <a name="prerequisites-for-meetings-first"></a>會議的先決條件

第一次會議的唯一硬性需求，與具有內部部署的 Active Directory和商務用 Skype內部部署的 Teams 需求相同：

- [Teams 的一般先決條件](upgrade-plan-journey-prerequisites.md)，包括
- [Teams 中的身分識別與驗證](identify-models-authentication.md)
- [設定適用于 Teams 和 商務用 Skype 的 Azure Active Directory](/skypeforbusiness/hybrid/configure-azure-ad-connect)。

不需要[商務用 Skype混合式拓撲](/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online)，但建議使用。 會議移轉服務和互通性等一些功能仰賴該拓撲。

會議 第一版支援任何版本的商務用 Skype Server (，且已知可與不再支援的 Lync Server) 搭配使用。 任何支援的商務用 Skype用戶端都會支援此功能，不過「更好的共聚」功能需要最新的用戶端。

一旦符合這些需求 (而非先前) ，使用者就可以[獲得 Microsoft 365 或 Office 365 和 Teams 的授權](/office365/enterprise/assign-licenses-to-user-accounts)。

為獲得最佳的「會議第一次」體驗，使用者應啟用[Exchange Online](exchange-teams-interact.md)[、SharePoint Online 和 商務用 OneDrive](sharepoint-onedrive-interact.md)，以及建立 Microsoft 365 群組。 第一個會議適用于信箱位於 Exchange 內部部署，或沒有 SharePoint Online、商務用 OneDrive 或 Microsoft 365 群組建立的使用者。 不過，他們的體驗會較不完整。 特別是對於使用內部部署Exchange Server的組織，可能會 (視Exchange Server) 從 Teams 用戶端建立和檢視會議以及合規性功能的一些限制而定。

使用者至少必須獲得 [Teams 的授權](/microsoft-365/admin/manage/assign-licenses-to-users)。 此外，如有需要，也可以授權他們使用 [音訊會議](set-up-audio-conferencing-in-teams.md)。

我們建議您在授權使用者時，預設 [授與 **SfBOnly** 或 **SfBWithTeamsCollab**](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)模式為租使用者。 這可確保使用者在您準備好啟動 [會議優先] 之前，不會以預設的 **群島** 模式開始使用 Teams。

Windows 和 Mac) 、瀏覽器用戶端和行動用戶端都支援完整的桌面用戶端 (會議。 它也與[Microsoft Teams 會議室](/microsoftteams/room-systems/)相容。 更好的搭配使用需要完整的桌面用戶端。

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>在會議中先準備 Teams 會議

若要讓使用者在 Teams 會議中獲得最佳體驗，您應該：

- 請特別按照 [Microsoft Teams 的會議和會議](deploy-meetings-microsoft-teams-landing-page.md)中的步驟進行。
- [評估您的環境](3-envision-evaluate-my-environment.md)。
- [為 Microsoft Teams 準備貴組織的網路](prepare-network.md)。
- 使用 Teams 功能強大的 [會議室裝置和解決方案](/skypeforbusiness/certification/devices-meeting-rooms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)來升級您的會議室，或使用 [Microsoft Teams 的雲端視訊 Interop](cloud-video-interop.md) ，讓您現有的協力廠商會議室和裝置加入 Teams 會議。
- 使用 [認證的 USB 音訊和視訊裝置](/skypeforbusiness/certification/devices-usb-devices?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)來讓您的使用者擁有資格。
- 為[Teams 會議準備提高意識和採用。](adopt-microsoft-teams-landing-page.md)
- [規劃您的服務管理](4-envision-plan-my-service-management.md)。
- 熟悉豐富的通話分析報告， [以疑難排解不佳的通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)。

在此階段，您可以考慮執行中等規模生產準備試驗。

## <a name="configure-users-for-meetings-first"></a>設定使用者的會議第一

一旦您已授權使用者並準備您的組織進行 Teams 會議，就可以先為您的使用者啟用會議。 我們讓您輕鬆上手：單一設定就能全部完成！

會議第一中的所有功能和使用者體驗，包括 Teams 用戶端設定和[使用者體驗的自動符合性](teams-client-experience-and-conformance-to-coexistence-modes.md)、會議移轉服務，以及更好的共聚功能，都是透過在[Microsoft Teams](manage-teams-in-modern-portal.md)系統管理中心或使用[PowerShell](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)中，授與使用者 (或使用者預設) [SfBWithTeamsCollabAndMeetings 共存模式](setting-your-coexistence-and-upgrade-settings.md)所設定。

![啟用 [會議] 的系統管理員設定螢幕擷取畫面。](media/teams-meeting-admin-settings.png)

或者，如果您想要將 Teams 和 Channels 應用程式從使用者 Teams 用戶端的左側導覽中隱藏，以進一步將他們的經驗集中在會議上，這可透過使用 [應用程式設定原則](teams-app-setup-policies.md)來達成。

## <a name="reporting-and-call-analytics"></a>報告和通話分析

[會議] 中 Teams 會議的報告和通話分析功能與其他模式的狀態保持不變。

## <a name="related-links"></a>相關連結

檢閱本文之後，建議您參閱[選擇升級旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)、[移轉與互通性指導方針](migration-interop-guidance-for-teams-with-skype.md)，以及[與商務用 Skype共存以](coexistence-chat-calls-presence.md)取得進一步的詳細資料。

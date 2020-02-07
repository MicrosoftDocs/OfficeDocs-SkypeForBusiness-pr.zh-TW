---
title: Microsoft 團隊 |先進行會議
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: francoid
description: 首先瞭解會議，在這裡使用者可以在小組中建立會議，同時繼續使用商務用 Skype 進行聊天、通話和目前狀態。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 10321d02398c6c2b0ffc2143a9bafa406fbec637
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836453"
---
# <a name="meetings-first"></a>會議優先

「會議優先」是以企業語音內部部署為目標，並針對商務用 Skype 伺服器組織進行優化，且要盡可能快速地開始使用團隊會議。 對於這些組織而言，會議優先是使用 [**孤島**] 模式來排定小組會議體驗的替代方案。

## <a name="what-is-meetings-first"></a>什麼是會議優先？

[會議優先] 是以**SfBWithTeamsCollabAndMeetings**共存模式為基礎。 會議優先不是產品或功能，它是一種可利用團隊和商務用 Skype 功能來提供唯一量身定制的共存體驗的設定。

在會議優先中，使用者會在團隊中建立會議，同時繼續使用商務用 Skype 進行聊天、通話和目前狀態。 團隊與商務用 Skype 之間沒有形式的重迭。 [聊天]、[通話] 和 [目前狀態] 是在商務用 Skype 和小組中關閉。 這可讓商務用 Skype 與團隊在共存期間加強使用者體驗的功能，以及與**小組**使用者之間的互通性案例。

![在團隊和商務用 Skype 中更好搭配案例的螢幕擷取畫面](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> [會議優先] 是針對沒有或只有任何活躍團隊聊天使用者的組織提供較佳的相符。 作用中的團隊聊天使用者不應該切換為會議的第一種模式，因為他們將失去在團隊中聊天的功能，以及存取他們的聊天記錄。 這些使用者應該 grandfathered 為 [**孤島**] 模式，而且只有在小組中的 [聊天] 中，才會首先授與會議。

## <a name="who-should-consider-meetings-first"></a>誰應該先考慮會議？

[會議優先] 是針對使用商務用 Skype Server 的組織而設計的，他們想要加速其搬遷至團隊會議，尤其是那些想要讓團隊具備具確定性的功能更新途徑的企業語音。

針對複雜或大型組織而言，語音遷移通常是在網站的基礎上完成，可能需要花很長的時間，從而延長共存情況。 如果該共存處於**孤島**模式，使用者將永遠能夠選擇兩個會議解決方案（商務用 Skype 與團隊），這可能會導致令人費解或不理想的情況。 與語音遷移不同，會議遷移通常可以在整個公司完成一小段時間。 想要儘快完全切換至團隊會議的組織（且不需等到其語音遷移完成），請先考慮會議。

只有沒有企業語音使用者的組織，才可以使用會議。 只有在他們能夠採用團隊會議之後，才能將這些組織升級至**團隊**。 他們應該先考慮略過會議。

此外，會議優先對於範圍為「純粹即用」會議解決方案的組織而言是有用的，例如，當發出「僅會議」 RFP 時。

## <a name="capabilities-in-meetings-first"></a>會議中的功能優先

會議首先會將下列功能結合在一起：

- 使用[團隊音訊會議](tutorial-audio-conferencing.yml)[供應商務用 Skype 伺服器（內部部署）使用者](https://docs.microsoft.com/microsoftteams/tutorial-audio-conferencing?tutorial-step=3)。
- [會議遷移服務](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)：使用者組織的會議將會在使用者升級到雲端並轉換為團隊會議（需要 Exchange Online）。
- 簡化了團隊中的使用者體驗，並在團隊會議與團隊和頻道（您可以選擇性地使用[應用程式許可權原則](teams-app-permission-policies.md)進行隱藏）中居中;[團隊私人聊天、通話和自我顯示功能](teams-client-experience-and-conformance-to-coexistence-modes.md)不會先在會議中公開，從而讓部署和採用工作完全集中在會議上。
- 卓越的[團隊會議體驗](tutorial-meetings-in-teams.yml)。
- 在團隊與商務用 Skype 之間的 [更好搭配]： 
  - 自動保留：在團隊中的會議中，在商務用 Skype 中撥打電話時，會將小組會議保持不變，反之亦然。 這可防止使用者將私人呼叫 overheard 給會議參與者。
    ![在團隊和商務用 Skype 中更好搭配案例的螢幕擷取畫面](media/meetings-first-better-together-hold.png)
  - 目前狀態調整：團隊中的活動會反映在使用者的目前狀態，即從聊天和通話到商務用 Skype 中的商務用 skype 目前狀態。 具體來說，會議第一位使用者在團隊會議中時，其目前狀態將會更新以反映該專案。 當他們呈現畫面時，其目前狀態將會更新為 [請勿打擾] （根據其在商務用 Skype 中的設定而定）。
  - USB 裝置 HID 控制項對帳（也可在 Mac 上使用）：當團隊會議中的小組與商務用 Skype，在其他情況下，HID 控制項就是由小組所擁有。
  - 除非另有提及，否則您目前的功能越接近，就需要最近的 Windows 桌面用戶端。

## <a name="prerequisites-for-meetings-first"></a>首先召開會議的先決條件

只有在擁有內部部署 Active Directory 和商務用 Skype 內部部署的團隊需求，才能開始進行會議的唯一硬性需求：

- [小組的一般前期必備元件](upgrade-plan-journey-prerequisites.md)，包括
- [團隊中的身分識別與驗證](identify-models-authentication.md)
- [針對團隊和商務用 Skype 設定 Azure Active Directory](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect)。

不需要[商務用 Skype 混合式拓朴](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online)，但建議使用。 某些功能（例如會議遷移服務和互通性）依賴該拓撲。

在任何版本的商務用 Skype Server （以及不支援的 Lync Server）中，都支援會議優先。 任何支援的商務用 Skype 用戶端都支援它，但最好搭配使用的功能必須是最新的用戶端。

在符合這些需求之後（而不是之前），使用者就可以[取得 Office 365 和團隊的授權](https://docs.microsoft.com/office365/enterprise/assign-licenses-to-user-accounts)。

針對最佳的會議第一次體驗，使用者應該啟用[Exchange Online](exchange-teams-interact.md)、 [SharePoint Online 和商務用 OneDrive](sharepoint-onedrive-interact.md)，以及建立 Office 365 群組。 只有信箱是在 Exchange 內部部署的使用者，或是沒有 SharePoint Online 或商務用 OneDrive 或 Office 365 群組建立的使用者，才支援會議優先。 不過，其體驗將不會太完整。 具體說來，對於使用 Exchange Server 內部部署的組織而言，可能會發生（視 Exchange Server 的版本而定），在小組用戶端建立及查看會議，以及與合規性功能有關的一些限制。

至少，使用者必須擁有[團隊的授權](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)。 此外，如果需要的話，也可以授權[音訊會議](set-up-audio-conferencing-in-teams.md)。

我們建議您在授權使用者時，將[ **SfBOnly**或**SfBWithTeamsCollab**模式授](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)與承租人預設值。 這可確保在您準備好要先啟動會議之前，使用者不會在預設**孤島**模式下自行開始使用團隊。

只有在完整的桌面用戶端（Windows 和 Mac）、瀏覽器用戶端和行動用戶端上，才支援會議優先。 它也與[Microsoft 團隊聊天室](https://docs.microsoft.com/microsoftteams/room-systems/)相容。 更好地需要完整的桌面用戶端。

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>在會議中先準備團隊會議

為了讓您的使用者在團隊會議中獲得最佳可能的體驗，您應該：

- 請特別[針對 Microsoft 團隊的會議和會議](deploy-meetings-microsoft-teams-landing-page.md)中的步驟進行。
- [評估您的環境](3-envision-evaluate-my-environment.md)。
- [針對 Microsoft 團隊準備貴組織的網路](prepare-network.md)。
- 透過具有小組的會議室[裝置和解決方案](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)來升級您的會議室，或針對[Microsoft 團隊使用雲端視頻交互操作](cloud-video-interop.md)，以讓您的現有協力廠商房間和裝置加入團隊會議。
- 為您的使用者提供[經認證的 USB 音訊與視頻裝置](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)。
- 準備[推動小組會議的知名度與採納](adopt-microsoft-teams-landing-page.md)。
- [規劃您的服務管理](4-envision-plan-my-service-management.md)。
- 熟悉豐富的呼叫分析報告，以[疑難排解不佳的通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)。

您可以考慮在此階段執行中等規模生產就緒試驗。

## <a name="configure-users-for-meetings-first"></a>先為會議設定使用者

在您授權使用者並準備好貴組織的小組會議之後，就可以開始為您的使用者啟用會議。 我們已將它簡化了：單一設定就可以執行所有工作！

您必須先在[Microsoft 團隊系統管理中心](manage-teams-in-modern-portal.md)或使用[PowerShell](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)中授予使用者（或使用者組管理員）的 [ [SfBWithTeamsCollabAndMeetings 共存] 模式](setting-your-coexistence-and-upgrade-settings.md)，以在會議中執行所有功能和使用者體驗，包括團隊用戶端設定和使用者體驗的[自動一致性](teams-client-experience-and-conformance-to-coexistence-modes.md)、會議遷移服務以及更好的功能。

![[管理員] 設定的螢幕擷取畫面，以先啟用會議](media/teams-meeting-admin-settings.png)

或者，如果您想要將團隊和頻道應用程式從使用者團隊用戶端的左側導覽中隱藏起來，以進一步將其精力集中在會議上，可以使用[應用程式許可權原則](teams-app-permission-policies.md)來完成。

## <a name="reporting-and-call-analytics"></a>報告及呼叫分析

在會議中，小組會議優先的報告及呼叫分析，不會與其他模式中的內容保持聯繫。

## <a name="related-links"></a>相關連結

在您複習本文之後，您可能會想要深入瞭解如何[選擇升級歷程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)、[移植與互通性指導](migration-interop-guidance-for-teams-with-skype.md)方針，以及[與商務用 Skype 共存](coexistence-chat-calls-presence.md)的相關詳細資訊。



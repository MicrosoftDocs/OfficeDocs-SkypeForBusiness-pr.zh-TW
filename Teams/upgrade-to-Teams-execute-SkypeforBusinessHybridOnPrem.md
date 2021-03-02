---
title: 將商務用 Skype 內部部署升級至 Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 瞭解如何從商務用 Skype 內部部署將貴組織升級至 Microsoft Teams。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7bd7d2fad4e4c35a26bcbb435caba5898dd54534
ms.sourcegitcommit: 79b19b326ef40bf04af03021a7c6506fdd9417ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2021
ms.locfileid: "50397548"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>從商務用 Skype 內部部署升級至 Teams

![升級歷程圖，強調部署與執行](media/upgrade-banner-deployment.png "升級旅程的階段，強調部署與執行階段")

本文是升級過程中部署與執行階段的一部分。 繼續進行之前，請確認您已完成下列活動：

-   [已招募專案專案關係人](upgrade-enlist-stakeholders.md)
-   [已定義您的專案範圍](https://aka.ms/SkypetoTeams-Scope)
-   [瞭解商務用 Skype 和 Teams 的共存和互通性](https://aka.ms/SkypeToTeams-Coexist)
-   [已選擇您的升級旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [準備您的環境](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [為貴組織做好準備](https://aka.ms/SkypeToTeams-UserReadiness)
-   [進行試驗](https://aka.ms/SkypeToTeams-Pilot)

如果您已經部署商務用 Skype Server 或 Microsoft Lync 內部部署，且您的組織想要升級至 Teams，請遵循本文中的指引。 您必須設定與 Microsoft 365 或 Office 365 組織的混合式連接，並判斷階段性地將使用者移往 Teams 時，需決定共存需求。

在您開始之前，IT 專業人員和系統管理員應先在本文稍後的文章中，先審查商務用 [Skype Server](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) 內部部署組織的重要考慮。

> [!IMPORTANT]
> 商務用 Skype Online 將於 2021 年 7 月 31 日淘汰，之後將無法再存取也不再受支援。 為了最大化權益的最大化並確保貴組織有適當的時間來實做升級，我們建議您立即開始使用 Microsoft Teams。 請記住，成功的升級會對齊技術和使用者的準備，因此請務必在流覽 Microsoft Teams 旅程時運用本文的指引。

## <a name="step-1-configure-hybrid-connectivity"></a>步驟 1：設定混合式連接 

將內部部署使用者升級至 Teams 的關鍵先決條件，就是為商務用 Skype Server 內部部署設定混合式連接。 

首先閱讀 [規劃混合式連接，](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) 然後遵循設定混合式連接 [性中概述的工作](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)。


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>步驟 2：設定選擇性的 (共存) 

商務用 Skype 與 Teams 用戶端和使用者之間的共存和互通性是由 Teams 升級模式所定義。  根據預設，組織採用群島模式，可讓使用者同時使用 Teams 和商務用 Skype 用戶端。

對於移入 Teams 的組織來說，TeamsOnly 模式是每個使用者的最終目的地，但並非所有使用者都需要同時獲得 TeamsOnly (或其他任何) 指派。

在使用者到達 TeamsOnly 模式之前，組織可以選擇性地使用任何商務用 Skype 共存模式，以確保 TeamsOnly 模式中的使用者與尚未使用的使用者之間能夠預測地通訊。  商務用 Skype 共存模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 的目的是在組織從商務用 Skype 轉換到 Teams 時，為使用者提供簡單且可預測的體驗。 

當使用者在任何商務用 Skype 模式中時，所有傳入的聊天和通話會路由至使用者的商務用 Skype 用戶端。 為了避免使用者混淆並確保正確的路由，當使用者處於任何商務用 Skype 模式時，Teams 用戶端中的通話和聊天功能會停用。 同樣地，當使用者處於 SfBOnly 或 SfBWithTeamsCollab 模式時，Teams 中的會議排程會明確停用，而且當使用者處於 SfBWithTeamsCollabAndMeetings 模式時，會明確啟用。

根據您的需求，您可以根據貴組織所選擇的升級路徑，指派適當的共存模式。 有關詳細資訊，請參閱針對使用 Teams 與商務用 [Skype](migration-interop-guidance-for-teams-with-skype.md) 的組織，以及設定您的 [共存](https://aka.ms/SkypeToTeams-SetCoexistence)與升級設定所提供之移移和互通性指南。


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>步驟 3：將使用者從商務用 Skype 內部部署移至 Teams

最後，您想要將使用者移至 TeamsOnly 模式。 視您的內部部署環境不同，這可能需要一或兩個步驟。  

詳細資訊請參閱在內部部署 [](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)和雲端之間移動使用者，以及將使用者從內部[部署移至 Teams。](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>步驟 4：停用混合式以完成移移至雲端

將所有使用者從內部部署移至雲端之後，就可以解除內部部署商務用 Skype 部署。 詳細資訊請參閱停用混合 [式以完成移移至雲端](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)。


## <a name="phone-system-and-pstn-connectivity-options"></a>電話系統與 PSTN 連接選項

使用者進入 TeamsOnly 模式後，支援 Teams 的電話系統。  (使用者位於群島模式，則只有商務用 Skype.)  

### <a name="pstn-connectivity-options"></a>PSTN 連接選項

考慮公用交換電話網路 (PSTN) 連接選項時，從商務用 Skype 內部部署切換到 TeamsOnly 模式時，有兩種可能的情況：

- 商務用 Skype 內部部署與企業語音的使用者，將會移往線上，並且使用 Microsoft 通話方案。 將此使用者移轉至 Teams 需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並且使用 A) 將該使用者電話號碼的埠移轉至 Microsoft 通話方案，或 B) 從可用地區指派新的訂閱者號碼來協調移動。  詳細資訊請參閱從商務用 Skype Server 內部部署、企業語音到 [Microsoft 通話方案](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)。

- 商務用 Skype 內部部署與企業語音的使用者，將會移往線上並保持內部部署 PSTN 連線。 將此使用者移轉至 Teams 需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並協調使用者移轉至直接路由的移轉。 詳細資訊請參閱從商務用 Skype Server 內部部署，以及企業 [語音，到直接路由](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)。


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>使用商務用 Skype Server 內部部署之組織的重要考慮

- 下列文章說明重要的升級概念和共存行為：
    - [Teams 和商務用 Skype 的共存](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [共存模式 - 參照](migration-interop-guidance-for-teams-with-skype.md)
    - [Teams 用戶端體驗和遵從共存模式](teams-client-experience-and-conformance-to-coexistence-modes.md)

- 設定商務用 Skype 混合式是遷移到 TeamsOnly 模式的先決條件。 雖然可以在沒有混合式的情況下在群島模式中使用 Teams，但必須等到使用者從商務用 Skype 內部部署移至商務用 Skype Online (使用 [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)) 之後，才能轉換到 TeamsOnly 模式。 詳細資訊請參閱設定 [混合式連接](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)。

- 如果貴組織有商務用 Skype Server，而且您尚未進行混合式連接，但您仍想要使用 Teams 來管理 Teams 功能，則必須使用具有 .onmicrosoft.com 網域的管理帳戶。 

- Teams 使用者擁有商務用 Skype 帳戶內部部署 (，也就是說，他們尚未使用 Move-CsUser) 移至雲端，因此無法與任何商務用 Skype 使用者交互操作，也無法與外部使用者進行聯盟。 只有在使用者移至雲端或位於 (，或 TeamsOnly 使用者登入雲端時，才能) 。 

- 如果您有內部部署商務用 Skype 帳戶的任何使用者，您無法在租使用者層級指派 TeamsOnly 模式。 您必須先使用內部部署商務用 Skype 帳戶將所有使用者移至雲端，然後停用混合式以 `Move-CsUser` [完成移轉至雲端。](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` 如果偵測到 Lyncdiscover DNS 記錄指向 Office 365 外的位置，便無法于租使用者層級上工作。

- 您必須確保您的使用者已正確同步處理到 Azure AD，並擁有正確的商務用 Skype 屬性。 這些屬性都是 "msRTCSIP-" 的首碼。 如果使用者未正確同步處理到 Azure AD，Teams 中的管理工具將無法管理這些使用者。  (例如，除非您正確地同步處理這些屬性，否則無法將 Teams 策略指派給內部部署使用者。) 請參閱設定 Teams 的 [Azure AD Connect](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)和商務用 Skype。

- 若要在混合式組織中建立新 TeamsOnly 或商務用 Skype Online 使用者，您必須先在商務用 *Skype Server* 內部部署中啟用使用者，然後使用 Move-CsUser 將使用者從內部部署移至雲端。  先在內部部署中建立使用者，可確保任何其他留在內部部署商務用 Skype 的使用者都能路由到新建立的使用者。 一旦所有使用者都移至線上，就不再需要先在內部部署中啟用使用者。

- 當使用者從內部部署移至雲端時，由該使用者組織的會議會移轉至商務用 Skype Online 或 Teams，視是否指定 -MoveToTeams 參數為不同。

- 如果您想要在商務用 Skype 用戶端中為內部部署使用者顯示通知，您必須在內部部署工具集使用 TeamsUpgradePolicy。 只有 NotifySfbUsers 參數與內部部署使用者相關。  內部部署使用者會從 TeamsUpgradePolicy 的線上實例接收其模式。 請參閱 [Grant-CsTeamsUpgradePolicy 中的附注](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)。 

>[!NOTE]
> 2019 年 9 月 3 日之後建立的任何新租使用者，會建立為 TeamsOnly 租使用者，除非組織已有商務用 Skype Server 內部部署。 Microsoft 會使用 DNS 記錄來識別內部部署商務用 Skype Server 組織。 如果貴組織內部部署商務用 Skype Server 沒有公用 DNS 專案，您必須致電 Microsoft 支援服務，將新租使用者降級。 

## <a name="related-links"></a>相關連結

[適用于將 Teams 與商務用 Skype 一起使用的組織之移移和互通性指南](migration-interop-guidance-for-teams-with-skype.md) 

[設定商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用會議移 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
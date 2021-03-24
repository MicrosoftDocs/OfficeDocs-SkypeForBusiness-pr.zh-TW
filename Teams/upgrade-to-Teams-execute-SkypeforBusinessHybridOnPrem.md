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
ms.openlocfilehash: b35a757ecd70fbf2926e668bef86cb21e51d8b8e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093783"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>從商務用 Skype 內部部署升級至 Teams

![升級歷程圖，強調部署與執行](media/upgrade-banner-deployment.png "升級歷程的階段，強調部署與執行階段")

本文是升級歷程的部署與執行階段之一。 繼續進行之前，請確認您已完成下列活動：

-   [已招募專案專案關係人](upgrade-enlist-stakeholders.md)
-   [已定義專案範圍](./upgrade-define-project-scope.md)
-   [瞭解商務用 Skype 和 Teams 的共存與互通性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
-   [已選擇升級旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [準備您的環境](./upgrade-prepare-environment.md)
-   [準備您的組織](./upgrade-prepare-organization.md)
-   [進行試驗](./pilot-essentials.md)

如果您已經部署商務用 Skype Server 或 Microsoft Lync 內部部署，而貴組織想要升級至 Teams，請遵循本文中的指引。 您必須設定與 Microsoft 365 或 Office 365 組織之間的混合式連接，並判斷階段將使用者移往 Teams 時，共同使用需求。

開始之前，IT 專業人員和系統管理員應于本文稍後閱讀商務用 [Skype Server](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) 內部部署組織的重要考慮。

> [!IMPORTANT]
> 商務用 Skype Online 將於 2021 年 7 月 31 日淘汰，之後將無法再存取也不再受支援。 為了最大化權益實現，並確保貴組織有適當的時間實做升級，我們鼓勵您立即開始 Microsoft Teams 之旅。 請記住，成功的升級會符合技術和使用者的準備狀態，因此請務必在流覽 Microsoft Teams 的歷程時，運用本文的指引。

## <a name="step-1-configure-hybrid-connectivity"></a>步驟 1：設定混合式連接 

將內部部署使用者升級至 Teams 的關鍵先決條件，就是為商務用 Skype Server 內部部署設定混合式連接。 

首先閱讀 [規劃混合式連接，](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json) 然後遵循設定混合式連接 [中概述的工作](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)。


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>步驟 2：設定轉換共存模式 (選擇性) 

商務用 Skype 與 Teams 用戶端與使用者之間的共存和互通性是由 Teams 升級模式所定義。  根據預設，組織會採用群島模式，讓使用者同時使用 Teams 和商務用 Skype 用戶端。

對於移入 Teams 的組織，TeamsOnly 模式是每個使用者的最終目的地，雖然並非所有使用者都需要同時指派 TeamsOnly (或其他) 模式。

在使用者到達 TeamsOnly 模式之前，組織可以選擇使用任何商務用 Skype 共存模式，以確保在 TeamsOnly 模式中的使用者與尚未使用的使用者之間可以預測的通訊。  商務用 Skype 共存模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 的目的是在組織從商務用 Skype 轉換至 Teams 時，為使用者提供簡單且可預測的體驗。 

當使用者在任何商務用 Skype 模式中時，所有傳入的聊天和通話會路由至使用者的商務用 Skype 用戶端。 為了避免使用者混淆並確保適當的路由，當使用者處於任何商務用 Skype 模式時，Teams 用戶端中的通話和聊天功能會停用。 同樣地，當使用者處於 SfBOnly 或 SfBWithTeamsCollab 模式時，Teams 中的會議排程會明確停用，且當使用者處於 SfBWithTeamsCollabAndMeetings 模式時，明確啟用。

視您的需求，您可以根據貴組織所選擇的升級路徑，指派適當的共存模式。 詳細資訊請參閱將 Teams 與商務用 Skype 一起使用 [的組織](migration-interop-guidance-for-teams-with-skype.md) 移移及互通性指南，以及 [設定您的共存與升級設定](./setting-your-coexistence-and-upgrade-settings.md)。


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>步驟 3：將使用者從商務用 Skype 內部部署移至 Teams

最後，您將想要將使用者移至 TeamsOnly 模式。 這可能需要一或兩個步驟，取決於您的內部部署環境。  

詳細資訊請參閱在內部部署 [](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)和雲端之間移動使用者，以及將使用者從內部部署[移至 Teams。](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>步驟 4：停用混合式以完成移向雲端

將所有使用者從內部部署移至雲端之後，就可以解除內部部署商務用 Skype 部署。 詳細資訊，請參閱[停用混合式以完成移向雲端。](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)


## <a name="phone-system-and-pstn-connectivity-options"></a>電話系統與 PSTN 連接選項

使用者進入 TeamsOnly 模式後，支援 Teams 電話系統。  (如果使用者位於群島模式，則只有商務用 Skype 才支援電話系統)  

### <a name="pstn-connectivity-options"></a>PSTN 連接選項

考慮使用公用交換式電話 (PSTN) 連接選項時，從內部部署商務用 Skype 移往 TeamsOnly 模式時，有兩種可能的情況：

- 在商務用 Skype 內部部署中使用企業語音的使用者，該使用者將會移往線上，並且使用 Microsoft 通話方案。 將該使用者移轉至 Teams 時，需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並配合 A) 將該使用者電話號碼的埠移至 Microsoft 通話方案，或 B) 從可用區域指派新的訂閱者號碼。  若要詳細資訊，請參閱從內部部署商務用 Skype Server 使用 [企業語音，到 Microsoft 通話方案](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)。

- 商務用 Skype 內部部署與企業語音的使用者，將會移往線上並保持內部部署 PSTN 連線。 將此使用者移轉至 Teams，需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並協調使用者移轉至直接路由。 詳細資訊，請參閱從內部部署商務用 Skype Server 使用 [企業語音，到直接路由](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)。


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>內部部署商務用 Skype Server 組織的重要考慮

- 下列文章說明重要的升級概念和共存行為：
    - [Teams 與商務用 Skype 共存](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [共存模式 - 參照](migration-interop-guidance-for-teams-with-skype.md)
    - [Teams 用戶端體驗和遵從共存模式](teams-client-experience-and-conformance-to-coexistence-modes.md)

- 設定商務用 Skype 混合式是遷移到 TeamsOnly 模式的先決條件。 雖然可以在不使用混合式的情況下在群島模式中使用 Teams，但除非使用者從商務用 Skype 內部部署移至商務用 Skype Online (使用 [Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)) ，才能轉換至 TeamsOnly 模式。 詳細資訊，請參閱設定 [混合式連接](/skypeforbusiness/hybrid/configure-hybrid-connectivity)。

- 如果貴組織有商務用 Skype Server，而且您尚未進行混合式連接，但您仍想要使用 Teams 來管理 Teams 功能，您必須使用具有 .onmicrosoft.com 網域的管理帳戶。 

- 擁有商務用 Skype 帳戶的小組使用者 (亦即尚未使用 Move-CsUser) 移至雲端，無法與任何商務用 Skype 使用者進行交互操作，也無法與外部使用者進行聯盟。 只有在使用者移至雲端或位於 (模式，或 TeamsOnly 使用者移至雲端時，才能) 。 

- 如果您有內部部署商務用 Skype 帳戶的任何使用者，您無法在租使用者層級指派 TeamsOnly 模式。 您必須先使用內部部署商務用 Skype 帳戶將所有使用者移至雲端，然後停用混合式以 `Move-CsUser` [完成移轉至雲端。](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` 如果偵測到 Lyncdiscover DNS 記錄指向 Office 365 外的位置，則無法在租使用者層級上工作。

- 您必須確保您的使用者以正確的商務用 Skype 屬性正確同步處理至 Azure AD。 這些屬性都是 "msRTCSIP-" 的首碼。 如果使用者未正確同步處理至 Azure AD，Teams 中的管理工具將無法管理這些使用者。  (例如，除非您正確地同步處理這些屬性，否則無法將 Teams 策略指派給內部部署使用者。) 若要瞭解詳細資訊，請參閱設定 Teams 的 [Azure AD Connect](/SkypeForBusiness/hybrid/configure-azure-ad-connect)和商務用 Skype。

- 若要在混合式組織中建立新的 TeamsOnly 或商務用 Skype Online 使用者，您必須先在商務用 *Skype Server* 內部部署中啟用使用者，然後使用 Move-CsUser 將使用者從內部部署移至雲端。  先在內部部署中建立使用者，可確保任何其他其餘的內部部署商務用 Skype 使用者都能路由至新建立的使用者。 一旦所有使用者都移至線上，就不再需要先在內部部署中啟用使用者。

- 當使用者從內部部署移至雲端時，該使用者組織的會議會移轉至商務用 Skype Online 或 Teams ，視是否指定 -MoveToTeams 切換而不同。

- 如果您想要在商務用 Skype 用戶端中顯示內部部署使用者的通知，您必須在內部部署工具集中使用 TeamsUpgradePolicy。 只有 NotifySfbUsers 參數與內部部署使用者相關。  內部部署使用者會從 TeamsUpgradePolicy 的線上實例接收其模式。 請參閱 [Grant-CsTeamsUpgradePolicy 中的筆記](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)。 

>[!NOTE]
> 2019 年 9 月 3 日之後建立的任何新租使用者會建立為 TeamsOnly 租使用者，除非組織已經有商務用 Skype Server 的內部部署。 Microsoft 會使用 DNS 記錄來識別內部部署商務用 Skype Server 組織。 如果貴組織內部部署商務用 Skype Server 沒有公用 DNS 專案，您必須打電話給 Microsoft 支援服務，將新租使用者降級。 

## <a name="related-links"></a>相關連結

[使用 Teams 與商務用 Skype 的組織移移和互通性指南](migration-interop-guidance-for-teams-with-skype.md) 

[設定商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連接](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用會議移 (MMS) ](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
---
title: 將商務用 Skype內部部署升級至Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 瞭解如何從內部部署Microsoft Teams升級商務用 Skype組織。
ms.localizationpriority: medium
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
ms.openlocfilehash: d5ad5bc82771a3a8f020600a48848a074b88aec4
ms.sourcegitcommit: d3c48f0c147cf0c47d5eb4ea1128b5bca13be718
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/01/2022
ms.locfileid: "62299058"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>從內部商務用 Skype升級至Teams

![升級歷程圖，強調部署和實現。](media/upgrade-banner-deployment.png "升級歷程的階段，強調部署與執行階段")

本文是升級歷程的部署與執行階段之一。 繼續進行之前，請確認您已完成下列活動：

-   [已招募專案專案關係人](upgrade-enlist-stakeholders.md)
-   [已定義專案範圍](./upgrade-define-project-scope.md)
-   [瞭解共同商務用 Skype和Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
-   [已選擇升級旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [準備您的環境](./upgrade-prepare-environment.md)
-   [準備您的組織](./upgrade-prepare-organization.md)
-   [進行試驗](./pilot-essentials.md)

如果您已經部署內部商務用 Skype Server或 Microsoft Lync Server，而貴組織想要升級至 Teams，請遵循本文中的指引。 您必須設定與貴組織之間的混合Microsoft 365，如規劃 商務用 Skype Server 和[Teams。](/skypeforbusiness/hybrid/plan-hybrid-connectivity)

在開始之前，您也應該在本文稍後的文章中，商務用 Skype Server[內部部署組織的重要](#important-considerations-for-organizations-with-skype-for-business-server-on-premises)考慮。

> [!IMPORTANT]
> 商務用 Skype于 2021 年 7 月 31 日停用。 為了最大化效益的實現，並確保貴組織有適當的時間實做升級，我們鼓勵您立即開始Microsoft Teams旅程。 請記住，成功的升級會對齊技術和使用者準備狀態，因此請務必在流覽至 Microsoft Teams。

## <a name="step-1-configure-hybrid-connectivity"></a>步驟 1：設定混合式連接 

將內部部署使用者升級至 Teams的關鍵先決條件是為內部部署商務用 Skype Server混合式連接。 

首先閱讀 [規劃混合式連接](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json)，然後遵循設定混合式連接 [中概述的工作](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)。


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>步驟 2：設定轉換共存模式 (選擇性) 

用戶端和使用者之間的商務用 Skype Teams互通性是由共存模式[所定義](migration-interop-guidance-for-teams-with-skype.md)。 混合式組織預設為群島模式。 群島模式允許使用者同時使用Teams商務用 Skype用戶端。 組織可以選擇使用其他共存模式，為使用者提供可預測的體驗，讓組織從 商務用 Skype 轉換Teams。 無論組織為內部部署使用者使用何種模式，當這些使用者從內部部署移至雲端時，他們會變成 TeamsOnly (，而且無法擁有任何其他模式) 。  只要使用者仍在使用商務用 Skype Server，就可以指派 TeamsOnly 外的任何模式。 如果需要，可以將 TeamsOnly 使用者移回內部部署，這可能會導致他們收到租使用者的 TeamsUpgradePolicy 全域原則。

當使用者在任一模式商務用 Skype，所有傳入的聊天和通話會路由至使用者的商務用 Skype用戶端。 為了避免使用者混淆並確保正確的路由，Teams 用戶端中的通話和聊天功能會針對指派任一模式的使用者 *商務用 Skype停用*。 當使用者處於 SfBOnly 或 SfBWithTeamsCollab 模式，且使用者處於 SfBWithTeamsCollabAndMeetings 模式時，會停用 Teams 中的會議排程。**

視您的需求，您可以根據貴組織所選擇的升級路徑，指派適當的共存模式。 有關詳細資訊，請參閱[將](migration-interop-guidance-for-teams-with-skype.md)應用程式與Teams一起使用商務用 Skype及設定共存和升級設定的組織移移和互通性[指南](./setting-your-coexistence-and-upgrade-settings.md)。


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>步驟 3：將使用者從內部商務用 Skype移至Teams

Microsoft 最近簡化了將使用者移至 TeamsOnly 的流程。 無論您使用的是哪個版本或 Lync Server 2013，商務用 Skype Server程式現在都是單一步驟。 若要詳細資訊，請參閱 [在](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)內部部署和雲端之間移動使用者，以及將使用者從內部部署移至[Teams](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)。 

## <a name="step-4-complete-your-migration-to-the-cloud-by-disabling-hybrid-and-decommissioning-on-premises-skype-for-business"></a>步驟 4：停用混合式和解除內部部署內部部署商務用 Skype

將所有使用者從內部部署移至雲端之後，就可以解除內部部署商務用 Skype部署。 詳細資訊請參閱解除[內部部署商務用 Skype授權](/skypeforbusiness/hybrid/decommission-on-prem-overview)。


## <a name="phone-system-and-pstn-connectivity-options"></a>電話系統 PSTN 連接選項

電話系統在Teams TeamsOnly 模式後，支援使用 Teams。  (如果使用者在群島模式中，電話系統僅支援 商務用 Skype.)  

### <a name="pstn-connectivity-options"></a>PSTN 連接選項

考慮使用公用交換式電話 (PSTN) 連接選項時，從內部部署 商務用 Skype 移至 TeamsOnly 模式時，有兩種可能的情況：

- 內部部署商務用 Skype使用者企業語音，他們將使用 Microsoft 通話方案移往線上。 將該使用者移轉至 Teams 時，需要將使用者的內部部署 商務用 Skype 帳戶移至雲端，然後使用 A) 將該使用者電話號碼的埠移轉至 Microsoft 通話方案，或 B) 從可用區域指派新的訂閱者號碼。  若要詳細資訊，請參閱從[內部商務用 Skype Server內部部署 ，企業語音到 Microsoft 通話方案](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)。

- 內部部署商務用 Skype使用者企業語音，他們將移往線上並保持內部部署 PSTN 連線。 將該使用者移轉Teams需要將使用者的內部部署 商務用 Skype 帳戶移至雲端，並協調使用者移轉至直接路由。 若要詳細資訊，請參閱從[內部商務用 Skype Server內部部署 ，企業語音直接路由](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)。


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>內部部署組織的重要商務用 Skype Server考慮

- 設定混合商務用 Skype是遷移到 TeamsOnly 模式的先決條件。 內部部署使用者可以不使用商務用 Skype Server模式使用Teams模式。 不過，若要轉換至 TeamsOnly 模式，必須使用 [Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)將使用者移至雲端，而需要混合式連接。 詳細資訊，請參閱設定 [混合式連接](/skypeforbusiness/hybrid/configure-hybrid-connectivity)。 即將停用的 商務用 Skype Online 不會變更此需求。 若要讓組織從商務用 Skype Server移至Teams，他們仍然必須使用相同的工具集來設定和設定混合式，就像在停用之前 *一樣*。

- 若要將內部部署使用者移至雲端，請使用 `Move-CsUser` 內部部署管理工具。 您不再需要指定參數 `-MoveToTeams` ，將使用者直接從內部部署移至 TeamsOnly。 系統會自動為使用者指派 TeamsOnly 模式 `-MoveToTeams` ，而且無論是否指定切換，其內部部署會議都會自動Teams會議。

- 如果貴組織有 商務用 Skype Server，而且您尚未配置混合式連接，但仍想要使用 Teams，則您必須使用具有 .onmicrosoft.com 網域的管理帳戶來管理 Teams 功能。 沒有混合式連接，管理工具無法識別您的內部部署網域。 

- Teams擁有 商務用 Skype 帳戶內部部署 (即尚未使用 Move-CsUser) 移至雲端的使用者，無法與 商務用 Skype 使用者進行交互操作，也無法與外部使用者進行聯盟。 只有當使用者移至雲端且是 TeamsOnly 使用者時，才能使用這項功能。 

- 如果您擁有內部商務用 Skype帳戶的任何使用者，或是您仍擁有內部部署 lyncdiscover DNS 記錄，則無法指派租使用者層級的 TeamsOnly 模式。 您必須先使用 內部部署帳戶商務用 Skype所有使用者移至雲端 `Move-CsUser` 。 接著，請遵循停用混合式以 [完成](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)移向雲端的步驟，包括移除 DNS 專案。 `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`如果偵測到 Lyncdiscover DNS 記錄指向其他位置，就不會在租使用者層級Office 365。

- 您必須確保您的使用者正確同步處理至Azure AD正確的商務用 Skype屬性。 這些屬性都是"msRTCSIP-"的首碼。 如果使用者未正確同步處理Azure AD，Teams中的管理工具將無法管理這些使用者。  (例如，除非您正確地同步處理這些屬性，否則無法指派 Teams 策略給內部部署使用者。) 若要瞭解詳細資訊，請參閱設定 Teams 和[商務用 Skype 的 Azure AD 連線](/SkypeForBusiness/hybrid/configure-azure-ad-connect)。

- 若要在混合式組織中建立新的 TeamsOnly，您必須先在 *商務用 Skype Server* 內部部署中啟用使用者，然後使用 Move-CsUser 將使用者從內部部署移至雲端。  先在內部部署中建立使用者，可確保任何其他內部部署商務用 Skype使用者都能路由至新建立的使用者。 一 *旦* 所有使用者都移至線上，就不再需要先在內部部署中啟用使用者。

- 如果您想要在內部部署商務用 Skype用戶端中顯示通知，您必須在內部部署工具集使用 TeamsUpgradePolicy。 只有 NotifySfbUsers 參數與內部部署使用者相關。  內部部署使用者會從 TeamsUpgradePolicy 的線上實例接收其模式。 請參閱 [Grant-CsTeamsUpgradePolicy 中的筆記](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)。 

>[!NOTE]
> 2019 年 9 月 3 日之後建立的任何新租使用者會建立為 TeamsOnly 租使用者，除非組織已有內部部署 商務用 Skype Server。 Microsoft 使用 DNS 記錄來識別內部部署商務用 Skype Server組織。 詳細資訊請參閱成為混合式內部部署 [組織的 DNS 影響](/SkypeForBusiness/hybrid/configure-hybrid-connectivity#dns-implications-for-on-premises-organizations-that-become-hybrid)。 

- 下列文章說明重要的升級概念和共存行為：
    - [Teams和商務用 Skype](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [共存模式 - 參照](migration-interop-guidance-for-teams-with-skype.md)
    - [Teams 用戶端體驗和遵從共存模式](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="related-links"></a>相關連結

[適用于使用應用程式與Teams之組織的移商務用 Skype](migration-interop-guidance-for-teams-with-skype.md) 

[設定商務用 Skype Server或商務用 Skype Server之間的Microsoft 365 Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用會議移 (MMS) ](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

---
title: 將商務用 Skype內部部署升級至Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 瞭解如何將貴組織從商務用 Skype內部部署升級至Microsoft Teams。
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
ms.openlocfilehash: c4b233978b9f9edf0aabbdfb8f9b24ff55a234cc
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681364"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>從商務用 Skype內部部署升級至Teams

![升級旅程圖，強調部署和實作。](media/upgrade-banner-deployment.png "升級旅程的階段，強調部署和實作階段")

本文是升級旅程中部署與實作階段的一部分。 繼續進行之前，請確認您已完成下列活動：

- [呼叫專案專案專案關係人](upgrade-enlist-stakeholders.md)
- [定義您的專案範圍](./upgrade-define-project-scope.md)
- [瞭解商務用 Skype與Teams的共存及互通性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [已選擇您的升級旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [準備好您的環境](./upgrade-prepare-environment.md)
- [為您的組織做好準備](./upgrade-prepare-organization.md)
- [進行試驗](./pilot-essentials.md)

如果您已在內部部署商務用 Skype Server或 Microsoft Lync Server，而您的組織想要升級至Teams，請依照本文中的指引進行。 您必須按照規劃商務用 Skype Server與Teams[之間的混合式聯](/skypeforbusiness/hybrid/plan-hybrid-connectivity)機，來設定與Microsoft 365組織的混合式連線。

開始之前，您也應該在本文稍後檢閱商務用 Skype Server內部部署[組織的重要考慮](#important-considerations-for-organizations-with-skype-for-business-server-on-premises)。

> [!IMPORTANT]
> 商務用 Skype Online 已于 2021 年 7 月 31 日淘汰。 為了充分運用權益並確保貴組織有適當的時間實作升級，我們鼓勵您立即開始進行Microsoft Teams。 請記住，成功升級會使技術和使用者整備一致，因此請務必運用此指導方針，引導您前往Microsoft Teams。

## <a name="step-1-configure-hybrid-connectivity"></a>步驟 1：設定混合式連線能力

將內部部署使用者升級至Teams的關鍵先決條件是為您的商務用 Skype Server內部部署設定混合式連線能力。

先閱讀 [規劃混合式連線](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json)能力，然後遵循設定 [混合式聯](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)機中所述的工作。

## <a name="step-2-set-transitional-coexistence-mode-optional"></a>步驟 2：將共存模式設定為選用 () 

商務用 Skype與Teams用戶端和使用者之間的共存和互通性是由[共存模式](migration-interop-guidance-for-teams-with-skype.md)定義。 混合式組織預設為群島模式。 群島模式可讓使用者同時使用Teams和商務用 Skype用戶端。 組織可以選擇性地使用其他共存模式，在組織從商務用 Skype轉換到Teams時，為使用者提供可預測的體驗。 無論組織針對內部部署使用者使用哪種模式，當這些使用者從內部部署移至雲端時，他們都會變成 TeamsOnly (，而且無法擁有任何其他模式) 。  只要使用者仍在使用 商務用 Skype Server，就可以指派 TeamsOnly 以外的任何模式。 如有需要，您可以將 TeamsOnly 使用者移回內部部署，這會讓他們收到 TeamsUpgradePolicy 的租使用者全域原則。

當使用者處於任何商務用 Skype模式時，所有傳入的聊天和通話都會路由至使用者的商務用 Skype用戶端。 為了避免使用者混淆，並確保Teams用戶端中的正確路由、通話和聊天功能會 *停用指派任一商務用 Skype模式的使用者*。 當使用者處於 SfBOnly 或 SfBWithTeamsCollab 模式，且使用者處於 SfBWithTeamsCollab 模式時，會 *停* 用Teams中的會議排程。

根據您的需求，您可以根據貴組織選擇的升級路徑，指派適當的共存模式。 如需詳細資訊，請參閱[搭配使用 Teams 與商務用 Skype的組織移轉和互通性指導方針](migration-interop-guidance-for-teams-with-skype.md)和[設定您的共存與升級設定](./setting-your-coexistence-and-upgrade-settings.md)。

## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>步驟 3：將使用者從商務用 Skype內部部署移至僅Teams

Microsoft 最近簡化了將使用者移至 TeamsOnly 的程式。 無論您使用哪個版本的 商務用 Skype Server 或 Lync Server 2013，此程式現在是單一步驟。 如需詳細資訊，請參閱[在內部部署和雲端之間移動使用者](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)和[將使用者從內部部署移至Teams](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)。

## <a name="step-4-complete-your-migration-to-the-cloud-by-disabling-hybrid-and-decommissioning-on-premises-skype-for-business"></a>步驟 4：停用混合式並解除委任內部部署商務用 Skype，以完成移轉至雲端的作業

將所有使用者從內部部署移至雲端之後，您可以解除委任內部部署商務用 Skype部署。 如需詳細資訊，請參閱[解除委任內部部署商務用 Skype環境](/skypeforbusiness/hybrid/decommission-on-prem-overview)。

## <a name="phone-system-and-pstn-connectivity-options"></a>電話系統和 PSTN 連線選項

在使用者處於 TeamsOnly 模式後，支援電話系統與Teams。  (如果使用者處於群島模式，電話系統僅支援 商務用 Skype.) 

### <a name="pstn-connectivity-options"></a>PSTN 連線選項

在考慮 [公用交換電話網路] (PSTN) 連線選項時，從內部部署的商務用 Skype移至 TeamsOnly 模式時，可能會有兩種情況：

- 商務用 Skype內部部署且擁有企業語音的使用者，將會移至線上並使用 Microsoft 通話方案。 將此使用者移轉到Teams需要將使用者的內部部署商務用 Skype帳戶移至雲端，並透過 A) 該使用者電話號碼的埠移至 Microsoft 通話方案，或 B) 從可用地區指派新的訂閱者號碼來進行協調。  如需詳細資訊，請參閱[從商務用 Skype Server內部部署、企業語音到 Microsoft 通話方案](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)。

- 商務用 Skype內部部署且擁有企業語音的使用者，將會移至線上並保持內部部署 PSTN 連線能力。 將此使用者移轉到Teams需要將使用者的內部部署商務用 Skype帳戶移至雲端，並配合使用者移轉到直接路由來協調移轉。 如需詳細資訊，請參閱[從商務用 Skype Server內部部署、含企業語音，到直接路由](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)。

## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>對於具有內部部署商務用 Skype Server組織的重要考慮

- 設定商務用 Skype混合式是移轉到 TeamsOnly 模式的先決條件。 內部部署商務用 Skype Server使用者可以使用不含混合式的島嶼模式Teams。 不過，若要移轉至 TeamsOnly 模式，必須使用 [Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)將使用者移至雲端，而需要混合式連線。 如需詳細資訊，請參閱 [設定混合式連線](/skypeforbusiness/hybrid/configure-hybrid-connectivity)。 即將淘汰 商務用 Skype Online 並不會變更此需求。 若要讓組織從商務用 Skype Server移至Teams，他們仍必須使用相同的工具組來設定混合式，*就和淘汰之前一樣*。

- 若要將內部部署使用者移至雲端，請使用 `Move-CsUser` 內部部署系統管理工具。 您不再需要指定 `-MoveToTeams` 將使用者直接從內部部署移至 TeamsOnly 的切換。 使用者會自動獲派 TeamsOnly 模式，而且無論是否 `-MoveToTeams` 指定切換，他們的內部部署會議都會自動轉換為Teams會議。

- 如果您的組織有商務用 Skype Server，但您尚未設定混合式連線，但仍想要使用Teams，若要管理Teams功能，您必須使用具有 .onmicrosoft.com 網域的系統管理帳戶。 如果沒有混合式連線能力，系統管理工具就無法辨識您的內部部署網域。

- Teams擁有內部部署 (商務用 Skype帳戶的使用者，他們尚未使用 Move-CsUser 移至雲端) 無法與任何商務用 Skype使用者相互合作，也無法與外部使用者同盟。 這項功能只有在使用者移至雲端並成為 TeamsOnly 使用者時才能使用。

- 如果您有任何使用者在內部部署使用商務用 Skype帳戶，或您仍有內部部署的 lyncdiscover DNS 記錄，您就無法在租使用者層級指派 TeamsOnly 模式。 您必須先使用 `Move-CsUser` ，將擁有內部部署商務用 Skype帳戶的所有使用者移至雲端。 然後依照停用混合式中所述的步驟 [完成移轉到雲端](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)，包括移除 DNS 專案。 `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`如果偵測到 lyncdiscover DNS 記錄指向Office 365以外的位置，則無法在租使用者層級運作。

- 您必須確定您的使用者已正確地與具有正確商務用 Skype屬性的 Azure AD 同步處理。 這些屬性都是使用 「msRTCSIP-」 的首碼。 如果使用者未正確同步處理至 Azure AD，Teams中的管理工具將無法管理這些使用者。  (例如，您將無法將Teams原則指派給內部部署使用者，除非您正確地同步處理這些屬性。) 如需詳細資訊，請參閱針對[Teams和商務用 Skype設定 Azure AD 連線](/SkypeForBusiness/hybrid/configure-azure-ad-connect)。

- 若要在混合式組織中建立新的 TeamsOnly，*您必須先在商務用 Skype Server內部部署中啟用使用者*，然後使用 Move-CsUser 將使用者從內部部署移至雲端。  先在內部部署中建立使用者，可確保任何其他剩餘的內部部署商務用 Skype使用者都能路由至新建立的使用者。 一旦 *將所有* 使用者移至線上，就不再需要先在內部部署中啟用使用者。

- 如果您想要在內部部署使用者的商務用 Skype用戶端中顯示通知，您必須在內部部署工具組中使用 TeamsUpgradePolicy。 只有 NotifySfbUsers 參數與內部部署使用者相關。  內部部署使用者會從 TeamsUpgradePolicy 的線上實例收到他們的模式。 請參閱 [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)中的備忘稿。

> [!NOTE]
> 在 2019 年 9 月 3 日之後建立的任何新租使用者都會建立為 TeamsOnly 租使用者，除非組織已經有內部部署的商務用 Skype Server。 Microsoft 會使用 DNS 記錄來識別內部部署商務用 Skype Server組織。 如需詳細資訊，請參閱 [DNS 對於變成混合式的內部部署組織的影響](/SkypeForBusiness/hybrid/configure-hybrid-connectivity#dns-implications-for-on-premises-organizations-that-become-hybrid)。

- 下列文章說明重要的升級概念和共存行為：
  - [Teams與商務用 Skype的共存](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
  - [共存模式 - 參照](migration-interop-guidance-for-teams-with-skype.md)
  - [Teams 用戶端體驗和遵從共存模式](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="related-links"></a>相關連結

[搭配使用Teams的組織移轉和互通性指導方針商務用 Skype](migration-interop-guidance-for-teams-with-skype.md)

[設定商務用 Skype Server與Microsoft 365或Office 365之間的混合式連線](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存與升級設定](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[使用會議移轉服務 (MMS) ](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

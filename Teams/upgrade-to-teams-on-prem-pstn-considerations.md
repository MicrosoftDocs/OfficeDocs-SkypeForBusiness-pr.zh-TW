---
title: 從 商務用 Skype 升級至 Teams 時的 PSTN 考慮
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 從 商務用 Skype 升級到 Teams 的語音考慮
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 130ff6164de3cae82902487f70dd6eaefb631c27
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681344"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>從內部部署升級至 Teams 的 PSTN 考慮商務用 Skype

本文將說明公用交換電話網路 (PSTN) 升級至 Teams 時的考慮。

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

下列文章說明重要的升級概念和共存行為：

- [Teams與商務用 Skype的共存](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [共存模式 - 參照](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 用戶端體驗和遵從共存模式](teams-client-experience-and-conformance-to-coexistence-modes.md)

> [!NOTE]
>
> - 只有當使用者的帳戶獲指派Teams僅限Teams模式的升級原則時，才支援搭配電話系統Teams。
> - 只有當使用者的帳戶獲派 SfB 模式的Teams升級原則時，才支援搭配商務用 Skype使用電話系統。
> - 當使用者的帳戶獲指派與群島模式Teams升級原則時，電話系統不受支援。
> - 任何來自商務用 Skype的來電轉接、小組通話群組和委派設定都不會移轉，您必須重新建立Teams。
> - 如需Microsoft Teams雲端語音功能的一般概觀，以及協助決定最適合貴組織的 Microsoft 語音解決方案，請參閱[規劃您的Teams語音解決方案](cloud-voice-landing-page.md)。

## <a name="pstn-calling-scenarios"></a>PSTN 通話案例

移至 TeamsOnly 模式時，有四種可能的通話案例：

- [商務用 Skype Online 中的使用者，且有 Microsoft 通話方案](#from-skype-for-business-online-with-microsoft-calling-plans)。 升級後，此使用者將繼續擁有 Microsoft 通話方案。

- [商務用 Skype Online 中的使用者，](#from-skype-for-business-online-with-on-premises-voice)可透過內部部署或雲端連接器版本商務用 Skype內部部署語音功能。 若要確保 TeamsOnly 使用者具備 PSTN 功能，您必須協調使用者升級至Teams與使用者移轉至直接路由。

- 商務用 Skype內部部署[且擁有企業語音的使用者](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)，將會移至線上並保持內部部署 PSTN 連線能力。  若要將此使用者移轉到Teams，您必須將使用者的內部部署商務用 Skype帳戶移至雲端，並與使用者移轉到直接路由進行協調。

- [商務用 Skype](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)內部部署且有企業語音的使用者，將會移至線上並使用 Microsoft 通話方案。  若要將此使用者移轉到Teams，您必須將使用者的內部部署商務用 Skype帳戶移至雲端。 您必須與 A) 該使用者電話號碼的埠協調移動至 Microsoft 通話方案，或 B) 從可用地區指派新的訂閱者號碼。

本文僅提供高層級概觀。 如需詳細資訊，[請參閱電話系統直接路由](direct-routing-landing-page.md)和[通話方案。](calling-plan-landing-page.md)

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>從 商務用 Skype Online 與 Microsoft 通話方案

此案例是涉及語音的最簡單升級案例。

1. 確認使用者已獲指派Teams授權。 根據預設，當您指派Microsoft 365或Office 365授權時，會啟用Teams。 除非您先前停用Teams授權，否則不需要採取任何動作。

2. 如果使用者已經有含有電話號碼的 Microsoft 通話方案，唯一的必要變更是指派使用者 Teams TeamsUpgradePolicy 中的 TeamsOnly 模式。 指派 TeamsOnly 模式之前，PSTN 來電會撥入使用者的商務用 Skype用戶端。 升級至 TeamsOnly 模式之後，PSTN 來電會接到使用者Teams用戶端。

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>從 商務用 Skype Online 使用內部部署語音

在此案例中，使用者已經在 商務用 Skype Online 中。 使用者的 PSTN 連線是內部部署，使用混合式模式中的商務用 Skype Server或雲端連接器版本。 若要使用 PSTN 功能將這些使用者移轉到 TeamsOnly 模式，您必須啟用使用者進行直接路由。 透過直接路由，PSTN 主幹會透過內部部署會話框線控制器直接連線至直接路由服務 (SBC) 。

基本步驟如下所列。  步驟 1 到 4 會依建議順序列出，但可以依任何循序執行。 這些步驟應在步驟 5 之前完成。

1. 如果您將整個租使用者的原則設定為其中一種商務用 Skype模式，請務必明確指派任何現有的群島使用者，如先前所述指派「群島」模式。

2. 設定您的租使用者以進行直接路由。 請參閱 [直接路由之每個租使用者設定的摘要](#summary-of-per-tenant-configuration-of-direct-routing)。

3. 如有需要，請為這些使用者設定各種Teams原則 (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等) 。 您可以隨時設定小工具。 不過，如果您想要確保使用者在升級時擁有正確的設定，請先設定這些原則，再將使用者升級至 TeamsOnly 模式。

4. 準備選取的使用者進行語音移轉：
   - 如有需要，請指派Teams授權。  假設使用者已在 商務用 Skype Online 內部部署語音中運作，使用者已商務用 Skype方案 2 和 Microsoft 電話 系統。 讓這兩個方案保持啟用，包括商務用 Skype線上方案 2 授權。
   - 指派所需的 OnlineVoiceRoutingPolicy。

5. 升級使用者：這些步驟應該是協調的。

   - 在 Microsoft 365 或 Office 365 中，將使用者升級至 TeamsOnly 模式 (Grant-CsTeamsUpgradePolicy) 。
   - 在 SBC 上，將來電傳送到直接路由，而不是內部部署的中接伺服器，藉此設定語音路由以啟用來電。

## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>從商務用 Skype Server內部部署、含企業語音，到直接路由

在此案例中，使用者仍會在內部部署商務用 Skype。 使用者的 PSTN 連線也是內部部署。 若要使用 PSTN 功能將此使用者移轉到 TeamsOnly 模式，您必須啟用使用者進行直接路由，然後將使用者移至雲端。

基本步驟如下所列。 步驟 1 到 5 會依建議順序列出，但可以依任何循序執行。 您必須在步驟 6 之前完成步驟 1-5。

1. 如果您將全租使用者原則設定為其中一種商務用 Skype模式，請務必明確指派現有群島使用者，如先前所述指派「群島」模式。

2. 如果您尚未這麼做，請為[組織設定商務用 Skype混合式](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。

3. 設定您的租使用者以進行直接路由。 請參閱 [直接路由之每個租使用者設定的摘要](#summary-of-per-tenant-configuration-of-direct-routing)。

4. 如有需要，請為這些使用者設定各種Teams原則， (例如 TeamsMessagingPolicy、TeamsMeetingPolicy) 。 您可以隨時設定原則。 不過，如果您想要確保使用者在升級時擁有正確的設定，請先設定這些原則，再將使用者升級至 TeamsOnly。

5. 視需要指派Microsoft 365或Office 365授權。  使用者應該同時擁有 Teams 和 商務用 Skype Online 方案 2 和 電話系統。 如果 商務用 Skype Online 方案 2 已停用，請重新啟用。

6. 升級使用者：這些步驟應該是協調的。

   - 使用內部部署商務用 Skype工具，使用 -MoveToTeams 參數執行Move-CsUser。 如果您使用的是不支援 -MoveToTeams 切換的商務用 Skype Server版本，請先執行Move-CsUser，然後在租使用者遠端 PowerShell 或Teams 管理員主機上指派 TeamsOnly 模式。

   - 在 SBC 上，將來電傳送到直接路由，而不是內部部署的中接伺服器，藉此設定語音路由以啟用來電。

   - 在 Microsoft 365 或Office 365：指派相關的 OnlineVoiceRoutingPolicy 來啟用撥出電話。

## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>從商務用 Skype Server內部部署、企業語音，到 Microsoft 通話方案

在此案例中，使用者仍會在內部部署商務用 Skype。 使用者的 PSTN 連線也是內部部署。 若要將此使用者移轉到具有 PSTN 功能的 TeamsOnly 模式，您必須將使用者移至雲端，並將其號碼從舊電信業者移轉至 Microsoft 通話方案，或將新號碼指派給使用者。

基本步驟如下所列。 步驟 1 到 5 會依建議順序列出，但可以依任何循序執行。 您必須在步驟 6 之前完成步驟 1-5。

1. 如果您將全租使用者原則設定為其中一種商務用 Skype模式，請務必明確指派現有群島使用者，如先前所述指派「群島」模式。

2. 如果您尚未這麼做，請為[組織設定商務用 Skype混合式](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。

3. 如有需要，請為這些使用者設定各種Teams原則 (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等) 。 您可以隨時設定原則。 不過，如果您想要確保使用者在升級時擁有正確的設定，請先設定這些原則，再將使用者升級至 TeamsOnly。

4. 視需要指派Microsoft 365或Office 365授權。 使用者應該同時擁有 Teams 和 商務用 Skype Online 方案 2 和 電話系統。 如果 商務用 Skype Online 方案 2 已停用，請重新啟用。

5. 為您的使用者取得電話號碼。  (如需詳細資料，請參閱 [管理組織的電話號碼](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。) 

   - 如果您要重複使用號碼，請向您的電信業者提交移轉要求。
   - 或者，您可以直接從 Microsoft 取得新的數位。

6. 升級使用者，並視需要指派 LineUri。 使用內部部署商務用 Skype工具，使用 -MoveToTeams 參數執行Move-CsUser。

    - 如果您要將號碼移轉到 Microsoft，您應該協調在埠發生時執行此作業的時間。

    - 如果您使用來自 Microsoft 的新號碼，您必須在使用 Set-CsPhoneNumberAssignment 將使用者移到線上之後，變更使用者的 LineUri。

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>直接路由之每個租使用者設定的摘要

1. 檢閱 [此清單](direct-routing-border-controllers.md)，確認會話框線控制器 (SBC) 支援直接路由。 也請確定您擁有正確的韌體版本。

2. 將您的內部部署 SBC 與Teams直接路由服務配對。 如需詳細資料，請參閱[將 SBC 與 電話系統 的直接路由服務配對](direct-routing-configure.md)。

3. 此設定基本上是內部部署設定的鏡像。 線上設定包含：
   - OnlineVoiceRoutingPolicy (在從 商務用 Skype Online 移轉使用者時，根據內部部署 VoiceRoutingPolicy，以及在使用 企業語音) 從內部部署移轉使用者時根據 VoicePolicy。
   - OnlinePSTN根據內部部署 PSTN 使用)  (物件。
   - OnlineVoiceRoute 物件 (內部部署 VoiceRoute) 。

如需詳細資訊，請參閱 [設定直接路由](direct-routing-configure.md)。

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>在移轉期間管理 EnterpriseVoiceEnabled 屬性

無論是使用直接路由還是 Microsoft 通話方案，使用者必須在 Azure AD 中擁有 EnterpriseVoiceEnabled=true，使用者才能使用 PSTN 功能。  EnterpriseVoiceEnabled (「EV-enabled」) 是屬性 (不是存在於內部部署目錄和雲端的原則) 。 雲端中的值對於Teams來說很重要。  啟用 EV 的確切邏輯設定為 True 取決於下列案例：

- 如果使用者已在內部部署商務用 Skype Server啟用 EV，且在使用 Move-CsUser 將使用者移至雲端之前，已指派電話系統授權給使用者，線上使用者將會布建 EV-enabled=true。

- 如果已將現有 TeamsOnly 或 商務用 Skype Online 使用者指派電話系統授權，則根據預設，啟用 EV 的功能未設為 True。 如果內部部署使用者在指派電話系統授權之前已移至雲端，也會發生這種情況。 無論哪種情況，系統管理員都必須指定下列 Cmdlet：

  ```PowerShell
  Set-CsPhoneNumberAssignment -EnterpriseVoiceEnabled $True
  ```

## <a name="related-links"></a>相關連結

[規劃Teams語音解決方案](cloud-voice-landing-page.md)

[搭配使用Teams的組織移轉和互通性指導方針商務用 Skype](migration-interop-guidance-for-teams-with-skype.md)

[設定商務用 Skype Server與Microsoft 365或Office 365之間的混合式連線](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存與升級設定](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[使用會議移轉服務 (MMS) ](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

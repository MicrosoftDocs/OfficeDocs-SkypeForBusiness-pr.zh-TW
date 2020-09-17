---
title: 從商務用 Skype 內部部署（Microsoft 團隊）升級至團隊
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 從商務用 Skype 升級至 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c7156c02dff45e170efde9314c15b5688fd43058
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940627"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a>針對 IT 系統管理員使用商務用 Skype Server 內部部署之組織的升級考慮事項 &mdash;

本文將說明使用商務用 Skype Server 內部部署之組織的其他考慮事項。 本文是幾個描述 IT 系統管理員升級概念與實現的第四個專案。  

- [概觀](upgrade-to-teams-on-prem-overview.md)
- [升級方法](upgrade-to-teams-on-prem-upgrade-methods.md)
- [管理升級的工具](upgrade-to-teams-on-prem-tools.md)
- **使用商務用 Skype 內部部署之組織的其他考慮事項** (本文) 
- [實施升級](upgrade-to-teams-on-prem-implement.md)
- [公用交換電話網絡 (PSTN) 考慮](upgrade-to-teams-on-prem-pstn-considerations.md)

此外，下列文章說明重要的升級概念與共存行為：

- [團隊與商務用 Skype 的共存](upgrade-to-teams-on-prem-coexistence.md)
- [共存模式-參考](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 用戶端體驗和遵從共存模式](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a>商務用 Skype Server 內部部署的組織考慮事項

- 設定商務用 Skype 混合式版是遷移至 TeamsOnly 模式的先決條件。 雖然您可以在沒有混合式的孤島模式下使用小組，但在使用者從商務用 Skype 內部部署移至商務用 skype Online (使用 [move-csuser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)) 時，才無法進行。 如需詳細資訊，請參閱 [設定混合式連線性](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)。

- 如果您的組織有商務用 Skype Server，而且您還沒有設定混合式連線性，但您仍想要使用團隊來管理團隊功能，您必須使用具有 onmicrosoft.com 網域的系統管理帳戶。 

- 擁有商務用 Skype 帳戶內部部署 (的小組使用者，尚未使用移動瀏覽器將其移到雲端，) 無法與任何商務用 Skype 使用者進行交互操作，也無法與外部使用者聯盟。 此功能只有在使用者移到雲端 (以孤島模式或 TeamsOnly 使用者) 時才可使用。 

- 如果您擁有內部部署商務用 Skype 帳戶的任何使用者，則不能在租使用者層級指派 TeamsOnly 模式，除非您明確地將部分其他模式指派給使用內部部署商務用 Skype 帳戶的所有使用者。 

- 您必須確保您的使用者能以正確的商務用 Skype 屬性正確地同步處理到 Azure AD。 這些屬性都是含 "msRTCSIP-" 的所有首碼。 如果使用者未正確地同步處理到 Azure AD，小組中的管理工具將無法管理這些使用者。  (例如，除非正確同步處理這些屬性，否則您無法將團隊原則指派給內部部署使用者 ) 。如需詳細資訊，請參閱 [設定團隊與商務用 Skype 的 AZURE AD Connect](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)。

- 若要在混合式組織中建立新的 TeamsOnly 或商務用 Skype Online 使用者， *您必須先在內部部署中啟用商務用 Skype Server 中的使用者*，然後使用 move-csuser 將使用者從內部部署移至雲端。  首先，在內部部署中建立使用者，以確保任何其他剩餘的內部部署商務用 Skype 使用者都能傳送給新建立的使用者。 當所有使用者都在線上移動之後，就不再需要先在內部部署中啟用使用者。

- 當使用者從內部部署移至雲端時，由該使用者組織的會議會遷移到商務用 Skype Online 或團隊中，視是否已指定-MoveToTeams 開關而定。

- 如果您想要在內部部署使用者的商務用 Skype 用戶端中顯示通知，您必須在內部部署工具集中使用 TeamsUpgradePolicy。 只有 NotifySfbUsers 參數與內部部署使用者有關。  內部部署使用者從 TeamsUpgradePolicy 的線上實例接收它們的模式。 請參閱授與 [授與 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)中的筆記。 

>[!NOTE]
> 2019在9月3日之後建立的任何新租使用者都會建立為 TeamsOnly 租使用者，除非組織已有內部部署的商務用 Skype 伺服器。 Microsoft 會使用 DNS 記錄來識別內部部署商務用 Skype 伺服器組織。 如果您的組織有內部部署商務用 Skype Server （沒有公用 DNS 專案），您必須致電 Microsoft 支援人員來降級新的租使用者。 



















## <a name="related-links"></a>相關連結

[與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南](migration-interop-guidance-for-teams-with-skype.md) 

[在商務用 Skype Server 與 Microsoft 365 或 Office 365 之間設定混合式連接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存與升級設定](setting-your-coexistence-and-upgrade-settings.md)

[授與 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用會議遷移服務 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)


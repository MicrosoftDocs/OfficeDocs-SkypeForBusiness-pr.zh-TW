---
title: 從商務用 Skype 內部部署（Microsoft 團隊）升級至團隊
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 從商務用 Skype 升級至 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8030f1504e56fb6bd9aee528e7969c9d66bf8c96
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328232"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>從商務用 Skype 升級至 &mdash; 適用于 IT 系統管理員的小組

## <a name="overview"></a>概觀

當您從商務用 Skype 升級至小組時，某些組織必須逐步推出由其 IT 部門規劃和管理的漸進式推出。 本節中的文章主要適用于大型組織中的 IT 系統管理員。 這些組織通常是內部部署的，但也可能是大型商務用 Skype Online 組織。 閱讀這些文章前，請務必閱讀 [您的小組升級](upgrade-start-here.md) 和 [升級架構](upgrade-framework.md)的入門。


下列文章將引導您完成貴組織的升級程式： 

- [升級方法](upgrade-to-teams-on-prem-upgrade-methods.md)
- [管理升級的工具](upgrade-to-teams-on-prem-tools.md)
- [使用商務用 Skype 內部部署之組織的其他考慮事項](upgrade-to-teams-on-prem-considerations.md)
- [實施您的升級](upgrade-to-teams-on-prem-implement.md)
- [公用交換電話網絡 (PSTN) 考慮](upgrade-to-teams-on-prem-pstn-considerations.md)

此外，下列文章說明重要的升級概念與共存行為：

- [團隊與商務用 Skype 的共存](upgrade-to-teams-on-prem-coexistence.md)
- [共存模式-參考](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 用戶端體驗和遵從共存模式](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
>這些文章使用 [商務用 Skype Online]、[商務用 skype 伺服器內部部署] 和 [商務用 Skype] 這兩個術語。 後一詞指的是線上和內部部署版本。

在您開始之前，請注意，已遷移至團隊的使用者不再使用商務用 Skype 用戶端，除非加入在商務用 Skype 中託管的會議。  無論寄件者是使用小組或商務用 Skype，所有傳入聊天和呼叫使用者團隊用戶端中的土地。 由遷移使用者組織的任何新會議，都會排程為團隊會議。 如果使用者嘗試使用商務用 Skype 用戶端，就會封鎖聊天和通話的啟動。  不過，使用者可以 (，而且必須) 使用商務用 Skype 用戶端來加入受邀的商務用 Skype 會議。  (在2017之前隨附的舊版商務用 Skype 用戶端不提供 TeamsUpgradePolicy。 請確定您使用的是最新的商務用 Skype 用戶端。 ) 
 
您可以使用 [模式](migration-interop-guidance-for-teams-with-skype.md)的概念（ [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)的屬性）來管理您的使用者對團隊的轉場。 如上述所述，按照上述方式遷移至團隊的使用者，請參閱「TeamsOnly」模式。  對於遷移至團隊的組織而言，最終目標是將所有使用者移至 TeamsOnly 模式。

>[!NOTE]
>擁有商務用 Skype 內部部署帳戶的使用者無法 TeamsOnly。 雖然這些使用者可以 [在孤島模式中使用團隊](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)，但這不會提供完整的小組功能（在 TeamsOnly 模式中提供）。 若要讓這些使用者 TeamsOnly，必須 `Move-CsUser` 在內部部署商務用 Skype Server 工具中將其移至雲端。

還行。 讓我們開始吧。  第一個步驟是瞭解 [您可以使用的升級方法](upgrade-to-teams-on-prem-upgrade-methods.md)。







   

## <a name="related-links"></a>相關連結

[與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南](migration-interop-guidance-for-teams-with-skype.md) 

[在商務用 Skype Server 與 Microsoft 365 或 Office 365 之間設定混合式連接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存與升級設定](setting-your-coexistence-and-upgrade-settings.md)

[授與 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用會議遷移服務 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)


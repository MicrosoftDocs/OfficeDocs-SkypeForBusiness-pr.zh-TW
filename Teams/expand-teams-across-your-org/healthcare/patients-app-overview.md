---
title: '適用于團隊管理員的患者應用程式 '
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto: Microsoft Teams
ms.reviewer: anach
description: 適用于團隊管理員的患者應用程式
ms.openlocfilehash: 85f0d382de11b9259c6839aa8d0e556ad2512f5a
ms.sourcegitcommit: 2064c94eae82a5453674d38f0b28dcd6dc5c370e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/30/2019
ms.locfileid: "37885497"
---
# <a name="patients-app-overview"></a>病患應用程式概觀

患者應用程式是適用于所有團隊使用者的 Microsoft 團隊商店應用程式。 應用程式可讓患者護理小組（例如護士、醫生、社會工人）彙整和審閱患者的清單，這些案例包括從倒圓角和 interdisciplinary 團隊會議到一般患者監控等。   

App 有兩種模式： 

- 透過 FHIR 連接至 EMRs 的 EMR 連線模式。 EMR 連線模式 app 會保留在私人預覽中，感興趣的客戶或系統管理員可能會透過在 teamsforhealthcare@service.microsoft.com 中除去 Microsoft 電子郵件，並提供其 Office 365 租使用者的相關資訊，以要求存取 app。 
- [手動] 模式可讓護理小組手動新增/攜帶患者資訊。 您可以在 [團隊 app] 商店中找到該應用程式，預設會供使用者下載，且位於公用預覽中。 在 Microsoft 團隊中，您可以使用[應用程式設定原則](../../teams-app-setup-policies.md)，將 app 限制在某些使用者區段中



## <a name="usage-example"></a>用法範例

在醫學 wards 的每個倒班期間，臨床醫師在 nursing 站上收集，以在 ward 中與患者進行最新的更新。  它們會醒目提示重要的度量單位（不一定是醫療，或是其在患者病歷上的明確），並確保患者在適當的 glide 路徑上，以根據其診斷來放電。 為了圍繞這些患者，[費用護士] 會在新增所有臨床醫師的小組中設定患者應用程式，並將患者新增至患者清單。 在舍入期間，在行動裝置上的患者 access Microsoft 團隊和患者應用程式的護士與其他護理 givers，並更新其裝置上的相關患者資訊，並在護理小組中的其他人都能看到這些更新與記事，以及保持同步處理。一天兩次，在班次的開始和結束，他們也會有多位 displicinary 小組會議，透過患者清單進行，並使用患者 App 來建立每個患者的相關資訊，並使用大型顯示畫面上的患者 app 分享有關每個患者的資訊。 通常情況下，某些臨床醫師可能也會在遠端撥入這些團隊會議，而且仍是討論的一部分。 

## <a name="configure-patients-app"></a>設定患者 app

如需如何準備您的環境以使用 EMR 模式患者 app 的詳細資訊，請參閱將[電子醫療保健記錄整合至 Microsoft 團隊](patients-app.md)。 您也需要[在 Microsoft 團隊中查看 [管理應用程式設定原則](../../teams-app-setup-policies.md)]，以便為您的組織啟用患者 app。

<!-- For information on how your end users can access and install the Patients App to a team that they own or manage, you will need to see [End user documentation for the Patients App]() -->

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>常見問題（FAQ）

**患者應用程式資料儲存在哪裡？**

使用者在患者 App 中輸入的所有資料（包括欄/欄位架構），在清單及清單專案（亦即患者）中輸入的實際資料都儲存在安全相容的 Exchange Online 基礎結構中。 所有資料都儲存在與小組相關聯的群組信箱中。 這個架構可讓患者 App 輕鬆地完成資料派駐、政府雲端支援（未來），以及 eDiscovery 支援等其他合規性/資訊保護功能。 患者 app 會在團隊範圍中運作。 您將需要安裝每個團隊的 app 實例。

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**我可以從哪裡取得患者應用程式？**

如果患者 app 由其系統管理員啟用，任何使用者都可以移至 [小組] app 商店，並將患者 app 新增至他們所屬的小組。 如需詳細資訊，請參閱[在 Microsoft 團隊中管理 app 設定原則](../../teams-app-setup-policies.md)。

**我可以在小組中有多個患者應用程式實例，因為我的 ward/單元的運作方式為何？**

目前，您只能針對特定團隊安裝一個患者應用程式實例，且僅適用于 [一般] 頻道。 不過，在應用程式中，可以建立多個清單來處理多聲道或隔離/分隔案例。 根據預設，小組中的所有成員都會有權存取 [一般] 頻道中的 [患者] 索引標籤。 

**我可以從患者 app 匯出所有資料嗎？**
目前尚不提供此功能，但即將推出這項功能。 

**因為這個 app 可容納 PHI，所以是否有審核來防止未經授權的存取或合規性遵從管理法規？**

是的，就是。 Microsoft 團隊使用者在患者 app 上執行的每個單一 UI 動作都會在安全性與合規性中心進行審核並提供。 [本文將](patients-audit.md)說明詳細資料


## <a name="related-topics"></a>相關主題

[將電子醫療保健記錄整合至 Microsoft Teams](patients-app.md)

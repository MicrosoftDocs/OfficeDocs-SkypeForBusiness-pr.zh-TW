---
title: 使用 Microsoft Teams 限域目錄搜尋
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何使用 Microsoft 團隊範圍的目錄搜尋來提供目錄的自訂視圖。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e81e2fb588e718060ffbdf90a51c020ff2d6556c
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326590"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>使用 Microsoft Teams 限域目錄搜尋

Microsoft 團隊範圍的目錄搜尋可讓組織建立虛擬邊界，以控制使用者如何在組織中找到其他使用者並與之通訊。 

Microsoft 團隊可讓組織為使用者提供目錄的自訂視圖。 Microsoft 團隊使用[資訊屏障原則](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)來支援這些自訂視圖。 啟用原則後，搜尋由其他使用者所傳回的結果（例如，啟動聊天或將成員新增至團隊）將會根據設定的原則來設定範圍。 當作用中的搜尋生效時，使用者將無法搜尋或探索團隊。 

> [!NOTE]
> 在 Exchange 混合式環境中，這項功能僅適用于 Exchange Online 信箱，不適用於內部部署信箱。

## <a name="when-should-you-use-scoped-directory-searches"></a>您何時應該使用範圍的目錄搜尋？

從範圍目錄搜尋獲益的案例，與通訊錄原則案例類似。 例如，您可能會想在下列情況下使用範圍內的目錄搜尋：

- 貴組織的租用戶中有多家公司，您想要將其分開。 
- 學校需要限制教職員與學生之間的交談。 
 
若要瞭解如何使用通訊錄原則，請參閱[Exchange Online 中的資訊屏障原則](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)。

> [!IMPORTANT]
> 通訊錄原則只提供從目錄角度來看使用者的虛擬隔離。 使用者仍可提供完整的電子郵件地址，以與其他人發起通訊。 另外，請務必注意，在強制執行新的或更新的通訊錄原則之前，已進行過快取的任何使用者資料，都會持續提供給最多30天的使用者。

## <a name="turn-on-scoped-directory-search"></a>開啟作用中的目錄搜尋

1. 使用資訊屏障原則將您的組織設定為虛擬子群組。 如需詳細資訊，請參閱[定義資訊屏障原則](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies)。

2. 在 Microsoft [團隊管理中心] 中，選取 [全**組織性設定**  >  **團隊設定**]。

3. 在 [**搜尋**] 底下，在**使用 Exchange 通訊錄原則（ABP）的 [小組] 中的 [範圍目錄搜尋**] 旁，開啟 **[開啟]。**

    ![Microsoft 團隊系統管理中心的作用中目錄搜尋範圍](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> 這項變更可能需要幾個小時才能進行複製。

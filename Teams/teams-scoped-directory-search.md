---
title: 使用 Microsoft Teams 限域目錄搜尋
author: SerdarSoysal
ms.author: serdars
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
description: 瞭解如何使用Microsoft Teams目錄搜尋來提供目錄的自訂視圖。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: df03c4d59b55780f38b5f99983a11fd5dc905e40
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587012"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>使用 Microsoft Teams 限域目錄搜尋

Microsoft Teams目錄搜尋功能可讓組織建立虛擬邊界，控制使用者如何尋找及與組織中其他使用者通訊。 

Microsoft Teams可讓組織提供目錄的自訂視圖給使用者。 Microsoft Teams資訊[障礙策略來](/microsoft-365/compliance/information-barriers)支援這些自訂視圖。 一旦啟用該政策，搜尋其他使用者 (例如啟動聊天或新增成員至小組) 所返回的結果，就會根據已配置的政策進行範圍。 當範圍搜尋生效時，使用者將無法搜尋或探索任何團隊，但這些團隊中的現有成員可以新增使用者，如使用中的資訊障礙政策所允許。

> [!NOTE]
> 在Exchange環境中，此功能僅適用于Exchange Online信箱，而非內部部署信箱。

另請參閱在 Exchange Online[中的通訊錄Exchange Online。](/exchange/address-books/address-book-policies/address-book-policies)

## <a name="when-should-you-use-scoped-directory-searches"></a>何時應該使用範圍目錄搜尋？

從範圍目錄搜尋獲益的情境與通訊錄策略案例類似。 例如，您可能會想要在下列情況下使用範圍目錄搜尋：

- 貴組織的租用戶中有多家公司，您想要將其分開。 
- 學校需要限制教職員與學生之間的交談。 
 
若要瞭解如何使用通訊錄政策，請參閱在 Exchange Online 中[的資訊Exchange Online。](/microsoft-365/compliance/information-barriers)

> [!IMPORTANT]
> 通訊錄原則僅提供使用者與目錄的虛擬分隔。 此外，請注意，在強制執行新的或更新的通訊錄政策之前，任何已緩存的使用者資料，都會在最多 30 天內可供使用者使用。

## <a name="turn-on-scoped-directory-search"></a>開啟範圍目錄搜尋

1. 使用資訊隔層策略將貴組織設定為虛擬子組。 詳細資訊，請參閱定義 [資訊障礙政策](/microsoft-365/compliance/information-barriers-policies)。

2. 在 Microsoft Teams系統管理中心中，選取整個 **組織** 範圍的設定  >  **Teams設定**。

3. 在 **搜尋** 下，使用 ABP Teams 通訊錄Teams目錄搜尋Exchange **ABP** (，) 開啟 **。**

    ![系統管理中心中的Microsoft Teams目錄搜尋](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> 此變更可能需要數小時才能複製。

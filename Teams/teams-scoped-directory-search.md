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
description: 瞭解如何使用 Microsoft Teams 範圍目錄搜尋來提供目錄的自訂視圖。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1ba7de8cea23efc23f1eaa6c568d87b0d3ec750
ms.sourcegitcommit: e29e38bf00536400e5826fc55bc86dfd6ed761f3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/08/2021
ms.locfileid: "50558322"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>使用 Microsoft Teams 限域目錄搜尋

Microsoft Teams 範圍目錄搜尋可讓組織建立虛擬界限，控制使用者如何尋找及與組織中其他使用者通訊。 

Microsoft Teams 可讓組織提供目錄的自訂視圖給使用者。 Microsoft Teams 會 [使用資訊隔層策略](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) 來支援這些自訂視圖。 一旦啟用該政策，搜尋其他使用者所返回的結果 (例如，啟動聊天或新增成員至小組) 將會根據已配置之策略來界定範圍。 當範圍搜尋生效時，使用者將無法搜尋或探索任何團隊，但這些團隊中的現有成員可以新增使用者，如作用中資訊障礙政策所允許。

> [!NOTE]
> 在 Exchange 混合式環境中，此功能僅適用于 Exchange Online 信箱，無法與內部部署信箱一起使用。

## <a name="when-should-you-use-scoped-directory-searches"></a>何時應該使用範圍目錄搜尋？

從範圍目錄搜尋獲益的情境與通訊錄政策案例類似。 例如，您可能會想要在下列情況下使用範圍目錄搜尋：

- 貴組織的租用戶中有多家公司，您想要將其分開。 
- 學校需要限制教職員與學生之間的交談。 
 
若要瞭解如何使用通訊錄策略，請閱讀 Exchange [Online 的資訊障礙政策](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)。

> [!IMPORTANT]
> 通訊錄原則僅提供從目錄的觀點虛擬分隔使用者。 另請注意，在強制執行新的或更新的通訊錄政策之前，任何已緩存的使用者資料，最多會保留 30 天。

## <a name="turn-on-scoped-directory-search"></a>開啟範圍目錄搜尋

1. 使用資訊障礙策略將貴組織設定為虛擬子組。 詳細資訊請參閱定義 [資訊障礙政策](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies)。

2. 在 Microsoft Teams 系統管理中心，選取 **整個組織設定**  >  **Teams 設定**。

3. 在 **搜尋下**，在 Teams 中使用 Exchange 通訊錄 (**ABP) ，** 開啟 **切換開關**。

    ![Microsoft Teams 系統管理中心的目錄範圍搜尋](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> 這項變更可能需要數小時的時間才能複製。

---
title: 在 Teams 中搜尋目錄時限制使用者可以查看的人員
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何在 Teams 中搜尋目錄時限制使用者可以查看的人員。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: c20c5acdafff69e5a43f02093b515b456daa8ff7
ms.sourcegitcommit: 193aec6f3f6b6ac14b07e778b3485eed813f5e99
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/13/2022
ms.locfileid: "66046425"
---
# <a name="limit-who-users-can-see-when-searching-the-directory-in-teams"></a>在 Teams 中搜尋目錄時限制使用者可以查看的人員

Microsoft Teams可讓組織為使用者提供目錄的自訂檢視。 這些檢視在下列情況中很有用：

- 貴組織的租用戶中有多家公司，您想要將其分開。
- 您的商務原則要求您防止組織中的特定群組彼此通訊。
- 學校需要限制教職員與學生之間的交談。

有兩個選項可限制使用者在 Teams 中搜尋目錄時可以看到的人員：

- [Microsoft Teams 中的資訊障礙](/MicrosoftTeams/information-barriers-in-teams)
- [Exchange Online 中的通訊錄原則](/exchange/address-books/address-book-policies/address-book-policies)

如果使用任一選項，您必須在Teams系統管理中心開啟依名稱搜尋。

如果貴組織符合 [必要的授權和許可權](/microsoft-365/compliance/information-barriers#required-licenses-and-permissions)，建議您使用資訊障礙。

開啟依名稱搜尋

1. 在Microsoft Teams系統管理中心中，選 **Teams**  >  **Teams設定。**

1. 在 [**依名稱搜尋**] 底下的 [**使用 Exchange通訊錄原則搜尋範圍目錄**] 旁，開啟 [開啟 **] 切換開關**。

> [!Note]
> 可能需要幾個小時，此變更才會生效。
> 
> 開啟 [依名稱搜尋] 會隱藏 [在 Teams 中 **加入或建立團隊**] 中的 [**搜尋團隊**] 方塊和公開團隊清單。 它也會在Teams頂端的命令方塊中輸入 `/join` ，停用加入團隊的功能。

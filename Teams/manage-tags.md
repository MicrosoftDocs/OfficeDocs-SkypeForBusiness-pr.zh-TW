---
title: 管理 Microsoft 團隊中的標記
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中管理組織中使用標記的方式。
ms.openlocfilehash: 5fbfa980f1cf6acd8ce32af810bf2527ece3d1fa
ms.sourcegitcommit: 0549714f17f9994cf832a303ec9bc58a537c3a51
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2020
ms.locfileid: "42951548"
---
# <a name="manage-tags-in-microsoft-teams"></a>管理 Microsoft 團隊中的標記

Microsoft 團隊中的標記可讓使用者與團隊中的人員子集進行通訊。 您可以將標籤新增至一或多個小組成員，輕鬆地與正確的人員子集連線。 小組擁有者和成員（如果已為他們啟用功能）可以在人員中新增一或多個標記。 然後，您就可以 @mentions 使用這些標籤，讓團隊中的任何人都能使用這些標籤，或只與已分派該標記的人員開始交談。

> [!NOTE]
> 在私有通道中尚不支援標記。 在美國政府社區雲端（GCC）、GCC 高或國防（DoD）組織中尚不提供標記。 

## <a name="how-tags-work"></a>標記的運作方式

您可以將標記新增至特定小組中的人員。 新增標籤之後，就可以在聊天的 @mentions 中或在團隊的任何標準頻道中使用它。 以下是如何在團隊中使用標記的一些範例：

- 商店管理員想要張貼公告至頻道並通知所有出納。
- 群組產品經理想要將頻道中的所有產品經理宣傳。
- 醫院管理員想要傳送訊息給頻道中的所有 radiologists。
- 行銷經理想要與所有設計人員一起開始進行群組聊天。 

若要深入瞭解，請參閱[在團隊中使用標記](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)。

## <a name="manage-tags-for-your-organization"></a>管理貴組織的標記

身為系統管理員，您可以控制誰可以新增標記，以及如何在 Microsoft 團隊系統管理中心的整個組織中使用標記。

![Microsoft 團隊系統管理中心的標記設定的螢幕擷取畫面](media/manage-tags-admin-settings.png)

### <a name="set-who-can-add-tags"></a>設定誰可以新增標記

根據預設，小組擁有者可以新增標記。 您可以變更此設定，以允許小組擁有者和小組成員新增標籤，或者您可以關閉組織的標記。

1. 在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**全組織性設定** > **團隊設定**]。
2. 在 [**標記**] 底下的 [**標記已啟用**] 旁，選取下列其中一個選項：

    - **小組擁有者和成員**：允許小組擁有者和成員新增標記。
    - **小組擁有**者：允許小組擁有者新增標記。
    - [**已停用**]：關閉標記。

### <a name="configure-tags-settings"></a>設定標籤設定

您可以設定下列標記設定，以控制如何在整個組織中使用標記。

1. 在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**全組織性設定** > **團隊設定**]。
2. 根據貴組織的需求，在 [**標記**] 底下設定下列各項。

    - **小組擁有者可以覆寫可以**套用標籤的人員：開啟此選項時，小組擁有者可以允許或不允許成員在團隊設定中新增標記。
    - **成員可以新增其他**標籤：如果您允許小組成員新增標籤，請開啟此選項，讓小組成員新增除了您所設定的預設標記以外的其他標記。 如果您關閉此功能，小組成員只能使用預設的標記。
    - **建議的預設**標籤：使用這個功能來新增一組預設的標籤。 您可以新增最多25個標籤，每個標籤最多可包含25個字元。 小組擁有者和成員（如果已為他們啟用功能）可以使用這些建議、新增至他們，或建立一組新的標記。

## <a name="manage-tags-settings-for-a-team"></a>管理團隊的標記設定

如果您開啟 [**小組擁有者可以覆寫**Microsoft 團隊系統管理中心中可以套用標籤] 設定的人員，小組擁有者可以設定成員是否可以在小組層級新增標記。 若要這樣做，請在團隊的 [**設定**] 索引標籤上，移至 [標籤 **]，然後**選擇誰可以新增標記。

![小組層次上的 [標籤] 設定的螢幕擷取畫面](media/manage-tags-team-settings.png)

## <a name="add-tags-in-teams"></a>在團隊中新增標記

在團隊中，小組的 [管理團隊] 頁面上的 [**成員**] 索引標籤包含 [**標記**] 欄。 小組擁有者和成員（如果已為他們啟用功能）可以按一下成員旁的 [**管理標記**]，即可查看該成員的建議標記清單，並將標記新增到清單中。

![如何在團隊用戶端套用標記的螢幕擷取畫面 ](media/manage-tags-teams.png) 

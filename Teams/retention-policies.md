---
title: Microsoft 團隊中的保留原則
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 使用 Microsoft 團隊的保留原則來保留遵守內部原則、行業法規或法律需求所需的訊息，以及刪除被視為責任或沒有合法商業價值的訊息。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aba9858466b43693603aa4a1cd396748d2c83d6e
ms.sourcegitcommit: def4b475b785a7b963f499cf9a1044e842ff66a5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2021
ms.locfileid: "49786825"
---
# <a name="retention-policies-in-microsoft-teams"></a>Microsoft 團隊中的保留原則

Microsoft 365 的保留原則和保留標籤可協助您更有效率地管理組織中的資訊。 您可以設定保留設定，以保留遵守貴組織的內部原則、行業法規或法律需求所需的資料。 您也可以設定保留設定，以刪除被視為債務的資料、您不再需要保留的資料，或是沒有任何法律或業務價值的資料。

團隊支援聊天和通道訊息的保留原則，以便管理員決定是否要保留這些資料、刪除該資料，或保留一段特定的時間，然後刪除。 您可以將團隊保留原則套用到整個組織或特定的使用者與團隊。 小組不支援保留標籤。

若要深入瞭解保留，以及如何在 Microsoft 365 中使用保留原則或其他工作負荷的保留標籤來套用保留設定，請參閱 [瞭解保留原則和保留標籤](https://docs.microsoft.com/microsoft-365/compliance/retention)。

小組保留原則的最低授權需求是 Microsoft 365 E3。 若要深入瞭解授權，請參閱 [Microsoft 團隊服務說明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。

## <a name="how-teams-retention-policies-work"></a>團隊保留原則的運作方式

團隊聊天訊息會儲存在聊天中每位使用者信箱的隱藏資料夾中，而團隊頻道訊息則會儲存在小組的群組信箱中類似的隱藏資料夾中。 若要保留受保留原則制約的郵件，內容的複本會自動保留在名為 **SubstrateHolds** 的隱藏資料夾中，做為 [Exchange 可復原的 **專案** ] 資料夾中的子資料夾。 在這些郵件從 SubstrateHolds 資料夾中永久刪除前，這些訊息會保持透過 eDiscovery 工具的搜尋。

如需小組保留原則所包含及排除之內容的詳細資訊，以及這些原則的運作方式，請參閱 [瞭解 Microsoft 團隊的保留](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)情況。

> [!NOTE]
> 這個頁面會說明為何保留原則刪除郵件時，可能會發生延遲。 例如，郵件在保留原則中設定的到期期限之後，最多可顯示7天。

如果您使用不同的保留設定設定多個小組保留原則，保留原則會解決任何衝突。 例如：
- 如果在保留或刪除相同內容時發生衝突，該內容會一直保留下來。
- 如果您保留相同內容的時間有多長，則會保留較長的保留期間。

當您有多個小組保留原則時，這些保留位址的兩個原則可能會產生大多數衝突，但如需詳細資訊，請參閱 [保留原則或優先順序為何？](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>何時使用小組的保留原則

在許多情況下，組織會考慮使用私人聊天資料，而不是頻道訊息，通常是更多與專案相關的交談。

您可以針對私人聊天 (1:1 或1：設定個別的保留原則，) 與頻道訊息。 您也可以設定適用于組織中特定使用者或團隊的唯一原則。 針對 [團隊聊天]，您可以選取要套用原則的使用者。 針對團隊頻道訊息，您可以選取要套用原則的小組。

例如，對於頻道訊息，您可以將一年刪除原則套用到貴組織中的特定小組，並將三年的刪除原則套用至所有其他團隊。

## <a name="create-and-manage-retention-policies-for-teams"></a>建立及管理團隊的保留原則

若要建立小組聊天與頻道訊息的保留原則，請使用 [小組位置的保留原則](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)中的指示。

此頁面包含有關在 Microsoft 365 中建立及管理其他工作負荷之保留原則的其他相關資訊。 例如，您可能會想要為 Microsoft 365 群組建立保留原則，以保留並刪除在小組中存取並儲存在 OneDrive 或 SharePoint 中的檔案。  

## <a name="end-user-experience"></a>使用者體驗

針對私人聊天 (1:1 聊天) 或群組聊天，最終使用者將會看到舊版的聊天與保留原則設定會被刪除，而「我們已刪除您組織的保留原則」等「我們已刪除較舊的郵件」的控制訊息會顯示在尚未刪除的郵件上。

:::image type="content" source="media/retention-policies-image1.png" alt-text="因團隊保留原則而刪除聊天訊息的小組中的使用者":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="小組中的使用者會因小組保留原則而刪除訊息":::

對於頻道訊息，) 的使用者 (頻道成員將會看到郵件過期後，已刪除的郵件會從視野中消失。 如果已刪除的郵件是有線程交談的父郵件，則會顯示一則訊息，指出「此郵件已因保留原則而刪除」。

:::image type="content" source="media/retention-policies-image3.png" alt-text="在保留之前先頻道的螢幕擷取畫面":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保留期間的頻道螢幕擷取畫面":::

> [!NOTE]
> 最終使用者看到的已刪除訊息結果的顯示訊息，此時無法進行設定。


## <a name="related-topics"></a>相關主題

- [開始使用保留原則和保留標籤](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-retention)
- [瞭解 Microsoft 團隊的保留](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)
- [建立及設定保留原則](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies)
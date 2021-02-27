---
title: 管理 Microsoft Teams 的保留政策
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 使用 Microsoft Teams 的保留原則，保留符合內部原則、產業法規或法律需求所需的郵件，並刪除被視為責任或無法律商業價值的郵件。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3b0197d9a5cf9ada93ac16ad083f293b573c4eed
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347653"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>管理 Microsoft Teams 的保留政策

> [!NOTE]
> 如果您是在 Teams 中看到訊息的使用者，該訊息指出您的聊天和訊息已由保留原則刪除，請參閱 Teams 關於保留原則 [的訊息](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。
> 
> 本頁面上的資訊適用于管理這些保留原則的 IT 系統管理員。

Microsoft 365 的保留政策與保留標記可協助您更有效地管理貴組織的資訊。 您可以設定保留設定，以保留符合貴組織內部政策、產業法規或法律需求所需的資料。 您也可以設定保留設定，刪除被視為責任、不再需要保留，或沒有任何法律或商務價值的資料。

Teams 支援聊天和頻道訊息的保留政策，因此，您可以主動決定是否要保留、刪除或保留資料一段特定時間，然後再將其刪除。 您可以將 Teams 保留原則適用于整個組織或特定的使用者和團隊。 Teams 不支援保留標記。

若要深入瞭解保留，以及如何在 Microsoft 365 中為其他工作負載使用保留原則或保留標籤來申請保留設定，請參閱瞭解保留原則 [與保留標籤](https://docs.microsoft.com/microsoft-365/compliance/retention)。

Teams 保留原則的最低授權需求為 Microsoft 365 E3。 若要深入瞭解授權，請參閱 Microsoft [Teams 服務描述](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。

## <a name="how-teams-retention-policies-work"></a>Teams 保留政策如何執行

Teams 聊天訊息會儲存在聊天中包含的每個使用者信箱中的隱藏資料夾中，而 Teams 頻道訊息會儲存在團隊群組信箱中的類似隱藏資料夾中。 若要保留受保留政策限制的郵件，內容複本會自動保留在名為 **Holds** 的隱藏資料夾中，做為 **Exchange** 可復原的專案資料夾中的子資料夾。 在這些郵件從Holds 資料夾永久刪除之前，eDiscovery 工具仍然可以搜尋這些郵件。

如需 Teams 保留政策包含與排除之內容的詳細資訊，以及這些策略如何根據您的策略組組而執行，請參閱深入瞭解 Microsoft Teams 的[保留。](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

> [!NOTE]
> 此頁面會說明為什麼保留原則刪除郵件時，有時可能會看到延遲。 例如，在您于保留政策中所配置的到期日後，最多 7 天可以看到郵件。

如果您使用不同的保留設定設定多個 Teams 保留原則，保留原則會解決任何衝突。 例如：
- 如果保留或刪除相同內容之間發生衝突，則一直保留內容。
- 如果保留相同內容的時間有衝突，會保留最長保留期間。

這兩個保留原則可解決當您有多個 Teams 保留原則時所可能產生的衝突，但詳細資訊請參閱保留原則，或 [優先處理哪些專案？](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>何時使用 Teams 的保留政策

在許多情況下，組織將私人聊天資料視為比頻道訊息更多的責任，頻道訊息通常更與專案相關的交談。

您可以針對私人聊天設定個別的保留 (1：1 或 1：) 和頻道訊息。 您也可以設定適用于貴組織中特定使用者或團隊的唯一原則。 對於 Teams 聊天，您可以選取原則所適用的使用者。 對於 Teams 頻道訊息，您可以選取原則所適用的團隊。

例如，針對頻道訊息，您可以將一年刪除原則適用于貴組織的特定團隊，並針對所有其他團隊使用三年刪除原則。

## <a name="create-and-manage-retention-policies-for-teams"></a>建立及管理 Teams 的保留政策

若要建立 Teams 聊天和頻道訊息的保留政策，請使用 Teams 位置的保留政策 [指示](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)。

該頁面包含有關在 Microsoft 365 中建立和管理其他工作負載保留原則的其他資訊。 例如，您可能也想要建立 Microsoft 365 群組的保留原則，以保留和刪除在 Teams 中存取並儲存在 OneDrive 或 SharePoint 中的檔案。  

## <a name="end-user-experience"></a>使用者經驗

對於私人聊天 (1 對 1 聊天) 或群組聊天，使用者會看到比保留政策組組更舊的聊天被刪除，且會在尚未刪除的郵件上方顯示「我們已因為貴組織保留政策而刪除較舊的訊息」的自動產生訊息。 例如：

:::image type="content" source="media/retention-policies-image1.png" alt-text="在 Teams 中通知使用者，由於 Teams 保留政策而刪除聊天訊息":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Teams 中的使用者說明訊息會因為 Teams 保留政策而被刪除":::

針對頻道訊息， (頻道成員) 會在郵件到期後看到已刪除的郵件從視野消失。 如果刪除的郵件是對話對話的父郵件，則會顯示一則訊息，指出「此郵件已因保留政策而遭到刪除」，以做為父訊息。 例如：

:::image type="content" source="media/retention-policies-image3.png" alt-text="保留前頻道的螢幕擷取畫面":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保留後頻道的螢幕擷取畫面":::

> [!NOTE]
> 使用者因刪除的郵件而看到的顯示訊息目前無法進行設置。

這些顯示的郵件中的連結會前往 [Teams 關於保留政策的郵件](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。 本文適用于使用者，可協助回答關於其郵件為何遭到刪除的基本問題。 不過，在保留原則部署中，請務必與使用者及技術支援人員溝通您設定設定的影響。

## <a name="related-topics"></a>相關主題

- [開始使用保留原則和保留標記](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-retention)
- [瞭解 Microsoft Teams 的保留](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)
- [建立及設定保留原則](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies)
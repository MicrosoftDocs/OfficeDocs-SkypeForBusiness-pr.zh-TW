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
description: 使用 Microsoft Teams 的保留原則，保留符合內部原則、產業法規或法律需求所需的郵件，以及刪除被視為責任或沒有法律商業價值的郵件。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d7d998afb47480fa59ce936a93e20af9ac4b2a12
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117601"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>管理 Microsoft Teams 的保留政策

> [!NOTE]
> 如果您在 Teams 中看到一則訊息，指出您的聊天或訊息已由保留原則刪除，請參閱 [Teams 關於保留政策的郵件](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。
> 
> 此頁面的資訊適用于管理這些保留原則的 IT 系統管理員。

Microsoft 365 的保留原則和保留標籤可協助您更有效地管理貴組織的資訊。 您可以設定保留設定，以保留符合貴組織的內部政策、產業法規或法律需求所需的資料。 您也可以設定保留設定，刪除被視為責任、不再需要保留或沒有法律或商務價值的資料。

Teams 支援聊天和頻道訊息的保留政策，這樣您才能主動決定是否要保留、刪除或保留資料一段時間，然後再刪除。 您可以將 Teams 保留原則適用于整個組織或特定使用者和團隊。 Teams 不支援保留標籤。

若要深入瞭解保留，以及如何針對 Microsoft 365 中其他工作負載使用保留原則或保留標籤來適用保留設定，請參閱瞭解保留原則與保留 [標籤](/microsoft-365/compliance/retention)。

Teams 保留政策的最低授權需求為 Microsoft 365 E3。 若要深入瞭解授權，請參閱 Microsoft [Teams 服務描述](/office365/servicedescriptions/teams-service-description)。

## <a name="how-teams-retentiondeletion-policies-work"></a>Teams 保留/刪除政策如何工作

Teams 聊天訊息會儲存在兩個位置。 主要副本會儲存在 Azure 中，這是用於編譯策略的次要副本，會儲存在聊天中每個使用者的 Exchange Online 信箱中的隱藏資料夾中，而 Teams 頻道訊息則儲存在小組群組信箱中的類似隱藏資料夾中。 當聊天訊息刪除原則適用于使用者或小組時，次要副本會先刪除，後面接著主要副本。 eDiscovery 或 Teams 搜尋是根據儲存在次要副本中的郵件所產生，因此當次要副本刪除時，郵件便無法被發現。 

當聊天訊息保留問題已適用于使用者或小組時，如果郵件因另一個刪除原則 (或使用者本身) 而刪除，主複本就會刪除，因此 Teams 用戶端會看到郵件消失，但次要複本會自動移至名為 **Holds** 的隱藏資料夾 ，該資料夾是 Exchange 可復原專案資料夾中的子資料夾。  在這些郵件從Holds 資料夾永久刪除之前，這些郵件仍然可于 eDiscovery 工具中搜尋。

如需 Teams 保留政策包含和排除哪些內容，以及這些策略如何根據您的策略組組而執行的詳細資訊，請參閱瞭解[Microsoft Teams 的保留。](/microsoft-365/compliance/retention-policies-teams)

> [!NOTE]
> 此頁面會說明為什麼保留原則刪除郵件時，有時候可能會看到延遲。 例如，在您于保留政策中所配置的到期日後，最多 7 天可以看見郵件。

如果您使用不同的保留設定設定多個 Teams 保留原則，保留原則會解決任何衝突。 例如：
- 如果保留或刪除相同內容之間發生衝突，內容會一直保留。
- 如果保留相同內容的時間有衝突，該內容會保留最長保留期間。

這兩個保留原則可解決當您有多個 Teams 保留原則時，可能會出現的衝突，但如需要詳細資訊，請參閱保留原則，或優先處理 [哪些原則？](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>何時使用 Teams 的保留政策

在許多情況下，組織將私人聊天資料視為比頻道訊息更相關的責任，而頻道訊息通常更與專案相關的交談。

您可以針對私人聊天設定個別的保留 (1：1 或 1：多聊天) 頻道訊息。 您也可以設定適用于貴組織中特定使用者或團隊的唯一原則。 針對 Teams 聊天，您可以選取原則所適用的使用者。 針對 Teams 頻道訊息，您可以選取原則所適用的團隊。

例如，針對頻道訊息，您可以將一年的刪除原則適用于貴組織的特定團隊，並針對所有其他團隊適用三年刪除原則。

## <a name="create-and-manage-retention-policies-for-teams"></a>建立及管理 Teams 的保留政策

若要為 Teams 聊天和頻道訊息建立保留原則，請使用 Teams 位置的保留政策 [中的指示](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)。

此頁面提供有關在 Microsoft 365 中建立及管理其他工作負載保留原則的其他資訊。 例如，您可能也想要為 Microsoft 365 群組建立保留原則，以保留和刪除 Teams 中存取並儲存在 OneDrive 或 SharePoint 中的檔案。  

## <a name="end-user-experience"></a>使用者經驗

對於私人聊天 (1：1 聊天) 或群組聊天，使用者會看到刪除保留原則組配置的較舊的聊天，而自動產生的訊息會指出「我們已因為貴組織保留政策而刪除較舊的訊息」，顯示在尚未刪除的郵件上方。 例如：

:::image type="content" source="media/retention-policies-image1.png" alt-text="在 Teams 中通知使用者聊天訊息會因為 Teams 保留政策而刪除":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Teams 中說明郵件的使用者會因為 Teams 保留政策而刪除":::

針對頻道訊息， (頻道) 使用者會看到已刪除的郵件在郵件過期後從視圖中消失。 如果刪除的郵件是對話對話的父郵件，則會顯示一則訊息，指出「此郵件已因保留政策而遭到刪除」，以代之父訊息。 例如：

:::image type="content" source="media/retention-policies-image3.png" alt-text="保留前頻道的螢幕擷取畫面":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保留後頻道的螢幕擷取畫面":::

> [!NOTE]
> 使用者目前無法針對已刪除的郵件看到顯示的郵件進行配置。

這些顯示的郵件中的連結會前往 [Teams 關於保留原則的郵件](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。 此適用于使用者的檔可協助回答有關其郵件為何遭到刪除的基本問題。 不過，在保留原則部署中，請確定您與使用者和技術支援人員溝通您設定設定的影響。

## <a name="related-topics"></a>相關主題

- [開始使用保留原則和保留標籤](/microsoft-365/compliance/get-started-with-retention)
- [瞭解 Microsoft Teams 的保留](/microsoft-365/compliance/retention-policies-teams)
- [建立及設定保留政策](/microsoft-365/compliance/create-retention-policies)
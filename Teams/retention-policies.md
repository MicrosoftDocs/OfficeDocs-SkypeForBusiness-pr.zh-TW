---
title: 管理 Microsoft Teams 的保留原則
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 使用 Microsoft Teams 保留原則，以保留有關貴組織需要遵守的內部原則、產業法規或法律要求的訊息，並刪除視為有責任或沒有法律商業價值的郵件。
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- tier1
- purview-compliance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 806e7f6dd3bccf9df74a97d537bcddc2e4b60979
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2022
ms.locfileid: "68047103"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>管理 Microsoft Teams 的保留原則

> [!NOTE]
> 如果您在 Teams 訊息中得知保留原則已刪除聊天或訊息，請參閱 [關於保留原則的 Teams 訊息](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。
> 
> 本頁面上的資訊適用於管理這些保留原則的 IT 系統管理員。

Microsoft 365 的保留原則和保留標籤可協助您更有效地管理組織中的資訊。 您可以設定保留原則，以保留符合貴組織的內部原則、產業法規或法律要求所需的資料。 您也可以設定保留設定以刪除被視為負債的資料、不再需要保留的資料，或沒有法律或商業價值的資料。

Microsoft Teams 支援適用於聊天和頻道訊息的保留原則，所以身為系統管理員，您可以主動決定是否要保留資料、刪除資料，或保留特定的一段時間然後刪除。 這些動作的保留期間啟動一律取決於訊息建立的時間。 您可以將 Teams 保留原則套用到整個組織或特定的使用者和小組。 Microsoft Teams 不支援保留標籤。

> [!NOTE]
> 保留原則支援[共用頻道](shared-channels.md)。

若要深入了解 Microsoft 365 中的保留解決方案，請參閱 [瞭解保留原則和保留標籤](/microsoft-365/compliance/retention)。

受 Microsoft Teams 保留原則限制的使用者必須擁有適當的授權，例如 Office 365 E3 或 Office 365 A3。 如需這些保留原則的其他授權選項，請參閱[Microsoft 365 安全性&合規性授權指導方針的Microsoft Purview 資料生命週期管理](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)一節。[ ](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-data-lifecycle-management) 若要深入瞭解 Microsoft Teams 授權，請參閱 [Microsoft Teams 服務描述](/office365/servicedescriptions/teams-service-description)。

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a>Microsoft Teams 保留原則支援保留和刪除動作的方式

如果您將 Teams 保留原則設定為保留聊天或頻道訊息，使用者仍然可以在 Microsoft Teams 應用程式中編輯和刪除其訊息。 雖然使用者不會再看到他們在 Teams 中預先編輯或刪除的訊息，但來自這些訊息的資料會儲存在安全的位置，該位置是專為合規性系統管理員的電子文件探索搜尋所設計。 此資料不會遭到永久刪除直到已設定的保留期間結束，或如果已設定其他保留原則保留此資料，或受到 [eDiscovery 保留](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds)。

當保留原則已設定為刪除聊天和頻道訊息時，這些訊息就符合自動刪除的資格。 如果訊息仍在 Teams 應用程式中顯示，這些訊息都將在此處消失，且 [使用者會收到通知表示保留原則已刪除這些訊息](#end-user-experience)。 如果訊息先前受到保留動作的限制，且已由使用者進行編輯或刪除，這些訊息將會在安全的位置遭到刪除，且不會再於電子文件探索搜尋中傳回。

如需根據原則設定和使用者動作的原則運作方式，以及 Teams 保留原則包含和排除哪些訊息資料的詳細資訊，請參閱 [瞭解 Microsoft Teams 的保留](/microsoft-365/compliance/retention-policies-teams)。 該頁面也會說明為什麼當保留原則刪除郵件時，您有時可能會遇到延遲的原因。 例如，在保留原則中，在到期期間後的 7 天內，Teams 應用程式中的使用者可以看到訊息。

如果您使用不同的保留設定設定多個 Teams 保留原則，保留的原則會解決任何衝突。 例如：

- 如果保留或刪除相同內容之間發生衝突，內容會一律保留在安全的位置，以便維持其可搜尋性使合規性系統管理員使用 eDiscovery 進行搜尋。
    
    此原則也會套用至因法律或調查理由而受到電子文件探索保留的訊息。

- 如果保留相同內容的時間長短出現衝突，系統會將此內容以最長的保留期間保留在安全的位置中。

當您擁有多個 Teams 保留原則時，這兩個保留原則可以解決大多數可能發生的衝突，但如需詳細資訊，請參閱 [原則保留或何者優先？](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>何時要使用 Teams 的保留原則？

在許多情況下，組織會認為私人聊天資料比頻道訊息有更多的責任，通常是和專案更相關的交談。

您可以非常有效率地為所有 Teams 訊息設定單一保留原則。 或者，如需更精細的控制措施，您可以：

- 針對私人聊天 (1：1 或 1：多聊天) 、來自標準頻道的訊息或來自私人頻道的訊息，有個別的保留原則。

- 只將原則套用至組織中的特定使用者或小組。 針對 Teams 聊天和私人頻道，您可以選取原則適用的使用者。 如果是使用 Teams 頻道訊息，您可以選取原則要套用到哪些小組。

例如，針對標準頻道訊息：為貴組織中的特定團隊建立保留原則，並在 1 年後以刪除動作設定該原則。 然後為所有其他團隊建立另一個標準頻道訊息的保留原則，並在 3 年後以刪除動作設定該原則。

## <a name="create-and-manage-retention-policies-for-teams"></a>建立和管理 Microsoft Teams 保留原則

若要建立或編輯 Teams 訊息的保留原則，請使用 [Teams 位置保留原則的](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)指示。

該頁面提供有關為 Microsoft 365 中的其他工作負載，建立和管理保留原則的其他資訊。 例如，您可能也想要為 Microsoft 365 群組建立保留原則，以保留和刪除在 Teams 中存取並儲存於 OneDrive 或 SharePoint 中的檔案。  

## <a name="end-user-experience"></a>使用者體驗

對於私人聊天 (1:1 聊天) 或群組聊天，使用者會看到時間早於保留原則組態的聊天遭到刪除，並在在尚未刪除的訊息上方顯示一個自動產生的訊息，表示「我們已因貴組織保留原則而刪除較舊的訊息」。 例如：

:::image type="content" source="media/retention-policies-image1.png" alt-text="在 Teams 中通知使用者，聊天訊息會因為 Teams 保留原則而遭刪除。":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Teams 中說明訊息的使用者會因為 Teams 保留原則而刪除。":::

對於頻道訊息，使用者 (頻道成員) 會在訊息過期後看到已刪除的訊息在檢視中消失。 如果刪除的訊息是往來交談的父郵件，則會顯示一則訊息，說明「此訊息已因保留原則而遭到刪除」。 例如：

:::image type="content" source="media/retention-policies-image3.png" alt-text="保留前頻道的螢幕擷取畫面。":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保留後頻道的螢幕擷取畫面。":::

> [!NOTE]
> 使用者因刪除郵件而看到的訊息顯示為目前無法進行設定。

這些顯示訊息中的連結會移至 [Teams 保留原則的訊息](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。 此份使用者的文件可協助回答有關為何訊息遭到刪除的基本問題。 不過，作為保留原則部署的一部分，請確定您向使用者和技術支援中心表達您已配置的設定影響。

## <a name="related-topics"></a>相關主題

- [開始使用保留原則和保留標籤](/microsoft-365/compliance/get-started-with-retention)
- [了解 Microsoft Teams 保留](/microsoft-365/compliance/retention-policies-teams)
- [建立及設定保留原則](/microsoft-365/compliance/create-retention-policies)
- 疑難排解：[保留原則意外刪除 Teams 和 Yammer 應用程式中的訊](/microsoftteams/troubleshoot/teams-im-presence/messages-unexpectedly-deleted-retention-policy)息

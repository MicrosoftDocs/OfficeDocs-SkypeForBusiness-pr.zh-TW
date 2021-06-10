---
title: 管理保留Microsoft Teams
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 使用適用于 Microsoft Teams 的保留原則，保留貴組織需要遵守內部原則、產業法規或法律要求的郵件，以及刪除被視為責任或沒有法律商業價值的郵件。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ec6b257f91c7e5003a4a69079e37b20b5f338528
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617755"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>管理保留Microsoft Teams

> [!NOTE]
> 如果您在郵件中看到一則Teams聊天或訊息已被保留政策刪除，請參閱Teams[保留政策相關訊息](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。
> 
> 此頁面的資訊適用于管理這些保留原則的 IT 系統管理員。

來自貴組織的保留Microsoft 365保留標籤，可協助您更有效地管理貴組織的資訊。 您可以設定保留設定，以保留符合貴組織的內部政策、產業法規或法律要求所需的資料。 您也可以設定保留設定，刪除被視為責任、不再需要保留或沒有法律或商務價值的資料。

Teams聊天和頻道訊息的保留政策，這樣您才能主動決定是否要保留、刪除或保留資料一段時間，然後再刪除。 這些動作的保留期間開始一直取決於郵件的建立時間。 您可以將保留原則Teams整個組織或特定使用者和團隊。 系統不支援保留Teams。

若要進一Microsoft 365保留解決方案，請參閱瞭解保留[策略和保留標籤](/microsoft-365/compliance/retention)。

受系統保留政策Teams使用者必須擁有適當的授權，Office 365 E3 或 Office 365 A3。 有關這些保留原則的其他授權選項，請參閱安全性與合規性[](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)Microsoft 365授權指南[&>一節](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)。 若要深入瞭解授權服務Teams，請參閱Microsoft Teams[描述](/office365/servicedescriptions/teams-service-description)。

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a>保留Teams如何支援保留和刪除動作

如果您設定保留Teams保留聊天或頻道訊息，使用者仍然可以編輯及刪除其應用程式中的郵件Teams訊息。 雖然使用者在 Teams 中不會再看到其預先編輯或刪除的郵件，但來自這些郵件的資料會儲存在安全的位置，該位置是專為合規性系統管理員為 eDiscovery 搜尋所設計。 此資料的永久刪除不會在已配置的保留期間結束之前，或如果另一個保留原則已配置為保留此資料，或受到 [eDiscovery](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds)保留。

當保留原則已配置為刪除聊天和頻道訊息時，這些郵件就符合自動刪除資格。 如果郵件仍顯示在 Teams應用程式中，這些郵件會從該位置消失，且使用者會得知保留原則已刪除[這些郵件](#end-user-experience)。 如果郵件先前受保留動作所保護，且使用者已編輯或刪除，這些郵件現在會從安全位置刪除，且不會再在 eDiscovery 搜尋中退回。

如需根據您的策略組組和使用者動作，以及 Teams 保留政策包含及排除哪些郵件資料的詳細資訊，請參閱瞭解保留[Microsoft Teams。](/microsoft-365/compliance/retention-policies-teams) 該頁面也會說明為什麼保留原則刪除郵件時，您有時會遇到延遲。 例如，在保留政策中Teams期限後 7 天內，Teams App 中的使用者可以看到郵件。

如果您使用不同的保留設定Teams多個保留原則，保留原則會解決任何衝突。 例如：

- 如果保留或刪除相同內容之間發生衝突，內容會一直保留在安全的位置，以便合規性系統管理員使用 eDiscovery 來搜尋內容。
    
    這項原則也適用于因法律或調查理由而以電子檔探索保留為理由的郵件。

- 如果保留相同內容的時間有衝突，該內容會保留于安全位置中最長保留期間。

這兩個保留原則可解決當您有多個 Teams 保留原則時，可能會出現的衝突，但如需要詳細資訊，請參閱保留原則，或優先處理[哪些原則？](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>何時使用保留Teams

在許多情況下，組織將私人聊天資料視為比頻道訊息更相關的責任，而頻道訊息通常更與專案相關的交談。

您可以針對私人聊天設定個別的保留 (1：1 或 1：多聊天) 頻道訊息。 您也可以設定適用于貴組織中特定使用者或團隊的唯一原則。 針對Teams聊天，您可以選取原則所適用的使用者。 針對Teams訊息，您可以選取原則所適用的團隊。

例如，針對頻道訊息，您可以將保留原則適用于貴組織的特定團隊，且該原則在 1 年後會以刪除動作進行配置。 然後，將另一個保留原則適用于所有其他團隊，且該原則在 3 年後會以刪除動作進行配置。

## <a name="create-and-manage-retention-policies-for-teams"></a>建立及管理保留Teams

若要建立或編輯聊天和Teams訊息的保留政策，請使用保留Teams[指示](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)。

該頁面包含有關在 Microsoft 365 中建立及管理其他工作負載的保留Microsoft 365。 例如，您可能也想要為 Microsoft 365 群組建立保留原則，以保留和刪除在 Teams 中存取並儲存在 OneDrive 或 SharePoint 中的檔案。  

## <a name="end-user-experience"></a>使用者體驗

對於私人聊天 (1：1 聊天) 或群組聊天，使用者會看到刪除保留原則組配置的較舊的聊天，而自動產生的訊息會指出「我們已因為貴組織保留政策而刪除較舊的訊息」，會顯示在尚未刪除的郵件上方。 例如：

:::image type="content" source="media/retention-policies-image1.png" alt-text="使用者Teams聊天訊息會因為保留Teams而刪除":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="在Teams中說明郵件的使用者會因為保留Teams而刪除":::

針對頻道訊息， (頻道) 使用者會看到已刪除的郵件在郵件過期後從視圖中消失。 如果刪除的郵件是討論執行緒交談的父郵件，則會顯示一則訊息，指出「此郵件已因保留政策而遭到刪除」，以代之父訊息。 例如：

:::image type="content" source="media/retention-policies-image3.png" alt-text="保留前頻道的螢幕擷取畫面":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保留後的頻道螢幕擷取畫面":::

> [!NOTE]
> 使用者目前無法針對已刪除的郵件看到顯示的郵件進行配置。

這些顯示的郵件中的連結會Teams[保留政策相關之郵件](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。 此適用于使用者的檔可協助回答有關其郵件為何遭到刪除的基本問題。 不過，在保留原則部署中，請確定您與使用者和技術支援人員溝通您設定設定的影響。

## <a name="related-topics"></a>相關主題

- [開始使用保留原則和保留標籤](/microsoft-365/compliance/get-started-with-retention)
- [瞭解保留Microsoft Teams](/microsoft-365/compliance/retention-policies-teams)
- [建立及設定保留政策](/microsoft-365/compliance/create-retention-policies)

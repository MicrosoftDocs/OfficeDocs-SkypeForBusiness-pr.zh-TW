---
title: Microsoft Teams 的敏感度標籤
ms.author: mikeplum
author: cabailey
manager: laurawi
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用敏感度標籤來保護 Microsoft Teams 中的團隊。
ms.openlocfilehash: 461daf6e91f9ba276dceef1929601d1188563931
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593861"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Microsoft Teams 的敏感度標籤

[敏感度標籤](/microsoft-365/compliance/sensitivity-labels) 可允許 Teams 系統管理員保護並規範在團隊內共同合作期間所建立之機密組織內容的存取權。 在 Microsoft 合規性中心設定敏感度標籤及其關聯原則之後[](/microsoft-365/compliance/go-to-the-securitycompliance-center)，這些標籤可以適用于貴組織的小組。

使用 Teams Education SKUs 的客戶目前在課程團隊中不支援敏感度標籤。 若要深入瞭解授權，請參閱 Microsoft [Teams 服務描述](/office365/servicedescriptions/teams-service-description)。

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>敏感度標籤和 Teams 分類標籤之間有什麼不同？

敏感度標籤與分類標籤不同，也稱為 Azure AD 群組分類。 分類標籤是可與 Microsoft 365 群組相關聯的文字字串，但沒有任何與其相關聯的實際政策。 您可以使用分類標籤做為中繼資料，然後必須使用其他方法 ，例如內部工具和腳本，以強制執行策略。

使用敏感度標籤的好處，是透過 Microsoft 365 群組平臺、合規性中心和 Teams 服務的組合，自動強制執行其政策。 敏感度標籤提供強大的基礎結構支援，可保護組織的機密資料，並確保符合您的內部政策或法規。

如果您目前使用分類標籤，請參閱下列檔以進一步瞭解如何將它們遷移到敏感度標籤： [傳統 Azure AD 群組分類](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)。

## <a name="example-scenarios-for-sensitivity-labels"></a>敏感度標籤的範例案例

如何在貴組織中將敏感度標籤用於 Teams 的範例案例：

- [設定團隊的 (或私人) 層級](#set-the-privacy-level-for-teams)
- [控制團隊的來賓存取權](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>設定團隊的隱私權等級

您可以建立和設定敏感度標籤，在建立小組時，允許使用者建立具有特定隱私權的小組， (公開或) 設定。

例如，您建立併發布名為「機密」的敏感度標籤，其標籤隱私權選項已配置為 **「私人」。** 因此，使用此標籤建立的任何團隊都必須是私人團隊。 

當使用者建立新團隊並選取機密標籤時，使用者唯一可用的隱私權選項是 **私人**。 使用者無法選取其他隱私權選項 ，例如公用和全組織：

![機密敏感度標籤的螢幕擷取畫面](media/sensitivity-labels-confidential-example.png)

同樣地，您建立併發布名為「一般」的敏感度標籤，其標籤隱私權選項已配置為 **公用**。 當使用者建立新團隊時，他們只有在選取此標籤時，才能建立公用或全組織團隊：

![一般敏感度標籤的螢幕擷取畫面](media/sensitivity-labels-general-example.png)

建立團隊時，敏感度標籤會顯示在團隊頻道的右上角。 

> [!NOTE]
> 如果您使用的是階層式父子標籤 ，例如「機密\財務」，則只有父標籤會顯示在頻道標題中。

![小組頻道中敏感度標籤的螢幕擷取畫面](media/sensitivity-labels-channel.png)

團隊擁有者可以隨時變更小組的敏感度標籤和隱私權設定，方法為進入團隊，然後按一下 [ **編輯團隊**。

![小組屬性中敏感度標籤的螢幕擷取畫面](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>控制團隊的來賓存取權

您可以使用敏感度標籤來控制來賓對團隊的存取權。 使用不允許來賓存取的標籤所建立的團隊，只有貴組織的使用者才能使用。 組織外部人員無法新加入團隊。

## <a name="microsoft-teams-admin-center"></a>Microsoft Teams 系統管理中心

您可以在 Microsoft Teams 系統管理中心建立或編輯團隊時，使用敏感度標籤。 

敏感度標籤也會顯示在小組屬性中，以及 Microsoft  Teams 系統管理中心的管理小組頁面上的分類欄。

## <a name="limitations"></a>限制

使用 Teams 的敏感度標籤之前，請注意下列限制：

- **子標籤不會顯示父標籤名稱**
    
    Teams 支援子標記，但不會顯示父標籤的名稱。 例如 **，機密** \\ **所有員工會顯示** 為 **所有員工**。

- **Teams Graph API、PowerShell Cmdlet 和範本不支援敏感度標籤**
    
    使用者無法透過 Teams Graph API、Teams PowerShell Cmdlet 和 Teams 範本直接建立團隊時指定敏感度標籤。 不過，新式群組圖形 API 和 PowerShell Cmdlet 允許使用標籤建立群組。 因此，使用者可以先使用群組圖形 API 或 PowerShell Cmdlet 建立具有標籤的群組，然後將這些群組轉換成 Teams。

- **支援私人頻道**
    
    在團隊中建立的私人頻道會繼承已用於團隊的敏感度標籤。 相同的標籤會自動用於私人頻道的 SharePoint 網站集合。
    
    不過，如果使用者直接變更私人頻道 SharePoint 網站上敏感度標籤，該標籤變更不會反映在 Teams 用戶端中。 在此情境中，使用者會繼續在私人頻道標題中看到在小組上所應用的原始敏感度標籤。

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>如何建立及設定 Teams 的敏感度標籤

使用 Microsoft 365 檔的指示建立和設定 Teams 的敏感度標籤： 

- [使用敏感度標籤來保護 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。

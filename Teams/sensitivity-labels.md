---
title: 自訂的敏感度Microsoft Teams
ms.author: cabailey
author: cabailey
manager: laurawi
ms.reviewer: shubjain
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
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何使用敏感度標籤來保護您Microsoft Teams。
ms.openlocfilehash: 135049e80d6a8c0e008886ca924cca64b5943695
ms.sourcegitcommit: 9fd9cfe3683503f3c35ad5591324396e2532caef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2021
ms.locfileid: "59496690"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>自訂的敏感度Microsoft Teams

[敏感度標籤](/microsoft-365/compliance/sensitivity-labels)Teams管理員保護並規範在團隊內共同合作期間所建立之機密組織內容的存取權。 在 Microsoft 合規性中心中設定敏感度標籤及其關聯原則[](/microsoft-365/compliance/go-to-the-securitycompliance-center)之後，這些標籤可以適用于貴組織的小組。

使用教育用 SKUs 的客戶目前不支援課程團隊中的敏感度Teams標籤。 若要深入瞭解授權，請參閱Microsoft Teams[描述](/office365/servicedescriptions/teams-service-description)。

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification"></a>敏感度標籤與分類分類Teams差異？

敏感度標籤與分類不同Teams也稱為 Azure AD 群組分類。 分類是文字字串，可以與Microsoft 365群組相關聯，但沒有任何與其相關的實際政策。 您可以使用分類做為中繼資料，然後必須使用其他方法 ，例如內部工具和腳本，以強制執行策略。

使用敏感度標籤的好處是，透過 Microsoft 365 群組平臺、合規性中心及服務的組合，自動強制執行其Teams。 敏感度標籤提供強大的基礎結構支援，可保護組織的機密資料，並確保符合您的內部政策或法規。

如果您目前使用Teams分類，請參閱下列檔以進一步瞭解如何將這些值轉換成敏感度標籤：[傳統 Azure AD 群組分類](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)。

## <a name="example-scenarios-for-sensitivity-labels"></a>敏感度標籤的範例案例

如何在組織中將敏感度標籤用於Teams範例案例：

- [設定團隊的 (或私人) 層級](#set-the-privacy-level-for-teams)
- [控制團隊的來賓存取權](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>設定團隊的隱私權等級

您可以建立和設定敏感度標籤，在建立小組時，允許使用者建立具有特定隱私權的小組， (公開或) 設定。

例如，您建立併發布名為「機密」的敏感度標籤，其標籤隱私權選項已配置為 **「私人」。** 因此，使用此標籤建立的任何團隊都必須是私人團隊。 

當使用者建立新團隊並選取機密標籤時，使用者唯一可用的隱私權選項是 **私人**。 使用者無法選取其他隱私權選項 ，例如公用和全組織：

![機密敏感度標籤的螢幕擷取畫面。](media/sensitivity-labels-confidential-example.png)

同樣地，您建立併發布名為「一般」的敏感度標籤，其標籤隱私權選項已配置為 **公用**。 當使用者建立新團隊時，他們只有在選取此標籤時，才能建立公用或全組織團隊：

![一般敏感度標籤的螢幕擷取畫面。](media/sensitivity-labels-general-example.png)

建立團隊時，小組中頻道右上角的使用者可以看到敏感度標籤。 

![小組頻道中敏感度標籤的螢幕擷取畫面。](media/sensitivity-labels-channel.png)

團隊擁有者可以隨時變更小組的敏感度標籤和隱私權設定，方法為進入團隊，然後按一下 [ **編輯團隊**。

![小組屬性中敏感度標籤的螢幕擷取畫面。](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>控制團隊的來賓存取權

您可以使用敏感度標籤來控制來賓對團隊的存取權。 Teams不允許來賓存取的標籤所建立，只有貴組織的使用者才能使用。 組織外部人員無法新加入團隊。

## <a name="microsoft-teams-admin-center"></a>Microsoft Teams系統管理中心

您可以在系統管理中心建立或編輯團隊時，Microsoft Teams敏感度標籤。 

敏感度標籤也會顯示在小組屬性中，以及系統管理中心的管理小組頁面的Microsoft Teams欄。

## <a name="limitations"></a>限制

在您將敏感度標籤用於Teams，請注意下列限制：

- **API、PowerShell Cmdlet 和範本不支援敏感度Teams Graph標籤**
    
    使用者無法直接透過 Teams Graph API、Teams PowerShell Cmdlet 和範本建立Teams標籤。 不過，新式群組Graph API 和 PowerShell Cmdlet 允許建立具有標籤的群組。 因此，使用者可以先使用群組或 api 或 PowerShell Cmdlet 建立具有標籤Graph群組，然後將這些群組轉換成 Teams。

- **支援私人頻道**
    
    在團隊中建立的私人頻道會繼承已用於團隊的敏感度標籤。 同一個標籤會自動SharePoint專用頻道的網站集合上。
    
    不過，如果使用者直接變更私人頻道SharePoint網站的敏感度標籤，該標籤變更不會反映在 Teams中。 在此情境中，使用者會繼續在私人頻道標題中看到在小組上所使用的原始敏感度標籤。

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>如何建立及設定敏感度標籤Teams

使用檔中的指示Microsoft 365建立及設定敏感度標籤Teams： 

- [使用敏感度標籤來保護網站Microsoft Teams、Microsoft 365群組SharePoint內容](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。

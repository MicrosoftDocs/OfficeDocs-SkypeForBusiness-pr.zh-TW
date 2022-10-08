---
title: Microsoft Teams 的敏感度標籤
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
- tier1
- purview-compliance
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中使用敏感度標籤來保護您的團隊。
ms.openlocfilehash: 59bd67ea59787a1f73b2a0c808bfa3464c3bc31b
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046873"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Microsoft Teams 的敏感度標籤

[敏感度標籤](/microsoft-365/compliance/sensitivity-labels) 可讓 Teams 系統管理員保護和規範在團隊內共同作業期間所建立之敏感組織內容的存取權。 當您在[Microsoft Purview 合規性入口網站](/microsoft-365/compliance/go-to-the-securitycompliance-center)中設定敏感度標籤及其相關原則之後，這些標籤就可以套用到組織中的小組。

敏感度標籤目前不支援使用 Teams 教育版 SKU 之客戶的課程團隊。 若要深入瞭解授權，請參閱 [Microsoft Teams 服務說明](/office365/servicedescriptions/teams-service-description)。

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification"></a>敏感度標籤與 Teams 分類有何不同？

敏感度標籤與 Teams 分類不同，也稱為 Azure AD 群組分類。 分類是文字字串，可以與 Microsoft 365 群組相關聯，但沒有任何與它們相關聯的實際原則。 您使用分類做為中繼資料，然後必須使用其他方法，例如內部工具和腳本，以強制執行原則。

使用敏感度標籤的好處是透過Microsoft 365 群組平臺、Microsoft Purview 合規性入口網站和 Teams 服務的組合，自動強制執行端對端原則。 敏感度標籤提供強大的基礎結構支援，可保護貴組織的機密資料，並確保符合您的內部原則或法規。

如果您目前使用 Teams 分類，請參閱下列檔以取得詳細資訊，並指示如何將這些值轉換為敏感度標籤： [傳統 Azure AD 群組分類](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)。

## <a name="example-scenarios-for-sensitivity-labels"></a>敏感度標籤的範例案例

您可以如何搭配組織中的 Teams 使用敏感度標籤的範例案例包括：

- [設定團隊的公開或私人)  (隱私權層級](#set-the-privacy-level-for-teams)
- [控制團隊的來賓存取權](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>設定團隊的隱私權層級

您可以建立並設定在團隊建立期間套用的敏感度標籤，允許使用者建立具有特定隱私權 (公用或私人) 設定的團隊。

例如，您建立併發布名為「機密」的敏感度標籤，該標籤隱私權選項已設定為 **[私人]**。 因此，任何使用此標籤建立的團隊都必須是私人團隊。 

當使用者建立新小組並選取 **[機密]** 標籤時，使用者唯一可用的隱私權選項是 [ **私人]**。 其他隱私選項，例如公用和組織，使用者無法選取：

![[機密敏感度] 標籤的螢幕擷取畫面。](media/sensitivity-labels-confidential-example.png)

同樣地，您會建立併發布名為「一般」的敏感度標籤，並將標籤隱私權選項設定為 **[公開]**。 當使用者建立新團隊時，他們只能在選取這個標籤時建立公用或整個組織團隊：

![[一般敏感度] 標籤的螢幕擷取畫面。](media/sensitivity-labels-general-example.png)

建立團隊時，團隊中頻道右上角的使用者會看到敏感度標籤。 

![團隊頻道中敏感度標籤的螢幕擷取畫面。](media/sensitivity-labels-channel.png)

團隊擁有者可以移至團隊，隨時變更團隊的敏感度標籤和隱私權設定，然後按一下 [ **編輯團隊]**。

![小組內容中敏感度標籤的螢幕擷取畫面。](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>控制團隊的來賓存取權

您可以使用敏感度標籤來控制團隊的來賓存取權。 使用不允許來賓存取的標籤建立的團隊，僅供貴組織中的使用者使用。 您組織外部的人員無法新增至團隊。

## <a name="microsoft-teams-admin-center"></a>Microsoft Teams 系統管理中心

當您在 Microsoft Teams 系統管理中心建立或編輯團隊時，可以套用敏感度標籤。 敏感度標籤也會顯示在小組內容和 Microsoft Teams 系統管理中心 [**管理小組**] 頁面的 [**分類**] 欄中。

## <a name="limitations"></a>限制

在您使用 Teams 的敏感度標籤之前，請注意下列限制：

- **Teams Graph API 和 PowerShell Cmdlet 不支援敏感度標籤**
    
    使用者無法指定敏感度標籤，同時直接透過 Teams 圖形 API 或 Teams PowerShell Cmdlet 建立團隊。 不過，新式群組圖形 API 和 PowerShell Cmdlet 確實允許建立具有敏感度標籤的群組。 這表示您可以使用這些方法建立具有敏感度標籤的群組，然後將這些群組轉換為小組。

- **支援私人頻道**
    
    在團隊中建立的私人頻道會繼承套用至團隊的敏感度標籤。 相同的標籤會自動套用至私人頻道的 SharePoint 網站集合。
    
    不過，如果使用者直接變更私人頻道 SharePoint 網站上的敏感度標籤，該標籤變更並不會反映在 Teams 用戶端中。 在此案例中，使用者會繼續看到原始敏感度標籤套用在私人頻道標題中的團隊上。

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>如何建立和設定 Teams 的敏感度標籤

使用 Microsoft Purview 檔中的指示建立及設定 Teams 的敏感度標籤： 

- [使用敏感度標籤來保護 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。

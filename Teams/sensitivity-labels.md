---
title: Microsoft 團隊的敏感度標籤
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
description: 瞭解如何使用敏感度標籤來保護您的小組在 Microsoft 團隊中。
ms.openlocfilehash: 3b994bd7f1aa8fbc1fde13aaf49b195a1698695a
ms.sourcegitcommit: 5473b9fcd2bfe8adeb05a4a8d23e4350c7970fb6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49937525"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Microsoft 團隊的敏感度標籤

[敏感度標籤](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) 可讓團隊管理員保護並控制在團隊中共同作業期間建立的機密組織內容的存取權。 在 [Microsoft 合規性中心](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)中使用相關聯的原則設定敏感度標籤之後，這些標籤就可以套用到貴組織中的小組。

目前不支援使用團隊教育版 Sku 的客戶使用敏感度標籤。 若要深入瞭解授權，請參閱 [Microsoft 團隊服務說明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>敏感度標籤與團隊保密標籤之間的差異為何？

敏感度標籤與分類標籤（亦稱為 Azure AD 群組分類）不同。 分類標籤是可與 Microsoft 365 群組相關聯但沒有任何相關聯之實際原則的文字字串。 您使用分類標籤做為中繼資料，然後必須使用其他方法（例如內部工具和腳本）來強制執行原則。

使用敏感度標籤的優點是，其原則會透過 Microsoft 365 群組平臺、合規性中心及團隊服務的組合，自動強制執行。 敏感度標籤可提供強大的基礎結構支援，以保護貴組織的機密資料，並確保遵守您的內部原則或管理法規。

如果您目前使用的是分類標籤，請參閱下列檔，以取得詳細資訊，以及如何將其遷移至敏感度標籤的相關指示： [傳統 AZURE AD 群組分類](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)。

## <a name="example-scenarios-for-sensitivity-labels"></a>敏感度標籤範例案例

您可以如何將敏感度標籤與組織中的小組搭配使用的範例案例：

- [針對團隊 (公開或私人) 設定隱私權層級](#set-the-privacy-level-for-teams)
- [控制對團隊的來賓存取權](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>設定團隊的隱私權等級

您可以建立及設定在小組建立期間套用的敏感度標籤，讓使用者能夠在公開或私人) 設定中，建立具有特定隱私權 (小組。

例如，您可以建立併發布一個名為「機密」的敏感度標籤，並將 [標籤隱私權] 選項設定為 [ **私人**]。 因此，使用此標籤建立的任何團隊都必須是私人團隊。 

當使用者建立新的小組並選取 [ **機密** ] 標籤時，使用者可以使用的唯一隱私權選項是 [ **私人**]。 使用者無法選取其他隱私權選項（例如公用與組織範圍）：

![[機密敏感度] 標籤的螢幕擷取畫面](media/sensitivity-labels-confidential-example.png)

同樣地，您也可以建立併發布名為「一般」的敏感度標籤，並將 [標籤隱私權] 選項設定為 [ **公開**]。 當使用者建立新的小組時，他們在選取此標籤時，只會建立公用或組織範圍的團隊：

![一般敏感度標籤的螢幕擷取畫面](media/sensitivity-labels-general-example.png)

建立小組後，[敏感度] 標籤會顯示在小組中頻道的右上角。

![小組頻道中敏感度標籤的螢幕擷取畫面](media/sensitivity-labels-channel.png)

小組擁有者可以隨時變更團隊的敏感度標籤和隱私權設定，只要前往小組，然後按一下 [ **編輯團隊**] 即可。

![團隊屬性中敏感度標籤的螢幕擷取畫面](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>控制對團隊的來賓存取權

您可以使用敏感度標籤來控制來賓對您團隊的存取權。 只有貴組織中的使用者可以使用不允許來賓存取權的標籤建立的團隊。 您組織外部的人員無法新增至小組。

## <a name="microsoft-teams-admin-center"></a>Microsoft 團隊系統管理中心

當您在 Microsoft 團隊系統管理中心建立或編輯小組時，您可以套用敏感度標籤。 

在團隊屬性以及 Microsoft 團隊系統管理中心 [**管理團隊**] 頁面上的 [**分類**] 欄中，也會顯示敏感度標籤。

## <a name="limitations"></a>有限

在您針對團隊使用敏感度標籤之前，請注意下列限制：

- **Sublabels 不會顯示父標籤名稱**
    
    團隊支援 sublabels，但不會顯示父標籤的名稱。 例如，[ **機密**] \\ **所有員工都會** 顯示為 [ **所有員工**]。

- **團隊圖形 Api、PowerShell Cmdlet 及範本不支援敏感度標籤**
    
    使用者將無法在直接透過團隊圖形 Api、團隊 PowerShell Cmdlet 和團隊範本建立的團隊上套用敏感度標籤。

- **支援專用通道**
    
    在團隊中建立的專用頻道會繼承已套用在小組中的敏感度標籤。 在 [私人頻道] 的 SharePoint 網站集合上，系統會自動套用相同的標籤。
    
    不過，如果使用者在 SharePoint 網站上直接變更私人頻道的敏感度標籤，則該標籤變更不會反映在團隊用戶端中。 在這種情況下，使用者會繼續在私人通道標題中查看在團隊上套用的原始敏感度標籤。

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>如何建立及設定小組的敏感度標籤

使用 Microsoft 365 檔中的指示來建立及設定小組的敏感度標籤： 

- [使用敏感度標籤來保護 Microsoft 團隊、microsoft 365 群組和 SharePoint 網站中的內容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。

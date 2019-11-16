---
title: Microsoft 團隊的敏感度標籤
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中定義及使用敏感度標籤。
ms.openlocfilehash: 3a0c40a51653a525587a0662949a3fdd4e63faf4
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653569"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Microsoft 團隊的敏感度標籤

[!INCLUDE [preview-feature](includes/preview-feature.md)]

[敏感度標籤](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)可讓團隊管理員控制在團隊中共同作業期間建立的機密組織內容的存取權。 您可以在[安全性 & 合規性中心](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)中定義敏感度標籤及其相關聯的原則。 這些標籤與原則會自動套用至貴組織中的小組。  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>敏感度標籤與團隊保密標籤之間的差異為何？

敏感度標籤與分類標籤不同，需要您使用 PowerShell 來建立它們。 分類標籤是可與群組相關聯但不含任何相關聯之實際原則的文字字串。 您可以使用分類標籤做為中繼資料，透過內部工具和腳本手動強制執行原則。

另一方面，敏感度標籤及其原則會自動強制執行，以結合群組平臺、安全性 & 合規性中心及團隊服務的組合來進行。 敏感度標籤可提供強大的基礎結構支援，以保護貴組織的機密資料。  

## <a name="create-and-publish-sensitivity-labels-for-teams"></a>建立及發佈小組的敏感度標籤

如需如何啟用、建立及發佈小組的敏感度標籤，請參閱[在 Microsoft 團隊、Office 365 群組和 SharePoint 網站上使用敏感度標籤](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。

## <a name="using-sensitivity-labels-with-teams"></a>在團隊中使用敏感度標籤

以下是一些範例，說明如何將敏感度標籤與組織中的小組搭配使用。

### <a name="privacy-setting-of-teams"></a>團隊的隱私權設定

您可以建立可在小組建立期間套用的敏感度標籤，讓使用者可以建立具備特定隱私權（公開或私人）設定的小組。

例如，您會在安全性 & 合規性中心建立名為 "機密" 的標籤，並設定團隊，讓使用此標籤建立的任何小組都必須是私人團隊。 當使用者建立新的小組並選取 [**機密**] 標籤時，使用者可以使用的唯一隱私權選項是 [**私人**]。 使用者已停用其他隱私權選項，例如公用與組織範圍。

![[機密敏感度] 標籤的螢幕擷取畫面](media/sensitivity-labels-confidential-example.png)

同樣地，如果使用者在建立新團隊時選取 **[一般**]，他們就只能建立公用或組織範圍的團隊。

![一般敏感度標籤的螢幕擷取畫面](media/sensitivity-labels-general-example.png)

建立小組後，[敏感度] 標籤會顯示在小組中頻道的右上角。

![小組頻道中敏感度標籤的螢幕擷取畫面](media/sensitivity-labels-channel.png)

小組擁有者可以隨時變更團隊的敏感度標籤和隱私權設定，只要前往小組，然後按一下 [**編輯團隊**] 即可。

![小組頻道中敏感度標籤的螢幕擷取畫面](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a>對團隊的來賓存取權

您可以指定使用特定標籤建立的小組是否允許來賓存取。 只有貴組織中的使用者可以使用不允許來賓存取權的標籤建立的團隊。 您組織外部的人員無法新增至小組。

## <a name="known-issues"></a>已知問題

**Microsoft 團隊系統管理中心的敏感度標籤支援**

目前，Microsoft [團隊管理中心] 不支援敏感度標籤。 如果您使用的是敏感度標籤，當您建立或編輯小組時，將無法設定敏感度標籤。 敏感度標籤在小組屬性中也看不到，而且在 Microsoft 團隊系統管理中心的**分類**欄中不會顯示。

**支援小組圖形 Api、Powershell Cmdlet 及範本中的敏感度標籤**

目前，使用者將無法在直接透過圖形 Api、Powershell Cmdlet 及範本建立的小組上套用敏感度標籤。

**在私人頻道的 SharePoint 網站集合上直接編輯敏感度標籤**

在團隊中建立的專用頻道會繼承已套用在小組中的敏感度標籤。 此外，在 [私人頻道] 的 SharePoint 網站集合上會自動套用相同的標籤。

如果使用者直接更新私人頻道之 SharePoint 網站集合上的敏感度標籤，就不會在團隊用戶端中更新該標籤。 在這種情況下，使用者會繼續在私人通道標題中查看在團隊上套用的敏感度標籤。

**套用至團隊 app 外敏感度標籤變更的傳播時間**

在團隊 app 外對敏感度標籤所做的變更，可能需要長達24小時才能反映在團隊 app 中。 這適用于針對您啟用或停用租使用者的標籤所做的任何變更、標籤名稱、設定及原則的變更。

此外，直接針對支援小組的群組或 SharePoint 網站集合所做的任何變更，都可能需要長達24小時才能傳播至團隊 app。
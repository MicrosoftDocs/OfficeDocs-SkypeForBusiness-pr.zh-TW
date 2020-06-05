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
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中定義及使用敏感度標籤。
ms.openlocfilehash: 7f8eb7e0fa0d34ae21829a12011f094d8e9c9126
ms.sourcegitcommit: 2c23a8c5afc4a6b74c2c6d7487975a94fe99dc07
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2020
ms.locfileid: "44562068"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Microsoft 團隊的敏感度標籤

[!INCLUDE [preview-feature](includes/preview-feature.md)]

[敏感度標籤](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)可讓團隊管理員控制在團隊中共同作業期間建立的機密組織內容的存取權。 您可以在[安全性 & 合規性中心](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)中定義敏感度標籤及其相關聯的原則。 這些標籤與原則會自動套用至貴組織中的小組。  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>敏感度標籤與團隊保密標籤之間的差異為何？

敏感度標籤與分類標籤不同，需要您使用 PowerShell 來建立它們。 分類標籤是可與群組相關聯但不含任何相關聯之實際原則的文字字串。 您可以使用分類標籤做為中繼資料，透過內部工具和腳本手動強制執行原則。

另一方面，敏感度標籤及其原則會自動強制執行，以結合群組平臺、安全性 & 合規性中心及團隊服務的組合來進行。 敏感度標籤可提供強大的基礎結構支援，以保護貴組織的機密資料。  

## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a>建立、管理及發佈小組的敏感度標籤

如需如何啟用、建立及發佈小組的敏感度標籤，請參閱[使用敏感度標籤與 Microsoft 團隊、microsoft 365 群組和 SharePoint 網站](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。

>[!IMPORTANT]
>建立、更新及刪除敏感度標籤時，需要小心地將發佈標籤與使用者進行排序。 順序中的任何偏差都可能會導致所有使用者的持續性團隊建立錯誤。 因此，當您<a href="#createpublishlabels">建立及發佈標籤</a>、<a href="#modifydeletelabels">修改及刪除已發佈的標籤</a>，以及<a href="#manageerrors">管理團隊建立錯誤</a>時，請務必執行下列動作。

**建立及發佈標籤** <a name="createpublishlabels"> </a>

在安全性 & 合規性中心建立及發佈標籤時，最多可能需要24小時才能讓標籤在團隊建立介面中變為可見。 使用下列步驟來發佈租使用者中所有使用者的標籤：
1. 建立標籤並將其發佈，以在租使用者中進行幾個選取的使用者帳戶。
2. 在標籤發佈之後，請等候24小時。
3. 24小時之後，請嘗試使用可存取標籤的其中一個使用者帳戶來建立擁有標籤的小組。
4. 如果團隊在步驟3中成功建立，請繼續進行併發布租使用者中其餘使用者的標籤。

**修改及刪除已發佈的標籤** <a name="modifydeletelabels"> </a>

刪除或修改與靈敏度原則相關聯的標籤時，可能會導致小組建立跨租使用者失敗。 因此，在您刪除或修改標籤之前，您必須先解除標籤與其相關聯原則的關聯。 使用下列步驟  
若要刪除或修改標籤：
1. 從使用標籤的所有原則中移除標籤。 或者，您也可以刪除原則本身。
2. 從原則移除標籤，或原則本身遭到刪除時，請等候48小時，然後再繼續進行。
3. 在48小時後，啟動團隊建立介面，並確認租使用者中的任何使用者都看不到該標籤。
4. 現在，您可以安全地刪除或修改標籤。

**管理團隊建立錯誤** <a name="manageerrors"> </a>

如果小組建立在公眾預覽版期間開始失敗，您有兩個選項：
 - 在小組建立期間，請確定任何使用者都不強制使用敏感度標籤。
 - 使用 [[啟用此預覽](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview)] 中的腳本關閉敏感度標籤。

請注意，EnableMIPLabels 設定必須設定為 false，如下所示：

```console
$setting["EnableMIPLabels"] = "False"
```

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

**在團隊 EDU Sku 中支援敏感度標籤**

目前不支援使用團隊教育版 Sku 的客戶使用敏感度標籤。

**在私人頻道的 SharePoint 網站集合上直接編輯敏感度標籤**

在團隊中建立的專用頻道會繼承已套用在小組中的敏感度標籤。 此外，在 [私人頻道] 的 SharePoint 網站集合上會自動套用相同的標籤。

如果使用者直接更新私人頻道之 SharePoint 網站集合上的敏感度標籤，就不會在團隊用戶端中更新該標籤。 在這種情況下，使用者會繼續在私人通道標題中查看在團隊上套用的敏感度標籤。

**套用至團隊 app 外敏感度標籤變更的傳播時間**

在團隊 app 外對敏感度標籤所做的變更，可能需要長達24小時才能反映在團隊 app 中。 這適用于針對您啟用或停用租使用者的標籤所做的任何變更、標籤名稱、設定及原則的變更。

此外，直接針對支援小組的群組或 SharePoint 網站集合所做的任何變更，都可能需要長達24小時才能傳播至團隊 app。

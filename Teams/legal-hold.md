---
title: 在法律封存上放置 Microsoft 團隊使用者或團隊
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解如何使用安全性 & 合規性中心在 Microsoft 團隊使用者或小組中進行法律封存，以及如何根據資料需求來瞭解需要法律封存。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6c46de971a63a212c0773f5048aeded697d05e0c
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863024"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>在法律封存上放置 Microsoft 團隊使用者或團隊
==================================================

當訴訟合理的預期情況下，組織必須保留以電子方式儲存的資訊（ESI），包括與案例相關的小組聊天訊息。 組織可能需要保留與特定主題或特定人員相關的所有訊息。 本文將涵蓋 Microsoft 團隊中的法律封存（若要在 M365 空間中解除保留實施），請參閱[管理 eDiscovery 案例：保留內容位置](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)。

> [!NOTE]
> 在2020年2月，我們已開啟專用頻道的法律封存或案例封存（私人通道聊天會儲存在使用者信箱中，一般通道聊天會儲存在該小組的群組信箱）。 如果已有合法保留使用者信箱，保留原則現在會自動套用至儲存在該信箱中的私人通道訊息。 系統管理員不需要採取進一步的動作，就能開啟此功能。 在專用通道中共用的檔案的法定保留也受到支援。

在 Microsoft 團隊中，整個團隊或選取的使用者都可以保留或法律封存。 執行此動作將會確保由組織的合規性管理員或團隊系統管理員發現所有在這些小組中交換的訊息（包括私人通道），或由這些人員所交換的訊息。

> [!NOTE]
> [保留使用者] 不會自動將群組放在 [保留] 或 [相反]。

若要讓使用者或團隊在法律上保留：

1. 流覽至[安全性 & 合規性中心](https://go.microsoft.com/fwlink/?linkid=854628)。 當您建立新的案例時，系統會顯示將信箱或網站保留的選項。
1. 移至 eDiscovery 或高級 eDiscovery，然後按一下 [+ 建立案例] 來建立案例。 一旦建立案例，請將其開啟。
![已選取 [Microsoft 團隊 eDiscovery] 索引標籤，並顯示 [建立案例] 按鈕。](media/LegalHold1.png)
1. 移至頂端功能表中的 [保留] 區段，然後按一下 [+ 建立] 以建立保留使用者或團隊在保留狀態的保留：在您建立新案例時，系統會顯示將信箱或網站放在暫留中的選項。
![顯示已選取 [保留] 索引標籤的影像，以及下方的 [建立] 按鈕。](media/LegalHold2.png)
    1. 為**您的保留命名**。 針對您要建立的保留，選取一個描述性且唯一的名稱。
![此螢幕擷取畫面顯示 [名稱] 您的 [保留] 索引標籤，您可以在此輸入您要建立之保留的名稱和描述。](media/LegalHold3.png)
    1. **選擇 [位置**]。 選擇您是否要在使用者或整個小組中套用保留（在目前無法在個別頻道上套用保留）。 注意：如果使用者已保留，則所有郵件都會保留，包括在1:1 聊天中傳送的任何內容、1：許多或群組聊天，或是頻道交談（包括私人頻道）。
    ![在這裡，我們有 [選擇位置] 區段來建立新的保留，您可以在其中決定要將 [保留] 套用到哪個 M365 選項（包括 Microsoft 團隊）。](media/LegalHold4.png)
    1. **建立查詢**。 如果您想要在保留原則中有更多的細微性，您可以自訂 [保留]。 例如，您可以指定要尋找的關鍵字，或者您可以新增更多的條件，保留才能生效。
    1. 在發佈到您的組織之前，請先**檢查您的設定**。

設定好法律封存之後，您就可以在 [[小組 eDiscovery](eDiscovery-investigation.md) ] 文章中，找出所有保留原則所保留的所有內容。

> [!IMPORTANT]
> 當使用者或群組處於保留狀態時，所有郵件複本都會保留下來。 例如，如果使用者在頻道中張貼一封郵件，然後修改該郵件，請在保留案例中，這兩份郵件複本都會保留下來。 如果沒有合法保留，就只會保留最新的訊息。

就像資料需求，您可以使用下表來瞭解必須針對法律封存施加的事項：

|例子  |保留內容  |
|---------|---------|
|**Microsoft 團隊透過使用者聊天內容（在1:1 聊天、1：多或群組聊天、私人頻道交談等）。**     |使用者信箱         |
|**Microsoft 團隊頻道聊天（不包括私人頻道）**    |小組使用的群組信箱         |
|**Microsoft 團隊內容（例如 Wiki、檔案）**     |小組使用的 SharePoint 網站         |
|**Microsoft 團隊私人頻道檔案**     |專用的專用頻道 SharePoint 網站     |
|**使用者的私人內容**     |使用者的商務用 OneDrive 網站         |

> [!NOTE]
> 若要在私人通道中保留通訊，您需要將使用者信箱（私人通道使用者）保留，以及使用 eDiscovery 工具進行搜尋時，您應該在該使用者的信箱中搜尋。 如先前所述，私人通道聊天是儲存在使用者信箱中，而不是在小組的群組信箱中。

如果您想進一步閱讀本主題中針對 M365 中的非團隊區域，請參閱[管理 eDiscovery 案例：保留內容位置](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)。

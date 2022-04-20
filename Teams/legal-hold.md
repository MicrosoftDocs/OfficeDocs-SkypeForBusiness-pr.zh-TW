---
title: 將Microsoft Teams使用者或小組依法保留
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解如何使用 Microsoft Purview 合規性入口網站，將Microsoft Teams使用者或小組設為法律保留狀態，並瞭解哪些專案需要根據資料需求進行法律保留。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d56bece07fe7342c4156abdae73508a1a149864
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922454"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>將Microsoft Teams使用者或小組依法保留

當合理的訴訟預期存在時，組織必須保留 ESI)  (電子儲存的資訊，包括Teams與案例相關的聊天訊息。 組織可能需要保留與特定調查或特定人員相關的所有郵件。 本文將討論如何使用法律保留來保留Microsoft Teams中的內容。 若要在Microsoft 365中保留其他服務中的內容，請參閱[建立電子檔探索保留](/microsoft-365/compliance/create-ediscovery-holds)。

> [!NOTE]
> 在 2020 年 2 月，我們針對私人頻道開啟了法律保留。 私人頻道聊天會儲存在使用者信箱中，而標準頻道聊天則儲存在與上層團隊相關聯的信箱中。 如果使用者信箱已有法律保留，保留原則現在會自動套用至儲存在該信箱中的私人頻道訊息。 系統管理員不需要採取其他動作即可開啟此功能。 也支援以法律方式保留在私人頻道中共用的檔案。

在Microsoft Teams內，整個小組或選取的使用者都可以受到法律保留。 這麼做可確保組織合規性管理員或Teams管理員能夠搜尋這些小組中所有 (包括私人和共用頻道) 或由這些人員交換的訊息。

> [!NOTE]
> 將使用者設為保留狀態並不會自動將群組設為保留狀態，反之亦然。
> 活動摘要中傳送的通知無法保留。

若要在核心電子檔探索案例中將使用者或小組以法律方式保留：

1. 移至 [Microsoft Purview 合規性入口網站](https://compliance.microsoft.com)。 當您建立新案例時，系統會顯示保留信箱或網站的選項。

2. 按一下 [建立案例]，移至 **eDiscoveryCore**  >  並建立 **案例**。**** 建立案例之後，請將它開啟。
  
   ![Microsoft Teams已選取電子檔探索索引標籤，顯示 [建立案例] 按鈕。](media/LegalHold1.png)

   > [!NOTE]
   > 您也可以將使用者置於與Advanced eDiscovery案例相關聯的保留中。 如需詳細資訊，請參閱[管理Advanced eDiscovery中的保留](/microsoft-365/compliance/managing-holds)。

3. 移至頂端功能表上的 [ **保留** ] 索引標籤，然後按一下 [ **建立** ] 以建立保留。 保留使用者或小組會保留這些使用者交換的所有訊息。 當您建立新案例時，系統會顯示保留信箱或網站的選項。

   ![顯示已選取 [保留] 索引標籤，以及下方 [建立] 按鈕的影像。](media/LegalHold2.png)

   1. **為您的保留命名**。 為您要建立的保留選取描述性且唯一的名稱。
  
       ![此螢幕擷取畫面顯示 [命名您的保留] 索引標籤，您可以在此輸入您正在建立之保留的名稱和描述。](media/LegalHold3.png)

   2. **選擇位置**。 選擇是否要將保留套用至使用者或整個團隊 (目前無法在個別頻道套用保留) 。 如果使用者被保留，則會保留其所有訊息，包括一對一聊天、群組聊天和私人頻道中的訊息。 當上層團隊被保留時，標準和共用頻道中的訊息會保留。

      ![選擇您要保留的資料位置。](media/LegalHold4.png)

   3. **建立查詢**。 如果您希望保留原則更加細分，可以自訂保留。 例如，您可以指定要尋找的關鍵字，或是新增需要滿足的更多條件，保留才會生效。

   4. 建立保留之前，請先 **檢閱您的設定**。

保留建立之後，您可以搜尋保留原則保留的內容。 如需詳細資訊，請參閱[在 Teams 中進行電子檔探索調查](eDiscovery-investigation.md)。

> [!IMPORTANT]
> 當使用者或群組被保留時，所有郵件的合規性複本都會保留。 例如，如果使用者在頻道中張貼訊息，然後修改郵件，則會保留這兩份郵件複本。 若不保留，只會保留最新的郵件。

## <a name="content-locations-to-place-on-hold-to-preserve-teams-content"></a>保留內容位置以保留Teams內容

如需實用的指南，請使用下表瞭解信箱或網站等 (要保留的內容位置) ，以保留不同類型的Teams內容。

|案例  |內容位置  |
|---------|---------|
|使用者 (聊天訊息，例如 1：1 聊天、1：N 群組聊天，以及私人頻道交談)      |使用者信箱         |
|標準和共用頻道中的聊天訊息    |與父團隊相關聯的信箱         |
|標準頻道中的檔案 (例如 Wiki 內容和檔案)      |SharePoint與上層小組相關聯的網站        |
|私人和共用頻道中的檔案     |與頻道相關聯的專用SharePoint網站
|使用者的私人內容     |使用者的商務用 OneDrive帳戶       |
|聊天中的卡片內容|1 對 1 聊天、1：N 群組聊天和私人頻道交談的使用者信箱;標準和共用頻道訊息中卡片內容的上層團隊信箱。 如需詳細資訊，請參閱 [建立電子檔探索保留](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)中的一節。|
|||

> [!NOTE]
> 若要保留私人頻道中的郵件內容，您必須保留私人頻道成員 (的使用者信箱) 保留。 使用電子檔探索工具搜尋私人頻道訊息時，您必須搜尋使用者的信箱。 如先前所述，私人頻道聊天會儲存在使用者信箱中，而非與上層團隊關聯的群組信箱中。

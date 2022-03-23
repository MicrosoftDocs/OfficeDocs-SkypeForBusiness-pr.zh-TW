---
title: 保留Microsoft Teams或小組
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
description: 瞭解如何使用資料Microsoft Teams將使用者或小組擱置Microsoft 365 合規性中心並瞭解根據資料需求需要法律保留哪些專案。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06b3ea009e538b8796a9e55b277dc4ec12f5a3a4
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711557"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>保留Microsoft Teams或小組

當有合理的訴訟預期時，組織必須保留電子 (ESI) ，包括Teams與案件相關的聊天訊息。 組織可能需要保留與特定調查或特定人員相關的所有郵件。 本文將討論使用法律保留來保留Microsoft Teams。 若要保留其他服務中的內容Microsoft 365，請參閱[建立電子檔探索保留](/microsoft-365/compliance/create-ediscovery-holds)。

> [!NOTE]
> 我們在 2020 年 2 月開啟私人頻道的法律保留。 私人頻道聊天會儲存在使用者信箱中，而標準頻道聊天則儲存在與父團隊相關聯的信箱中。 如果使用者信箱已有合法保留狀態，保留原則現在會自動適用于儲存在該信箱中的私人通道郵件。 系統管理員無需執行其他動作來開啟此功能。 也支援合法保留在私人頻道中共用的檔案。

在 Microsoft Teams，整個團隊或選取的使用者都可以被置於法律保留狀態。 這麼做會確保組織合規性管理員或系統管理員 (在這些團隊中交換的所有郵件) 包括私人和共用通道) 或由這些人員交換的郵件，都Teams找到。

> [!NOTE]
> 將使用者置於保留狀態不會自動將群組置於保留狀態，反之亦然。
> 無法保留以活動摘要傳送的通知。

若要將使用者或小組置於核心電子檔探索案例的保留狀態：

1. 請[前往Microsoft 365 合規性中心](https://compliance.microsoft.com)。 當您建立新案例時，系統提供將信箱或網站置於保留狀態的選項。

2. 按一下建立案例，前往 **eDiscoveryCore**  >  並 **建立案例**。**** 建立案例之後，請開啟它。
  
   ![Microsoft Teams已選取 eDiscovery 定位停駐點，顯示建立大小寫按鈕。](media/LegalHold1.png)

   > [!NOTE]
   > 您也可以將使用者放在與案例關聯的保留Advanced eDiscovery狀態。 詳細資訊，請參閱[管理保留Advanced eDiscovery](/microsoft-365/compliance/managing-holds)。

3. 前往 **頂端功能表上的** [保留資料表>，然後按一下 [ **建立** 以建立保留狀態。 保留使用者或團隊會保留這些使用者交換的所有郵件。 當您建立新案例時，系統提供將信箱或網站置於保留狀態的選項。

   ![顯示已選取的保留選項卡和下方的建立按鈕的影像。](media/LegalHold2.png)

   1. **為保留命名**。 選取要建立保留狀態的描述性唯一名稱。
  
       ![此螢幕擷取畫面顯示的顯示名稱您的保留點，您可以在其中輸入您建立保留的名稱和描述。](media/LegalHold3.png)

   2. **選擇位置**。 選擇是否要將保留狀態用於使用者或整個小組 (目前無法將保留功能用於個別頻道) 。 如果使用者保持保留狀態，會保留其所有訊息，包括 1：1 聊天、群組聊天和私人頻道中的訊息。 當父團隊處於保留狀態時，標準和共用頻道中的訊息會保留。

      ![選擇要保留的資料位置。](media/LegalHold4.png)

   3. **建立查詢**。 如果您想要保留原則的更精細度，您可以自訂保留。 例如，您可以指定要尋找的關鍵字，或者您可以新增更多條件，讓保留生效時必須滿足這些條件。

   4. **建立保留之前，** 先檢查您的設定。

建立保留後，您可以搜尋保留政策保留的內容。 詳細資訊，請參閱在 Teams 中[執行電子資料探索Teams](eDiscovery-investigation.md)。

> [!IMPORTANT]
> 當使用者或群組處於保留狀態時，所有郵件的合規性複本會保留。 例如，如果使用者在頻道中張貼郵件，然後修改郵件，這兩個郵件複本會保留。 如果沒有保留，只會保留最新的郵件。

## <a name="content-locations-to-place-on-hold-to-preserve-teams-content"></a>要保留的內容位置，以保留Teams內容

做為實用指南，請使用下表瞭解哪些內容位置 (例如信箱或網站) 保留，以保留不同類型的Teams內容。

|案例  |內容位置  |
|---------|---------|
|使用者聊天訊息 (例如 1：1 聊天、1：N 群組聊天，以及私人頻道交談)      |使用者信箱         |
|標準頻道和共用頻道中的聊天訊息    |與父團隊相關聯的信箱         |
|標準頻道中的檔案 (例如 Wiki 內容和檔案)      |SharePoint與父團隊相關聯的網站        |
|私人和共用頻道中的檔案     |與SharePoint相關聯的私人網路站
|使用者的私人內容     |使用者的帳戶商務用 OneDrive帳戶       |
|聊天中的卡片內容|1：1 聊天、1：N 群組聊天和私人頻道交談的使用者信箱;標準及共用頻道訊息中卡片內容的父團隊信箱。 若要詳細資訊，請參閱建立電子檔探索保留中的「保留卡片 [內容」一節](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)。|
|||

> [!NOTE]
> 若要在私人頻道中保留郵件內容，您必須將使用者信箱 (私人頻道成員) 保留。 使用 eDiscovery 工具搜尋私人頻道訊息時，您必須搜尋使用者的信箱。 如先前所述，私人頻道聊天會儲存在使用者信箱中，而不是與父團隊相關聯的群組信箱中。

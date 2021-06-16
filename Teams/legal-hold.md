---
title: 將Microsoft Teams或小組保留為法律保留狀態
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
description: 瞭解如何使用安全性Microsoft Teams合規性中心將使用者或小組&保留狀態，並瞭解根據資料需求需要法律保留哪些專案。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3e52b10f0a7a8dd3ac67f7a2c15b9d1e082186ab
ms.sourcegitcommit: dba7984f899f8921b462a56d158fa0a1cc2c2a8b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929289"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>將Microsoft Teams或小組保留為法律保留狀態
==================================================

當訴訟有合理的預期時，組織必須保留電子 (ESI) ，包括Teams與案件相關的聊天訊息。 組織可能需要保留與特定主題或特定人員相關的所有郵件。 本文將涵蓋 Microsoft Teams (中的法律保留：若要解決 M365 空間中保留的實現，請參閱管理[電子檔探索案例：](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)將內容位置保留 。) 。

> [!NOTE]
> 在 2020 年 2 月，我們啟用私人頻道的法律保留或案例保留 (私人頻道聊天會儲存在使用者信箱中，一般頻道聊天會儲存在小組的群組信箱) 。 如果使用者信箱已有法律保留，保留原則現在會自動適用于儲存在該信箱中的私人通道郵件。 系統管理員無需執行其他動作來開啟此功能。 也支援合法保留在私人頻道中共用的檔案。

在Microsoft Teams，整個團隊或選取的使用者都可以保留或合法保留。 這麼做會確保組織合規性管理員或系統管理員 (在這些團隊中交換的所有郵件) 包括私人頻道) 或由這些人員交換的郵件，都Teams找到。

> [!NOTE]
> 將使用者置於保留狀態不會自動將群組置於保留狀態，反之亦然。
> 在活動提要中所送出的通知無法置於法律保留狀態。

若要將使用者或小組置於法律保留狀態：

1. 流覽至 [安全性與&中心](https://go.microsoft.com/fwlink/?linkid=854628)。 當您建立新案例時，系統提供將信箱或網站置於保留狀態的選項。

2. 前往 eDiscovery 或 Advanced eDiscovery，然後按一下 「建立案例」來建立案例。 建立案例後，請開啟它。

   > [!div class="mx-imgBorder"]
   > ![Microsoft Teams已選取 eDiscovery 定位停駐點，顯示建立大小寫按鈕。](media/LegalHold1.png)

3. 從頂端功能表前往 [保留> 區段，然後按一下 [+ 建立」 以建立保留狀態。 保留使用者或團隊會保留這些使用者或郵件交換的所有郵件。 當您建立新案例時，系統提供將信箱或網站置於保留狀態的選項。

   > [!div class="mx-imgBorder"]
   > ![顯示已選取的保留選項卡，以及下方的建立按鈕的影像。](media/LegalHold2.png)

   1. **為保留命名**。 針對要建立保留狀態，選取描述性且唯一的名稱。

      > [!div class="mx-imgBorder"]
      > ![此螢幕擷取畫面顯示名稱您的保留點，您可以在其中輸入您建立保留的名稱和描述。](media/LegalHold3.png)

    2. **選擇位置**。 選擇是否要將保留狀態用於使用者或整個小組， (目前無法將保留) 。 注意：如果使用者保持保留狀態，其所有訊息都會保留，包括他們在 1：1 聊天、1：多或群組聊天或頻道交談 (包括私人頻道) 。
  
       > [!div class="mx-imgBorder"]
       > ![在這裡，我們有建立新保留的選擇位置區段，您可以在此決定要申請的 M365 選項，包括 Microsoft Teams 選項。](media/LegalHold4.png)

    3. **建立查詢**。 如果您想要保留原則的更精細度，您可以自訂保留。 例如，您可以指定要尋找的關鍵字，或者您可以新增更多條件，讓保留生效時必須滿足這些條件。
    
    4. **在發佈至** 貴組織之前，先檢查您的設定。

設定法律保留之後，您可以在電子檔探索一文之後，探索任何保留Teams[內容](eDiscovery-investigation.md)。

> [!IMPORTANT]
> 當使用者或群組處於保留狀態時，所有郵件複本都會保留。 例如，如果使用者在頻道中張貼郵件，然後修改郵件，在保留情況下，郵件的兩份複本會保留。 若未就地保留法律，只會保留最新的郵件。

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a>保留保留內容的位置，以保留Teams內容

做為實用指南，您可以使用下表瞭解哪些內容位置 (例如信箱或網站) 可置於法律保留狀態，以保留不同類型的Teams內容。

|案例  |內容位置  |
|---------|---------|
|Teams使用者聊天 (例如 1：1 聊天、1：N 群組聊天，以及私人頻道交談)      |使用者信箱。         |
|Teams頻道聊天 (私人頻道)     |小組使用的群組信箱。         |
|Teams檔案內容 (例如 Wiki 內容和檔案)      |SharePoint小組使用的網站。         |
|Teams私人頻道檔案     |私人SharePoint私人網路站。     |
|使用者的私人內容     |使用者的帳戶商務用 OneDrive帳戶。         |
|聊天中的卡片內容|1：1 聊天、1：N 群組聊天的使用者信箱，以及頻道訊息中卡片內容的私人頻道交談或群組信箱。 若要詳細資訊，請參閱建立電子檔探索保留中的「保留卡片 [內容」一節](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)。
||||

> [!NOTE]
> 若要在私人頻道中保留通訊，您必須保留使用者信箱 (私人通道使用者) ，而使用 eDiscovery 工具進行搜尋時，您應該在該使用者的信箱中搜尋。 如先前所述，私人頻道聊天會儲存在使用者信箱中，而不是儲存在小組的群組信箱中。

如果您想要進一步閱讀本主題中的非Teams區域，Microsoft 365請參閱管理電子檔探索[案例：](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)保留內容位置。

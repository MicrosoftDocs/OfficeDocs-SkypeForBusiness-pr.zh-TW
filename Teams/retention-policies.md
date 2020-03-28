---
title: Microsoft 團隊中的保留原則
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: 瞭解保留原則，以及如何在團隊中建立及管理它們。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: a9097dfc43ca0f70d37b0051e6b0e10283da26c3
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033387"
---
# <a name="retention-policies-in-microsoft-teams"></a>Microsoft 團隊中的保留原則

保留原則可協助您更有效率地管理組織中的資訊。 您可以使用保留原則來保留遵守貴組織的內部原則、行業管理法規或法律需求所需的資料，以及刪除被視為債務的資料，或是不需要保留，或是沒有合法或商業價值。

依預設，小組聊天、頻道和檔案資料都會永久保留。 就像管理員一樣，您可以為聊天和頻道訊息設定小組保留原則，並提前決定是否要保留資料、刪除資料，或將資料保留一段特定的時間，然後將其刪除。

您可以在[Office 365 安全 & 合規性中心](https://protection.office.com/)或使用安全性 & 合規性中心 PowerShell Cmdlet 中，建立及管理小組和其他工作負載的保留原則。 您可以將團隊保留原則套用到整個組織或特定的使用者與團隊。

> [!NOTE]
> 我們還不支援保留私人通道訊息的設定。 支援在私人通道中共用的檔案保留。

若要深入瞭解 Office 365 的保留原則，請參閱[保留原則概覽](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)。

## <a name="what-are-retention-policies-for-teams"></a>什麼是團隊的保留原則？

當您設定團隊或任何其他工作負荷的保留原則時，您可以將其設定為：

- **保留資料**：使用保留原則，確保您的資料在指定的一段時間內保留，不論使用者應用程式中發生什麼情況。 出於合規性原因，仍會保留資料，且可在電子檔探索期間到期前取得資料，在此之後，您的原則會指出是不執行任何動作，或刪除資料。 例如，如果您建立團隊保留原則來保留頻道訊息7年，則郵件會保留7年，即使使用者已在小組中刪除他們的郵件也一樣。
- **刪除資料**：使用保留原則刪除資料，以確保它不是貴組織的責任。 使用團隊保留原則時，當您刪除資料時，系統會從團隊服務上的所有儲存位置永久刪除該資料。

使用小組的保留原則，您可以：

- 針對指定的持續時間保留團隊聊天和/或頻道訊息，然後不執行任何動作。
- 針對指定的持續時間保留團隊聊天和/或頻道訊息，然後刪除資料。
- 在指定的持續時間之後刪除小組聊天和/或頻道訊息。

> [!NOTE]
> 請記住，在小組中，使用者在私人聊天中共用的檔案，會儲存在共用檔案之使用者的商務用 OneDrive 帳戶中。 而且，小組成員上傳到頻道交談的檔案會儲存在小組的 SharePoint 網站上。 因此，若要保留或刪除小組中的檔案，請建立適用于商務用 OneDrive 和 SharePoint Online 的保留原則。

當資料服從保留原則時，使用者可以繼續使用它，因為資料會保留在原來的位置。 如果使用者編輯或刪除受原則制約的資料，則會將複本儲存到在原則生效時保留的安全位置。

保留原則的最低授權需求是 Office 365 E3。 若要深入瞭解授權，請參閱適用[于團隊的 Office 365 授權](Office-365-licensing.md)。

## <a name="how-teams-retention-policies-work"></a>團隊保留原則的運作方式

團隊聊天是儲存在聊天中每位使用者信箱的隱藏 SubstrateHolds 資料夾中，而團隊頻道訊息則會儲存在團隊群組信箱中的隱藏 [SubstratesHolds] 資料夾中。 小組使用一個支援 Azure 的聊天服務來儲存這個資料，而且根據預設，此服務會永久儲存資料。 使用團隊保留原則時，當您刪除資料時，會從 Exchange 信箱和基礎聊天服務中永久刪除該資料。

當您將保留原則套用至團隊聊天和頻道訊息時，會發生下列情況：

- 如果您在保留期間內由使用者編輯或刪除聊天或頻道訊息，則會將郵件複製（如果已編輯）或移動（如果已刪除）至 SubstrateHolds 資料夾，並儲存在保留期間到期的位置。 如果原則已設定為在保留期間到期後刪除資料，郵件會在保留期間到期日永久刪除。
- 如果使用者不會在保留期間中刪除聊天或頻道訊息，郵件會在保留期間到期後的一天內移至 [SubstrateHolds] 資料夾。 如果將原則設定為在保留期間到期後刪除資料，郵件移至資料夾後，就會永久刪除一天。

> [!NOTE]
> 在商務用 Skype Online 和小組交互操作聊天中，相同的流程都是可行的。 當商務用 Skype Online 聊天加入小組時，會成為小組聊天線索中的訊息，並 ingested 至適當的信箱。 團隊保留原則將會從小組執行緒中刪除這些訊息。 不過，如果已開啟商務用 Skype Online 與商務用 Skype Online 用戶端的 [交談記錄]，且這些資訊是儲存在信箱中，則該聊天資料不會由小組保留原則處理。

小組中的保留原則是以聊天或頻道訊息的建立日期為基礎，並回溯性。 換句話說，如果您建立保留原則來刪除超過90天的資料，則會刪除超過90天之前建立的小組資料。

您可以將已套用至 SharePoint Online 或商務用 OneDrive 的保留原則刪除，在刪除前，在小組聊天或頻道訊息中所參照的檔案。 在這種情況下，檔案仍會顯示在 [小組] 訊息中，當使用者按一下檔案時，會收到「找不到檔案」錯誤。 如果有人手動刪除 SharePoint Online 或商務用 OneDrive 中的檔案，也可能會在沒有原則的情況下發生這種情況。

### <a name="considerations-and-limitations"></a>考慮與限制

以下是使用團隊保留原則時應注意的一些考慮事項與限制：

- 小組需要與其他工作負載分開的保留原則。 換句話說，您必須為小組聊天與/或傳送頻道訊息建立特定的保留原則。 基於這個原因，您無法將團隊納入組織內的保留原則。

- 不支援私人通道訊息。 目前，小組的保留原則只適用于標準通道訊息。

- 小組不支援 [高級保留] 設定，例如，將原則套用至包含關鍵字或機密資訊的內容。 目前，小組中的保留原則會套用至所有聊天和/或通道郵件內容。

- 小組可能需要長達三天的時間來清除過期的訊息。 當保留期間到期時，小組保留原則會刪除聊天和頻道訊息。 不過，您可能需要長達三天的時間來清除這些訊息，並將它們永久刪除。 此外，聊天和頻道訊息在保留期到期之後以及永久刪除郵件的時間之間，都能使用 eDiscovery 工具進行搜尋。

### <a name="multiple-retention-policies-and-the-principles-of-retention"></a>多種保留原則和保留原則

如果您使用不同的期間設定多個小組保留原則，將會套用[保留原則的原則](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence)。 以下是優先考慮的事項：

- 保留 [永遠刪除 wins]
- 最長保留期間總是獲勝
- 明確包含在位置的隱式包含 wins
- 最短刪除期間獲勝

## <a name="when-to-use-retention-policies-for-teams"></a>何時使用小組的保留原則

在許多情況下，組織會考慮使用私人聊天資料，而不是頻道訊息，通常是更多與專案相關的交談。

您可以針對私人聊天設定個別保留原則（1:1 或1：許多聊天）和頻道訊息。 您也可以設定適用于組織中特定使用者或團隊的唯一原則。 針對 [團隊聊天]，您可以選取要套用原則的使用者。 針對團隊頻道訊息，您可以選取要套用原則的小組。

例如，對於頻道訊息，您可以將一年刪除原則套用到貴組織中的特定小組，並將三年的刪除原則套用至所有其他團隊。

## <a name="manage-retention-policies-for-teams"></a>管理團隊的保留原則

### <a name="using-the-security--compliance-center"></a>使用安全性 & 合規性中心

#### <a name="create-a-retention-policy"></a>建立保留原則

若要建立小組聊天與頻道訊息的保留原則，請執行下列動作：

1. 在安全性 & 合規性中心的左側導覽中，移至 [**資訊管理** > **保留**]。
2. 選取 [**建立**]。
3. 在 [**命名您的原則**] 頁面上，輸入原則的名稱和描述，然後按 **[下一步]**。
4. 在 [**設定**] 頁面上，指定您是否要保留資料、刪除（或兩者）保留期間，然後按 **[下一步]**。
5. 在 [**選擇位置**] 頁面上，執行下列動作，然後按一下 **[下一步]**：

    - 若要將原則套用到頻道訊息，請開啟 [**小組頻道] 訊息**。  如果您想要將原則套用到貴組織中的特定小組，請選取 **[選擇團隊**]，然後選取您想要的小組。
    - 若要將原則套用至聊天，請開啟 [**小組聊天**]。 如果您想要將原則套用到貴組織中的特定使用者，請選取 **[選擇使用者**]，然後選取您想要的使用者。
      > [!NOTE]
      > 當您開啟 [**小組頻道] 訊息**和/或 [**小組聊天**] 時，所有其他位置都會自動關閉。 團隊保留原則只能包含團隊位置。

        ![[選擇位置] 頁面上的 [團隊頻道訊息] 和 [團隊聊天] 選項的螢幕擷取畫面](media/retention-policies-create.png)

      > [!IMPORTANT]
      > 在**Exchange 電子郵件**或**Office 365 群組**位置中，對於使用者或群組信箱套用的保留原則，小組聊天和頻道訊息不會受到影響。 雖然團隊聊天和頻道訊息會儲存在 Exchange 中，但它們只能受到團隊位置所套用的保留原則影響。

6. 檢查您的設定，當您準備好時，請選取 [**建立此原則**]。

#### <a name="edit-a-retention-policy"></a>編輯保留原則

若要編輯團隊保留原則，請執行下列動作：

1. 在安全性 & 合規性中心的左側導覽中，移至 [**資訊管理** > **保留**]。
2. 在保留原則清單中，選取您要編輯之保留原則旁的核取方塊。
3. 選取您要編輯的專案旁的 [**編輯**]，進行變更，按一下 [**儲存**]，然後按一下 [**關閉**]。

    ![[選擇位置] 頁面上的 [團隊頻道訊息] 和 [團隊聊天] 選項的螢幕擷取畫面](media/retention-policies-edit.png)

#### <a name="delete-a-retention-policy"></a>刪除保留原則

若要刪除團隊保留原則，請執行下列動作：

1. 在安全性 & 合規性中心的左側導覽中，移至 [**資訊管理** > **保留**]。
2. 在保留原則清單中，選取您要刪除之保留原則旁的核取方塊。
3. 選取 [**刪除原則**]。

### <a name="using-powershell"></a>使用 PowerShell

若要使用[Office 365 安全性 & 合規性 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)來建立及管理小組保留原則，請使用下列 Cmdlet：

|原則|基準|
|---|---|
|[新-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy?view=exchange-ps)| [新-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule?view=exchange-ps)|
|[RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy?view=exchange-ps)| [RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps)|
|[Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy?view=exchange-ps)| [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule?view=exchange-ps)|
|[移除-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy?view=exchange-ps)| [移除-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule?view=exchange-ps)|

## <a name="known-issues"></a>已知問題

下列是追蹤及調查之小組中保留原則的已知問題。

- 在 [**團隊頻道訊息**位置] 列中的 **[選擇團隊**] 底下，您可能會看到不是「團隊」的 Office 365 群組。 未來將會解決這個問題。

- 在 [**小組聊天**位置] 列中的 **[選擇使用者**] 底下，您可能會看到 [來賓] 和 [非信箱] 使用者。 保留原則並非要針對來賓進行設定，我們正在努力從清單中移除這些原則。

- Exchange 生命週期助理（ELC）每天都會執行一次，但其 SLA 是7天。 因此，如果您有小組保留原則刪除超過60天的專案，這些專案可能會持續到67天。 這不是一種新的情況-它是在 Exchange 模型之後。 當然，在大多數情況下，不會有延遲。

## <a name="related-topics"></a>相關主題

- [保留原則概述](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)

---
title: Microsoft 團隊保留原則常見問題
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: prvijay
audience: admin
description: Microsoft 團隊中的保留原則常見問題。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dbeab6df377dd898b9c0d424288300ad7f01fbfc
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569970"
---
# <a name="microsoft-teams-retention-policies-faq"></a>Microsoft 團隊保留原則常見問題

### <a name="what-types-of-policies-can-i-set-up-in-retention-policies-and-how-do-they-work"></a>我可以在保留原則中設定哪些類型的原則，以及它們的運作方式為何？

在安全性 & 合規性中心] 中，當您為小組或任何其他工作負荷設定保留原則時，您可以設定兩種主要的原則類型： 
- 保留：這些原則可確保您的資料在指定的一段時間內保持不變，不論在最終使用者工具中發生什麼情況。 它們可確保針對合規性原因保留資料並在 eDiscovery 中提供，直到此時間到期為止。 時間到期之後，您的原則就可以指出是否要執行任何動作或刪除資料。 在團隊中，如果您建立了7年的保留原則，即使最終使用者刪除其小組訊息，這些訊息仍會保留在7年的 eDiscovery 中。
- 刪除：這些原則可確保資料不是貴組織的責任。 在指定的持續時間之後，會從團隊中的所有相關儲存空間中刪除資料。 

### <a name="can-we-include-teams-in-org-wide-policies"></a>我們可以在組織內的原則中加入團隊嗎？ 

否，目前不會。 您必須使用 [團隊位置] 列或這些團隊 Cmdlet 來建立小組聊天與頻道訊息的特定原則： [[新-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & ][-[新增-TeamsComplianceRetentionRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)]。 這些 Cmdlet 也有取得與設定的版本。

### <a name="are-these-retention-policies-retroactive"></a>這些保留原則會回溯性嗎？ 

是的，就是。 如果您建立保留原則以刪除超過60天的資料，則會刪除超過60天之前建立的小組資料。 

### <a name="what-is-the-default-retention-policy"></a>預設的保留原則為何？ 

依預設，小組聊天、頻道和檔案資料都會永久保留。 使用者可以刪除某個專案，但在沒有保留原則的情況下，小組資料永遠會歸檔到 Exchange online 信箱（使用者和群組），並留在其中供 eDiscovery 使用。 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>我可以針對原則中的使用者或團隊設定目標嗎？ 

是的，您這麼做。 在 [原則建立] 嚮導中的 [位置] 步驟中，您可以加入或排除小組（**團隊頻道訊息**）或使用者（**團隊聊天**），並為您的組織建立目標原則。 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>在保留原則中使用群組信箱位置列和小組頻道訊息位置列的主要差異為何？ 

如果您使用 [群組信箱] 和 [使用者信箱位置] 列進行 Exchange Online，則會從指定的信箱中刪除 [小組] 資料。 不過，這只會從信箱中移除資料。 它不會刪除其他團隊資料，例如聊天服務。 建議您使用團隊保留原則來正確管理所有團隊資料。 團隊保留原則會從所有儲存位置（信箱、聊天服務、團隊用戶端）移除團隊資料。 

注意：啟動小組的保留原則功能可確保只有小組原則會刪除儲存在 Exchange 信箱位置（使用者或群組）內的小組專案。 在信箱上設定的其他原則不會影響小組專案。 這在過去是如此，但已在啟動保留原則功能時修正。 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>商務用 Skype Online 與團隊交互操作聊天會發生什麼情況–它們會受到保留原則的影響嗎？

是，商務用 Skype Online 與團隊交互操作聊天的運作方式相同。 在商務用 Skype Online 聊天加入團隊之後，就會成為小組聊天線索中的訊息，並 ingested 到適當的信箱中。 在相同的流程中，小組刪除原則會從小組執行緒中刪除這些訊息。 不過，如果已開啟商務用 Skype Online 與商務用 Skype Online 用戶端的 [交談記錄]，且這些資訊已儲存在信箱中，則小組保留原則不會處理此聊天資料。

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>我可以透過安全性 & 合規性中心 Cmdlet 來執行這些操作嗎？ 我應該使用什麼？ 

完全. 您可以使用[安全性 & 合規性中心 Powershell Cmdlet]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)來建立小組保留原則。 請記住，這些不是 Exchange Online Cmdlet。 以下是我們為團隊建立的 Cmdlet。 它們遵循目前在安全性 & 合規性中心提供的保留 Cmdlet 中的現有命名法和樣式。

|原則|基準|
|---|---|
|[新-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [新-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[移除-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [移除-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>如果有多個針對不同工期的小組保留原則，那一個獲勝？

我們遵循[保留原則的原則](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)，我們也建議您這麼做。 簡短答案為： 
-   保留 [永遠刪除 wins]
-   最長保留期間總是獲勝
-   明確包含在位置的隱式包含 wins
-   最短刪除期間獲勝

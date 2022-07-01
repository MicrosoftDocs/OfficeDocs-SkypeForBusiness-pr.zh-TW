---
title: Microsoft Teams 中的團隊到期日與續約
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解團隊到期與續約，以及如何使用 Microsoft 365 群組到期原則來自動清除 Microsoft Teams 中未使用的團隊。
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1a322e07df81727c75c05ebb16c4cdabc0916a4
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564171"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Microsoft Teams 中的團隊到期日與續約

擁有大量團隊的組織通常都有從未實際使用的團隊。 這可能是因為數個原因而發生，包括產品試驗、短期團隊共同作業或團隊擁有者離開組織。 一段時間後，這類團隊就會累積起來，並造成租使用者資源的負擔。  

若要限制未使用的團隊數目，身為系統管理員，您可以使用 [Microsoft 365 群組到期原則](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) 來自動清理未使用的團隊。 由於團隊是由群組所支援，因此群組到期原則也會自動套用至團隊。

當您將到期原則套用至團隊時，團隊擁有者會在團隊到期日前 30 天、15 天和 1 天前收到團隊續約通知。 當團隊擁有者收到通知時，他們可以在團隊設定中按一下 [ **立即續約** ] 來續約團隊。

![在團隊設定中更新團隊的 [立即續約] 按鈕螢幕擷取畫面。](media/team-expiration.png "在團隊設定中更新團隊的 [立即續約] 按鈕的螢幕擷取畫面")

如果團隊擁有者未續約團隊，而且在到期原則結束之前，團隊上沒有進一步的活動，則該團隊會處於「虛刪除」狀態，這表示可以在接下來的 30 天內還原。

## <a name="team-auto-renewal"></a>團隊自動續約

有時候團隊擁有者可能因為忘記續約或在續約到期時離開而無法續約團隊。 在這些案例中，使用中的團隊可能會因為套用至團隊的到期原則而遭刪除。  

為了避免意外刪除，群組到期原則中的團隊會自動啟用自動續約。 設定群組到期原則時，任何在團隊成員到期日之前至少造訪過一個頻道的團隊，都會自動續約，而不需團隊擁有者手動介入。

## <a name="known-issues"></a>已知的問題

**小組和基礎組的到期日不相符**

在續約團隊之前，會先續約支援小組的群組。 續約期間，群組會針對未來的日期設定新的到期日。 Teams 可能無法立即看到這個新日期。 最多可能需要 24 小時來同步處理。如果您看到小組及其基礎組的到期日之間有差異，請等候 24 小時，然後再尋求進一步的支援。
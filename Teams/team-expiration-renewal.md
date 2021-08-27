---
title: 團隊到期與續約Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解團隊到期與續約，以及如何使用群組Microsoft 365，在團隊中自動清理未使用的Microsoft Teams。
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0e8f123bf7a351689747649b75f429588445a5d6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625925"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>團隊到期與續約Microsoft Teams

擁有大量團隊的組織通常擁有從未實際使用的團隊。 發生此情況的原因有幾個，包括產品試驗、短期小組共同合作，或團隊擁有者離開組織。 隨著時間的過去，這類團隊可能會累積並給租使用者資源造成負擔。  

若要限制未使用的團隊數目，您可以以系統管理員Microsoft 365[組到期](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy)政策來自動清理未使用的團隊。 由於團隊是由群組所支援，因此群組到期原則也會自動適用于團隊。

當您將到期原則適用于團隊時，團隊擁有者會于團隊到期日前 30 天、15 天和 1 天收到小組續約的通知。 當團隊擁有者收到通知時，他們可以按一下 **[在** 小組設定中立即續約以續約團隊。

![在小組設定中更新團隊的立即續約按鈕螢幕擷取畫面](media/team-expiration.png "在小組設定中更新團隊的立即續約按鈕螢幕擷取畫面")

如果團隊擁有者未為小組續約，且在到期政策結束之前團隊中沒有任何進一步活動，團隊會置於「柔刪除」狀態，這表示小組可以在接下來 30 天內還原。

## <a name="team-auto-renewal"></a>小組自動續約

有時候，團隊擁有者可能因為忘記續約或因為續約到期而無法續約。 在這些情況下，使用中團隊可能會因為適用于團隊的到期原則而被刪除。  

為了避免意外刪除，群組到期政策中的小組會自動啟用自動續約。 設定群組到期政策時，任何在到期日之前至少有一個頻道流覽的小組都會自動續約，而不需要團隊擁有者手動介入。

## <a name="known-issues"></a>已知問題

**團隊與基礎群組的到期日不相符**

在團隊續約之前，先續約支援小組的群組。 續約的一部分，會為群組設定未來日期的新到期日。 此新日期可能不會立即顯示在 Teams。 同步最多可能需要 24 小時。如果您看到團隊及其基礎群組的到期日有差異，請等候 24 小時再尋求進一步支援。
---
title: Microsoft 團隊中的小組到期與更新
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abhisgu
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解小組到期及續約，以及如何使用 Office 365 群組過期原則，自動清理 Microsoft 團隊中未使用的小組。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2fd7dfdececc9a490ff930bdba9948e9196c74f2
ms.sourcegitcommit: fc7d5e812873b648b374eef23d02c914a56b51d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2019
ms.locfileid: "37639301"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Microsoft 團隊中的小組到期與更新

擁有大量小組的組織通常會有小組，這些都不是實際使用。 這可能是因為幾個原因，包括產品實驗、短期團隊共同作業，或團隊擁有者離開組織。 隨著時間的推移，此類團隊可以在租使用者資源上累計並產生負擔。  

若要將未使用的團隊數作為系統管理員，您可以使用[Office 365 群組過期原則](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups-expiration-policy)自動清理未使用的團隊。 由於團隊是由群組來支援，因此群組過期原則也會自動套用至小組。

當您將過期原則套用至小組時，小組擁有者會在團隊的到期日之前，在30天、15天和1天之前收到小組更新通知。 當小組擁有者收到通知時，他們可以按一下 [團隊設定] 中的 [**立即更新**] 來更新小組。

![[立即更新] 按鈕的螢幕擷取畫面，用來更新小組設定中的小組](media/team-expiration.png "[立即更新] 按鈕的螢幕擷取畫面，用來更新小組設定中的小組")

如果小組擁有者沒有更新小組，則會將小組放在「虛刪除」狀態，這表示它可以在未來30天內還原。

## <a name="team-auto-renewal"></a>小組自動續約

有時候，小組擁有者可能無法更新小組，可能是因為他們忘記在續約時續約或離開。 在這些案例中，活動中使用的小組可能會因套用至小組的過期原則而被刪除。  

若要防止意外刪除，自動續約會自動啟用群組過期原則中的小組。 設定了群組過期原則之後，只要任何小組成員的到期日，就會自動更新，而不需要由團隊擁有者手動干預。

## <a name="known-issues"></a>已知問題

**團隊和基礎群組的到期日不相符**

在更新小組之前，會先續約支援小組的群組。 在續約時，會在群組中針對未來日期設定新的到期日。 在團隊中可能不會立即看到這個新日期。 同步處理可能需要長達24小時。如果您在團隊及其基礎群組的到期日之間看到差異，請等候24小時，再尋求進一步的支援。

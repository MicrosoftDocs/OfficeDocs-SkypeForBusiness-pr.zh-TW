---
title: 輔助升級|Skype Business Online 升級至 Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: 從商務用 Skype Online 升級到 Teams 的輔助升級概觀
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03ea21de9f8cb64b1221044babeeae335a52d8ea
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995192"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>從商務用 Skype Online 協助升級至 Microsoft Teams

Microsoft 提供 Teams 的協助升級，以協助組織在服務于 2021 年 7 月 31 日淘汰時，順利從商務用 Skype Online 進行轉換。 輔助升級可以減少您需要執行的技術工作數量，並更專注于組織準備、使用者認知和 Teams 訓練。

建議您在 [升級前先](https://aka.ms/SkypeToTeams) 查看我們的升級指南。 我們的升級指南包含建議的活動，以及完成從商務用 Skype Online 升級至 Teams 的實用資源。 本指南適用于規劃升級至 Teams 的任何組織，無論他們管理升級的所有層面，或使用輔助程式。

> [!NOTE]
> 如果您已排程協助升級至 Teams，您可以在排定的升級日期之前，從商務用 Skype Online 執行自己的升級。 若要進一步瞭解如何手動升級至 Teams，請參閱我們的 [升級指南](https://aka.ms/SkypeToTeams)。
>
> 商務用 Skype Server 內部部署無法進行輔助升級。

## <a name="notifications-for-scheduled-customers"></a>已排程客戶的通知

排定協助升級 Teams 的商務用 Skype Online 客戶會收到一系列的升級通知。 這些通知將在排定的升級日期前 90 天開始。 這些通知會以 Microsoft  365 訊息中心中的變更文章計畫、在 Teams 系統管理中心升級儀表板通知，以及應用程式內標標傳送給使用者。

升級通知會包含輔助升級的排定日期，並連結至升級資源與訓練，以協助推動 Teams 的採用和使用。

## <a name="the-assisted-upgrade-experience"></a>輔助升級體驗

輔助升級將于 2021 年 8 月開始，並分享上述排程通知中的租使用者特定日期。

升級持續時間會因使用者數量和部署特性而不同。 不過，在大多數情況下，租使用者中的使用者將在升級開始後的 24 小時內升級。 在此期間，使用者仍可存取商務用 Skype Online 功能。 升級完成且使用者登出商務用 Skype Online 之後，就會開始使用 Teams 進行傳訊、會議和通話。

## <a name="the-post-upgrade-experience"></a>升級後的體驗

輔助升級完成後，升級使用者的共存模式會設為 Teams Only，且 Microsoft 只能變更為不同的共存模式。 建議您在升級前先查看 [Teams Only](teams-only-mode-considerations.md) 模式考慮事項。 下表提供 Teams Only 使用者體驗的高層次概觀。

:::row:::
    :::column span="1":::
        **聊天和通話**
    :::column-end:::
    :::column span="3":::
        - 在 Teams 中開始和接收所有通話和聊天
        - 使用者可以在任何商務 (聊天/通話) 任何商務用 Skype 使用者通訊
        - 組織可以管理外部存取許可權，讓 Teams 使用者與 Skype 消費者服務的使用者 [通訊](manage-external-access.md)
        - 嘗試登錄商務用 Skype Online 的 Teams 使用者將會重新導向至 Teams
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **會議**
    :::column-end:::
    :::column span="3":::
        - 使用者在 Teams 中排程所有新會議 (外掛程式已取代) 
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **移移的資料**
    :::column-end:::
    :::column span="3":::
        - 商務用 Skype Online 的現有連絡人，包括 (但沒有通訊群組清單
        - 現有的商務用 Skype Online 會議會轉換成 Teams 會議
    :::column-end:::
:::row-end:::

## <a name="related-content"></a>相關內容

- [開始升級您的 Microsoft Teams](upgrade-start-here.md)
- [終止對商務用 Skype Online 的支援](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Teams 僅模式考慮事項](teams-only-mode-considerations.md)

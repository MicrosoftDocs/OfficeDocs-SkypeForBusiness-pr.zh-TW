---
title: 輔助升級|SkypeBusiness Online Teams升級
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: 從線上到 商務用 Skype 的Teams
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
ms.openlocfilehash: 9c19a0569fe56e9bf8c822b1418ac2fe0685532b
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855932"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>從線上到 商務用 Skype 的輔助升級Microsoft Teams

Microsoft 提供協助升級Teams協助組織從 商務用 Skype Online 順利轉換，因為服務將于 2021 年 7 月 31 日淘汰。 無論貴組織是在 商務用 Skype Online 和 **商務用 Skype Server)** 環境中使用混合式 (使用者從 *商務用 Skype Online* 或 *商務用 Skype Online* 升級，輔助升級都可減少您需要執行的技術工作數量，並更專注于組織準備、使用者認知和 Teams 訓練。

建議您在 [升級前先](https://aka.ms/SkypeToTeams) 查看我們的升級指南。 我們的升級指南包含建議的活動和實用資源，可完成從 商務用 Skype Online Teams。 本指南適用于規劃升級至 Teams的組織，無論他們管理升級的所有層面或使用輔助程式。

> [!NOTE]
> 如果您排程了輔助升級至 Teams，您可以在排定的升級日期商務用 Skype線上執行您自己的升級。 若要進一步瞭解如何手動升級至 Teams，請參閱我們的[升級指南](https://aka.ms/SkypeToTeams)。
>
> 輔助升級不適用於內部部署商務用 Skype Server。

## <a name="notifications-for-scheduled-customers"></a>已排程客戶的通知

商務用 Skype排定協助升級至 Teams的線上客戶會收到一系列的升級通知。 這些通知將在排定的升級日期前 90 天開始。 這些通知會以郵件中心中的變更文章Microsoft 365、在系統管理中心升級儀表板通知Teams，以及將應用程式內標標傳送給使用者。

升級通知會包含輔助升級的排定日期，並連結至升級資源與訓練，以協助推動採用和使用Teams。

## <a name="the-assisted-upgrade-experience"></a>輔助升級體驗

輔助升級將于 2021 年 8 月開始，並分享上述排程通知中的租使用者特定日期。

您的輔助升級體驗會稍有不同，商務用 Skype Online 版或具有混合式商務用 Skype的線上版：

- **商務用 Skype Online-only** 輔助升級程式會將原則 `TeamsUpgradeOverridePolicy` 適用于您的組織。 當此原則適用時，您的所有 商務用 Skype Online 使用者都會置於Teams模式。
- **商務用 Skype混合式線上** 混合式環境的使用者可能屬於下列其中一個類別：

  - 內部部署使用者商務用 Skype Server
  - 商務用 Skype目前為僅Teams線上使用者
  - 商務用 Skype未 **在僅Teams** 線上使用者

  如果您在上述各個類別中混合使用使用者，輔助升級程式只會將 商務用 Skype Online 使用者切換為 Teams 如果尚未進入該模式。 內部部署商務用 Skype使用者不會受到輔助升級程式的影響。

> [!NOTE]
> 如果輔助升級排程為 2021 年 7 月 31 日之後的日期，別擔心。 您的組織將能夠使用線上商務用 Skype升級完成。

升級持續時間會因使用者數量和部署特性而不同。 在大多數情況下，租使用者中的使用者將在升級開始後的 24 小時內升級。 在此期間，使用者仍可存取 商務用 Skype Online 功能。 升級完成後，使用者登出 商務用 Skype Online 後，就會開始使用 Teams、會議和通話等功能。

## <a name="the-post-upgrade-experience"></a>升級後的體驗

當輔助升級完成時，升級使用者的共存模式會設定為Teams模式。 建議您在升級前Teams[僅模式](teams-only-mode-considerations.md)考慮事項。 下表提供僅提供使用者體驗Teams概觀。

:::row:::
    :::column span="1":::
        **聊天和通話**
    :::column-end:::
    :::column span="3":::
        - 所有通話和聊天在 Teams
        - 使用者可以與 (聊天/通話) 任何商務用 Skype通訊
        - 組織可以Teams管理外部存取許可權，Skype使用者與消費者服務的使用者[通訊](manage-external-access.md)
        - Teams嘗試在線上商務用 Skype的使用者會重新導向至Teams
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **會議**
    :::column-end:::
    :::column span="3":::
        - 使用者排程外掛程式取代Teams (中) 
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **移移的資料**
    :::column-end:::
    :::column span="3":::
        - 來自 商務用 Skype Online 的現有連絡人，包括 (通訊群組清單) 
        - 當使用者第一次登入Teams連絡人會移移。
            > [!IMPORTANT]
            >您必須在升級完成後的 90 天內移移連絡人。
        - 現有的商務用 Skype線上會議會轉換成Teams會議
            > [!IMPORTANT]
            > 擁有純粹 商務用 Skype Online 組 (的客戶，必須使用會議移 (MMS) 將現有的 商務用 Skype Online 會議移Teams會議。 我們建議您在輔助升級日期之前使用 MMS。 有關 MMS 的資訊，請參閱[使用會議移 (MMS) 。](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
    :::column-end:::
:::row-end:::

如果您有混合式部署商務用 Skype Server升級至 Teams，您可以在升級完成商務用 Skype Server Teams移動使用者。

## <a name="related-content"></a>相關內容

- [開始升級您的 Microsoft Teams](upgrade-start-here.md)
- [終止對商務用 Skype Online 的支援](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Teams僅模式考慮事項](teams-only-mode-considerations.md)

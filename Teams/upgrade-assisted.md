---
title: 輔助升級|Skype Business Online Teams升級
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: 從線上至 商務用 Skype 的Teams升級概Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a162a9151413137282d80e47f8f2b08c841e171a
ms.sourcegitcommit: 39378888464ade3cb45879a449143f40f202f3e9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2022
ms.locfileid: "64456886"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>協助從線上商務用 Skype升級至Microsoft Teams

Microsoft 于 商務用 Skype 2021 年 7 月 31 日停用線上版。  Microsoft 提供輔助升級程式，以協助組織將剩餘的線上商務用 Skype移至Teams。  無論您的組織是：Microsoft 輔助升級可以減少技術工作的數量，並簡化向沒有線上商務用 Skype世界轉換：
 - 一個純粹線上組織，需要從 *商務用 Skype Online* 升級，成為純粹Teams，或
 - 一個混合式組織，商務用 Skype *Online* 和內部部署 *商務用 Skype Server* 環境中的使用者，這必須僅將 商務用 Skype *Online* 使用者升級為 Teams。

建議您在升級 [前先查看](https://aka.ms/SkypeToTeams) 我們的升級指南。 我們的升級指南包含建議的活動和實用資源，可完成從 商務用 Skype Online Teams。 本指南適用于規劃升級至 Teams的組織，無論他們管理升級的所有層面或使用輔助程式。

## <a name="the-assisted-upgrade-experience"></a>輔助升級體驗
商務用 Skype排定協助升級至 Teams 的 Online 客戶會收到各種通知：規劃 Microsoft 365 訊息中心中的變更文章、在 Teams 系統管理中心升級儀表板通知，以及將應用程式內標標升級給使用者。 訊息中心與系統管理中心中的升級通知Teams包括輔助升級的排定日期，以及升級資源與訓練的連結，以協助推動採用及使用Teams。

根據貴組織是否將任何使用者放在內部部署環境，輔助升級體驗商務用 Skype Server不同：
- **純粹線上組織：** 若組織 *沒有任何* 內部部署Skype Busineess Server 使用者 `TeamsUpgradeOverridePolicy` ，輔助升級程式會將原則適用于您的組織。 當此原則適用時，商務用 Skype Online 的所有使用者都會置於 TeamsOnly 模式中。
- **具有內部部署使用者** 商務用 Skype混合式組織：這包括任何使用者位於 商務用 Skype Server 的組織，無論是否已進行混合式配置。 這些組織的使用者可能屬於下列其中一個類別：

  - 內部部署使用者位於商務用 Skype Server (使用者，Teams使用者Teams使用者) 
  - TeamsOnly 使用者以 商務用 Skype Online 商務用 Skype
  - 在 Online 中主商務用 Skype TeamsOnly 使用者

輔助升級程式只會影響最後一個類別的使用者：非 Teams 只有位於 商務用 Skype Online 中的使用者會升級至 Teams 模式。 內部商務用 Skype使用者和現有的 TeamsOnly 使用者不會受到輔助升級程式的影響。

> [!NOTE]
> 您的組織可以繼續使用線上商務用 Skype，直到您的升級完成。 如果您排程了輔助升級至 Teams，您可以在排定的升級日期商務用 Skype線上執行您自己的升級。 若要進一步瞭解如何手動升級至 Teams，請參閱我們的[升級指南](https://aka.ms/SkypeToTeams)。

升級持續時間會因使用者數量和部署特性而不同。 在大多數情況下，租使用者中的使用者將在升級開始後的 24 小時內升級。 在此期間，使用者仍可存取線上商務用 Skype功能。 升級完成且使用者登出 商務用 Skype Online 後，就會開始使用 Teams、會議和通話功能。

## <a name="the-post-upgrade-experience"></a>升級後的體驗

當輔助升級完成時，升級使用者的共存模式會設定為Teams模式。 建議您在升級前Teams[僅模式](teams-only-mode-considerations.md)考慮事項。 下表提供僅提供使用者體驗Teams概觀。

:::row:::
    :::column span="1":::
        **聊天和通話**
    :::column-end:::
    :::column span="3":::
        - 所有通話和聊天在 Teams
        - 使用者可以與 (聊天/通話) 任何商務用 Skype通訊
        - 組織可以管理Teams存取許可權，讓Skype使用者與消費者服務的使用者[通訊](manage-external-access.md)
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
        - 來自 商務用 Skype Online 的現有連絡人， (沒有通訊群組清單) 
        - 當使用者第一次登入連絡人Teams連絡人。
            > [!IMPORTANT]
            >您必須在升級完成後的 90 天內移移連絡人。
        - 現有的商務用 Skype線上會議會轉換成Teams會議
            > [!IMPORTANT]
            > 擁有純粹 商務用 Skype Online 商務用 Skype的客戶，必須使用會議移 (MMS) 將現有的 商務用 Skype Online 會議移Teams會議。 我們建議您在輔助升級日期之前使用 MMS。 有關 MMS 的資訊，請參閱 [使用會議移 (MMS) ](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。
    :::column-end:::
:::row-end:::

如果您有混合式部署商務用 Skype Server升級至 Teams，您可以在升級完成商務用 Skype Server Teams移動使用者。

## <a name="related-content"></a>相關內容

- [開始升級您的 Microsoft Teams](upgrade-start-here.md)
- [終止對商務用 Skype Online 的支援](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Teams模式考慮](teams-only-mode-considerations.md)

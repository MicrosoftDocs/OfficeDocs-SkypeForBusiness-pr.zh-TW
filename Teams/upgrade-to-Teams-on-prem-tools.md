---
title: 從商務用 Skype 內部部署升級至 Teams 的工具
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 從商務用 Skype 升級至 Teams 的工具
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5585a2d2995b2f7d470c4d07eab3f5bb7f1934c7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097499"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>適用于 IT 系統管理員的升級至 &mdash; Teams 的工具

本文將說明從商務用 Skype 升級到 Teams 的工具。 

開始升級之前，Microsoft 會建議下列文章說明重要的升級概念和共存行為：

- [Teams 與商務用 Skype 共存](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [共存模式 - 參照](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 用戶端體驗和遵從共存模式](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a>管理升級的工具

無論您選擇哪一種升級方法，對於已經擁有商務用 Skype Online 的使用者，您可以使用 TeamsUpgradePolicy 管理向 TeamsOnly 的轉換，而 [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)會控制使用者的共存模式。 對於在商務用 Skype Server 中使用內部部署帳戶的使用者，您也可以將它們 `Move-CsUser` 移至 [雲端](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)。  有關每個模式的資訊，請參閱 [共存模式](migration-interop-guidance-for-teams-with-skype.md)。

> [!NOTE]
> 如果您目前使用商務用 Skype Online Connector 來管理您的服務，則需要移至 Teams PowerShell 模組並更新現有的 PowerShell 腳本。 請參閱 [從商務用 Skype Online Connector 移至 Teams PowerShell 模組](teams-powershell-move-from-sfbo.md) 以瞭解更多資訊。

無論您是使用商務用 Skype 模式執行選取功能轉換，或只是從預設島嶼組態升級至 TeamsOnly 模式，TeamsUpgradePolicy 都是已擁有商務用 Skype Online 使用者的主要工具。 就像 Teams 中的其他任何策略一樣，您可以直接將 TeamsUpgradePolicy 指派給使用者。 您也可以將策略設定為租使用者範圍的預設值。 任何指派給使用者的優先順序都高於租使用者的預設設定。  您可以在 Teams 系統管理主控台和 PowerShell 中管理該策略。

您也可以將 TeamsUpgradePolicy 的任何模式指派給位於商務用 Skype 內部部署中的使用者，但 TeamsOnly 模式除外。 **TeamsOnly 模式只能** 指派給已經位於商務用 Skype Online 中的使用者。 這是因為只有使用者位於商務用 Skype Online 中，才能與商務用 Skype 使用者和聯盟及 Microsoft 365 電話系統功能進行交互操作。 此外，如果您有商務用 Skype 內部部署 (則無法將 **TeamsOnly** 模式指派為整個租使用者的預設模式 (此部署會以 Lyncdiscover DNS 記錄的存在來偵測到指向 Office 365 之外的位置。

擁有內部部署商務用 Skype 帳戶的使用者必須移至 [線上 (移至](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 商務用 Skype Online，或直接移至 Teams) 使用商務用 Skype 內部部署工具集的 Move-CsUser。 這些使用者可以在 1 或 2 個步驟中移至 TeamsOnly：

-   1 個步驟：在 Move-CsUser 中指定 -MoveToTeams 切換。 這需要使用商務用 Skype Server 2019 或具有 CU8 或更新更新的商務用 Skype Server 2015。

-   2 個步驟：執行 Move-CsUser 之後，使用 TeamsUpgradePolicy 將 TeamsOnly 模式授予使用者。

不同于其他政策，在 Microsoft 365 或 Office 365 中無法建立 TeamsUpgradePolicy 的新實例。 所有現有的實例都內建于服務中。   (請注意，mode 是 TeamsUpgradePolicy 中的屬性，而不是策略實例的名稱。) 在某些情況下 ，但並非所有的情況中，策略實例的名稱與模式相同。 特別是，若要將 TeamsOnly 模式指派給使用者，您將授予該使用者 TeamsUpgradePolicy 的 「UpgradeToTeams」 實例。 若要查看所有實例的清單，您可以執行下列命令：

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

若要將線上使用者升級至 TeamsOnly 模式，請指派「UpgradeToTeams」實例： 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

若要將內部部署商務用 Skype 使用者升級至 TeamsOnly 模式，Move-CsUser內部部署工具集使用以下選項：

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

若要變更租使用者中所有使用者的模式，但具有明確每個使用者授權的使用者除外 (優先) ，請執行下列命令：

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>如果您有內部部署商務用 Skype 帳戶的任何使用者，您無法在租使用者層級指派 TeamsOnly 模式。 您必須使用 Move-CsUser 將這些使用者個別移至雲端。


## <a name="using-notifications-in-skype-for-business-clients"></a>在商務用 Skype 用戶端中使用通知

系統管理員可以選擇在商務用 Skype 用戶端中提供使用者通知，通知使用者他們即將升級至 Teams，如下圖所示。 例如，在系統管理員打算將一組使用者升級至 TeamsOnly 模式的一周之前，系統管理員可能會想要針對該使用者群組開啟這些通知。 這些通知會使用具有 NotifySfbUsers=true 的 TeamsUpgradePolicy 實例啟用。  針對 TeamsOnly 外的所有模式，每個模式實際上有兩個實例，對應到 NotifySfbUsers 的兩個值。  針對 TeamsOnly 外的所有模式，每個模式實際上有兩個實例，對應到 NotifySfbUsers 的兩個值。 

![顯示通知的圖表](media/teams-upgrade-sfb-with-notifications.png)

如果您的使用者是商務用 Skype Online 中的主使用者，只要指派與使用者模式相同的策略實例，但使用 NotifySfbUsers=true。 

如果您的使用者位於商務用 Skype Server 內部部署中，您必須使用內部部署工具集，而您需要商務用 Skype Server 2019 或適用于商務用 Skype Server 2015 的 CU8。 對於內部部署在商務用 Skype Server 中的使用者，會遵守 TeamsUpgradePolicy 線上實例的 mode 屬性，但 NotifySfbUsers 屬性則沒有。 如果需要通知，您必須建立 TeamsUpgradePolicy 的內部部署實例，以控制用戶端行為。 

在內部部署 PowerShell 視窗中，使用 NotifySfbUsers=true 建立 TeamsUpgradePolicy 的新實例：

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

接著，使用相同的內部部署 PowerShell 視窗，將新策略指派給想要的使用者：

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>會議移移

當使用者移轉至 TeamsOnly 模式時，根據預設，他們組織的現有商務用 Skype 會議會轉換成 Teams。 您可以將 TeamsOnly 模式指派給使用者時，選擇性地停用預設行為。 將使用者從內部部署移轉時，會議必須移轉至雲端，以使用線上使用者帳戶運作，但如果您未指定 -MoveToTeams，會議會移轉為商務用 Skype 會議，而不是轉換成 Teams。 

在租使用者層級指派 TeamsOnly 模式時，不會針對任何使用者觸發會議移移。 如果您想要在租使用者層級指派 TeamsOnly 模式並移移會議，您可以使用 PowerShell 在租使用者 (中取得使用者清單，例如，在 Get-CsOnlineUser 中使用所需的任何篩選) ，然後迴圈流覽這些使用者，以啟動使用 Start-CsExMeetingMigration 進行會議移入。 詳細資料請參閱使用會議移 ([MMS) 。](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)



## <a name="related-links"></a>相關連結

[共存模式 - 參照](migration-interop-guidance-for-teams-with-skype.md) 

[設定商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連接](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用會議移 (MMS) ](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
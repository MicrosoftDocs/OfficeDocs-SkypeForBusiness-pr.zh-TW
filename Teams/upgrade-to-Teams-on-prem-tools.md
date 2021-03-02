---
title: 從商務用 Skype 內部部署升級到 Teams 的工具
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
ms.openlocfilehash: afe6b57b5b2b430c056d49b29a752e55bd4a0afe
ms.sourcegitcommit: 79b19b326ef40bf04af03021a7c6506fdd9417ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2021
ms.locfileid: "50397538"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>適用于 IT 系統管理員升級至 Teams &mdash; 的工具

本文將說明從商務用 Skype 升級到 Teams 的工具。 

在開始升級之前，Microsoft 會建議下列文章說明重要的升級概念和共存行為：

- [Teams 和商務用 Skype 的共存](upgrade-to-teams-on-prem-coexistence.md)
- [共存模式 - 參照](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 用戶端體驗和遵從共存模式](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a>管理升級的工具

無論您選擇哪一種升級方法，對於已經有商務用 Skype Online 的使用者，您都使用 [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)管理 TeamsOnly 的轉換，此模式會控制使用者的共存模式。 對於在商務用 Skype Server 中擁有內部部署帳戶的使用者，您也可以將它們移至 `Move-CsUser` [雲端](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)。  有關每個模式的資訊，請參閱 [共存模式](migration-interop-guidance-for-teams-with-skype.md)。

> [!NOTE]
> 如果您目前使用商務用 Skype Online Connector 來管理服務，您必須移至 Teams PowerShell 模組並更新現有的 PowerShell 腳本。 詳細資訊 [請參閱從商務用 Skype Online Connector](teams-powershell-move-from-sfbo.md) 移至 Teams PowerShell 模組。

無論您是使用商務用 Skype 模式執行選取功能轉換，或只是從預設群島組態升級到 TeamsOnly 模式，TeamsUpgradePolicy 都是擁有商務用 Skype Online 使用者的主要工具。 就像 Teams 中的其他任何政策一樣，您可以直接將 TeamsUpgradePolicy 指派給使用者。 您也可以將策略設定為全租使用者的預設。 任何指派給使用者的作業都優先于租使用者的預設設定。  您可以在 Teams 系統管理主控台和 PowerShell 中管理該政策。

您也可以將 TeamsOnly 模式以外的任何 TeamsUpgradePolicy 模式指派給位於商務用 Skype 內部部署中的使用者。 **TeamsOnly** 模式只能指派給已位於商務用 Skype Online 中的使用者。 這是因為只有使用者位於商務用 Skype Online 中，才能與商務用 Skype 使用者和聯盟以及 Microsoft 365 電話系統功能進行互動。 此外，如果您有商務用 Skype 內部部署 (如果 Lyncdiscover DNS 記錄指向 Office 365 之外的位置，您就無法將 **TeamsOnly** 模式指派為全租使用者的預設模式。

擁有內部部署商務用 Skype 帳戶的使用者必須[](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)移至線上 (或是移至商務用 Skype Online，或直接使用商務用 Skype 內部部署工具集的) Move-CsUser 移至 Teams Move-CsUser。 這些使用者可以按照 1 或 2 個步驟移至 TeamsOnly：

-   1 個步驟：在 Move-CsUser 中指定 -MoveToTeams 參數。 這需要商務用 Skype Server 2019 或商務用 Skype Server 2015 與 CU8 或更新版。

-   2 個步驟：執行 Move-CsUser 之後，使用 TeamsUpgradePolicy 將 TeamsOnly 模式授予使用者。

不同于其他策略，在 Microsoft 365 或 Office 365 中無法建立 TeamsUpgradePolicy 的新實例。 所有現有的實例都內建于服務中。   (請注意，模式是 TeamsUpgradePolicy 中的屬性，而不是一個策略實例的名稱。) 在某些情況中 ，但並非全部，該策略實例的名稱與模式相同。 特別是，若要將 TeamsOnly 模式指派給使用者，您必須將 TeamsUpgradePolicy 的「UpgradeToTeams」實例授予該使用者。 若要查看所有實例的清單，您可以執行下列命令：

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

若要將線上使用者升級至 TeamsOnly 模式，請指派「UpgradeToTeams」實例： 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

若要將內部部署商務用 Skype 使用者升級至 TeamsOnly 模式，Move-CsUser內部部署工具集：

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

若要變更租使用者中所有使用者的模式，但具有明確每個使用者授予許可權的使用者除外 (優先) ，請執行下列命令：

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>如果您有內部部署商務用 Skype 帳戶的任何使用者，您無法在租使用者層級指派 TeamsOnly 模式。 您必須使用 Move-CsUser，將這些使用者個別移至雲端。


## <a name="using-notifications-in-skype-for-business-clients"></a>在商務用 Skype 用戶端中使用通知

系統管理員可選擇在商務用 Skype 用戶端中提供使用者通知，通知使用者即將升級至 Teams，如下圖所示。 例如，在系統管理員計畫將一組使用者升級至 TeamsOnly 模式的一周之前，系統管理員可能會想要針對該使用者群組開啟這些通知。 這些通知是使用 TeamsUpgradePolicy 實例與 NotifySfbUsers=true 啟用。  對於 TeamsOnly 外的所有模式，每個模式實際上都有兩個實例，對應到 NotifySfbUsers 的兩個值。  對於 TeamsOnly 外的所有模式，每個模式實際上都有兩個實例，對應到 NotifySfbUsers 的兩個值。 

![顯示通知的圖表](media/teams-upgrade-sfb-with-notifications.png)

如果您的使用者是商務用 Skype Online 的首頁，只要指派與使用者模式相同的策略實例，但使用 NotifySfbUsers=true。 

如果您的使用者位於商務用 Skype Server 內部部署中，您必須使用內部部署工具集，而且您需要商務用 Skype Server 2019 或商務用 Skype Server 2015 的 CU8。 對於位於內部部署商務用 Skype Server 的使用者，會使用 TeamsUpgradePolicy 線上實例的 mode 屬性，但不使用 NotifySfbUsers 屬性。 如果需要通知，您必須建立 TeamsUpgradePolicy 內部部署實例，以控制用戶端行為。 

在內部部署 PowerShell 視窗中，使用 NotifySfbUsers=true 建立 TeamsUpgradePolicy 的新實例：

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

然後，使用相同的內部部署 PowerShell 視窗，將新策略指派給所需的使用者：

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>會議移移

當使用者移轉至 TeamsOnly 模式時，根據預設，他們組織的現有商務用 Skype 會議將會轉換成 Teams。 您可以選擇性地停用將 TeamsOnly 模式指派給使用者時的預設行為。 從內部部署移動使用者時，會議必須移至雲端，以使用線上使用者帳戶運作，但如果您未指定 -MoveToTeams，會議會以商務用 Skype 會議方式移轉，而不是轉換成 Teams。 

在租使用者層級指派 TeamsOnly 模式時，不會針對任何使用者觸發會議移移。 如果您想要在租使用者層級指派 TeamsOnly 模式並移移會議，您可以使用 PowerShell 在租使用者 (中取得使用者清單 (例如，使用 Get-CsOnlineUser 具有所需的任何篩選準則) 然後迴圈流覽這些使用者，以使用 Start-CsExMeetingMigration 觸發會議移入。 有關詳細資料，請參閱使用會議移 ([MMS) 。](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)



## <a name="related-links"></a>相關連結

[共存模式 - 參照](migration-interop-guidance-for-teams-with-skype.md) 

[設定商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用會議移 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)


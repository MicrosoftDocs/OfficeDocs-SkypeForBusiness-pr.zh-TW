---
title: 從內部部署Teams升級商務用 Skype工具
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 從 商務用 Skype 升級至 Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d98257e9a29564d22b57c5cc537d703bbb1fe842
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729302"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>適用于 IT 系統管理員的升級Teams &mdash; 工具

本文將說明從 Teams 升級商務用 Skype。 

在開始升級之前，Microsoft 建議下列文章說明重要的升級概念和共存行為：

- [Teams和商務用 Skype](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [共存模式 - 參照](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 用戶端體驗和遵從共存模式](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a>管理升級的工具

無論您選擇哪一種升級方法，對於已經有 商務用 Skype Online 的使用者，您都使用 TeamsUpgradePolicy 管理向 TeamsOnly 的轉換，而[TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)會控制使用者的共存模式。 對於擁有內部部署帳戶的使用者商務用 Skype Server，您也可以將它們移至 `Move-CsUser` [雲端](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)。  有關每個模式的資訊，請參閱 [共存模式](migration-interop-guidance-for-teams-with-skype.md)。

> [!NOTE]
> 如果您目前使用 商務用 Skype連線連接器來管理您的服務，您必須移至 PowerShell 模組Teams並更新現有的 PowerShell 腳本。 請參閱[從線上連接器商務用 Skype移至 powerShell Teams模組以](teams-powershell-move-from-sfbo.md)瞭解更多資訊。

無論您使用不同的模式執行選取功能轉換商務用 Skype或只是從預設群島組態升級至 TeamsOnly 模式，TeamsUpgradePolicy 都是主要工具。就像其他系統Teams一樣，您可以直接將 TeamsUpgradePolicy 指派給使用者。 您也可以將策略設定為租使用者範圍的預設值。 指派給使用者的任何作業，都優先于租使用者的預設設定。  您可以在系統管理主控台和 PowerShell Teams管理原則。

您可以將 TeamsUpgradePolicy 的任何模式指派給位於內部部署中商務用 Skype TeamsOnly 模式除外。 相反地，雲端使用者只能指派 TeamsOnly 模式。 **TeamsOnly** 模式只能指派給已經位於雲端中的使用者，因為只有使用者位於 商務用 Skype Online 中，才能與 商務用 Skype 使用者以及 Microsoft 365 電話系統 使用者進行交互操作和聯盟功能。  此外，如果您有 商務用 Skype 內部部署 (，則無法將 **TeamsOnly** 模式指派為整個租使用者的預設模式，因為 lyncdiscover DNS 記錄的存在會偵測到 Office 365 外的位置。 詳細資料請參閱[停用混合式組組以完成](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid)移Teams 。

擁有商務用 Skype內部部署帳戶的使用者，必須使用 Teams內部部署[](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)工具集Move-CsUser移至 商務用 Skype 模式。 

與其他政策不同，在系統或系統內無法建立 TeamsUpgradePolicy Microsoft 365 Office 365。 所有現有的實例都內建于服務中。   (請注意，mode 是 TeamsUpgradePolicy 中的屬性，而非策略實例的名稱。) 在某些情況下 ，但並非所有的情況中，策略實例的名稱與模式相同。 特別是，若要將 TeamsOnly 模式指派給使用者，您將授予該使用者 TeamsUpgradePolicy 的 「UpgradeToTeams」 實例。 若要查看所有實例的清單，您可以執行下列命令：

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

若要將線上使用者升級至 TeamsOnly 模式，請指派「UpgradeToTeams」實例： 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

若要將內部部署使用者商務用 Skype TeamsOnly 模式，請使用Move-CsUser工具集的以下選項：

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -credential $cred
```

若要變更租使用者中所有使用者的模式，但具有明確每個使用者授權的使用者除外 (優先) ，請執行下列命令：

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>如果您有任何擁有內部商務用 Skype使用者，您無法在租使用者層級指派 TeamsOnly 模式。 您必須使用 Move-CsUser 將這些使用者個別Teams至僅使用模式。


## <a name="using-notifications-in-skype-for-business-clients"></a>在用戶端商務用 Skype通知

系統管理員可選擇在 商務用 Skype 中提供使用者通知，通知使用者他們即將升級至 Teams，如下圖所示。 例如，在系統管理員打算將一組使用者升級至 TeamsOnly 模式的一周之前，系統管理員可能會想要開啟該使用者群組的這些通知。 這些通知會使用具有 NotifySfbUsers=true 的 TeamsUpgradePolicy 實例啟用。  針對 TeamsOnly 外的所有模式，每個模式實際上有兩個實例，對應到 NotifySfbUsers 的兩個值。  針對 TeamsOnly 外的所有模式，每個模式實際上有兩個實例，對應到 NotifySfbUsers 的兩個值。 

![顯示通知的圖表。](media/teams-upgrade-sfb-with-notifications.png)

如果您的使用者是使用 商務用 Skype Online，只要指派與使用者模式相同的策略實例，但使用 NotifySfbUsers=true。 

如果您的使用者位於 商務用 Skype Server 內部部署中，您必須使用內部部署工具集，2015 年 2019 商務用 Skype Server CU 商務用 Skype Server 8。 對於位於內部商務用 Skype Server中的使用者，會遵守 TeamsUpgradePolicy 線上實例中的 mode 屬性，但 NotifySfbUsers 屬性不會。 如果需要通知，您必須建立 TeamsUpgradePolicy 內部部署實例，以控制用戶端行為。 

在內部部署 PowerShell 視窗中，使用 NotifySfbUsers=true 建立 TeamsUpgradePolicy 的新實例：

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

接著，使用相同的內部部署 PowerShell 視窗，將新策略指派給想要的使用者：

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>會議移移

當使用者移轉至 TeamsOnly 模式時，根據預設商務用 Skype他們組織的現有會議將會轉換成Teams。 您可以將 TeamsOnly 模式指派給使用者時，選擇性地停用預設行為。 將使用者從內部部署移轉時，會議必須移轉至雲端，以使用線上使用者帳戶運作，但如果您未指定 -MoveToTeams，會議會移轉為 商務用 Skype 會議，而不是轉換成 Teams。 

在租使用者層級指派 TeamsOnly 模式時，不會針對任何使用者觸發會議移移。 如果您想要在租使用者層級指派 TeamsOnly 模式並移移會議，您可以使用 PowerShell 在租使用者 (中取得使用者清單，例如，在 Get-CsOnlineUser 中使用所需的任何篩選) ，然後迴圈流覽這些使用者，以啟動使用 Start-CsExMeetingMigration 進行會議移入。 詳細資料請參閱使用會議移 ([MMS) 。](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)



## <a name="related-links"></a>相關連結

[共存模式 - 參照](migration-interop-guidance-for-teams-with-skype.md) 

[設定使用者與商務用 Skype Server之間的Microsoft 365 Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用會議移 (MMS) ](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

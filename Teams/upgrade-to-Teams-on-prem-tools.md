---
title: 從商務用 Skype 內部部署（Microsoft 團隊）升級至團隊
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 從商務用 Skype 升級至 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bf51019aad5b2deb6239c698623475263241b3f
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940626"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>為 IT 系統管理員升級至團隊的工具 &mdash;

本文將說明升級至團隊的工具。 本文是幾個描述 IT 系統管理員升級概念與實現的第三個專案。  

- [概觀](upgrade-to-teams-on-prem-overview.md)
- [升級方法](upgrade-to-teams-on-prem-upgrade-methods.md)
-  (本文**的管理升級工具**) 
- [使用商務用 Skype 內部部署之組織的其他考慮事項](upgrade-to-teams-on-prem-considerations.md)
- [實施您的升級](upgrade-to-teams-on-prem-implement.md)
- [公用交換電話網絡 (PSTN) 考慮](upgrade-to-teams-on-prem-pstn-considerations.md)

此外，下列文章說明重要的升級概念與共存行為：

- [團隊與商務用 Skype 的共存](upgrade-to-teams-on-prem-coexistence.md)
- [共存模式-參考](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 用戶端體驗和遵從共存模式](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a>管理升級的工具

無論您選擇哪一種升級方法，都可以使用 [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)來管理切換至 TeamsOnly，以控制使用者的共存模式。 如需每個模式的詳細資訊，請參閱 [共存模式](migration-interop-guidance-for-teams-with-skype.md)。

無論您是使用商務用 Skype 模式執行選取功能轉場，或是直接從預設孤島設定升級到 TeamsOnly 模式，TeamsUpgradePolicy 是主要工具。 與團隊中的任何其他原則一樣，您可以將 TeamsUpgradePolicy 直接指派給使用者。 您也可以將原則設定為租使用者範圍的預設值。 針對使用者的任何指派，都優先于租使用者預設設定。  您可以在 [團隊管理員] 主控台和 PowerShell 中管理原則。

您可以將 TeamsUpgradePolicy 的任何模式指派給使用者，不論該使用者是駐留在商務用 Skype Online 或內部部署中，除了只能將 **TeamsOnly 模式指派給已在商務用 Skype online 中的使用者**。 這是因為與商務用 Skype 使用者、同盟以及 Microsoft 365 電話系統功能的互通性，只有當使用者駐留在商務用 Skype Online 中時，才可以使用。

使用商務用 Skype 帳戶駐留內部部署的使用者 [必須在線上 (移](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 至商務用 skype online 或直接在商務用 skype 內部部署工具組中) 使用 move-csuser。 在1或2個步驟中，您可以將這些使用者移至 TeamsOnly：

-   1步驟：在 Move-csuser 中指定-MoveToTeams 開關。 這需要有 CU8 或更新版本的商務用 Skype Server 2019 或商務用 Skype Server 2015。

-   2個步驟：執行移動 Move-csuser 之後，使用 TeamsUpgradePolicy 將 TeamsOnly 模式授與使用者。

與其他原則不同，您無法在 Microsoft 365 或 Office 365 中建立新的 TeamsUpgradePolicy 實例。 所有現有的實例都會內嵌在服務中。   (請注意，mode 是 TeamsUpgradePolicy 內的屬性，而不是原則實例的名稱。 ) 在部分（但非全部）情況下，原則實例的名稱與模式相同。 特別是，若要將 TeamsOnly 模式指派給使用者，您會將 TeamsUpgradePolicy 的「UpgradeToTeams」實例授與該使用者。 若要查看所有實例的清單，您可以執行下列命令：

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

若要將線上使用者升級為 TeamsOnly 模式，請指派「UpgradeToTeams」實例： 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

若要將內部部署商務用 Skype 使用者升級到 TeamsOnly 模式，請在內部部署工具集中使用 Move-csuser：

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

若要變更租使用者中所有使用者的模式，除了擁有明確的每位使用者 (授與優先順序) 的人員外，請執行下列命令：

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>如果您擁有內部部署商務用 Skype 帳戶的任何使用者，則不能在租使用者層級指派 TeamsOnly 模式，除非您明確地將部分其他模式指派給使用內部部署商務用 Skype 帳戶的所有使用者。


## <a name="using-notifications-in-skype-for-business-clients"></a>在商務用 Skype 用戶端中使用通知

系統管理員可以選擇在商務用 Skype 用戶端中提供使用者通知，以通知使用者即將升級至團隊，如下圖所示。 例如，管理員將一周的時間升級為 TeamsOnly 模式，系統管理員可能會想要針對該使用者群組開啟這些通知。 使用 TeamsUpgradePolicy 與 NotifySfbUsers = true 的實例啟用這些通知。  針對除 TeamsOnly 以外的所有模式，實際會有兩個模式的實例，對應到兩個 NotifySfbUsers 值。  針對除 TeamsOnly 以外的所有模式，實際會有兩個模式的實例，對應到兩個 NotifySfbUsers 值。 

![顯示通知的圖表](media/teams-upgrade-sfb-with-notifications.png)

如果您的使用者是駐留在商務用 Skype Online，只要指派的原則實例與使用者的模式相同，但 NotifySfbUsers = true。 

如果您的使用者是駐留在內部部署的商務用 Skype 伺服器，您必須使用內部部署工具集，且需要商務用 Skype server 2019 或 CU8 （適用于商務用 skype Server 2015）。 針對駐留在內部部署的商務用 Skype 伺服器中的使用者，TeamsUpgradePolicy 來自線上實例的 mode 屬性，但 NotifySfbUsers 屬性不會生效。 如果您需要通知，您必須建立 TeamsUpgradePolicy 的內部部署實例來控制用戶端行為。 

在 [內部部署] PowerShell 視窗中，使用 NotifySfbUsers = true 建立新的 TeamsUpgradePolicy 實例：

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

接著，使用相同的內部部署 PowerShell 視窗，將該新原則指派給所需的使用者：

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>會議遷移

當使用者被遷移至 TeamsOnly 模式時，預設會將他們所組織的現有商務用 Skype 會議轉換成小組。 您也可以選擇在指派 TeamsOnly 模式給使用者時，停用預設行為。 從內部部署移動使用者時，必須將會議遷移到雲端，才能與線上使用者帳戶共同作業，但如果您沒有指定-MoveToTeams，會議將會以商務用 Skype 會議進行遷移，而不是轉換成團隊。 

在租使用者層級指派 TeamsOnly 模式時，不會觸發會議遷移給任何使用者。 如果您想要在租使用者層級指派 TeamsOnly 模式和遷移會議，您可以使用 PowerShell 來取得 (租使用者的使用者清單，例如，在) 需要的任何篩選器中使用 CsOnlineUser，然後遍歷這些使用者，以觸發會議遷移（使用啟動 CsExMeetingMigration）。 如需詳細資訊，請參閱 [使用會議遷移服務 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。



## <a name="related-links"></a>相關連結

[與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南](migration-interop-guidance-for-teams-with-skype.md) 

[在商務用 Skype Server 與 Microsoft 365 或 Office 365 之間設定混合式連接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存與升級設定](setting-your-coexistence-and-upgrade-settings.md)

[授與 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用會議遷移服務 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)


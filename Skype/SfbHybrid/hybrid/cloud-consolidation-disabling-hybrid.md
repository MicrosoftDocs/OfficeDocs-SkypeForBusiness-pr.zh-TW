---
title: 停用混合式以完成移轉至僅限 Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 本文包含停用混合成 Teams 和商務用 Skype 之雲端合併的一部分的詳細步驟。
ms.openlocfilehash: 90f3b6d5cd533ca92966a46dd271d2f82f40acc4
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510504"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a>停用混合式設定，僅完成 Teams 的遷移 

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


本文說明如何在解除您的內部部署商務用 Skype 環境之前停用混合式設定。 這是下列步驟的步驟2，以解除委任您的內部部署環境：

- 步驟 1。 [將所有必要使用者從內部部署移至線上](decommission-move-on-prem-users.md)。

- **步驟2。停用您的混合式設定。**  (本文) 

- 步驟 3. [從內部部署向線上遷移混合應用程式端點](decommission-move-on-prem-endpoints.md)。

- 步驟 4： [移除您的內部部署商務用 Skype 部署](decommission-remove-on-prem.md)。

> [!NOTE]
> 步驟2和3應該在相同維護視窗中進行，因為任何現有的混合應用程式端點在步驟2和步驟3完成之間不會發現。


## <a name="summary"></a>摘要

將所有使用者從商務用 Skype 內部部署升級至僅 Microsoft 365 中 Teams 後，您就可以解除委任內部部署商務用 Skype 部署。

在您解除委任內部部署商務用 Skype 部署和移除任何硬體之前，您必須以邏輯方式從 Microsoft 365 中停用內部部署，方法是停用混合式。 停用混合式包含下列四個步驟：

1. [更新 DNS 記錄，以指向 Microsoft 365](#update-dns-to-point-to-microsoft-365)。

2. [將您組織的共存模式變更為 [Teams]](#change-the-coexistence-mode-for-your-organization-to-teams-only)。

3. [停用 Microsoft 365 組織中的共用 sip 位址空間 (也稱為「分割網域」 ) ](#disable-shared-sip-address-space-in-microsoft-365-organization)。

4. [停用內部部署與 Microsoft 365 之間的通訊](#disable-communication-between-on-premises-and-microsoft-365)

這些步驟會以邏輯方式將您的內部部署商務用 Skype Server 從 Microsoft 365 中部署，並確保您的組織完全 Teams。 在您完成這些步驟之後，您可以使用[決定如何在解除委任後管理屬性](cloud-consolidation-managing-attributes.md)的兩個方法中所述的其中一個方法，讓您的內部部署商務用 Skype 部署退役。

> [!Important] 
> 完成此邏輯分隔之後，來自內部部署 Active Directory 的 msRTCSIP 屬性仍然具有值，而且會繼續透過 Azure AD 連線同步處理到 Azure AD。 如何解除委任內部部署環境取決於您想要將這些屬性保留在原處，還是先從您的內部部署 Active Directory 加以清除。 請注意，在您從內部部署遷移之後清除內部部署 msRTCSIP 屬性，可能會導致使用者的服務遺失！ 在 [解除委任後](cloud-consolidation-managing-attributes.md)，會說明兩個解除委任方法的詳細資料和折衷。

## <a name="update-dns-to-point-to-microsoft-365"></a>將 DNS 更新為指向 Microsoft 365

組織的外部 DNS 必須更新內部部署組織，使商務用 Skype 記錄指向 Microsoft 365 而非內部部署。 

此外，如果存在) 可刪除，則為符合或撥入 (的 CNAME 記錄。 最後，您應該移除內部網路中商務用 Skype 的任何 DNS 記錄。

如需更新 dns 記錄的詳細資訊，請參閱[更新 dns 專案，讓您的組織全部 Teams](decommission-manage-dns-entries.md)。

## <a name="change-the-coexistence-mode-for-your-organization-to-teams-only"></a>將貴組織的共存模式變更為僅 Teams

此步驟可確保您組織中的任何新使用者永遠都建立為僅 Teams 使用者。 

嘗試將租使用者模式變更為 Teams，只會自動檢查是否存在步驟1中已錯過的任何內部部署 DNS 記錄，並在輸出中識別這些記錄。 只有在更新組織的所有 DNS 記錄後，才能將租使用者模式變更為 Teams 才會失敗。 

若要將租使用者模式變更為 Teams 只從 Teams PowerShell] 視窗執行下列命令。

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
```

或者，您也可以使用 Teams 系統管理中心，將租使用者共存模式變更為 TeamsOnly，在 [整個組織設定] 下，> "Teams Upgrade]。    

## <a name="disable-shared-sip-address-space-in-microsoft-365-organization"></a>停用 Microsoft 365 組織中的共用 sip 位址空間
    
若要停用共用 sip 位址空間，請從 Teams PowerShell] 視窗中執行下列命令。

```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
```
 
## <a name="disable-communication-between-on-premises-and-microsoft-365"></a>停用內部部署與 Microsoft 365 之間的通訊

若要停用內部部署環境與 Microsoft 365 之間的通訊，請從內部部署 PowerShell 視窗執行下列命令：

```PowerShell
Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```


## <a name="see-also"></a>另請參閱

- [Teams 與商務用 Skype 的雲整合](cloud-consolidation.md)

- [解除您的內部部署商務用 Skype 環境](decommission-on-prem-overview.md)


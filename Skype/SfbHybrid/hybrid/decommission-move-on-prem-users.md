---
title: 將使用者移至雲端
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 在解除委任商務用 Skype 內部部署環境之前，請先移動使用者。
ms.openlocfilehash: 44092460fa1db0664fe95b12cc99f3488544dc0ad049d75d56074e6bf0873c60
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54292361"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a>在解除委任內部部署環境之前，移動必要使用者

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本文說明如何在解除您的內部部署商務用 Skype 環境之前，將所需使用者移至 Microsoft 雲端。 這是解除委任內部部署環境之下列步驟的步驟1：

- **步驟1。將所有必要使用者從內部部署移至線上。**  (本文) 

- 步驟 2. [停用您的混合](cloud-consolidation-disabling-hybrid.md)式設定。

- 步驟 3. [從內部部署向線上遷移混合應用程式端點](decommission-move-on-prem-endpoints.md)。 請注意，在執行上述步驟2之前，任何現有的混合應用程式端點都不會發現，直到您完成此步驟為止。 您應該規劃在相同維護視窗中執行步驟2和3。

- 步驟 4. [移除您的內部部署商務用 Skype 部署](decommission-remove-on-prem.md)。


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>將所有必要使用者從內部部署移至雲端

完成遷移之後，您將繼續使用的任何使用者，必須先從內部部署移至雲端。 您可以使用內部部署系統管理工具移動使用者。 如需詳細資訊，請參閱 [在內部部署與雲端之間移動使用者](move-users-between-on-premises-and-cloud.md)。

雖然具有內部部署商務用 Skype Server 帳戶的使用者可以使用 Teams，但這些使用者沒有 Teams 的完整功能。 這些使用者無法使用商務用 Skype (線上或內部部署) 的任何其他使用者進行交互操作或聯盟。 這些使用者也不能在其 Teams 用戶端接收 PSTN 通話。 因此，您必須將這些使用者移至線上。 此步驟也可確保將商務用 Skype Server 中所建立的任何連絡人或會議遷移至 Teams。

若要檢查內部部署中是否還有其他使用者，請在商務用 Skype Server PowerShell] 視窗中執行下列指令程式。

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

若傳回任何使用者，請複查輸出以判斷是否必須將任何帳戶移至雲端，並針對任何這類使用者執行[下列步驟。](move-users-between-on-premises-and-cloud.md) 如需不再需要的使用者帳戶，請執行下列商務用 Skype Server PowerShell Cmdlet：

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> 執行 Disable-CsUser 會移除所有滿足篩選準則之使用者的所有商務用 Skype 屬性。 繼續之前，請先確認這些帳戶已不再需要繼續進行。


您現在已準備好 [停用混合](cloud-consolidation-disabling-hybrid.md)式設定。

## <a name="see-also"></a>另請參閱

- [解除您的內部部署商務用 Skype 環境](decommission-on-prem-overview.md)

- [停用混合式設定](cloud-consolidation-disabling-hybrid.md)

- [將混合應用程式端點從內部部署移至線上](decommission-move-on-prem-endpoints.md)

- [移除您的內部部署商務用 Skype 部署](decommission-remove-on-prem.md)





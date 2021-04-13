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
description: 在解除委任商務用 Skype 內部部署環境之前，移動使用者。
ms.openlocfilehash: f04ebeec51b739faa89f907de6c363f0ef70a78e
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656669"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a>在解除委任內部部署環境之前，移動必要使用者

本文說明如何在解除委任您的內部部署商務用 Skype 環境之前，將所需使用者移至 Microsoft 雲端。 這是解除委任內部部署環境之下列步驟的步驟1：

- **步驟1。將所有必要使用者從內部部署移至線上。**  (本文) 

- 步驟 2. [停用您的混合](cloud-consolidation-disabling-hybrid.md)式設定。

- 步驟 3. [將混合應用程式端點從內部部署移至線上](decommission-move-on-prem-endpoints.md)。

- 步驟 4. [移除您的內部部署商務用 Skype 部署](decommission-remove-on-prem.md)。


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>將所有必要使用者從內部部署移至雲端

完成遷移之後，您將繼續使用的任何使用者，必須先從內部部署移至雲端。 您可以使用內部部署系統管理工具移動使用者。 如需詳細資訊，請參閱 [在內部部署與雲端之間移動使用者](move-users-between-on-premises-and-cloud.md)。

雖然具有內部部署商務用 Skype 伺服器帳戶的使用者可以使用小組，但這些使用者卻沒有小組的完整功能。 無論是線上或內部部署) ，這些使用者都無法與其他任何使用商務用 Skype 的使用者進行交互操作或同盟 (。 這些使用者也不能在其團隊用戶端接收 PSTN 通話。 因此，您必須將這些使用者移至線上。 此步驟也可確保在商務用 Skype Server 中建立的任何連絡人或會議都會遷移至小組。

若要檢查內部部署中是否還有任何其他使用者，請在 [商務用 Skype Server PowerShell] 視窗中執行下列 Cmdlet。

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

若傳回任何使用者，請複查輸出以判斷是否必須將任何帳戶移至雲端，並針對任何這類使用者執行[下列步驟。](move-users-between-on-premises-and-cloud.md) 針對不再需要的使用者帳戶，請執行下列商務用 Skype Server PowerShell Cmdlet：

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> 執行 Disable-CsUser 會移除所有符合篩選準則之使用者的所有商務用 Skype 屬性。 繼續之前，請先確認這些帳戶已不再需要繼續進行。


您現在已準備好 [停用混合](cloud-consolidation-disabling-hybrid.md)式設定。

## <a name="see-also"></a>另請參閱

- [解除您的內部部署商務用 Skype 環境](decommission-on-prem-overview.md)

- [停用混合式設定](cloud-consolidation-disabling-hybrid.md)

- [將混合應用程式端點從內部部署移至線上](decommission-move-on-prem-endpoints.md)

- [移除您的內部部署商務用 Skype 部署](decommission-remove-on-prem.md)





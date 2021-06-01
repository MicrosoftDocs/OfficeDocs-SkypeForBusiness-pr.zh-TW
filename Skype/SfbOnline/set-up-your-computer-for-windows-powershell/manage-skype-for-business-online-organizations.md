---
title: 管理商務用 Skype線上組織
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 使用 Windows PowerShell 和 Get-CsTenant Get-CsTenantLicensingConfiguration Cmdlet 來取得您的線上租使用者商務用 Skype相關資訊。
ms.openlocfilehash: 2fa95bf8997dd0aff7271b1383c69d9b27c4f4a9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238783"
---
# <a name="manage-skype-for-business-online-organizations"></a>管理商務用 Skype線上組織

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
> [!NOTE]
> 最新版[powerShell Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)預覽版已與 商務用 Skype Online Connector 整合，提供單一模組Teams PowerShell 管理。

您可以使用 **Get-CsTenant** 商務用 Skype **Get-CsTenantLicensingConfiguration** Cmdlet 來尋找您的線上租使用者相關資訊。
  
## <a name="manage-skype-for-business-online-tenants"></a>管理 商務用 Skype Online 租使用者

若要返回您的線上租使用者商務用 Skype相關資訊，請撥打[Get-CsTenant](/powershell/module/skype/Get-CsTenant) Cmdlet，而不需要任何其他參數。
  
```PowerShell
Get-CsTenant
```

若要只返回租使用者名稱和識別碼，請使用此命令。
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

執行  _Cmdlet_ 時，需要 TenantID 參數的值，例如 [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) 和 [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration)。
  
若要在 商務用 Skype Online 系統管理中心尋找指定租使用者的授權資訊，請使用[Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) Cmdlet。
  
## <a name="related-topics"></a>相關主題
[使用電腦設定商務用 skype 線上管理Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  

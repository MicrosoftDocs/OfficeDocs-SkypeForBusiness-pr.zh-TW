---
title: 管理商務用 Skype Online 組織
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
description: 使用 Windows PowerShell 和 Get-CsTenant Get-CsTenantLicensingConfiguration Cmdlet 取得商務用 Skype Online 租使用者相關資訊。
ms.openlocfilehash: ed15d062bf4f2e5f2ad0f47169ac0626d2c59d20
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113179"
---
# <a name="manage-skype-for-business-online-organizations"></a>管理商務用 Skype Online 組織
> [!NOTE]
> 最新的 [Teams PowerShell 公開預覽](https://www.powershellgallery.com/packages/MicrosoftTeams/) 版已與商務用 Skype Online Connector 整合，為 Teams PowerShell 管理提供單一模組。

您可以使用 **Get-CsTenant 和** **Get-CsTenantLicensingConfiguration** Cmdlet 來尋找商務用 Skype Online 租使用者相關資訊。
  
## <a name="manage-skype-for-business-online-tenants"></a>管理商務用 Skype Online 租使用者

若要返回商務用 Skype Online 租使用者相關資訊，請撥打 [Get-CsTenant](/powershell/module/skype/Get-CsTenant) Cmdlet，而不提供任何其他參數。
  
```PowerShell
Get-CsTenant
```

若要只返回租使用者名稱和識別碼，請使用此命令。
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

執行  _Cmdlet_ 時，需要 TenantID 參數的值，例如 [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) 和 [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration)。
  
若要尋找指定租使用者的授權資訊是否可在商務用 Skype Online 系統管理中心取得，請使用 [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) Cmdlet。
  
## <a name="related-topics"></a>相關主題
[使用 Windows PowerShell 設定商務用 Skype 線上管理的電腦](set-up-your-computer-for-windows-powershell.md)

  

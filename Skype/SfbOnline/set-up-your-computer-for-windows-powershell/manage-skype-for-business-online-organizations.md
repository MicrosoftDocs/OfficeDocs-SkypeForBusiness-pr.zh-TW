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
description: 使用 Windows PowerShell 以及 CsTenant 和 CsTenantLicensingConfiguration Cmdlet 來取得商務用 Skype Online 租使用者的相關資訊。
ms.openlocfilehash: 06597447edaf095be3df26b58e6210bb919ee0bd
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085689"
---
# <a name="manage-skype-for-business-online-organizations"></a>管理商務用 Skype Online 組織
> [!NOTE]
> 最新的[團隊 powershell 公開預覽版](https://www.powershellgallery.com/packages/MicrosoftTeams/)已與商務用 Skype Online 連接器整合，提供單一模組供團隊 PowerShell 管理使用。

您可以使用**CsTenant**和**CsTenantLicensingConfiguration** Cmdlet，找到有關商務用 Skype Online 租使用者的資訊。
  
## <a name="manage-skype-for-business-online-tenants"></a>管理商務用 Skype Online 租使用者

若要傳回商務用 Skype Online 租使用者的相關資訊，請呼叫[CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) Cmdlet （不含任何其他參數）。
  
```PowerShell
Get-CsTenant
```

若要只返回租使用者名稱和識別碼，請使用此命令。
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

在執行[CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602)和[set CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080.aspx)等 Cmdlet 時，需要_TenantID_參數的值。
  
若要在商務用 Skype Online 系統管理中心尋找指定租使用者的授權資訊的相關資訊，請使用[CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) Cmdlet。
  
## <a name="related-topics"></a>相關主題
[使用 Windows PowerShell 設定商務用 skype online 管理電腦](set-up-your-computer-for-windows-powershell.md)

  
 

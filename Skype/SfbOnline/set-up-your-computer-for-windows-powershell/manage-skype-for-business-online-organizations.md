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
ms.openlocfilehash: e4765fbbe8c705300bb93c09651034e080a8132e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010616"
---
# <a name="manage-skype-for-business-online-organizations"></a>管理商務用 Skype Online 組織

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

  
 

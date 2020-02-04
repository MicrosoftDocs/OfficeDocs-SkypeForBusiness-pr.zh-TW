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
ms.openlocfilehash: 3c4a8f72caca634b208de5cf4aa555b88518f4da
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706248"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="a704f-103">管理商務用 Skype Online 組織</span><span class="sxs-lookup"><span data-stu-id="a704f-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="a704f-104">您可以使用**CsTenant**和**CsTenantLicensingConfiguration** Cmdlet，找到有關商務用 Skype Online 租使用者的資訊。</span><span class="sxs-lookup"><span data-stu-id="a704f-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="a704f-105">管理商務用 Skype Online 租使用者</span><span class="sxs-lookup"><span data-stu-id="a704f-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="a704f-106">若要傳回商務用 Skype Online 租使用者的相關資訊，請呼叫[CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) Cmdlet （不含任何其他參數）。</span><span class="sxs-lookup"><span data-stu-id="a704f-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="a704f-107">若要只返回租使用者名稱和識別碼，請使用此命令。</span><span class="sxs-lookup"><span data-stu-id="a704f-107">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="a704f-108">在執行[CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602)和[set CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx)等 Cmdlet 時，需要_TenantID_參數的值。</span><span class="sxs-lookup"><span data-stu-id="a704f-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="a704f-109">若要在商務用 Skype Online 系統管理中心尋找指定租使用者的授權資訊的相關資訊，請使用[CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a704f-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a704f-110">相關主題</span><span class="sxs-lookup"><span data-stu-id="a704f-110">Related topics</span></span>
[<span data-ttu-id="a704f-111">使用 Windows PowerShell 設定商務用 skype online 管理電腦</span><span class="sxs-lookup"><span data-stu-id="a704f-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 

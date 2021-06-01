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
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="281d1-103">管理商務用 Skype線上組織</span><span class="sxs-lookup"><span data-stu-id="281d1-103">Manage Skype for Business Online organizations</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
> [!NOTE]
> <span data-ttu-id="281d1-104">最新版[powerShell Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)預覽版已與 商務用 Skype Online Connector 整合，提供單一模組Teams PowerShell 管理。</span><span class="sxs-lookup"><span data-stu-id="281d1-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="281d1-105">您可以使用 **Get-CsTenant** 商務用 Skype **Get-CsTenantLicensingConfiguration** Cmdlet 來尋找您的線上租使用者相關資訊。</span><span class="sxs-lookup"><span data-stu-id="281d1-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="281d1-106">管理 商務用 Skype Online 租使用者</span><span class="sxs-lookup"><span data-stu-id="281d1-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="281d1-107">若要返回您的線上租使用者商務用 Skype相關資訊，請撥打[Get-CsTenant](/powershell/module/skype/Get-CsTenant) Cmdlet，而不需要任何其他參數。</span><span class="sxs-lookup"><span data-stu-id="281d1-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="281d1-108">若要只返回租使用者名稱和識別碼，請使用此命令。</span><span class="sxs-lookup"><span data-stu-id="281d1-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="281d1-109">執行  _Cmdlet_ 時，需要 TenantID 參數的值，例如 [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) 和 [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="281d1-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) and [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration).</span></span>
  
<span data-ttu-id="281d1-110">若要在 商務用 Skype Online 系統管理中心尋找指定租使用者的授權資訊，請使用[Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="281d1-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="281d1-111">相關主題</span><span class="sxs-lookup"><span data-stu-id="281d1-111">Related topics</span></span>
[<span data-ttu-id="281d1-112">使用電腦設定商務用 skype 線上管理Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="281d1-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  

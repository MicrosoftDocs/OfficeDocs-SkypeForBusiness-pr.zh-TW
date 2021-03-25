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
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="99cef-103">管理商務用 Skype Online 組織</span><span class="sxs-lookup"><span data-stu-id="99cef-103">Manage Skype for Business Online organizations</span></span>
> [!NOTE]
> <span data-ttu-id="99cef-104">最新的 [Teams PowerShell 公開預覽](https://www.powershellgallery.com/packages/MicrosoftTeams/) 版已與商務用 Skype Online Connector 整合，為 Teams PowerShell 管理提供單一模組。</span><span class="sxs-lookup"><span data-stu-id="99cef-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="99cef-105">您可以使用 **Get-CsTenant 和** **Get-CsTenantLicensingConfiguration** Cmdlet 來尋找商務用 Skype Online 租使用者相關資訊。</span><span class="sxs-lookup"><span data-stu-id="99cef-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="99cef-106">管理商務用 Skype Online 租使用者</span><span class="sxs-lookup"><span data-stu-id="99cef-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="99cef-107">若要返回商務用 Skype Online 租使用者相關資訊，請撥打 [Get-CsTenant](/powershell/module/skype/Get-CsTenant) Cmdlet，而不提供任何其他參數。</span><span class="sxs-lookup"><span data-stu-id="99cef-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="99cef-108">若要只返回租使用者名稱和識別碼，請使用此命令。</span><span class="sxs-lookup"><span data-stu-id="99cef-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="99cef-109">執行  _Cmdlet_ 時，需要 TenantID 參數的值，例如 [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) 和 [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="99cef-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) and [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration).</span></span>
  
<span data-ttu-id="99cef-110">若要尋找指定租使用者的授權資訊是否可在商務用 Skype Online 系統管理中心取得，請使用 [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="99cef-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="99cef-111">相關主題</span><span class="sxs-lookup"><span data-stu-id="99cef-111">Related topics</span></span>
[<span data-ttu-id="99cef-112">使用 Windows PowerShell 設定商務用 Skype 線上管理的電腦</span><span class="sxs-lookup"><span data-stu-id="99cef-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  

---
title: 從商務用 Skype Online 連接器移至 Teams PowerShell 模組
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 瞭解如何從商務用 Skype Online Connector 移至 Teams PowerShell 模組來管理 Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5a2b502edc84c853a0a140a11f8c028b7c78aca6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094124"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="475b2-103">從商務用 Skype Online 連接器移至 Teams PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="475b2-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="475b2-104">若要從使用商務用 Skype Online Connector 移至 Teams PowerShell 模組來管理 Teams，您必須更新現有的 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="475b2-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="475b2-105">本文將說明如何執行此工作。</span><span class="sxs-lookup"><span data-stu-id="475b2-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="475b2-106">安裝最新的 Teams PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="475b2-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="475b2-107">有關步驟，請參閱 [安裝 Microsoft Teams Powershell](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="475b2-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="475b2-108">卸載商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="475b2-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="475b2-109">若要這麼做，請在控制台中，前往程式和功能，選取商務用 **Skype Online、Windows PowerShell 模組**，然後 **選取卸載**。</span><span class="sxs-lookup"><span data-stu-id="475b2-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="475b2-110">在 PowerShell 腳本中，將參照的模組名稱變更為 ```Import-Module``` 或 ```SkypeOnlineConnector``` ```LyncOnlineConnector``` ```MicrosoftTeams``` 。</span><span class="sxs-lookup"><span data-stu-id="475b2-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="475b2-111">例如，變更 ```Import-Module -Name SkypeOnlineConnector``` 為 ```Import-Module -Name MicrosoftTeams``` 。</span><span class="sxs-lookup"><span data-stu-id="475b2-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>
4. <span data-ttu-id="475b2-112">使用 Teams PowerShell 模組 2.0 或更高版本時，請將 New-csOnlineSession 變更為 Connect-MicrosoftTeams。</span><span class="sxs-lookup"><span data-stu-id="475b2-112">When using Teams PowerShell Module 2.0 or later, change New-csOnlineSession to Connect-MicrosoftTeams.</span></span> 

```powershell
  # When using Teams PowerShell Module 1.1.6
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfbSession
   
   # When using Teams PowerShell Module 2.0 or later
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="related-topics"></a><span data-ttu-id="475b2-113">相關主題</span><span class="sxs-lookup"><span data-stu-id="475b2-113">Related topics</span></span>

[<span data-ttu-id="475b2-114">安裝 Microsoft Teams Powershell</span><span class="sxs-lookup"><span data-stu-id="475b2-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="475b2-115">使用 Teams PowerShell 管理 Teams</span><span class="sxs-lookup"><span data-stu-id="475b2-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="475b2-116">Teams PowerShell 版本資訊</span><span class="sxs-lookup"><span data-stu-id="475b2-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="475b2-117">Microsoft Teams Cmdlet 參照</span><span class="sxs-lookup"><span data-stu-id="475b2-117">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="475b2-118">商務用 Skype Cmdlet 參照</span><span class="sxs-lookup"><span data-stu-id="475b2-118">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
---
title: 從商務用 Skype Online 連接器移至團隊 PowerShell 模組
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 瞭解如何從商務用 Skype Online 連接器移至團隊 PowerShell 模組以管理團隊。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469662"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="e5128-103">從商務用 Skype Online 連接器移至團隊 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="e5128-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="e5128-104">若要從使用商務用 Skype Online 連接器移至團隊 PowerShell 模組以管理團隊，您必須更新現有的 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="e5128-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="e5128-105">本文說明如何執行此動作。</span><span class="sxs-lookup"><span data-stu-id="e5128-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="e5128-106">安裝最新的團隊 PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="e5128-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="e5128-107">如需步驟，請參閱 [安裝 Microsoft 團隊 Powershell](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="e5128-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="e5128-108">卸載商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="e5128-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="e5128-109">若要這樣做，請在 [控制台] 中，移至 [ **程式和功能**]，選取 [ **商務用 Skype Online]、[Windows PowerShell 模組**]，然後選取 [ **卸載**]。</span><span class="sxs-lookup"><span data-stu-id="e5128-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="e5128-110">在您的 PowerShell 腳本中，變更 [ ```Import-Module``` 寄件者] 或 [至] 中所參照的模組名稱 ```SkypeOnlineConnector``` ```LyncOnlineConnector``` ```MicrosoftTeams``` 。</span><span class="sxs-lookup"><span data-stu-id="e5128-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="e5128-111">例如，[變更 ```Import-Module -Name SkypeOnlineConnector``` 為] ```Import-Module -Name MicrosoftTeams``` 。</span><span class="sxs-lookup"><span data-stu-id="e5128-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>

> [!NOTE]
> <span data-ttu-id="e5128-112">系統管理員應該在使用商務用 Skype Online Cmdlet 之前，繼續使用 [新的 CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) ，並匯入會話。</span><span class="sxs-lookup"><span data-stu-id="e5128-112">Admins should continue to use [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) and import the session before using Skype for Business Online cmdlets.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="e5128-113">相關主題</span><span class="sxs-lookup"><span data-stu-id="e5128-113">Related topics</span></span>

[<span data-ttu-id="e5128-114">安裝 Microsoft 團隊 Powershell</span><span class="sxs-lookup"><span data-stu-id="e5128-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="e5128-115">使用團隊 PowerShell 管理團隊</span><span class="sxs-lookup"><span data-stu-id="e5128-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="e5128-116">團隊 PowerShell 版本資訊</span><span class="sxs-lookup"><span data-stu-id="e5128-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="e5128-117">Microsoft 團隊 Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="e5128-117">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="e5128-118">商務用 Skype Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="e5128-118">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

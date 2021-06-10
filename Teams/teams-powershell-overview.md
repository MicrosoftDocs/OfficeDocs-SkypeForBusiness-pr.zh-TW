---
title: Microsoft TeamsPowerShell 概觀
ms.reviewer: ''
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 瞭解如何使用 PowerShell 控制項來管理Microsoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 448658fb844052815e14b85e0c70a33cb737b72d
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768352"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="32ce7-103">Microsoft TeamsPowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="32ce7-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="32ce7-104">Microsoft TeamsPowerShell 是一組 Cmdlet，Teams直接從 PowerShell 命令列管理資料。</span><span class="sxs-lookup"><span data-stu-id="32ce7-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="32ce7-105">PowerShell 以 .NET Standard 撰寫Teams PowerShell 5.1 適用于 Windows、PowerShell 6.x 及更高版本的所有平臺，包括 Azure Cloud Shell。</span><span class="sxs-lookup"><span data-stu-id="32ce7-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="32ce7-106">開始使用 PowerShell 之前，您必須 [安裝它](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="32ce7-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="32ce7-107">PowerShell 7 和 PowerShell Teams已知問題。</span><span class="sxs-lookup"><span data-stu-id="32ce7-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="32ce7-108">我們建議您使用 PowerShell 5.1，直到問題解決為止。</span><span class="sxs-lookup"><span data-stu-id="32ce7-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="32ce7-109">釋放</span><span class="sxs-lookup"><span data-stu-id="32ce7-109">Releases</span></span>


<span data-ttu-id="32ce7-110">TeamsPowerShell 可在[PowerShell 圖庫中提供](https://www.powershellgallery.com/packages/MicrosoftTeams)兩種發行類型。</span><span class="sxs-lookup"><span data-stu-id="32ce7-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="32ce7-111">**一般 (GA)**： 生產就緒的 Cmdlet，每月更新一次。</span><span class="sxs-lookup"><span data-stu-id="32ce7-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="32ce7-112">**公用預覽**：提早存取功能。</span><span class="sxs-lookup"><span data-stu-id="32ce7-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="32ce7-113">更新頻率可能會高於 GA。</span><span class="sxs-lookup"><span data-stu-id="32ce7-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="32ce7-114">有關兩個發行版本功能新增[及改良功能的詳細資訊](teams-powershell-release-notes.md)，請參閱 powerShell Teams說明。</span><span class="sxs-lookup"><span data-stu-id="32ce7-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="32ce7-115">使用 powerShell Teams管理</span><span class="sxs-lookup"><span data-stu-id="32ce7-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="32ce7-116">您將使用 PowerShell 模組Teams完全管理Teams：</span><span class="sxs-lookup"><span data-stu-id="32ce7-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="32ce7-117">[Microsoft Teams PowerShell 模組：PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)模組Teams包含用於管理團隊、聊天和頻道的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="32ce7-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="32ce7-118">PowerShell [Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)版本 2.0 或更新版本包含所有 商務用 Skype Online Connector Cmdlet，提供單一模組Teams PowerShell 管理。</span><span class="sxs-lookup"><span data-stu-id="32ce7-118">The [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) version 2.0 or higher includes all  Skype for Business Online Connector cmdlets, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="32ce7-119">[商務用 Skype PowerShell 連接器](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)：商務用 Skype PowerShell 連接器現在是 PowerShell 模組Teams的一部分。</span><span class="sxs-lookup"><span data-stu-id="32ce7-119">[Skype for Business PowerShell Connector](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="32ce7-120">如需使用這些模組管理Teams的完整指南，請參閱使用[PowerShell](teams-powershell-managing-teams.md)Teams管理Teams程式。</span><span class="sxs-lookup"><span data-stu-id="32ce7-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="32ce7-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="32ce7-121">Related topics</span></span>

[<span data-ttu-id="32ce7-122">安裝 powerShell Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="32ce7-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="32ce7-123">使用 powerShell Teams管理Teams</span><span class="sxs-lookup"><span data-stu-id="32ce7-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="32ce7-124">TeamsPowerShell 版本資訊</span><span class="sxs-lookup"><span data-stu-id="32ce7-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="32ce7-125">Microsoft Teams Cmdlet 參照</span><span class="sxs-lookup"><span data-stu-id="32ce7-125">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="32ce7-126">商務用 Skype Cmdlet 參照</span><span class="sxs-lookup"><span data-stu-id="32ce7-126">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="32ce7-127">使用Microsoft Teams系統管理員角色來管理Teams</span><span class="sxs-lookup"><span data-stu-id="32ce7-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)

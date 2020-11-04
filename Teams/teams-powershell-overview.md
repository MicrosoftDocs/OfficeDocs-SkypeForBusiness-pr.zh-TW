---
title: Microsoft 團隊 PowerShell 概覽
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
description: 瞭解如何使用 PowerShell 控制項來管理 Microsoft 團隊。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 12360110df90fb5de2e3e4547534c8569cc5537a
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852154"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="87011-103">Microsoft 團隊 PowerShell 概覽</span><span class="sxs-lookup"><span data-stu-id="87011-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="87011-104">Microsoft 團隊 PowerShell 是一組用來從 PowerShell 命令列直接管理團隊的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="87011-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="87011-105">在 .NET 標準版中，小組 PowerShell 在 Windows 上的 PowerShell 5.1 上運作，而在所有平臺上（包括 Azure 雲端 Shell）都可以使用。</span><span class="sxs-lookup"><span data-stu-id="87011-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="87011-106">您必須先 [安裝它](teams-powershell-install.md)，才能開始使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="87011-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="87011-107">PowerShell 7 和團隊 PowerShell 存在已知問題。</span><span class="sxs-lookup"><span data-stu-id="87011-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="87011-108">我們建議您使用 PowerShell 5.1，直到問題解決為止。</span><span class="sxs-lookup"><span data-stu-id="87011-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="87011-109">鬆開</span><span class="sxs-lookup"><span data-stu-id="87011-109">Releases</span></span>


<span data-ttu-id="87011-110">您可以在兩種版本類型中的 [PowerShell 庫](https://www.powershellgallery.com/packages/MicrosoftTeams) 上使用團隊 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="87011-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="87011-111">**正式供貨 (GA)** ：生產已就緒的 Cmdlet，每月更新。</span><span class="sxs-lookup"><span data-stu-id="87011-111">**General Availability (GA)** : Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="87011-112">**公用預覽** ：提前存取功能。</span><span class="sxs-lookup"><span data-stu-id="87011-112">**Public Preview** : Early access to features.</span></span> <span data-ttu-id="87011-113">更新頻率可能比 GA 更新。</span><span class="sxs-lookup"><span data-stu-id="87011-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="87011-114">如需這兩個版本之功能新增和改良的詳細資訊，請閱讀 [團隊 PowerShell 版本](teams-powershell-release-notes.md)資訊。</span><span class="sxs-lookup"><span data-stu-id="87011-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="87011-115">使用 PowerShell 管理團隊</span><span class="sxs-lookup"><span data-stu-id="87011-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="87011-116">您將使用團隊 PowerShell 模組來全面管理團隊：</span><span class="sxs-lookup"><span data-stu-id="87011-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="87011-117">[Microsoft 團隊 powershell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams/)：團隊 powershell 模組包含管理團隊、聊天和頻道的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="87011-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="87011-118">最新的 [團隊 powershell 公開發行](https://www.powershellgallery.com/packages/MicrosoftTeams/) 與商務用 Skype Online 連接器整合，提供單一模組供團隊 PowerShell 管理使用。</span><span class="sxs-lookup"><span data-stu-id="87011-118">The latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="87011-119">[商務用 Skype Powershell 連接器](https://www.microsoft.com/download/details.aspx?id=39366)：商務用 skype powershell 連接器現已成為團隊 PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="87011-119">[Skype for Business PowerShell Connector](https://www.microsoft.com/download/details.aspx?id=39366): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="87011-120">如需使用這些模組管理團隊的完整指南，請參閱使用 [團隊 PowerShell 管理團隊](teams-powershell-managing-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="87011-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="87011-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="87011-121">Related topics</span></span>

[<span data-ttu-id="87011-122">安裝團隊 PowerShell</span><span class="sxs-lookup"><span data-stu-id="87011-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="87011-123">使用團隊 PowerShell 管理團隊</span><span class="sxs-lookup"><span data-stu-id="87011-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="87011-124">團隊 PowerShell 版本資訊</span><span class="sxs-lookup"><span data-stu-id="87011-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="87011-125">Microsoft 團隊 Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="87011-125">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="87011-126">商務用 Skype Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="87011-126">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="87011-127">使用 Microsoft 團隊管理員角色管理團隊</span><span class="sxs-lookup"><span data-stu-id="87011-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)

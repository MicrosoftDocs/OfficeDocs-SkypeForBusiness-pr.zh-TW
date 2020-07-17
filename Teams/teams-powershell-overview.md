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
ms.openlocfilehash: 5385430c7db8aab0adf1efbaec546134e9adf388
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943986"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="b03b4-103">Microsoft 團隊 PowerShell 概覽</span><span class="sxs-lookup"><span data-stu-id="b03b4-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="b03b4-104">Microsoft 團隊 PowerShell 是一組用來從 PowerShell 命令列直接管理團隊的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b03b4-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="b03b4-105">在 .NET 標準版中，小組 PowerShell 在 Windows 上的 PowerShell 5.1 上運作，在所有平臺上（包括 Azure Shell）都可以使用。</span><span class="sxs-lookup"><span data-stu-id="b03b4-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows,PowerShell 6.x and higher on all platforms including Azure Shell.</span></span>

<span data-ttu-id="b03b4-106">您必須先[安裝它](teams-powershell-install.md)，才能開始使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b03b4-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="b03b4-107">PowerShell 7 和團隊 PowerShell 存在已知問題。</span><span class="sxs-lookup"><span data-stu-id="b03b4-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="b03b4-108">我們建議您使用 PowerShell 5.1，直到問題解決為止。</span><span class="sxs-lookup"><span data-stu-id="b03b4-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="b03b4-109">鬆開</span><span class="sxs-lookup"><span data-stu-id="b03b4-109">Releases</span></span>


<span data-ttu-id="b03b4-110">您可以在兩種版本類型中的[PowerShell 庫](https://www.powershellgallery.com/packages/MicrosoftTeams)上使用團隊 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b03b4-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="b03b4-111">**正式供貨（GA）**：已完成生產的 Cmdlet （每月更新）。</span><span class="sxs-lookup"><span data-stu-id="b03b4-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="b03b4-112">**公用預覽**：提前存取功能。</span><span class="sxs-lookup"><span data-stu-id="b03b4-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="b03b4-113">更新頻率可能比 GA 更新。</span><span class="sxs-lookup"><span data-stu-id="b03b4-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="b03b4-114">如需這兩個版本之功能新增和改良的詳細資訊，請閱讀[團隊 PowerShell 版本](teams-powershell-release-notes.md)資訊。</span><span class="sxs-lookup"><span data-stu-id="b03b4-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="b03b4-115">使用 PowerShell 管理團隊</span><span class="sxs-lookup"><span data-stu-id="b03b4-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="b03b4-116">您會使用這兩個 PowerShell 模組來完全管理團隊：</span><span class="sxs-lookup"><span data-stu-id="b03b4-116">You'll use both of these PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="b03b4-117">[Microsoft 團隊 powershell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams/)：團隊 powershell 模組包含管理團隊、聊天和頻道的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b03b4-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

- <span data-ttu-id="b03b4-118">[商務用 Skype powershell 模組](https://www.microsoft.com/download/details.aspx?id=39366)：商務用 skype powershell 模組包含管理會議、電話系統及原則功能的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b03b4-118">[Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366): The Skype for Business PowerShell module contains the cmdlets to manage meetings, phone system, and policies features.</span></span>

<span data-ttu-id="b03b4-119">如需使用這些模組管理團隊的完整指南，請參閱使用[團隊 PowerShell 管理團隊](teams-powershell-managing-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="b03b4-119">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b03b4-120">最新的[團隊 powershell 公開預覽版](https://www.powershellgallery.com/packages/MicrosoftTeams/)已與商務用 Skype Online 連接器整合，提供單一模組供團隊 PowerShell 管理使用。</span><span class="sxs-lookup"><span data-stu-id="b03b4-120">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b03b4-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="b03b4-121">Related topics</span></span>

[<span data-ttu-id="b03b4-122">安裝團隊 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b03b4-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="b03b4-123">使用團隊 PowerShell 管理團隊</span><span class="sxs-lookup"><span data-stu-id="b03b4-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="b03b4-124">團隊 PowerShell 版本資訊</span><span class="sxs-lookup"><span data-stu-id="b03b4-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="b03b4-125">Microsoft 團隊 Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="b03b4-125">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="b03b4-126">商務用 Skype Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="b03b4-126">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="b03b4-127">使用 Microsoft 團隊管理員角色管理團隊</span><span class="sxs-lookup"><span data-stu-id="b03b4-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)

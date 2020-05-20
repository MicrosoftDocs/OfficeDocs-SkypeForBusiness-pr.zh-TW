---
title: 安裝團隊 PowerShell 模組的預發行版本本
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: brandber
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 請依照下列步驟，從 PowerShell 測試圖庫安裝團隊 PowerShell 模組的預發行版本本。
ms.openlocfilehash: 1d85fac2ee6a1c8565f8482f7208a2f5ae33db60
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321766"
---
# <a name="install-the-pre-release-version-of-the-teams-powershell-module"></a><span data-ttu-id="ed1b3-103">安裝團隊 PowerShell 模組的預發行版本本</span><span class="sxs-lookup"><span data-stu-id="ed1b3-103">Install the pre-release version of the Teams PowerShell module</span></span>

<span data-ttu-id="ed1b3-104">本文說明如何從[PowerShell 測試圖庫](https://www.poshtestgallery.com/packages/MicrosoftTeams/)安裝團隊 PowerShell 模組最新的預發行版本本。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-104">This article describes how to install the latest pre-release version of the Teams PowerShell module from the [PowerShell Test Gallery](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="ed1b3-105">您需要在案例中使用團隊 PowerShell 模組的預發行版本本，在此案例中，系統不支援管理團隊功能的 Cmdlet，且僅適用于預發行版本本。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-105">You'll need the pre-release version of the Teams PowerShell module in scenarios where cmdlets for managing a Teams feature aren't supported in the Generally Available version of the module and are only available in the pre-release version.</span></span>

<span data-ttu-id="ed1b3-106">使用這些步驟從 PowerShell 測試圖庫安裝團隊 PowerShell 模組的最新預發行版本本。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-106">Use these steps to install the latest pre-release version of the Teams PowerShell module from the PowerShell Test Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="ed1b3-107">請勿從 PowerShell 測試圖庫並排安裝團隊 PowerShell 模組與[公用 PowerShell 庫](https://www.powershellgallery.com/packages/MicrosoftTeams/)中的模組版本。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-107">Don't install the Teams PowerShell module from the PowerShell Test Gallery side-by-side with a version of the module from the [public PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="ed1b3-108">請依照下列步驟，先從公用 PowerShell 庫中卸載團隊 PowerShell 模組，然後從 PowerShell 測試圖庫安裝最新版本的模組。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-108">Follow these steps to first uninstall the Teams PowerShell module from the public PowerShell Gallery, and then install the latest version of the module from the PowerShell Test Gallery.</span></span>

1. <span data-ttu-id="ed1b3-109">關閉所有現有的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-109">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="ed1b3-110">啟動新的 Windows PowerShell 模組實例。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-110">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="ed1b3-111">執行下列動作，從公用 PowerShell 庫中卸載團隊 PowerShell 模組：</span><span class="sxs-lookup"><span data-stu-id="ed1b3-111">Run the following to uninstall the Teams PowerShell module from the public PowerShell Gallery:</span></span>

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. <span data-ttu-id="ed1b3-112">關閉所有現有的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-112">Close all existing PowerShell sessions.</span></span>
5. <span data-ttu-id="ed1b3-113">再次啟動 Windows PowerShell 模組，然後執行下列動作，以將 PowerShell 測試圖庫註冊為受信任的來源：</span><span class="sxs-lookup"><span data-stu-id="ed1b3-113">Start the Windows PowerShell module again, and then run the following to register the PowerShell Test Gallery as a trusted source:</span></span>

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. <span data-ttu-id="ed1b3-114">執行下列動作，從 PowerShell 測試圖庫安裝最新的團隊 PowerShell 模組：</span><span class="sxs-lookup"><span data-stu-id="ed1b3-114">Run the following to install the latest Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. <span data-ttu-id="ed1b3-115">執行下列動作，確認已成功安裝 PowerShell 測試圖庫中的最新版本的團隊 PowerShell 模組：</span><span class="sxs-lookup"><span data-stu-id="ed1b3-115">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="ed1b3-116">從 PowerShell 測試圖庫更新到最新版本的團隊 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="ed1b3-116">Update to the latest version of the Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="ed1b3-117">如果您已經從 PowerShell 測試庫安裝團隊 PowerShell 模組，請使用下列步驟更新到最新版本。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-117">If you already installed the Teams PowerShell module from the PowerShell Test Gallery, use the following steps to update to the latest version.</span></span>

1. <span data-ttu-id="ed1b3-118">關閉所有現有的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-118">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="ed1b3-119">啟動新的 Windows PowerShell 模組實例。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-119">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="ed1b3-120">執行下列操作以從 PowerShell 測試圖庫更新目前已安裝的團隊 PowerShell 模組版本：</span><span class="sxs-lookup"><span data-stu-id="ed1b3-120">Run the following to update the currently installed version of the Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. <span data-ttu-id="ed1b3-121">執行下列動作，確認已成功安裝 PowerShell 測試圖庫中的最新版本的團隊 PowerShell 模組：</span><span class="sxs-lookup"><span data-stu-id="ed1b3-121">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a><span data-ttu-id="ed1b3-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="ed1b3-122">Related topics</span></span>

- [<span data-ttu-id="ed1b3-123">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="ed1b3-123">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

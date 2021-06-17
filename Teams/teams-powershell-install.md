---
title: 在 PowerShell Microsoft Teams安裝
ms.reviewer: brandber
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
ms.openlocfilehash: 3a1e969a1310a64a281434a630f4fb608b8cfb30
ms.sourcegitcommit: 1b057bfcc3207960b956962845fd5051afe91722
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/15/2021
ms.locfileid: "52947564"
---
# <a name="install-microsoft-teams-powershell-module"></a><span data-ttu-id="d250e-103">安裝 Microsoft Teams PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="d250e-103">Install Microsoft Teams PowerShell Module</span></span>

<span data-ttu-id="d250e-104">本文說明如何使用 PowerShell 圖庫Microsoft Teams PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="d250e-104">This article explains how to install the Microsoft Teams PowerShell module using PowerShell Gallery.</span></span> <span data-ttu-id="d250e-105">所有Microsoft Teams都支援 PowerShell 模組Windows模組。</span><span class="sxs-lookup"><span data-stu-id="d250e-105">The Microsoft Teams PowerShell module is supported on all Windows platforms.</span></span> 

## <a name="requirements"></a><span data-ttu-id="d250e-106">需求</span><span class="sxs-lookup"><span data-stu-id="d250e-106">Requirements</span></span>

<span data-ttu-id="d250e-107">Microsoft TeamsPowerShell 模組在所有平臺上都需要 PowerShell 5.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d250e-107">Microsoft Teams PowerShell module requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="d250e-108">安裝 [適用于您作業系統的最新版本的 PowerShell。](/powershell/scripting/install/installing-powershell)  </span><span class="sxs-lookup"><span data-stu-id="d250e-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span> 

<span data-ttu-id="d250e-109">若要檢查 PowerShell 版本，請在 PowerShell 會話內執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d250e-109">To check your PowerShell version, run the following command from within a PowerShell session:</span></span> 

```powershell
$PSVersionTable.PSVersion 
```
<span data-ttu-id="d250e-110">我們建議您使用 Install-Module Cmdlet 來安裝 Microsoft Teams PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="d250e-110">We recommend that you use the  Install-Module cmdlet to install the Microsoft Teams PowerShell module.</span></span> 
 
<span data-ttu-id="d250e-111">如果 PowerShell 圖庫 (PSGallery) 未配置為 **PowerShellGet** 的可信任存放庫，當您第一次使用 PSGallery 時，會看到下列訊息：</span><span class="sxs-lookup"><span data-stu-id="d250e-111">If PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**, the first time you use the PSGallery you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="d250e-112">若要 **繼續** 安裝 **，** 請回答是或全部是。</span><span class="sxs-lookup"><span data-stu-id="d250e-112">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>

## <a name="installing-using-the-powershellgallery"></a><span data-ttu-id="d250e-113">使用 PowerShellGallery 安裝</span><span class="sxs-lookup"><span data-stu-id="d250e-113">Installing using the PowerShellGallery</span></span>

<span data-ttu-id="d250e-114">Microsoft TeamsPowerShell 模組目前支援與 PowerShell 5.1 一Windows。</span><span class="sxs-lookup"><span data-stu-id="d250e-114">Microsoft Teams PowerShell module is currently supported for use with PowerShell 5.1 on Windows.</span></span> <span data-ttu-id="d250e-115">請遵循下列步驟安裝模組：</span><span class="sxs-lookup"><span data-stu-id="d250e-115">Follow these steps to install the module:</span></span> 

- <span data-ttu-id="d250e-116">更新至[Windows PowerShell 5.1。](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="d250e-116">Update to [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).</span></span> <span data-ttu-id="d250e-117">如果您是使用 1607 Windows 10版本，表示您已安裝 PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="d250e-117">If you're on Windows 10 version 1607 or higher, you already have PowerShell 5.1 installed.</span></span> 
- <span data-ttu-id="d250e-118">安裝[.NET Framework 4.7.2](/dotnet/framework/install)或更新版。</span><span class="sxs-lookup"><span data-stu-id="d250e-118">Install [.NET Framework 4.7.2](/dotnet/framework/install) or later.</span></span> 
- <span data-ttu-id="d250e-119">執行下列命令以安裝最新的 PowerShellGet：</span><span class="sxs-lookup"><span data-stu-id="d250e-119">Run the following command to install the latest PowerShellGet:</span></span>
 
```powershell
Install-Module -Name PowerShellGet -Force -AllowClobber
```
- <span data-ttu-id="d250e-120">安裝 powerShell Teams模組。</span><span class="sxs-lookup"><span data-stu-id="d250e-120">Install the Teams PowerShell Module.</span></span>

```powershell
Install-Module -Name MicrosoftTeams -Force -AllowClobber
```

## <a name="offline-installation"></a><span data-ttu-id="d250e-121">離線安裝</span><span class="sxs-lookup"><span data-stu-id="d250e-121">Offline Installation</span></span> 

<span data-ttu-id="d250e-122">在某些環境中，無法連接到 PowerShell 圖庫。</span><span class="sxs-lookup"><span data-stu-id="d250e-122">In some environments, it's not possible to connect to the PowerShell Gallery.</span></span> <span data-ttu-id="d250e-123">在這些情況下，請遵循這些 [手動安裝步驟](https://aka.ms/psgallery-manualdownload)。</span><span class="sxs-lookup"><span data-stu-id="d250e-123">In those situations, please follow these [manual installation steps](https://aka.ms/psgallery-manualdownload).</span></span>  

## <a name="sign-in"></a><span data-ttu-id="d250e-124">登錄</span><span class="sxs-lookup"><span data-stu-id="d250e-124">Sign in</span></span>

<span data-ttu-id="d250e-125">若要開始使用 PowerShell 模組Microsoft Teams，請以 Azure 認證來登錄。</span><span class="sxs-lookup"><span data-stu-id="d250e-125">To start working with Microsoft Teams PowerShell module, sign in with your Azure credentials.</span></span>

```PowerShell
Connect-MicrosoftTeams 
``` 

## <a name="update-teams-powershell-module"></a><span data-ttu-id="d250e-126">更新 Teams PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="d250e-126">Update Teams PowerShell Module</span></span>

<span data-ttu-id="d250e-127">若要更新任何 PowerShell 模組，您應該使用與安裝模組相同的方法。</span><span class="sxs-lookup"><span data-stu-id="d250e-127">To update any PowerShell module, you should use the same method used to install the module.</span></span> <span data-ttu-id="d250e-128">例如，如果您原本是使用 Install-Module，您應該使用 [Update-Module](/powershell/module/powershellget/update-module) 取得最新版本。</span><span class="sxs-lookup"><span data-stu-id="d250e-128">For example, if you originally used Install-Module, then you should use [Update-Module](/powershell/module/powershellget/update-module) to get the latest version.</span></span>  

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="d250e-129">如果Teams PowerShell 已導入到 PowerShell 會話，更新模組將會失敗。</span><span class="sxs-lookup"><span data-stu-id="d250e-129">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="d250e-130">關閉 PowerShell，然後重新開啟新的提升的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="d250e-130">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="d250e-131">卸載 Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="d250e-131">Uninstall Teams PowerShell</span></span>

<span data-ttu-id="d250e-132">若要卸載 powerShell Microsoft Teams，請開啟新的 PowerShell 命令提示，然後執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="d250e-132">To uninstall Microsoft Teams PowerShell, open a new PowerShell command prompt and run the following:</span></span> 

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions 
```

## <a name="next-steps"></a><span data-ttu-id="d250e-133">後續步驟</span><span class="sxs-lookup"><span data-stu-id="d250e-133">Next Steps</span></span> 

<span data-ttu-id="d250e-134">現在，您可以使用 PowerShell Microsoft Teams管理Microsoft Teams應用程式。</span><span class="sxs-lookup"><span data-stu-id="d250e-134">Now you're ready to manage Microsoft Teams using Microsoft Teams PowerShell.</span></span> <span data-ttu-id="d250e-135">請參閱[使用 powerShell Teams管理Teams以](teams-powershell-managing-teams.md)開始使用。</span><span class="sxs-lookup"><span data-stu-id="d250e-135">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="d250e-136">相關主題</span><span class="sxs-lookup"><span data-stu-id="d250e-136">Related topics</span></span>

[<span data-ttu-id="d250e-137">使用 powerShell Teams管理Teams</span><span class="sxs-lookup"><span data-stu-id="d250e-137">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="d250e-138">TeamsPowerShell 版本資訊</span><span class="sxs-lookup"><span data-stu-id="d250e-138">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="d250e-139">Microsoft Teams Cmdlet 參照</span><span class="sxs-lookup"><span data-stu-id="d250e-139">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="d250e-140">商務用 Skype Cmdlet 參照</span><span class="sxs-lookup"><span data-stu-id="d250e-140">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)

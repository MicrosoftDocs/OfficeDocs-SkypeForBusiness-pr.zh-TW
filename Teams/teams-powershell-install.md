---
title: 安裝 Microsoft Teams PowerShell
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
description: 瞭解如何使用 PowerShell 控制項來管理 Microsoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: e6ba8545159f8b18ebe39e49356f64378f946b29
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874803"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="c569f-103">安裝 Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="c569f-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="c569f-104">本文說明如何使用 PowerShellGet 安裝 Microsoft Teams [PowerShell 模組](/powershell/scripting/gallery/installing-psget)。</span><span class="sxs-lookup"><span data-stu-id="c569f-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="c569f-105">這些指示可于 [Azure Cloud Shell、Linux、macOS](/azure/cloud-shell/overview)和 Windows 平臺上使用。</span><span class="sxs-lookup"><span data-stu-id="c569f-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="c569f-106">需求</span><span class="sxs-lookup"><span data-stu-id="c569f-106">Requirements</span></span>

<span data-ttu-id="c569f-107">Teams PowerShell 需要在所有平臺上使用 PowerShell 5.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="c569f-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="c569f-108">安裝[適用于您作業系統的最新版本的 PowerShell。](/powershell/scripting/install/installing-powershell)</span><span class="sxs-lookup"><span data-stu-id="c569f-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="c569f-109">PowerShell 7 和 Teams PowerShell 有已知問題。</span><span class="sxs-lookup"><span data-stu-id="c569f-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="c569f-110">為了獲得最佳體驗，建議您使用 PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="c569f-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="c569f-111">安裝 Teams PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="c569f-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="c569f-112">為了獲得最佳體驗，請使用一般 (GA) 或公用預覽模組 -而不是兩者。</span><span class="sxs-lookup"><span data-stu-id="c569f-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="c569f-113">它們並不適合共同作業。</span><span class="sxs-lookup"><span data-stu-id="c569f-113">They're not intended to work together.</span></span>


<span data-ttu-id="c569f-114">使用 **PowerShellGet** Cmdlet 來安裝 Teams PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="c569f-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="c569f-115">在系統上為所有使用者安裝模組時，需要提升許可權。</span><span class="sxs-lookup"><span data-stu-id="c569f-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="c569f-116">使用 Windows 中的系統管理員 **執行** PowerShell 會話，或使用 macOS 或 `sudo` Linux 上的命令：</span><span class="sxs-lookup"><span data-stu-id="c569f-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="c569f-117">根據預設，PSGallery (的 PowerShell 圖庫) 未配置為 **PowerShellGet** 的受信任的存放庫。</span><span class="sxs-lookup"><span data-stu-id="c569f-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="c569f-118">第一次使用 PSGallery 時，會看到下列訊息：</span><span class="sxs-lookup"><span data-stu-id="c569f-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="c569f-119">回答 **是** 或 **全部是** 以繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="c569f-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="c569f-120">安裝 Teams PowerShell 公開預覽版</span><span class="sxs-lookup"><span data-stu-id="c569f-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="c569f-121">如果您使用的是 Teams PowerShell 的公用預覽版，我們強烈建議您先卸載商務用 Skype Online Connector。</span><span class="sxs-lookup"><span data-stu-id="c569f-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="c569f-122">在系統上為所有使用者安裝 Teams PowerShell 公用預覽模組時，需要提升許可權。</span><span class="sxs-lookup"><span data-stu-id="c569f-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="c569f-123">使用 Windows 中的系統管理員 **執行** PowerShell 會話，或使用 macOS 或 `sudo` Linux 上的命令。</span><span class="sxs-lookup"><span data-stu-id="c569f-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="c569f-124">如果您使用的是 PowerShell 5.1，則必須事先更新 **PowerShellGet** 模組。</span><span class="sxs-lookup"><span data-stu-id="c569f-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="c569f-125">更新 **PowerShellGet** 之後，關閉並重新開啟提升的 PowerShell 會話，以確保載入最新的 **PowerShellGet。**</span><span class="sxs-lookup"><span data-stu-id="c569f-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="c569f-126">若要安裝 Teams PowerShell 公開預覽版，請執行下方的 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="c569f-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="c569f-127">您可以在 PowerShell 圖庫或 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 中，使用「Find-Module MicrosoftTeams -AllowPrerelease -AllVersions」來尋找最新的預覽版本</span><span class="sxs-lookup"><span data-stu-id="c569f-127">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="c569f-128">安裝商務用 Skype Online 連接器</span><span class="sxs-lookup"><span data-stu-id="c569f-128">Install the Skype for Business Online Connector</span></span>

> [!NOTE]
>
> <span data-ttu-id="c569f-129">商務用 Skype Online Connector 目前是 Teams PowerShell 最新模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="c569f-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
> <span data-ttu-id="c569f-130">如果您使用的是最新的 [Teams PowerShell 公開發行](https://www.powershellgallery.com/packages/MicrosoftTeams/)，則不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="c569f-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>


```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in"></a><span data-ttu-id="c569f-131">登錄</span><span class="sxs-lookup"><span data-stu-id="c569f-131">Sign in</span></span>

<span data-ttu-id="c569f-132">若要開始使用 Teams PowerShell，請以 Azure 認證來登錄。</span><span class="sxs-lookup"><span data-stu-id="c569f-132">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="c569f-133">如果您使用的是最新的 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)公開預覽版，則不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="c569f-133">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a><span data-ttu-id="c569f-134">使用 MFA 和新式驗證來登錄</span><span class="sxs-lookup"><span data-stu-id="c569f-134">Sign in using MFA and modern authentication</span></span>

 <span data-ttu-id="c569f-135">如果您的帳戶使用多重要素驗證，請使用本節中的步驟。</span><span class="sxs-lookup"><span data-stu-id="c569f-135">If your account uses multi-factor authentication, use the steps in this section.</span></span>

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="c569f-136">更新 Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="c569f-136">Update Teams PowerShell</span></span>

<span data-ttu-id="c569f-137">若要更新 Teams PowerShell，請開啟新的提升的 PowerShell 命令提示，然後執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c569f-137">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="c569f-138">如果 Teams PowerShell 已導入 PowerShell 會話，更新模組將會失敗。</span><span class="sxs-lookup"><span data-stu-id="c569f-138">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="c569f-139">關閉 PowerShell，然後重新開啟新的提升的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="c569f-139">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="c569f-140">卸載 Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="c569f-140">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="c569f-141">若要卸載 Teams PowerShell，請開啟新的提升的 PowerShell 命令提示，然後執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c569f-141">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="c569f-142">如果 Teams PowerShell 已導入 PowerShell 會話，卸載模組將會失敗。</span><span class="sxs-lookup"><span data-stu-id="c569f-142">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="c569f-143">關閉 PowerShell，然後重新開啟新的提升的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="c569f-143">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c569f-144">後續步驟</span><span class="sxs-lookup"><span data-stu-id="c569f-144">Next Steps</span></span>

<span data-ttu-id="c569f-145">現在，您已準備好使用 Teams PowerShell 來管理 Teams。</span><span class="sxs-lookup"><span data-stu-id="c569f-145">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="c569f-146">請參閱 [使用 Teams PowerShell 管理 Teams](teams-powershell-managing-teams.md) 以開始使用。</span><span class="sxs-lookup"><span data-stu-id="c569f-146">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c569f-147">相關主題</span><span class="sxs-lookup"><span data-stu-id="c569f-147">Related topics</span></span>

[<span data-ttu-id="c569f-148">使用 Teams PowerShell 管理 Teams</span><span class="sxs-lookup"><span data-stu-id="c569f-148">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="c569f-149">Teams PowerShell 版本資訊</span><span class="sxs-lookup"><span data-stu-id="c569f-149">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="c569f-150">Microsoft Teams Cmdlet 參照</span><span class="sxs-lookup"><span data-stu-id="c569f-150">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="c569f-151">商務用 Skype Cmdlet 參照</span><span class="sxs-lookup"><span data-stu-id="c569f-151">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

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
ms.openlocfilehash: 6679cd22800307ec95ac242c190d6483411413a9
ms.sourcegitcommit: 109b3869afb5ff1ca4eaf771399d7cda70a43bea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/05/2021
ms.locfileid: "51586542"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="ad3fc-103">安裝 Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad3fc-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="ad3fc-104">本文說明如何使用 PowerShellGet 安裝 Microsoft Teams [PowerShell 模組](/powershell/scripting/gallery/installing-psget)。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="ad3fc-105">這些指示可于 [Azure Cloud Shell、Linux、macOS](/azure/cloud-shell/overview)和 Windows 平臺上使用。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="ad3fc-106">需求</span><span class="sxs-lookup"><span data-stu-id="ad3fc-106">Requirements</span></span>

<span data-ttu-id="ad3fc-107">Teams PowerShell 需要在所有平臺上使用 PowerShell 5.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="ad3fc-108">安裝[適用于您作業系統的最新版本的 PowerShell。](/powershell/scripting/install/installing-powershell)</span><span class="sxs-lookup"><span data-stu-id="ad3fc-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="ad3fc-109">PowerShell 7 和 Teams PowerShell 有已知問題。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="ad3fc-110">為了獲得最佳體驗，建議您使用 PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="ad3fc-111">安裝 Teams PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="ad3fc-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="ad3fc-112">為了獲得最佳體驗，請使用一般 (GA) 或公用預覽模組 -而不是兩者。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="ad3fc-113">它們並不適合共同作業。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-113">They're not intended to work together.</span></span>


<span data-ttu-id="ad3fc-114">使用 **PowerShellGet** Cmdlet 來安裝 Teams PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="ad3fc-115">在系統上為所有使用者安裝模組時，需要提升許可權。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="ad3fc-116">使用 Windows 中的系統管理員 **執行** PowerShell 會話，或使用 macOS 或 `sudo` Linux 上的命令：</span><span class="sxs-lookup"><span data-stu-id="ad3fc-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="ad3fc-117">根據預設，PSGallery (的 PowerShell 圖庫) 未配置為 **PowerShellGet** 的受信任的存放庫。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="ad3fc-118">第一次使用 PSGallery 時，會看到下列訊息：</span><span class="sxs-lookup"><span data-stu-id="ad3fc-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="ad3fc-119">若要 **繼續** 安裝 **，** 請回答是或全部是。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>

## <a name="sign-in"></a><span data-ttu-id="ad3fc-120">登錄</span><span class="sxs-lookup"><span data-stu-id="ad3fc-120">Sign in</span></span>

<span data-ttu-id="ad3fc-121">若要開始使用 Teams PowerShell，請以 Azure 認證來登錄。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-121">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="ad3fc-122">如果您使用的是最新的 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)公開預覽版，則不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-122">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a><span data-ttu-id="ad3fc-123">使用 MFA 和新式驗證來登錄</span><span class="sxs-lookup"><span data-stu-id="ad3fc-123">Sign in using MFA and modern authentication</span></span>

 <span data-ttu-id="ad3fc-124">如果您的帳戶使用多重要素驗證，請使用本節中的步驟。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-124">If your account uses multi-factor authentication, use the steps in this section.</span></span>

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="ad3fc-125">更新 Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad3fc-125">Update Teams PowerShell</span></span>

<span data-ttu-id="ad3fc-126">若要更新 Teams PowerShell，請開啟新的提升的 PowerShell 命令提示，然後執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ad3fc-126">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="ad3fc-127">如果 Teams PowerShell 已導入 PowerShell 會話，更新模組將會失敗。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-127">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="ad3fc-128">關閉 PowerShell，然後重新開啟新的提升的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-128">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="ad3fc-129">卸載 Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad3fc-129">Uninstall Teams PowerShell</span></span>

<span data-ttu-id="ad3fc-130">若要卸載 Teams PowerShell，請開啟新的提升的 PowerShell 命令提示，然後執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ad3fc-130">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="ad3fc-131">如果 Teams PowerShell 已導入您的 PowerShell 會話，卸載模組將會失敗。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-131">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="ad3fc-132">關閉 PowerShell，然後重新開啟新的提升的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-132">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="ad3fc-133">安裝 Teams PowerShell 公開預覽版</span><span class="sxs-lookup"><span data-stu-id="ad3fc-133">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="ad3fc-134">如果您使用的是 Teams PowerShell 的公用預覽版，我們強烈建議您先卸載商務用 Skype Online Connector。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-134">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="ad3fc-135">在系統上為所有使用者安裝 Teams PowerShell 公用預覽模組時，需要提升許可權。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-135">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="ad3fc-136">使用 Windows 中的系統管理員 **執行** PowerShell 會話，或使用 macOS 或 `sudo` Linux 上的命令。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-136">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="ad3fc-137">如果您使用的是 PowerShell 5.1，則必須事先更新 **PowerShellGet** 模組。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-137">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="ad3fc-138">更新 **PowerShellGet** 之後，關閉並重新開啟提升的 PowerShell 會話，以確保載入最新的 **PowerShellGet。**</span><span class="sxs-lookup"><span data-stu-id="ad3fc-138">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="ad3fc-139">若要安裝 Teams PowerShell 公開預覽版，請執行下方的 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-139">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="ad3fc-140">您可以在 PowerShell 圖庫或 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 中，使用「Find-Module MicrosoftTeams -AllowPrerelease -AllVersions」來尋找最新的預覽版本</span><span class="sxs-lookup"><span data-stu-id="ad3fc-140">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="next-steps"></a><span data-ttu-id="ad3fc-141">後續步驟</span><span class="sxs-lookup"><span data-stu-id="ad3fc-141">Next Steps</span></span>

<span data-ttu-id="ad3fc-142">現在，您已準備好使用 Teams PowerShell 來管理 Teams。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-142">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="ad3fc-143">請參閱 [使用 Teams PowerShell 管理 Teams](teams-powershell-managing-teams.md) 以開始使用。</span><span class="sxs-lookup"><span data-stu-id="ad3fc-143">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ad3fc-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="ad3fc-144">Related topics</span></span>

[<span data-ttu-id="ad3fc-145">使用 Teams PowerShell 管理 Teams</span><span class="sxs-lookup"><span data-stu-id="ad3fc-145">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="ad3fc-146">Teams PowerShell 版本資訊</span><span class="sxs-lookup"><span data-stu-id="ad3fc-146">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="ad3fc-147">Microsoft Teams Cmdlet 參照</span><span class="sxs-lookup"><span data-stu-id="ad3fc-147">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="ad3fc-148">商務用 Skype Cmdlet 參照</span><span class="sxs-lookup"><span data-stu-id="ad3fc-148">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
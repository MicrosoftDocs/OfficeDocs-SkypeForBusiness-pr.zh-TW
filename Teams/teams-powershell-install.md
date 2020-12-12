---
title: 安裝 Microsoft 團隊 PowerShell
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
description: 瞭解如何使用 PowerShell 控制項來管理 Microsoft 團隊。
appliesto:
- Microsoft Teams
ms.openlocfilehash: cd5b38dd3a43a405794209a9dc7ac4a4468386ef
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662018"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="8bed5-103">安裝 Microsoft 團隊 PowerShell</span><span class="sxs-lookup"><span data-stu-id="8bed5-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="8bed5-104">本文說明如何使用 [PowerShellGet](/powershell/scripting/gallery/installing-psget)來安裝 Microsoft 團隊 PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="8bed5-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="8bed5-105">這些指示適用于 [Azure 雲端 Shell](/azure/cloud-shell/overview)、Linux、MacOS 和 Windows 平臺。</span><span class="sxs-lookup"><span data-stu-id="8bed5-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="8bed5-106">需求</span><span class="sxs-lookup"><span data-stu-id="8bed5-106">Requirements</span></span>

<span data-ttu-id="8bed5-107">團隊 PowerShell 在所有平臺上都需要 PowerShell 5.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="8bed5-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="8bed5-108">安裝適用于您作業系統的 [最新版本 PowerShell](/powershell/scripting/install/installing-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="8bed5-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="8bed5-109">PowerShell 7 和團隊 PowerShell 存在已知問題。</span><span class="sxs-lookup"><span data-stu-id="8bed5-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="8bed5-110">我們建議您使用 PowerShell 5.1，以獲得最佳使用體驗。</span><span class="sxs-lookup"><span data-stu-id="8bed5-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="8bed5-111">安裝團隊 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="8bed5-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="8bed5-112">若要獲得最佳體驗，請使用一般可用性 (GA) 或公用預覽模組，不包括兩者。</span><span class="sxs-lookup"><span data-stu-id="8bed5-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="8bed5-113">它們不是共同合作。</span><span class="sxs-lookup"><span data-stu-id="8bed5-113">They're not intended to work together.</span></span>


<span data-ttu-id="8bed5-114">使用 **PowerShellGet** Cmdlet 來安裝團隊 PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="8bed5-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="8bed5-115">針對系統上的所有使用者安裝模組需要提升許可權。</span><span class="sxs-lookup"><span data-stu-id="8bed5-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="8bed5-116">在 Windows 中使用 [ **以系統管理員身分執行** ] 或使用 `sudo` macOS 或 Linux 上的命令來啟動 PowerShell 會話：</span><span class="sxs-lookup"><span data-stu-id="8bed5-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="8bed5-117">根據預設，PowerShell 圖庫 (PSGallery) 未設定為 **PowerShellGet** 的可信儲存庫。</span><span class="sxs-lookup"><span data-stu-id="8bed5-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="8bed5-118">第一次使用 PSGallery 時，您會看到下列訊息：</span><span class="sxs-lookup"><span data-stu-id="8bed5-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="8bed5-119">回答 **[是]** 或 **[是]** 以繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="8bed5-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="8bed5-120">安裝團隊 PowerShell 公開預覽版</span><span class="sxs-lookup"><span data-stu-id="8bed5-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="8bed5-121">如果您使用的是公開預覽版的團隊 PowerShell，我們強烈建議您先卸載商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="8bed5-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="8bed5-122">針對系統上的所有使用者安裝團隊 PowerShell 公用預覽模組需要提升許可權。</span><span class="sxs-lookup"><span data-stu-id="8bed5-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="8bed5-123">在 Windows 中使用 [ **以系統管理員身分執行** ] 或使用 `sudo` macOS 或 Linux 中的命令來啟動 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="8bed5-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="8bed5-124">如果您使用的是 PowerShell 5.1，您必須事先更新 **PowerShellGet** 模組。</span><span class="sxs-lookup"><span data-stu-id="8bed5-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="8bed5-125">更新 **PowerShellGet** 之後，請關閉並重新開啟提升許可權的 PowerShell 會話，以確保載入最新的 **PowerShellGet** 。</span><span class="sxs-lookup"><span data-stu-id="8bed5-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="8bed5-126">若要安裝團隊 PowerShell 公開預覽版，請執行下列 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="8bed5-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="8bed5-127">您可以透過執行「Find-Module MicrosoftTeams-AllowPrerelease」，在 [Powershell 庫](https://www.powershellgallery.com/packages/MicrosoftTeams) 或 powershell 中尋找最新的預覽版本。</span><span class="sxs-lookup"><span data-stu-id="8bed5-127">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="8bed5-128">安裝商務用 Skype Online 連接器</span><span class="sxs-lookup"><span data-stu-id="8bed5-128">Install the Skype for Business Online Connector</span></span>

> [!NOTE]
>
> <span data-ttu-id="8bed5-129">商務用 Skype Online 連接器目前是最新團隊 PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="8bed5-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
> <span data-ttu-id="8bed5-130">如果您使用的是最新的 [團隊 PowerShell 公開發行](https://www.powershellgallery.com/packages/MicrosoftTeams/)，就不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="8bed5-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="8bed5-131">登錄</span><span class="sxs-lookup"><span data-stu-id="8bed5-131">Sign in</span></span>

<span data-ttu-id="8bed5-132">若要開始使用團隊 PowerShell，請使用您的 Azure 認證登入。</span><span class="sxs-lookup"><span data-stu-id="8bed5-132">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="8bed5-133">如果您使用的是最新的 [團隊 PowerShell 公開預覽版](https://www.powershellgallery.com/packages/MicrosoftTeams/)，就不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="8bed5-133">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="8bed5-134">更新團隊 PowerShell</span><span class="sxs-lookup"><span data-stu-id="8bed5-134">Update Teams PowerShell</span></span>

<span data-ttu-id="8bed5-135">若要更新團隊 PowerShell，請開啟新的提升 PowerShell 命令提示字元，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8bed5-135">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="8bed5-136">如果團隊 PowerShell 已匯入您的 PowerShell 會話，更新模組將會失敗。</span><span class="sxs-lookup"><span data-stu-id="8bed5-136">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="8bed5-137">關閉 PowerShell，然後重新開啟新的提升的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="8bed5-137">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="8bed5-138">卸載團隊 PowerShell</span><span class="sxs-lookup"><span data-stu-id="8bed5-138">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="8bed5-139">若要卸載團隊 PowerShell，請開啟新的提升 PowerShell 命令提示字元，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8bed5-139">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="8bed5-140">如果團隊 PowerShell 已匯入您的 PowerShell 會話，則卸載模組將會失敗。</span><span class="sxs-lookup"><span data-stu-id="8bed5-140">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="8bed5-141">關閉 PowerShell，然後重新開啟新的提升的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="8bed5-141">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8bed5-142">後續步驟</span><span class="sxs-lookup"><span data-stu-id="8bed5-142">Next Steps</span></span>

<span data-ttu-id="8bed5-143">現在您已經準備好使用團隊 PowerShell 管理團隊。</span><span class="sxs-lookup"><span data-stu-id="8bed5-143">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="8bed5-144">請參閱 [使用團隊 PowerShell 管理團隊](teams-powershell-managing-teams.md) 以開始使用。</span><span class="sxs-lookup"><span data-stu-id="8bed5-144">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8bed5-145">相關主題</span><span class="sxs-lookup"><span data-stu-id="8bed5-145">Related topics</span></span>

[<span data-ttu-id="8bed5-146">使用團隊 PowerShell 管理團隊</span><span class="sxs-lookup"><span data-stu-id="8bed5-146">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="8bed5-147">團隊 PowerShell 版本資訊</span><span class="sxs-lookup"><span data-stu-id="8bed5-147">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="8bed5-148">Microsoft 團隊 Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="8bed5-148">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="8bed5-149">商務用 Skype Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="8bed5-149">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

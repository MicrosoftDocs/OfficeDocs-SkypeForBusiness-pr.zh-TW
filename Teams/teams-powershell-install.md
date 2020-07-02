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
ms.openlocfilehash: 849b22d09c79e97c5eaaeab4dee96b1d432970cb
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944092"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="ec79c-103">安裝 Microsoft 團隊 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec79c-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="ec79c-104">本文說明如何使用[PowerShellGet](/powershell/scripting/gallery/installing-psget)來安裝 Microsoft 團隊 PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="ec79c-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="ec79c-105">這些指示適用于[Azure 雲端 Shell](/azure/cloud-shell/overview)、Linux、MacOS 和 Windows 平臺。</span><span class="sxs-lookup"><span data-stu-id="ec79c-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="ec79c-106">需求</span><span class="sxs-lookup"><span data-stu-id="ec79c-106">Requirements</span></span>

<span data-ttu-id="ec79c-107">團隊 PowerShell 可搭配 PowerShell 6.2.4 及更新版本的所有平臺使用。</span><span class="sxs-lookup"><span data-stu-id="ec79c-107">Teams PowerShell works with PowerShell 6.2.4 and later on all platforms.</span></span> <span data-ttu-id="ec79c-108">Windows 上的 PowerShell 5.1 也支援它。</span><span class="sxs-lookup"><span data-stu-id="ec79c-108">It is also supported with PowerShell 5.1 on Windows.</span></span> <span data-ttu-id="ec79c-109">安裝適用于您作業系統的[最新版本 PowerShell](/powershell/scripting/install/installing-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="ec79c-109">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span> <span data-ttu-id="ec79c-110">在 PowerShell 6.2.4 及更新版本上執行時，小組 PowerShell 沒有其他需求。</span><span class="sxs-lookup"><span data-stu-id="ec79c-110">Teams PowerShell has no additional requirements when run on PowerShell 6.2.4 and later.</span></span>

> [!WARNING]
> <span data-ttu-id="ec79c-111">PowerShell 7 和團隊 PowerShell 存在已知問題。</span><span class="sxs-lookup"><span data-stu-id="ec79c-111">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="ec79c-112">我們建議您使用 PowerShell 5.1，以獲得最佳使用體驗。</span><span class="sxs-lookup"><span data-stu-id="ec79c-112">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="ec79c-113">安裝團隊 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="ec79c-113">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="ec79c-114">若要獲得最佳體驗，請使用 [一般可用性（GA）] 或 [公用預覽] 模組（不是兩者）。</span><span class="sxs-lookup"><span data-stu-id="ec79c-114">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="ec79c-115">它們不是共同合作。</span><span class="sxs-lookup"><span data-stu-id="ec79c-115">They're not intended to work together.</span></span>


<span data-ttu-id="ec79c-116">使用**PowerShellGet** Cmdlet 來安裝團隊 PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="ec79c-116">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="ec79c-117">針對系統上的所有使用者安裝模組需要提升許可權。</span><span class="sxs-lookup"><span data-stu-id="ec79c-117">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="ec79c-118">在 Windows 中使用 [**以系統管理員身分執行**] 或使用 `sudo` macOS 或 Linux 上的命令來啟動 PowerShell 會話：</span><span class="sxs-lookup"><span data-stu-id="ec79c-118">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="ec79c-119">根據預設，PowerShell 庫（PSGallery）未設定為**PowerShellGet**的可信儲存庫。</span><span class="sxs-lookup"><span data-stu-id="ec79c-119">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="ec79c-120">第一次使用 PSGallery 時，您會看到下列訊息：</span><span class="sxs-lookup"><span data-stu-id="ec79c-120">The first time you use the PSGallery, you'll see the following message:</span></span>

```output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="ec79c-121">[回答] `Yes` 或 [ `Yes to All` 繼續安裝]。</span><span class="sxs-lookup"><span data-stu-id="ec79c-121">Answer `Yes` or `Yes to All` to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="ec79c-122">安裝團隊 PowerShell 公開預覽版</span><span class="sxs-lookup"><span data-stu-id="ec79c-122">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="ec79c-123">如果您使用的是公開預覽版的團隊 PowerShell，我們強烈建議您先卸載商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="ec79c-123">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="ec79c-124">針對系統上的所有使用者安裝團隊 PowerShell 公用預覽模組需要提升許可權。</span><span class="sxs-lookup"><span data-stu-id="ec79c-124">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="ec79c-125">在 Windows 中使用 [**以系統管理員身分執行**] 或使用 `sudo` macOS 或 Linux 中的命令來啟動 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="ec79c-125">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="ec79c-126">如果您使用的是 PowerShell 5.1，您必須事先更新**PowerShellGet**模組。</span><span class="sxs-lookup"><span data-stu-id="ec79c-126">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="ec79c-127">更新**PowerShellGet**之後，請關閉並重新開啟提升許可權的 PowerShell 會話，以確保載入最新的**PowerShellGet** 。</span><span class="sxs-lookup"><span data-stu-id="ec79c-127">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="ec79c-128">若要安裝團隊 Powershell 公開預覽版，請執行下列 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="ec79c-128">To install Teams Powershell public preview, run the PowerShell command below.</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="ec79c-129">安裝商務用 Skype Online 連接器</span><span class="sxs-lookup"><span data-stu-id="ec79c-129">Install the Skype for Business Online Connector</span></span>

> [!WARNING]
> <span data-ttu-id="ec79c-130">商務用 Skype Online 連接器目前是團隊 PowerShell 公開預覽版的一部分。</span><span class="sxs-lookup"><span data-stu-id="ec79c-130">Skype for Business Online Connector is currently part of Teams PowerShell public preview.</span></span> <span data-ttu-id="ec79c-131">我們將此功能匯總至團隊 PowerShell 的 GA 發行中後，商務用 Skype Online 連接器將無法使用。</span><span class="sxs-lookup"><span data-stu-id="ec79c-131">Once we've rolled this feature into the GA release of Teams PowerShell, Skype for Business Online Connector will no longer be available.</span></span>

<span data-ttu-id="ec79c-132">下載並安裝[商務用 Skype PowerShell 模組](https://www.microsoft.com/download/details.aspx?id=39366)，然後在 PowerShell 中執行下列操作。</span><span class="sxs-lookup"><span data-stu-id="ec79c-132">Download and install the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), then run the following in PowerShell.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="ec79c-133">登錄</span><span class="sxs-lookup"><span data-stu-id="ec79c-133">Sign in</span></span>

<span data-ttu-id="ec79c-134">若要開始使用團隊 PowerShell，請使用您的 Azure 認證登入。</span><span class="sxs-lookup"><span data-stu-id="ec79c-134">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="ec79c-135">如果您使用的是最新的[團隊 PowerShell 公開預覽版](https://www.powershellgallery.com/packages/MicrosoftTeams/)，就不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="ec79c-135">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credentials

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credentials $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credentials $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="ec79c-136">更新團隊 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec79c-136">Update Teams PowerShell</span></span>

<span data-ttu-id="ec79c-137">若要更新團隊 PowerShell，請開啟新的提升 PowerShell 命令提示字元，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ec79c-137">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="ec79c-138">如果團隊 PowerShell 已匯入您的 PowerShell 會話，更新模組將會失敗。</span><span class="sxs-lookup"><span data-stu-id="ec79c-138">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="ec79c-139">關閉 PowerShell，然後重新開啟新的提升的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="ec79c-139">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="ec79c-140">卸載團隊 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec79c-140">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="ec79c-141">若要卸載團隊 PowerShell，請開啟新的提升 PowerShell 命令提示字元，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ec79c-141">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="ec79c-142">如果團隊 PowerShell 已匯入您的 PowerShell 會話，則卸載模組將會失敗。</span><span class="sxs-lookup"><span data-stu-id="ec79c-142">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="ec79c-143">關閉 PowerShell，然後重新開啟新的提升的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="ec79c-143">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ec79c-144">後續步驟</span><span class="sxs-lookup"><span data-stu-id="ec79c-144">Next Steps</span></span>

<span data-ttu-id="ec79c-145">現在您已經準備好使用團隊 PowerShell 管理團隊。</span><span class="sxs-lookup"><span data-stu-id="ec79c-145">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="ec79c-146">請參閱[使用團隊 PowerShell 管理團隊](teams-powershell-managing-teams.md)以開始使用。</span><span class="sxs-lookup"><span data-stu-id="ec79c-146">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ec79c-147">相關主題</span><span class="sxs-lookup"><span data-stu-id="ec79c-147">Related topics</span></span>

[<span data-ttu-id="ec79c-148">使用團隊 PowerShell 管理團隊</span><span class="sxs-lookup"><span data-stu-id="ec79c-148">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="ec79c-149">團隊 PowerShell 版本資訊</span><span class="sxs-lookup"><span data-stu-id="ec79c-149">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="ec79c-150">Microsoft 團隊 Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="ec79c-150">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="ec79c-151">商務用 Skype Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="ec79c-151">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

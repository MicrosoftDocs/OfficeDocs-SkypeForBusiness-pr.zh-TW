---
title: 適用於虛擬桌面架構的 Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: 瞭解如何在虛擬桌面基礎結構和 VDI (中) Microsoft Teams。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 020ed67b695c10e54d43891d78a77783ab61ee81
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119192"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="a449f-103">適用於虛擬桌面架構的 Teams</span><span class="sxs-lookup"><span data-stu-id="a449f-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="a449f-104">本文將說明在虛擬化環境中使用 Microsoft Teams 的需求和限制。</span><span class="sxs-lookup"><span data-stu-id="a449f-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="a449f-105">什麼是 VDI？</span><span class="sxs-lookup"><span data-stu-id="a449f-105">What is VDI?</span></span>

<span data-ttu-id="a449f-106">虛擬桌面基礎結構 (VDI) 是虛擬化技術，在資料中心集中式伺服器上託管桌面作業系統和應用程式。</span><span class="sxs-lookup"><span data-stu-id="a449f-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="a449f-107">這可讓擁有完整安全且合規性集中式來源的使用者獲得完全個人化的桌面體驗。</span><span class="sxs-lookup"><span data-stu-id="a449f-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>

<span data-ttu-id="a449f-108">虛擬化環境中 Microsoft Teams 支援聊天和共同合作。</span><span class="sxs-lookup"><span data-stu-id="a449f-108">Microsoft Teams in a virtualized environment supports chat and collaboration.</span></span> <span data-ttu-id="a449f-109">此外，Windows 虛擬桌面、Citrix 和 VWindows 平臺也支援通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="a449f-109">And with the Windows Virtual Desktop, Citrix, and VMware platforms, calling and meeting functionality is also supported.</span></span>

<span data-ttu-id="a449f-110">虛擬化環境中的團隊支援多種配置。</span><span class="sxs-lookup"><span data-stu-id="a449f-110">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="a449f-111">這些包括 VDI、專用、共用、永久和非持續性模式。</span><span class="sxs-lookup"><span data-stu-id="a449f-111">These include VDI, dedicated, shared, persistent, and non-persistent modes.</span></span> <span data-ttu-id="a449f-112">功能正在持續開發中，並且會定期新增，且功能將會于未來幾個月和數年內擴充。</span><span class="sxs-lookup"><span data-stu-id="a449f-112">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>

<span data-ttu-id="a449f-113">在虛擬化環境中使用 Teams 可能與在非虛擬化環境中使用 Teams 稍有不同。</span><span class="sxs-lookup"><span data-stu-id="a449f-113">Using Teams in a virtualized environment might be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="a449f-114">例如，某些進位功能可能無法在虛擬化環境中使用，而且視像解析度可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="a449f-114">For example, some advanced features might not be available in a virtualized environment, and video resolution might differ.</span></span>

<span data-ttu-id="a449f-115">若要確保最佳的使用者體驗，請遵循本文中的指引。</span><span class="sxs-lookup"><span data-stu-id="a449f-115">To ensure an optimal user experience, follow the guidance in this article.</span></span>

> [!Note]
> <span data-ttu-id="a449f-116">有關不同平臺上 Teams VDI 的詳細資訊，請參閱 [平臺的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。</span><span class="sxs-lookup"><span data-stu-id="a449f-116">For details about Teams VDI on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="a449f-117">VDI 元件上的 Teams</span><span class="sxs-lookup"><span data-stu-id="a449f-117">Teams on VDI components</span></span>

<span data-ttu-id="a449f-118">在虛擬化環境中使用 Teams 需要下列元件。</span><span class="sxs-lookup"><span data-stu-id="a449f-118">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="a449f-119">**虛擬化代理**：虛擬化提供者的資源和連接管理員，例如 Azure</span><span class="sxs-lookup"><span data-stu-id="a449f-119">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="a449f-120">**虛擬桌面**：執行 Microsoft Teams 的虛擬機器 (虛擬機器) 堆疊</span><span class="sxs-lookup"><span data-stu-id="a449f-120">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="a449f-121">**精簡用戶端**：使用者實際介面的端點</span><span class="sxs-lookup"><span data-stu-id="a449f-121">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="a449f-122">**Teams 桌面應用程式**：Teams 桌面用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="a449f-122">**Teams desktop app**: The Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="a449f-123">VDI 需求團隊</span><span class="sxs-lookup"><span data-stu-id="a449f-123">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="a449f-124">虛擬化提供者需求</span><span class="sxs-lookup"><span data-stu-id="a449f-124">Virtualization provider requirements</span></span>

<span data-ttu-id="a449f-125">Teams 桌面應用程式已經過與領先虛擬化解決方案提供者的驗證。</span><span class="sxs-lookup"><span data-stu-id="a449f-125">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="a449f-126">對於多個市場提供者，我們建議您諮詢您的虛擬化解決方案提供者，以確保您符合最低需求。</span><span class="sxs-lookup"><span data-stu-id="a449f-126">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure that you meet the minimum requirements.</span></span>
  
<span data-ttu-id="a449f-127">目前，在 VDI 上使用音訊/視 (AV) 優化的 Teams 已通過 Windows Virtual Desktop、Citrix 和 V3 的認證。</span><span class="sxs-lookup"><span data-stu-id="a449f-127">Currently, Teams on VDI with audio/video (AV) optimization is certified with Windows Virtual Desktop, Citrix, and VMware.</span></span> <span data-ttu-id="a449f-128">請閱閱本節的資訊，以確保您符合正確功能的所有需求。</span><span class="sxs-lookup"><span data-stu-id="a449f-128">Review the information in this section to ensure that you meet all requirements for proper functionality.</span></span>

### <a name="platforms-certified-for-teams"></a><span data-ttu-id="a449f-129">Teams 平臺認證</span><span class="sxs-lookup"><span data-stu-id="a449f-129">Platforms certified for Teams</span></span>

<span data-ttu-id="a449f-130">下列平臺提供 Teams 的虛擬桌面基礎結構解決方案。</span><span class="sxs-lookup"><span data-stu-id="a449f-130">The following platforms have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="a449f-131">平台</span><span class="sxs-lookup"><span data-stu-id="a449f-131">Platform</span></span>|<span data-ttu-id="a449f-132">解決 方案</span><span class="sxs-lookup"><span data-stu-id="a449f-132">Solution</span></span>|
|----|---|
|![代表 Microsoft 的標誌](media/microsoft-logo.png)| <span data-ttu-id="a449f-134"><a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows 虛擬桌面</a></span><span class="sxs-lookup"><span data-stu-id="a449f-134"><a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows Virtual Desktop</a></span></span> |
|![代表 Citrix 的標誌](media/citrix-logo.png)| <span data-ttu-id="a449f-136"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 虛擬應用程式與桌面</a></span><span class="sxs-lookup"><span data-stu-id="a449f-136"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |
|![代表 VMware 的標誌](media/vmware-logo.png)| <span data-ttu-id="a449f-138"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a></span><span class="sxs-lookup"><span data-stu-id="a449f-138"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a></span></span> |

### <a name="windows-virtual-desktop"></a><span data-ttu-id="a449f-139">Windows 虛擬桌面</span><span class="sxs-lookup"><span data-stu-id="a449f-139">Windows Virtual Desktop</span></span>

<span data-ttu-id="a449f-140">Windows 虛擬桌面為 VDI 上的 Teams 提供 AV 優化。</span><span class="sxs-lookup"><span data-stu-id="a449f-140">Windows Virtual Desktop provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="a449f-141">若要深入瞭解及需求及安裝，請參閱在 [Windows 虛擬桌面使用 Teams](/azure/virtual-desktop/teams-on-wvd)。</span><span class="sxs-lookup"><span data-stu-id="a449f-141">To learn more and requirements and installation, see [Use Teams on Windows Virtual Desktop](/azure/virtual-desktop/teams-on-wvd).</span></span>

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="a449f-142">Citrix 虛擬應用程式與桌面需求</span><span class="sxs-lookup"><span data-stu-id="a449f-142">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="a449f-143">之前稱為 XenApp 和 XenDesktop (的 Citrix 虛擬 App 和桌面) 提供 VDI 上的 Teams AV 優化。</span><span class="sxs-lookup"><span data-stu-id="a449f-143">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="a449f-144">有了 Citrix 虛擬 App 和桌面，VDI 上的 Teams 除了支援聊天和共同合作之外，還支援通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="a449f-144">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="a449f-145">您可以在 Citrix 下載網站下載最新版本的 [Citrix](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)虛擬 App 和桌面。</span><span class="sxs-lookup"><span data-stu-id="a449f-145">You can download the latest version of Citrix Virtual Apps and Desktops at [the Citrix downloads site](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="a449f-146"> (您必須先登錄。) 根據預設，必要元件會套件到 [Citrix Workspace 應用程式 (CWA) ](https://www.citrix.com/downloads/workspace-app/) 和虛擬傳遞代理程式 (VDA) 。</span><span class="sxs-lookup"><span data-stu-id="a449f-146">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="a449f-147">您不需要在 CWA 或 VDA 上安裝任何其他元件或外掛程式。</span><span class="sxs-lookup"><span data-stu-id="a449f-147">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="a449f-148">有關最新的伺服器和用戶端需求，請參閱 [此 Citrix 網站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。</span><span class="sxs-lookup"><span data-stu-id="a449f-148">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a><span data-ttu-id="a449f-149">VMware Horizon Workspace 和桌面需求</span><span class="sxs-lookup"><span data-stu-id="a449f-149">VMware Horizon Workspace and Desktop requirements</span></span>

<span data-ttu-id="a449f-150">V Azure Horizon 是一個現代化平臺，可安全地跨混合式雲端傳遞虛擬桌面和應用程式。</span><span class="sxs-lookup"><span data-stu-id="a449f-150">VMware Horizon is a modern platform for secure delivery of virtual desktops and apps across the hybrid cloud.</span></span> <span data-ttu-id="a449f-151">為了提供出色的使用者體驗，V3 Horizon 提供 Teams 的媒體優化。</span><span class="sxs-lookup"><span data-stu-id="a449f-151">To offer a great end-user experience, VMware Horizon provides media optimization for Teams.</span></span> <span data-ttu-id="a449f-152">這項優化可改善虛擬桌面和應用程式的整體生產力，並提升使用 Teams 通話和開會時的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="a449f-152">This optimization improves overall productivity across virtual desktops and apps, and enhances user experience when calling and meeting using Teams.</span></span>

<span data-ttu-id="a449f-153">您可以從 V 試用版下載頁面下載[最新版本的 V3 Horizon。](https://my.vmware.com/web/vmware/downloads/#all_products)</span><span class="sxs-lookup"><span data-stu-id="a449f-153">You can download the latest version of VMware Horizon from the [VMware Downloads](https://my.vmware.com/web/vmware/downloads/#all_products) page.</span></span> <span data-ttu-id="a449f-154">根據預設，所需的媒體優化元件是 Horizon Agent 和 Horizon Client 的一部分，因此不需要安裝任何其他外掛程式，才能使用 Teams 的優化功能。</span><span class="sxs-lookup"><span data-stu-id="a449f-154">The required media optimization components are part of the Horizon Agent and Horizon Client by default and there's no need to install any additional plug-in to use the optimization feature for Teams.</span></span>

<span data-ttu-id="a449f-155">若要取得有關如何為 Teams 設定媒體優化的最新需求與指示，請參閱 [此 V 方法網站](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)。</span><span class="sxs-lookup"><span data-stu-id="a449f-155">To get the latest requirements and instructions on how to configure media optimization for Teams, see [this VMware website](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html).</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="a449f-156">在 VDI 上安裝或更新 Teams 桌面應用程式</span><span class="sxs-lookup"><span data-stu-id="a449f-156">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="a449f-157">您可以使用每部電腦安裝或使用 MSI 套件的每個使用者安裝來部署適用于 VDI 的 Teams 桌面應用程式。</span><span class="sxs-lookup"><span data-stu-id="a449f-157">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="a449f-158">決定使用哪種方法取決於您是使用永久或非持續性設定，以及貴組織的相關功能需求。</span><span class="sxs-lookup"><span data-stu-id="a449f-158">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>

<span data-ttu-id="a449f-159">對於專用的永久設定，任一方法都會使用。</span><span class="sxs-lookup"><span data-stu-id="a449f-159">For a dedicated persistent setup, either approach would work.</span></span> <span data-ttu-id="a449f-160">不過，對於非持續性設定，Teams 需要每部電腦安裝，才能有效率地運作。</span><span class="sxs-lookup"><span data-stu-id="a449f-160">However, for a non-persistent setup, Teams requires a per-machine installation in order to work efficiently.</span></span> <span data-ttu-id="a449f-161">請參閱 [非持續性設定一](#non-persistent-setup) 節。</span><span class="sxs-lookup"><span data-stu-id="a449f-161">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="a449f-162">每部電腦安裝時，自動更新會停用。</span><span class="sxs-lookup"><span data-stu-id="a449f-162">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="a449f-163">這表示若要更新 Teams 應用程式，您必須卸載目前的版本，以更新至較新版本。</span><span class="sxs-lookup"><span data-stu-id="a449f-163">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="a449f-164">在每個使用者安裝時，自動更新會啟用。</span><span class="sxs-lookup"><span data-stu-id="a449f-164">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="a449f-165">針對大部分的 VDI 部署，我們建議您使用每部電腦安裝來部署 Teams。</span><span class="sxs-lookup"><span data-stu-id="a449f-165">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="a449f-166">若要更新至最新的 Teams 版本，請從卸載程式開始，後面接著最新的 Teams 版本部署。</span><span class="sxs-lookup"><span data-stu-id="a449f-166">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="a449f-167">若要讓 VDI 環境中 Teams AV 優化正常運作，精簡用戶端端點必須能夠存取網際網路。</span><span class="sxs-lookup"><span data-stu-id="a449f-167">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="a449f-168">如果精簡用戶端端點無法存取網際網路，優化啟動將不會成功。</span><span class="sxs-lookup"><span data-stu-id="a449f-168">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="a449f-169">這表示使用者是未優化的媒體狀態。</span><span class="sxs-lookup"><span data-stu-id="a449f-169">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="a449f-170">專用永久設定</span><span class="sxs-lookup"><span data-stu-id="a449f-170">Dedicated persistent setup</span></span>

<span data-ttu-id="a449f-171">在專用的永久設定中，使用者登出後會保留使用者的當地作業系統變更。</span><span class="sxs-lookup"><span data-stu-id="a449f-171">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span> <span data-ttu-id="a449f-172">針對持續性設定，Teams 同時支援每個使用者和每部電腦安裝。</span><span class="sxs-lookup"><span data-stu-id="a449f-172">For persistent setup, Teams supports both per-user and per-machine installation.</span></span>

<span data-ttu-id="a449f-173">以下是建議的最小值 VM 組組。</span><span class="sxs-lookup"><span data-stu-id="a449f-173">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="a449f-174">參數</span><span class="sxs-lookup"><span data-stu-id="a449f-174">Parameter</span></span>  |<span data-ttu-id="a449f-175">工作站作業系統</span><span class="sxs-lookup"><span data-stu-id="a449f-175">Workstation operating system</span></span>  |<span data-ttu-id="a449f-176">伺服器作業系統</span><span class="sxs-lookup"><span data-stu-id="a449f-176">Server operating system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a449f-177">vCPU</span><span class="sxs-lookup"><span data-stu-id="a449f-177">vCPU</span></span>   |    <span data-ttu-id="a449f-178">2 個核心</span><span class="sxs-lookup"><span data-stu-id="a449f-178">2 cores</span></span>     |  <span data-ttu-id="a449f-179">4、6 或 8</span><span class="sxs-lookup"><span data-stu-id="a449f-179">4,6, or 8</span></span><br><span data-ttu-id="a449f-180">瞭解 NUMA (基本非統一) 存取權，並據此設定您的虛擬機器非常重要。</span><span class="sxs-lookup"><span data-stu-id="a449f-180">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="a449f-181">RAM</span><span class="sxs-lookup"><span data-stu-id="a449f-181">RAM</span></span>     |   <span data-ttu-id="a449f-182">4 GB</span><span class="sxs-lookup"><span data-stu-id="a449f-182">4 GB</span></span>      | <span data-ttu-id="a449f-183">每個使用者 512 到 1024 MB</span><span class="sxs-lookup"><span data-stu-id="a449f-183">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="a449f-184">儲存空間</span><span class="sxs-lookup"><span data-stu-id="a449f-184">Storage</span></span>    | <span data-ttu-id="a449f-185">8 GB</span><span class="sxs-lookup"><span data-stu-id="a449f-185">8 GB</span></span>        | <span data-ttu-id="a449f-186">40 到 60 GB</span><span class="sxs-lookup"><span data-stu-id="a449f-186">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="a449f-187">非持續性設定</span><span class="sxs-lookup"><span data-stu-id="a449f-187">Non-persistent setup</span></span>

<span data-ttu-id="a449f-188">在非持續性設定中，使用者登出後不會保留使用者的當地作業系統變更。</span><span class="sxs-lookup"><span data-stu-id="a449f-188">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="a449f-189">這類設定是一般共用的多使用者會話。</span><span class="sxs-lookup"><span data-stu-id="a449f-189">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="a449f-190">VM 組式會依據使用者數量和可用的實體方塊資源而不同。</span><span class="sxs-lookup"><span data-stu-id="a449f-190">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="a449f-191">對於非持續性設定，Teams 桌面應用程式必須每部電腦安裝至金色影像。</span><span class="sxs-lookup"><span data-stu-id="a449f-191">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="a449f-192"> (若要深入瞭解，請參閱在 [VDI](#install-or-update-the-teams-desktop-app-on-vdi) 上安裝或更新 Teams 桌面應用程式一節) 這可確保在使用者會話期間有效率地啟動 Teams 應用程式。</span><span class="sxs-lookup"><span data-stu-id="a449f-192">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.) This ensures an efficient launch of the Teams app during a user session.</span></span>

<span data-ttu-id="a449f-193">在非持續性設定中使用 Teams 也需要設定檔-緩存管理員，以有效進行 Teams 執行時間資料同步處理。</span><span class="sxs-lookup"><span data-stu-id="a449f-193">Using Teams in a non-persistent setup also requires a profile-caching manager, for efficient Teams runtime data synchronization.</span></span> <span data-ttu-id="a449f-194">有效的資料同步處理可確保在使用者會話期間 (適當的使用者特定資訊，例如使用者的資料、設定檔或) 設定。</span><span class="sxs-lookup"><span data-stu-id="a449f-194">Efficient data synchronization ensures that the appropriate user-specific information (such as a user's data, profile, or settings) is cached during the user's session.</span></span> <span data-ttu-id="a449f-195">確認這兩個資料夾中的資料已同步處理：</span><span class="sxs-lookup"><span data-stu-id="a449f-195">Make sure data in these two folders are synched:</span></span><br>
- <span data-ttu-id="a449f-196">C：\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache) </span><span class="sxs-lookup"><span data-stu-id="a449f-196">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span></span>
- <span data-ttu-id="a449f-197">C：\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams) </span><span class="sxs-lookup"><span data-stu-id="a449f-197">C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)</span></span>

> [!NOTE]
> <span data-ttu-id="a449f-198">漫遊資料夾 (，或者如果您使用的是資料夾重新導向，則需要快用管理員) 才能確保 Teams App 具有執行應用程式所需的執行時間資料和檔案。</span><span class="sxs-lookup"><span data-stu-id="a449f-198">A roaming folder (or, if you are using folder redirection, a caching manager) is required to ensure that the Teams app has the runtime data and files required to run the application.</span></span> <span data-ttu-id="a449f-199">這是為了減輕網路延遲問題或網路問題所必須的，否則會造成應用程式錯誤，以及因無法使用的資料和檔案而造成緩慢的體驗。</span><span class="sxs-lookup"><span data-stu-id="a449f-199">This is necessary to mitigate network latency issues or network glitches, which would otherwise cause application errors and a slow experience due to unavailable data and files.</span></span>

<span data-ttu-id="a449f-200">有許多可用的緩存管理員解決方案。</span><span class="sxs-lookup"><span data-stu-id="a449f-200">There are a variety of caching manager solutions available.</span></span> <span data-ttu-id="a449f-201">例如 [，FSLogix](/fslogix/overview)。</span><span class="sxs-lookup"><span data-stu-id="a449f-201">For example, [FSLogix](/fslogix/overview).</span></span> <span data-ttu-id="a449f-202">請參閱您的緩存管理員提供者，以獲得特定組組指示。</span><span class="sxs-lookup"><span data-stu-id="a449f-202">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="a449f-203">適用于非持續性設定之 Teams 的緩存內容排除清單</span><span class="sxs-lookup"><span data-stu-id="a449f-203">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="a449f-204">從 Teams 快取檔案夾 %appdata%/Microsoft/Teams 中排除下列專案。</span><span class="sxs-lookup"><span data-stu-id="a449f-204">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span> <span data-ttu-id="a449f-205">排除這些專案有助於減少使用者緩存大小，進一步優化非持續性設定。</span><span class="sxs-lookup"><span data-stu-id="a449f-205">Excluding these items helps reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="a449f-206">.txt 檔案</span><span class="sxs-lookup"><span data-stu-id="a449f-206">.txt files</span></span>
- <span data-ttu-id="a449f-207">媒體堆疊資料夾</span><span class="sxs-lookup"><span data-stu-id="a449f-207">Media-stack folder</span></span>
- <span data-ttu-id="a449f-208">會議-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache) </span><span class="sxs-lookup"><span data-stu-id="a449f-208">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)</span></span>

### <a name="microsoft-365-apps-for-enterprise-considerations"></a><span data-ttu-id="a449f-209">適用于企業考慮的 Microsoft 365 應用程式</span><span class="sxs-lookup"><span data-stu-id="a449f-209">Microsoft 365 Apps for enterprise considerations</span></span>

<span data-ttu-id="a449f-210">當您在 VDI 上使用 Microsoft 365 企業版 App 部署 Teams 時，請考慮下列事項。</span><span class="sxs-lookup"><span data-stu-id="a449f-210">Consider the following when you deploy Teams with Microsoft 365 Apps for enterprise on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="a449f-211">透過 Microsoft 365 企業版應用程式部署 Teams 的新部署</span><span class="sxs-lookup"><span data-stu-id="a449f-211">New deployments of Teams through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="a449f-212">在透過 Microsoft 365 企業版 App 部署 Teams 之前，您必須先卸載任何使用每部電腦安裝部署的現有 Teams 應用程式。</span><span class="sxs-lookup"><span data-stu-id="a449f-212">Before you deploy Teams through Microsoft 365 Apps for enterprise, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="a449f-213">透過 Microsoft 365 企業版 App 的 Teams 是每個使用者安裝的。</span><span class="sxs-lookup"><span data-stu-id="a449f-213">Teams through Microsoft 365 Apps for enterprise is installed per-user.</span></span> <span data-ttu-id="a449f-214">若要深入瞭解，請參閱在 [VDI](#install-or-update-the-teams-desktop-app-on-vdi) 上安裝或更新 Teams 桌面應用程式一節。</span><span class="sxs-lookup"><span data-stu-id="a449f-214">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a><span data-ttu-id="a449f-215">透過 Microsoft 365 應用程式進行企業更新的 Teams 部署</span><span class="sxs-lookup"><span data-stu-id="a449f-215">Teams deployments through Microsoft 365 Apps for enterprise updates</span></span>

<span data-ttu-id="a449f-216">Teams 也會新增到企業用 Microsoft 365 應用程式的現有安裝中。</span><span class="sxs-lookup"><span data-stu-id="a449f-216">Teams is also being added to existing installations of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="a449f-217">由於適用于企業的 Microsoft 365 應用程式只會安裝 Teams 每個使用者，請參閱在 VDI 上安裝或更新 [Teams 桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi) 一節。</span><span class="sxs-lookup"><span data-stu-id="a449f-217">Since Microsoft 365 Apps for enterprise installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="a449f-218">使用 Teams 進行每部電腦安裝，以及適用于企業的 Microsoft 365 應用程式</span><span class="sxs-lookup"><span data-stu-id="a449f-218">Using Teams with per-machine installation and Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="a449f-219">適用于企業的 Microsoft 365 應用程式不支援 Teams 的整部電腦安裝。</span><span class="sxs-lookup"><span data-stu-id="a449f-219">Microsoft 365 Apps for enterprise doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="a449f-220">若要使用每部電腦安裝，您必須將 Teams 排除在 Microsoft 365 企業版 App 中。</span><span class="sxs-lookup"><span data-stu-id="a449f-220">To use per-machine installation, you must exclude Teams from Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="a449f-221">請參閱 [將 Teams 桌面應用程式部署到虛擬機器](#deploy-the-teams-desktop-app-to-the-vm) ，以及如何透過 [Microsoft 365](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) 企業版 App 排除 Teams 部署> 區段。</span><span class="sxs-lookup"><span data-stu-id="a449f-221">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Microsoft 365 Apps for enterprise](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="a449f-222">如何透過 Microsoft 365 企業版應用程式排除 Teams 部署</span><span class="sxs-lookup"><span data-stu-id="a449f-222">How to exclude Teams deployment through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="a449f-223">若要深入瞭解 Teams 和企業用 Microsoft 365 應用程式，請參閱如何將 Teams 排除在適用于企業的 [Microsoft 365 應用程式](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) 的新安裝中，以及使用群組原則來控制 Teams 的 [安裝](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="a449f-223">To learn more about Teams and Microsoft 365 Apps for enterprise, see [How to exclude Teams from new installations of Microsoft 365 Apps for enterprise](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="a449f-224">將 Teams 桌面應用程式部署到虛擬機器</span><span class="sxs-lookup"><span data-stu-id="a449f-224">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="a449f-225">使用下列其中一個連結下載符合 VDI VM 作業系統的 Teams MSI 套件：</span><span class="sxs-lookup"><span data-stu-id="a449f-225">Download the Teams MSI package that matches your VDI VM operating system using one of the following links:</span></span>

    - [<span data-ttu-id="a449f-226">32 位版本</span><span class="sxs-lookup"><span data-stu-id="a449f-226">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [<span data-ttu-id="a449f-227">64 位版本</span><span class="sxs-lookup"><span data-stu-id="a449f-227">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > <span data-ttu-id="a449f-228">針對政府雲端，請參閱使用 [Microsoft 端點組組管理員](msi-deployment.md) 安裝 Microsoft Teams 以下載 MSI 檔案的連結。</span><span class="sxs-lookup"><span data-stu-id="a449f-228">For government clouds, see [Install Microsoft Teams using Microsoft Endpoint Configuration Manager](msi-deployment.md) for the download links to the MSI files.</span></span>

    <span data-ttu-id="a449f-229">Teams 桌面應用程式的最低版本為版本 1.3.00.4461。</span><span class="sxs-lookup"><span data-stu-id="a449f-229">The minimum version of the Teams desktop app that's required is version 1.3.00.4461.</span></span> <span data-ttu-id="a449f-230"> (版本不支援 PSTN 保留) </span><span class="sxs-lookup"><span data-stu-id="a449f-230">(PSTN hold isn't supported in earlier versions.)</span></span>

2. <span data-ttu-id="a449f-231">執行下列其中一個命令，將 MSI 安裝到 VDI VM：</span><span class="sxs-lookup"><span data-stu-id="a449f-231">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="a449f-232">每個使用者安裝 (預設) </span><span class="sxs-lookup"><span data-stu-id="a449f-232">Per-user installation (default)</span></span>
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        <span data-ttu-id="a449f-233">此程式是預設安裝，會將 Teams 安裝至 %AppData% 使用者資料夾。</span><span class="sxs-lookup"><span data-stu-id="a449f-233">This process is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="a449f-234">此時，金色影像設定已完成。</span><span class="sxs-lookup"><span data-stu-id="a449f-234">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="a449f-235">在非持續性設定上，Teams 無法與每個使用者安裝一起正常運作。</span><span class="sxs-lookup"><span data-stu-id="a449f-235">Teams won't work properly with per-user installation on a non-persistent setup.</span></span>

    - <span data-ttu-id="a449f-236">每部電腦安裝</span><span class="sxs-lookup"><span data-stu-id="a449f-236">Per-machine installation</span></span>

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        <span data-ttu-id="a449f-237">此程式會將 Teams 安裝到 64 位作業系統上的 (x86) 資料夾，以及 32 位作業系統上的程式檔案資料夾。</span><span class="sxs-lookup"><span data-stu-id="a449f-237">This process installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="a449f-238">此時，金色影像設定已完成。</span><span class="sxs-lookup"><span data-stu-id="a449f-238">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="a449f-239">非持續性設定需要每部電腦安裝 Teams。</span><span class="sxs-lookup"><span data-stu-id="a449f-239">Installing Teams per-machine is required for non-persistent setups.</span></span>

        <span data-ttu-id="a449f-240">下一個互動式登入會話會啟動 Teams，並要求認證。</span><span class="sxs-lookup"><span data-stu-id="a449f-240">The next interactive logon session starts Teams and asks for credentials.</span></span>

        > [!NOTE]
        > <span data-ttu-id="a449f-241">這些範例也會使用 **ALLUSERS=1** 參數。</span><span class="sxs-lookup"><span data-stu-id="a449f-241">These examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="a449f-242">當您設定此參數時，Teams Machine-Wide安裝程式會顯示在控制台中的程式和功能中，& Windows 設定中適用于電腦的所有使用者的 App 中顯示功能。</span><span class="sxs-lookup"><span data-stu-id="a449f-242">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="a449f-243">如果使用者擁有系統管理員認證，則所有使用者都可以卸載 Teams。</span><span class="sxs-lookup"><span data-stu-id="a449f-243">All users can then uninstall Teams if they have admin credentials.</span></span>
        <span data-ttu-id="a449f-244">瞭解 **ALLUSERS=1** 與 **ALLUSER=1 的差異非常重要**。</span><span class="sxs-lookup"><span data-stu-id="a449f-244">It's important to understand the difference between **ALLUSERS=1** and **ALLUSER=1**.</span></span> <span data-ttu-id="a449f-245">**ALLUSERS=1** 參數可用於非 VDI 和 VDI 環境，而 **ALLUSER=1** 參數只能在 VDI 環境中使用，以指定每部電腦安裝。</span><span class="sxs-lookup"><span data-stu-id="a449f-245">The **ALLUSERS=1** parameter can be used in non-VDI and VDI environments, while the **ALLUSER=1** parameter is used only in VDI environments to specify a per-machine installation.</span></span>

3. <span data-ttu-id="a449f-246">從 VDI VM 卸載 MSI。</span><span class="sxs-lookup"><span data-stu-id="a449f-246">Uninstall the MSI from the VDI VM.</span></span> <span data-ttu-id="a449f-247">卸載 Teams 的方法有兩種。</span><span class="sxs-lookup"><span data-stu-id="a449f-247">There are two ways to uninstall Teams.</span></span>

    - <span data-ttu-id="a449f-248">PowerShell 腳本：您可以使用 [此 PowerShell 腳本](scripts/powershell-script-deployment-cleanup.md) 卸載 Teams，並移除使用者的 Teams 資料夾。</span><span class="sxs-lookup"><span data-stu-id="a449f-248">PowerShell script: You can use [this PowerShell script](scripts/powershell-script-deployment-cleanup.md) to uninstall Teams and remove the Teams folder for a user.</span></span> <span data-ttu-id="a449f-249">針對電腦上安裝 Teams 的每個使用者設定檔執行腳本。</span><span class="sxs-lookup"><span data-stu-id="a449f-249">Run the script for each user profile in which Teams was installed on the computer.</span></span>
    - <span data-ttu-id="a449f-250">命令列：執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="a449f-250">Command line: Run the following command.</span></span>
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      <span data-ttu-id="a449f-251">此程式會視作業系統環境，從 (x86) 資料夾或程式檔案資料夾中卸載 Teams。</span><span class="sxs-lookup"><span data-stu-id="a449f-251">This process uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="a449f-252">關於 VDI 績效考慮的 Teams</span><span class="sxs-lookup"><span data-stu-id="a449f-252">Teams on VDI performance considerations</span></span>

<span data-ttu-id="a449f-253">有各種不同的虛擬化設定設定，每個設定都有不同的優化焦點。</span><span class="sxs-lookup"><span data-stu-id="a449f-253">There are a variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="a449f-254">例如，組組可能會著重于使用者密度。</span><span class="sxs-lookup"><span data-stu-id="a449f-254">For example, a configuration might focus on user density.</span></span> <span data-ttu-id="a449f-255">規劃時，請考慮下列專案，以根據貴組織的工作量需求來協助優化您的設定。</span><span class="sxs-lookup"><span data-stu-id="a449f-255">When planning, consider the following to help optimize your setup based on your organization's workload needs.</span></span>

- <span data-ttu-id="a449f-256">最低需求：某些工作負載可能需要使用高於最低需求的資源進行設定。</span><span class="sxs-lookup"><span data-stu-id="a449f-256">Minimum requirement: Some workloads might require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="a449f-257">例如，針對使用需要更多計算資源之應用程式之開發人員的工作負載。</span><span class="sxs-lookup"><span data-stu-id="a449f-257">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="a449f-258">相依性：這些包括基礎結構、工作負載及其他 Teams 桌面應用程式外部環境考慮的相依性。</span><span class="sxs-lookup"><span data-stu-id="a449f-258">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="a449f-259">VDI 上的停用功能：Teams 會停用 VDI 的 GPU 密集功能，這有助於改善暫時性的 CPU 使用率。</span><span class="sxs-lookup"><span data-stu-id="a449f-259">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="a449f-260">下列功能已停用：</span><span class="sxs-lookup"><span data-stu-id="a449f-260">The following features are disabled:</span></span>
    - <span data-ttu-id="a449f-261">Teams CSS 動畫</span><span class="sxs-lookup"><span data-stu-id="a449f-261">Teams CSS animation</span></span>
    - <span data-ttu-id="a449f-262">Giphy 自動啟動</span><span class="sxs-lookup"><span data-stu-id="a449f-262">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="a449f-263">VDI 上的 Teams 與通話和會議</span><span class="sxs-lookup"><span data-stu-id="a449f-263">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="a449f-264">除了聊天和共同合作之外，支援虛擬化提供者平臺的 VDI 上的 Teams 也提供通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="a449f-264">In addition to chat and collaboration, Teams on VDI with calling and meetings is available with supported virtualization provider platforms.</span></span> <span data-ttu-id="a449f-265">支援的功能是以 WebRTC 媒體堆疊和虛擬化提供者的實現為基礎。</span><span class="sxs-lookup"><span data-stu-id="a449f-265">Supported features are based on the WebRTC media stack and virtualization provider implementation.</span></span> <span data-ttu-id="a449f-266">下圖提供架構概觀。</span><span class="sxs-lookup"><span data-stu-id="a449f-266">The following diagram provides an overview of the architecture.</span></span>

![顯示 VDI 架構上的 Teams 圖表](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> <span data-ttu-id="a449f-268">如果您目前執行 Teams 時未在 VDI 中執行 AV 優化，而且使用尚未支援的功能進行優化 (例如當 App 共用時提供並控制) ，您必須設定虛擬化提供者政策，以關閉 Teams 重新導向。</span><span class="sxs-lookup"><span data-stu-id="a449f-268">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set virtualization provider policies to turn off Teams redirection.</span></span> <span data-ttu-id="a449f-269">這表示 Teams 媒體會話不會優化。</span><span class="sxs-lookup"><span data-stu-id="a449f-269">This means that Teams media sessions won't be optimized.</span></span> <span data-ttu-id="a449f-270">如需如何設定關閉 Teams 重新導向之策略的步驟，請與您的虛擬化提供者聯繫。</span><span class="sxs-lookup"><span data-stu-id="a449f-270">For steps on how to set policies to turn off Teams redirection, contact your virtualization provider.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="a449f-271">網路需求</span><span class="sxs-lookup"><span data-stu-id="a449f-271">Network requirements</span></span>

<span data-ttu-id="a449f-272">我們建議您評估您的環境，找出可能會影響整體雲端語音和視像部署的任何風險與需求。</span><span class="sxs-lookup"><span data-stu-id="a449f-272">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="a449f-273">使用 [商務用 Skype 網路評定工具](https://www.microsoft.com/download/details.aspx?id=53885) ，測試您的網路是否已準備好供 Teams 使用。</span><span class="sxs-lookup"><span data-stu-id="a449f-273">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="a449f-274">若要深入瞭解如何為 Teams 準備您的網路，請參閱準備貴組織的 Teams [網路](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="a449f-274">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="a449f-275">從 VDI 上的商務用 Skype 遷移到 VDI 上的 Teams</span><span class="sxs-lookup"><span data-stu-id="a449f-275">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="a449f-276">如果您要從 VDI 上的商務用 Skype 移至 VDI 上的 Teams，除了這兩種應用程式之間的差異之外，在 VDI 也執行時也會有一些差異。</span><span class="sxs-lookup"><span data-stu-id="a449f-276">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="a449f-277">商務用 Skype VDI 中的 Teams VDI 目前不支援的一些功能如下：</span><span class="sxs-lookup"><span data-stu-id="a449f-277">Some capabilities that aren't currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="a449f-278">在 VDI 中停用部分 AV 功能的每個平臺策略</span><span class="sxs-lookup"><span data-stu-id="a449f-278">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="a449f-279">在應用程式共用時給予並控制</span><span class="sxs-lookup"><span data-stu-id="a449f-279">Give and take control when app sharing</span></span>
- <span data-ttu-id="a449f-280">從沒有音訊的聊天分享螢幕畫面</span><span class="sxs-lookup"><span data-stu-id="a449f-280">Screen share from chat without audio</span></span>
- <span data-ttu-id="a449f-281">同時傳送和接收視像和螢幕畫面共用</span><span class="sxs-lookup"><span data-stu-id="a449f-281">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="a449f-282">Chrome 瀏覽器上的 Teams 與適用于 VDI 的 Teams 桌面應用程式</span><span class="sxs-lookup"><span data-stu-id="a449f-282">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="a449f-283">Chrome 瀏覽器上的 Teams 無法以 AV 優化取代 VDI 的 Teams 桌面應用程式。</span><span class="sxs-lookup"><span data-stu-id="a449f-283">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="a449f-284">聊天和共同合作體驗如預期運作。</span><span class="sxs-lookup"><span data-stu-id="a449f-284">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="a449f-285">當需要媒體時，Chrome 瀏覽器上的某些體驗可能不符合使用者預期：</span><span class="sxs-lookup"><span data-stu-id="a449f-285">When media is needed, there are some experiences that might not meet user expectations on the Chrome browser:</span></span>

- <span data-ttu-id="a449f-286">音訊和視音訊串流體驗可能並非最佳。</span><span class="sxs-lookup"><span data-stu-id="a449f-286">The audio and video streaming experience might not be optimal.</span></span> <span data-ttu-id="a449f-287">使用者可能會遭遇延遲或品質降低的問題。</span><span class="sxs-lookup"><span data-stu-id="a449f-287">Users might experiences delays or reduced quality.</span></span>
- <span data-ttu-id="a449f-288">瀏覽器設定中無法提供裝置設定。</span><span class="sxs-lookup"><span data-stu-id="a449f-288">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="a449f-289">裝置管理是透過瀏覽器處理，需要瀏覽器網站設定中的多個設定。</span><span class="sxs-lookup"><span data-stu-id="a449f-289">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="a449f-290">您可能也需要在 Windows 裝置管理中設定裝置設定。</span><span class="sxs-lookup"><span data-stu-id="a449f-290">Device settings might also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="a449f-291">使用聊天和共同合作功能在 VDI 上的團隊</span><span class="sxs-lookup"><span data-stu-id="a449f-291">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="a449f-292">如果貴組織只想在 Teams 中使用聊天和共同合作功能，您可以設定使用者層級策略以關閉 Teams 中的通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="a449f-292">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span> 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="a449f-293">設定關閉通話和會議功能的政策</span><span class="sxs-lookup"><span data-stu-id="a449f-293">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="a449f-294">您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來設定策略。</span><span class="sxs-lookup"><span data-stu-id="a449f-294">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="a449f-295">可能需要幾個小時 (，) 策略變更才能傳播。</span><span class="sxs-lookup"><span data-stu-id="a449f-295">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="a449f-296">如果您沒立即看到給定帳戶的變更，請在幾個小時後再試一次。</span><span class="sxs-lookup"><span data-stu-id="a449f-296">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="a449f-297">[**通話策略**](teams-calling-policy.md)：Teams 包含內建的 DisallowCalling 通話政策，其中會關閉所有通話功能。</span><span class="sxs-lookup"><span data-stu-id="a449f-297">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="a449f-298">將 DisallowCalling 政策指派給組織中在虛擬化環境中使用 Teams 的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="a449f-298">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="a449f-299">[**會議政策**](meeting-policies-in-teams.md)：Teams 包含內建的 AllOff 會議政策，其中所有會議功能都已關閉。</span><span class="sxs-lookup"><span data-stu-id="a449f-299">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="a449f-300">將 AllOff 政策指派給組織中在虛擬化環境中使用 Teams 的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="a449f-300">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a449f-301">使用 Microsoft Teams 系統管理中心指派政策</span><span class="sxs-lookup"><span data-stu-id="a449f-301">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="a449f-302">若要將 DisallowCalling 通話策略和 AllOff 會議策略指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="a449f-302">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="a449f-303">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **使用者**。</span><span class="sxs-lookup"><span data-stu-id="a449f-303">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="a449f-304">按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]。</span><span class="sxs-lookup"><span data-stu-id="a449f-304">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="a449f-305">請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="a449f-305">Do the following:</span></span>
    1.  <span data-ttu-id="a449f-306">在 **[通話政策中**， **Click DisallowCalling.**</span><span class="sxs-lookup"><span data-stu-id="a449f-306">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2.  <span data-ttu-id="a449f-307">在 **[會議政策>** 下，按一下 **[AllOff>**。</span><span class="sxs-lookup"><span data-stu-id="a449f-307">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="a449f-308">按一下 **[Apply.**</span><span class="sxs-lookup"><span data-stu-id="a449f-308">Click **Apply**.</span></span>

<span data-ttu-id="a449f-309">若要一次將原則指派給多位使用者：</span><span class="sxs-lookup"><span data-stu-id="a449f-309">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="a449f-310">在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="a449f-310">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="a449f-311">在 [&#x2713;] (核取方塊) 欄中，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="a449f-311">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="a449f-312">若要選取 [所有使用者]，請按一下表格頂端的 [&#x2713;] (核取方塊)。</span><span class="sxs-lookup"><span data-stu-id="a449f-312">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="a449f-313">按一下 [編輯設定]，進行所需的變更，然後按一下 [套用]。</span><span class="sxs-lookup"><span data-stu-id="a449f-313">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="a449f-314">或者，您也可以執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a449f-314">Or, you can also do the following:</span></span>

1. <span data-ttu-id="a449f-315">在 Microsoft Teams 系統管理中心的左側流覽中，前往您想要指派的政策。</span><span class="sxs-lookup"><span data-stu-id="a449f-315">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="a449f-316">例如：</span><span class="sxs-lookup"><span data-stu-id="a449f-316">For example:</span></span>
    - <span data-ttu-id="a449f-317">請前往 **[**  >  **語音通話政策**，然後按一下 **[取消禁止使用Calling>**。</span><span class="sxs-lookup"><span data-stu-id="a449f-317">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="a449f-318">前往[  >  **會議會議政策**，然後按一下 **AllOff**。</span><span class="sxs-lookup"><span data-stu-id="a449f-318">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
2. <span data-ttu-id="a449f-319">選取 [管理使用者]。</span><span class="sxs-lookup"><span data-stu-id="a449f-319">Select **Manage users**.</span></span>
3. <span data-ttu-id="a449f-320">在 [管理使用者] 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="a449f-320">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="a449f-321">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="a449f-321">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="a449f-322">新增使用者完成後，請按一下 [**儲存。**</span><span class="sxs-lookup"><span data-stu-id="a449f-322">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="a449f-323">使用 PowerShell 指派策略</span><span class="sxs-lookup"><span data-stu-id="a449f-323">Assign policies using PowerShell</span></span>

<span data-ttu-id="a449f-324">下列範例顯示如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 將 DisallowCalling 通話策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="a449f-324">The following example shows how to use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="a449f-325">若要深入瞭解使用 PowerShell 管理通話政策，請參閱 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="a449f-325">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="a449f-326">下列範例顯示如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) 將 AllOff 會議策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="a449f-326">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="a449f-327">若要深入瞭解使用 PowerShell 管理會議政策，請參閱 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="a449f-327">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a><span data-ttu-id="a449f-328">使用聊天和共同合作在 VDI 上遷移 Teams，以使用通話和會議優化 Teams</span><span class="sxs-lookup"><span data-stu-id="a449f-328">Migrate Teams on VDI with chat and collaboration to optimize Teams with calling and meetings</span></span>

<span data-ttu-id="a449f-329">如果您有在 VDI 上使用聊天和共同合作功能的現有 Teams 實現，其中您設定了使用者層級策略以關閉通話和會議功能，而且您正使用 AV 優化移轉至 Teams，則必須設定策略，為 VDI 使用者上的 Teams 開啟通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="a449f-329">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Teams with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="a449f-330">設定開啟通話和會議功能的政策</span><span class="sxs-lookup"><span data-stu-id="a449f-330">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="a449f-331">您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來設定和指派通話和會議政策給使用者。</span><span class="sxs-lookup"><span data-stu-id="a449f-331">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="a449f-332">可能需要幾個小時 (，) 策略變更才能傳播。</span><span class="sxs-lookup"><span data-stu-id="a449f-332">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="a449f-333">如果您沒立即看到給定帳戶的變更，請在幾個小時後再試一次。</span><span class="sxs-lookup"><span data-stu-id="a449f-333">If you don't see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="a449f-334">[**通話策略**](teams-calling-policy.md)：Teams 中的通話政策可控制哪些通話功能可供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="a449f-334">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="a449f-335">Teams 包含內建的 AllowCalling 通話政策，其中所有通話功能都開啟。</span><span class="sxs-lookup"><span data-stu-id="a449f-335">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="a449f-336">若要開啟所有通話功能，請指派 AllowCalling 政策。</span><span class="sxs-lookup"><span data-stu-id="a449f-336">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="a449f-337">或者，建立自訂通話策略以開啟您想要的通話功能，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="a449f-337">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span> 

<span data-ttu-id="a449f-338">[**會議政策**](meeting-policies-in-teams.md)：Teams 中的會議政策可控制使用者可以建立的會議類型，以及貴組織中使用者所排程的會議參與者可用的功能。</span><span class="sxs-lookup"><span data-stu-id="a449f-338">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="a449f-339">Teams 包含內建的 AllOn 會議政策，其中所有會議功能都開啟。</span><span class="sxs-lookup"><span data-stu-id="a449f-339">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="a449f-340">若要開啟所有會議功能，請指派 AllOn 策略。</span><span class="sxs-lookup"><span data-stu-id="a449f-340">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="a449f-341">或者，建立自訂會議策略以開啟您想要的會議功能，並指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="a449f-341">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a449f-342">使用 Microsoft Teams 系統管理中心指派政策</span><span class="sxs-lookup"><span data-stu-id="a449f-342">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="a449f-343">若要將 AllowCalling 通話策略和 AllOn 會議策略指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="a449f-343">To assign the AllowCalling calling policy and the AllOn meeting policy to a user:</span></span>

1. <span data-ttu-id="a449f-344">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **使用者**。</span><span class="sxs-lookup"><span data-stu-id="a449f-344">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="a449f-345">按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]。</span><span class="sxs-lookup"><span data-stu-id="a449f-345">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="a449f-346">請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="a449f-346">Do the following:</span></span>
    1.  <span data-ttu-id="a449f-347">在 **[通話政策>** 下，按一下 **[AllowCalling>**。</span><span class="sxs-lookup"><span data-stu-id="a449f-347">Under **Calling policy**, click **AllowCalling**.</span></span>
    2.  <span data-ttu-id="a449f-348">在 **[會議政策>** 下，按一下 **[AllOn.**</span><span class="sxs-lookup"><span data-stu-id="a449f-348">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="a449f-349">按一下 **[Apply.**</span><span class="sxs-lookup"><span data-stu-id="a449f-349">Click **Apply**.</span></span>

<span data-ttu-id="a449f-350">若要一次將原則指派給多位使用者：</span><span class="sxs-lookup"><span data-stu-id="a449f-350">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="a449f-351">在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="a449f-351">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="a449f-352">在 [&#x2713;] (核取方塊) 欄中，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="a449f-352">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="a449f-353">若要選取所有使用者，請按一下 **&#x2713;()** 表格頂端的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="a449f-353">To select all users, click the **&#x2713;** (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="a449f-354">按一下 [編輯設定]，進行所需的變更，然後按一下 [套用]。</span><span class="sxs-lookup"><span data-stu-id="a449f-354">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="a449f-355">或者，您也可以執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a449f-355">Or, you can also do the following:</span></span>

1. <span data-ttu-id="a449f-356">在 Microsoft Teams 系統管理中心的左側流覽中，前往您想要指派的政策。</span><span class="sxs-lookup"><span data-stu-id="a449f-356">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="a449f-357">例如：</span><span class="sxs-lookup"><span data-stu-id="a449f-357">For example:</span></span>
    - <span data-ttu-id="a449f-358">前往 **[語音**  >  **通話政策**，然後按一下 **AllowCalling。**</span><span class="sxs-lookup"><span data-stu-id="a449f-358">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="a449f-359">前往[  >  **會議會議政策**，然後按一下 **AllOn。**</span><span class="sxs-lookup"><span data-stu-id="a449f-359">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
2. <span data-ttu-id="a449f-360">選取 [管理使用者]。</span><span class="sxs-lookup"><span data-stu-id="a449f-360">Select **Manage users**.</span></span>
3. <span data-ttu-id="a449f-361">在 [管理使用者] 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="a449f-361">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="a449f-362">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="a449f-362">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="a449f-363">新增使用者完成後，請按一下 [**儲存。**</span><span class="sxs-lookup"><span data-stu-id="a449f-363">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="a449f-364">使用 PowerShell 指派策略</span><span class="sxs-lookup"><span data-stu-id="a449f-364">Assign policies using PowerShell</span></span>

<span data-ttu-id="a449f-365">下列範例顯示如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 將 AllowCalling 通話策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="a449f-365">The following example shows how to use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

<span data-ttu-id="a449f-366">若要深入瞭解使用 PowerShell 管理通話政策，請參閱 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="a449f-366">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="a449f-367">下列範例顯示如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) 將 AllOn 會議策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="a449f-367">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

<span data-ttu-id="a449f-368">若要深入瞭解使用 PowerShell 管理會議政策，請參閱 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="a449f-368">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="control-fallback-mode-in-teams"></a><span data-ttu-id="a449f-369">Teams 中的控制項後背模式</span><span class="sxs-lookup"><span data-stu-id="a449f-369">Control fallback mode in Teams</span></span>

<span data-ttu-id="a449f-370">當使用者從不支援的端點進行連接時，使用者會進入退後模式，而 AV 未優化。</span><span class="sxs-lookup"><span data-stu-id="a449f-370">When users connect from an unsupported endpoint, the users are in fallback mode, in which AV isn't optimized.</span></span> <span data-ttu-id="a449f-371">您可以設定下列其中一個註冊表 DWORD 值，以停用或啟用退後模式：</span><span class="sxs-lookup"><span data-stu-id="a449f-371">You can disable or enable fallback mode by setting one of the following registry DWORD values:</span></span>

- <span data-ttu-id="a449f-372">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="a449f-372">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span></span>
- <span data-ttu-id="a449f-373">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="a449f-373">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span></span>

<span data-ttu-id="a449f-374">若要停用退後模式，將值設為 **1。**</span><span class="sxs-lookup"><span data-stu-id="a449f-374">To disable fallback mode, set the value to **1**.</span></span> <span data-ttu-id="a449f-375">若要僅啟用音訊，請設定為 **2。**</span><span class="sxs-lookup"><span data-stu-id="a449f-375">To enable audio only, set the value to **2**.</span></span> <span data-ttu-id="a449f-376">如果值不存在或設為 0 (**0，)** 會啟用退後模式。</span><span class="sxs-lookup"><span data-stu-id="a449f-376">If the value isn't present or is set to **0** (zero), fallback mode is enabled.</span></span>

<span data-ttu-id="a449f-377">此功能可在 Teams 版本 1.3.00.13565 及更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="a449f-377">This feature is available in Teams version 1.3.00.13565 and later.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="a449f-378">已知問題和限制</span><span class="sxs-lookup"><span data-stu-id="a449f-378">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="a449f-379">用戶端部署、安裝和設定</span><span class="sxs-lookup"><span data-stu-id="a449f-379">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="a449f-380">每部電腦安裝時，VDI 上的 Teams 不會以非 VDI Teams 用戶端的方式自動更新。</span><span class="sxs-lookup"><span data-stu-id="a449f-380">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="a449f-381">您必須安裝新的 MSI 以更新 VM 映射，如在 [VDI](#install-or-update-the-teams-desktop-app-on-vdi) 上安裝或更新 Teams 桌面應用程式一節中所述。</span><span class="sxs-lookup"><span data-stu-id="a449f-381">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="a449f-382">您必須卸載目前的版本，以更新至較新版本。</span><span class="sxs-lookup"><span data-stu-id="a449f-382">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="a449f-383">團隊應該會以每個使用者或每部電腦部署。</span><span class="sxs-lookup"><span data-stu-id="a449f-383">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="a449f-384">不支援針對每個使用者和每部電腦同時部署 Teams。</span><span class="sxs-lookup"><span data-stu-id="a449f-384">Deployment of Teams for concurrent per user and per machine is not supported.</span></span> <span data-ttu-id="a449f-385">若要從每部電腦或每個使用者遷移到其中一種模式，請遵循卸載程式，然後重新調配至任一模式。</span><span class="sxs-lookup"><span data-stu-id="a449f-385">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="a449f-386">Windows 虛擬桌面和 V Linux 目前不支援 MacOS 和 Linux 型用戶端。</span><span class="sxs-lookup"><span data-stu-id="a449f-386">Windows Virtual Desktop and VMware don't support MacOS and Linux-based clients at this time.</span></span>
- <span data-ttu-id="a449f-387">目前，系統不支援 MacOs 用戶端。</span><span class="sxs-lookup"><span data-stu-id="a449f-387">Citrix doesn't support MacOs clients at this time.</span></span>
- <span data-ttu-id="a449f-388">奇特克斯不支援使用在端點上定義的明確 HTTP 代理。</span><span class="sxs-lookup"><span data-stu-id="a449f-388">Citrix doesn't support the use of explicit HTTP proxies defined on an endpoint.</span></span>

### <a name="calling-and-meetings"></a><span data-ttu-id="a449f-389">通話和會議</span><span class="sxs-lookup"><span data-stu-id="a449f-389">Calling and meetings</span></span>

<span data-ttu-id="a449f-390">不支援下列通話和會議功能：</span><span class="sxs-lookup"><span data-stu-id="a449f-390">The following calling and meeting features are not supported:</span></span>

- <span data-ttu-id="a449f-391">任何多視窗功能，例如新的會議體驗或任何新會議體驗隨附的功能</span><span class="sxs-lookup"><span data-stu-id="a449f-391">Any multi-window functionality like the new meeting experiences or any functionality that comes with the new meeting experience</span></span>
- <span data-ttu-id="a449f-392">增強的緊急服務</span><span class="sxs-lookup"><span data-stu-id="a449f-392">Enhanced emergency services</span></span>
- <span data-ttu-id="a449f-393">Teams 應用程式與裝置之間的 HID 按鈕和 LED 控制項</span><span class="sxs-lookup"><span data-stu-id="a449f-393">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="a449f-394">背景模糊和效果</span><span class="sxs-lookup"><span data-stu-id="a449f-394">Background blur and effects</span></span>
- <span data-ttu-id="a449f-395">廣播和即時活動製作人及簡報者角色</span><span class="sxs-lookup"><span data-stu-id="a449f-395">Broadcast and live event producer and presenter roles</span></span>
- <span data-ttu-id="a449f-396">Location-Based LBR (路由) </span><span class="sxs-lookup"><span data-stu-id="a449f-396">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="a449f-397">通話停駐</span><span class="sxs-lookup"><span data-stu-id="a449f-397">Call park</span></span>
- <span data-ttu-id="a449f-398">通話佇列</span><span class="sxs-lookup"><span data-stu-id="a449f-398">Call queue</span></span>
- <span data-ttu-id="a449f-399">共用系統音訊/電腦音效</span><span class="sxs-lookup"><span data-stu-id="a449f-399">Shared system audio/computer sound</span></span>
- <span data-ttu-id="a449f-400">直接路由的媒體旁路</span><span class="sxs-lookup"><span data-stu-id="a449f-400">Media bypass for Direct Routing</span></span>

> [!NOTE]
> <span data-ttu-id="a449f-401">我們正在努力新增目前僅適用于非 VDI 環境的通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="a449f-401">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="a449f-402">這些可能包括對品質的更多系統管理員控制、其他螢幕共用案例，以及最近新加入 Teams 的進一步功能。</span><span class="sxs-lookup"><span data-stu-id="a449f-402">These might include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="a449f-403">請與您的 Teams 代表聯繫，以深入瞭解即將推出的功能。</span><span class="sxs-lookup"><span data-stu-id="a449f-403">Contact your Teams representative to learn more about upcoming features.</span></span>

<span data-ttu-id="a449f-404">以下是通話和會議的已知問題和限制：</span><span class="sxs-lookup"><span data-stu-id="a449f-404">The following are known issues and limitations for calling and meetings:</span></span>

- <span data-ttu-id="a449f-405">商務用 Skype 的互通性僅限於音訊通話;沒有視音訊模式。</span><span class="sxs-lookup"><span data-stu-id="a449f-405">Interoperability with Skype for Business is limited to audio calls; there is no video modality.</span></span>
- <span data-ttu-id="a449f-406">會議或群組通話中僅支援單一傳入視音訊流。</span><span class="sxs-lookup"><span data-stu-id="a449f-406">Only a single incoming video stream is supported in meetings or group calls.</span></span> <span data-ttu-id="a449f-407">當多人傳送視音訊時，任何時間只會顯示主要演講者的視像。</span><span class="sxs-lookup"><span data-stu-id="a449f-407">When multiple people send video, only the dominant speaker's video is shown at any given time.</span></span>
- <span data-ttu-id="a449f-408">傳入和傳出視音訊串流解析度限制為 720p 解析度。</span><span class="sxs-lookup"><span data-stu-id="a449f-408">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span> <span data-ttu-id="a449f-409">這是 WebRTC 限制。</span><span class="sxs-lookup"><span data-stu-id="a449f-409">This is a WebRTC limitation.</span></span>
- <span data-ttu-id="a449f-410">僅支援來自內接相機或螢幕共用流的一個視音訊流。</span><span class="sxs-lookup"><span data-stu-id="a449f-410">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="a449f-411">當有傳入的螢幕共用時，畫面共用會顯示，而不是主要喇叭的視像。</span><span class="sxs-lookup"><span data-stu-id="a449f-411">When there's an incoming screen share, that screen share is shown, instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="a449f-412">如果裝置已中斷連接，然後重新連接，Teams 不會切換到使用使用者選取的最後一個音訊裝置。</span><span class="sxs-lookup"><span data-stu-id="a449f-412">Teams doesn't switch to use the last audio device that a user selected, if the device is disconnected, and then reconnected.</span></span>
- <span data-ttu-id="a449f-413">外發畫面共用：</span><span class="sxs-lookup"><span data-stu-id="a449f-413">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="a449f-414">不支援應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="a449f-414">Application sharing is not supported.</span></span>
- <span data-ttu-id="a449f-415">提供控制權並控制：</span><span class="sxs-lookup"><span data-stu-id="a449f-415">Give control and take control:</span></span>
    - <span data-ttu-id="a449f-416">在螢幕共用或應用程式共用會話期間不支援。</span><span class="sxs-lookup"><span data-stu-id="a449f-416">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="a449f-417">在 PowerPoint 共用會話期間支援。</span><span class="sxs-lookup"><span data-stu-id="a449f-417">Supported during a PowerPoint sharing session.</span></span>
- <span data-ttu-id="a449f-418">僅以黃水晶為限的限制</span><span class="sxs-lookup"><span data-stu-id="a449f-418">Citrix-only limitations</span></span>
    - <span data-ttu-id="a449f-419">在多監視器設定中共用螢幕時，只會共用主監視器。</span><span class="sxs-lookup"><span data-stu-id="a449f-419">When screen sharing in a multi-monitor setup, only the main monitor is shared.</span></span>
    - <span data-ttu-id="a449f-420">不支援 CWA 上的高 DPI 縮放比例。</span><span class="sxs-lookup"><span data-stu-id="a449f-420">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="a449f-421">針對與 VDI 不相關的 Teams 已知問題，請參閱 [貴組織的支援小組](/MicrosoftTeams/troubleshoot/teams-welcome)。</span><span class="sxs-lookup"><span data-stu-id="a449f-421">For Teams known issues that aren't related to VDI, see [Support Teams in your organization](/MicrosoftTeams/troubleshoot/teams-welcome).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a449f-422">疑難排解</span><span class="sxs-lookup"><span data-stu-id="a449f-422">Troubleshooting</span></span>

### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="a449f-423">疑難排解黃水晶元件</span><span class="sxs-lookup"><span data-stu-id="a449f-423">Troubleshoot Citrix components</span></span>

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a><span data-ttu-id="a449f-424">Teams 當機或 Teams 的登錄畫面為空白</span><span class="sxs-lookup"><span data-stu-id="a449f-424">Teams crashes or the Teams sign in screen is blank</span></span>

<span data-ttu-id="a449f-425">這是關於 1906 和 1909 的 Citrix VDA 版本已知問題。</span><span class="sxs-lookup"><span data-stu-id="a449f-425">This is a known issue with Citrix VDA versions 1906 and 1909.</span></span> <span data-ttu-id="a449f-426">若要解決此問題，請新增下列註冊表 DWORD 值，並設定為 204 (十六進位) 。</span><span class="sxs-lookup"><span data-stu-id="a449f-426">To work around this issue, add the following registry DWORD value, and set it to 204 (hexadecimal).</span></span>

<span data-ttu-id="a449f-427">HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe</span><span class="sxs-lookup"><span data-stu-id="a449f-427">HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe</span></span>

<span data-ttu-id="a449f-428">接著，重新開機 VDA。</span><span class="sxs-lookup"><span data-stu-id="a449f-428">Then, restart VDA.</span></span> <span data-ttu-id="a449f-429">若要深入瞭解，請參閱此關於 Teams HDX 優化的疑難排解的此 [Citrix 支援文章](https://support.citrix.com/article/CTX253754)。</span><span class="sxs-lookup"><span data-stu-id="a449f-429">To learn more, see this Citrix support article, [Troubleshooting HDX optimization for Teams](https://support.citrix.com/article/CTX253754).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a449f-430">相關主題</span><span class="sxs-lookup"><span data-stu-id="a449f-430">Related topics</span></span>

- [<span data-ttu-id="a449f-431">使用 MSI 安裝 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a449f-431">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="a449f-432">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="a449f-432">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="a449f-433">在 Windows 虛擬桌面使用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a449f-433">Use Microsoft Teams on Windows Virtual desktop</span></span>](/azure/virtual-desktop/teams-on-wvd)
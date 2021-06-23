---
title: 適用於虛擬桌面架構的 Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: 瞭解如何在虛擬桌面基礎結構Microsoft Teams虛擬桌面基礎結構 (VDI) 執行。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6eba4f1da849a2cf8e355454fd1ba794a3496db
ms.sourcegitcommit: cae94cd5761baafde51aea1137e6d164722eead9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53075386"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="af134-103">適用於虛擬桌面架構的 Teams</span><span class="sxs-lookup"><span data-stu-id="af134-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="af134-104">本文將說明在虛擬化環境中使用Microsoft Teams的需求和限制。</span><span class="sxs-lookup"><span data-stu-id="af134-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="af134-105">什麼是 VDI？</span><span class="sxs-lookup"><span data-stu-id="af134-105">What is VDI?</span></span>

<span data-ttu-id="af134-106">虛擬桌面基礎結構 (VDI) 是虛擬化技術，在資料中心集中式伺服器上託管桌面作業系統和應用程式。</span><span class="sxs-lookup"><span data-stu-id="af134-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="af134-107">這可讓擁有完整安全且合規性集中式來源的使用者獲得完全個人化的桌面體驗。</span><span class="sxs-lookup"><span data-stu-id="af134-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>

<span data-ttu-id="af134-108">Microsoft Teams環境中，支援聊天和共同合作。</span><span class="sxs-lookup"><span data-stu-id="af134-108">Microsoft Teams in a virtualized environment supports chat and collaboration.</span></span> <span data-ttu-id="af134-109">此外，Windows虛擬桌面、Citrix 和 V3 平臺，通話和會議功能也受到支援。</span><span class="sxs-lookup"><span data-stu-id="af134-109">And with the Windows Virtual Desktop, Citrix, and VMware platforms, calling and meeting functionality is also supported.</span></span>

<span data-ttu-id="af134-110">Teams環境中，系統支援多個配置。</span><span class="sxs-lookup"><span data-stu-id="af134-110">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="af134-111">這些包括 VDI、專用、共用、永久和非持續性模式。</span><span class="sxs-lookup"><span data-stu-id="af134-111">These include VDI, dedicated, shared, persistent, and non-persistent modes.</span></span> <span data-ttu-id="af134-112">功能正在持續開發中，並且會定期新增，且功能將會于未來幾個月和數年內擴充。</span><span class="sxs-lookup"><span data-stu-id="af134-112">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>

<span data-ttu-id="af134-113">在Teams環境中使用應用程式可能與在非虛擬化Teams環境中使用應用程式稍有不同。</span><span class="sxs-lookup"><span data-stu-id="af134-113">Using Teams in a virtualized environment might be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="af134-114">例如，某些進位功能可能無法在虛擬化環境中使用，而且視像解析度可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="af134-114">For example, some advanced features might not be available in a virtualized environment, and video resolution might differ.</span></span>

<span data-ttu-id="af134-115">若要確保最佳的使用者體驗，請遵循本文中的指引。</span><span class="sxs-lookup"><span data-stu-id="af134-115">To ensure an optimal user experience, follow the guidance in this article.</span></span>

> [!Note]
> <span data-ttu-id="af134-116">有關在不同平臺上Teams VDI 的詳細資訊，請參閱[Teams功能。](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)</span><span class="sxs-lookup"><span data-stu-id="af134-116">For details about Teams VDI on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="af134-117">Teams VDI 元件上的</span><span class="sxs-lookup"><span data-stu-id="af134-117">Teams on VDI components</span></span>

<span data-ttu-id="af134-118">在Teams環境中使用應用程式需要下列元件。</span><span class="sxs-lookup"><span data-stu-id="af134-118">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="af134-119">**虛擬化代理**：虛擬化提供者的資源和連接管理員，例如 Azure</span><span class="sxs-lookup"><span data-stu-id="af134-119">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="af134-120">**虛擬桌面**：虛擬機器 (虛擬機器) 堆疊Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="af134-120">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="af134-121">**精簡用戶端**：使用者實際介面的端點</span><span class="sxs-lookup"><span data-stu-id="af134-121">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="af134-122">**Teams桌面應用程式**：Teams桌面用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="af134-122">**Teams desktop app**: The Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="af134-123">Teams VDI 需求</span><span class="sxs-lookup"><span data-stu-id="af134-123">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="af134-124">虛擬化提供者需求</span><span class="sxs-lookup"><span data-stu-id="af134-124">Virtualization provider requirements</span></span>

<span data-ttu-id="af134-125">桌面Teams已與領先虛擬化解決方案提供者驗證。</span><span class="sxs-lookup"><span data-stu-id="af134-125">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="af134-126">對於多個市場提供者，我們建議您諮詢您的虛擬化解決方案提供者，以確保您符合最低需求。</span><span class="sxs-lookup"><span data-stu-id="af134-126">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure that you meet the minimum requirements.</span></span>
  
<span data-ttu-id="af134-127">目前，Teams視音訊/視 (AV) 的 VDI Windows虛擬桌面、Citrix 和 V Azure 通過認證。</span><span class="sxs-lookup"><span data-stu-id="af134-127">Currently, Teams on VDI with audio/video (AV) optimization is certified with Windows Virtual Desktop, Citrix, and VMware.</span></span> <span data-ttu-id="af134-128">請閱閱本節的資訊，以確保您符合正確功能的所有需求。</span><span class="sxs-lookup"><span data-stu-id="af134-128">Review the information in this section to ensure that you meet all requirements for proper functionality.</span></span>

### <a name="platforms-certified-for-teams"></a><span data-ttu-id="af134-129">平臺已Teams</span><span class="sxs-lookup"><span data-stu-id="af134-129">Platforms certified for Teams</span></span>

<span data-ttu-id="af134-130">下列平臺提供適用于 Teams 的虛擬桌面Teams。</span><span class="sxs-lookup"><span data-stu-id="af134-130">The following platforms have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="af134-131">平台</span><span class="sxs-lookup"><span data-stu-id="af134-131">Platform</span></span>|<span data-ttu-id="af134-132">解決 方案</span><span class="sxs-lookup"><span data-stu-id="af134-132">Solution</span></span>|
|----|---|
|![代表 Microsoft 的標誌](media/microsoft-logo.png)| <span data-ttu-id="af134-134"><a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows虛擬桌面</a></span><span class="sxs-lookup"><span data-stu-id="af134-134"><a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows Virtual Desktop</a></span></span> |
|![代表 Citrix 的標誌](media/citrix-logo.png)| <span data-ttu-id="af134-136"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 虛擬應用程式與桌面</a></span><span class="sxs-lookup"><span data-stu-id="af134-136"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |
|![代表 VMware 的標誌](media/vmware-logo.png)| <span data-ttu-id="af134-138"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a></span><span class="sxs-lookup"><span data-stu-id="af134-138"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a></span></span> |

### <a name="windows-virtual-desktop"></a><span data-ttu-id="af134-139">Windows虛擬桌面</span><span class="sxs-lookup"><span data-stu-id="af134-139">Windows Virtual Desktop</span></span>

<span data-ttu-id="af134-140">Windows虛擬桌面提供 VDI Teams AV 優化。</span><span class="sxs-lookup"><span data-stu-id="af134-140">Windows Virtual Desktop provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="af134-141">若要深入瞭解及需求及安裝，請參閱在虛擬桌面Teams[使用Windows程式](/azure/virtual-desktop/teams-on-wvd)。</span><span class="sxs-lookup"><span data-stu-id="af134-141">To learn more and requirements and installation, see [Use Teams on Windows Virtual Desktop](/azure/virtual-desktop/teams-on-wvd).</span></span>

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="af134-142">Citrix 虛擬應用程式與桌面需求</span><span class="sxs-lookup"><span data-stu-id="af134-142">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="af134-143">在 VDI 上 (XenApp 和 XenDesktop) 提供視Teams優化。</span><span class="sxs-lookup"><span data-stu-id="af134-143">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="af134-144">有了 Citrix 虛擬 App 和桌面Teams，VDI 上除了聊天和共同合作之外，還支援通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="af134-144">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="af134-145">您可以在 Citrix 下載網站下載最新版本的 [Citrix](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)虛擬 App 和桌面。</span><span class="sxs-lookup"><span data-stu-id="af134-145">You can download the latest version of Citrix Virtual Apps and Desktops at [the Citrix downloads site](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="af134-146"> (您必須先登錄。) 根據預設，必要元件會套件到 [Citrix Workspace 應用程式 (CWA) ](https://www.citrix.com/downloads/workspace-app/) 和虛擬傳遞代理程式 (VDA) 。</span><span class="sxs-lookup"><span data-stu-id="af134-146">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="af134-147">您不需要在 CWA 或 VDA 上安裝任何其他元件或外掛程式。</span><span class="sxs-lookup"><span data-stu-id="af134-147">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="af134-148">有關最新的伺服器和用戶端需求，請參閱 [此 Citrix 網站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。</span><span class="sxs-lookup"><span data-stu-id="af134-148">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a><span data-ttu-id="af134-149">VMware Horizon Workspace 和桌面需求</span><span class="sxs-lookup"><span data-stu-id="af134-149">VMware Horizon Workspace and Desktop requirements</span></span>

<span data-ttu-id="af134-150">V Azure Horizon 是一個現代化平臺，可安全地跨混合式雲端傳遞虛擬桌面和應用程式。</span><span class="sxs-lookup"><span data-stu-id="af134-150">VMware Horizon is a modern platform for secure delivery of virtual desktops and apps across the hybrid cloud.</span></span> <span data-ttu-id="af134-151">為了提供出色的使用者體驗，V3 Horizon 提供適用于使用者的媒體優化Teams。</span><span class="sxs-lookup"><span data-stu-id="af134-151">To offer a great end-user experience, VMware Horizon provides media optimization for Teams.</span></span> <span data-ttu-id="af134-152">這項優化可改善虛擬桌面和應用程式的整體生產力，並增強使用 Teams 通話和會議時Teams。</span><span class="sxs-lookup"><span data-stu-id="af134-152">This optimization improves overall productivity across virtual desktops and apps, and enhances user experience when calling and meeting using Teams.</span></span>

<span data-ttu-id="af134-153">您可以從 V 試用版下載頁面下載[最新版本的 V3 Horizon。](https://my.vmware.com/web/vmware/downloads/#all_products)</span><span class="sxs-lookup"><span data-stu-id="af134-153">You can download the latest version of VMware Horizon from the [VMware Downloads](https://my.vmware.com/web/vmware/downloads/#all_products) page.</span></span> <span data-ttu-id="af134-154">根據預設，所需的媒體優化元件是 Horizon Agent 和 Horizon Client 的一部分，因此不需要安裝任何其他外掛程式，以使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="af134-154">The required media optimization components are part of the Horizon Agent and Horizon Client by default and there's no need to install any additional plug-in to use the optimization feature for Teams.</span></span>

<span data-ttu-id="af134-155">若要取得有關如何設定媒體優化功能的最新需求Teams指示，請參閱[此 V3 網站](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)。</span><span class="sxs-lookup"><span data-stu-id="af134-155">To get the latest requirements and instructions on how to configure media optimization for Teams, see [this VMware website](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html).</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="af134-156">在 VDI 上Teams或更新桌面應用程式</span><span class="sxs-lookup"><span data-stu-id="af134-156">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="af134-157">您可以使用每Teams安裝或使用 MSI 套件的每個使用者安裝來部署適用于 VDI 的桌面應用程式。</span><span class="sxs-lookup"><span data-stu-id="af134-157">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="af134-158">決定使用哪種方法取決於您是使用永久或非持續性設定，以及貴組織的相關功能需求。</span><span class="sxs-lookup"><span data-stu-id="af134-158">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>

<span data-ttu-id="af134-159">對於專用的永久設定，任一方法都適合使用。</span><span class="sxs-lookup"><span data-stu-id="af134-159">For a dedicated persistent setup, either approach would work.</span></span> <span data-ttu-id="af134-160">不過，對於非持續性設定，Teams需要每部電腦安裝，才能有效率地運作。</span><span class="sxs-lookup"><span data-stu-id="af134-160">However, for a non-persistent setup, Teams requires a per-machine installation in order to work efficiently.</span></span> <span data-ttu-id="af134-161">請參閱 [非持續性設定一](#non-persistent-setup) 節。</span><span class="sxs-lookup"><span data-stu-id="af134-161">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="af134-162">使用每部電腦安裝時，自動更新會停用。</span><span class="sxs-lookup"><span data-stu-id="af134-162">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="af134-163">這表示若要更新 Teams應用程式，您必須卸載目前的版本，以更新至較新版本。</span><span class="sxs-lookup"><span data-stu-id="af134-163">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="af134-164">在每個使用者安裝時，自動更新會啟用。</span><span class="sxs-lookup"><span data-stu-id="af134-164">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="af134-165">針對大部分的 VDI 部署，建議您使用Teams部署。</span><span class="sxs-lookup"><span data-stu-id="af134-165">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="af134-166">若要更新至最新版本Teams，請先卸載程式，Teams版本部署。</span><span class="sxs-lookup"><span data-stu-id="af134-166">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="af134-167">若要Teams VDI 環境中進行 AV 優化，精簡用戶端端點必須能夠存取網際網路。</span><span class="sxs-lookup"><span data-stu-id="af134-167">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="af134-168">如果精簡用戶端端點無法存取網際網路，優化啟動將不會成功。</span><span class="sxs-lookup"><span data-stu-id="af134-168">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="af134-169">這表示使用者是未優化的媒體狀態。</span><span class="sxs-lookup"><span data-stu-id="af134-169">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="af134-170">專用永久設定</span><span class="sxs-lookup"><span data-stu-id="af134-170">Dedicated persistent setup</span></span>

<span data-ttu-id="af134-171">在專用的永久設定中，使用者登出後會保留使用者的當地作業系統變更。</span><span class="sxs-lookup"><span data-stu-id="af134-171">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span> <span data-ttu-id="af134-172">針對持續性設定，Teams使用者和每部電腦安裝。</span><span class="sxs-lookup"><span data-stu-id="af134-172">For persistent setup, Teams supports both per-user and per-machine installation.</span></span>

<span data-ttu-id="af134-173">以下是建議的最小值 VM 組組。</span><span class="sxs-lookup"><span data-stu-id="af134-173">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="af134-174">參數</span><span class="sxs-lookup"><span data-stu-id="af134-174">Parameter</span></span>  |<span data-ttu-id="af134-175">工作站作業系統</span><span class="sxs-lookup"><span data-stu-id="af134-175">Workstation operating system</span></span>  |<span data-ttu-id="af134-176">伺服器作業系統</span><span class="sxs-lookup"><span data-stu-id="af134-176">Server operating system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="af134-177">vCPU</span><span class="sxs-lookup"><span data-stu-id="af134-177">vCPU</span></span>   |    <span data-ttu-id="af134-178">2 個核心</span><span class="sxs-lookup"><span data-stu-id="af134-178">2 cores</span></span>     |  <span data-ttu-id="af134-179">4、6 或 8</span><span class="sxs-lookup"><span data-stu-id="af134-179">4,6, or 8</span></span><br><span data-ttu-id="af134-180">瞭解 NUMA (基本非統一) 存取權，並據此設定您的虛擬機器非常重要。</span><span class="sxs-lookup"><span data-stu-id="af134-180">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="af134-181">RAM</span><span class="sxs-lookup"><span data-stu-id="af134-181">RAM</span></span>     |   <span data-ttu-id="af134-182">4 GB</span><span class="sxs-lookup"><span data-stu-id="af134-182">4 GB</span></span>      | <span data-ttu-id="af134-183">每個使用者 512 到 1024 MB</span><span class="sxs-lookup"><span data-stu-id="af134-183">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="af134-184">儲存空間</span><span class="sxs-lookup"><span data-stu-id="af134-184">Storage</span></span>    | <span data-ttu-id="af134-185">8 GB</span><span class="sxs-lookup"><span data-stu-id="af134-185">8 GB</span></span>        | <span data-ttu-id="af134-186">40 到 60 GB</span><span class="sxs-lookup"><span data-stu-id="af134-186">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="af134-187">非持續性設定</span><span class="sxs-lookup"><span data-stu-id="af134-187">Non-persistent setup</span></span>

<span data-ttu-id="af134-188">在非持續性設定中，使用者登出後不會保留使用者的當地作業系統變更。</span><span class="sxs-lookup"><span data-stu-id="af134-188">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="af134-189">這類設定是一般共用的多使用者會話。</span><span class="sxs-lookup"><span data-stu-id="af134-189">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="af134-190">VM 組式會依據使用者數量和可用的實體方塊資源而不同。</span><span class="sxs-lookup"><span data-stu-id="af134-190">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="af134-191">對於非持續性設定，Teams桌面應用程式必須每部電腦安裝至金色影像。</span><span class="sxs-lookup"><span data-stu-id="af134-191">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="af134-192"> (若要深入瞭解，請參閱在[VDI](#install-or-update-the-teams-desktop-app-on-vdi)上安裝或更新 Teams 桌面應用程式一節。) 這可確保在使用者會話期間有效率地啟動 Teams 應用程式。</span><span class="sxs-lookup"><span data-stu-id="af134-192">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.) This ensures an efficient launch of the Teams app during a user session.</span></span>

<span data-ttu-id="af134-193">在Teams設定中使用資料庫也需要設定檔-緩存管理員，Teams執行時間資料同步處理。</span><span class="sxs-lookup"><span data-stu-id="af134-193">Using Teams in a non-persistent setup also requires a profile-caching manager, for efficient Teams runtime data synchronization.</span></span> <span data-ttu-id="af134-194">有效的資料同步處理可確保在使用者的會話 (，例如使用者的資料、設定檔或設定等適當的使用者) 資訊。</span><span class="sxs-lookup"><span data-stu-id="af134-194">Efficient data synchronization ensures that the appropriate user-specific information (such as a user's data, profile, or settings) is cached during the user's session.</span></span> <span data-ttu-id="af134-195">確認這兩個資料夾中的資料已同步處理：</span><span class="sxs-lookup"><span data-stu-id="af134-195">Make sure data in these two folders are synched:</span></span><br>
- <span data-ttu-id="af134-196">C：\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache) </span><span class="sxs-lookup"><span data-stu-id="af134-196">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span></span>
- <span data-ttu-id="af134-197">C：\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams) </span><span class="sxs-lookup"><span data-stu-id="af134-197">C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)</span></span>

> [!NOTE]
> <span data-ttu-id="af134-198">漫遊資料夾 (，或者如果您使用的是資料夾重新導向，則需要快用管理員) 才能確保 Teams 應用程式具有執行應用程式所需的執行時間資料和檔案。</span><span class="sxs-lookup"><span data-stu-id="af134-198">A roaming folder (or, if you are using folder redirection, a caching manager) is required to ensure that the Teams app has the runtime data and files required to run the application.</span></span> <span data-ttu-id="af134-199">這是為了減輕網路延遲問題或網路問題所必須的，否則會造成應用程式錯誤，以及因無法使用的資料和檔案而造成緩慢的體驗。</span><span class="sxs-lookup"><span data-stu-id="af134-199">This is necessary to mitigate network latency issues or network glitches, which would otherwise cause application errors and a slow experience due to unavailable data and files.</span></span>

<span data-ttu-id="af134-200">有許多可用的緩存管理員解決方案。</span><span class="sxs-lookup"><span data-stu-id="af134-200">There are a variety of caching manager solutions available.</span></span> <span data-ttu-id="af134-201">例如 [，FSLogix](/fslogix/overview)。</span><span class="sxs-lookup"><span data-stu-id="af134-201">For example, [FSLogix](/fslogix/overview).</span></span> <span data-ttu-id="af134-202">請參閱您的緩存管理員提供者，以獲得特定組組指示。</span><span class="sxs-lookup"><span data-stu-id="af134-202">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="af134-203">Teams非持續性設定之緩存內容排除清單</span><span class="sxs-lookup"><span data-stu-id="af134-203">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="af134-204">將下列專案排除在 Teams 資料夾 、%appdata%/Microsoft/Teams。</span><span class="sxs-lookup"><span data-stu-id="af134-204">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span> <span data-ttu-id="af134-205">排除這些專案有助於減少使用者緩存大小，進一步優化非持續性設定。</span><span class="sxs-lookup"><span data-stu-id="af134-205">Excluding these items helps reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="af134-206">.txt檔案</span><span class="sxs-lookup"><span data-stu-id="af134-206">.txt files</span></span>
- <span data-ttu-id="af134-207">媒體堆疊資料夾</span><span class="sxs-lookup"><span data-stu-id="af134-207">Media-stack folder</span></span>
- <span data-ttu-id="af134-208">會議-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache) </span><span class="sxs-lookup"><span data-stu-id="af134-208">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)</span></span>

### <a name="microsoft-365-apps-for-enterprise-considerations"></a><span data-ttu-id="af134-209">Microsoft 365 Apps 企業版考慮</span><span class="sxs-lookup"><span data-stu-id="af134-209">Microsoft 365 Apps for enterprise considerations</span></span>

<span data-ttu-id="af134-210">當您在 VDI 上使用 Teams 部署Microsoft 365 Apps 企業版請考慮下列事項。</span><span class="sxs-lookup"><span data-stu-id="af134-210">Consider the following when you deploy Teams with Microsoft 365 Apps for enterprise on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="af134-211">新部署Teams到Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="af134-211">New deployments of Teams through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="af134-212">在透過 Teams部署Microsoft 365 Apps 企業版，您必須先卸載任何預先Teams應用程式 ，如果他們是使用每部電腦安裝進行部署。</span><span class="sxs-lookup"><span data-stu-id="af134-212">Before you deploy Teams through Microsoft 365 Apps for enterprise, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="af134-213">Teams每個Microsoft 365 Apps 企業版安裝一次。</span><span class="sxs-lookup"><span data-stu-id="af134-213">Teams through Microsoft 365 Apps for enterprise is installed per-user.</span></span> <span data-ttu-id="af134-214">若要深入瞭解，請參閱在[VDI 上安裝Teams更新桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi)一節。</span><span class="sxs-lookup"><span data-stu-id="af134-214">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a><span data-ttu-id="af134-215">Teams更新來Microsoft 365 Apps 企業版部署</span><span class="sxs-lookup"><span data-stu-id="af134-215">Teams deployments through Microsoft 365 Apps for enterprise updates</span></span>

<span data-ttu-id="af134-216">Teams也會新增到現有的 Microsoft 365 Apps 企業版。</span><span class="sxs-lookup"><span data-stu-id="af134-216">Teams is also being added to existing installations of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="af134-217">由於Microsoft 365 Apps 企業版使用者Teams安裝，請參閱在[VDI](#install-or-update-the-teams-desktop-app-on-vdi)上安裝或Teams桌面應用程式>一節。</span><span class="sxs-lookup"><span data-stu-id="af134-217">Since Microsoft 365 Apps for enterprise installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="af134-218">使用Teams機器安裝及Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="af134-218">Using Teams with per-machine installation and Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="af134-219">Microsoft 365 Apps 企業版不支援每部電腦安裝 Teams。</span><span class="sxs-lookup"><span data-stu-id="af134-219">Microsoft 365 Apps for enterprise doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="af134-220">若要使用每部電腦安裝，您必須將Teams排除Microsoft 365 Apps 企業版。</span><span class="sxs-lookup"><span data-stu-id="af134-220">To use per-machine installation, you must exclude Teams from Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="af134-221">請參閱[將桌面Teams應用程式部署到虛擬機器](#deploy-the-teams-desktop-app-to-the-vm)，以及如何透過[Teams>節Microsoft 365 Apps 企業版](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise)部署。</span><span class="sxs-lookup"><span data-stu-id="af134-221">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Microsoft 365 Apps for enterprise](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="af134-222">如何透過Teams排除Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="af134-222">How to exclude Teams deployment through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="af134-223">若要深入瞭解 Teams 和 Microsoft 365 Apps 企業版，請參閱如何將 Teams 排除在 Microsoft 365 Apps 企業版 的新安裝中[，](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus)以及使用群組原則來控制[Teams。](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="af134-223">To learn more about Teams and Microsoft 365 Apps for enterprise, see [How to exclude Teams from new installations of Microsoft 365 Apps for enterprise](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="af134-224">將桌面Teams應用程式部署到虛擬機器</span><span class="sxs-lookup"><span data-stu-id="af134-224">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="af134-225">使用下列Teams之一下載符合 VDI VM 作業系統的 MSI 套件：</span><span class="sxs-lookup"><span data-stu-id="af134-225">Download the Teams MSI package that matches your VDI VM operating system using one of the following links:</span></span>

    - [<span data-ttu-id="af134-226">32 位版本</span><span class="sxs-lookup"><span data-stu-id="af134-226">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [<span data-ttu-id="af134-227">64 位版本</span><span class="sxs-lookup"><span data-stu-id="af134-227">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > <span data-ttu-id="af134-228">有關政府雲端，請參閱使用 Microsoft Teams[安裝Microsoft Endpoint Configuration Manager](msi-deployment.md)以下載 MSI 檔案的連結。</span><span class="sxs-lookup"><span data-stu-id="af134-228">For government clouds, see [Install Microsoft Teams using Microsoft Endpoint Configuration Manager](msi-deployment.md) for the download links to the MSI files.</span></span>

    <span data-ttu-id="af134-229">桌面應用程式的最低Teams版本為版本 1.3.00.4461。</span><span class="sxs-lookup"><span data-stu-id="af134-229">The minimum version of the Teams desktop app that's required is version 1.3.00.4461.</span></span> <span data-ttu-id="af134-230"> (版本不支援 PSTN 保留) </span><span class="sxs-lookup"><span data-stu-id="af134-230">(PSTN hold isn't supported in earlier versions.)</span></span>

2. <span data-ttu-id="af134-231">執行下列其中一個命令，將 MSI 安裝到 VDI VM：</span><span class="sxs-lookup"><span data-stu-id="af134-231">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="af134-232">每個使用者安裝 (預設) </span><span class="sxs-lookup"><span data-stu-id="af134-232">Per-user installation (default)</span></span>
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        <span data-ttu-id="af134-233">此程式是預設安裝，Teams %AppData% 使用者資料夾。</span><span class="sxs-lookup"><span data-stu-id="af134-233">This process is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="af134-234">此時，金色影像設定已完成。</span><span class="sxs-lookup"><span data-stu-id="af134-234">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="af134-235">Teams非持續性設定上的每個使用者安裝無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="af134-235">Teams won't work properly with per-user installation on a non-persistent setup.</span></span>

    - <span data-ttu-id="af134-236">每部電腦安裝</span><span class="sxs-lookup"><span data-stu-id="af134-236">Per-machine installation</span></span>

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```
        <span data-ttu-id="af134-237">此程式會新增必要的登錄機碼至電腦，讓安裝程式Teams知道它是 VDI 實例。</span><span class="sxs-lookup"><span data-stu-id="af134-237">This process adds a required registry key to the machine that lets the Teams installer know it is a VDI instance.</span></span>  <span data-ttu-id="af134-238">如果沒有安裝，安裝程式就會發生錯誤，指出：「安裝失敗。</span><span class="sxs-lookup"><span data-stu-id="af134-238">Without it, the installer will error out, stating: "Installation has failed.</span></span>  <span data-ttu-id="af134-239">當未偵測到 VDI 環境時，無法為所有使用者安裝。」</span><span class="sxs-lookup"><span data-stu-id="af134-239">Cannot install for all users when a VDI environment is not detected."</span></span>

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        <span data-ttu-id="af134-240">此程式會Teams 64 位作業系統上的 (x86) 資料夾，以及 32 位作業系統上的程式檔案資料夾。</span><span class="sxs-lookup"><span data-stu-id="af134-240">This process installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="af134-241">此時，金色影像設定已完成。</span><span class="sxs-lookup"><span data-stu-id="af134-241">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="af134-242">非Teams安裝時，必須安裝每部電腦。</span><span class="sxs-lookup"><span data-stu-id="af134-242">Installing Teams per-machine is required for non-persistent setups.</span></span>

        <span data-ttu-id="af134-243">下一個互動式登入會話Teams並詢問認證。</span><span class="sxs-lookup"><span data-stu-id="af134-243">The next interactive logon session starts Teams and asks for credentials.</span></span>

        > [!NOTE]
        > <span data-ttu-id="af134-244">這些範例也會使用 **ALLUSERS=1** 參數。</span><span class="sxs-lookup"><span data-stu-id="af134-244">These examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="af134-245">當您設定此參數時，Teams Machine-Wide安裝程式會顯示在控制台中的程式和功能中，&應用程式Windows 設定所有電腦使用者的功能。</span><span class="sxs-lookup"><span data-stu-id="af134-245">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="af134-246">然後所有使用者都可以卸載Teams管理員認證。</span><span class="sxs-lookup"><span data-stu-id="af134-246">All users can then uninstall Teams if they have admin credentials.</span></span>
        <span data-ttu-id="af134-247">瞭解 **ALLUSERS=1** 與 **ALLUSER=1** 的差異非常重要。</span><span class="sxs-lookup"><span data-stu-id="af134-247">It's important to understand the difference between **ALLUSERS=1** and **ALLUSER=1**.</span></span> <span data-ttu-id="af134-248">**ALLUSERS=1** 參數可用於非 VDI 和 VDI 環境，而 **ALLUSER=1** 參數僅適用于 VDI 環境，以指定每部電腦安裝。</span><span class="sxs-lookup"><span data-stu-id="af134-248">The **ALLUSERS=1** parameter can be used in non-VDI and VDI environments, while the **ALLUSER=1** parameter is used only in VDI environments to specify a per-machine installation.</span></span>

3. <span data-ttu-id="af134-249">從 VDI VM 卸載 MSI。</span><span class="sxs-lookup"><span data-stu-id="af134-249">Uninstall the MSI from the VDI VM.</span></span> <span data-ttu-id="af134-250">有兩種方法可以卸載Teams。</span><span class="sxs-lookup"><span data-stu-id="af134-250">There are two ways to uninstall Teams.</span></span>

    - <span data-ttu-id="af134-251">PowerShell 腳本：您可以使用[這個 PowerShell](scripts/powershell-script-deployment-cleanup.md)腳本來卸載Teams並移除Teams資料夾。</span><span class="sxs-lookup"><span data-stu-id="af134-251">PowerShell script: You can use [this PowerShell script](scripts/powershell-script-deployment-cleanup.md) to uninstall Teams and remove the Teams folder for a user.</span></span> <span data-ttu-id="af134-252">針對每一個使用者設定檔執行腳本，Teams電腦上安裝該設定檔。</span><span class="sxs-lookup"><span data-stu-id="af134-252">Run the script for each user profile in which Teams was installed on the computer.</span></span>
    - <span data-ttu-id="af134-253">命令列：執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="af134-253">Command line: Run the following command.</span></span>
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      <span data-ttu-id="af134-254">此程式會視Teams環境 (x86) 資料夾或程式檔案資料夾卸載程式檔案。</span><span class="sxs-lookup"><span data-stu-id="af134-254">This process uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="af134-255">Teams VDI 的績效考慮</span><span class="sxs-lookup"><span data-stu-id="af134-255">Teams on VDI performance considerations</span></span>

<span data-ttu-id="af134-256">有各種不同的虛擬化設定設定，每個設定都有不同的優化焦點。</span><span class="sxs-lookup"><span data-stu-id="af134-256">There are a variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="af134-257">例如，組組可能會著重于使用者密度。</span><span class="sxs-lookup"><span data-stu-id="af134-257">For example, a configuration might focus on user density.</span></span> <span data-ttu-id="af134-258">規劃時，請考慮下列專案，協助根據貴組織的工作量需求優化您的設定。</span><span class="sxs-lookup"><span data-stu-id="af134-258">When planning, consider the following to help optimize your setup based on your organization's workload needs.</span></span>

- <span data-ttu-id="af134-259">最低需求：某些工作負載可能需要使用高於最低需求的資源進行設定。</span><span class="sxs-lookup"><span data-stu-id="af134-259">Minimum requirement: Some workloads might require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="af134-260">例如，針對使用需要更多計算資源之應用程式之開發人員的工作負載。</span><span class="sxs-lookup"><span data-stu-id="af134-260">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="af134-261">相依性：這些包括基礎結構、工作負載和其他環境考慮的相依性，Teams應用程式。</span><span class="sxs-lookup"><span data-stu-id="af134-261">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="af134-262">VDI 上的停用功能：Teams停用 VDI 的 GPU 密集功能，這有助於改善暫時性的 CPU 使用量。</span><span class="sxs-lookup"><span data-stu-id="af134-262">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="af134-263">下列功能已停用：</span><span class="sxs-lookup"><span data-stu-id="af134-263">The following features are disabled:</span></span>
    - <span data-ttu-id="af134-264">TeamsCSS 動畫</span><span class="sxs-lookup"><span data-stu-id="af134-264">Teams CSS animation</span></span>
    - <span data-ttu-id="af134-265">Giphy 自動啟動</span><span class="sxs-lookup"><span data-stu-id="af134-265">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="af134-266">Teams VDI 使用通話和會議</span><span class="sxs-lookup"><span data-stu-id="af134-266">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="af134-267">除了聊天和共同Teams，支援虛擬化提供者平臺Teams VDI 上的通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="af134-267">In addition to chat and collaboration, Teams on VDI with calling and meetings is available with supported virtualization provider platforms.</span></span> <span data-ttu-id="af134-268">支援的功能是以 WebRTC 媒體堆疊和虛擬化提供者的實現為基礎。</span><span class="sxs-lookup"><span data-stu-id="af134-268">Supported features are based on the WebRTC media stack and virtualization provider implementation.</span></span> <span data-ttu-id="af134-269">下圖提供架構概觀。</span><span class="sxs-lookup"><span data-stu-id="af134-269">The following diagram provides an overview of the architecture.</span></span>

![顯示 VDI 架構Teams圖表](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> <span data-ttu-id="af134-271">如果您目前執行 Teams 時未在 VDI 中執行 AV 優化，而且使用尚未支援優化的功能 (例如當 App 共用時提供並控制) ，您必須設定虛擬化提供者政策以關閉 Teams 重新導向。</span><span class="sxs-lookup"><span data-stu-id="af134-271">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set virtualization provider policies to turn off Teams redirection.</span></span> <span data-ttu-id="af134-272">這表示Teams媒體會話不會優化。</span><span class="sxs-lookup"><span data-stu-id="af134-272">This means that Teams media sessions won't be optimized.</span></span> <span data-ttu-id="af134-273">如需如何設定關閉重新導向Teams相關步驟，請與您的虛擬化提供者聯繫。</span><span class="sxs-lookup"><span data-stu-id="af134-273">For steps on how to set policies to turn off Teams redirection, contact your virtualization provider.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="af134-274">網路需求</span><span class="sxs-lookup"><span data-stu-id="af134-274">Network requirements</span></span>

<span data-ttu-id="af134-275">我們建議您評估您的環境，找出可能會影響整體雲端語音和視像部署的任何風險與需求。</span><span class="sxs-lookup"><span data-stu-id="af134-275">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="af134-276">使用 商務用 Skype[網路評定工具](https://www.microsoft.com/download/details.aspx?id=53885)，測試您的網路是否已準備好Teams。</span><span class="sxs-lookup"><span data-stu-id="af134-276">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="af134-277">若要深入瞭解如何準備您的網路以Teams，請參閱準備貴組織的網路[以Teams。](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="af134-277">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="af134-278">從 VDI 商務用 Skype到 VDI Teams的用戶端</span><span class="sxs-lookup"><span data-stu-id="af134-278">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="af134-279">如果您要從 VDI 上的 商務用 Skype 移Teams到 VDI 上的 Teams，除了兩個應用程式之間的差異之外，在 VDI 也實現時也會有一些差異。</span><span class="sxs-lookup"><span data-stu-id="af134-279">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="af134-280">VDI 中目前不支援Teams VDI 中的商務用 Skype如下：</span><span class="sxs-lookup"><span data-stu-id="af134-280">Some capabilities that aren't currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="af134-281">在 VDI 中停用部分 AV 功能的每個平臺策略</span><span class="sxs-lookup"><span data-stu-id="af134-281">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="af134-282">在 App 共用時給予並控制</span><span class="sxs-lookup"><span data-stu-id="af134-282">Give and take control when app sharing</span></span>
- <span data-ttu-id="af134-283">從沒有音訊的聊天分享螢幕畫面</span><span class="sxs-lookup"><span data-stu-id="af134-283">Screen share from chat without audio</span></span>
- <span data-ttu-id="af134-284">同時傳送和接收視像和螢幕畫面共用</span><span class="sxs-lookup"><span data-stu-id="af134-284">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="af134-285">Teams瀏覽器與適用于 VDI 的桌面Teams應用程式</span><span class="sxs-lookup"><span data-stu-id="af134-285">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="af134-286">Teams瀏覽器上的應用程式無法以 AV 優化Teams取代 VDI 的桌面應用程式。</span><span class="sxs-lookup"><span data-stu-id="af134-286">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="af134-287">聊天和共同合作體驗如預期運作。</span><span class="sxs-lookup"><span data-stu-id="af134-287">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="af134-288">當需要媒體時，Chrome 瀏覽器上的某些體驗可能不符合使用者預期：</span><span class="sxs-lookup"><span data-stu-id="af134-288">When media is needed, there are some experiences that might not meet user expectations on the Chrome browser:</span></span>

- <span data-ttu-id="af134-289">音訊和視音訊串流體驗可能並非最佳。</span><span class="sxs-lookup"><span data-stu-id="af134-289">The audio and video streaming experience might not be optimal.</span></span> <span data-ttu-id="af134-290">使用者可能會遭遇延遲或品質降低的問題。</span><span class="sxs-lookup"><span data-stu-id="af134-290">Users might experiences delays or reduced quality.</span></span>
- <span data-ttu-id="af134-291">瀏覽器設定中無法提供裝置設定。</span><span class="sxs-lookup"><span data-stu-id="af134-291">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="af134-292">裝置管理是透過瀏覽器處理，需要瀏覽器網站設定中的多個設定。</span><span class="sxs-lookup"><span data-stu-id="af134-292">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="af134-293">裝置設定可能也需要在裝置管理Windows設定。</span><span class="sxs-lookup"><span data-stu-id="af134-293">Device settings might also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="af134-294">Teams聊天和共同合作使用 VDI</span><span class="sxs-lookup"><span data-stu-id="af134-294">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="af134-295">如果貴組織只想在 Teams 中使用聊天和共同Teams，您可以設定使用者層級策略，以在 Teams 中關閉通話和Teams。</span><span class="sxs-lookup"><span data-stu-id="af134-295">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span> 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="af134-296">設定關閉通話和會議功能的政策</span><span class="sxs-lookup"><span data-stu-id="af134-296">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="af134-297">您可以使用系統管理中心或 PowerShell Microsoft Teams設定策略。</span><span class="sxs-lookup"><span data-stu-id="af134-297">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="af134-298">可能需要幾個小時 (，) 策略變更才能傳播。</span><span class="sxs-lookup"><span data-stu-id="af134-298">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="af134-299">如果您沒立即看到給定帳戶的變更，請在幾個小時後再試一次。</span><span class="sxs-lookup"><span data-stu-id="af134-299">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="af134-300">[**通話策略**](teams-calling-policy.md)：Teams包括內建的 DisallowCalling 通話政策，其中所有通話功能都已關閉。</span><span class="sxs-lookup"><span data-stu-id="af134-300">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="af134-301">將 DisallowCalling 政策指派給組織中在虛擬化環境中Teams使用者。</span><span class="sxs-lookup"><span data-stu-id="af134-301">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="af134-302">[**會議政策**](meeting-policies-in-teams.md)：Teams包含內建的 AllOff 會議政策，其中會關閉所有會議功能。</span><span class="sxs-lookup"><span data-stu-id="af134-302">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="af134-303">將 AllOff 政策指派給組織中在虛擬化環境中Teams所有使用者。</span><span class="sxs-lookup"><span data-stu-id="af134-303">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="af134-304">使用系統管理中心Microsoft Teams指派政策</span><span class="sxs-lookup"><span data-stu-id="af134-304">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="af134-305">若要將 DisallowCalling 通話策略和 AllOff 會議策略指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="af134-305">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="af134-306">在系統管理中心的左側導Microsoft Teams，**請前往** 使用者 。</span><span class="sxs-lookup"><span data-stu-id="af134-306">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="af134-307">按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]。</span><span class="sxs-lookup"><span data-stu-id="af134-307">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="af134-308">請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="af134-308">Do the following:</span></span>
    1.  <span data-ttu-id="af134-309">在 **[通話政策中**， **Click DisallowCalling.**</span><span class="sxs-lookup"><span data-stu-id="af134-309">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2.  <span data-ttu-id="af134-310">在 **[會議政策>** 下，按一下 **[AllOff>**。</span><span class="sxs-lookup"><span data-stu-id="af134-310">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="af134-311">按一下 **[Apply.**</span><span class="sxs-lookup"><span data-stu-id="af134-311">Click **Apply**.</span></span>

<span data-ttu-id="af134-312">若要一次將原則指派給多位使用者：</span><span class="sxs-lookup"><span data-stu-id="af134-312">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="af134-313">在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="af134-313">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="af134-314">在 [&#x2713;] (核取方塊) 欄中，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="af134-314">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="af134-315">若要選取 [所有使用者]，請按一下表格頂端的 [&#x2713;] (核取方塊)。</span><span class="sxs-lookup"><span data-stu-id="af134-315">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="af134-316">按一下 [編輯設定]，進行所需的變更，然後按一下 [套用]。</span><span class="sxs-lookup"><span data-stu-id="af134-316">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="af134-317">或者，您也可以執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="af134-317">Or, you can also do the following:</span></span>

1. <span data-ttu-id="af134-318">在系統管理中心的左側導Microsoft Teams，前往您想要指派的政策。</span><span class="sxs-lookup"><span data-stu-id="af134-318">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="af134-319">例如：</span><span class="sxs-lookup"><span data-stu-id="af134-319">For example:</span></span>
    - <span data-ttu-id="af134-320">請前往 **[**  >  **語音通話政策**，然後按一下 **[取消禁止使用Calling>**。</span><span class="sxs-lookup"><span data-stu-id="af134-320">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="af134-321">前往[  >  **會議會議政策**，然後按一下 **AllOff**。</span><span class="sxs-lookup"><span data-stu-id="af134-321">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
2. <span data-ttu-id="af134-322">選取 [管理使用者]。</span><span class="sxs-lookup"><span data-stu-id="af134-322">Select **Manage users**.</span></span>
3. <span data-ttu-id="af134-323">在 [管理使用者] 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="af134-323">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="af134-324">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="af134-324">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="af134-325">新增使用者完成後，請按一下 [**儲存。**</span><span class="sxs-lookup"><span data-stu-id="af134-325">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="af134-326">使用 PowerShell 指派策略</span><span class="sxs-lookup"><span data-stu-id="af134-326">Assign policies using PowerShell</span></span>

<span data-ttu-id="af134-327">下列範例顯示如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 將 DisallowCalling 通話策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="af134-327">The following example shows how to use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="af134-328">若要深入瞭解使用 PowerShell 管理通話政策，請參閱 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="af134-328">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="af134-329">下列範例顯示如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) 將 AllOff 會議策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="af134-329">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="af134-330">若要深入瞭解使用 PowerShell 管理會議政策，請參閱 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="af134-330">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a><span data-ttu-id="af134-331">使用Teams和共同合作在 VDI 上遷移Teams通話和會議來優化通話和會議</span><span class="sxs-lookup"><span data-stu-id="af134-331">Migrate Teams on VDI with chat and collaboration to optimize Teams with calling and meetings</span></span>

<span data-ttu-id="af134-332">如果您在 VDI 上有現有的 Teams 與聊天和共同合作的實現，其中您設定了使用者層級策略以關閉通話和會議功能，而您正使用 AV 優化移轉至 Teams，則必須設定策略，為 VDI 使用者上的 Teams 開啟通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="af134-332">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Teams with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="af134-333">設定開啟通話和會議功能的政策</span><span class="sxs-lookup"><span data-stu-id="af134-333">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="af134-334">您可以使用系統管理中心Microsoft Teams PowerShell 來設定和指派通話和會議政策給使用者。</span><span class="sxs-lookup"><span data-stu-id="af134-334">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="af134-335">可能需要幾個小時 (，) 策略變更才能傳播。</span><span class="sxs-lookup"><span data-stu-id="af134-335">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="af134-336">如果您沒立即看到給定帳戶的變更，請在幾個小時後再試一次。</span><span class="sxs-lookup"><span data-stu-id="af134-336">If you don't see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="af134-337">[**通話策略**](teams-calling-policy.md)：Teams控制哪些通話功能可供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="af134-337">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="af134-338">Teams包含內建的 AllowCalling 通話政策，其中所有通話功能都開啟。</span><span class="sxs-lookup"><span data-stu-id="af134-338">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="af134-339">若要開啟所有通話功能，請指派 AllowCalling 政策。</span><span class="sxs-lookup"><span data-stu-id="af134-339">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="af134-340">或者，建立自訂通話策略以開啟您想要的通話功能，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="af134-340">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span> 

<span data-ttu-id="af134-341">[**會議政策**](meeting-policies-in-teams.md)：Teams中的會議政策可控制使用者可以建立的會議類型，以及貴組織中使用者所排程的會議參與者可用的功能。</span><span class="sxs-lookup"><span data-stu-id="af134-341">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="af134-342">Teams包含內建的 AllOn 會議政策，其中所有會議功能都開啟。</span><span class="sxs-lookup"><span data-stu-id="af134-342">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="af134-343">若要開啟所有會議功能，請指派 AllOn 策略。</span><span class="sxs-lookup"><span data-stu-id="af134-343">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="af134-344">或者，建立自訂會議策略以開啟您想要的會議功能，並指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="af134-344">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="af134-345">使用系統管理中心Microsoft Teams指派政策</span><span class="sxs-lookup"><span data-stu-id="af134-345">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="af134-346">若要將 AllowCalling 通話策略和 AllOn 會議策略指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="af134-346">To assign the AllowCalling calling policy and the AllOn meeting policy to a user:</span></span>

1. <span data-ttu-id="af134-347">在系統管理中心的左側導Microsoft Teams，**請前往** 使用者 。</span><span class="sxs-lookup"><span data-stu-id="af134-347">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="af134-348">按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]。</span><span class="sxs-lookup"><span data-stu-id="af134-348">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="af134-349">請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="af134-349">Do the following:</span></span>
    1.  <span data-ttu-id="af134-350">在 **[通話政策>** 下，按一下 **[AllowCalling>**。</span><span class="sxs-lookup"><span data-stu-id="af134-350">Under **Calling policy**, click **AllowCalling**.</span></span>
    2.  <span data-ttu-id="af134-351">在 **[會議政策>** 下，按一下 **[AllOn.**</span><span class="sxs-lookup"><span data-stu-id="af134-351">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="af134-352">按一下 **[Apply.**</span><span class="sxs-lookup"><span data-stu-id="af134-352">Click **Apply**.</span></span>

<span data-ttu-id="af134-353">若要一次將原則指派給多位使用者：</span><span class="sxs-lookup"><span data-stu-id="af134-353">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="af134-354">在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="af134-354">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="af134-355">在 [&#x2713;] (核取方塊) 欄中，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="af134-355">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="af134-356">若要選取所有使用者，請按一下 **&#x2713;()** 表格頂端的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="af134-356">To select all users, click the **&#x2713;** (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="af134-357">按一下 [編輯設定]，進行所需的變更，然後按一下 [套用]。</span><span class="sxs-lookup"><span data-stu-id="af134-357">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="af134-358">或者，您也可以執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="af134-358">Or, you can also do the following:</span></span>

1. <span data-ttu-id="af134-359">在系統管理中心的左側導Microsoft Teams，前往您想要指派的政策。</span><span class="sxs-lookup"><span data-stu-id="af134-359">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="af134-360">例如：</span><span class="sxs-lookup"><span data-stu-id="af134-360">For example:</span></span>
    - <span data-ttu-id="af134-361">前往 **[語音**  >  **通話政策**，然後按一下 **AllowCalling。**</span><span class="sxs-lookup"><span data-stu-id="af134-361">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="af134-362">前往[  >  **會議會議政策**，然後按一下 **AllOn。**</span><span class="sxs-lookup"><span data-stu-id="af134-362">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
2. <span data-ttu-id="af134-363">選取 [管理使用者]。</span><span class="sxs-lookup"><span data-stu-id="af134-363">Select **Manage users**.</span></span>
3. <span data-ttu-id="af134-364">在 [管理使用者] 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="af134-364">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="af134-365">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="af134-365">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="af134-366">新增使用者完成後，請按一下 [**儲存。**</span><span class="sxs-lookup"><span data-stu-id="af134-366">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="af134-367">使用 PowerShell 指派策略</span><span class="sxs-lookup"><span data-stu-id="af134-367">Assign policies using PowerShell</span></span>

<span data-ttu-id="af134-368">下列範例顯示如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 將 AllowCalling 通話策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="af134-368">The following example shows how to use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

<span data-ttu-id="af134-369">若要深入瞭解使用 PowerShell 管理通話政策，請參閱 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="af134-369">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="af134-370">下列範例顯示如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) 將 AllOn 會議策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="af134-370">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

<span data-ttu-id="af134-371">若要深入瞭解使用 PowerShell 管理會議政策，請參閱 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="af134-371">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="control-fallback-mode-in-teams"></a><span data-ttu-id="af134-372">控制項的後Teams</span><span class="sxs-lookup"><span data-stu-id="af134-372">Control fallback mode in Teams</span></span>

<span data-ttu-id="af134-373">當使用者從不支援的端點進行連接時，使用者會進入退後模式，而 AV 未優化。</span><span class="sxs-lookup"><span data-stu-id="af134-373">When users connect from an unsupported endpoint, the users are in fallback mode, in which AV isn't optimized.</span></span> <span data-ttu-id="af134-374">您可以設定下列其中一個註冊表 DWORD 值，以停用或啟用退後模式：</span><span class="sxs-lookup"><span data-stu-id="af134-374">You can disable or enable fallback mode by setting one of the following registry DWORD values:</span></span>

- <span data-ttu-id="af134-375">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="af134-375">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span></span>
- <span data-ttu-id="af134-376">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="af134-376">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span></span>

<span data-ttu-id="af134-377">若要停用退後模式，將值設為 **1。**</span><span class="sxs-lookup"><span data-stu-id="af134-377">To disable fallback mode, set the value to **1**.</span></span> <span data-ttu-id="af134-378">若要僅啟用音訊，請設定為 **2。**</span><span class="sxs-lookup"><span data-stu-id="af134-378">To enable audio only, set the value to **2**.</span></span> <span data-ttu-id="af134-379">如果值不存在或設為 0 (**0，)** 會啟用退後模式。</span><span class="sxs-lookup"><span data-stu-id="af134-379">If the value isn't present or is set to **0** (zero), fallback mode is enabled.</span></span>

<span data-ttu-id="af134-380">這項功能可在 Teams 1.3.00.13565 及更新版本中使用。</span><span class="sxs-lookup"><span data-stu-id="af134-380">This feature is available in Teams version 1.3.00.13565 and later.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="af134-381">已知問題和限制</span><span class="sxs-lookup"><span data-stu-id="af134-381">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="af134-382">用戶端部署、安裝和設定</span><span class="sxs-lookup"><span data-stu-id="af134-382">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="af134-383">每部電腦安裝Teams VDI 上的更新不會以非 VDI 用戶端Teams的方式自動更新。</span><span class="sxs-lookup"><span data-stu-id="af134-383">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="af134-384">您必須安裝新的 MSI 以更新 VM 映射，如在[VDI](#install-or-update-the-teams-desktop-app-on-vdi)上安裝或更新Teams桌面應用程式一節中所述。</span><span class="sxs-lookup"><span data-stu-id="af134-384">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="af134-385">您必須卸載目前的版本，以更新至較新版本。</span><span class="sxs-lookup"><span data-stu-id="af134-385">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="af134-386">在 Citrix 環境中，如果使用者在 Teams 執行時與虛擬機器中斷連接，Teams 更新可能會導致使用者重新連接時，AV 狀態未優化。</span><span class="sxs-lookup"><span data-stu-id="af134-386">In Citrix environments, if the user disconnects from the Virtual Machine while Teams is running, Teams updates can result in the user to be in a non-optimized state for AV when they reconnect.</span></span> <span data-ttu-id="af134-387">建議您在使用者從Teams中斷連接之前先退出此帳戶，以避免發生此情況。</span><span class="sxs-lookup"><span data-stu-id="af134-387">We recommend that users quit Teams before they disconnect from Citrix Virtual Machine to avoid this scenario.</span></span>
- <span data-ttu-id="af134-388">Teams使用者或每部電腦部署。</span><span class="sxs-lookup"><span data-stu-id="af134-388">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="af134-389">不支援Teams使用者和每部電腦同時部署用戶端。</span><span class="sxs-lookup"><span data-stu-id="af134-389">Deployment of Teams for concurrent per user and per machine is not supported.</span></span> <span data-ttu-id="af134-390">若要從每部電腦或每個使用者遷移到其中一種模式，請遵循卸載程式，然後重新調配至任一模式。</span><span class="sxs-lookup"><span data-stu-id="af134-390">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="af134-391">Windows虛擬桌面目前不支援 macOS 和 Linux 型用戶端。</span><span class="sxs-lookup"><span data-stu-id="af134-391">Windows Virtual Desktop doesn't support macOS and Linux-based clients at this time.</span></span>

### <a name="calling-and-meetings"></a><span data-ttu-id="af134-392">通話和會議</span><span class="sxs-lookup"><span data-stu-id="af134-392">Calling and meetings</span></span>

<span data-ttu-id="af134-393">不支援下列通話和會議功能：</span><span class="sxs-lookup"><span data-stu-id="af134-393">The following calling and meeting features are not supported:</span></span>

- <span data-ttu-id="af134-394">任何多視窗功能，例如新的會議體驗或任何新會議體驗隨附的功能</span><span class="sxs-lookup"><span data-stu-id="af134-394">Any multi-window functionality like the new meeting experiences or any functionality that comes with the new meeting experience</span></span>
- <span data-ttu-id="af134-395">增強的緊急服務</span><span class="sxs-lookup"><span data-stu-id="af134-395">Enhanced emergency services</span></span>
- <span data-ttu-id="af134-396">應用程式與裝置之間的 HID 按鈕Teams LED 控制項</span><span class="sxs-lookup"><span data-stu-id="af134-396">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="af134-397">背景模糊和效果</span><span class="sxs-lookup"><span data-stu-id="af134-397">Background blur and effects</span></span>
- <span data-ttu-id="af134-398">廣播和即時活動製作人及簡報者角色</span><span class="sxs-lookup"><span data-stu-id="af134-398">Broadcast and live event producer and presenter roles</span></span>
- <span data-ttu-id="af134-399">Location-Based LBR (路由) </span><span class="sxs-lookup"><span data-stu-id="af134-399">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="af134-400">PSTN 通話回鈴鈴聲</span><span class="sxs-lookup"><span data-stu-id="af134-400">PSTN call ringback tone</span></span>
- <span data-ttu-id="af134-401">共用系統音訊/電腦音效</span><span class="sxs-lookup"><span data-stu-id="af134-401">Shared system audio/computer sound</span></span>
- <span data-ttu-id="af134-402">直接路由的媒體旁路</span><span class="sxs-lookup"><span data-stu-id="af134-402">Media bypass for Direct Routing</span></span>
- <span data-ttu-id="af134-403">通話停駐</span><span class="sxs-lookup"><span data-stu-id="af134-403">Call park</span></span>
- <span data-ttu-id="af134-404">縮放控制項</span><span class="sxs-lookup"><span data-stu-id="af134-404">Zoom control</span></span> 

> [!NOTE]
> <span data-ttu-id="af134-405">我們正在努力新增目前僅適用于非 VDI 環境的通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="af134-405">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="af134-406">這些可能包括對品質的更多系統管理員控制、其他螢幕共用案例，以及最近新加入至 Teams。</span><span class="sxs-lookup"><span data-stu-id="af134-406">These might include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="af134-407">請與您的Teams聯絡，以深入瞭解即將推出的功能。</span><span class="sxs-lookup"><span data-stu-id="af134-407">Contact your Teams representative to learn more about upcoming features.</span></span>

<span data-ttu-id="af134-408">以下是通話和會議的已知問題和限制：</span><span class="sxs-lookup"><span data-stu-id="af134-408">The following are known issues and limitations for calling and meetings:</span></span>

- <span data-ttu-id="af134-409">與音訊商務用 Skype僅限音訊通話;沒有視音訊模式。</span><span class="sxs-lookup"><span data-stu-id="af134-409">Interoperability with Skype for Business is limited to audio calls; there is no video modality.</span></span>
- <span data-ttu-id="af134-410">傳入和傳出視音訊串流解析度限制為 720p 解析度。</span><span class="sxs-lookup"><span data-stu-id="af134-410">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span>
- <span data-ttu-id="af134-411">僅支援來自內接相機或螢幕共用流的一個視音訊流。</span><span class="sxs-lookup"><span data-stu-id="af134-411">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="af134-412">當有傳入的螢幕共用時，畫面共用會顯示，而不是主要喇叭的視像。</span><span class="sxs-lookup"><span data-stu-id="af134-412">When there's an incoming screen share, that screen share is shown, instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="af134-413">Teams切換為使用使用者選取的最後一個音訊裝置 ，如果裝置已中斷連接，然後重新連接。</span><span class="sxs-lookup"><span data-stu-id="af134-413">Teams doesn't switch to use the last audio device that a user selected, if the device is disconnected, and then reconnected.</span></span>
- <span data-ttu-id="af134-414">外發畫面分享：</span><span class="sxs-lookup"><span data-stu-id="af134-414">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="af134-415">不支援應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="af134-415">Application sharing is not supported.</span></span>
- <span data-ttu-id="af134-416">提供控制權並控制：</span><span class="sxs-lookup"><span data-stu-id="af134-416">Give control and take control:</span></span>
    - <span data-ttu-id="af134-417">在螢幕畫面共用或應用程式共用會話期間不支援。</span><span class="sxs-lookup"><span data-stu-id="af134-417">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="af134-418">在共用會話PowerPoint支援。</span><span class="sxs-lookup"><span data-stu-id="af134-418">Supported during a PowerPoint sharing session.</span></span>
- <span data-ttu-id="af134-419">僅以黃水晶為限的限制</span><span class="sxs-lookup"><span data-stu-id="af134-419">Citrix-only limitations</span></span>
    - <span data-ttu-id="af134-420">在多監視器設定中共用螢幕時，只會共用主監視器。</span><span class="sxs-lookup"><span data-stu-id="af134-420">When screen sharing in a multi-monitor setup, only the main monitor is shared.</span></span>
    - <span data-ttu-id="af134-421">不支援 CWA 上的高 DPI 縮放比例。</span><span class="sxs-lookup"><span data-stu-id="af134-421">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="af134-422">有關Teams VDI 相關之已知問題，請參閱Teams[支援。](/MicrosoftTeams/troubleshoot/teams-welcome)</span><span class="sxs-lookup"><span data-stu-id="af134-422">For Teams known issues that aren't related to VDI, see [Support Teams in your organization](/MicrosoftTeams/troubleshoot/teams-welcome).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="af134-423">疑難排解</span><span class="sxs-lookup"><span data-stu-id="af134-423">Troubleshooting</span></span>

### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="af134-424">疑難排解黃水晶元件</span><span class="sxs-lookup"><span data-stu-id="af134-424">Troubleshoot Citrix components</span></span>

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a><span data-ttu-id="af134-425">Teams當機或Teams畫面為空白</span><span class="sxs-lookup"><span data-stu-id="af134-425">Teams crashes or the Teams sign in screen is blank</span></span>

<span data-ttu-id="af134-426">這是關於 1906 和 1909 的 Citrix VDA 版本已知問題。</span><span class="sxs-lookup"><span data-stu-id="af134-426">This is a known issue with Citrix VDA versions 1906 and 1909.</span></span> <span data-ttu-id="af134-427">若要解決此問題，請新增下列註冊表 DWORD 值，並設定為 204 (十六進位) 。</span><span class="sxs-lookup"><span data-stu-id="af134-427">To work around this issue, add the following registry DWORD value, and set it to 204 (hexadecimal).</span></span>

<span data-ttu-id="af134-428">HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe</span><span class="sxs-lookup"><span data-stu-id="af134-428">HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe</span></span>

<span data-ttu-id="af134-429">接著，重新開機 VDA。</span><span class="sxs-lookup"><span data-stu-id="af134-429">Then, restart VDA.</span></span> <span data-ttu-id="af134-430">若要深入瞭解，請參閱此關於針對 系統進行[HDX](https://support.citrix.com/article/CTX253754)優化的疑難Teams。</span><span class="sxs-lookup"><span data-stu-id="af134-430">To learn more, see this Citrix support article, [Troubleshooting HDX optimization for Teams](https://support.citrix.com/article/CTX253754).</span></span>

## <a name="related-topics"></a><span data-ttu-id="af134-431">相關主題</span><span class="sxs-lookup"><span data-stu-id="af134-431">Related topics</span></span>

- [<span data-ttu-id="af134-432">使用 MSI Microsoft Teams安裝</span><span class="sxs-lookup"><span data-stu-id="af134-432">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="af134-433">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="af134-433">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="af134-434">在Microsoft Teams桌面Windows使用</span><span class="sxs-lookup"><span data-stu-id="af134-434">Use Microsoft Teams on Windows Virtual desktop</span></span>](/azure/virtual-desktop/teams-on-wvd)

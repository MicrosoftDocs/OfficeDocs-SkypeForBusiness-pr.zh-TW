---
title: 適用於虛擬桌面架構的 Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: 瞭解如何在 (VDI) 環境的虛擬化桌面基礎結構中執行 Microsoft 團隊。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e286611823ddfd12b43abd3a8ff385885fd02a38
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803988"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="c6f6b-103">適用於虛擬桌面架構的 Teams</span><span class="sxs-lookup"><span data-stu-id="c6f6b-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="c6f6b-104">本文將說明在虛擬化環境中使用 Microsoft 團隊的需求與限制。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="c6f6b-105">什麼是 VDI？</span><span class="sxs-lookup"><span data-stu-id="c6f6b-105">What is VDI?</span></span>

<span data-ttu-id="c6f6b-106">虛擬桌面基礎結構 (VDI) 是虛擬化技術，可在資料中心的中央伺服器上託管桌面作業系統和應用程式。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="c6f6b-107">這可讓使用者具備完全安全且相容的集中來源，為使用者提供完整的個人化桌面體驗。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>

<span data-ttu-id="c6f6b-108">虛擬化環境中的 Microsoft 團隊支援聊天與共同作業。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-108">Microsoft Teams in a virtualized environment supports chat and collaboration.</span></span> <span data-ttu-id="c6f6b-109">而且有了 Windows 虛擬桌面版、Citrix 和 VMware 平臺，也支援通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-109">And with the Windows Virtual Desktop, Citrix, and VMware platforms, calling and meeting functionality is also supported.</span></span>

<span data-ttu-id="c6f6b-110">虛擬化環境中的小組支援多種設定。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-110">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="c6f6b-111">其中包括 VDI、專用、共用、持久且非持久的模式。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-111">These include VDI, dedicated, shared, persistent, and non-persistent modes.</span></span> <span data-ttu-id="c6f6b-112">功能在連續開發並定期新增，功能將會在未來的幾個月和幾年中擴充。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-112">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>

<span data-ttu-id="c6f6b-113">在虛擬化環境中使用團隊的方式可能與在非虛擬化環境中使用團隊稍有不同。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-113">Using Teams in a virtualized environment might be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="c6f6b-114">例如，某些高級功能可能無法在虛擬化的環境中使用，而且可能會有不同的影片解析度。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-114">For example, some advanced features might not be available in a virtualized environment, and video resolution might differ.</span></span>

<span data-ttu-id="c6f6b-115">若要確保最佳的使用者體驗，請遵循本文中的指導方針。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-115">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="c6f6b-116">VDI 元件上的小組</span><span class="sxs-lookup"><span data-stu-id="c6f6b-116">Teams on VDI components</span></span>

<span data-ttu-id="c6f6b-117">在虛擬化環境中使用團隊需要下列元件。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-117">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="c6f6b-118">**虛擬化 broker**：虛擬化提供者的資源和連線管理員（例如 Azure）</span><span class="sxs-lookup"><span data-stu-id="c6f6b-118">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="c6f6b-119">**虛擬桌面**：執行 Microsoft 團隊 (VM) 堆疊的虛擬機器</span><span class="sxs-lookup"><span data-stu-id="c6f6b-119">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="c6f6b-120">**瘦用戶端**：使用者使用物理介面的端點</span><span class="sxs-lookup"><span data-stu-id="c6f6b-120">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="c6f6b-121">**團隊桌面應用程式**：團隊桌面用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="c6f6b-121">**Teams desktop app**: The Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="c6f6b-122">針對 VDI 需求的小組</span><span class="sxs-lookup"><span data-stu-id="c6f6b-122">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="c6f6b-123">虛擬化提供者需求</span><span class="sxs-lookup"><span data-stu-id="c6f6b-123">Virtualization provider requirements</span></span>

<span data-ttu-id="c6f6b-124">已使用主要的虛擬化解決方案提供者驗證團隊桌面應用程式。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-124">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="c6f6b-125">有了多個市場供應商，我們建議您諮詢您的虛擬化解決方案供應商，以確保您符合最低需求。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-125">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure that you meet the minimum requirements.</span></span>
  
<span data-ttu-id="c6f6b-126">目前，使用音訊/視頻 (AV) 優化的小組，都是使用 Windows Virtual Desktop、Citrix 和 VMware 進行認證。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-126">Currently, Teams on VDI with audio/video (AV) optimization is certified with Windows Virtual Desktop, Citrix, and VMware.</span></span> <span data-ttu-id="c6f6b-127">請參閱本節中的資訊，以確保您符合所有對適當功能的需求。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-127">Review the information in this section to ensure that you meet all requirements for proper functionality.</span></span>

### <a name="platforms-certified-for-teams"></a><span data-ttu-id="c6f6b-128">針對團隊認證的平臺</span><span class="sxs-lookup"><span data-stu-id="c6f6b-128">Platforms certified for Teams</span></span>

<span data-ttu-id="c6f6b-129">下列平臺擁有小組的虛擬桌面基礎結構解決方案。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-129">The following platforms have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="c6f6b-130">平台</span><span class="sxs-lookup"><span data-stu-id="c6f6b-130">Platform</span></span>|<span data-ttu-id="c6f6b-131">解</span><span class="sxs-lookup"><span data-stu-id="c6f6b-131">Solution</span></span>|
|----|---|
|![代表 Microsoft 的標誌](media/microsoft-logo.png)| <span data-ttu-id="c6f6b-133"><a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows 虛擬桌面</a></span><span class="sxs-lookup"><span data-stu-id="c6f6b-133"><a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows Virtual Desktop</a></span></span> |
|![代表 Citrix 的標誌](media/citrix-logo.png)| <span data-ttu-id="c6f6b-135"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 虛擬 App 與桌面</a></span><span class="sxs-lookup"><span data-stu-id="c6f6b-135"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |
|![代表 VMware 的標誌](media/vmware-logo.png)| <span data-ttu-id="c6f6b-137"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware 範圍</a></span><span class="sxs-lookup"><span data-stu-id="c6f6b-137"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a></span></span> |

### <a name="windows-virtual-desktop"></a><span data-ttu-id="c6f6b-138">Windows 虛擬桌面</span><span class="sxs-lookup"><span data-stu-id="c6f6b-138">Windows Virtual Desktop</span></span>

<span data-ttu-id="c6f6b-139">Windows 虛擬桌面電腦為 VDI 上的小組提供 AV 優化。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-139">Windows Virtual Desktop provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="c6f6b-140">若要深入瞭解及需求及安裝，請參閱 [在 Windows 虛擬桌面電腦上使用團隊](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-140">To learn more and requirements and installation, see [Use Teams on Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd).</span></span>

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="c6f6b-141">Citrix 虛擬 App 與桌面需求</span><span class="sxs-lookup"><span data-stu-id="c6f6b-141">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="c6f6b-142">Citrix 虛擬 App 和桌面 (先前稱為 XenApp 和 XenDesktop) 為 VDI 上的小組提供 AV 優化。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-142">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="c6f6b-143">借助 Citrix 虛擬 App 和電腦版，VDI 的小組除了聊天與共同作業之外，還支援通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-143">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="c6f6b-144">您可以在 [citrix 下載網站](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)下載最新版本的 Citrix 虛擬 App 和桌上型電腦。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-144">You can download the latest version of Citrix Virtual Apps and Desktops at [the Citrix downloads site](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="c6f6b-145"> (您必須先登入。 ) 必要元件已捆綁到 [Citrix 工作區應用程式 (CWA) ](https://www.citrix.com/downloads/workspace-app/) 和虛擬傳遞代理程式 (VDA) 預設。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-145">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="c6f6b-146">您不需要在 CWA 或 VDA 上安裝任何其他元件或外掛程式。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-146">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="c6f6b-147">如需最新的伺服器和用戶端需求，請參閱 [此 Citrix 網站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-147">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a><span data-ttu-id="c6f6b-148">VMware 地平線工作區和桌面需求</span><span class="sxs-lookup"><span data-stu-id="c6f6b-148">VMware Horizon Workspace and Desktop requirements</span></span>

<span data-ttu-id="c6f6b-149">VMware 橫向針對 VDI 的小組提供優化的 AV 支援，以改善虛擬桌面電腦的生產力。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-149">VMware Horizon provides optimized AV support for Teams on VDI for improved productivity across virtual desktops.</span></span> <span data-ttu-id="c6f6b-150">您可以從 [ [Vmware 下載](https://my.vmware.com/web/vmware/downloads/#all_products) ] 頁面下載最新版本的 VMware。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-150">You can download the latest version of VMware Horizon from the [VMware Downloads](https://my.vmware.com/web/vmware/downloads/#all_products) page.</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="c6f6b-151">在 VDI 上安裝或更新小組桌面應用程式</span><span class="sxs-lookup"><span data-stu-id="c6f6b-151">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="c6f6b-152">您可以使用每電腦安裝或使用 MSI 套件的每個使用者安裝，部署 VDI 版團隊桌面應用程式。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-152">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="c6f6b-153">決定使用哪種方法，取決於您使用的是持續性或非持續設定，以及貴組織的相關功能需求。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-153">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>

<span data-ttu-id="c6f6b-154">針對專用的持續設定，這兩種方法都可以運作。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-154">For a dedicated persistent setup, either approach would work.</span></span> <span data-ttu-id="c6f6b-155">不過，對於非持續性設定，小組需要每電腦安裝才能有效運作。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-155">However, for a non-persistent setup, Teams requires a per-machine installation in order to work efficiently.</span></span> <span data-ttu-id="c6f6b-156">請參閱 [非持續性設定](#non-persistent-setup) 一節。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-156">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="c6f6b-157">在安裝每電腦的情況下，自動更新是停用的。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-157">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="c6f6b-158">這表示若要更新團隊應用程式，您必須卸載目前的版本，才能更新為較新的版本。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-158">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="c6f6b-159">針對每位使用者安裝，會啟用自動更新。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-159">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="c6f6b-160">對於大多數的 VDI 部署，我們建議您使用每電腦安裝來部署團隊。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-160">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="c6f6b-161">若要更新為最新的團隊版本，請先從最新的團隊版本部署開始卸載程式。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-161">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="c6f6b-162">為了讓 VDI 環境中的團隊 AV 優化功能正常運作，瘦用戶端端點必須能夠存取網際網路。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-162">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="c6f6b-163">如果瘦用戶端端點無法使用網際網路存取，優化啟動將會失敗。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-163">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="c6f6b-164">這表示使用者處於未優化的媒體狀態。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-164">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="c6f6b-165">專用持續設定</span><span class="sxs-lookup"><span data-stu-id="c6f6b-165">Dedicated persistent setup</span></span>

<span data-ttu-id="c6f6b-166">在專用的持續設定中，使用者會在使用者登出後保留使用者的本機作業系統變更。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-166">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span> <span data-ttu-id="c6f6b-167">針對持續性設定，小組支援針對每位使用者和每電腦安裝。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-167">For persistent setup, Teams supports both per-user and per-machine installation.</span></span>

<span data-ttu-id="c6f6b-168">以下是建議的最低 VM 設定。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-168">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="c6f6b-169">參數</span><span class="sxs-lookup"><span data-stu-id="c6f6b-169">Parameter</span></span>  |<span data-ttu-id="c6f6b-170">工作站作業系統</span><span class="sxs-lookup"><span data-stu-id="c6f6b-170">Workstation operating system</span></span>  |<span data-ttu-id="c6f6b-171">伺服器作業系統</span><span class="sxs-lookup"><span data-stu-id="c6f6b-171">Server operating system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="c6f6b-172">vCPU</span><span class="sxs-lookup"><span data-stu-id="c6f6b-172">vCPU</span></span>   |    <span data-ttu-id="c6f6b-173">2個核心</span><span class="sxs-lookup"><span data-stu-id="c6f6b-173">2 cores</span></span>     |  <span data-ttu-id="c6f6b-174">4、6或8</span><span class="sxs-lookup"><span data-stu-id="c6f6b-174">4,6, or 8</span></span><br><span data-ttu-id="c6f6b-175">請務必瞭解基礎非統一記憶體存取 (NUMA) 設定，並據此設定您的 Vm。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-175">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="c6f6b-176">RAM</span><span class="sxs-lookup"><span data-stu-id="c6f6b-176">RAM</span></span>     |   <span data-ttu-id="c6f6b-177">4 GB</span><span class="sxs-lookup"><span data-stu-id="c6f6b-177">4 GB</span></span>      | <span data-ttu-id="c6f6b-178">每位使用者512到 1024 MB</span><span class="sxs-lookup"><span data-stu-id="c6f6b-178">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="c6f6b-179">儲存空間</span><span class="sxs-lookup"><span data-stu-id="c6f6b-179">Storage</span></span>    | <span data-ttu-id="c6f6b-180">8 GB</span><span class="sxs-lookup"><span data-stu-id="c6f6b-180">8 GB</span></span>        | <span data-ttu-id="c6f6b-181">40到 60 GB</span><span class="sxs-lookup"><span data-stu-id="c6f6b-181">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="c6f6b-182">非持久性設定</span><span class="sxs-lookup"><span data-stu-id="c6f6b-182">Non-persistent setup</span></span>

<span data-ttu-id="c6f6b-183">在非永久性設定中，使用者登出後，使用者的本機作業系統變更就不會保留。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-183">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="c6f6b-184">這類設置通常是共用多個使用者會話。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-184">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="c6f6b-185">VM 配置會根據使用者數量及可用的物理盒資源而有所不同。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-185">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="c6f6b-186">針對非持續性設定，小組桌面應用程式必須安裝在每一台電腦上的黃金影像中。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-186">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="c6f6b-187"> (若要深入瞭解，請參閱 [安裝或更新 VDI 區段上的團隊桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi) 。 ) 這可確保在使用者會話期間有效啟動團隊 app。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-187">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.) This ensures an efficient launch of the Teams app during a user session.</span></span>

<span data-ttu-id="c6f6b-188">將團隊與非持久設定搭配使用時，也需要設定檔的快取管理員，才能高效地進行團隊執行時間資料同步處理。這樣可確保在使用者會話期間，會快取使用者資料、設定檔和設定) 等適當的使用者特定資訊 (範例。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-188">Using Teams with a non-persistent setup also requires a profile caching manager for efficient Teams runtime data sync. This ensures that the appropriate user-specific information (for example, user data, profile, and settings) is cached during the user session.</span></span> <span data-ttu-id="c6f6b-189">請確定這兩個資料夾中的資料已同步處理。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-189">Make sure data in these two folders are synced.</span></span>  

- <span data-ttu-id="c6f6b-190">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache) </span><span class="sxs-lookup"><span data-stu-id="c6f6b-190">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span></span>
- <span data-ttu-id="c6f6b-191">C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams) </span><span class="sxs-lookup"><span data-stu-id="c6f6b-191">C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)</span></span>

<span data-ttu-id="c6f6b-192">有許多可用的緩存管理器解決方案。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-192">There are a variety of caching manager solutions available.</span></span> <span data-ttu-id="c6f6b-193">例如， [FSLogix](https://docs.microsoft.com/fslogix/overview)。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-193">For example, [FSLogix](https://docs.microsoft.com/fslogix/overview).</span></span> <span data-ttu-id="c6f6b-194">如需特定的設定指示，請參閱您的快取管理員提供者。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-194">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="c6f6b-195">小組快取內容排除清單以進行非持續設定</span><span class="sxs-lookup"><span data-stu-id="c6f6b-195">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="c6f6b-196">從 [團隊快取] 資料夾（% appdata%/Microsoft/Teams.）中排除下列各項：</span><span class="sxs-lookup"><span data-stu-id="c6f6b-196">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span> <span data-ttu-id="c6f6b-197">排除這些專案有助於減少使用者的快取大小，進一步優化您的非持久設定。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-197">Excluding these items helps reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="c6f6b-198">.txt 檔案</span><span class="sxs-lookup"><span data-stu-id="c6f6b-198">.txt files</span></span>
- <span data-ttu-id="c6f6b-199">媒體堆疊資料夾</span><span class="sxs-lookup"><span data-stu-id="c6f6b-199">Media-stack folder</span></span>
- <span data-ttu-id="c6f6b-200">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache) </span><span class="sxs-lookup"><span data-stu-id="c6f6b-200">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)</span></span>

### <a name="microsoft-365-apps-for-enterprise-considerations"></a><span data-ttu-id="c6f6b-201">適用于企業考慮的 Microsoft 365 應用程式</span><span class="sxs-lookup"><span data-stu-id="c6f6b-201">Microsoft 365 Apps for enterprise considerations</span></span>

<span data-ttu-id="c6f6b-202">當您使用 VDI 上的企業版 Microsoft 365 應用程式部署團隊時，請考慮下列事項。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-202">Consider the following when you deploy Teams with Microsoft 365 Apps for enterprise on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="c6f6b-203">透過企業版 Microsoft 365 應用程式的新部署團隊</span><span class="sxs-lookup"><span data-stu-id="c6f6b-203">New deployments of Teams through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="c6f6b-204">在透過企業版 Microsoft 365 應用程式部署團隊前，您必須先卸載任何預先存在的團隊應用程式（如果它們是使用各電腦安裝來部署）。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-204">Before you deploy Teams through Microsoft 365 Apps for enterprise, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="c6f6b-205">團隊透過適用于企業的 Microsoft 365 應用程式是針對每位使用者安裝的。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-205">Teams through Microsoft 365 Apps for enterprise is installed per-user.</span></span> <span data-ttu-id="c6f6b-206">若要深入瞭解，請參閱 [安裝或更新 VDI 區段上的小組桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi) 。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-206">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a><span data-ttu-id="c6f6b-207">透過適用于企業更新的 Microsoft 365 應用程式部署團隊</span><span class="sxs-lookup"><span data-stu-id="c6f6b-207">Teams deployments through Microsoft 365 Apps for enterprise updates</span></span>

<span data-ttu-id="c6f6b-208">團隊也會新增至企業版 Microsoft 365 應用程式的現有安裝。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-208">Teams is also being added to existing installations of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="c6f6b-209">由於 [企業版 Microsoft 365 應用程式] 只會針對每位使用者安裝小組，請參閱在 [VDI 上安裝或更新小組桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi) 。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-209">Since Microsoft 365 Apps for enterprise installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="c6f6b-210">使用團隊進行每電腦安裝和適用于企業的 Microsoft 365 應用程式</span><span class="sxs-lookup"><span data-stu-id="c6f6b-210">Using Teams with per-machine installation and Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="c6f6b-211">適用于企業的 Microsoft 365 應用程式不支援小組的每電腦安裝。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-211">Microsoft 365 Apps for enterprise doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="c6f6b-212">若要使用 [每電腦安裝]，您必須從適用于企業的 Microsoft 365 App 中排除團隊。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-212">To use per-machine installation, you must exclude Teams from Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="c6f6b-213">請參閱將 [團隊傳統型應用程式部署至 VM](#deploy-the-teams-desktop-app-to-the-vm) ，以及 [如何透過適用于企業的 Microsoft 365 應用程式排除團隊部署](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) 。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-213">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Microsoft 365 Apps for enterprise](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="c6f6b-214">如何透過適用于企業的 Microsoft 365 應用程式排除團隊部署</span><span class="sxs-lookup"><span data-stu-id="c6f6b-214">How to exclude Teams deployment through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="c6f6b-215">若要深入瞭解團隊和適用于企業的 Microsoft 365 應用程式，請參閱 [如何將團隊從新安裝的企業版 microsoft 365 應用程式中排除](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) ，並 [使用群組原則來控制團隊的安裝](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-215">To learn more about Teams and Microsoft 365 Apps for enterprise, see [How to exclude Teams from new installations of Microsoft 365 Apps for enterprise](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="c6f6b-216">將團隊桌面應用程式部署到 VM</span><span class="sxs-lookup"><span data-stu-id="c6f6b-216">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="c6f6b-217">使用下列其中一個連結，下載與您的 VDI VM 作業系統相符的團隊 MSI 套件：</span><span class="sxs-lookup"><span data-stu-id="c6f6b-217">Download the Teams MSI package that matches your VDI VM operating system using one of the following links:</span></span>

    - [<span data-ttu-id="c6f6b-218">32位版本</span><span class="sxs-lookup"><span data-stu-id="c6f6b-218">32-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows/1.3.00.21759/Teams_windows.msi)
    - [<span data-ttu-id="c6f6b-219">64位版本</span><span class="sxs-lookup"><span data-stu-id="c6f6b-219">64-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows-x64/1.3.00.21759/Teams_windows_x64.msi)

    <span data-ttu-id="c6f6b-220">所需的小組桌面應用程式最低版本為版本1.3.00.4461。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-220">The minimum version of the Teams desktop app that's required is version 1.3.00.4461.</span></span> <span data-ttu-id="c6f6b-221">舊版中不支援 (PSTN 保留。 ) </span><span class="sxs-lookup"><span data-stu-id="c6f6b-221">(PSTN hold isn't supported in earlier versions.)</span></span>

2. <span data-ttu-id="c6f6b-222">執行下列其中一項命令，將 MSI 安裝到 VDI VM：</span><span class="sxs-lookup"><span data-stu-id="c6f6b-222">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="c6f6b-223">依使用者安裝 (預設) </span><span class="sxs-lookup"><span data-stu-id="c6f6b-223">Per-user installation (default)</span></span>
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        <span data-ttu-id="c6f6b-224">這個處理常式是預設安裝，可將團隊安裝到% AppData% user 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-224">This process is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="c6f6b-225">此時，黃金影像設定就完成了。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-225">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="c6f6b-226">在非持續設定上，小組無法針對每位使用者安裝正常運作。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-226">Teams won't work properly with per-user installation on a non-persistent setup.</span></span>

    - <span data-ttu-id="c6f6b-227">每電腦安裝</span><span class="sxs-lookup"><span data-stu-id="c6f6b-227">Per-machine installation</span></span>

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        <span data-ttu-id="c6f6b-228">此程式會將團隊安裝至64位作業系統上的 [x86) ] 資料夾 (的程式檔案，以及32位作業系統上的 [程式檔案] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-228">This process installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="c6f6b-229">此時，黃金影像設定就完成了。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-229">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="c6f6b-230">針對非持久的安裝，必須針對每台電腦安裝團隊。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-230">Installing Teams per-machine is required for non-persistent setups.</span></span>

        <span data-ttu-id="c6f6b-231">下次互動式登入會話會啟動團隊並要求認證。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-231">The next interactive logon session starts Teams and asks for credentials.</span></span>

        > [!NOTE]
        > <span data-ttu-id="c6f6b-232">這些範例也會使用 **ALLUSERS = 1** 參數。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-232">These examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="c6f6b-233">當您設定此參數時，系統會在 [控制台] 的 [程式和功能] 和 [應用程式 & Windows 設定] 中的 [應用程式] 中，顯示「團隊電腦範圍」的安裝程式。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-233">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="c6f6b-234">如果有管理員認證，所有使用者都可以卸載小組。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-234">All users can then uninstall Teams if they have admin credentials.</span></span>
        <span data-ttu-id="c6f6b-235">請務必瞭解 **ALLUSERS = 1** 與 **ALLUSER = 1**之間的差異。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-235">It's important to understand the difference between **ALLUSERS=1** and **ALLUSER=1**.</span></span> <span data-ttu-id="c6f6b-236">您可以在非 VDI 和 VDI 環境中使用 **ALLUSERS = 1** 參數，而 **ALLUSER = 1** 參數只會在 VDI 環境中用來指定每電腦安裝。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-236">The **ALLUSERS=1** parameter can be used in non-VDI and VDI environments, while the **ALLUSER=1** parameter is used only in VDI environments to specify a per-machine installation.</span></span>

3. <span data-ttu-id="c6f6b-237">從 VDI VM 卸載 MSI。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-237">Uninstall the MSI from the VDI VM.</span></span>
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      <span data-ttu-id="c6f6b-238">這個程式會將小組從程式檔案卸載 (x86) 資料夾或 Program Files 資料夾，視作業系統環境而定。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-238">This process uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="c6f6b-239">VDI 效能考慮的小組</span><span class="sxs-lookup"><span data-stu-id="c6f6b-239">Teams on VDI performance considerations</span></span>

<span data-ttu-id="c6f6b-240">有多種虛擬化設定設定，每個都有不同的焦點可供優化。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-240">There are a variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="c6f6b-241">例如，配置可能會將焦點放在使用者密度上。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-241">For example, a configuration might focus on user density.</span></span> <span data-ttu-id="c6f6b-242">規劃時，請考慮下列事項，以根據貴組織的工作負載需求來優化您的設定。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-242">When planning, consider the following to help optimize your setup based on your organization's workload needs.</span></span>

- <span data-ttu-id="c6f6b-243">最低需求：某些工作負載可能需要使用超過最低需求的資源進行設定。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-243">Minimum requirement: Some workloads might require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="c6f6b-244">例如，使用需要更多計算資源之應用程式之開發人員的工作負載。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-244">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="c6f6b-245">相依性：這些專案包括在小組桌面應用程式以外的基礎結構、工作負載及其他環境考慮因素的相依性。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-245">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="c6f6b-246">VDI 上停用的功能：團隊會針對 VDI 停用 GPU 密集型功能，這可以協助改善暫時的 CPU 利用率。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-246">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="c6f6b-247">下列功能已停用：</span><span class="sxs-lookup"><span data-stu-id="c6f6b-247">The following features are disabled:</span></span>
    - <span data-ttu-id="c6f6b-248">團隊 CSS 動畫</span><span class="sxs-lookup"><span data-stu-id="c6f6b-248">Teams CSS animation</span></span>
    - <span data-ttu-id="c6f6b-249">Giphy 自動啟動</span><span class="sxs-lookup"><span data-stu-id="c6f6b-249">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="c6f6b-250">VDI 上的小組與通話與會議</span><span class="sxs-lookup"><span data-stu-id="c6f6b-250">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="c6f6b-251">除了聊天與共同作業之外，您還可以使用支援的虛擬化提供者平臺提供通話和會議的 VDI 小組。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-251">In addition to chat and collaboration, Teams on VDI with calling and meetings is available with supported virtualization provider platforms.</span></span> <span data-ttu-id="c6f6b-252">支援的功能是以 WebRTC 媒體堆疊和虛擬化提供者實現為基礎。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-252">Supported features are based on the WebRTC media stack and virtualization provider implementation.</span></span> <span data-ttu-id="c6f6b-253">下圖提供架構的概覽。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-253">The following diagram provides an overview of the architecture.</span></span>

![顯示 VDI 架構小組的圖表](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> <span data-ttu-id="c6f6b-255">如果您目前在 VDI 中執行的團隊沒有 AV 優化，且您使用的功能尚不受優化 (例如，在應用程式共用) 中授與控制權，您必須設定 [虛擬化提供者原則] 來關閉 [小組重新導向]。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-255">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set virtualization provider policies to turn off Teams redirection.</span></span> <span data-ttu-id="c6f6b-256">這表示小組媒體會話不會進行優化。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-256">This means that Teams media sessions won't be optimized.</span></span> <span data-ttu-id="c6f6b-257">如需如何設定原則以關閉小組重新導向的相關步驟，請聯絡您的虛擬化提供者。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-257">For steps on how to set policies to turn off Teams redirection, contact your virtualization provider.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="c6f6b-258">網路需求</span><span class="sxs-lookup"><span data-stu-id="c6f6b-258">Network requirements</span></span>

<span data-ttu-id="c6f6b-259">我們建議您評估您的環境，以找出任何風險與需求，這些風險與需求可能會影響您的整體雲端語音及視頻部署。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-259">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="c6f6b-260">使用 [商務用 Skype 網路評估工具](https://www.microsoft.com/download/details.aspx?id=53885) 來測試您的網路是否已準備好供團隊使用。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-260">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="c6f6b-261">若要進一步瞭解如何為團隊準備您的網路，請參閱 [準備貴組織的小組網路](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-261">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="c6f6b-262">從 VDI 上的商務用 Skype 遷移到 VDI 的小組</span><span class="sxs-lookup"><span data-stu-id="c6f6b-262">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="c6f6b-263">如果您是從 VDI 的商務用 Skype 遷移到 VDI 的小組，除了兩個應用程式之間的差異之外，也會有一些差異。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-263">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="c6f6b-264">在商務用 Skype VDI 中，「團隊 VDI」目前不支援的部分功能如下：</span><span class="sxs-lookup"><span data-stu-id="c6f6b-264">Some capabilities that aren't currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="c6f6b-265">使用限制媒體比對的原則控制 VDI 通話體驗</span><span class="sxs-lookup"><span data-stu-id="c6f6b-265">Control of VDI calling experiences with policies for limiting media bitrate</span></span>
- <span data-ttu-id="c6f6b-266">在 VDI 中停用某些防病毒功能的每個平臺原則</span><span class="sxs-lookup"><span data-stu-id="c6f6b-266">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="c6f6b-267">在應用程式共用時提供控制權並加以控制</span><span class="sxs-lookup"><span data-stu-id="c6f6b-267">Give and take control when app sharing</span></span>
- <span data-ttu-id="c6f6b-268">不含音訊的聊天螢幕共用</span><span class="sxs-lookup"><span data-stu-id="c6f6b-268">Screen share from chat without audio</span></span>
- <span data-ttu-id="c6f6b-269">同時進行影片和螢幕共用的傳送和接收</span><span class="sxs-lookup"><span data-stu-id="c6f6b-269">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="c6f6b-270">Chrome 瀏覽器上的小組與 VDI 的小組桌面應用程式</span><span class="sxs-lookup"><span data-stu-id="c6f6b-270">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="c6f6b-271">Chrome 瀏覽器上的小組無法使用 AV 優化來為 VDI 的小組桌面應用程式提供取代。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-271">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="c6f6b-272">聊天與共同作業體驗會如期運作。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-272">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="c6f6b-273">需要媒體時，有一些可能無法在 Chrome 瀏覽器中滿足使用者預期的體驗：</span><span class="sxs-lookup"><span data-stu-id="c6f6b-273">When media is needed, there are some experiences that might not meet user expectations on the Chrome browser:</span></span>

- <span data-ttu-id="c6f6b-274">音訊與視頻資料流程體驗可能不是最佳的。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-274">The audio and video streaming experience might not be optimal.</span></span> <span data-ttu-id="c6f6b-275">使用者可能會遇到延遲或降低品質。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-275">Users might experiences delays or reduced quality.</span></span>
- <span data-ttu-id="c6f6b-276">在瀏覽器設定中無法使用裝置設定。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-276">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="c6f6b-277">裝置管理是透過瀏覽器處理，且需要瀏覽器網站設定中的多項設定。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-277">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="c6f6b-278">裝置設定也可能需要在 Windows 裝置管理中設定。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-278">Device settings might also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="c6f6b-279">VDI 上的小組與聊天與共同作業</span><span class="sxs-lookup"><span data-stu-id="c6f6b-279">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="c6f6b-280">如果您的組織想要只使用團隊中的聊天與共同作業功能，您可以設定使用者層級原則，以關閉小組中的通話與會議功能。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-280">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span> 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="c6f6b-281">設定原則以關閉通話與會議功能</span><span class="sxs-lookup"><span data-stu-id="c6f6b-281">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="c6f6b-282">您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來設定原則。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-282">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="c6f6b-283">可能需要一些時間 (幾個小時) ，原則才能傳播。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-283">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="c6f6b-284">如果您沒有立即看到特定帳戶的變更，請在幾個小時後再試一次。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-284">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="c6f6b-285">[**通話**](teams-calling-policy.md)原則：團隊包含內建的 DisallowCalling 通話原則，其中所有的通話功能都已關閉。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-285">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="c6f6b-286">將 DisallowCalling 原則指派給貴組織中的所有使用虛擬化環境中的小組的使用者。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-286">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="c6f6b-287">[**會議原則**](meeting-policies-in-teams.md)：團隊包含內建的 AllOff 會議原則，其中所有會議功能都已關閉。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-287">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="c6f6b-288">將 AllOff 原則指派給貴組織中的所有使用虛擬化環境中的小組的使用者。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-288">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c6f6b-289">使用 Microsoft 團隊系統管理中心指派原則</span><span class="sxs-lookup"><span data-stu-id="c6f6b-289">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="c6f6b-290">若要將 DisallowCalling 通話原則和 AllOff 會議原則指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="c6f6b-290">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="c6f6b-291">在 Microsoft 團隊系統管理中心的左導覽中，前往 [ **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-291">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="c6f6b-292">按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-292">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="c6f6b-293">請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c6f6b-293">Do the following:</span></span>
    1.  <span data-ttu-id="c6f6b-294">按一下 [ **呼叫原則**] 底下的 [ **DisallowCalling**]。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-294">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2.  <span data-ttu-id="c6f6b-295">按一下 [ **會議原則**] 底下的 [ **AllOff**]。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-295">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="c6f6b-296">按一下 **[** 套用]。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-296">Click **Apply**.</span></span>

<span data-ttu-id="c6f6b-297">若要一次將原則指派給多位使用者：</span><span class="sxs-lookup"><span data-stu-id="c6f6b-297">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="c6f6b-298">在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]\*\*\*\*，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-298">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="c6f6b-299">在 [&#x2713;]\*\*\*\* (核取方塊) 欄中，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-299">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="c6f6b-300">若要選取 [所有使用者]，請按一下表格頂端的 [&#x2713;] (核取方塊)。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-300">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="c6f6b-301">按一下 [編輯設定]\*\*\*\*，進行所需的變更，然後按一下 [套用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-301">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="c6f6b-302">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c6f6b-302">Or, you can also do the following:</span></span>

1. <span data-ttu-id="c6f6b-303">在 Microsoft 團隊系統管理中心的左導覽中，移至您要指派的原則。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-303">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="c6f6b-304">例如：</span><span class="sxs-lookup"><span data-stu-id="c6f6b-304">For example:</span></span>
    - <span data-ttu-id="c6f6b-305">移至 [**語音**  >  **通話原則**]，然後按一下 [ **DisallowCalling**]。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-305">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="c6f6b-306">移至 [**會議**  >  **會議原則**]，然後按一下 [ **AllOff**]。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-306">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
2. <span data-ttu-id="c6f6b-307">選取 [管理使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-307">Select **Manage users**.</span></span>
3. <span data-ttu-id="c6f6b-308">在 [管理使用者]\*\*\*\* 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-308">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="c6f6b-309">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-309">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="c6f6b-310">完成新增使用者後，請按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-310">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="c6f6b-311">使用 PowerShell 指派原則</span><span class="sxs-lookup"><span data-stu-id="c6f6b-311">Assign policies using PowerShell</span></span>

<span data-ttu-id="c6f6b-312">下列範例顯示如何使用 [授與 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) ，將 DisallowCalling 通話原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-312">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="c6f6b-313">若要深入瞭解如何使用 PowerShell 來管理通話原則，請參閱 [設定 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-313">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="c6f6b-314">下列範例顯示如何使用 [授與 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) ，將 AllOff 會議原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-314">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="c6f6b-315">若要深入瞭解如何使用 PowerShell 來管理會議原則，請參閱 [設定 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-315">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a><span data-ttu-id="c6f6b-316">使用聊天與共同作業將小組遷移至 VDI，以使用通話與會議優化團隊</span><span class="sxs-lookup"><span data-stu-id="c6f6b-316">Migrate Teams on VDI with chat and collaboration to optimize Teams with calling and meetings</span></span>

<span data-ttu-id="c6f6b-317">如果您在 VDI 上有現有的小組實現，且您已將使用者層級原則設定為關閉通話與會議功能，且您是透過 AV 優化來遷移至小組，則您必須設定原則來針對 VDI 使用者上的小組開啟通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-317">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Teams with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="c6f6b-318">設定原則以開啟通話與會議功能</span><span class="sxs-lookup"><span data-stu-id="c6f6b-318">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="c6f6b-319">您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來設定通話與會議原則，並指派給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-319">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="c6f6b-320">可能需要一些時間 (幾個小時) ，才能傳播原則變更。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-320">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="c6f6b-321">如果您沒有立即看到特定帳戶的變更，請在幾個小時後再試一次。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-321">If you don't see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="c6f6b-322">[**通話**](teams-calling-policy.md)原則：在團隊中呼叫原則控制使用者可以使用哪些通話功能。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-322">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="c6f6b-323">團隊包含內建的 AllowCalling 通話原則，其中所有的通話功能都已開啟。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-323">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="c6f6b-324">若要開啟所有通話功能，請指派 AllowCalling 原則。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-324">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="c6f6b-325">或者，建立自訂通話原則來開啟您想要的通話功能，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-325">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span> 

<span data-ttu-id="c6f6b-326">[**會議原則**](meeting-policies-in-teams.md)：團隊中的會議原則控制使用者可以建立的會議類型，以及由貴組織中的使用者所排程的會議參與者所提供的功能。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-326">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="c6f6b-327">團隊包含內建的 AllOn 會議原則，其中所有會議功能都已開啟。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-327">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="c6f6b-328">若要開啟所有會議功能，請指派 AllOn 原則。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-328">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="c6f6b-329">或者，建立自訂會議原則來開啟您想要的會議功能，並指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-329">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c6f6b-330">使用 Microsoft 團隊系統管理中心指派原則</span><span class="sxs-lookup"><span data-stu-id="c6f6b-330">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="c6f6b-331">若要將 AllowCalling 通話原則和 AllOn 會議原則指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="c6f6b-331">To assign the AllowCalling calling policy and the AllOn meeting policy to a user:</span></span>

1. <span data-ttu-id="c6f6b-332">在 Microsoft 團隊系統管理中心的左導覽中，前往 [ **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-332">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="c6f6b-333">按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-333">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="c6f6b-334">請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c6f6b-334">Do the following:</span></span>
    1.  <span data-ttu-id="c6f6b-335">按一下 [ **呼叫原則**] 底下的 [ **AllowCalling**]。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-335">Under **Calling policy**, click **AllowCalling**.</span></span>
    2.  <span data-ttu-id="c6f6b-336">按一下 [ **會議原則**] 底下的 [ **AllOn**]。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-336">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="c6f6b-337">按一下 **[** 套用]。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-337">Click **Apply**.</span></span>

<span data-ttu-id="c6f6b-338">若要一次將原則指派給多位使用者：</span><span class="sxs-lookup"><span data-stu-id="c6f6b-338">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="c6f6b-339">在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]\*\*\*\*，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-339">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="c6f6b-340">在 [&#x2713;]\*\*\*\* (核取方塊) 欄中，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-340">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="c6f6b-341">若要選取 [所有使用者]，請按一下表格頂端的 [ **&#x2713;** (核取記號) 。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-341">To select all users, click the **&#x2713;** (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="c6f6b-342">按一下 [編輯設定]\*\*\*\*，進行所需的變更，然後按一下 [套用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-342">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="c6f6b-343">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c6f6b-343">Or, you can also do the following:</span></span>

1. <span data-ttu-id="c6f6b-344">在 Microsoft 團隊系統管理中心的左導覽中，移至您要指派的原則。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-344">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="c6f6b-345">例如：</span><span class="sxs-lookup"><span data-stu-id="c6f6b-345">For example:</span></span>
    - <span data-ttu-id="c6f6b-346">移至 [**語音**  >  **通話原則**]，然後按一下 [ **AllowCalling**]。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-346">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="c6f6b-347">移至 [**會議**  >  **會議原則**]，然後按一下 [ **AllOn**]。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-347">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
2. <span data-ttu-id="c6f6b-348">選取 [管理使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-348">Select **Manage users**.</span></span>
3. <span data-ttu-id="c6f6b-349">在 [管理使用者]\*\*\*\* 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-349">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="c6f6b-350">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-350">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="c6f6b-351">完成新增使用者後，請按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-351">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="c6f6b-352">使用 PowerShell 指派原則</span><span class="sxs-lookup"><span data-stu-id="c6f6b-352">Assign policies using PowerShell</span></span>

<span data-ttu-id="c6f6b-353">下列範例顯示如何使用 [授與 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) ，將 AllowCalling 通話原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-353">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

<span data-ttu-id="c6f6b-354">若要深入瞭解如何使用 PowerShell 來管理通話原則，請參閱 [設定 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-354">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="c6f6b-355">下列範例顯示如何使用 [授與 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) ，將 AllOn 會議原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-355">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

<span data-ttu-id="c6f6b-356">若要深入瞭解如何使用 PowerShell 來管理會議原則，請參閱 [設定 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-356">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="control-fallback-mode-in-teams"></a><span data-ttu-id="c6f6b-357">在團隊中控制回退模式</span><span class="sxs-lookup"><span data-stu-id="c6f6b-357">Control fallback mode in Teams</span></span>

<span data-ttu-id="c6f6b-358">當使用者從不受支援的端點連線時，使用者就會處於 [回退] 模式，但在這種情況下未優化 AV。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-358">When users connect from an unsupported endpoint, the users are in fallback mode, in which AV isn't optimized.</span></span> <span data-ttu-id="c6f6b-359">您可以設定下列其中一個登錄 DWORD 值來停用或啟用回退模式：</span><span class="sxs-lookup"><span data-stu-id="c6f6b-359">You can disable or enable fallback mode by setting one of the following registry DWORD values:</span></span>

- <span data-ttu-id="c6f6b-360">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="c6f6b-360">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span></span>
- <span data-ttu-id="c6f6b-361">HKEY_CURRENT_USER \SOFTWARE\Microsoft\Office\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="c6f6b-361">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span></span>

<span data-ttu-id="c6f6b-362">若要停用回退模式，請將此值設定為 **1**。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-362">To disable fallback mode, set the value to **1**.</span></span> <span data-ttu-id="c6f6b-363">若要只啟用音訊，請將此值設定為 **2**。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-363">To enable audio only, set the value to **2**.</span></span> <span data-ttu-id="c6f6b-364">如果該值不存在，或設定為 **0** (零) ，即表示已啟用回退模式。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-364">If the value isn't present or is set to **0** (zero), fallback mode is enabled.</span></span>

<span data-ttu-id="c6f6b-365">[團隊版本 1.3.00.13565] 和 [更新版本] 中提供此功能。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-365">This feature is available in Teams version 1.3.00.13565 and later.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="c6f6b-366">已知問題與限制</span><span class="sxs-lookup"><span data-stu-id="c6f6b-366">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="c6f6b-367">用戶端部署、安裝和設定</span><span class="sxs-lookup"><span data-stu-id="c6f6b-367">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="c6f6b-368">在每電腦安裝中，VDI 上的團隊不會以非 VDI 團隊用戶端的方式自動更新。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-368">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="c6f6b-369">您必須安裝新的 MSI 來更新 VM 影像，如在 VDI 的 [ [安裝或更新團隊桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi) ] 區段中所述。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-369">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="c6f6b-370">您必須卸載目前的版本，才能更新為較新的版本。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-370">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="c6f6b-371">團隊應該針對每個使用者或每個電腦來部署。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-371">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="c6f6b-372">不支援針對每位使用者和每個電腦並行部署團隊。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-372">Deployment of Teams for concurrent per user and per machine is not supported.</span></span> <span data-ttu-id="c6f6b-373">若要從每個電腦或每位使用者遷移到其中一個模式，請遵循卸載程式，然後重新部署到其中一種模式。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-373">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="c6f6b-374">Windows 虛擬桌面及 VMware 目前不支援 MacOS 和 Linux 的用戶端。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-374">Windows Virtual Desktop and VMware don't support MacOS and Linux-based clients at this time.</span></span>
- <span data-ttu-id="c6f6b-375">Citrix 目前不支援 MacOs 用戶端。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-375">Citrix doesn't support MacOs clients at this time.</span></span>
- <span data-ttu-id="c6f6b-376">Citrix 不支援使用在端點上定義的明確 HTTP proxy。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-376">Citrix doesn't support the use of explicit HTTP proxies defined on an endpoint.</span></span>

### <a name="calling-and-meetings"></a><span data-ttu-id="c6f6b-377">通話與會議</span><span class="sxs-lookup"><span data-stu-id="c6f6b-377">Calling and meetings</span></span>

<span data-ttu-id="c6f6b-378">不支援下列通話與會議功能：</span><span class="sxs-lookup"><span data-stu-id="c6f6b-378">The following calling and meeting features are not supported:</span></span>

- <span data-ttu-id="c6f6b-379">增強的緊急服務</span><span class="sxs-lookup"><span data-stu-id="c6f6b-379">Enhanced emergency services</span></span>
- <span data-ttu-id="c6f6b-380">小組 app 與裝置之間的 HID 按鈕和 LED 控制項</span><span class="sxs-lookup"><span data-stu-id="c6f6b-380">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="c6f6b-381">背景模糊和效果</span><span class="sxs-lookup"><span data-stu-id="c6f6b-381">Background blur and effects</span></span>
- <span data-ttu-id="c6f6b-382">廣播/即時事件</span><span class="sxs-lookup"><span data-stu-id="c6f6b-382">Broadcast/live events</span></span>
- <span data-ttu-id="c6f6b-383">以位置為基礎的路由 (LBR) </span><span class="sxs-lookup"><span data-stu-id="c6f6b-383">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="c6f6b-384">通話駐留</span><span class="sxs-lookup"><span data-stu-id="c6f6b-384">Call park</span></span>
- <span data-ttu-id="c6f6b-385">通話佇列</span><span class="sxs-lookup"><span data-stu-id="c6f6b-385">Call queue</span></span>

> [!NOTE]
> <span data-ttu-id="c6f6b-386">我們正在努力新增目前僅適用于非 VDI 環境中的通話與會議功能。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-386">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="c6f6b-387">這些可能包括更多系統管理員控制品質、其他螢幕共用案例，以及最近新增至團隊的高級功能。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-387">These might include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="c6f6b-388">若要深入瞭解即將推出的功能，請與您的小組代表聯繫。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-388">Contact your Teams representative to learn more about upcoming features.</span></span>

<span data-ttu-id="c6f6b-389">下列是通話與會議的已知問題與限制：</span><span class="sxs-lookup"><span data-stu-id="c6f6b-389">The following are known issues and limitations for calling and meetings:</span></span>

- <span data-ttu-id="c6f6b-390">與商務用 Skype 的互通性限制在音訊通話中;沒有任何視頻模態。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-390">Interoperability with Skype for Business is limited to audio calls; there is no video modality.</span></span>
- <span data-ttu-id="c6f6b-391">在會議或群組通話中只支援單一傳入的視頻資料流程。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-391">Only a single incoming video stream is supported in meetings or group calls.</span></span> <span data-ttu-id="c6f6b-392">當多人傳送影片時，任何指定時間只會顯示主要喇叭的影片。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-392">When multiple people send video, only the dominant speaker's video is shown at any given time.</span></span>
- <span data-ttu-id="c6f6b-393">內送和外寄的視頻資料流程解析度限制為720p 解析度。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-393">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span> <span data-ttu-id="c6f6b-394">這是 WebRTC 的限制。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-394">This is a WebRTC limitation.</span></span>
- <span data-ttu-id="c6f6b-395">只支援來自內送相機或畫面共用資料流程的一個影片串流。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-395">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="c6f6b-396">當有傳入螢幕共用時，會顯示該螢幕共用，而不是主要喇叭的影片。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-396">When there's an incoming screen share, that screen share is shown, instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="c6f6b-397">外寄螢幕共用：</span><span class="sxs-lookup"><span data-stu-id="c6f6b-397">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="c6f6b-398">不支援應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-398">Application sharing is not supported.</span></span>
- <span data-ttu-id="c6f6b-399">授與控制權並加以控制：</span><span class="sxs-lookup"><span data-stu-id="c6f6b-399">Give control and take control:</span></span>
    - <span data-ttu-id="c6f6b-400">在螢幕共用或應用程式共用會話期間不支援。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-400">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="c6f6b-401">在 PowerPoint 共用會話期間支援。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-401">Supported during a PowerPoint sharing session.</span></span>
- <span data-ttu-id="c6f6b-402">僅限 Citrix 限制</span><span class="sxs-lookup"><span data-stu-id="c6f6b-402">Citrix-only limitations</span></span>
    - <span data-ttu-id="c6f6b-403">雙音調多重頻率 (DTMF) 目前不支援與電話系統進行互動。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-403">Dual Tone Multi Frequency (DTMF) interaction with telephony systems is currently not supported.</span></span>
    - <span data-ttu-id="c6f6b-404">在多重監視器設定中進行螢幕共用時，只會共用主要監視器。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-404">When screen sharing in a multi-monitor setup, only the main monitor is shared.</span></span>
    - <span data-ttu-id="c6f6b-405">不支援 CWA 上的高 DPI 縮放。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-405">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="c6f6b-406">針對與 VDI 無關的小組已知問題，請參閱 [貴組織中的支援小組](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-406">For Teams known issues that aren't related to VDI, see [Support Teams in your organization](Known-issues.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c6f6b-407">疑難排解</span><span class="sxs-lookup"><span data-stu-id="c6f6b-407">Troubleshooting</span></span>

### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="c6f6b-408">Citrix 元件疑難排解</span><span class="sxs-lookup"><span data-stu-id="c6f6b-408">Troubleshoot Citrix components</span></span>

<span data-ttu-id="c6f6b-409">如需如何針對 VDA 和 CWA 問題進行疑難排解的資訊，請參閱 [此 Citrix 網站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。</span><span class="sxs-lookup"><span data-stu-id="c6f6b-409">For information on how to troubleshoot VDA and CWA issues, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c6f6b-410">相關主題</span><span class="sxs-lookup"><span data-stu-id="c6f6b-410">Related topics</span></span>

- [<span data-ttu-id="c6f6b-411">使用 MSI 安裝 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="c6f6b-411">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="c6f6b-412">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="c6f6b-412">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="c6f6b-413">在 Windows 虛擬桌面電腦上使用 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="c6f6b-413">Use Microsoft Teams on Windows Virtual desktop</span></span>](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)

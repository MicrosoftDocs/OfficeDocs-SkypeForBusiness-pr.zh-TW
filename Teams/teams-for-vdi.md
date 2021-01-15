---
title: 適用於虛擬桌面架構的 Teams
author: msdmaguire
ms.author: dmaguire
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
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 52c3a4fd1f8ce3871874468590662f223520dc07
ms.sourcegitcommit: 9787b84ab15ee2e14890151e966c81b4a4d43e62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2021
ms.locfileid: "49868348"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="b995b-103">適用於虛擬桌面架構的 Teams</span><span class="sxs-lookup"><span data-stu-id="b995b-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="b995b-104">本文將說明在虛擬化環境中使用 Microsoft 團隊的需求與限制。</span><span class="sxs-lookup"><span data-stu-id="b995b-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="b995b-105">什麼是 VDI？</span><span class="sxs-lookup"><span data-stu-id="b995b-105">What is VDI?</span></span>

<span data-ttu-id="b995b-106">虛擬桌面基礎結構 (VDI) 是虛擬化技術，可在資料中心的中央伺服器上託管桌面作業系統和應用程式。</span><span class="sxs-lookup"><span data-stu-id="b995b-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="b995b-107">這可讓使用者具備完全安全且相容的集中來源，為使用者提供完整的個人化桌面體驗。</span><span class="sxs-lookup"><span data-stu-id="b995b-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>

<span data-ttu-id="b995b-108">虛擬化環境中的 Microsoft 團隊支援聊天與共同作業。</span><span class="sxs-lookup"><span data-stu-id="b995b-108">Microsoft Teams in a virtualized environment supports chat and collaboration.</span></span> <span data-ttu-id="b995b-109">而且有了 Windows 虛擬桌面版、Citrix 和 VMware 平臺，也支援通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="b995b-109">And with the Windows Virtual Desktop, Citrix, and VMware platforms, calling and meeting functionality is also supported.</span></span>

<span data-ttu-id="b995b-110">虛擬化環境中的小組支援多種設定。</span><span class="sxs-lookup"><span data-stu-id="b995b-110">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="b995b-111">其中包括 VDI、專用、共用、持久且非持久的模式。</span><span class="sxs-lookup"><span data-stu-id="b995b-111">These include VDI, dedicated, shared, persistent, and non-persistent modes.</span></span> <span data-ttu-id="b995b-112">功能在連續開發並定期新增，功能將會在未來的幾個月和幾年中擴充。</span><span class="sxs-lookup"><span data-stu-id="b995b-112">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>

<span data-ttu-id="b995b-113">在虛擬化環境中使用團隊的方式可能與在非虛擬化環境中使用團隊稍有不同。</span><span class="sxs-lookup"><span data-stu-id="b995b-113">Using Teams in a virtualized environment might be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="b995b-114">例如，某些高級功能可能無法在虛擬化的環境中使用，而且可能會有不同的影片解析度。</span><span class="sxs-lookup"><span data-stu-id="b995b-114">For example, some advanced features might not be available in a virtualized environment, and video resolution might differ.</span></span>

<span data-ttu-id="b995b-115">若要確保最佳的使用者體驗，請遵循本文中的指導方針。</span><span class="sxs-lookup"><span data-stu-id="b995b-115">To ensure an optimal user experience, follow the guidance in this article.</span></span>

> [!Note]
> <span data-ttu-id="b995b-116">如需有關不同平臺上的團隊 VDI 的詳細資訊，請參閱 [依平臺的團隊功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。</span><span class="sxs-lookup"><span data-stu-id="b995b-116">For details about Teams VDI on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="b995b-117">VDI 元件上的小組</span><span class="sxs-lookup"><span data-stu-id="b995b-117">Teams on VDI components</span></span>

<span data-ttu-id="b995b-118">在虛擬化環境中使用團隊需要下列元件。</span><span class="sxs-lookup"><span data-stu-id="b995b-118">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="b995b-119">**虛擬化 broker**：虛擬化提供者的資源和連線管理員（例如 Azure）</span><span class="sxs-lookup"><span data-stu-id="b995b-119">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="b995b-120">**虛擬桌面**：執行 Microsoft 團隊 (VM) 堆疊的虛擬機器</span><span class="sxs-lookup"><span data-stu-id="b995b-120">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="b995b-121">**瘦用戶端**：使用者使用物理介面的端點</span><span class="sxs-lookup"><span data-stu-id="b995b-121">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="b995b-122">**團隊桌面應用程式**：團隊桌面用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="b995b-122">**Teams desktop app**: The Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="b995b-123">針對 VDI 需求的小組</span><span class="sxs-lookup"><span data-stu-id="b995b-123">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="b995b-124">虛擬化提供者需求</span><span class="sxs-lookup"><span data-stu-id="b995b-124">Virtualization provider requirements</span></span>

<span data-ttu-id="b995b-125">已使用主要的虛擬化解決方案提供者驗證團隊桌面應用程式。</span><span class="sxs-lookup"><span data-stu-id="b995b-125">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="b995b-126">有了多個市場供應商，我們建議您諮詢您的虛擬化解決方案供應商，以確保您符合最低需求。</span><span class="sxs-lookup"><span data-stu-id="b995b-126">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure that you meet the minimum requirements.</span></span>
  
<span data-ttu-id="b995b-127">目前，使用音訊/視頻 (AV) 優化的小組，都是使用 Windows Virtual Desktop、Citrix 和 VMware 進行認證。</span><span class="sxs-lookup"><span data-stu-id="b995b-127">Currently, Teams on VDI with audio/video (AV) optimization is certified with Windows Virtual Desktop, Citrix, and VMware.</span></span> <span data-ttu-id="b995b-128">請參閱本節中的資訊，以確保您符合所有對適當功能的需求。</span><span class="sxs-lookup"><span data-stu-id="b995b-128">Review the information in this section to ensure that you meet all requirements for proper functionality.</span></span>

### <a name="platforms-certified-for-teams"></a><span data-ttu-id="b995b-129">針對團隊認證的平臺</span><span class="sxs-lookup"><span data-stu-id="b995b-129">Platforms certified for Teams</span></span>

<span data-ttu-id="b995b-130">下列平臺擁有小組的虛擬桌面基礎結構解決方案。</span><span class="sxs-lookup"><span data-stu-id="b995b-130">The following platforms have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="b995b-131">平台</span><span class="sxs-lookup"><span data-stu-id="b995b-131">Platform</span></span>|<span data-ttu-id="b995b-132">解</span><span class="sxs-lookup"><span data-stu-id="b995b-132">Solution</span></span>|
|----|---|
|![代表 Microsoft 的標誌](media/microsoft-logo.png)| <span data-ttu-id="b995b-134"><a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows 虛擬桌面</a></span><span class="sxs-lookup"><span data-stu-id="b995b-134"><a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows Virtual Desktop</a></span></span> |
|![代表 Citrix 的標誌](media/citrix-logo.png)| <span data-ttu-id="b995b-136"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 虛擬 App 與桌面</a></span><span class="sxs-lookup"><span data-stu-id="b995b-136"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |
|![代表 VMware 的標誌](media/vmware-logo.png)| <span data-ttu-id="b995b-138"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware 範圍</a></span><span class="sxs-lookup"><span data-stu-id="b995b-138"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a></span></span> |

### <a name="windows-virtual-desktop"></a><span data-ttu-id="b995b-139">Windows 虛擬桌面</span><span class="sxs-lookup"><span data-stu-id="b995b-139">Windows Virtual Desktop</span></span>

<span data-ttu-id="b995b-140">Windows 虛擬桌面電腦為 VDI 上的小組提供 AV 優化。</span><span class="sxs-lookup"><span data-stu-id="b995b-140">Windows Virtual Desktop provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="b995b-141">若要深入瞭解及需求及安裝，請參閱 [在 Windows 虛擬桌面電腦上使用團隊](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)。</span><span class="sxs-lookup"><span data-stu-id="b995b-141">To learn more and requirements and installation, see [Use Teams on Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd).</span></span>

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="b995b-142">Citrix 虛擬 App 與桌面需求</span><span class="sxs-lookup"><span data-stu-id="b995b-142">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="b995b-143">Citrix 虛擬 App 和桌面 (先前稱為 XenApp 和 XenDesktop) 為 VDI 上的小組提供 AV 優化。</span><span class="sxs-lookup"><span data-stu-id="b995b-143">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="b995b-144">借助 Citrix 虛擬 App 和電腦版，VDI 的小組除了聊天與共同作業之外，還支援通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="b995b-144">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="b995b-145">您可以在 [citrix 下載網站](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)下載最新版本的 Citrix 虛擬 App 和桌上型電腦。</span><span class="sxs-lookup"><span data-stu-id="b995b-145">You can download the latest version of Citrix Virtual Apps and Desktops at [the Citrix downloads site](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="b995b-146"> (您必須先登入。 ) 必要元件已捆綁到 [Citrix 工作區應用程式 (CWA) ](https://www.citrix.com/downloads/workspace-app/) 和虛擬傳遞代理程式 (VDA) 預設。</span><span class="sxs-lookup"><span data-stu-id="b995b-146">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="b995b-147">您不需要在 CWA 或 VDA 上安裝任何其他元件或外掛程式。</span><span class="sxs-lookup"><span data-stu-id="b995b-147">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="b995b-148">如需最新的伺服器和用戶端需求，請參閱 [此 Citrix 網站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。</span><span class="sxs-lookup"><span data-stu-id="b995b-148">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a><span data-ttu-id="b995b-149">VMware 地平線工作區和桌面需求</span><span class="sxs-lookup"><span data-stu-id="b995b-149">VMware Horizon Workspace and Desktop requirements</span></span>

<span data-ttu-id="b995b-150">VMware 範圍是一個現代平臺，可在混合式雲端上安全地傳送虛擬桌面和應用程式。</span><span class="sxs-lookup"><span data-stu-id="b995b-150">VMware Horizon is a modern platform for secure delivery of virtual desktops and apps across the hybrid cloud.</span></span> <span data-ttu-id="b995b-151">為提供最佳的使用者體驗，VMware 地平線為小組提供媒體優化功能。</span><span class="sxs-lookup"><span data-stu-id="b995b-151">To offer a great end-user experience, VMware Horizon provides media optimization for Teams.</span></span> <span data-ttu-id="b995b-152">這種優化改善了整個虛擬桌面和應用程式的整體生產力，並可在使用團隊進行通話與會議時改善使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="b995b-152">This optimization improves overall productivity across virtual desktops and apps, and enhances user experience when calling and meeting using Teams.</span></span>

<span data-ttu-id="b995b-153">您可以從 [ [Vmware 下載](https://my.vmware.com/web/vmware/downloads/#all_products) ] 頁面下載最新版本的 VMware。</span><span class="sxs-lookup"><span data-stu-id="b995b-153">You can download the latest version of VMware Horizon from the [VMware Downloads](https://my.vmware.com/web/vmware/downloads/#all_products) page.</span></span> <span data-ttu-id="b995b-154">根據預設，所需的媒體優化元件是集中式代理程式和集中式用戶端的一部分，而且不需要安裝任何其他外掛程式即可使用小組的優化功能。</span><span class="sxs-lookup"><span data-stu-id="b995b-154">The required media optimization components are part of the Horizon Agent and Horizon Client by default and there's no need to install any additional plug-in to use the optimization feature for Teams.</span></span>

<span data-ttu-id="b995b-155">若要取得如何設定團隊媒體優化的最新需求與指示，請參閱 [此 VMware 網站](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)。</span><span class="sxs-lookup"><span data-stu-id="b995b-155">To get the latest requirements and instructions on how to configure media optimization for Teams, see [this VMware website](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html).</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="b995b-156">在 VDI 上安裝或更新小組桌面應用程式</span><span class="sxs-lookup"><span data-stu-id="b995b-156">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="b995b-157">您可以使用每電腦安裝或使用 MSI 套件的每個使用者安裝，部署 VDI 版團隊桌面應用程式。</span><span class="sxs-lookup"><span data-stu-id="b995b-157">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="b995b-158">決定使用哪種方法，取決於您使用的是持續性或非持續設定，以及貴組織的相關功能需求。</span><span class="sxs-lookup"><span data-stu-id="b995b-158">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>

<span data-ttu-id="b995b-159">針對專用的持續設定，這兩種方法都可以運作。</span><span class="sxs-lookup"><span data-stu-id="b995b-159">For a dedicated persistent setup, either approach would work.</span></span> <span data-ttu-id="b995b-160">不過，對於非持續性設定，小組需要每電腦安裝才能有效運作。</span><span class="sxs-lookup"><span data-stu-id="b995b-160">However, for a non-persistent setup, Teams requires a per-machine installation in order to work efficiently.</span></span> <span data-ttu-id="b995b-161">請參閱 [非持續性設定](#non-persistent-setup) 一節。</span><span class="sxs-lookup"><span data-stu-id="b995b-161">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="b995b-162">在安裝每電腦的情況下，自動更新是停用的。</span><span class="sxs-lookup"><span data-stu-id="b995b-162">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="b995b-163">這表示若要更新團隊應用程式，您必須卸載目前的版本，才能更新為較新的版本。</span><span class="sxs-lookup"><span data-stu-id="b995b-163">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="b995b-164">針對每位使用者安裝，會啟用自動更新。</span><span class="sxs-lookup"><span data-stu-id="b995b-164">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="b995b-165">對於大多數的 VDI 部署，我們建議您使用每電腦安裝來部署團隊。</span><span class="sxs-lookup"><span data-stu-id="b995b-165">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="b995b-166">若要更新為最新的團隊版本，請先從最新的團隊版本部署開始卸載程式。</span><span class="sxs-lookup"><span data-stu-id="b995b-166">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="b995b-167">為了讓 VDI 環境中的團隊 AV 優化功能正常運作，瘦用戶端端點必須能夠存取網際網路。</span><span class="sxs-lookup"><span data-stu-id="b995b-167">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="b995b-168">如果瘦用戶端端點無法使用網際網路存取，優化啟動將會失敗。</span><span class="sxs-lookup"><span data-stu-id="b995b-168">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="b995b-169">這表示使用者處於未優化的媒體狀態。</span><span class="sxs-lookup"><span data-stu-id="b995b-169">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="b995b-170">專用持續設定</span><span class="sxs-lookup"><span data-stu-id="b995b-170">Dedicated persistent setup</span></span>

<span data-ttu-id="b995b-171">在專用的持續設定中，使用者會在使用者登出後保留使用者的本機作業系統變更。</span><span class="sxs-lookup"><span data-stu-id="b995b-171">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span> <span data-ttu-id="b995b-172">針對持續性設定，小組支援針對每位使用者和每電腦安裝。</span><span class="sxs-lookup"><span data-stu-id="b995b-172">For persistent setup, Teams supports both per-user and per-machine installation.</span></span>

<span data-ttu-id="b995b-173">以下是建議的最低 VM 設定。</span><span class="sxs-lookup"><span data-stu-id="b995b-173">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="b995b-174">參數</span><span class="sxs-lookup"><span data-stu-id="b995b-174">Parameter</span></span>  |<span data-ttu-id="b995b-175">工作站作業系統</span><span class="sxs-lookup"><span data-stu-id="b995b-175">Workstation operating system</span></span>  |<span data-ttu-id="b995b-176">伺服器作業系統</span><span class="sxs-lookup"><span data-stu-id="b995b-176">Server operating system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b995b-177">vCPU</span><span class="sxs-lookup"><span data-stu-id="b995b-177">vCPU</span></span>   |    <span data-ttu-id="b995b-178">2個核心</span><span class="sxs-lookup"><span data-stu-id="b995b-178">2 cores</span></span>     |  <span data-ttu-id="b995b-179">4、6或8</span><span class="sxs-lookup"><span data-stu-id="b995b-179">4,6, or 8</span></span><br><span data-ttu-id="b995b-180">請務必瞭解基礎非統一記憶體存取 (NUMA) 設定，並據此設定您的 Vm。</span><span class="sxs-lookup"><span data-stu-id="b995b-180">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="b995b-181">RAM</span><span class="sxs-lookup"><span data-stu-id="b995b-181">RAM</span></span>     |   <span data-ttu-id="b995b-182">4 GB</span><span class="sxs-lookup"><span data-stu-id="b995b-182">4 GB</span></span>      | <span data-ttu-id="b995b-183">每位使用者512到 1024 MB</span><span class="sxs-lookup"><span data-stu-id="b995b-183">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="b995b-184">儲存空間</span><span class="sxs-lookup"><span data-stu-id="b995b-184">Storage</span></span>    | <span data-ttu-id="b995b-185">8 GB</span><span class="sxs-lookup"><span data-stu-id="b995b-185">8 GB</span></span>        | <span data-ttu-id="b995b-186">40到 60 GB</span><span class="sxs-lookup"><span data-stu-id="b995b-186">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="b995b-187">非持久性設定</span><span class="sxs-lookup"><span data-stu-id="b995b-187">Non-persistent setup</span></span>

<span data-ttu-id="b995b-188">在非永久性設定中，使用者登出後，使用者的本機作業系統變更就不會保留。</span><span class="sxs-lookup"><span data-stu-id="b995b-188">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="b995b-189">這類設置通常是共用多個使用者會話。</span><span class="sxs-lookup"><span data-stu-id="b995b-189">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="b995b-190">VM 配置會根據使用者數量及可用的物理盒資源而有所不同。</span><span class="sxs-lookup"><span data-stu-id="b995b-190">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="b995b-191">針對非持續性設定，小組桌面應用程式必須安裝在每一台電腦上的黃金影像中。</span><span class="sxs-lookup"><span data-stu-id="b995b-191">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="b995b-192"> (若要深入瞭解，請參閱 [安裝或更新 VDI 區段上的團隊桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi) 。 ) 這可確保在使用者會話期間有效啟動團隊 app。</span><span class="sxs-lookup"><span data-stu-id="b995b-192">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.) This ensures an efficient launch of the Teams app during a user session.</span></span>

<span data-ttu-id="b995b-193">在非持久性設定中使用團隊也需要配置檔案快取管理員，以便高效團隊執行時間資料同步處理。</span><span class="sxs-lookup"><span data-stu-id="b995b-193">Using Teams in a non-persistent setup also requires a profile-caching manager, for efficient Teams runtime data synchronization.</span></span> <span data-ttu-id="b995b-194">高效的資料同步處理可確保在使用者的會話期間，會快取使用者特定的資訊 (例如使用者的資料、設定檔或設定) 。</span><span class="sxs-lookup"><span data-stu-id="b995b-194">Efficient data synchronization ensures that the appropriate user-specific information (such as a user's data, profile, or settings) is cached during the user's session.</span></span> <span data-ttu-id="b995b-195">請確定這兩個資料夾中的資料已同步處理：</span><span class="sxs-lookup"><span data-stu-id="b995b-195">Make sure data in these two folders are synched:</span></span><br>
- <span data-ttu-id="b995b-196">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache) </span><span class="sxs-lookup"><span data-stu-id="b995b-196">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span></span>
- <span data-ttu-id="b995b-197">C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams) </span><span class="sxs-lookup"><span data-stu-id="b995b-197">C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)</span></span>

> [!NOTE]
> <span data-ttu-id="b995b-198">漫遊資料夾 (或者，如果您使用的是資料夾重新導向，則需要使用緩存管理員) ，以確保團隊 app 擁有執行應用程式所需的執行時間資料和檔案。</span><span class="sxs-lookup"><span data-stu-id="b995b-198">A roaming folder (or, if you are using folder redirection, a caching manager) is required to ensure that the Teams app has the runtime data and files required to run the application.</span></span> <span data-ttu-id="b995b-199">這對於減少網路延遲問題或網路難題是必要的，否則會因無法使用的資料和檔案而造成應用程式錯誤和緩慢的體驗。</span><span class="sxs-lookup"><span data-stu-id="b995b-199">This is necessary to mitigate network latency issues or network glitches, which would otherwise cause application errors and a slow experience due to unavailable data and files.</span></span>

<span data-ttu-id="b995b-200">有許多可用的緩存管理器解決方案。</span><span class="sxs-lookup"><span data-stu-id="b995b-200">There are a variety of caching manager solutions available.</span></span> <span data-ttu-id="b995b-201">例如， [FSLogix](https://docs.microsoft.com/fslogix/overview)。</span><span class="sxs-lookup"><span data-stu-id="b995b-201">For example, [FSLogix](https://docs.microsoft.com/fslogix/overview).</span></span> <span data-ttu-id="b995b-202">如需特定的設定指示，請參閱您的快取管理員提供者。</span><span class="sxs-lookup"><span data-stu-id="b995b-202">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="b995b-203">小組快取內容排除清單以進行非持續設定</span><span class="sxs-lookup"><span data-stu-id="b995b-203">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="b995b-204">從 [團隊快取] 資料夾（% appdata%/Microsoft/Teams.）中排除下列各項：</span><span class="sxs-lookup"><span data-stu-id="b995b-204">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span> <span data-ttu-id="b995b-205">排除這些專案有助於減少使用者的快取大小，進一步優化您的非持久設定。</span><span class="sxs-lookup"><span data-stu-id="b995b-205">Excluding these items helps reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="b995b-206">.txt 檔案</span><span class="sxs-lookup"><span data-stu-id="b995b-206">.txt files</span></span>
- <span data-ttu-id="b995b-207">媒體堆疊資料夾</span><span class="sxs-lookup"><span data-stu-id="b995b-207">Media-stack folder</span></span>
- <span data-ttu-id="b995b-208">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache) </span><span class="sxs-lookup"><span data-stu-id="b995b-208">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)</span></span>

### <a name="microsoft-365-apps-for-enterprise-considerations"></a><span data-ttu-id="b995b-209">適用于企業考慮的 Microsoft 365 應用程式</span><span class="sxs-lookup"><span data-stu-id="b995b-209">Microsoft 365 Apps for enterprise considerations</span></span>

<span data-ttu-id="b995b-210">當您使用 VDI 上的企業版 Microsoft 365 應用程式部署團隊時，請考慮下列事項。</span><span class="sxs-lookup"><span data-stu-id="b995b-210">Consider the following when you deploy Teams with Microsoft 365 Apps for enterprise on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="b995b-211">透過企業版 Microsoft 365 應用程式的新部署團隊</span><span class="sxs-lookup"><span data-stu-id="b995b-211">New deployments of Teams through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="b995b-212">在透過企業版 Microsoft 365 應用程式部署團隊前，您必須先卸載任何預先存在的團隊應用程式（如果它們是使用各電腦安裝來部署）。</span><span class="sxs-lookup"><span data-stu-id="b995b-212">Before you deploy Teams through Microsoft 365 Apps for enterprise, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="b995b-213">團隊透過適用于企業的 Microsoft 365 應用程式是針對每位使用者安裝的。</span><span class="sxs-lookup"><span data-stu-id="b995b-213">Teams through Microsoft 365 Apps for enterprise is installed per-user.</span></span> <span data-ttu-id="b995b-214">若要深入瞭解，請參閱 [安裝或更新 VDI 區段上的小組桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi) 。</span><span class="sxs-lookup"><span data-stu-id="b995b-214">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a><span data-ttu-id="b995b-215">透過適用于企業更新的 Microsoft 365 應用程式部署團隊</span><span class="sxs-lookup"><span data-stu-id="b995b-215">Teams deployments through Microsoft 365 Apps for enterprise updates</span></span>

<span data-ttu-id="b995b-216">團隊也會新增至企業版 Microsoft 365 應用程式的現有安裝。</span><span class="sxs-lookup"><span data-stu-id="b995b-216">Teams is also being added to existing installations of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="b995b-217">由於 [企業版 Microsoft 365 應用程式] 只會針對每位使用者安裝小組，請參閱在 [VDI 上安裝或更新小組桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi) 。</span><span class="sxs-lookup"><span data-stu-id="b995b-217">Since Microsoft 365 Apps for enterprise installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="b995b-218">使用團隊進行每電腦安裝和適用于企業的 Microsoft 365 應用程式</span><span class="sxs-lookup"><span data-stu-id="b995b-218">Using Teams with per-machine installation and Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="b995b-219">適用于企業的 Microsoft 365 應用程式不支援小組的每電腦安裝。</span><span class="sxs-lookup"><span data-stu-id="b995b-219">Microsoft 365 Apps for enterprise doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="b995b-220">若要使用 [每電腦安裝]，您必須從適用于企業的 Microsoft 365 App 中排除團隊。</span><span class="sxs-lookup"><span data-stu-id="b995b-220">To use per-machine installation, you must exclude Teams from Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="b995b-221">請參閱將 [團隊傳統型應用程式部署至 VM](#deploy-the-teams-desktop-app-to-the-vm) ，以及 [如何透過適用于企業的 Microsoft 365 應用程式排除團隊部署](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) 。</span><span class="sxs-lookup"><span data-stu-id="b995b-221">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Microsoft 365 Apps for enterprise](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="b995b-222">如何透過適用于企業的 Microsoft 365 應用程式排除團隊部署</span><span class="sxs-lookup"><span data-stu-id="b995b-222">How to exclude Teams deployment through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="b995b-223">若要深入瞭解團隊和適用于企業的 Microsoft 365 應用程式，請參閱 [如何將團隊從新安裝的企業版 microsoft 365 應用程式中排除](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) ，並 [使用群組原則來控制團隊的安裝](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="b995b-223">To learn more about Teams and Microsoft 365 Apps for enterprise, see [How to exclude Teams from new installations of Microsoft 365 Apps for enterprise](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="b995b-224">將團隊桌面應用程式部署到 VM</span><span class="sxs-lookup"><span data-stu-id="b995b-224">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="b995b-225">使用下列其中一個連結，下載與您的 VDI VM 作業系統相符的團隊 MSI 套件：</span><span class="sxs-lookup"><span data-stu-id="b995b-225">Download the Teams MSI package that matches your VDI VM operating system using one of the following links:</span></span>

    - [<span data-ttu-id="b995b-226">32位版本</span><span class="sxs-lookup"><span data-stu-id="b995b-226">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [<span data-ttu-id="b995b-227">64位版本</span><span class="sxs-lookup"><span data-stu-id="b995b-227">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > <span data-ttu-id="b995b-228">若為政府群，請參閱 [使用 Microsoft 端點 Configuration Manager 安裝 Microsoft 團隊](msi-deployment.md) ，以取得 MSI 檔案的下載連結。</span><span class="sxs-lookup"><span data-stu-id="b995b-228">For government clouds, see [Install Microsoft Teams using Microsoft Endpoint Configuration Manager](msi-deployment.md) for the download links to the MSI files.</span></span>

    <span data-ttu-id="b995b-229">所需的小組桌面應用程式最低版本為版本1.3.00.4461。</span><span class="sxs-lookup"><span data-stu-id="b995b-229">The minimum version of the Teams desktop app that's required is version 1.3.00.4461.</span></span> <span data-ttu-id="b995b-230">舊版中不支援 (PSTN 保留。 ) </span><span class="sxs-lookup"><span data-stu-id="b995b-230">(PSTN hold isn't supported in earlier versions.)</span></span>

2. <span data-ttu-id="b995b-231">執行下列其中一項命令，將 MSI 安裝到 VDI VM：</span><span class="sxs-lookup"><span data-stu-id="b995b-231">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="b995b-232">依使用者安裝 (預設) </span><span class="sxs-lookup"><span data-stu-id="b995b-232">Per-user installation (default)</span></span>
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        <span data-ttu-id="b995b-233">這個處理常式是預設安裝，可將團隊安裝到% AppData% user 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="b995b-233">This process is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="b995b-234">此時，黃金影像設定就完成了。</span><span class="sxs-lookup"><span data-stu-id="b995b-234">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="b995b-235">在非持續設定上，小組無法針對每位使用者安裝正常運作。</span><span class="sxs-lookup"><span data-stu-id="b995b-235">Teams won't work properly with per-user installation on a non-persistent setup.</span></span>

    - <span data-ttu-id="b995b-236">每電腦安裝</span><span class="sxs-lookup"><span data-stu-id="b995b-236">Per-machine installation</span></span>

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        <span data-ttu-id="b995b-237">此程式會將團隊安裝至64位作業系統上的 [x86) ] 資料夾 (的程式檔案，以及32位作業系統上的 [程式檔案] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="b995b-237">This process installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="b995b-238">此時，黃金影像設定就完成了。</span><span class="sxs-lookup"><span data-stu-id="b995b-238">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="b995b-239">針對非持久的安裝，必須針對每台電腦安裝團隊。</span><span class="sxs-lookup"><span data-stu-id="b995b-239">Installing Teams per-machine is required for non-persistent setups.</span></span>

        <span data-ttu-id="b995b-240">下次互動式登入會話會啟動團隊並要求認證。</span><span class="sxs-lookup"><span data-stu-id="b995b-240">The next interactive logon session starts Teams and asks for credentials.</span></span>

        > [!NOTE]
        > <span data-ttu-id="b995b-241">這些範例也會使用 **ALLUSERS = 1** 參數。</span><span class="sxs-lookup"><span data-stu-id="b995b-241">These examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="b995b-242">當您設定此參數時，[小組] Machine-Wide 安裝程式會出現在 [控制台] 的 [程式和功能] 中，以及電腦所有使用者的 [Windows 設定] & 功能。</span><span class="sxs-lookup"><span data-stu-id="b995b-242">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="b995b-243">如果有管理員認證，所有使用者都可以卸載小組。</span><span class="sxs-lookup"><span data-stu-id="b995b-243">All users can then uninstall Teams if they have admin credentials.</span></span>
        <span data-ttu-id="b995b-244">請務必瞭解 **ALLUSERS = 1** 與 **ALLUSER = 1** 之間的差異。</span><span class="sxs-lookup"><span data-stu-id="b995b-244">It's important to understand the difference between **ALLUSERS=1** and **ALLUSER=1**.</span></span> <span data-ttu-id="b995b-245">您可以在非 VDI 和 VDI 環境中使用 **ALLUSERS = 1** 參數，而 **ALLUSER = 1** 參數只會在 VDI 環境中用來指定每電腦安裝。</span><span class="sxs-lookup"><span data-stu-id="b995b-245">The **ALLUSERS=1** parameter can be used in non-VDI and VDI environments, while the **ALLUSER=1** parameter is used only in VDI environments to specify a per-machine installation.</span></span>

3. <span data-ttu-id="b995b-246">從 VDI VM 卸載 MSI。</span><span class="sxs-lookup"><span data-stu-id="b995b-246">Uninstall the MSI from the VDI VM.</span></span> <span data-ttu-id="b995b-247">有兩種方式可以卸載小組。</span><span class="sxs-lookup"><span data-stu-id="b995b-247">There are two ways to uninstall Teams.</span></span>

    - <span data-ttu-id="b995b-248">PowerShell 腳本：您可以使用 [此 PowerShell 腳本](scripts/powershell-script-deployment-cleanup.md) 卸載小組，並移除使用者的 [小組] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="b995b-248">PowerShell script: You can use [this PowerShell script](scripts/powershell-script-deployment-cleanup.md) to uninstall Teams and remove the Teams folder for a user.</span></span> <span data-ttu-id="b995b-249">針對在電腦上安裝團隊的每個使用者設定檔執行腳本。</span><span class="sxs-lookup"><span data-stu-id="b995b-249">Run the script for each user profile in which Teams was installed on the computer.</span></span>
    - <span data-ttu-id="b995b-250">命令列：執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="b995b-250">Command line: Run the following command.</span></span>
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      <span data-ttu-id="b995b-251">這個程式會將小組從程式檔案卸載 (x86) 資料夾或 Program Files 資料夾，視作業系統環境而定。</span><span class="sxs-lookup"><span data-stu-id="b995b-251">This process uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="b995b-252">VDI 效能考慮的小組</span><span class="sxs-lookup"><span data-stu-id="b995b-252">Teams on VDI performance considerations</span></span>

<span data-ttu-id="b995b-253">有多種虛擬化設定設定，每個都有不同的焦點可供優化。</span><span class="sxs-lookup"><span data-stu-id="b995b-253">There are a variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="b995b-254">例如，配置可能會將焦點放在使用者密度上。</span><span class="sxs-lookup"><span data-stu-id="b995b-254">For example, a configuration might focus on user density.</span></span> <span data-ttu-id="b995b-255">規劃時，請考慮下列事項，以根據貴組織的工作負載需求來優化您的設定。</span><span class="sxs-lookup"><span data-stu-id="b995b-255">When planning, consider the following to help optimize your setup based on your organization's workload needs.</span></span>

- <span data-ttu-id="b995b-256">最低需求：某些工作負載可能需要使用超過最低需求的資源進行設定。</span><span class="sxs-lookup"><span data-stu-id="b995b-256">Minimum requirement: Some workloads might require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="b995b-257">例如，使用需要更多計算資源之應用程式之開發人員的工作負載。</span><span class="sxs-lookup"><span data-stu-id="b995b-257">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="b995b-258">相依性：這些專案包括在小組桌面應用程式以外的基礎結構、工作負載及其他環境考慮因素的相依性。</span><span class="sxs-lookup"><span data-stu-id="b995b-258">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="b995b-259">VDI 上停用的功能：團隊會針對 VDI 停用 GPU 密集型功能，這可以協助改善暫時的 CPU 利用率。</span><span class="sxs-lookup"><span data-stu-id="b995b-259">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="b995b-260">下列功能已停用：</span><span class="sxs-lookup"><span data-stu-id="b995b-260">The following features are disabled:</span></span>
    - <span data-ttu-id="b995b-261">團隊 CSS 動畫</span><span class="sxs-lookup"><span data-stu-id="b995b-261">Teams CSS animation</span></span>
    - <span data-ttu-id="b995b-262">Giphy 自動啟動</span><span class="sxs-lookup"><span data-stu-id="b995b-262">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="b995b-263">VDI 上的小組與通話與會議</span><span class="sxs-lookup"><span data-stu-id="b995b-263">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="b995b-264">除了聊天與共同作業之外，您還可以使用支援的虛擬化提供者平臺提供通話和會議的 VDI 小組。</span><span class="sxs-lookup"><span data-stu-id="b995b-264">In addition to chat and collaboration, Teams on VDI with calling and meetings is available with supported virtualization provider platforms.</span></span> <span data-ttu-id="b995b-265">支援的功能是以 WebRTC 媒體堆疊和虛擬化提供者實現為基礎。</span><span class="sxs-lookup"><span data-stu-id="b995b-265">Supported features are based on the WebRTC media stack and virtualization provider implementation.</span></span> <span data-ttu-id="b995b-266">下圖提供架構的概覽。</span><span class="sxs-lookup"><span data-stu-id="b995b-266">The following diagram provides an overview of the architecture.</span></span>

![顯示 VDI 架構小組的圖表](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> <span data-ttu-id="b995b-268">如果您目前在 VDI 中執行的團隊沒有 AV 優化，且您使用的功能尚不受優化 (例如，在應用程式共用) 中授與控制權，您必須設定 [虛擬化提供者原則] 來關閉 [小組重新導向]。</span><span class="sxs-lookup"><span data-stu-id="b995b-268">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set virtualization provider policies to turn off Teams redirection.</span></span> <span data-ttu-id="b995b-269">這表示小組媒體會話不會進行優化。</span><span class="sxs-lookup"><span data-stu-id="b995b-269">This means that Teams media sessions won't be optimized.</span></span> <span data-ttu-id="b995b-270">如需如何設定原則以關閉小組重新導向的相關步驟，請聯絡您的虛擬化提供者。</span><span class="sxs-lookup"><span data-stu-id="b995b-270">For steps on how to set policies to turn off Teams redirection, contact your virtualization provider.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="b995b-271">網路需求</span><span class="sxs-lookup"><span data-stu-id="b995b-271">Network requirements</span></span>

<span data-ttu-id="b995b-272">我們建議您評估您的環境，以找出任何風險與需求，這些風險與需求可能會影響您的整體雲端語音及視頻部署。</span><span class="sxs-lookup"><span data-stu-id="b995b-272">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="b995b-273">使用 [商務用 Skype 網路評估工具](https://www.microsoft.com/download/details.aspx?id=53885) 來測試您的網路是否已準備好供團隊使用。</span><span class="sxs-lookup"><span data-stu-id="b995b-273">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="b995b-274">若要進一步瞭解如何為團隊準備您的網路，請參閱 [準備貴組織的小組網路](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="b995b-274">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="b995b-275">從 VDI 上的商務用 Skype 遷移到 VDI 的小組</span><span class="sxs-lookup"><span data-stu-id="b995b-275">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="b995b-276">如果您是從 VDI 的商務用 Skype 遷移到 VDI 的小組，除了兩個應用程式之間的差異之外，也會有一些差異。</span><span class="sxs-lookup"><span data-stu-id="b995b-276">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="b995b-277">在商務用 Skype VDI 中，「團隊 VDI」目前不支援的部分功能如下：</span><span class="sxs-lookup"><span data-stu-id="b995b-277">Some capabilities that aren't currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="b995b-278">在 VDI 中停用某些防病毒功能的每個平臺原則</span><span class="sxs-lookup"><span data-stu-id="b995b-278">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="b995b-279">在應用程式共用時提供控制權並加以控制</span><span class="sxs-lookup"><span data-stu-id="b995b-279">Give and take control when app sharing</span></span>
- <span data-ttu-id="b995b-280">不含音訊的聊天螢幕共用</span><span class="sxs-lookup"><span data-stu-id="b995b-280">Screen share from chat without audio</span></span>
- <span data-ttu-id="b995b-281">同時進行影片和螢幕共用的傳送和接收</span><span class="sxs-lookup"><span data-stu-id="b995b-281">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="b995b-282">Chrome 瀏覽器上的小組與 VDI 的小組桌面應用程式</span><span class="sxs-lookup"><span data-stu-id="b995b-282">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="b995b-283">Chrome 瀏覽器上的小組無法使用 AV 優化來為 VDI 的小組桌面應用程式提供取代。</span><span class="sxs-lookup"><span data-stu-id="b995b-283">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="b995b-284">聊天與共同作業體驗會如期運作。</span><span class="sxs-lookup"><span data-stu-id="b995b-284">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="b995b-285">需要媒體時，有一些可能無法在 Chrome 瀏覽器中滿足使用者預期的體驗：</span><span class="sxs-lookup"><span data-stu-id="b995b-285">When media is needed, there are some experiences that might not meet user expectations on the Chrome browser:</span></span>

- <span data-ttu-id="b995b-286">音訊與視頻資料流程體驗可能不是最佳的。</span><span class="sxs-lookup"><span data-stu-id="b995b-286">The audio and video streaming experience might not be optimal.</span></span> <span data-ttu-id="b995b-287">使用者可能會遇到延遲或降低品質。</span><span class="sxs-lookup"><span data-stu-id="b995b-287">Users might experiences delays or reduced quality.</span></span>
- <span data-ttu-id="b995b-288">在瀏覽器設定中無法使用裝置設定。</span><span class="sxs-lookup"><span data-stu-id="b995b-288">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="b995b-289">裝置管理是透過瀏覽器處理，且需要瀏覽器網站設定中的多項設定。</span><span class="sxs-lookup"><span data-stu-id="b995b-289">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="b995b-290">裝置設定也可能需要在 Windows 裝置管理中設定。</span><span class="sxs-lookup"><span data-stu-id="b995b-290">Device settings might also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="b995b-291">VDI 上的小組與聊天與共同作業</span><span class="sxs-lookup"><span data-stu-id="b995b-291">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="b995b-292">如果您的組織想要只使用團隊中的聊天與共同作業功能，您可以設定使用者層級原則，以關閉小組中的通話與會議功能。</span><span class="sxs-lookup"><span data-stu-id="b995b-292">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span> 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="b995b-293">設定原則以關閉通話與會議功能</span><span class="sxs-lookup"><span data-stu-id="b995b-293">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="b995b-294">您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來設定原則。</span><span class="sxs-lookup"><span data-stu-id="b995b-294">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="b995b-295">可能需要一些時間 (幾個小時) ，原則才能傳播。</span><span class="sxs-lookup"><span data-stu-id="b995b-295">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="b995b-296">如果您沒有立即看到特定帳戶的變更，請在幾個小時後再試一次。</span><span class="sxs-lookup"><span data-stu-id="b995b-296">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="b995b-297">[**通話**](teams-calling-policy.md)原則：團隊包含內建的 DisallowCalling 通話原則，其中所有的通話功能都已關閉。</span><span class="sxs-lookup"><span data-stu-id="b995b-297">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="b995b-298">將 DisallowCalling 原則指派給貴組織中的所有使用虛擬化環境中的小組的使用者。</span><span class="sxs-lookup"><span data-stu-id="b995b-298">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="b995b-299">[**會議原則**](meeting-policies-in-teams.md)：團隊包含內建的 AllOff 會議原則，其中所有會議功能都已關閉。</span><span class="sxs-lookup"><span data-stu-id="b995b-299">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="b995b-300">將 AllOff 原則指派給貴組織中的所有使用虛擬化環境中的小組的使用者。</span><span class="sxs-lookup"><span data-stu-id="b995b-300">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b995b-301">使用 Microsoft 團隊系統管理中心指派原則</span><span class="sxs-lookup"><span data-stu-id="b995b-301">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="b995b-302">若要將 DisallowCalling 通話原則和 AllOff 會議原則指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="b995b-302">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="b995b-303">在 Microsoft 團隊系統管理中心的左導覽中，前往 [ **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="b995b-303">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="b995b-304">按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]。</span><span class="sxs-lookup"><span data-stu-id="b995b-304">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="b995b-305">請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b995b-305">Do the following:</span></span>
    1.  <span data-ttu-id="b995b-306">按一下 [ **呼叫原則**] 底下的 [ **DisallowCalling**]。</span><span class="sxs-lookup"><span data-stu-id="b995b-306">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2.  <span data-ttu-id="b995b-307">按一下 [ **會議原則**] 底下的 [ **AllOff**]。</span><span class="sxs-lookup"><span data-stu-id="b995b-307">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="b995b-308">按一下 **[** 套用]。</span><span class="sxs-lookup"><span data-stu-id="b995b-308">Click **Apply**.</span></span>

<span data-ttu-id="b995b-309">若要一次將原則指派給多位使用者：</span><span class="sxs-lookup"><span data-stu-id="b995b-309">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="b995b-310">在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="b995b-310">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="b995b-311">在 [&#x2713;] (核取方塊) 欄中，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="b995b-311">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="b995b-312">若要選取 [所有使用者]，請按一下表格頂端的 [&#x2713;] (核取方塊)。</span><span class="sxs-lookup"><span data-stu-id="b995b-312">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="b995b-313">按一下 [編輯設定]，進行所需的變更，然後按一下 [套用]。</span><span class="sxs-lookup"><span data-stu-id="b995b-313">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="b995b-314">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b995b-314">Or, you can also do the following:</span></span>

1. <span data-ttu-id="b995b-315">在 Microsoft 團隊系統管理中心的左導覽中，移至您要指派的原則。</span><span class="sxs-lookup"><span data-stu-id="b995b-315">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="b995b-316">例如：</span><span class="sxs-lookup"><span data-stu-id="b995b-316">For example:</span></span>
    - <span data-ttu-id="b995b-317">移至 [**語音**  >  **通話原則**]，然後按一下 [ **DisallowCalling**]。</span><span class="sxs-lookup"><span data-stu-id="b995b-317">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="b995b-318">移至 [**會議**  >  **會議原則**]，然後按一下 [ **AllOff**]。</span><span class="sxs-lookup"><span data-stu-id="b995b-318">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
2. <span data-ttu-id="b995b-319">選取 [管理使用者]。</span><span class="sxs-lookup"><span data-stu-id="b995b-319">Select **Manage users**.</span></span>
3. <span data-ttu-id="b995b-320">在 [管理使用者] 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="b995b-320">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="b995b-321">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="b995b-321">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="b995b-322">完成新增使用者後，請按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="b995b-322">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="b995b-323">使用 PowerShell 指派原則</span><span class="sxs-lookup"><span data-stu-id="b995b-323">Assign policies using PowerShell</span></span>

<span data-ttu-id="b995b-324">下列範例顯示如何使用 [授與 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) ，將 DisallowCalling 通話原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="b995b-324">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="b995b-325">若要深入瞭解如何使用 PowerShell 來管理通話原則，請參閱 [設定 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="b995b-325">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="b995b-326">下列範例顯示如何使用 [授與 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) ，將 AllOff 會議原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="b995b-326">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="b995b-327">若要深入瞭解如何使用 PowerShell 來管理會議原則，請參閱 [設定 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="b995b-327">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a><span data-ttu-id="b995b-328">使用聊天與共同作業將小組遷移至 VDI，以使用通話與會議優化團隊</span><span class="sxs-lookup"><span data-stu-id="b995b-328">Migrate Teams on VDI with chat and collaboration to optimize Teams with calling and meetings</span></span>

<span data-ttu-id="b995b-329">如果您在 VDI 上有現有的小組實現，且您已將使用者層級原則設定為關閉通話與會議功能，且您是透過 AV 優化來遷移至小組，則您必須設定原則來針對 VDI 使用者上的小組開啟通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="b995b-329">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Teams with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="b995b-330">設定原則以開啟通話與會議功能</span><span class="sxs-lookup"><span data-stu-id="b995b-330">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="b995b-331">您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來設定通話與會議原則，並指派給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="b995b-331">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="b995b-332">可能需要一些時間 (幾個小時) ，才能傳播原則變更。</span><span class="sxs-lookup"><span data-stu-id="b995b-332">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="b995b-333">如果您沒有立即看到特定帳戶的變更，請在幾個小時後再試一次。</span><span class="sxs-lookup"><span data-stu-id="b995b-333">If you don't see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="b995b-334">[**通話**](teams-calling-policy.md)原則：在團隊中呼叫原則控制使用者可以使用哪些通話功能。</span><span class="sxs-lookup"><span data-stu-id="b995b-334">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="b995b-335">團隊包含內建的 AllowCalling 通話原則，其中所有的通話功能都已開啟。</span><span class="sxs-lookup"><span data-stu-id="b995b-335">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="b995b-336">若要開啟所有通話功能，請指派 AllowCalling 原則。</span><span class="sxs-lookup"><span data-stu-id="b995b-336">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="b995b-337">或者，建立自訂通話原則來開啟您想要的通話功能，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="b995b-337">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span> 

<span data-ttu-id="b995b-338">[**會議原則**](meeting-policies-in-teams.md)：團隊中的會議原則控制使用者可以建立的會議類型，以及由貴組織中的使用者所排程的會議參與者所提供的功能。</span><span class="sxs-lookup"><span data-stu-id="b995b-338">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="b995b-339">團隊包含內建的 AllOn 會議原則，其中所有會議功能都已開啟。</span><span class="sxs-lookup"><span data-stu-id="b995b-339">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="b995b-340">若要開啟所有會議功能，請指派 AllOn 原則。</span><span class="sxs-lookup"><span data-stu-id="b995b-340">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="b995b-341">或者，建立自訂會議原則來開啟您想要的會議功能，並指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="b995b-341">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b995b-342">使用 Microsoft 團隊系統管理中心指派原則</span><span class="sxs-lookup"><span data-stu-id="b995b-342">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="b995b-343">若要將 AllowCalling 通話原則和 AllOn 會議原則指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="b995b-343">To assign the AllowCalling calling policy and the AllOn meeting policy to a user:</span></span>

1. <span data-ttu-id="b995b-344">在 Microsoft 團隊系統管理中心的左導覽中，前往 [ **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="b995b-344">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="b995b-345">按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]。</span><span class="sxs-lookup"><span data-stu-id="b995b-345">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="b995b-346">請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b995b-346">Do the following:</span></span>
    1.  <span data-ttu-id="b995b-347">按一下 [ **呼叫原則**] 底下的 [ **AllowCalling**]。</span><span class="sxs-lookup"><span data-stu-id="b995b-347">Under **Calling policy**, click **AllowCalling**.</span></span>
    2.  <span data-ttu-id="b995b-348">按一下 [ **會議原則**] 底下的 [ **AllOn**]。</span><span class="sxs-lookup"><span data-stu-id="b995b-348">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="b995b-349">按一下 **[** 套用]。</span><span class="sxs-lookup"><span data-stu-id="b995b-349">Click **Apply**.</span></span>

<span data-ttu-id="b995b-350">若要一次將原則指派給多位使用者：</span><span class="sxs-lookup"><span data-stu-id="b995b-350">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="b995b-351">在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="b995b-351">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="b995b-352">在 [&#x2713;] (核取方塊) 欄中，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="b995b-352">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="b995b-353">若要選取 [所有使用者]，請按一下表格頂端的 [ **&#x2713;** (核取記號) 。</span><span class="sxs-lookup"><span data-stu-id="b995b-353">To select all users, click the **&#x2713;** (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="b995b-354">按一下 [編輯設定]，進行所需的變更，然後按一下 [套用]。</span><span class="sxs-lookup"><span data-stu-id="b995b-354">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="b995b-355">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b995b-355">Or, you can also do the following:</span></span>

1. <span data-ttu-id="b995b-356">在 Microsoft 團隊系統管理中心的左導覽中，移至您要指派的原則。</span><span class="sxs-lookup"><span data-stu-id="b995b-356">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="b995b-357">例如：</span><span class="sxs-lookup"><span data-stu-id="b995b-357">For example:</span></span>
    - <span data-ttu-id="b995b-358">移至 [**語音**  >  **通話原則**]，然後按一下 [ **AllowCalling**]。</span><span class="sxs-lookup"><span data-stu-id="b995b-358">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="b995b-359">移至 [**會議**  >  **會議原則**]，然後按一下 [ **AllOn**]。</span><span class="sxs-lookup"><span data-stu-id="b995b-359">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
2. <span data-ttu-id="b995b-360">選取 [管理使用者]。</span><span class="sxs-lookup"><span data-stu-id="b995b-360">Select **Manage users**.</span></span>
3. <span data-ttu-id="b995b-361">在 [管理使用者] 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="b995b-361">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="b995b-362">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="b995b-362">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="b995b-363">完成新增使用者後，請按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="b995b-363">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="b995b-364">使用 PowerShell 指派原則</span><span class="sxs-lookup"><span data-stu-id="b995b-364">Assign policies using PowerShell</span></span>

<span data-ttu-id="b995b-365">下列範例顯示如何使用 [授與 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) ，將 AllowCalling 通話原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="b995b-365">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

<span data-ttu-id="b995b-366">若要深入瞭解如何使用 PowerShell 來管理通話原則，請參閱 [設定 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="b995b-366">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="b995b-367">下列範例顯示如何使用 [授與 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) ，將 AllOn 會議原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="b995b-367">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

<span data-ttu-id="b995b-368">若要深入瞭解如何使用 PowerShell 來管理會議原則，請參閱 [設定 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="b995b-368">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="control-fallback-mode-in-teams"></a><span data-ttu-id="b995b-369">在團隊中控制回退模式</span><span class="sxs-lookup"><span data-stu-id="b995b-369">Control fallback mode in Teams</span></span>

<span data-ttu-id="b995b-370">當使用者從不受支援的端點連線時，使用者就會處於 [回退] 模式，但在這種情況下未優化 AV。</span><span class="sxs-lookup"><span data-stu-id="b995b-370">When users connect from an unsupported endpoint, the users are in fallback mode, in which AV isn't optimized.</span></span> <span data-ttu-id="b995b-371">您可以設定下列其中一個登錄 DWORD 值來停用或啟用回退模式：</span><span class="sxs-lookup"><span data-stu-id="b995b-371">You can disable or enable fallback mode by setting one of the following registry DWORD values:</span></span>

- <span data-ttu-id="b995b-372">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="b995b-372">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span></span>
- <span data-ttu-id="b995b-373">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="b995b-373">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span></span>

<span data-ttu-id="b995b-374">若要停用回退模式，請將此值設定為 **1**。</span><span class="sxs-lookup"><span data-stu-id="b995b-374">To disable fallback mode, set the value to **1**.</span></span> <span data-ttu-id="b995b-375">若要只啟用音訊，請將此值設定為 **2**。</span><span class="sxs-lookup"><span data-stu-id="b995b-375">To enable audio only, set the value to **2**.</span></span> <span data-ttu-id="b995b-376">如果該值不存在，或設定為 **0** (零) ，即表示已啟用回退模式。</span><span class="sxs-lookup"><span data-stu-id="b995b-376">If the value isn't present or is set to **0** (zero), fallback mode is enabled.</span></span>

<span data-ttu-id="b995b-377">[團隊版本 1.3.00.13565] 和 [更新版本] 中提供此功能。</span><span class="sxs-lookup"><span data-stu-id="b995b-377">This feature is available in Teams version 1.3.00.13565 and later.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="b995b-378">已知問題與限制</span><span class="sxs-lookup"><span data-stu-id="b995b-378">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="b995b-379">用戶端部署、安裝和設定</span><span class="sxs-lookup"><span data-stu-id="b995b-379">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="b995b-380">在每電腦安裝中，VDI 上的團隊不會以非 VDI 團隊用戶端的方式自動更新。</span><span class="sxs-lookup"><span data-stu-id="b995b-380">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="b995b-381">您必須安裝新的 MSI 來更新 VM 影像，如在 VDI 的 [ [安裝或更新團隊桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi) ] 區段中所述。</span><span class="sxs-lookup"><span data-stu-id="b995b-381">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="b995b-382">您必須卸載目前的版本，才能更新為較新的版本。</span><span class="sxs-lookup"><span data-stu-id="b995b-382">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="b995b-383">團隊應該針對每個使用者或每個電腦來部署。</span><span class="sxs-lookup"><span data-stu-id="b995b-383">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="b995b-384">不支援針對每位使用者和每個電腦並行部署團隊。</span><span class="sxs-lookup"><span data-stu-id="b995b-384">Deployment of Teams for concurrent per user and per machine is not supported.</span></span> <span data-ttu-id="b995b-385">若要從每個電腦或每位使用者遷移到其中一個模式，請遵循卸載程式，然後重新部署到其中一種模式。</span><span class="sxs-lookup"><span data-stu-id="b995b-385">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="b995b-386">Windows 虛擬桌面及 VMware 目前不支援 MacOS 和 Linux 的用戶端。</span><span class="sxs-lookup"><span data-stu-id="b995b-386">Windows Virtual Desktop and VMware don't support MacOS and Linux-based clients at this time.</span></span>
- <span data-ttu-id="b995b-387">Citrix 目前不支援 MacOs 用戶端。</span><span class="sxs-lookup"><span data-stu-id="b995b-387">Citrix doesn't support MacOs clients at this time.</span></span>
- <span data-ttu-id="b995b-388">Citrix 不支援使用在端點上定義的明確 HTTP proxy。</span><span class="sxs-lookup"><span data-stu-id="b995b-388">Citrix doesn't support the use of explicit HTTP proxies defined on an endpoint.</span></span>

### <a name="calling-and-meetings"></a><span data-ttu-id="b995b-389">通話與會議</span><span class="sxs-lookup"><span data-stu-id="b995b-389">Calling and meetings</span></span>

<span data-ttu-id="b995b-390">不支援下列通話與會議功能：</span><span class="sxs-lookup"><span data-stu-id="b995b-390">The following calling and meeting features are not supported:</span></span>

- <span data-ttu-id="b995b-391">增強的緊急服務</span><span class="sxs-lookup"><span data-stu-id="b995b-391">Enhanced emergency services</span></span>
- <span data-ttu-id="b995b-392">小組 app 與裝置之間的 HID 按鈕和 LED 控制項</span><span class="sxs-lookup"><span data-stu-id="b995b-392">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="b995b-393">背景模糊和效果</span><span class="sxs-lookup"><span data-stu-id="b995b-393">Background blur and effects</span></span>
- <span data-ttu-id="b995b-394">廣播與即時事件製造者與簡報者角色</span><span class="sxs-lookup"><span data-stu-id="b995b-394">Broadcast and live event producer and presenter roles</span></span>
- <span data-ttu-id="b995b-395">Location-Based 路由 (LBR) </span><span class="sxs-lookup"><span data-stu-id="b995b-395">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="b995b-396">通話駐留</span><span class="sxs-lookup"><span data-stu-id="b995b-396">Call park</span></span>
- <span data-ttu-id="b995b-397">通話佇列</span><span class="sxs-lookup"><span data-stu-id="b995b-397">Call queue</span></span>
- <span data-ttu-id="b995b-398">共用系統音訊/電腦音效</span><span class="sxs-lookup"><span data-stu-id="b995b-398">Shared system audio/computer sound</span></span>
- <span data-ttu-id="b995b-399">直接路由的媒體旁路</span><span class="sxs-lookup"><span data-stu-id="b995b-399">Media bypass for Direct Routing</span></span>

> [!NOTE]
> <span data-ttu-id="b995b-400">我們正在努力新增目前僅適用于非 VDI 環境中的通話與會議功能。</span><span class="sxs-lookup"><span data-stu-id="b995b-400">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="b995b-401">這些可能包括更多系統管理員控制品質、其他螢幕共用案例，以及最近新增至團隊的高級功能。</span><span class="sxs-lookup"><span data-stu-id="b995b-401">These might include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="b995b-402">若要深入瞭解即將推出的功能，請與您的小組代表聯繫。</span><span class="sxs-lookup"><span data-stu-id="b995b-402">Contact your Teams representative to learn more about upcoming features.</span></span>

<span data-ttu-id="b995b-403">下列是通話與會議的已知問題與限制：</span><span class="sxs-lookup"><span data-stu-id="b995b-403">The following are known issues and limitations for calling and meetings:</span></span>

- <span data-ttu-id="b995b-404">與商務用 Skype 的互通性限制在音訊通話中;沒有任何視頻模態。</span><span class="sxs-lookup"><span data-stu-id="b995b-404">Interoperability with Skype for Business is limited to audio calls; there is no video modality.</span></span>
- <span data-ttu-id="b995b-405">在會議或群組通話中只支援單一傳入的視頻資料流程。</span><span class="sxs-lookup"><span data-stu-id="b995b-405">Only a single incoming video stream is supported in meetings or group calls.</span></span> <span data-ttu-id="b995b-406">當多人傳送影片時，任何指定時間只會顯示主要喇叭的影片。</span><span class="sxs-lookup"><span data-stu-id="b995b-406">When multiple people send video, only the dominant speaker's video is shown at any given time.</span></span>
- <span data-ttu-id="b995b-407">內送和外寄的視頻資料流程解析度限制為720p 解析度。</span><span class="sxs-lookup"><span data-stu-id="b995b-407">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span> <span data-ttu-id="b995b-408">這是 WebRTC 的限制。</span><span class="sxs-lookup"><span data-stu-id="b995b-408">This is a WebRTC limitation.</span></span>
- <span data-ttu-id="b995b-409">只支援來自內送相機或畫面共用資料流程的一個影片串流。</span><span class="sxs-lookup"><span data-stu-id="b995b-409">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="b995b-410">當有傳入螢幕共用時，會顯示該螢幕共用，而不是主要喇叭的影片。</span><span class="sxs-lookup"><span data-stu-id="b995b-410">When there's an incoming screen share, that screen share is shown, instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="b995b-411">如果裝置已中斷連線，然後重新連接，小組就不會切換成使用使用者選取的最後一個音訊裝置。</span><span class="sxs-lookup"><span data-stu-id="b995b-411">Teams doesn't switch to use the last audio device that a user selected, if the device is disconnected, and then reconnected.</span></span>
- <span data-ttu-id="b995b-412">外寄螢幕共用：</span><span class="sxs-lookup"><span data-stu-id="b995b-412">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="b995b-413">不支援應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="b995b-413">Application sharing is not supported.</span></span>
- <span data-ttu-id="b995b-414">授與控制權並加以控制：</span><span class="sxs-lookup"><span data-stu-id="b995b-414">Give control and take control:</span></span>
    - <span data-ttu-id="b995b-415">在螢幕共用或應用程式共用會話期間不支援。</span><span class="sxs-lookup"><span data-stu-id="b995b-415">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="b995b-416">在 PowerPoint 共用會話期間支援。</span><span class="sxs-lookup"><span data-stu-id="b995b-416">Supported during a PowerPoint sharing session.</span></span>
- <span data-ttu-id="b995b-417">僅限 Citrix 限制</span><span class="sxs-lookup"><span data-stu-id="b995b-417">Citrix-only limitations</span></span>
    - <span data-ttu-id="b995b-418">在多重監視器設定中進行螢幕共用時，只會共用主要監視器。</span><span class="sxs-lookup"><span data-stu-id="b995b-418">When screen sharing in a multi-monitor setup, only the main monitor is shared.</span></span>
    - <span data-ttu-id="b995b-419">不支援 CWA 上的高 DPI 縮放。</span><span class="sxs-lookup"><span data-stu-id="b995b-419">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="b995b-420">針對與 VDI 無關的小組已知問題，請參閱 [貴組織中的支援小組](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="b995b-420">For Teams known issues that aren't related to VDI, see [Support Teams in your organization](Known-issues.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b995b-421">疑難排解</span><span class="sxs-lookup"><span data-stu-id="b995b-421">Troubleshooting</span></span>

### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="b995b-422">Citrix 元件疑難排解</span><span class="sxs-lookup"><span data-stu-id="b995b-422">Troubleshoot Citrix components</span></span>

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a><span data-ttu-id="b995b-423">團隊當機或團隊登入畫面為空白</span><span class="sxs-lookup"><span data-stu-id="b995b-423">Teams crashes or the Teams sign in screen is blank</span></span>

<span data-ttu-id="b995b-424">這是 Citrix VDA 版本1906和1909的已知問題。</span><span class="sxs-lookup"><span data-stu-id="b995b-424">This is a known issue with Citrix VDA versions 1906 and 1909.</span></span> <span data-ttu-id="b995b-425">若要解決此問題，請新增下列登錄 DWORD 值，並將它設為 204 (十六進位) 。</span><span class="sxs-lookup"><span data-stu-id="b995b-425">To work around this issue, add the following registry DWORD value, and set it to 204 (hexadecimal).</span></span>

<span data-ttu-id="b995b-426">HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe</span><span class="sxs-lookup"><span data-stu-id="b995b-426">HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe</span></span>

<span data-ttu-id="b995b-427">然後，重新開機 VDA。</span><span class="sxs-lookup"><span data-stu-id="b995b-427">Then, restart VDA.</span></span> <span data-ttu-id="b995b-428">若要深入瞭解，請參閱此 Citrix 支援文章、 [疑難排解 HDX 優化小組](https://support.citrix.com/article/CTX253754)。</span><span class="sxs-lookup"><span data-stu-id="b995b-428">To learn more, see this Citrix support article, [Troubleshooting HDX optimization for Teams](https://support.citrix.com/article/CTX253754).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b995b-429">相關主題</span><span class="sxs-lookup"><span data-stu-id="b995b-429">Related topics</span></span>

- [<span data-ttu-id="b995b-430">使用 MSI 安裝 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="b995b-430">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="b995b-431">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="b995b-431">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="b995b-432">在 Windows 虛擬桌面電腦上使用 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="b995b-432">Use Microsoft Teams on Windows Virtual desktop</span></span>](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)

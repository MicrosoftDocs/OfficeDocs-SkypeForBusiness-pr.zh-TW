---
title: 虛擬化桌面基礎結構的團隊
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: 瞭解如何在虛擬化桌面基礎結構（VDI）環境中執行 Microsoft 團隊。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 479f272f45c4ac7c8f84f0aa26fe923ea16ff3d7
ms.sourcegitcommit: df552697ae9c8c01c40f816bbe98b251db147199
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/25/2020
ms.locfileid: "42278006"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="dcb04-103">虛擬化桌面基礎結構的團隊</span><span class="sxs-lookup"><span data-stu-id="dcb04-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="dcb04-104">本文將說明在虛擬化環境中使用 Microsoft 團隊的需求與限制。</span><span class="sxs-lookup"><span data-stu-id="dcb04-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="dcb04-105">什麼是 VDI？</span><span class="sxs-lookup"><span data-stu-id="dcb04-105">What is VDI?</span></span>

<span data-ttu-id="dcb04-106">虛擬桌面基礎結構（VDI）是虛擬化技術，可在資料中心的中央伺服器上託管桌面作業系統和應用程式。</span><span class="sxs-lookup"><span data-stu-id="dcb04-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="dcb04-107">這可讓使用者具備完全安全且相容的集中來源，為使用者提供完整的個人化桌面體驗。</span><span class="sxs-lookup"><span data-stu-id="dcb04-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>
 
<span data-ttu-id="dcb04-108">虛擬化環境中的 Microsoft 團隊支援聊天與共同作業，而且還支援 Citrix 平臺、通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="dcb04-108">Microsoft Teams in a virtualized environment supports chat and collaboration, and with the Citrix platform, calling and meeting functionality are also supported.</span></span>

<span data-ttu-id="dcb04-109">虛擬化環境中的小組支援多種設定。</span><span class="sxs-lookup"><span data-stu-id="dcb04-109">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="dcb04-110">其中包括 VDI、專用、共用、持久且不持久的模式。</span><span class="sxs-lookup"><span data-stu-id="dcb04-110">These include VDI, dedicated, shared, persistent and non-persistent modes.</span></span> <span data-ttu-id="dcb04-111">功能在連續開發並定期新增，功能將會在未來的幾個月和幾年中擴充。</span><span class="sxs-lookup"><span data-stu-id="dcb04-111">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>
 
<span data-ttu-id="dcb04-112">在虛擬化環境中使用團隊的方式可能與在非虛擬化環境中使用團隊稍有不同。</span><span class="sxs-lookup"><span data-stu-id="dcb04-112">Using Teams in a virtualized environment may be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="dcb04-113">例如，某些高級功能可能無法在虛擬化環境中使用，而且可能會有不同的影片解析度。</span><span class="sxs-lookup"><span data-stu-id="dcb04-113">For example, some advanced features may not be available in a virtualized environment and video resolution may differ.</span></span> <span data-ttu-id="dcb04-114">若要確保最佳的使用者體驗，請遵循本文中的指導方針。</span><span class="sxs-lookup"><span data-stu-id="dcb04-114">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="dcb04-115">VDI 元件上的小組</span><span class="sxs-lookup"><span data-stu-id="dcb04-115">Teams on VDI components</span></span>

<span data-ttu-id="dcb04-116">在虛擬化環境中使用團隊需要下列元件。</span><span class="sxs-lookup"><span data-stu-id="dcb04-116">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="dcb04-117">**虛擬化 broker**：虛擬化提供者的資源和連線管理員（例如 Azure）</span><span class="sxs-lookup"><span data-stu-id="dcb04-117">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="dcb04-118">**虛擬桌面**：執行 Microsoft 團隊的虛擬機器（VM）堆疊</span><span class="sxs-lookup"><span data-stu-id="dcb04-118">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="dcb04-119">**瘦用戶端**：使用者使用物理介面的端點</span><span class="sxs-lookup"><span data-stu-id="dcb04-119">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="dcb04-120">**團隊桌面應用程式**：這是團隊桌面用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="dcb04-120">**Teams desktop app**: This is the Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="dcb04-121">針對 VDI 需求的小組</span><span class="sxs-lookup"><span data-stu-id="dcb04-121">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="dcb04-122">虛擬化提供者需求</span><span class="sxs-lookup"><span data-stu-id="dcb04-122">Virtualization provider requirements</span></span>

<span data-ttu-id="dcb04-123">已使用主要的虛擬化解決方案提供者驗證團隊桌面應用程式。</span><span class="sxs-lookup"><span data-stu-id="dcb04-123">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="dcb04-124">有了多個市場供應商，我們建議您諮詢您的虛擬化解決方案供應商，以確保符合最低需求。</span><span class="sxs-lookup"><span data-stu-id="dcb04-124">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure minimum requirements are met.</span></span>
  
<span data-ttu-id="dcb04-125">目前，具有音訊/視頻（AV）優化的團隊在使用 Citrix 進行認證。</span><span class="sxs-lookup"><span data-stu-id="dcb04-125">Currently, Teams on VDI with audio/video (AV) optimization is certified with Citrix.</span></span> <span data-ttu-id="dcb04-126">請參閱本節中的資訊，以確保同時滿足 Citrix 與團隊需求，才能正常功能。</span><span class="sxs-lookup"><span data-stu-id="dcb04-126">Review the information in this section to ensure both Citrix and Teams requirements are met for proper functionality.</span></span>

### <a name="partners-certified-for-teams"></a><span data-ttu-id="dcb04-127">針對團隊認證的合作夥伴</span><span class="sxs-lookup"><span data-stu-id="dcb04-127">Partners certified for Teams</span></span>

<span data-ttu-id="dcb04-128">下列合作夥伴擁有小組的虛擬桌面基礎結構解決方案。</span><span class="sxs-lookup"><span data-stu-id="dcb04-128">The following partners have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="dcb04-129">Partner</span><span class="sxs-lookup"><span data-stu-id="dcb04-129">Partner</span></span>|<span data-ttu-id="dcb04-130">合作夥伴解決方案</span><span class="sxs-lookup"><span data-stu-id="dcb04-130">Partner solution</span></span>|
|----|---|
|![代表 Citrix 的標誌](media/citrix.png)| <span data-ttu-id="dcb04-132"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 虛擬 App 與桌面</a></span><span class="sxs-lookup"><span data-stu-id="dcb04-132"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="dcb04-133">Citrix 虛擬 App 與桌面需求</span><span class="sxs-lookup"><span data-stu-id="dcb04-133">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="dcb04-134">Citrix 虛擬 App 與桌上型電腦（先前稱為 XenApp 和 XenDesktop）為 VDI 上的小組提供 AV 優化。</span><span class="sxs-lookup"><span data-stu-id="dcb04-134">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="dcb04-135">借助 Citrix 虛擬 App 和電腦版，VDI 的小組除了聊天與共同作業之外，還支援通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="dcb04-135">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="dcb04-136">您可以在[這裡](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)下載最新版本的 Citrix 虛擬 App 和桌上型電腦。</span><span class="sxs-lookup"><span data-stu-id="dcb04-136">You can download the latest version of Citrix Virtual Apps and Desktops [here](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="dcb04-137">（您必須先登入。）預設會將必要的元件捆綁到[Citrix 工作區應用程式（CWA）](https://www.citrix.com/downloads/workspace-app/)和虛擬傳遞代理程式（VDA）。</span><span class="sxs-lookup"><span data-stu-id="dcb04-137">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="dcb04-138">您不需要在 CWA 或 VDA 上安裝任何其他元件或外掛程式。</span><span class="sxs-lookup"><span data-stu-id="dcb04-138">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="dcb04-139">如需最新的伺服器和用戶端需求，請參閱[此 Citrix 網站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。</span><span class="sxs-lookup"><span data-stu-id="dcb04-139">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="dcb04-140">在 VDI 上安裝或更新小組桌面應用程式</span><span class="sxs-lookup"><span data-stu-id="dcb04-140">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="dcb04-141">您可以使用每電腦安裝或使用 MSI 套件的每個使用者安裝，部署 VDI 版團隊桌面應用程式。</span><span class="sxs-lookup"><span data-stu-id="dcb04-141">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="dcb04-142">決定使用哪種方法，取決於您使用的是持續性或非持續設定，以及貴組織的相關功能需求。</span><span class="sxs-lookup"><span data-stu-id="dcb04-142">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>
<span data-ttu-id="dcb04-143">針對專用的持續設定，這兩種方法都可以運作。</span><span class="sxs-lookup"><span data-stu-id="dcb04-143">For a dedicated persistent setup, either approach would work.</span></span>  <span data-ttu-id="dcb04-144">不過，對於非持續性設定，小組需要使用每電腦安裝才能有效運作。</span><span class="sxs-lookup"><span data-stu-id="dcb04-144">However, for a non-persistent setup, per-machine installation is required for Teams to work efficiently.</span></span> <span data-ttu-id="dcb04-145">請參閱[非持續性設定](#non-persistent-setup)一節。</span><span class="sxs-lookup"><span data-stu-id="dcb04-145">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="dcb04-146">在安裝每電腦的情況下，自動更新是停用的。</span><span class="sxs-lookup"><span data-stu-id="dcb04-146">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="dcb04-147">這表示若要更新團隊應用程式，您必須卸載目前的版本，才能更新為較新的版本。</span><span class="sxs-lookup"><span data-stu-id="dcb04-147">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="dcb04-148">針對每位使用者安裝，會啟用自動更新。</span><span class="sxs-lookup"><span data-stu-id="dcb04-148">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="dcb04-149">對於大多數的 VDI 部署，我們建議您使用每電腦安裝來部署團隊。</span><span class="sxs-lookup"><span data-stu-id="dcb04-149">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="dcb04-150">若要更新為最新的團隊版本，請先從最新的團隊版本部署開始卸載程式。</span><span class="sxs-lookup"><span data-stu-id="dcb04-150">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="dcb04-151">為了讓 VDI 環境中的團隊 AV 優化功能正常運作，瘦用戶端端點必須能夠存取網際網路。</span><span class="sxs-lookup"><span data-stu-id="dcb04-151">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="dcb04-152">如果瘦用戶端端點無法使用網際網路存取，優化啟動將會失敗。</span><span class="sxs-lookup"><span data-stu-id="dcb04-152">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="dcb04-153">這表示使用者處於未優化的媒體狀態。</span><span class="sxs-lookup"><span data-stu-id="dcb04-153">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="dcb04-154">專用持續設定</span><span class="sxs-lookup"><span data-stu-id="dcb04-154">Dedicated persistent setup</span></span>

<span data-ttu-id="dcb04-155">在專用的持續設定中，使用者會在使用者登出後保留使用者的本機作業系統變更。</span><span class="sxs-lookup"><span data-stu-id="dcb04-155">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span>  <span data-ttu-id="dcb04-156">針對持續設定，團隊支援每個使用者和每電腦的安裝。</span><span class="sxs-lookup"><span data-stu-id="dcb04-156">For persistent setup, Teams support both per-user and per-machine installation.</span></span>

<span data-ttu-id="dcb04-157">以下是建議的最低 VM 設定。</span><span class="sxs-lookup"><span data-stu-id="dcb04-157">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="dcb04-158">參數</span><span class="sxs-lookup"><span data-stu-id="dcb04-158">Parameter</span></span>  |<span data-ttu-id="dcb04-159">工作站作業系統</span><span class="sxs-lookup"><span data-stu-id="dcb04-159">Workstation operating system</span></span>  |<span data-ttu-id="dcb04-160">伺服器作業系統</span><span class="sxs-lookup"><span data-stu-id="dcb04-160">Server operation system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="dcb04-161">vCPU</span><span class="sxs-lookup"><span data-stu-id="dcb04-161">vCPU</span></span>   |    <span data-ttu-id="dcb04-162">2個核心</span><span class="sxs-lookup"><span data-stu-id="dcb04-162">2 cores</span></span>     |  <span data-ttu-id="dcb04-163">4、6或8</span><span class="sxs-lookup"><span data-stu-id="dcb04-163">4,6, or 8</span></span><br><span data-ttu-id="dcb04-164">瞭解基礎非一致性記憶體存取（NUMA）設定並據此設定您的 Vm 非常重要。</span><span class="sxs-lookup"><span data-stu-id="dcb04-164">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="dcb04-165">RAM</span><span class="sxs-lookup"><span data-stu-id="dcb04-165">RAM</span></span>     |   <span data-ttu-id="dcb04-166">4 GB</span><span class="sxs-lookup"><span data-stu-id="dcb04-166">4 GB</span></span>      | <span data-ttu-id="dcb04-167">每位使用者512到 1024 MB</span><span class="sxs-lookup"><span data-stu-id="dcb04-167">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="dcb04-168">儲存空間</span><span class="sxs-lookup"><span data-stu-id="dcb04-168">Storage</span></span>    | <span data-ttu-id="dcb04-169">8 GB</span><span class="sxs-lookup"><span data-stu-id="dcb04-169">8 GB</span></span>        | <span data-ttu-id="dcb04-170">40到 60 GB</span><span class="sxs-lookup"><span data-stu-id="dcb04-170">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="dcb04-171">非持久性設定</span><span class="sxs-lookup"><span data-stu-id="dcb04-171">Non-persistent setup</span></span>

<span data-ttu-id="dcb04-172">在非永久性設定中，使用者登出後，使用者的本機作業系統變更就不會保留。</span><span class="sxs-lookup"><span data-stu-id="dcb04-172">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="dcb04-173">這類設置通常是共用多個使用者會話。</span><span class="sxs-lookup"><span data-stu-id="dcb04-173">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="dcb04-174">VM 配置會根據使用者數量及可用的物理盒資源而有所不同。</span><span class="sxs-lookup"><span data-stu-id="dcb04-174">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="dcb04-175">針對非持續性設定，小組桌面應用程式必須安裝在每一台電腦上的黃金影像中。</span><span class="sxs-lookup"><span data-stu-id="dcb04-175">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="dcb04-176">（若要深入瞭解，請參閱[安裝或更新 VDI 區段上的小組桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi)）。</span><span class="sxs-lookup"><span data-stu-id="dcb04-176">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section).</span></span> <span data-ttu-id="dcb04-177">這可確保在使用者會話期間有效啟動團隊 app。</span><span class="sxs-lookup"><span data-stu-id="dcb04-177">This ensures an efficient launch of the Teams app during a user session.</span></span> <span data-ttu-id="dcb04-178">將團隊與非持久設定搭配使用時，也需要設定檔的快取管理員，才能高效地進行團隊執行時間資料同步處理。這樣可確保在使用者會話期間會快取適當的使用者特定資訊（例如，使用者資料、設定檔和設定）。</span><span class="sxs-lookup"><span data-stu-id="dcb04-178">Using Teams with a non-persistent setup also requires a profile caching manager for efficient Teams runtime data sync. This ensures that the appropriate user-specific information (for example, user data, profile, and settings) are cached during the user session.</span></span>  <span data-ttu-id="dcb04-179">有許多可用的快取管理員解決方案。</span><span class="sxs-lookup"><span data-stu-id="dcb04-179">There are variety of caching manager solutions available.</span></span> <span data-ttu-id="dcb04-180">例如， [FSLogix](https://docs.microsoft.com/fslogix/overview)。</span><span class="sxs-lookup"><span data-stu-id="dcb04-180">For example, [FSLogix](https://docs.microsoft.com/fslogix/overview).</span></span> <span data-ttu-id="dcb04-181">如需特定的設定指示，請參閱您的快取管理員提供者。</span><span class="sxs-lookup"><span data-stu-id="dcb04-181">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="dcb04-182">小組快取內容排除清單以進行非持續設定</span><span class="sxs-lookup"><span data-stu-id="dcb04-182">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="dcb04-183">從 [團隊快取] 資料夾（% appdata%/Microsoft/Teams.）中排除下列各項：</span><span class="sxs-lookup"><span data-stu-id="dcb04-183">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span>  <span data-ttu-id="dcb04-184">排除這些說明可減少使用者的快取大小，進一步優化您的非持久設定。</span><span class="sxs-lookup"><span data-stu-id="dcb04-184">Excluding these help reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="dcb04-185">.txt 檔案</span><span class="sxs-lookup"><span data-stu-id="dcb04-185">.txt files</span></span>
- <span data-ttu-id="dcb04-186">媒體堆疊資料夾</span><span class="sxs-lookup"><span data-stu-id="dcb04-186">Media-stack folder</span></span>

### <a name="office-365-proplus-considerations"></a><span data-ttu-id="dcb04-187">Office 365 專業增強版考慮</span><span class="sxs-lookup"><span data-stu-id="dcb04-187">Office 365 ProPlus considerations</span></span>

<span data-ttu-id="dcb04-188">在 VDI 上使用 Office 365 專業增強版部署團隊時，請考慮下列事項。</span><span class="sxs-lookup"><span data-stu-id="dcb04-188">Consider the following when you deploy Teams with Office 365 ProPlus on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-office-365-proplus"></a><span data-ttu-id="dcb04-189">透過 Office 365 專業增強版新的團隊部署</span><span class="sxs-lookup"><span data-stu-id="dcb04-189">New deployments of Teams through Office 365 ProPlus</span></span>

<span data-ttu-id="dcb04-190">在透過 Office 365 專業增強版部署團隊之前，您必須先卸載任何預先存在的團隊應用程式（如果這些 app 是使用各電腦安裝來部署的）。</span><span class="sxs-lookup"><span data-stu-id="dcb04-190">Before you deploy Teams through Office 365 ProPlus, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="dcb04-191">透過 Office 365 專業增強版的團隊是針對每位使用者所安裝。</span><span class="sxs-lookup"><span data-stu-id="dcb04-191">Teams through Office 365 ProPlus is installed per-user.</span></span> <span data-ttu-id="dcb04-192">若要深入瞭解，請參閱[安裝或更新 VDI 區段上的小組桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi)。</span><span class="sxs-lookup"><span data-stu-id="dcb04-192">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-office-365-proplus-updates"></a><span data-ttu-id="dcb04-193">透過 Office 365 專業增強版更新的團隊部署</span><span class="sxs-lookup"><span data-stu-id="dcb04-193">Teams deployments through Office 365 ProPlus updates</span></span>

<span data-ttu-id="dcb04-194">團隊也會新增至 Office 365 專業增強版的現有安裝。</span><span class="sxs-lookup"><span data-stu-id="dcb04-194">Teams is also being added to existing installations of Office 365 ProPlus.</span></span> <span data-ttu-id="dcb04-195">由於 Office 365 專業增強版只會針對每位使用者安裝小組，請參閱[安裝或更新 VDI 區段上的小組桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi)。</span><span class="sxs-lookup"><span data-stu-id="dcb04-195">Since Office 365 ProPlus installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-office-365-proplus"></a><span data-ttu-id="dcb04-196">使用團隊進行每電腦安裝和 Office 365 專業增強版</span><span class="sxs-lookup"><span data-stu-id="dcb04-196">Using Teams with per-machine installation and Office 365 ProPlus</span></span>

<span data-ttu-id="dcb04-197">Office 365 專業增強版不支援小組的每電腦安裝。</span><span class="sxs-lookup"><span data-stu-id="dcb04-197">Office 365 ProPlus doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="dcb04-198">若要使用 [每電腦安裝]，您必須從 Office 365 專業增強版中排除團隊。</span><span class="sxs-lookup"><span data-stu-id="dcb04-198">To use per-machine installation, you must exclude Teams from Office 365 ProPlus.</span></span> <span data-ttu-id="dcb04-199">請參閱將[團隊桌面應用程式部署到 VM](#deploy-the-teams-desktop-app-to-the-vm) ，以及[如何透過 Office 365 專業增強版區段排除團隊部署](#how-to-exclude-teams-deployment-through-office-365-proplus)。</span><span class="sxs-lookup"><span data-stu-id="dcb04-199">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Office 365 ProPlus](#how-to-exclude-teams-deployment-through-office-365-proplus) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-office-365-proplus"></a><span data-ttu-id="dcb04-200">如何透過 Office 365 專業增強版排除團隊部署</span><span class="sxs-lookup"><span data-stu-id="dcb04-200">How to exclude Teams deployment through Office 365 ProPlus</span></span>

<span data-ttu-id="dcb04-201">若要深入瞭解團隊和 Office 365 專業增強版，請參閱[如何從新安裝的 Office 365 專業增強版中排除團隊](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus)，並[使用群組原則來控制團隊的安裝](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="dcb04-201">To learn more about Teams and Office 365 ProPlus, see [How to exclude Teams from new installations of Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="dcb04-202">將團隊桌面應用程式部署到 VM</span><span class="sxs-lookup"><span data-stu-id="dcb04-202">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="dcb04-203">使用下列其中一個連結，下載與您的 VDI VM 作業系統相符的團隊 MSI 套件：</span><span class="sxs-lookup"><span data-stu-id="dcb04-203">Download the Teams MSI package that matches your VDI VM operating system using one of the following links:</span></span>

    - [<span data-ttu-id="dcb04-204">32位版本</span><span class="sxs-lookup"><span data-stu-id="dcb04-204">32-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows/1.2.00.32462/Teams_windows.msi)
    - [<span data-ttu-id="dcb04-205">64位版本</span><span class="sxs-lookup"><span data-stu-id="dcb04-205">64-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows-x64/1.2.00.32462/Teams_windows_x64.msi)

    <span data-ttu-id="dcb04-206">所需的小組桌面應用程式最低版本為版本1.2.00.31357。</span><span class="sxs-lookup"><span data-stu-id="dcb04-206">The minimum version of the Teams desktop app that's required is version 1.2.00.31357.</span></span> <span data-ttu-id="dcb04-207">（舊版中不支援 PSTN 保留。）</span><span class="sxs-lookup"><span data-stu-id="dcb04-207">(PSTN hold is not supported in earlier versions.)</span></span>

2. <span data-ttu-id="dcb04-208">執行下列其中一項命令，將 MSI 安裝到 VDI VM：</span><span class="sxs-lookup"><span data-stu-id="dcb04-208">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="dcb04-209">每位使用者安裝（預設）</span><span class="sxs-lookup"><span data-stu-id="dcb04-209">Per-user installation  (default)</span></span>
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name>
        ```
    
        <span data-ttu-id="dcb04-210">這是預設安裝，可將團隊安裝至 [% AppData% user] （使用者）資料夾。</span><span class="sxs-lookup"><span data-stu-id="dcb04-210">This is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="dcb04-211">此時，黃金影像設定就完成了。</span><span class="sxs-lookup"><span data-stu-id="dcb04-211">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="dcb04-212">在非持久性設定上，小組將無法與每位使用者安裝正常運作。</span><span class="sxs-lookup"><span data-stu-id="dcb04-212">Teams will not work properly with per-user installation on a non-persistent setup.</span></span>
    
    - <span data-ttu-id="dcb04-213">每電腦安裝</span><span class="sxs-lookup"><span data-stu-id="dcb04-213">Per-machine installation</span></span>

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1
        ```

        <span data-ttu-id="dcb04-214">這會將團隊安裝至64位作業系統上的 [程式檔案（x86）] 資料夾，以及32位作業系統上的 [程式] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="dcb04-214">This installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="dcb04-215">此時，黃金影像設定就完成了。</span><span class="sxs-lookup"><span data-stu-id="dcb04-215">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="dcb04-216">針對非持久的安裝，必須針對每台電腦安裝團隊。</span><span class="sxs-lookup"><span data-stu-id="dcb04-216">Installing Teams per-machine is required for non-persistent setups.</span></span>
 
        <span data-ttu-id="dcb04-217">下次互動式登入會話會啟動團隊並要求認證。</span><span class="sxs-lookup"><span data-stu-id="dcb04-217">The next interactive logon session starts Teams and asks for credentials.</span></span>

3. <span data-ttu-id="dcb04-218">從 VDI VM 卸載 MSI。</span><span class="sxs-lookup"><span data-stu-id="dcb04-218">Uninstall the MSI from the VDI VM.</span></span> 

    <span data-ttu-id="dcb04-219">有兩種方式可以卸載團隊：</span><span class="sxs-lookup"><span data-stu-id="dcb04-219">There are two ways to uninstall Teams:</span></span>  
  
    - <span data-ttu-id="dcb04-220">PowerShell 腳本（建議使用）</span><span class="sxs-lookup"><span data-stu-id="dcb04-220">PowerShell script (recommended)</span></span>
    
    - <span data-ttu-id="dcb04-221">命令列：此方法會移除團隊，但不會重新安裝團隊。</span><span class="sxs-lookup"><span data-stu-id="dcb04-221">Command line: This approach removes Teams, yet prevents re-installation of Teams.</span></span> <span data-ttu-id="dcb04-222">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="dcb04-222">Run the following command:</span></span>
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```
      <span data-ttu-id="dcb04-223">這會從 [程式檔（x86）] 資料夾或 [Program Files] 資料夾中卸載小組，視作業系統環境而定。</span><span class="sxs-lookup"><span data-stu-id="dcb04-223">This uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="dcb04-224">VDI 效能考慮的小組</span><span class="sxs-lookup"><span data-stu-id="dcb04-224">Teams on VDI performance considerations</span></span>

<span data-ttu-id="dcb04-225">有許多虛擬化設定設定，每個都有不同的焦點可供優化。</span><span class="sxs-lookup"><span data-stu-id="dcb04-225">There are variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="dcb04-226">例如，使用者密度。</span><span class="sxs-lookup"><span data-stu-id="dcb04-226">For example, user density.</span></span> <span data-ttu-id="dcb04-227">規劃時，請考慮下列事項，以根據貴組織的工作量需求來優化您的設定：</span><span class="sxs-lookup"><span data-stu-id="dcb04-227">When planning, consider the following to help optimize your setup based on the workload needs of your organization:</span></span>

- <span data-ttu-id="dcb04-228">最低需求：某些工作負載可能需要使用超過最低需求的資源進行設定。</span><span class="sxs-lookup"><span data-stu-id="dcb04-228">Minimum requirement: Some workloads may require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="dcb04-229">例如，使用需要更多計算資源之應用程式之開發人員的工作負載。</span><span class="sxs-lookup"><span data-stu-id="dcb04-229">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="dcb04-230">相依性：這些專案包括在小組桌面應用程式以外的基礎結構、工作負載及其他環境考慮因素的相依性。</span><span class="sxs-lookup"><span data-stu-id="dcb04-230">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="dcb04-231">VDI 上停用的功能：團隊會針對 VDI 停用 GPU 密集型功能，這可以協助改善暫時的 CPU 利用率。</span><span class="sxs-lookup"><span data-stu-id="dcb04-231">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="dcb04-232">下列功能已停用：</span><span class="sxs-lookup"><span data-stu-id="dcb04-232">The following features are disabled:</span></span>
    - <span data-ttu-id="dcb04-233">團隊 CSS 動畫</span><span class="sxs-lookup"><span data-stu-id="dcb04-233">Teams CSS animation</span></span>
    - <span data-ttu-id="dcb04-234">Giphy 自動啟動</span><span class="sxs-lookup"><span data-stu-id="dcb04-234">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="dcb04-235">VDI 上的小組與通話與會議</span><span class="sxs-lookup"><span data-stu-id="dcb04-235">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="dcb04-236">除了聊天與共同作業之外，您還可以使用 Citrix 與會議支援來使用與客戶進行通話與會議支援的小組。</span><span class="sxs-lookup"><span data-stu-id="dcb04-236">In addition to chat and collaboration, Teams on VDI with calling and meeting support is available with Citrix-based platforms.</span></span> <span data-ttu-id="dcb04-237">支援的功能是以 WebRTC 媒體堆疊和 Citrix 專用的實現為基礎。</span><span class="sxs-lookup"><span data-stu-id="dcb04-237">Supported features are based on the WebRTC media stack and Citrix-specific implementation.</span></span> <span data-ttu-id="dcb04-238">下圖提供架構的概覽。</span><span class="sxs-lookup"><span data-stu-id="dcb04-238">The following diagram provides an overview of the architecture.</span></span>

![顯示 VDI 架構小組的圖表](media/teams-on-vdi-architecture.png)

<span data-ttu-id="dcb04-240">不支援以下通話與會議功能：</span><span class="sxs-lookup"><span data-stu-id="dcb04-240">These calling and meeting features are not supported:</span></span>

- <span data-ttu-id="dcb04-241">增強的緊急服務</span><span class="sxs-lookup"><span data-stu-id="dcb04-241">Enhanced emergency services</span></span>
- <span data-ttu-id="dcb04-242">小組 app 與裝置之間的 HID 按鈕和 LED 控制項</span><span class="sxs-lookup"><span data-stu-id="dcb04-242">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="dcb04-243">背景模糊和效果</span><span class="sxs-lookup"><span data-stu-id="dcb04-243">Background blur and effects</span></span>
- <span data-ttu-id="dcb04-244">廣播/即時事件</span><span class="sxs-lookup"><span data-stu-id="dcb04-244">Broadcast/live events</span></span>
- <span data-ttu-id="dcb04-245">以位置為基礎的路由（LBR）</span><span class="sxs-lookup"><span data-stu-id="dcb04-245">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="dcb04-246">通話駐留</span><span class="sxs-lookup"><span data-stu-id="dcb04-246">Call park</span></span>
- <span data-ttu-id="dcb04-247">通話佇列</span><span class="sxs-lookup"><span data-stu-id="dcb04-247">Call queue</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dcb04-248">如果您目前在 VDI 中執行的團隊沒有 AV 優化，且您使用的功能尚不支援（例如，在應用程式共用時授與控制權），您必須設定 Citrix 原則，以關閉小組重新導向。</span><span class="sxs-lookup"><span data-stu-id="dcb04-248">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set Citrix policies to turn off Teams redirection.</span></span> <span data-ttu-id="dcb04-249">這表示小組媒體會話不會進行優化。</span><span class="sxs-lookup"><span data-stu-id="dcb04-249">This means that Teams media sessions won’t be optimized.</span></span> <span data-ttu-id="dcb04-250">如需如何設定原則以關閉小組重新導向的步驟，請參閱此[Citrix 網站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html)。</span><span class="sxs-lookup"><span data-stu-id="dcb04-250">For steps on how to set policies to turn off Teams redirection, see this [Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html).</span></span>

<span data-ttu-id="dcb04-251">我們正在努力新增目前僅適用于非 VDI 環境中的通話與會議功能。</span><span class="sxs-lookup"><span data-stu-id="dcb04-251">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="dcb04-252">這些專案可能包含更多系統管理員控制品質、其他螢幕共用案例，以及最近新增至團隊的高級功能。</span><span class="sxs-lookup"><span data-stu-id="dcb04-252">These may include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="dcb04-253">若要深入瞭解即將推出的功能，請與您的小組代表聯繫。</span><span class="sxs-lookup"><span data-stu-id="dcb04-253">Contact your Teams representative to learn more about upcoming features.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="dcb04-254">網路需求</span><span class="sxs-lookup"><span data-stu-id="dcb04-254">Network requirements</span></span>

<span data-ttu-id="dcb04-255">我們建議您評估您的環境，以找出任何風險與需求，這些風險與需求可能會影響您的整體雲端語音及視頻部署。</span><span class="sxs-lookup"><span data-stu-id="dcb04-255">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="dcb04-256">使用[商務用 Skype 網路評估工具](https://www.microsoft.com/download/details.aspx?id=53885)來測試您的網路是否已準備好供團隊使用。</span><span class="sxs-lookup"><span data-stu-id="dcb04-256">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="dcb04-257">若要進一步瞭解如何為團隊準備您的網路，請參閱[準備貴組織的小組網路](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="dcb04-257">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for  Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="dcb04-258">從 VDI 上的商務用 Skype 遷移到 VDI 的小組</span><span class="sxs-lookup"><span data-stu-id="dcb04-258">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="dcb04-259">如果您是從 VDI 的商務用 Skype 遷移到 VDI 的小組，除了兩個應用程式之間的差異之外，也會有一些差異。</span><span class="sxs-lookup"><span data-stu-id="dcb04-259">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="dcb04-260">在商務用 Skype VDI 中，「團隊 VDI」目前不支援的部分功能如下：</span><span class="sxs-lookup"><span data-stu-id="dcb04-260">Some capabilities that aren’t currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="dcb04-261">使用限制媒體比對的原則控制 VDI 通話體驗</span><span class="sxs-lookup"><span data-stu-id="dcb04-261">Control of VDI calling experiences with policies for limiting media bitrate</span></span>
- <span data-ttu-id="dcb04-262">在 VDI 中停用某些防病毒功能的每個平臺原則</span><span class="sxs-lookup"><span data-stu-id="dcb04-262">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="dcb04-263">在應用程式共用時提供控制權並加以控制</span><span class="sxs-lookup"><span data-stu-id="dcb04-263">Give and take control when app sharing</span></span>
- <span data-ttu-id="dcb04-264">不含音訊的聊天螢幕共用</span><span class="sxs-lookup"><span data-stu-id="dcb04-264">Screen share from chat without audio</span></span>
- <span data-ttu-id="dcb04-265">同時進行影片和螢幕共用的傳送和接收</span><span class="sxs-lookup"><span data-stu-id="dcb04-265">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="dcb04-266">Chrome 瀏覽器上的小組與 VDI 的小組桌面應用程式</span><span class="sxs-lookup"><span data-stu-id="dcb04-266">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="dcb04-267">Chrome 瀏覽器上的小組無法使用 AV 優化來為 VDI 的小組桌面應用程式提供取代。</span><span class="sxs-lookup"><span data-stu-id="dcb04-267">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="dcb04-268">聊天與共同作業體驗會如期運作。</span><span class="sxs-lookup"><span data-stu-id="dcb04-268">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="dcb04-269">需要媒體時，有一些經驗可能無法在 Chrome 瀏覽器中滿足使用者的預期：</span><span class="sxs-lookup"><span data-stu-id="dcb04-269">When media is needed, there are some experiences that may not meet user expectations on the Chrome browser:</span></span>

- <span data-ttu-id="dcb04-270">音訊與視頻資料流程體驗可能不是最佳的。</span><span class="sxs-lookup"><span data-stu-id="dcb04-270">The audio and video streaming experience may not be optimal.</span></span> <span data-ttu-id="dcb04-271">使用者可能會遇到延遲或降低品質。</span><span class="sxs-lookup"><span data-stu-id="dcb04-271">Users may experiences delays or reduced quality.</span></span>
- <span data-ttu-id="dcb04-272">在瀏覽器設定中無法使用裝置設定。</span><span class="sxs-lookup"><span data-stu-id="dcb04-272">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="dcb04-273">裝置管理是透過瀏覽器處理，且需要瀏覽器網站設定中的多項設定。</span><span class="sxs-lookup"><span data-stu-id="dcb04-273">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="dcb04-274">裝置設定也可能需要在 Windows 裝置管理中設定。</span><span class="sxs-lookup"><span data-stu-id="dcb04-274">Device settings may also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="dcb04-275">VDI 上的小組與聊天與共同作業</span><span class="sxs-lookup"><span data-stu-id="dcb04-275">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="dcb04-276">如果您的組織想要只使用團隊中的聊天與共同作業功能，您可以設定使用者層級原則，以關閉小組中的通話與會議功能。</span><span class="sxs-lookup"><span data-stu-id="dcb04-276">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span> <span data-ttu-id="dcb04-277">此功能層級不需要 Citrix 虛擬 App 與桌上型電腦。</span><span class="sxs-lookup"><span data-stu-id="dcb04-277">This feature level doesn't require Citrix Virtual Apps and Desktops.</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="dcb04-278">設定原則以關閉通話與會議功能</span><span class="sxs-lookup"><span data-stu-id="dcb04-278">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="dcb04-279">您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來設定原則。</span><span class="sxs-lookup"><span data-stu-id="dcb04-279">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="dcb04-280">策略變更可能需要幾個時間（幾個小時）才能傳播。</span><span class="sxs-lookup"><span data-stu-id="dcb04-280">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="dcb04-281">如果您沒有立即看到特定帳戶的變更，請在幾個小時後再試一次。</span><span class="sxs-lookup"><span data-stu-id="dcb04-281">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="dcb04-282">[**通話**](teams-calling-policy.md)原則：團隊包含內建的 DisallowCalling 通話原則，其中所有的通話功能都已關閉。</span><span class="sxs-lookup"><span data-stu-id="dcb04-282">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="dcb04-283">將 DisallowCalling 原則指派給貴組織中的所有使用虛擬化環境中的小組的使用者。</span><span class="sxs-lookup"><span data-stu-id="dcb04-283">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="dcb04-284">[**會議原則**](meeting-policies-in-teams.md)：團隊包含內建的 AllOff 會議原則，其中所有會議功能都已關閉。</span><span class="sxs-lookup"><span data-stu-id="dcb04-284">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="dcb04-285">將 AllOff 原則指派給貴組織中的所有使用虛擬化環境中的小組的使用者。</span><span class="sxs-lookup"><span data-stu-id="dcb04-285">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="dcb04-286">使用 Microsoft 團隊系統管理中心指派原則</span><span class="sxs-lookup"><span data-stu-id="dcb04-286">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="dcb04-287">若要將 DisallowCalling 通話原則和 AllOff 會議原則指派給使用者，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="dcb04-287">To assign the DisallowCalling calling policy and the AllOff meeting policy to users, follow these steps:</span></span>

1. <span data-ttu-id="dcb04-288">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="dcb04-288">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="dcb04-289">按一下使用者名稱左邊的，然後按一下 [**編輯設定**]，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="dcb04-289">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="dcb04-290">請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="dcb04-290">Do the following:</span></span>
    1.  <span data-ttu-id="dcb04-291">按一下 [**呼叫原則**] 底下的 [ **DisallowCalling**]。</span><span class="sxs-lookup"><span data-stu-id="dcb04-291">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2.  <span data-ttu-id="dcb04-292">按一下 [**會議原則**] 底下的 [ **AllOff**]。</span><span class="sxs-lookup"><span data-stu-id="dcb04-292">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="dcb04-293">按一下 **[** 套用]。</span><span class="sxs-lookup"><span data-stu-id="dcb04-293">Click **Apply**.</span></span>

<span data-ttu-id="dcb04-294">若要一次將原則指派給多位使用者，請參閱[大量編輯團隊使用者設定](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="dcb04-294">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="dcb04-295">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="dcb04-295">Or, you can also do the following:</span></span>

1. <span data-ttu-id="dcb04-296">在 Microsoft 團隊系統管理中心的左導覽中，移至您要指派的原則。</span><span class="sxs-lookup"><span data-stu-id="dcb04-296">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="dcb04-297">例如：</span><span class="sxs-lookup"><span data-stu-id="dcb04-297">For example:</span></span>
    - <span data-ttu-id="dcb04-298">移至 [**語音** > **通話原則**]，然後按一下 [ **DisallowCalling**]。</span><span class="sxs-lookup"><span data-stu-id="dcb04-298">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="dcb04-299">移至 [**會議** > **會議原則**]，然後按一下 [ **AllOff**]。</span><span class="sxs-lookup"><span data-stu-id="dcb04-299">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
3. <span data-ttu-id="dcb04-300">選取 [**管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="dcb04-300">Select **Manage users**.</span></span>
4. <span data-ttu-id="dcb04-301">在 [**管理使用者**] 窗格中，依 [顯示名稱] 或 [使用者名稱] 搜尋使用者，選取名稱，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="dcb04-301">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="dcb04-302">針對您要新增的每個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="dcb04-302">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="dcb04-303">完成新增使用者後，請按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="dcb04-303">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="dcb04-304">使用 PowerShell 指派原則</span><span class="sxs-lookup"><span data-stu-id="dcb04-304">Assign policies using PowerShell</span></span>

<span data-ttu-id="dcb04-305">下列範例顯示如何使用[授與 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) ，將 DisallowCalling 通話原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="dcb04-305">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”
```

<span data-ttu-id="dcb04-306">若要深入瞭解如何使用 PowerShell 來管理通話原則，請參閱[設定 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="dcb04-306">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="dcb04-307">下列範例顯示如何使用[授與 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) ，將 AllOff 會議原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="dcb04-307">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”
```

<span data-ttu-id="dcb04-308">若要深入瞭解如何使用 PowerShell 來管理會議原則，請參閱[設定 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="dcb04-308">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-citrix-with-calling-and-meetings"></a><span data-ttu-id="dcb04-309">使用通話與會議，在 VDI 上將團隊遷移到與 Citrix 進行聊天與共同作業</span><span class="sxs-lookup"><span data-stu-id="dcb04-309">Migrate Teams on VDI with chat and collaboration to Citrix with calling and meetings</span></span>

<span data-ttu-id="dcb04-310">如果您在 VDI 上已有使用您已設定使用者層級原則來關閉通話和會議功能的小組，且您是透過 AV 優化來遷移到 Citrix，您必須設定原則來開啟通話，並針對 VDI 使用者的小組提供的會議功能。</span><span class="sxs-lookup"><span data-stu-id="dcb04-310">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Citrix with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="dcb04-311">設定原則以開啟通話與會議功能</span><span class="sxs-lookup"><span data-stu-id="dcb04-311">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="dcb04-312">您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來設定通話與會議原則，並指派給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="dcb04-312">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="dcb04-313">要傳播原則變更，可能需要一些時間（幾個小時）。</span><span class="sxs-lookup"><span data-stu-id="dcb04-313">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="dcb04-314">如果您沒有立即看到特定帳戶的變更，請在幾個小時後再試一次。</span><span class="sxs-lookup"><span data-stu-id="dcb04-314">If you don’t see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="dcb04-315">[**通話**](teams-calling-policy.md)原則：在團隊中呼叫原則控制使用者可以使用哪些通話功能。</span><span class="sxs-lookup"><span data-stu-id="dcb04-315">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="dcb04-316">團隊包含內建的 AllowCalling 通話原則，其中所有的通話功能都已開啟。</span><span class="sxs-lookup"><span data-stu-id="dcb04-316">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="dcb04-317">若要開啟所有通話功能，請指派 AllowCalling 原則。</span><span class="sxs-lookup"><span data-stu-id="dcb04-317">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="dcb04-318">或者，建立自訂通話原則來開啟您想要的通話功能，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="dcb04-318">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span> 

<span data-ttu-id="dcb04-319">[**會議原則**](meeting-policies-in-teams.md)：團隊中的會議原則控制使用者可以建立的會議類型，以及由貴組織中的使用者所排程的會議參與者所提供的功能。</span><span class="sxs-lookup"><span data-stu-id="dcb04-319">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="dcb04-320">團隊包含內建的 AllOn 會議原則，其中所有會議功能都已開啟。</span><span class="sxs-lookup"><span data-stu-id="dcb04-320">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="dcb04-321">若要開啟所有會議功能，請指派 AllOn 原則。</span><span class="sxs-lookup"><span data-stu-id="dcb04-321">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="dcb04-322">或者，建立自訂會議原則來開啟您想要的會議功能，並指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="dcb04-322">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="dcb04-323">使用 Microsoft 團隊系統管理中心指派原則</span><span class="sxs-lookup"><span data-stu-id="dcb04-323">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="dcb04-324">若要將 AllowCalling 通話原則和 AllOn 會議原則指派給使用者，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="dcb04-324">To assign the AllowCalling calling policy and the AllOn meeting policy to users, follow these steps:</span></span>

1. <span data-ttu-id="dcb04-325">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="dcb04-325">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="dcb04-326">按一下使用者名稱左邊的，然後按一下 [**編輯設定**]，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="dcb04-326">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="dcb04-327">請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="dcb04-327">Do the following:</span></span>
    1.  <span data-ttu-id="dcb04-328">按一下 [**呼叫原則**] 底下的 [ **AllowCalling**]。</span><span class="sxs-lookup"><span data-stu-id="dcb04-328">Under **Calling policy**, click **AllowCalling**.</span></span>
    2.  <span data-ttu-id="dcb04-329">按一下 [**會議原則**] 底下的 [ **AllOn**]。</span><span class="sxs-lookup"><span data-stu-id="dcb04-329">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="dcb04-330">按一下 **[** 套用]。</span><span class="sxs-lookup"><span data-stu-id="dcb04-330">Click **Apply**.</span></span>

<span data-ttu-id="dcb04-331">若要一次將原則指派給多位使用者，請參閱[大量編輯團隊使用者設定](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="dcb04-331">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="dcb04-332">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="dcb04-332">Or, you can also do the following:</span></span>

1. <span data-ttu-id="dcb04-333">在 Microsoft 團隊系統管理中心的左導覽中，移至您要指派的原則。</span><span class="sxs-lookup"><span data-stu-id="dcb04-333">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="dcb04-334">例如：</span><span class="sxs-lookup"><span data-stu-id="dcb04-334">For example:</span></span>
    - <span data-ttu-id="dcb04-335">移至 [**語音** > **通話原則**]，然後按一下 [ **AllowCalling**]。</span><span class="sxs-lookup"><span data-stu-id="dcb04-335">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="dcb04-336">移至 [**會議** > **會議原則**]，然後按一下 [ **AllOn**]。</span><span class="sxs-lookup"><span data-stu-id="dcb04-336">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
3. <span data-ttu-id="dcb04-337">選取 [**管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="dcb04-337">Select **Manage users**.</span></span>
4. <span data-ttu-id="dcb04-338">在 [**管理使用者**] 窗格中，依 [顯示名稱] 或 [使用者名稱] 搜尋使用者，選取名稱，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="dcb04-338">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="dcb04-339">針對您要新增的每個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="dcb04-339">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="dcb04-340">完成新增使用者後，請按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="dcb04-340">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="dcb04-341">使用 PowerShell 指派原則</span><span class="sxs-lookup"><span data-stu-id="dcb04-341">Assign policies using PowerShell</span></span>

<span data-ttu-id="dcb04-342">下列範例顯示如何使用[授與 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) ，將 AllowCalling 通話原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="dcb04-342">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity “user email id”
```

<span data-ttu-id="dcb04-343">若要深入瞭解如何使用 PowerShell 來管理通話原則，請參閱[設定 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="dcb04-343">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="dcb04-344">下列範例顯示如何使用[授與 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) ，將 AllOn 會議原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="dcb04-344">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity “user email id”
```

<span data-ttu-id="dcb04-345">若要深入瞭解如何使用 PowerShell 來管理會議原則，請參閱[設定 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="dcb04-345">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="dcb04-346">已知問題與限制</span><span class="sxs-lookup"><span data-stu-id="dcb04-346">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="dcb04-347">用戶端部署、安裝和設定</span><span class="sxs-lookup"><span data-stu-id="dcb04-347">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="dcb04-348">在每電腦安裝中，VDI 上的團隊不會以非 VDI 團隊用戶端的方式自動更新。</span><span class="sxs-lookup"><span data-stu-id="dcb04-348">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="dcb04-349">您必須安裝新的 MSI 來更新 VM 影像，如在 VDI 的 [[安裝或更新團隊桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi)] 區段中所述。</span><span class="sxs-lookup"><span data-stu-id="dcb04-349">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="dcb04-350">您必須卸載目前的版本，才能更新為較新的版本。</span><span class="sxs-lookup"><span data-stu-id="dcb04-350">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="dcb04-351">團隊應該針對每個使用者或每個電腦來部署。</span><span class="sxs-lookup"><span data-stu-id="dcb04-351">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="dcb04-352">不支援針對每位使用者和每個電腦並行部署團隊。</span><span class="sxs-lookup"><span data-stu-id="dcb04-352">Deployment of Teams for concurrent per user and per machine is not supported.</span></span>  <span data-ttu-id="dcb04-353">若要從每個電腦或每位使用者遷移到其中一個模式，請遵循卸載程式，然後重新部署到其中一種模式。</span><span class="sxs-lookup"><span data-stu-id="dcb04-353">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="dcb04-354">在此時間，Citrix 不支援 MacOs 和 Linux 版用戶端。</span><span class="sxs-lookup"><span data-stu-id="dcb04-354">MacOs and Linux-based clients are not supported by Citrix at this time.</span></span>
- <span data-ttu-id="dcb04-355">Citrix 不支援使用在端點上定義的明確 HTTP proxy。</span><span class="sxs-lookup"><span data-stu-id="dcb04-355">Citrix doesn't support the use of explicit HTTP proxies defined on an endpoint.</span></span> 

### <a name="calling-and-meetings"></a><span data-ttu-id="dcb04-356">通話與會議</span><span class="sxs-lookup"><span data-stu-id="dcb04-356">Calling and meetings</span></span>

- <span data-ttu-id="dcb04-357">與商務用 Skype 的互通性限制在音訊通話中，沒有視頻模態。</span><span class="sxs-lookup"><span data-stu-id="dcb04-357">Interoperability with Skype for Business is limited to audio calls, no video modality.</span></span>
- <span data-ttu-id="dcb04-358">目前不支援雙音調多重頻率（DTMF）與電話系統互動。</span><span class="sxs-lookup"><span data-stu-id="dcb04-358">Dual Tone Multi Frequency (DTMF) interaction with telephony systems  is currently not supported.</span></span>
- <span data-ttu-id="dcb04-359">以匿名使用者身分加入團隊會議不是 AV 優化的。</span><span class="sxs-lookup"><span data-stu-id="dcb04-359">Joining Teams meetings as an anonymous user isn't AV-optimized.</span></span> <span data-ttu-id="dcb04-360">使用者可以加入會議，且有未優化的體驗。</span><span class="sxs-lookup"><span data-stu-id="dcb04-360">The user can join the meeting and have a non-optimized experience.</span></span>
- <span data-ttu-id="dcb04-361">在會議或群組通話中只支援單一傳入的視頻資料流程。</span><span class="sxs-lookup"><span data-stu-id="dcb04-361">Only a single incoming video stream is supported in meetings or group calls.</span></span> <span data-ttu-id="dcb04-362">當多人傳送影片時，任何指定時間只會顯示主要喇叭的影片。</span><span class="sxs-lookup"><span data-stu-id="dcb04-362">When multiple people send video, only the dominant speaker's video is shown at any given time.</span></span>  
- <span data-ttu-id="dcb04-363">內送和外寄的視頻資料流程解析度限制為720p 解析度。</span><span class="sxs-lookup"><span data-stu-id="dcb04-363">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span> <span data-ttu-id="dcb04-364">這是 WebRTC 的限制。</span><span class="sxs-lookup"><span data-stu-id="dcb04-364">This is a WebRTC limitation.</span></span>
- <span data-ttu-id="dcb04-365">只支援來自內送相機或畫面共用資料流程的一個影片串流。</span><span class="sxs-lookup"><span data-stu-id="dcb04-365">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="dcb04-366">當有內送螢幕共用時，就會顯示畫面共用，而不是主要喇叭的影片。</span><span class="sxs-lookup"><span data-stu-id="dcb04-366">When there's an incoming screen share, that screen share is shown it instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="dcb04-367">外寄螢幕共用：</span><span class="sxs-lookup"><span data-stu-id="dcb04-367">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="dcb04-368">不支援應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="dcb04-368">Application sharing is not supported.</span></span>
- <span data-ttu-id="dcb04-369">授與控制權並加以控制：</span><span class="sxs-lookup"><span data-stu-id="dcb04-369">Give control and take control:</span></span>  
    - <span data-ttu-id="dcb04-370">在螢幕共用或應用程式共用會話期間不支援。</span><span class="sxs-lookup"><span data-stu-id="dcb04-370">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="dcb04-371">在 PowerPoint 共用會話期間支援。</span><span class="sxs-lookup"><span data-stu-id="dcb04-371">Supported during a PowerPoint sharing session.</span></span>  
- <span data-ttu-id="dcb04-372">不支援 CWA 上的高 DPI 縮放。</span><span class="sxs-lookup"><span data-stu-id="dcb04-372">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="dcb04-373">針對與 VDI 無關的小組已知問題，請參閱[小組的已知問題](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="dcb04-373">For Teams known issues that aren’t related to VDI, see [Known issues for Teams](Known-issues.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="dcb04-374">疑難排解</span><span class="sxs-lookup"><span data-stu-id="dcb04-374">Troubleshooting</span></span>

#### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="dcb04-375">Citrix 元件疑難排解</span><span class="sxs-lookup"><span data-stu-id="dcb04-375">Troubleshoot Citrix components</span></span>

<span data-ttu-id="dcb04-376">如需如何針對 VDA 和 CWA 問題進行疑難排解的資訊，請參閱[此 Citrix 網站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。</span><span class="sxs-lookup"><span data-stu-id="dcb04-376">For information on how to troubleshoot VDA and CWA issues, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="related-topics"></a><span data-ttu-id="dcb04-377">相關主題</span><span class="sxs-lookup"><span data-stu-id="dcb04-377">Related topics</span></span>

- [<span data-ttu-id="dcb04-378">使用 MSI 安裝 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="dcb04-378">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="dcb04-379">團隊 PowerShell 概覽</span><span class="sxs-lookup"><span data-stu-id="dcb04-379">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

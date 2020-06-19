---
title: 適用於虛擬桌面架構的 Teams
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
ms.openlocfilehash: cb1be3215aff5aa97d97b0bc7cfbb81febd7d7fe
ms.sourcegitcommit: 8acc2ed4cb807f941a6526ec8aad562536f45aa6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2020
ms.locfileid: "44804697"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="f5157-103">適用於虛擬桌面架構的 Teams</span><span class="sxs-lookup"><span data-stu-id="f5157-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="f5157-104">本文將說明在虛擬化環境中使用 Microsoft 團隊的需求與限制。</span><span class="sxs-lookup"><span data-stu-id="f5157-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="f5157-105">什麼是 VDI？</span><span class="sxs-lookup"><span data-stu-id="f5157-105">What is VDI?</span></span>

<span data-ttu-id="f5157-106">虛擬桌面基礎結構（VDI）是虛擬化技術，可在資料中心的中央伺服器上託管桌面作業系統和應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5157-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="f5157-107">這可讓使用者具備完全安全且相容的集中來源，為使用者提供完整的個人化桌面體驗。</span><span class="sxs-lookup"><span data-stu-id="f5157-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>
 
<span data-ttu-id="f5157-108">虛擬化環境中的 Microsoft 團隊支援聊天與共同作業。</span><span class="sxs-lookup"><span data-stu-id="f5157-108">Microsoft Teams in a virtualized environment supports chat and collaboration.</span></span> <span data-ttu-id="f5157-109">而且在 Citrix 平臺中，也支援通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="f5157-109">And with the Citrix platform, calling and meeting functionality also are supported.</span></span>

<span data-ttu-id="f5157-110">虛擬化環境中的小組支援多種設定。</span><span class="sxs-lookup"><span data-stu-id="f5157-110">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="f5157-111">其中包括 VDI、專用、共用、持久且非持久的模式。</span><span class="sxs-lookup"><span data-stu-id="f5157-111">These include VDI, dedicated, shared, persistent, and non-persistent modes.</span></span> <span data-ttu-id="f5157-112">功能在連續開發並定期新增，功能將會在未來的幾個月和幾年中擴充。</span><span class="sxs-lookup"><span data-stu-id="f5157-112">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>
 
<span data-ttu-id="f5157-113">在虛擬化環境中使用團隊的方式可能與在非虛擬化環境中使用團隊稍有不同。</span><span class="sxs-lookup"><span data-stu-id="f5157-113">Using Teams in a virtualized environment might be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="f5157-114">例如，某些高級功能可能無法在虛擬化的環境中使用，而且可能會有不同的影片解析度。</span><span class="sxs-lookup"><span data-stu-id="f5157-114">For example, some advanced features might not be available in a virtualized environment, and video resolution might differ.</span></span> 

<span data-ttu-id="f5157-115">若要確保最佳的使用者體驗，請遵循本文中的指導方針。</span><span class="sxs-lookup"><span data-stu-id="f5157-115">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="f5157-116">VDI 元件上的小組</span><span class="sxs-lookup"><span data-stu-id="f5157-116">Teams on VDI components</span></span>

<span data-ttu-id="f5157-117">在虛擬化環境中使用團隊需要下列元件。</span><span class="sxs-lookup"><span data-stu-id="f5157-117">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="f5157-118">**虛擬化 broker**：虛擬化提供者的資源和連線管理員（例如 Azure）</span><span class="sxs-lookup"><span data-stu-id="f5157-118">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="f5157-119">**虛擬桌面**：執行 Microsoft 團隊的虛擬機器（VM）堆疊</span><span class="sxs-lookup"><span data-stu-id="f5157-119">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="f5157-120">**瘦用戶端**：使用者使用物理介面的端點</span><span class="sxs-lookup"><span data-stu-id="f5157-120">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="f5157-121">**團隊桌面應用程式**：團隊桌面用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="f5157-121">**Teams desktop app**: The Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="f5157-122">針對 VDI 需求的小組</span><span class="sxs-lookup"><span data-stu-id="f5157-122">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="f5157-123">虛擬化提供者需求</span><span class="sxs-lookup"><span data-stu-id="f5157-123">Virtualization provider requirements</span></span>

<span data-ttu-id="f5157-124">已使用主要的虛擬化解決方案提供者驗證團隊桌面應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5157-124">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="f5157-125">有了多個市場供應商，我們建議您諮詢您的虛擬化解決方案供應商，以確保您符合最低需求。</span><span class="sxs-lookup"><span data-stu-id="f5157-125">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure that you meet the minimum requirements.</span></span>
  
<span data-ttu-id="f5157-126">目前，具有音訊/視頻（AV）優化的團隊在使用 Citrix 進行認證。</span><span class="sxs-lookup"><span data-stu-id="f5157-126">Currently, Teams on VDI with audio/video (AV) optimization is certified with Citrix.</span></span> <span data-ttu-id="f5157-127">請參閱本節中的資訊，以確保您符合 Citrix 與團隊對適當功能的需求。</span><span class="sxs-lookup"><span data-stu-id="f5157-127">Review the information in this section to ensure that you meet both Citrix and Teams requirements for proper functionality.</span></span>

### <a name="partners-certified-for-teams"></a><span data-ttu-id="f5157-128">針對團隊認證的合作夥伴</span><span class="sxs-lookup"><span data-stu-id="f5157-128">Partners certified for Teams</span></span>

<span data-ttu-id="f5157-129">下列合作夥伴擁有小組的虛擬桌面基礎結構解決方案。</span><span class="sxs-lookup"><span data-stu-id="f5157-129">The following partners have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="f5157-130">Partner</span><span class="sxs-lookup"><span data-stu-id="f5157-130">Partner</span></span>|<span data-ttu-id="f5157-131">合作夥伴解決方案</span><span class="sxs-lookup"><span data-stu-id="f5157-131">Partner solution</span></span>|
|----|---|
|![代表 Citrix 的標誌](media/citrix.png)| <span data-ttu-id="f5157-133"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 虛擬 App 與桌面</a></span><span class="sxs-lookup"><span data-stu-id="f5157-133"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="f5157-134">Citrix 虛擬 App 與桌面需求</span><span class="sxs-lookup"><span data-stu-id="f5157-134">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="f5157-135">Citrix 虛擬 App 與桌上型電腦（先前稱為 XenApp 和 XenDesktop）為 VDI 上的小組提供 AV 優化。</span><span class="sxs-lookup"><span data-stu-id="f5157-135">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="f5157-136">借助 Citrix 虛擬 App 和電腦版，VDI 的小組除了聊天與共同作業之外，還支援通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="f5157-136">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="f5157-137">您可以在[citrix 下載網站](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)下載最新版本的 Citrix 虛擬 App 和桌上型電腦。</span><span class="sxs-lookup"><span data-stu-id="f5157-137">You can download the latest version of Citrix Virtual Apps and Desktops at [the Citrix downloads site](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="f5157-138">（您必須先登入。）預設會將必要的元件捆綁到[Citrix 工作區應用程式（CWA）](https://www.citrix.com/downloads/workspace-app/)和虛擬傳遞代理程式（VDA）。</span><span class="sxs-lookup"><span data-stu-id="f5157-138">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="f5157-139">您不需要在 CWA 或 VDA 上安裝任何其他元件或外掛程式。</span><span class="sxs-lookup"><span data-stu-id="f5157-139">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="f5157-140">如需最新的伺服器和用戶端需求，請參閱[此 Citrix 網站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。</span><span class="sxs-lookup"><span data-stu-id="f5157-140">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="f5157-141">在 VDI 上安裝或更新小組桌面應用程式</span><span class="sxs-lookup"><span data-stu-id="f5157-141">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="f5157-142">您可以使用每電腦安裝或使用 MSI 套件的每個使用者安裝，部署 VDI 版團隊桌面應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5157-142">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="f5157-143">決定使用哪種方法，取決於您使用的是持續性或非持續設定，以及貴組織的相關功能需求。</span><span class="sxs-lookup"><span data-stu-id="f5157-143">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>

<span data-ttu-id="f5157-144">針對專用的持續設定，這兩種方法都可以運作。</span><span class="sxs-lookup"><span data-stu-id="f5157-144">For a dedicated persistent setup, either approach would work.</span></span> <span data-ttu-id="f5157-145">不過，對於非持續性設定，小組需要每電腦安裝才能有效運作。</span><span class="sxs-lookup"><span data-stu-id="f5157-145">However, for a non-persistent setup, Teams requires a per-machine installation in order to work efficiently.</span></span> <span data-ttu-id="f5157-146">請參閱[非持續性設定](#non-persistent-setup)一節。</span><span class="sxs-lookup"><span data-stu-id="f5157-146">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="f5157-147">在安裝每電腦的情況下，自動更新是停用的。</span><span class="sxs-lookup"><span data-stu-id="f5157-147">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="f5157-148">這表示若要更新團隊應用程式，您必須卸載目前的版本，才能更新為較新的版本。</span><span class="sxs-lookup"><span data-stu-id="f5157-148">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="f5157-149">針對每位使用者安裝，會啟用自動更新。</span><span class="sxs-lookup"><span data-stu-id="f5157-149">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="f5157-150">對於大多數的 VDI 部署，我們建議您使用每電腦安裝來部署團隊。</span><span class="sxs-lookup"><span data-stu-id="f5157-150">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="f5157-151">若要更新為最新的團隊版本，請先從最新的團隊版本部署開始卸載程式。</span><span class="sxs-lookup"><span data-stu-id="f5157-151">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="f5157-152">為了讓 VDI 環境中的團隊 AV 優化功能正常運作，瘦用戶端端點必須能夠存取網際網路。</span><span class="sxs-lookup"><span data-stu-id="f5157-152">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="f5157-153">如果瘦用戶端端點無法使用網際網路存取，優化啟動將會失敗。</span><span class="sxs-lookup"><span data-stu-id="f5157-153">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="f5157-154">這表示使用者處於未優化的媒體狀態。</span><span class="sxs-lookup"><span data-stu-id="f5157-154">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="f5157-155">專用持續設定</span><span class="sxs-lookup"><span data-stu-id="f5157-155">Dedicated persistent setup</span></span>

<span data-ttu-id="f5157-156">在專用的持續設定中，使用者會在使用者登出後保留使用者的本機作業系統變更。</span><span class="sxs-lookup"><span data-stu-id="f5157-156">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span> <span data-ttu-id="f5157-157">針對持續性設定，小組支援針對每位使用者和每電腦安裝。</span><span class="sxs-lookup"><span data-stu-id="f5157-157">For persistent setup, Teams supports both per-user and per-machine installation.</span></span>

<span data-ttu-id="f5157-158">以下是建議的最低 VM 設定。</span><span class="sxs-lookup"><span data-stu-id="f5157-158">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="f5157-159">參數</span><span class="sxs-lookup"><span data-stu-id="f5157-159">Parameter</span></span>  |<span data-ttu-id="f5157-160">工作站作業系統</span><span class="sxs-lookup"><span data-stu-id="f5157-160">Workstation operating system</span></span>  |<span data-ttu-id="f5157-161">伺服器作業系統</span><span class="sxs-lookup"><span data-stu-id="f5157-161">Server operating system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="f5157-162">vCPU</span><span class="sxs-lookup"><span data-stu-id="f5157-162">vCPU</span></span>   |    <span data-ttu-id="f5157-163">2個核心</span><span class="sxs-lookup"><span data-stu-id="f5157-163">2 cores</span></span>     |  <span data-ttu-id="f5157-164">4、6或8</span><span class="sxs-lookup"><span data-stu-id="f5157-164">4,6, or 8</span></span><br><span data-ttu-id="f5157-165">瞭解基礎非一致性記憶體存取（NUMA）設定並據此設定您的 Vm 非常重要。</span><span class="sxs-lookup"><span data-stu-id="f5157-165">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="f5157-166">RAM</span><span class="sxs-lookup"><span data-stu-id="f5157-166">RAM</span></span>     |   <span data-ttu-id="f5157-167">4 GB</span><span class="sxs-lookup"><span data-stu-id="f5157-167">4 GB</span></span>      | <span data-ttu-id="f5157-168">每位使用者512到 1024 MB</span><span class="sxs-lookup"><span data-stu-id="f5157-168">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="f5157-169">儲存空間</span><span class="sxs-lookup"><span data-stu-id="f5157-169">Storage</span></span>    | <span data-ttu-id="f5157-170">8 GB</span><span class="sxs-lookup"><span data-stu-id="f5157-170">8 GB</span></span>        | <span data-ttu-id="f5157-171">40到 60 GB</span><span class="sxs-lookup"><span data-stu-id="f5157-171">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="f5157-172">非持久性設定</span><span class="sxs-lookup"><span data-stu-id="f5157-172">Non-persistent setup</span></span>

<span data-ttu-id="f5157-173">在非永久性設定中，使用者登出後，使用者的本機作業系統變更就不會保留。</span><span class="sxs-lookup"><span data-stu-id="f5157-173">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="f5157-174">這類設置通常是共用多個使用者會話。</span><span class="sxs-lookup"><span data-stu-id="f5157-174">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="f5157-175">VM 配置會根據使用者數量及可用的物理盒資源而有所不同。</span><span class="sxs-lookup"><span data-stu-id="f5157-175">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="f5157-176">針對非持續性設定，小組桌面應用程式必須安裝在每一台電腦上的黃金影像中。</span><span class="sxs-lookup"><span data-stu-id="f5157-176">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="f5157-177">（若要深入瞭解，請參閱[安裝或更新 VDI 區段上的小組桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi)）。這可確保在使用者會話期間有效啟動團隊 app。</span><span class="sxs-lookup"><span data-stu-id="f5157-177">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.) This ensures an efficient launch of the Teams app during a user session.</span></span> 

<span data-ttu-id="f5157-178">將團隊與非持久設定搭配使用時，也需要設定檔的快取管理員，才能高效地進行團隊執行時間資料同步處理。這樣可確保在使用者會話期間，會緩存適當的使用者特定資訊（例如，使用者資料、設定檔和設定）。</span><span class="sxs-lookup"><span data-stu-id="f5157-178">Using Teams with a non-persistent setup also requires a profile caching manager for efficient Teams runtime data sync. This ensures that the appropriate user-specific information (for example, user data, profile, and settings) is cached during the user session.</span></span> <span data-ttu-id="f5157-179">請確定這兩個資料夾中的資料已同步處理。</span><span class="sxs-lookup"><span data-stu-id="f5157-179">Make sure data in these two folders are synced.</span></span>  

- <span data-ttu-id="f5157-180">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span><span class="sxs-lookup"><span data-stu-id="f5157-180">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span></span>
- <span data-ttu-id="f5157-181">C:\Users\username\AppData\Roaming\Microsoft\Teams(%appdata%\Microsoft\Teams)</span><span class="sxs-lookup"><span data-stu-id="f5157-181">C:\Users\username\AppData\Roaming\Microsoft\Teams(%appdata%\Microsoft\Teams)</span></span>

<span data-ttu-id="f5157-182">有許多可用的緩存管理器解決方案。</span><span class="sxs-lookup"><span data-stu-id="f5157-182">There are a variety of caching manager solutions available.</span></span> <span data-ttu-id="f5157-183">例如， [FSLogix](https://docs.microsoft.com/fslogix/overview)。</span><span class="sxs-lookup"><span data-stu-id="f5157-183">For example, [FSLogix](https://docs.microsoft.com/fslogix/overview).</span></span> <span data-ttu-id="f5157-184">如需特定的設定指示，請參閱您的快取管理員提供者。</span><span class="sxs-lookup"><span data-stu-id="f5157-184">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="f5157-185">小組快取內容排除清單以進行非持續設定</span><span class="sxs-lookup"><span data-stu-id="f5157-185">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="f5157-186">從 [團隊快取] 資料夾（% appdata%/Microsoft/Teams.）中排除下列各項：</span><span class="sxs-lookup"><span data-stu-id="f5157-186">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span> <span data-ttu-id="f5157-187">排除這些專案有助於減少使用者的快取大小，進一步優化您的非持久設定。</span><span class="sxs-lookup"><span data-stu-id="f5157-187">Excluding these items helps reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="f5157-188">.txt 檔案</span><span class="sxs-lookup"><span data-stu-id="f5157-188">.txt files</span></span>
- <span data-ttu-id="f5157-189">媒體堆疊資料夾</span><span class="sxs-lookup"><span data-stu-id="f5157-189">Media-stack folder</span></span>

### <a name="microsoft-365-apps-for-enterprise-considerations"></a><span data-ttu-id="f5157-190">適用于企業考慮的 Microsoft 365 應用程式</span><span class="sxs-lookup"><span data-stu-id="f5157-190">Microsoft 365 Apps for enterprise considerations</span></span>

<span data-ttu-id="f5157-191">當您使用 VDI 上的企業版 Microsoft 365 應用程式部署團隊時，請考慮下列事項。</span><span class="sxs-lookup"><span data-stu-id="f5157-191">Consider the following when you deploy Teams with Microsoft 365 Apps for enterprise on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="f5157-192">透過企業版 Microsoft 365 應用程式的新部署團隊</span><span class="sxs-lookup"><span data-stu-id="f5157-192">New deployments of Teams through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="f5157-193">在透過企業版 Microsoft 365 應用程式部署團隊前，您必須先卸載任何預先存在的團隊應用程式（如果它們是使用各電腦安裝來部署）。</span><span class="sxs-lookup"><span data-stu-id="f5157-193">Before you deploy Teams through Microsoft 365 Apps for enterprise, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="f5157-194">團隊透過適用于企業的 Microsoft 365 應用程式是針對每位使用者安裝的。</span><span class="sxs-lookup"><span data-stu-id="f5157-194">Teams through Microsoft 365 Apps for enterprise is installed per-user.</span></span> <span data-ttu-id="f5157-195">若要深入瞭解，請參閱[安裝或更新 VDI 區段上的小組桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi)。</span><span class="sxs-lookup"><span data-stu-id="f5157-195">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a><span data-ttu-id="f5157-196">透過適用于企業更新的 Microsoft 365 應用程式部署團隊</span><span class="sxs-lookup"><span data-stu-id="f5157-196">Teams deployments through Microsoft 365 Apps for enterprise updates</span></span>

<span data-ttu-id="f5157-197">團隊也會新增至企業版 Microsoft 365 應用程式的現有安裝。</span><span class="sxs-lookup"><span data-stu-id="f5157-197">Teams is also being added to existing installations of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="f5157-198">由於 [企業版 Microsoft 365 應用程式] 只會針對每位使用者安裝小組，請參閱在[VDI 上安裝或更新小組桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi)。</span><span class="sxs-lookup"><span data-stu-id="f5157-198">Since Microsoft 365 Apps for enterprise installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="f5157-199">使用團隊進行每電腦安裝和適用于企業的 Microsoft 365 應用程式</span><span class="sxs-lookup"><span data-stu-id="f5157-199">Using Teams with per-machine installation and Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="f5157-200">適用于企業的 Microsoft 365 應用程式不支援小組的每電腦安裝。</span><span class="sxs-lookup"><span data-stu-id="f5157-200">Microsoft 365 Apps for enterprise doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="f5157-201">若要使用 [每電腦安裝]，您必須從適用于企業的 Microsoft 365 App 中排除團隊。</span><span class="sxs-lookup"><span data-stu-id="f5157-201">To use per-machine installation, you must exclude Teams from Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="f5157-202">請參閱將[團隊傳統型應用程式部署至 VM](#deploy-the-teams-desktop-app-to-the-vm) ，以及[如何透過適用于企業的 Microsoft 365 應用程式排除團隊部署](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="f5157-202">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Microsoft 365 Apps for enterprise](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="f5157-203">如何透過適用于企業的 Microsoft 365 應用程式排除團隊部署</span><span class="sxs-lookup"><span data-stu-id="f5157-203">How to exclude Teams deployment through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="f5157-204">若要深入瞭解團隊和適用于企業的 Microsoft 365 應用程式，請參閱[如何將團隊從新安裝的企業版 microsoft 365 應用程式中排除](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus)，並[使用群組原則來控制團隊的安裝](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="f5157-204">To learn more about Teams and Microsoft 365 Apps for enterprise, see [How to exclude Teams from new installations of Microsoft 365 Apps for enterprise](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="f5157-205">將團隊桌面應用程式部署到 VM</span><span class="sxs-lookup"><span data-stu-id="f5157-205">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="f5157-206">使用下列其中一個連結，下載與您的 VDI VM 作業系統相符的團隊 MSI 套件：</span><span class="sxs-lookup"><span data-stu-id="f5157-206">Download the Teams MSI package that matches your VDI VM operating system using one of the following links:</span></span>


    - [<span data-ttu-id="f5157-207">32位版本</span><span class="sxs-lookup"><span data-stu-id="f5157-207">32-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows/1.3.00.12058/Teams_windows.msi)
    - [<span data-ttu-id="f5157-208">64位版本</span><span class="sxs-lookup"><span data-stu-id="f5157-208">64-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows-x64/1.3.00.12058/Teams_windows_x64.msi)


    <span data-ttu-id="f5157-209">所需的小組桌面應用程式最低版本為版本1.3.00.4461。</span><span class="sxs-lookup"><span data-stu-id="f5157-209">The minimum version of the Teams desktop app that's required is version 1.3.00.4461.</span></span> <span data-ttu-id="f5157-210">（較舊的版本不支援 PSTN 保留）。</span><span class="sxs-lookup"><span data-stu-id="f5157-210">(PSTN hold isn't supported in earlier versions.)</span></span>

2. <span data-ttu-id="f5157-211">執行下列其中一項命令，將 MSI 安裝到 VDI VM：</span><span class="sxs-lookup"><span data-stu-id="f5157-211">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="f5157-212">每位使用者安裝（預設）</span><span class="sxs-lookup"><span data-stu-id="f5157-212">Per-user installation (default)</span></span>
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        <span data-ttu-id="f5157-213">這個處理常式是預設安裝，可將團隊安裝到% AppData% user 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="f5157-213">This process is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="f5157-214">此時，黃金影像設定就完成了。</span><span class="sxs-lookup"><span data-stu-id="f5157-214">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="f5157-215">在非持續設定上，小組無法針對每位使用者安裝正常運作。</span><span class="sxs-lookup"><span data-stu-id="f5157-215">Teams won't work properly with per-user installation on a non-persistent setup.</span></span>

    - <span data-ttu-id="f5157-216">每電腦安裝</span><span class="sxs-lookup"><span data-stu-id="f5157-216">Per-machine installation</span></span>

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        <span data-ttu-id="f5157-217">這個程式會將團隊安裝至64位作業系統上的 [程式檔案（x86）] 資料夾，以及32位作業系統上的 [程式檔案] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="f5157-217">This process installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="f5157-218">此時，黃金影像設定就完成了。</span><span class="sxs-lookup"><span data-stu-id="f5157-218">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="f5157-219">針對非持久的安裝，必須針對每台電腦安裝團隊。</span><span class="sxs-lookup"><span data-stu-id="f5157-219">Installing Teams per-machine is required for non-persistent setups.</span></span>

        <span data-ttu-id="f5157-220">下次互動式登入會話會啟動團隊並要求認證。</span><span class="sxs-lookup"><span data-stu-id="f5157-220">The next interactive logon session starts Teams and asks for credentials.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f5157-221">這些範例也會使用**ALLUSERS = 1**參數。</span><span class="sxs-lookup"><span data-stu-id="f5157-221">These examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="f5157-222">當您設定此參數時，系統會在 [控制台] 的 [程式和功能] 和 [應用程式 & Windows 設定] 中的 [應用程式] 中，顯示「團隊電腦範圍」的安裝程式。</span><span class="sxs-lookup"><span data-stu-id="f5157-222">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="f5157-223">如果有管理員認證，所有使用者都可以卸載小組。</span><span class="sxs-lookup"><span data-stu-id="f5157-223">All users can then uninstall Teams if they have admin credentials.</span></span>
    <span data-ttu-id="f5157-224">請務必瞭解**ALLUSERS = 1**與**ALLUSER = 1**之間的差異。</span><span class="sxs-lookup"><span data-stu-id="f5157-224">It's important to understand the difference between **ALLUSERS=1** and **ALLUSER=1**.</span></span> <span data-ttu-id="f5157-225">您可以在非 VDI 和 VDI 環境中使用**ALLUSERS = 1**參數，而**ALLUSER = 1**參數只會在 VDI 環境中用來指定每電腦安裝。</span><span class="sxs-lookup"><span data-stu-id="f5157-225">The **ALLUSERS=1** parameter can be used in non-VDI and VDI environments, while the **ALLUSER=1** parameter is used only in VDI environments to specify a per-machine installation.</span></span>

3. <span data-ttu-id="f5157-226">從 VDI VM 卸載 MSI。</span><span class="sxs-lookup"><span data-stu-id="f5157-226">Uninstall the MSI from the VDI VM.</span></span>
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```
      <span data-ttu-id="f5157-227">這個程式會從 [程式檔（x86）] 資料夾或 [Program Files] 資料夾中卸載小組，視作業系統環境而定。</span><span class="sxs-lookup"><span data-stu-id="f5157-227">This process uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="f5157-228">VDI 效能考慮的小組</span><span class="sxs-lookup"><span data-stu-id="f5157-228">Teams on VDI performance considerations</span></span>

<span data-ttu-id="f5157-229">有多種虛擬化設定設定，每個都有不同的焦點可供優化。</span><span class="sxs-lookup"><span data-stu-id="f5157-229">There are a variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="f5157-230">例如，配置可能會將焦點放在使用者密度上。</span><span class="sxs-lookup"><span data-stu-id="f5157-230">For example, a configuration might focus on user density.</span></span> <span data-ttu-id="f5157-231">規劃時，請考慮下列事項，以根據貴組織的工作負載需求來優化您的設定。</span><span class="sxs-lookup"><span data-stu-id="f5157-231">When planning, consider the following to help optimize your setup based on your organization's workload needs.</span></span>

- <span data-ttu-id="f5157-232">最低需求：某些工作負載可能需要使用超過最低需求的資源進行設定。</span><span class="sxs-lookup"><span data-stu-id="f5157-232">Minimum requirement: Some workloads might require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="f5157-233">例如，使用需要更多計算資源之應用程式之開發人員的工作負載。</span><span class="sxs-lookup"><span data-stu-id="f5157-233">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="f5157-234">相依性：這些專案包括在小組桌面應用程式以外的基礎結構、工作負載及其他環境考慮因素的相依性。</span><span class="sxs-lookup"><span data-stu-id="f5157-234">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="f5157-235">VDI 上停用的功能：團隊會針對 VDI 停用 GPU 密集型功能，這可以協助改善暫時的 CPU 利用率。</span><span class="sxs-lookup"><span data-stu-id="f5157-235">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="f5157-236">下列功能已停用：</span><span class="sxs-lookup"><span data-stu-id="f5157-236">The following features are disabled:</span></span>
    - <span data-ttu-id="f5157-237">團隊 CSS 動畫</span><span class="sxs-lookup"><span data-stu-id="f5157-237">Teams CSS animation</span></span>
    - <span data-ttu-id="f5157-238">Giphy 自動啟動</span><span class="sxs-lookup"><span data-stu-id="f5157-238">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="f5157-239">VDI 上的小組與通話與會議</span><span class="sxs-lookup"><span data-stu-id="f5157-239">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="f5157-240">除了聊天與共同作業之外，您還可以使用 Citrix 與會議支援來使用與客戶進行通話與會議支援的小組。</span><span class="sxs-lookup"><span data-stu-id="f5157-240">In addition to chat and collaboration, Teams on VDI with calling and meeting support is available with Citrix-based platforms.</span></span> <span data-ttu-id="f5157-241">支援的功能是以 WebRTC 媒體堆疊和 Citrix 專用的實現為基礎。</span><span class="sxs-lookup"><span data-stu-id="f5157-241">Supported features are based on the WebRTC media stack and Citrix-specific implementation.</span></span> <span data-ttu-id="f5157-242">下圖提供架構的概覽。</span><span class="sxs-lookup"><span data-stu-id="f5157-242">The following diagram provides an overview of the architecture.</span></span>

![顯示 VDI 架構小組的圖表](media/teams-on-vdi-architecture.png)

<span data-ttu-id="f5157-244">不支援以下通話與會議功能：</span><span class="sxs-lookup"><span data-stu-id="f5157-244">These calling and meeting features are not supported:</span></span>

- <span data-ttu-id="f5157-245">增強的緊急服務</span><span class="sxs-lookup"><span data-stu-id="f5157-245">Enhanced emergency services</span></span>
- <span data-ttu-id="f5157-246">小組 app 與裝置之間的 HID 按鈕和 LED 控制項</span><span class="sxs-lookup"><span data-stu-id="f5157-246">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="f5157-247">背景模糊和效果</span><span class="sxs-lookup"><span data-stu-id="f5157-247">Background blur and effects</span></span>
- <span data-ttu-id="f5157-248">廣播/即時事件</span><span class="sxs-lookup"><span data-stu-id="f5157-248">Broadcast/live events</span></span>
- <span data-ttu-id="f5157-249">以位置為基礎的路由（LBR）</span><span class="sxs-lookup"><span data-stu-id="f5157-249">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="f5157-250">通話駐留</span><span class="sxs-lookup"><span data-stu-id="f5157-250">Call park</span></span>
- <span data-ttu-id="f5157-251">通話佇列</span><span class="sxs-lookup"><span data-stu-id="f5157-251">Call queue</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5157-252">如果您目前在 VDI 中執行的團隊沒有 AV 優化，且您使用的功能尚不支援（例如，在應用程式共用時授與控制權），您必須設定 Citrix 原則，以關閉小組重新導向。</span><span class="sxs-lookup"><span data-stu-id="f5157-252">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set Citrix policies to turn off Teams redirection.</span></span> <span data-ttu-id="f5157-253">這表示小組媒體會話不會進行優化。</span><span class="sxs-lookup"><span data-stu-id="f5157-253">This means that Teams media sessions won't be optimized.</span></span> <span data-ttu-id="f5157-254">如需如何設定原則以關閉小組重新導向的步驟，請參閱此[Citrix 網站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html)。</span><span class="sxs-lookup"><span data-stu-id="f5157-254">For steps on how to set policies to turn off Teams redirection, see this [Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html).</span></span>

<span data-ttu-id="f5157-255">我們正在努力新增目前僅適用于非 VDI 環境中的通話與會議功能。</span><span class="sxs-lookup"><span data-stu-id="f5157-255">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="f5157-256">這些可能包括更多系統管理員控制品質、其他螢幕共用案例，以及最近新增至團隊的高級功能。</span><span class="sxs-lookup"><span data-stu-id="f5157-256">These might include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="f5157-257">若要深入瞭解即將推出的功能，請與您的小組代表聯繫。</span><span class="sxs-lookup"><span data-stu-id="f5157-257">Contact your Teams representative to learn more about upcoming features.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="f5157-258">網路需求</span><span class="sxs-lookup"><span data-stu-id="f5157-258">Network requirements</span></span>

<span data-ttu-id="f5157-259">我們建議您評估您的環境，以找出任何風險與需求，這些風險與需求可能會影響您的整體雲端語音及視頻部署。</span><span class="sxs-lookup"><span data-stu-id="f5157-259">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="f5157-260">使用[商務用 Skype 網路評估工具](https://www.microsoft.com/download/details.aspx?id=53885)來測試您的網路是否已準備好供團隊使用。</span><span class="sxs-lookup"><span data-stu-id="f5157-260">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="f5157-261">若要進一步瞭解如何為團隊準備您的網路，請參閱[準備貴組織的小組網路](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="f5157-261">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="f5157-262">從 VDI 上的商務用 Skype 遷移到 VDI 的小組</span><span class="sxs-lookup"><span data-stu-id="f5157-262">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="f5157-263">如果您是從 VDI 的商務用 Skype 遷移到 VDI 的小組，除了兩個應用程式之間的差異之外，也會有一些差異。</span><span class="sxs-lookup"><span data-stu-id="f5157-263">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="f5157-264">在商務用 Skype VDI 中，「團隊 VDI」目前不支援的部分功能如下：</span><span class="sxs-lookup"><span data-stu-id="f5157-264">Some capabilities that aren't currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="f5157-265">使用限制媒體比對的原則控制 VDI 通話體驗</span><span class="sxs-lookup"><span data-stu-id="f5157-265">Control of VDI calling experiences with policies for limiting media bitrate</span></span>
- <span data-ttu-id="f5157-266">在 VDI 中停用某些防病毒功能的每個平臺原則</span><span class="sxs-lookup"><span data-stu-id="f5157-266">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="f5157-267">在應用程式共用時提供控制權並加以控制</span><span class="sxs-lookup"><span data-stu-id="f5157-267">Give and take control when app sharing</span></span>
- <span data-ttu-id="f5157-268">不含音訊的聊天螢幕共用</span><span class="sxs-lookup"><span data-stu-id="f5157-268">Screen share from chat without audio</span></span>
- <span data-ttu-id="f5157-269">同時進行影片和螢幕共用的傳送和接收</span><span class="sxs-lookup"><span data-stu-id="f5157-269">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="f5157-270">Chrome 瀏覽器上的小組與 VDI 的小組桌面應用程式</span><span class="sxs-lookup"><span data-stu-id="f5157-270">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="f5157-271">Chrome 瀏覽器上的小組無法使用 AV 優化來為 VDI 的小組桌面應用程式提供取代。</span><span class="sxs-lookup"><span data-stu-id="f5157-271">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="f5157-272">聊天與共同作業體驗會如期運作。</span><span class="sxs-lookup"><span data-stu-id="f5157-272">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="f5157-273">需要媒體時，有一些可能無法在 Chrome 瀏覽器中滿足使用者預期的體驗：</span><span class="sxs-lookup"><span data-stu-id="f5157-273">When media is needed, there are some experiences that might not meet user expectations on the Chrome browser:</span></span>

- <span data-ttu-id="f5157-274">音訊與視頻資料流程體驗可能不是最佳的。</span><span class="sxs-lookup"><span data-stu-id="f5157-274">The audio and video streaming experience might not be optimal.</span></span> <span data-ttu-id="f5157-275">使用者可能會遇到延遲或降低品質。</span><span class="sxs-lookup"><span data-stu-id="f5157-275">Users might experiences delays or reduced quality.</span></span>
- <span data-ttu-id="f5157-276">在瀏覽器設定中無法使用裝置設定。</span><span class="sxs-lookup"><span data-stu-id="f5157-276">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="f5157-277">裝置管理是透過瀏覽器處理，且需要瀏覽器網站設定中的多項設定。</span><span class="sxs-lookup"><span data-stu-id="f5157-277">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="f5157-278">裝置設定也可能需要在 Windows 裝置管理中設定。</span><span class="sxs-lookup"><span data-stu-id="f5157-278">Device settings might also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="f5157-279">VDI 上的小組與聊天與共同作業</span><span class="sxs-lookup"><span data-stu-id="f5157-279">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="f5157-280">如果您的組織想要只使用團隊中的聊天與共同作業功能，您可以設定使用者層級原則，以關閉小組中的通話與會議功能。</span><span class="sxs-lookup"><span data-stu-id="f5157-280">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span> <span data-ttu-id="f5157-281">此功能層級不需要 Citrix 虛擬 App 與桌上型電腦。</span><span class="sxs-lookup"><span data-stu-id="f5157-281">This feature level doesn't require Citrix Virtual Apps and Desktops.</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="f5157-282">設定原則以關閉通話與會議功能</span><span class="sxs-lookup"><span data-stu-id="f5157-282">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="f5157-283">您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來設定原則。</span><span class="sxs-lookup"><span data-stu-id="f5157-283">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="f5157-284">策略變更可能需要幾個時間（幾個小時）才能傳播。</span><span class="sxs-lookup"><span data-stu-id="f5157-284">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="f5157-285">如果您沒有立即看到特定帳戶的變更，請在幾個小時後再試一次。</span><span class="sxs-lookup"><span data-stu-id="f5157-285">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="f5157-286">[**通話**](teams-calling-policy.md)原則：團隊包含內建的 DisallowCalling 通話原則，其中所有的通話功能都已關閉。</span><span class="sxs-lookup"><span data-stu-id="f5157-286">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="f5157-287">將 DisallowCalling 原則指派給貴組織中的所有使用虛擬化環境中的小組的使用者。</span><span class="sxs-lookup"><span data-stu-id="f5157-287">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="f5157-288">[**會議原則**](meeting-policies-in-teams.md)：團隊包含內建的 AllOff 會議原則，其中所有會議功能都已關閉。</span><span class="sxs-lookup"><span data-stu-id="f5157-288">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="f5157-289">將 AllOff 原則指派給貴組織中的所有使用虛擬化環境中的小組的使用者。</span><span class="sxs-lookup"><span data-stu-id="f5157-289">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f5157-290">使用 Microsoft 團隊系統管理中心指派原則</span><span class="sxs-lookup"><span data-stu-id="f5157-290">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="f5157-291">若要將 DisallowCalling 通話原則和 AllOff 會議原則指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="f5157-291">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="f5157-292">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="f5157-292">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="f5157-293">按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5157-293">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="f5157-294">請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f5157-294">Do the following:</span></span>
    1.  <span data-ttu-id="f5157-295">按一下 [**呼叫原則**] 底下的 [ **DisallowCalling**]。</span><span class="sxs-lookup"><span data-stu-id="f5157-295">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2.  <span data-ttu-id="f5157-296">按一下 [**會議原則**] 底下的 [ **AllOff**]。</span><span class="sxs-lookup"><span data-stu-id="f5157-296">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="f5157-297">按一下 **[** 套用]。</span><span class="sxs-lookup"><span data-stu-id="f5157-297">Click **Apply**.</span></span>

<span data-ttu-id="f5157-298">若要一次將原則指派給多位使用者：</span><span class="sxs-lookup"><span data-stu-id="f5157-298">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="f5157-299">在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]\*\*\*\*，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="f5157-299">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="f5157-300">在 [&#x2713;]\*\*\*\* (核取方塊) 欄中，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="f5157-300">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="f5157-301">若要選取 [所有使用者]，請按一下表格頂端的 [&#x2713;] (核取方塊)。</span><span class="sxs-lookup"><span data-stu-id="f5157-301">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="f5157-302">按一下 [編輯設定]\*\*\*\*，進行所需的變更，然後按一下 [套用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5157-302">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="f5157-303">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f5157-303">Or, you can also do the following:</span></span>

1. <span data-ttu-id="f5157-304">在 Microsoft 團隊系統管理中心的左導覽中，移至您要指派的原則。</span><span class="sxs-lookup"><span data-stu-id="f5157-304">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="f5157-305">例如：</span><span class="sxs-lookup"><span data-stu-id="f5157-305">For example:</span></span>
    - <span data-ttu-id="f5157-306">移至 [**語音**  >  **通話原則**]，然後按一下 [ **DisallowCalling**]。</span><span class="sxs-lookup"><span data-stu-id="f5157-306">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="f5157-307">移至 [**會議**  >  **會議原則**]，然後按一下 [ **AllOff**]。</span><span class="sxs-lookup"><span data-stu-id="f5157-307">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
3. <span data-ttu-id="f5157-308">選取 [管理使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5157-308">Select **Manage users**.</span></span>
4. <span data-ttu-id="f5157-309">在 [管理使用者]\*\*\*\* 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5157-309">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="f5157-310">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="f5157-310">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="f5157-311">完成新增使用者後，請按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="f5157-311">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="f5157-312">使用 PowerShell 指派原則</span><span class="sxs-lookup"><span data-stu-id="f5157-312">Assign policies using PowerShell</span></span>

<span data-ttu-id="f5157-313">下列範例顯示如何使用[授與 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) ，將 DisallowCalling 通話原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="f5157-313">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="f5157-314">若要深入瞭解如何使用 PowerShell 來管理通話原則，請參閱[設定 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="f5157-314">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="f5157-315">下列範例顯示如何使用[授與 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) ，將 AllOff 會議原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="f5157-315">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="f5157-316">若要深入瞭解如何使用 PowerShell 來管理會議原則，請參閱[設定 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="f5157-316">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-citrix-with-calling-and-meetings"></a><span data-ttu-id="f5157-317">使用通話與會議，在 VDI 上將團隊遷移到與 Citrix 進行聊天與共同作業</span><span class="sxs-lookup"><span data-stu-id="f5157-317">Migrate Teams on VDI with chat and collaboration to Citrix with calling and meetings</span></span>

<span data-ttu-id="f5157-318">如果您在 VDI 上有現有的小組實現，且您已將使用者層級原則設定為關閉通話與會議功能，且您是透過 AV 優化來移植到 Citrix，則您必須設定原則來針對 VDI 使用者的小組開啟與會議功能。</span><span class="sxs-lookup"><span data-stu-id="f5157-318">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Citrix with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="f5157-319">設定原則以開啟通話與會議功能</span><span class="sxs-lookup"><span data-stu-id="f5157-319">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="f5157-320">您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來設定通話與會議原則，並指派給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="f5157-320">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="f5157-321">要傳播原則變更，可能需要一些時間（幾個小時）。</span><span class="sxs-lookup"><span data-stu-id="f5157-321">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="f5157-322">如果您沒有立即看到特定帳戶的變更，請在幾個小時後再試一次。</span><span class="sxs-lookup"><span data-stu-id="f5157-322">If you don't see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="f5157-323">[**通話**](teams-calling-policy.md)原則：在團隊中呼叫原則控制使用者可以使用哪些通話功能。</span><span class="sxs-lookup"><span data-stu-id="f5157-323">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="f5157-324">團隊包含內建的 AllowCalling 通話原則，其中所有的通話功能都已開啟。</span><span class="sxs-lookup"><span data-stu-id="f5157-324">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="f5157-325">若要開啟所有通話功能，請指派 AllowCalling 原則。</span><span class="sxs-lookup"><span data-stu-id="f5157-325">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="f5157-326">或者，建立自訂通話原則來開啟您想要的通話功能，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="f5157-326">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span> 

<span data-ttu-id="f5157-327">[**會議原則**](meeting-policies-in-teams.md)：團隊中的會議原則控制使用者可以建立的會議類型，以及由貴組織中的使用者所排程的會議參與者所提供的功能。</span><span class="sxs-lookup"><span data-stu-id="f5157-327">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="f5157-328">團隊包含內建的 AllOn 會議原則，其中所有會議功能都已開啟。</span><span class="sxs-lookup"><span data-stu-id="f5157-328">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="f5157-329">若要開啟所有會議功能，請指派 AllOn 原則。</span><span class="sxs-lookup"><span data-stu-id="f5157-329">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="f5157-330">或者，建立自訂會議原則來開啟您想要的會議功能，並指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="f5157-330">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f5157-331">使用 Microsoft 團隊系統管理中心指派原則</span><span class="sxs-lookup"><span data-stu-id="f5157-331">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="f5157-332">若要將 AllowCalling 通話原則和 AllOn 會議原則指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="f5157-332">To assign the AllowCalling calling policy and the AllOn meeting policy to a user:</span></span>

1. <span data-ttu-id="f5157-333">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="f5157-333">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="f5157-334">按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5157-334">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="f5157-335">請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f5157-335">Do the following:</span></span>
    1.  <span data-ttu-id="f5157-336">按一下 [**呼叫原則**] 底下的 [ **AllowCalling**]。</span><span class="sxs-lookup"><span data-stu-id="f5157-336">Under **Calling policy**, click **AllowCalling**.</span></span>
    2.  <span data-ttu-id="f5157-337">按一下 [**會議原則**] 底下的 [ **AllOn**]。</span><span class="sxs-lookup"><span data-stu-id="f5157-337">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="f5157-338">按一下 **[** 套用]。</span><span class="sxs-lookup"><span data-stu-id="f5157-338">Click **Apply**.</span></span>

<span data-ttu-id="f5157-339">若要一次將原則指派給多位使用者：</span><span class="sxs-lookup"><span data-stu-id="f5157-339">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="f5157-340">在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]\*\*\*\*，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="f5157-340">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="f5157-341">在 [&#x2713;]\*\*\*\* (核取方塊) 欄中，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="f5157-341">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="f5157-342">若要選取 [所有使用者]，請按一下表格頂端的 [ **&#x2713;** （核取符號）。</span><span class="sxs-lookup"><span data-stu-id="f5157-342">To select all users, click the **&#x2713;** (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="f5157-343">按一下 [編輯設定]\*\*\*\*，進行所需的變更，然後按一下 [套用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5157-343">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="f5157-344">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f5157-344">Or, you can also do the following:</span></span>

1. <span data-ttu-id="f5157-345">在 Microsoft 團隊系統管理中心的左導覽中，移至您要指派的原則。</span><span class="sxs-lookup"><span data-stu-id="f5157-345">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="f5157-346">例如：</span><span class="sxs-lookup"><span data-stu-id="f5157-346">For example:</span></span>
    - <span data-ttu-id="f5157-347">移至 [**語音**  >  **通話原則**]，然後按一下 [ **AllowCalling**]。</span><span class="sxs-lookup"><span data-stu-id="f5157-347">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="f5157-348">移至 [**會議**  >  **會議原則**]，然後按一下 [ **AllOn**]。</span><span class="sxs-lookup"><span data-stu-id="f5157-348">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
3. <span data-ttu-id="f5157-349">選取 [管理使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5157-349">Select **Manage users**.</span></span>
4. <span data-ttu-id="f5157-350">在 [管理使用者]\*\*\*\* 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5157-350">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="f5157-351">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="f5157-351">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="f5157-352">完成新增使用者後，請按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="f5157-352">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="f5157-353">使用 PowerShell 指派原則</span><span class="sxs-lookup"><span data-stu-id="f5157-353">Assign policies using PowerShell</span></span>

<span data-ttu-id="f5157-354">下列範例顯示如何使用[授與 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) ，將 AllowCalling 通話原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="f5157-354">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

<span data-ttu-id="f5157-355">若要深入瞭解如何使用 PowerShell 來管理通話原則，請參閱[設定 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="f5157-355">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="f5157-356">下列範例顯示如何使用[授與 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) ，將 AllOn 會議原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="f5157-356">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

<span data-ttu-id="f5157-357">若要深入瞭解如何使用 PowerShell 來管理會議原則，請參閱[設定 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="f5157-357">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="f5157-358">已知問題與限制</span><span class="sxs-lookup"><span data-stu-id="f5157-358">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="f5157-359">用戶端部署、安裝和設定</span><span class="sxs-lookup"><span data-stu-id="f5157-359">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="f5157-360">在每電腦安裝中，VDI 上的團隊不會以非 VDI 團隊用戶端的方式自動更新。</span><span class="sxs-lookup"><span data-stu-id="f5157-360">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="f5157-361">您必須安裝新的 MSI 來更新 VM 影像，如在 VDI 的 [[安裝或更新團隊桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi)] 區段中所述。</span><span class="sxs-lookup"><span data-stu-id="f5157-361">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="f5157-362">您必須卸載目前的版本，才能更新為較新的版本。</span><span class="sxs-lookup"><span data-stu-id="f5157-362">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="f5157-363">團隊應該針對每個使用者或每個電腦來部署。</span><span class="sxs-lookup"><span data-stu-id="f5157-363">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="f5157-364">不支援針對每位使用者和每個電腦並行部署團隊。</span><span class="sxs-lookup"><span data-stu-id="f5157-364">Deployment of Teams for concurrent per user and per machine is not supported.</span></span> <span data-ttu-id="f5157-365">若要從每個電腦或每位使用者遷移到其中一個模式，請遵循卸載程式，然後重新部署到其中一種模式。</span><span class="sxs-lookup"><span data-stu-id="f5157-365">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="f5157-366">Citrix 目前不支援 MacOs 和 Linux 的用戶端。</span><span class="sxs-lookup"><span data-stu-id="f5157-366">Citrix doesn't support MacOs and Linux-based clients at this time.</span></span>
- <span data-ttu-id="f5157-367">Citrix 不支援使用在端點上定義的明確 HTTP proxy。</span><span class="sxs-lookup"><span data-stu-id="f5157-367">Citrix doesn't support the use of explicit HTTP proxies defined on an endpoint.</span></span>

### <a name="calling-and-meetings"></a><span data-ttu-id="f5157-368">通話與會議</span><span class="sxs-lookup"><span data-stu-id="f5157-368">Calling and meetings</span></span>

- <span data-ttu-id="f5157-369">與商務用 Skype 的互通性限制在音訊通話中;沒有任何視頻模態。</span><span class="sxs-lookup"><span data-stu-id="f5157-369">Interoperability with Skype for Business is limited to audio calls; there is no video modality.</span></span>
- <span data-ttu-id="f5157-370">目前不支援雙音調多重頻率（DTMF）與電話系統互動。</span><span class="sxs-lookup"><span data-stu-id="f5157-370">Dual Tone Multi Frequency (DTMF) interaction with telephony systems is currently not supported.</span></span>
- <span data-ttu-id="f5157-371">以匿名使用者身分加入團隊會議不是 AV 優化的。</span><span class="sxs-lookup"><span data-stu-id="f5157-371">Joining Teams meetings as an anonymous user isn't AV-optimized.</span></span> <span data-ttu-id="f5157-372">使用者可以加入會議，且有未優化的體驗。</span><span class="sxs-lookup"><span data-stu-id="f5157-372">The user can join the meeting and have a non-optimized experience.</span></span>
- <span data-ttu-id="f5157-373">在會議或群組通話中只支援單一傳入的視頻資料流程。</span><span class="sxs-lookup"><span data-stu-id="f5157-373">Only a single incoming video stream is supported in meetings or group calls.</span></span> <span data-ttu-id="f5157-374">當多人傳送影片時，任何指定時間只會顯示主要喇叭的影片。</span><span class="sxs-lookup"><span data-stu-id="f5157-374">When multiple people send video, only the dominant speaker's video is shown at any given time.</span></span>
- <span data-ttu-id="f5157-375">內送和外寄的視頻資料流程解析度限制為720p 解析度。</span><span class="sxs-lookup"><span data-stu-id="f5157-375">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span> <span data-ttu-id="f5157-376">這是 WebRTC 的限制。</span><span class="sxs-lookup"><span data-stu-id="f5157-376">This is a WebRTC limitation.</span></span>
- <span data-ttu-id="f5157-377">只支援來自內送相機或畫面共用資料流程的一個影片串流。</span><span class="sxs-lookup"><span data-stu-id="f5157-377">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="f5157-378">當有傳入螢幕共用時，會顯示該螢幕共用，而不是主要喇叭的影片。</span><span class="sxs-lookup"><span data-stu-id="f5157-378">When there's an incoming screen share, that screen share is shown, instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="f5157-379">外寄螢幕共用：</span><span class="sxs-lookup"><span data-stu-id="f5157-379">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="f5157-380">不支援從聊天進行螢幕共用。</span><span class="sxs-lookup"><span data-stu-id="f5157-380">Screen sharing from chat is not supported.</span></span>
    - <span data-ttu-id="f5157-381">不支援應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="f5157-381">Application sharing is not supported.</span></span>
- <span data-ttu-id="f5157-382">授與控制權並加以控制：</span><span class="sxs-lookup"><span data-stu-id="f5157-382">Give control and take control:</span></span>
    - <span data-ttu-id="f5157-383">在螢幕共用或應用程式共用會話期間不支援。</span><span class="sxs-lookup"><span data-stu-id="f5157-383">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="f5157-384">在 PowerPoint 共用會話期間支援。</span><span class="sxs-lookup"><span data-stu-id="f5157-384">Supported during a PowerPoint sharing session.</span></span>
- <span data-ttu-id="f5157-385">在多重監視器設定中進行螢幕共用時，只會共用主要監視器。</span><span class="sxs-lookup"><span data-stu-id="f5157-385">When screen sharing in a multi-monitor setup, only the main monitor is shared.</span></span>
- <span data-ttu-id="f5157-386">不支援 CWA 上的高 DPI 縮放。</span><span class="sxs-lookup"><span data-stu-id="f5157-386">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="f5157-387">針對與 VDI 無關的小組已知問題，請參閱[貴組織中的支援小組](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="f5157-387">For Teams known issues that aren't related to VDI, see [Support Teams in your organization](Known-issues.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f5157-388">疑難排解</span><span class="sxs-lookup"><span data-stu-id="f5157-388">Troubleshooting</span></span>

#### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="f5157-389">Citrix 元件疑難排解</span><span class="sxs-lookup"><span data-stu-id="f5157-389">Troubleshoot Citrix components</span></span>

<span data-ttu-id="f5157-390">如需如何針對 VDA 和 CWA 問題進行疑難排解的資訊，請參閱[此 Citrix 網站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。</span><span class="sxs-lookup"><span data-stu-id="f5157-390">For information on how to troubleshoot VDA and CWA issues, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f5157-391">相關主題</span><span class="sxs-lookup"><span data-stu-id="f5157-391">Related topics</span></span>

- [<span data-ttu-id="f5157-392">使用 MSI 安裝 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="f5157-392">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="f5157-393">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="f5157-393">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="f5157-394">在 Windows 虛擬桌面電腦上使用 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="f5157-394">Use Microsoft Teams on Windows Virtual desktop</span></span>](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)

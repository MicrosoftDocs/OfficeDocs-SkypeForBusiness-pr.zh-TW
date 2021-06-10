---
title: 使用Microsoft Teams 會議室部署Microsoft Endpoint Configuration Manager
author: dstrome
ms.author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: 瞭解如何使用 Microsoft Teams 會議室 部署大型部署Microsoft Endpoint Configuration Manager。
no-loc:
- Microsoft
- Microsoft Corporation
- Microsoft Teams Rooms
- Microsoft Teams Room
- System Center
- Configuration Manager
- Windows
- Surface
- Surface Pro
- Windows PE
- Windows 10
- Windows 10 Enterprise
- Azure
- Azure Monitor
- Log Analytics
- Operations Management Suite
ms.openlocfilehash: 2348d0f3e9d94aed80494155fbaab8288ddd97a6
ms.sourcegitcommit: 95386369e2256ba382b4d6e34adb7473de050b26
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2021
ms.locfileid: "51410109"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="87c90-103">使用 Microsoft Teams 會議室 部署Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="87c90-103">Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="87c90-104">本文提供您所有必要的資訊，以使用 Microsoft Teams 會議室建立您的Microsoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="87c90-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="87c90-105">使用 Configuration Manager 提供的便於使用的方法，您可以將作業系統和其他應用程式部署到多個目標裝置。</span><span class="sxs-lookup"><span data-stu-id="87c90-105">With the easy-to-use methods provided by Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="87c90-106">請使用下列說明的方法，引導您完成 Configuration Manager 組式，並根據您的組織需要自訂本指南中提供的範例套件和腳本。</span><span class="sxs-lookup"><span data-stu-id="87c90-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Microsoft Teams 會議室 Configuration Manager 管理部署程式](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="87c90-108">此解決方案僅使用以Surface Pro型部署進行測試。</span><span class="sxs-lookup"><span data-stu-id="87c90-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="87c90-109">請遵循製造商的指導方針，進行不以Surface Pro。</span><span class="sxs-lookup"><span data-stu-id="87c90-109">Follow the manufacturer's guidelines for configurations that aren't based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="87c90-110">驗證先決條件</span><span class="sxs-lookup"><span data-stu-id="87c90-110">Validate prerequisites</span></span>

<span data-ttu-id="87c90-111">若要使用 configuration Manager Microsoft Teams 會議室部署應用程式，請確保您符合下列先決條件和需求。</span><span class="sxs-lookup"><span data-stu-id="87c90-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="microsoft-endpoint-configuration-manager-requirements"></a><span data-ttu-id="87c90-112">Microsoft Endpoint Configuration Manager需求</span><span class="sxs-lookup"><span data-stu-id="87c90-112">Microsoft Endpoint Configuration Manager requirements</span></span>

-   <span data-ttu-id="87c90-113">Microsoft Endpoint Configuration Manager版本必須至少為 1706 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="87c90-113">Microsoft Endpoint Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="87c90-114">我們建議您使用 1710 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="87c90-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="87c90-115">請查看[Configuration Manager Windows 10](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)支援，以瞭解 Configuration Manager Windows 10支援的版本。</span><span class="sxs-lookup"><span data-stu-id="87c90-115">Check out [Support for Windows 10 in Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="87c90-116">必須安裝適用于 Windows 的 ADK (評定) 部署套件Windows 10版本。</span><span class="sxs-lookup"><span data-stu-id="87c90-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="87c90-117">請參閱適用于不同Windows 10的[ADK](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk)版本，並確保您的部署包含正確的版本。</span><span class="sxs-lookup"><span data-stu-id="87c90-117">See the versions of the [Windows 10 ADK](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="87c90-118">網站系統伺服器必須已指派通訊點角色，且啟動映射應針對 PXE ([PXE](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network)) 啟用網路啟動部署啟用。</span><span class="sxs-lookup"><span data-stu-id="87c90-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="87c90-119">如果未啟用 PXE 支援，您可以使用可啟動的 [媒體進行部署](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) 。</span><span class="sxs-lookup"><span data-stu-id="87c90-119">If PXE support isn't enabled, you can use [bootable media](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="87c90-120">網路存取帳戶必須配置為支援新電腦 (部署) 部署案例。</span><span class="sxs-lookup"><span data-stu-id="87c90-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="87c90-121">若要深入瞭解網路存取帳戶的組組，請參閱 Configuration [Manager 中使用的帳戶](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)。</span><span class="sxs-lookup"><span data-stu-id="87c90-121">To learn more about the configuration of a network access account, see [Accounts used in Configuration Manager](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="87c90-122">建議您啟用[多](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)播支援 ，如果您可能同時將相同的Microsoft Teams 會議室映射部署到多個單位。</span><span class="sxs-lookup"><span data-stu-id="87c90-122">We recommend that you enable [multicast support](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you're likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="87c90-123">網路需求</span><span class="sxs-lookup"><span data-stu-id="87c90-123">Networking requirements</span></span>

-   <span data-ttu-id="87c90-124">您的網路應該具有動態主機組態通訊協定 (DHCP) 伺服器，其為自動 IP 位址分配所配置的子網，Microsoft Teams 會議室單元將部署。</span><span class="sxs-lookup"><span data-stu-id="87c90-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="87c90-125">DHCP 租賃持續時間必須設定為超過影像部署持續時間的值。</span><span class="sxs-lookup"><span data-stu-id="87c90-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="87c90-126">否則，部署可能會失敗。</span><span class="sxs-lookup"><span data-stu-id="87c90-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="87c90-127">您的網路 ，包括切換和虛擬 LANs (VLANs) ，應該會配置為支援 PXE。</span><span class="sxs-lookup"><span data-stu-id="87c90-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="87c90-128">請參閱您的網路廠商，以瞭解有關 IP Helper 和 PXE 組配置的資訊。</span><span class="sxs-lookup"><span data-stu-id="87c90-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="87c90-129">或者，如果 [未啟用](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) PXE 支援，您也可以使用可啟動媒體進行部署。</span><span class="sxs-lookup"><span data-stu-id="87c90-129">Alternatively, you can use [bootable media](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn't enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="87c90-130">針對Surface Pro，只有使用 Microsoft 的乙太網路適配 (或固定基座) 才能從網路啟動 PXE 啟動裝置。</span><span class="sxs-lookup"><span data-stu-id="87c90-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="87c90-131">協力廠商乙太網路介面卡不支援使用 PXE Surface Pro。</span><span class="sxs-lookup"><span data-stu-id="87c90-131">Third-party Ethernet adapters don't support PXE boot with Surface Pro.</span></span> <span data-ttu-id="87c90-132">請參閱 [乙太網路介面卡和 Surface 部署](/surface/ethernet-adapters-and-surface-device-deployment) 以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="87c90-132">See [Ethernet adapters and Surface deployment](/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="87c90-133">設定Microsoft Endpoint Configuration Manager部署</span><span class="sxs-lookup"><span data-stu-id="87c90-133">Configure Microsoft Endpoint Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="87c90-134">本文假設您已經擁有正常的 Configuration Manager 部署，而且不會詳述從頭部署和設定 Configuration Manager 所需的所有步驟。</span><span class="sxs-lookup"><span data-stu-id="87c90-134">This article assumes you already have a healthy Configuration Manager deployment, and doesn't detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="87c90-135">檔[與組Microsoft Endpoint Configuration Manager](/configmgr/)是很好的資源;如果您尚未部署 Configuration Manager，建議您從這些資源開始。</span><span class="sxs-lookup"><span data-stu-id="87c90-135">The [documentation and the configuration guidance](/configmgr/) on the Microsoft Endpoint Configuration Manager is a great resource; we recommend you start with these resources if you haven't yet deployed Configuration Manager.</span></span>

<span data-ttu-id="87c90-136">請使用下列指示來確認作業系統部署 (OSD) 功能已正確配置。</span><span class="sxs-lookup"><span data-stu-id="87c90-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="87c90-137">驗證及升級 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="87c90-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="87c90-138">在 Configuration Manager 主控台中，前往 **管理** \> **更新和服務**。</span><span class="sxs-lookup"><span data-stu-id="87c90-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="87c90-139">檢查已安裝的建和尚未安裝的適用更新。</span><span class="sxs-lookup"><span data-stu-id="87c90-139">Check the installed build and applicable updates that haven't been installed yet.</span></span>

3.  <span data-ttu-id="87c90-140">在 [Configuration Manager 中Windows 10支援;](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)如果您需要升級部署，請選取您想要安裝的更新，然後選取 **下載**。</span><span class="sxs-lookup"><span data-stu-id="87c90-140">Review [Support for Windows 10 in Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="87c90-141">下載完成後，選取更新，然後選取安裝 **更新套件**。</span><span class="sxs-lookup"><span data-stu-id="87c90-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="87c90-142">設定發佈點以支援 PXE 和多播</span><span class="sxs-lookup"><span data-stu-id="87c90-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="87c90-143">在 Configuration Manager 主控台中，前往 **系統** \> **管理發佈點**。</span><span class="sxs-lookup"><span data-stu-id="87c90-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="87c90-144">選取將提供部署服務的通訊Microsoft Teams 會議室伺服器，**然後選取** 屬性 。</span><span class="sxs-lookup"><span data-stu-id="87c90-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="87c90-145">選取 **PXE** Tab，然後確保已啟用下列設定：</span><span class="sxs-lookup"><span data-stu-id="87c90-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="87c90-146">啟用用戶端的 PXE 支援</span><span class="sxs-lookup"><span data-stu-id="87c90-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="87c90-147">允許此通訊點回應傳入的 PXE 要求</span><span class="sxs-lookup"><span data-stu-id="87c90-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="87c90-148">啟用未知的電腦支援</span><span class="sxs-lookup"><span data-stu-id="87c90-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="87c90-149">*選擇性：* 若要啟用多播支援，請選取 **多重廣播** 選項卡，並確保已啟用下列設定：</span><span class="sxs-lookup"><span data-stu-id="87c90-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="87c90-150">啟用多播以同時將資料傳送至多個用戶端</span><span class="sxs-lookup"><span data-stu-id="87c90-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="87c90-151">根據網路小組的建議設定 UDP 埠範圍</span><span class="sxs-lookup"><span data-stu-id="87c90-151">Configure the UDP port range as per your network team's recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="87c90-152">設定網路存取帳戶</span><span class="sxs-lookup"><span data-stu-id="87c90-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="87c90-153">在 Configuration Manager 主控台中，前往 **管理** \> **網站組組** \> **網站**，然後選取網站。</span><span class="sxs-lookup"><span data-stu-id="87c90-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="87c90-154">在 **設定群組** 中，選取 **設定網站元件** \> **軟體發佈**。</span><span class="sxs-lookup"><span data-stu-id="87c90-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="87c90-155">選取網路 **存取帳戶選項卡** 。設定一或多個帳戶， **然後選取確定**。</span><span class="sxs-lookup"><span data-stu-id="87c90-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="87c90-156">除了在通訊點伺服器上從網路存取此電腦之外，帳戶不需要任何特殊許可權。</span><span class="sxs-lookup"><span data-stu-id="87c90-156">The accounts don't need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="87c90-157">適合使用一般網域使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="87c90-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="87c90-158">詳細資訊，請參閱 [Configuration Manager 中使用的帳戶](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)。</span><span class="sxs-lookup"><span data-stu-id="87c90-158">For more information, see [Accounts used in Configuration Manager](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="87c90-159">設定開機圖像</span><span class="sxs-lookup"><span data-stu-id="87c90-159">Configure a boot image</span></span>

1.  <span data-ttu-id="87c90-160">在 Configuration Manager 主控台中，前往 **軟體庫** \> **作業系統** \> **啟動映射**。</span><span class="sxs-lookup"><span data-stu-id="87c90-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="87c90-161">選取 **x64 (的)**， **然後選取** 屬性 。</span><span class="sxs-lookup"><span data-stu-id="87c90-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="87c90-162">選取資料來源 **選項卡，** 然後從啟用 **PXE** 的通訊點啟用部署此啟動映射。</span><span class="sxs-lookup"><span data-stu-id="87c90-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="87c90-163">選取選擇性 **元件選項卡** 以安裝必要的元件：</span><span class="sxs-lookup"><span data-stu-id="87c90-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="87c90-164">選取星號圖示，然後搜尋 **WINPE-HTA** (HTML) </span><span class="sxs-lookup"><span data-stu-id="87c90-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="87c90-165">選取 **確定** ，將 HTML 應用程式支援新到啟動映射。</span><span class="sxs-lookup"><span data-stu-id="87c90-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="87c90-166">*選擇性：* 若要自訂部署體驗，請選取自訂 **選項卡** 。</span><span class="sxs-lookup"><span data-stu-id="87c90-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="87c90-167">若要 **在部署 (，)** 命令提示符，才啟用命令支援。</span><span class="sxs-lookup"><span data-stu-id="87c90-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="87c90-168">啟用此功能後，您隨時都可以在部署期間選取 **F8，** 以啟動命令提示。</span><span class="sxs-lookup"><span data-stu-id="87c90-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="87c90-169">您也可以指定部署期間要顯示的自訂背景影像。</span><span class="sxs-lookup"><span data-stu-id="87c90-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="87c90-170">若要設定影像，請啟用在 UNC 路徑 (自訂背景圖像 **檔案，** 然後選取您的背景。</span><span class="sxs-lookup"><span data-stu-id="87c90-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="87c90-171">當系統詢問時，請選取 **是** ，並將更新的啟動映射發佈至您的發佈點。</span><span class="sxs-lookup"><span data-stu-id="87c90-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="87c90-172">詳細資訊，請參閱使用 [Configuration Manager 管理啟動映射](/configmgr/osd/get-started/manage-boot-images)。</span><span class="sxs-lookup"><span data-stu-id="87c90-172">For more information, see [Manage boot images with Configuration Manager](/configmgr/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="87c90-173">您可以建立可啟動的 USB 媒體，針對沒有 PXE 支援的環境啟動 Configuration Manager 工作順序型部署。</span><span class="sxs-lookup"><span data-stu-id="87c90-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="87c90-174">可啟動媒體僅包含啟動映射、選擇性的預啟動命令及其所需檔案，以及 Configuration Manager 二進位檔案，可支援啟動至 Windows PE，並連接到 Configuration Manager 以完成其餘的部署程式。</span><span class="sxs-lookup"><span data-stu-id="87c90-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="87c90-175">詳細資訊，請參閱 [建立可啟動的媒體](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)。</span><span class="sxs-lookup"><span data-stu-id="87c90-175">For more information, see [Create bootable media](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="87c90-176">建立 Configuration Manager 套件</span><span class="sxs-lookup"><span data-stu-id="87c90-176">Create Configuration Manager packages</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87c90-177">每個 SRS 安裝程式版本所需的作業系統版本會隨著每個 MSI 版本而變更。</span><span class="sxs-lookup"><span data-stu-id="87c90-177">The required operating system version for each SRS installer version changes with every MSI release.</span></span> <span data-ttu-id="87c90-178">若要判斷給定 MSI 的最佳作業系統版本，請執行一次主控台設定腳本。</span><span class="sxs-lookup"><span data-stu-id="87c90-178">To determine the best operating system version for a given MSI, run the console setup script once.</span></span> <span data-ttu-id="87c90-179">若要深入瞭解，請參閱使用 Microsoft Teams 會議室[部署Microsoft Endpoint Configuration Manager。](rooms-scale.md)</span><span class="sxs-lookup"><span data-stu-id="87c90-179">To learn more, see [Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager](rooms-scale.md).</span></span>

<span data-ttu-id="87c90-180">Configuration Manager 需要許多套件來部署及設定Microsoft Teams 會議室單位。</span><span class="sxs-lookup"><span data-stu-id="87c90-180">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="87c90-181">您需要建立並設定下列套件，然後將這些套件發佈至已指派通訊點伺服器角色的 Configuration Manager 網站系統。</span><span class="sxs-lookup"><span data-stu-id="87c90-181">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="87c90-182">**套件名稱**</span><span class="sxs-lookup"><span data-stu-id="87c90-182">**Package name**</span></span>                     | <span data-ttu-id="87c90-183">**類型**</span><span class="sxs-lookup"><span data-stu-id="87c90-183">**Type**</span></span>               | <span data-ttu-id="87c90-184">**描述**</span><span class="sxs-lookup"><span data-stu-id="87c90-184">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="87c90-185">SRS v2 - SRS 應用程式套件</span><span class="sxs-lookup"><span data-stu-id="87c90-185">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="87c90-186">套裝軟體</span><span class="sxs-lookup"><span data-stu-id="87c90-186">Software package</span></span>       | <span data-ttu-id="87c90-187">適用于部署套件Microsoft Teams 會議室套件</span><span class="sxs-lookup"><span data-stu-id="87c90-187">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="87c90-188">SRS v2 - Sysprep 套件</span><span class="sxs-lookup"><span data-stu-id="87c90-188">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="87c90-189">套裝軟體</span><span class="sxs-lookup"><span data-stu-id="87c90-189">Software package</span></span>       | <span data-ttu-id="87c90-190">自訂裝置套件Unattended.xml設定Microsoft Teams 會議室單位</span><span class="sxs-lookup"><span data-stu-id="87c90-190">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="87c90-191">SRS v2 - Set-SRSComputerName套件</span><span class="sxs-lookup"><span data-stu-id="87c90-191">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="87c90-192">套裝軟體</span><span class="sxs-lookup"><span data-stu-id="87c90-192">Software package</span></span>       | <span data-ttu-id="87c90-193">HTML 應用程式套件 (HTA) 在部署期間指派電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="87c90-193">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="87c90-194">SRS v2 - 設定 SRS 設定</span><span class="sxs-lookup"><span data-stu-id="87c90-194">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="87c90-195">套裝軟體</span><span class="sxs-lookup"><span data-stu-id="87c90-195">Software package</span></span>       | <span data-ttu-id="87c90-196">套件以設定應用程式Microsoft Teams 會議室部署</span><span class="sxs-lookup"><span data-stu-id="87c90-196">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="87c90-197">SRS v2 - OS 更新套件</span><span class="sxs-lookup"><span data-stu-id="87c90-197">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="87c90-198">套裝軟體</span><span class="sxs-lookup"><span data-stu-id="87c90-198">Software package</span></span>       | <span data-ttu-id="87c90-199">部署強制作業系統更新的套件</span><span class="sxs-lookup"><span data-stu-id="87c90-199">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="87c90-200">SRS v2 - 根憑證套件</span><span class="sxs-lookup"><span data-stu-id="87c90-200">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="87c90-201">套裝軟體</span><span class="sxs-lookup"><span data-stu-id="87c90-201">Software package</span></span>       | <span data-ttu-id="87c90-202">選擇性 - 套件以部署根憑證 (網域聯入單位) </span><span class="sxs-lookup"><span data-stu-id="87c90-202">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="87c90-203">SRS v2 - Microsoft Monitoring Agent套件</span><span class="sxs-lookup"><span data-stu-id="87c90-203">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="87c90-204">套裝軟體</span><span class="sxs-lookup"><span data-stu-id="87c90-204">Software package</span></span>       | <span data-ttu-id="87c90-205">選擇性 - 套件以部署及設定 Microsoft Operations Management Suite 代理程式</span><span class="sxs-lookup"><span data-stu-id="87c90-205">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="87c90-206">SRS v2 - WinPE 背景套件</span><span class="sxs-lookup"><span data-stu-id="87c90-206">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="87c90-207">套裝軟體</span><span class="sxs-lookup"><span data-stu-id="87c90-207">Software package</span></span>       | <span data-ttu-id="87c90-208">自訂背景影像套件，以用於開機影像</span><span class="sxs-lookup"><span data-stu-id="87c90-208">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="87c90-209">Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="87c90-209">Windows 10 Enterprise</span></span>                | <span data-ttu-id="87c90-210">作業系統圖像</span><span class="sxs-lookup"><span data-stu-id="87c90-210">Operating system image</span></span> | <span data-ttu-id="87c90-211">安裝安裝檔案套件 (.wim) </span><span class="sxs-lookup"><span data-stu-id="87c90-211">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="87c90-212">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="87c90-212">Surface Pro</span></span>                          | <span data-ttu-id="87c90-213">驅動程式套件</span><span class="sxs-lookup"><span data-stu-id="87c90-213">Driver package</span></span>         | <span data-ttu-id="87c90-214">適用于 Microsoft Surface Pro</span><span class="sxs-lookup"><span data-stu-id="87c90-214">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="87c90-215">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="87c90-215">Surface Pro 4</span></span>                        | <span data-ttu-id="87c90-216">驅動程式套件</span><span class="sxs-lookup"><span data-stu-id="87c90-216">Driver package</span></span>         | <span data-ttu-id="87c90-217">適用于 Microsoft Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="87c90-217">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="87c90-218">詳細資訊，請參閱 [Configuration Manager 中的套件和程式](/configmgr/apps/deploy-use/packages-and-programs)。</span><span class="sxs-lookup"><span data-stu-id="87c90-218">For more information, see [Packages and programs in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="87c90-219">建立套件來源檔案的資料夾</span><span class="sxs-lookup"><span data-stu-id="87c90-219">Create folders for the package source files</span></span>

<span data-ttu-id="87c90-220">Configuration Manager 要求當套件來源檔案第一次建立及更新時，以特定資料夾結構整理。</span><span class="sxs-lookup"><span data-stu-id="87c90-220">Configuration Manager requires package source files to be organized in a specific folder structure when they're first created and when they're updated.</span></span>

<span data-ttu-id="87c90-221">在中央系統管理Microsoft Endpoint Configuration Manager或主網站上，或在您用於託管套件來源檔案的伺服器共用上建立下列資料夾結構：</span><span class="sxs-lookup"><span data-stu-id="87c90-221">Create the following folder structure on the Microsoft Endpoint Configuration Manager central administration site or primary site, or on a server share you're using to host package source files:</span></span>

-   <span data-ttu-id="87c90-222">SRS v2 - Microsoft Monitoring Agent套件</span><span class="sxs-lookup"><span data-stu-id="87c90-222">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="87c90-223">SRS v2 - OS 更新套件</span><span class="sxs-lookup"><span data-stu-id="87c90-223">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="87c90-224">SRS v2 - 根憑證套件</span><span class="sxs-lookup"><span data-stu-id="87c90-224">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="87c90-225">SRS v2 - Set-SRSComputerName套件</span><span class="sxs-lookup"><span data-stu-id="87c90-225">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="87c90-226">SRS v2 - SRS 應用程式套件</span><span class="sxs-lookup"><span data-stu-id="87c90-226">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="87c90-227">SRS v2 - 設定 SRS 設定</span><span class="sxs-lookup"><span data-stu-id="87c90-227">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="87c90-228">SRS v2 - Sysprep 套件</span><span class="sxs-lookup"><span data-stu-id="87c90-228">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="87c90-229">司機</span><span class="sxs-lookup"><span data-stu-id="87c90-229">Drivers</span></span>
    -   <span data-ttu-id="87c90-230">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="87c90-230">Surface Pro</span></span>
    -   <span data-ttu-id="87c90-231">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="87c90-231">Surface Pro 4</span></span>
-   <span data-ttu-id="87c90-232">作業系統</span><span class="sxs-lookup"><span data-stu-id="87c90-232">Operating Systems</span></span>
    -   <span data-ttu-id="87c90-233">Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="87c90-233">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="87c90-234">您也可以下載 [並使用](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) zip 檔案，其中包含套件的資料夾結構、您需要使用的腳本，以及您需要輸入的工作順序範本。</span><span class="sxs-lookup"><span data-stu-id="87c90-234">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="87c90-235">建立監控代理程式套件</span><span class="sxs-lookup"><span data-stu-id="87c90-235">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="87c90-236">從 下載監控代理程式 <https://go.microsoft.com/fwlink/?LinkId=828603> 。</span><span class="sxs-lookup"><span data-stu-id="87c90-236">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="87c90-237">開啟命令提示視窗，Microsoft Monitoring Agent **/C：** 在命令提示符中輸入 /C，將套件解壓縮到 **SRS v2 -** Microsoft Monitoring AgentMMASetup-AMD64.exe套件資料夾。</span><span class="sxs-lookup"><span data-stu-id="87c90-237">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="87c90-238">在 Configuration Manager 主控台中，前往 **軟體文件庫** \> **應用程式管理** \> **套件**，然後選取建立 **套件**。</span><span class="sxs-lookup"><span data-stu-id="87c90-238">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="87c90-239">輸入下列資訊以建立套件：</span><span class="sxs-lookup"><span data-stu-id="87c90-239">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="87c90-240">名稱<strong>：SRS v2 - Microsoft Monitoring Agent套件</strong></span><span class="sxs-lookup"><span data-stu-id="87c90-240">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="87c90-241">製造商<strong>：Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="87c90-241">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="87c90-242">版本<strong>：8.1.11081.0</strong> (輸入下載的安裝檔案) </span><span class="sxs-lookup"><span data-stu-id="87c90-242">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="87c90-243">選取此 **套件包含來源檔案** 核取方塊，輸入 **SRS v2 -** Microsoft Monitoring Agent套件資料夾的路徑，然後選取下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-243">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="87c90-244">選取 **不建立程式，** 然後選取 下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-244">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="87c90-245">查看確認 **設定頁面** ，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-245">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="87c90-246">選取 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="87c90-246">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="87c90-247">建立作業系統更新套件</span><span class="sxs-lookup"><span data-stu-id="87c90-247">Create the operating system updates package</span></span>

1. <span data-ttu-id="87c90-248">在 **SRS v2 - OS 更新套件** 資料夾中，建立名為Install-SRSv2-OS-Updates.ps1 **的新 PowerShell 腳本**。</span><span class="sxs-lookup"><span data-stu-id="87c90-248">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="87c90-249">將下列腳本 **複製到Install-SRSv2-OS-Updates.ps1腳本** 。</span><span class="sxs-lookup"><span data-stu-id="87c90-249">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="87c90-250">或者，您也可以從這裡下載Install-SRSv2-OS-Updates.ps1[腳本。](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="87c90-250">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```
   # Install-SRSv2-OS-Updates.ps1
   $strPath = split-path -parent $MyInvocation.MyCommand.Definition
   $total = gci $strPath *.msu | measure | Select-Object -expand Count
   $i = 0
   gci $strPath *.msu | ForEach-Object {
     $i++
     WUSA ""$_.FullName /quiet /norestart""
     Write-Progress -activity "Applying Mandatory Updates" -status "Installing
     $_ .. $i of $total" -percentComplete (($i / $total) * 100)
     Wait-Process -name wusa
   }
   ```
3. <span data-ttu-id="87c90-251">將必填Windows更新套件下載至同一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="87c90-251">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="87c90-252">本文發佈時，只需要[KB4056892。](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu)</span><span class="sxs-lookup"><span data-stu-id="87c90-252">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="87c90-253">檢查[設定Microsoft Teams 會議室](console.md)主控台，以查看是否需要任何其他更新。</span><span class="sxs-lookup"><span data-stu-id="87c90-253">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="87c90-254">在 Configuration Manager 主控台中，前往 **軟體文件庫** \> **應用程式管理** \> **套件**，然後選取建立 **套件**。</span><span class="sxs-lookup"><span data-stu-id="87c90-254">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="87c90-255">輸入下列資訊以建立套件：</span><span class="sxs-lookup"><span data-stu-id="87c90-255">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="87c90-256">名稱 **：SRS v2 – OS 更新套件**</span><span class="sxs-lookup"><span data-stu-id="87c90-256">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="87c90-257">製造商 **：Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="87c90-257">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="87c90-258">版本 **：1.0.0**</span><span class="sxs-lookup"><span data-stu-id="87c90-258">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="87c90-259">選取此 **套件包含來源檔案** 核取方塊，輸入 **SRS v2 - OS 更新套件** 資料夾的路徑，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-259">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="87c90-260">選取 **不建立程式，** 然後選取 下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-260">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="87c90-261">查看確認 **設定頁面** ，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-261">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="87c90-262">選取 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="87c90-262">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="87c90-263">建立根憑證套件 (選項) </span><span class="sxs-lookup"><span data-stu-id="87c90-263">Create the root certificate package (optional)</span></span>

<span data-ttu-id="87c90-264">您可以建立此套件，以發佈不會加入 Active Directory 網域之裝置之根憑證。</span><span class="sxs-lookup"><span data-stu-id="87c90-264">You create this package to distribute the root certificate for devices that won't be joined to an Active Directory domain.</span></span> <span data-ttu-id="87c90-265">只有在同時套用下列兩個條件時，才能建立此套件：</span><span class="sxs-lookup"><span data-stu-id="87c90-265">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="87c90-266">您的部署包括內部部署 Lync 或 商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="87c90-266">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="87c90-267">Microsoft Teams 會議室單位已配置為在工作組中工作，而非網域成員。</span><span class="sxs-lookup"><span data-stu-id="87c90-267">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="87c90-268">將根憑證複製到 **SRS v2 – 根憑證套件** 資料夾。</span><span class="sxs-lookup"><span data-stu-id="87c90-268">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="87c90-269">在 Configuration Manager 主控台中，前往 **軟體文件庫** \> **應用程式管理** \> **套件**，然後選取建立 **套件**。</span><span class="sxs-lookup"><span data-stu-id="87c90-269">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="87c90-270">輸入下列資訊以建立套件：</span><span class="sxs-lookup"><span data-stu-id="87c90-270">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="87c90-271">名稱 **：SRS v2 – 根憑證套件**</span><span class="sxs-lookup"><span data-stu-id="87c90-271">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="87c90-272">製造商 *：貴組織的名稱*</span><span class="sxs-lookup"><span data-stu-id="87c90-272">Manufacturer: *Your organization's name*</span></span>
    -   <span data-ttu-id="87c90-273">版本 **：1.0.0**</span><span class="sxs-lookup"><span data-stu-id="87c90-273">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="87c90-274">選取此 **套件包含來源檔案** 核取方塊，輸入 **SRS v2 – 根憑證套件** 資料夾的路徑，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-274">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="87c90-275">選取 **不建立程式，** 然後選取 下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-275">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="87c90-276">查看確認 **設定頁面** ，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-276">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="87c90-277">選取 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="87c90-277">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="87c90-278">建立Microsoft Teams 會議室套件</span><span class="sxs-lookup"><span data-stu-id="87c90-278">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="87c90-279">從 下載最新版本的 **Microsoft Teams 會議室** <https://go.microsoft.com/fwlink/?linkid=851168> 套件，然後安裝至工作站。</span><span class="sxs-lookup"><span data-stu-id="87c90-279">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="87c90-280">從 C 複製內容：將 **\\ x86 \\** (程式檔案) Skype會議室系統部署套件複製到 **SRS v2 - SRS** 應用程式套件資料夾。</span><span class="sxs-lookup"><span data-stu-id="87c90-280">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="87c90-281">在 Configuration Manager 主控台中，前往 **軟體文件庫** \> **應用程式管理** \> **套件**，然後選取建立 **套件**。</span><span class="sxs-lookup"><span data-stu-id="87c90-281">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="87c90-282">輸入下列資訊以建立套件：</span><span class="sxs-lookup"><span data-stu-id="87c90-282">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="87c90-283">名稱 **：SRS v2 – SRS 應用程式套件**</span><span class="sxs-lookup"><span data-stu-id="87c90-283">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="87c90-284">製造商 **：Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="87c90-284">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="87c90-285">版本 **：3.1.104.0** (輸入下載安裝檔案的版本) </span><span class="sxs-lookup"><span data-stu-id="87c90-285">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="87c90-286">選取此 **套件包含來源檔案** 核取方塊，輸入 **SRS v2 – SRS 應用程式套件** 資料夾的路徑，然後選取下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-286">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="87c90-287">選取 **不建立程式，** 然後選取 下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-287">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="87c90-288">查看確認 **設定頁面** ，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-288">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="87c90-289">選取 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="87c90-289">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="87c90-290">建立電腦名稱稱工作分派套件</span><span class="sxs-lookup"><span data-stu-id="87c90-290">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="87c90-291">在 **SRS v2 - Set-SRSComputerName套件** 資料夾中，建立名為 **Set-SRSComputerName.hta 的新 HTML 應用程式** 。</span><span class="sxs-lookup"><span data-stu-id="87c90-291">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="87c90-292">將下列腳本複製到 **Set-SRSComputerName.hta** 檔案。</span><span class="sxs-lookup"><span data-stu-id="87c90-292">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="87c90-293">或者，您也可以從這裡下載 Set-SRSComputerName.hta [檔案](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="87c90-293">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
    ```HTML
    <!DOCTYPE HTML>
    <html>
    <head>
    <title>Set SRS Computer Name</title>
    <HTA:APPLICATION
      APPLICATIONNAME="Set SRS Computer Name"
      ID="SetSRSComputerName"
      VERSION="1.0"
      SCROLL="no"
      SINGLEINSTANCE="yes"
      WINDOWSTATE="maximize"
      MaximizeButton="no"
      MinimizeButton="no"
      SysMenu="no"
      ShowInTaskbar="no"
      Caption="no"
      />
    <style type="text/css">
    body {
        background-color: #fdfeff;
        color: darkblue;
        font-family: Calibri;
        font-size: 12pt;
        margin: 4em 3em;
    }
    </style>
    </head>
    <script language="VBScript">
    Public strNewComputerName
    Sub GenerateComputerName()
        strComputer = "."
        Set objWMIService = GetObject("winmgmts:\\" & strComputer & "\root\cimv2")
        Set colItems = objWMIService.ExecQuery("Select * from Win32_BIOS",,48)
        For Each objItem in colItems
            strSerialNumber = objItem.SerialNumber
        Next
        strNewComputerName = "SRS-"  & right(replace(strSerialNumber, "-","") ,10)
        TextArea1.innerHTML = "The serial number of the device: " & strSerialNumber
        strHTMLText = strHTMLText & "<br> Computer name to be assigned: <font color = red>" & strNewComputerName & "</font>"
        strHTMLText = strHTMLText & "<br><br> Click Accept to use this as the computer name and continue deployment, or Change to set a new name."
        strHTMLText = strHTMLText & "<p><input type=""button"" value=""Accept"" name = ""Accept_Button"" onclick=""SetComputerName"" />"
        strHTMLText = strHTMLText & " <input type=""button"" value=""Change"" name = ""Change_Button"" onclick=""ChangeComputerName"" />"
        TextArea2.innerHTML = strHTMLText
    End Sub

    Sub SetComputerName()
        dim result
        result = MsgBox("Computer Name to be assigned: " & strNewComputerName &vbcrlf & "Are you sure you want to continue?", 36)
        If (result = vbYes) then
            SET env = CreateObject("Microsoft.SMS.TSEnvironment")
            env("OSDComputerName") = strNewComputerName
            self.close
        elseif (result = vbNo) then
            Window_OnLoad
        End If
    End Sub

    Sub UpdateComputerName()
        strNewComputerName = newcomputername.value
        if len(trim(strNewComputerName)) = 0 then
            MsgBox "Computer name cannot be empty." &vbcrlf & "Update and try again.",16
            exit sub
        end if
        SetComputerName
    End Sub

    Sub ChangeComputerName()
        TextArea2.innerHTML = "<p>Type the new computer name and click Accept:  <input type=""text"" name=""newcomputername"" value =" & strNewComputerName & " />"
        TextArea2.innerHTML = TextArea2.innerHTML & "<br><input type=""button"" value=""Update"" name = ""Update_Button"" onclick=""UpdateComputerName"" />"
    End Sub

    Sub Window_OnLoad
        Set oTSProgressUI = CreateObject("Microsoft.SMS.TsProgressUI")
        oTSProgressUI.CloseProgressDialog
        GenerateComputerName
    End Sub
    </script>

    <body>
    <span id = "TextArea1"></span>
    <span id = "TextArea2">
    </span>
    </body>
    </html>

    ```
3.  <span data-ttu-id="87c90-294">在 Configuration Manager 主控台中，前往 **軟體文件庫** \> **應用程式管理** \> **套件**，然後選取建立 **套件**。</span><span class="sxs-lookup"><span data-stu-id="87c90-294">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="87c90-295">輸入下列資訊以建立套件：</span><span class="sxs-lookup"><span data-stu-id="87c90-295">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="87c90-296">名稱 **：SRS v2 - Set-SRSComputerName套件**</span><span class="sxs-lookup"><span data-stu-id="87c90-296">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="87c90-297">製造商 **：Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="87c90-297">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="87c90-298">版本 **：1.0.0**</span><span class="sxs-lookup"><span data-stu-id="87c90-298">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="87c90-299">選取此 **套件包含來源檔案** 核取方塊，輸入 **SRS v2 - Set-SRSComputerName套件資料夾** 的路徑，然後選取下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-299">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="87c90-300">選取 **不建立程式，** 然後選取 下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-300">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="87c90-301">查看確認 **設定頁面** ，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-301">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="87c90-302">選取 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="87c90-302">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="87c90-303">建立 Sysprep 套件</span><span class="sxs-lookup"><span data-stu-id="87c90-303">Create the Sysprep package</span></span>

1. <span data-ttu-id="87c90-304">在 **SRS v2 – Sysprep 套件** 資料夾中，建立名為Unattend.xml **的新 XML 檔案** 。</span><span class="sxs-lookup"><span data-stu-id="87c90-304">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="87c90-305">將下列文字複製到 **Unattend.xml檔案。**</span><span class="sxs-lookup"><span data-stu-id="87c90-305">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="87c90-306">或者，您也可以從這裡下載[Unattend.xml檔案。](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="87c90-306">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```XML
   <?xml version="1.0" encoding="utf-8"?>
   <unattend xmlns="urn:schemas-microsoft-com:unattend">
   <settings pass="specialize">
       <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <DisableBootMenu>1</DisableBootMenu>
           <DisplayDisabled>1</DisplayDisabled>
       </component>
       <component name="Microsoft-Windows-powercpl" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <PreferredPlan>8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c</PreferredPlan>
       </component>
   </settings>
   <settings pass="oobeSystem">
       <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <OOBE>
               <HideEULAPage>true</HideEULAPage>
               <HideLocalAccountScreen>true</HideLocalAccountScreen>
               <HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>
               <HideOnlineAccountScreens>true</HideOnlineAccountScreens>
               <HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>
               <SkipMachineOOBE>true</SkipMachineOOBE>
               <SkipUserOOBE>true</SkipUserOOBE>
               <ProtectYourPC>1</ProtectYourPC>
           </OOBE>
           <AutoLogon>
               <Enabled>true</Enabled>
               <Username>Skype</Username>
               <Password>
                   <Value>UABhAHMAcwB3AG8AcgBkAA==</Value>
                   <PlainText>false</PlainText>
               </Password>
           </AutoLogon>
           <UserAccounts>
               <LocalAccounts>
                   <LocalAccount wcm:action="add">
                       <Password>
                           <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
                           <PlainText>false</PlainText>
                       </Password>
                       <Name>Admin</Name>
                       <Group>Administrators</Group>
                       <DisplayName>Administrator</DisplayName>
                       <Description>Administrator</Description>
                   </LocalAccount>
               </LocalAccounts>
           </UserAccounts>
       </component>
   </settings>
   <cpi:offlineImage cpi:source="wim:h:/install.wim#Windows 10 Enterprise" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
   </unattend>
   ```
3. <span data-ttu-id="87c90-307">在 Configuration Manager 主控台中，前往 **軟體文件庫** \> **應用程式管理** \> **套件**，然後選取建立 **套件**。</span><span class="sxs-lookup"><span data-stu-id="87c90-307">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="87c90-308">輸入下列資訊以建立套件：</span><span class="sxs-lookup"><span data-stu-id="87c90-308">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="87c90-309">名稱 **：SRS v2 - Sysprep 套件**</span><span class="sxs-lookup"><span data-stu-id="87c90-309">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="87c90-310">製造商 **：Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="87c90-310">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="87c90-311">版本 **：1.0.0**</span><span class="sxs-lookup"><span data-stu-id="87c90-311">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="87c90-312">選取此 **套件包含來源檔案** 核取方塊，輸入 **SRS v2 – Sysprep 套件資料夾** 的路徑，然後選取下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-312">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="87c90-313">選取 **不建立程式**，然後選取 下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-313">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="87c90-314">查看確認 **設定頁面** ，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-314">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="87c90-315">選取 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="87c90-315">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="87c90-316">建立Windows 10 企業版套件</span><span class="sxs-lookup"><span data-stu-id="87c90-316">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="87c90-317">取得Windows 10 企業版 x64 媒體，然後將 **install.wim** 檔案複製到作業系統Windows 10 企業版 **資料夾。 \\**</span><span class="sxs-lookup"><span data-stu-id="87c90-317">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="87c90-318">在 Configuration Manager 主控台中，前往 **軟體庫** \> **作業系統** \> **映射**，然後選取新增 **作業系統映射**。</span><span class="sxs-lookup"><span data-stu-id="87c90-318">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="87c90-319">指定您剛剛複製 **的 install.wim** 檔案路徑，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-319">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="87c90-320">更新版本 **欄位**，以符合影像Windows 10 企業版的組Windows 10 企業版，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-320">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="87c90-321">請閱 **閱詳細資料** 頁面，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-321">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="87c90-322">選取 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="87c90-322">Select **Close**.</span></span>

<span data-ttu-id="87c90-323">詳細資訊，請參閱使用 [Configuration Manager 管理 OS 映射](/configmgr/osd/get-started/manage-operating-system-images)。</span><span class="sxs-lookup"><span data-stu-id="87c90-323">For more information, see [Manage OS images with Configuration Manager](/configmgr/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="87c90-324">建立Surface Pro驅動程式套件</span><span class="sxs-lookup"><span data-stu-id="87c90-324">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="87c90-325">Microsoft Teams 會議室和Surface Pro都Surface Pro 4。</span><span class="sxs-lookup"><span data-stu-id="87c90-325">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="87c90-326">您需要為環境中擁有的每個Surface Pro建立驅動程式套件。</span><span class="sxs-lookup"><span data-stu-id="87c90-326">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87c90-327">驅動程式必須與部署套件Windows 10 企業版版本Microsoft Teams 會議室相容。</span><span class="sxs-lookup"><span data-stu-id="87c90-327">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="87c90-328">若要詳細資訊，請參閱 [下載 Surface](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) 裝置的最新固件和驅動程式，以及 [設定主機](console.md)。</span><span class="sxs-lookup"><span data-stu-id="87c90-328">For more information, see [Download the latest firmware and drivers for Surface devices](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="87c90-329">下載最新的驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="87c90-329">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="87c90-330">適用于Surface Pro：<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="87c90-330">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="87c90-331">適用于Surface Pro 4：<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="87c90-331">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="87c90-332">解壓縮下載的驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="87c90-332">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="87c90-333">開啟命令提示視窗，然後于命令提示符輸入下列其中一個命令：</span><span class="sxs-lookup"><span data-stu-id="87c90-333">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="87c90-334">在 Configuration Manager 主控台中，前往 **軟體文件庫** \> **作業系統** \> **驅動程式**，然後選取匯出 **驅動程式**。</span><span class="sxs-lookup"><span data-stu-id="87c90-334">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="87c90-335">選取 **下列** 網路路徑 (UNC) 中所有驅動程式，選取來源資料夾 (例如 C：_Sources驅動程式Surface Pro) ，然後選取下一 \\ 步 \\ \\ 。 </span><span class="sxs-lookup"><span data-stu-id="87c90-335">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="87c90-336">在指定 **已輸入驅動程式** 詳細資料頁面上，選取列出的所有驅動程式，然後選取啟用這些驅動程式並允許 **電腦安裝。**</span><span class="sxs-lookup"><span data-stu-id="87c90-336">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="87c90-337">選取 **類別**，建立符合 Surface 模型的新類別， **選取確定，** 然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-337">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="87c90-338">選取 **新套件**。</span><span class="sxs-lookup"><span data-stu-id="87c90-338">Select **New Package**.</span></span>

8.  <span data-ttu-id="87c90-339">指定與模型Surface Pro的套件名稱、輸入資料夾路徑以將驅動程式套件檔案儲存在中、選取確定，然後選取下一 **步**。 </span><span class="sxs-lookup"><span data-stu-id="87c90-339">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="87c90-340">在啟動 **影像** 頁面上，請確保未選取任何開機影像，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-340">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="87c90-341">選取 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="87c90-341">Select **Close**.</span></span>

11. <span data-ttu-id="87c90-342">前往 **軟體文檔** 庫 \> **作業系統** \> **驅動程式\*\*\*\*\>**，選取資料夾建立資料夾，然後輸入符合您剛剛Surface Pro驅動程式之模型的資料夾名稱。</span><span class="sxs-lookup"><span data-stu-id="87c90-342">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="87c90-343">將所有已輸入的驅動程式移至新建立的資料夾，以便更輕鬆地流覽和操作。</span><span class="sxs-lookup"><span data-stu-id="87c90-343">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="87c90-344">針對您可能擁有的其他Surface Pro重複相同的步驟。</span><span class="sxs-lookup"><span data-stu-id="87c90-344">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="87c90-345">詳細資訊，請參閱在 [Configuration Manager 中管理驅動程式](/configmgr/osd/get-started/manage-drivers)。</span><span class="sxs-lookup"><span data-stu-id="87c90-345">For more information, see [Manage drivers in Configuration Manager](/configmgr/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="87c90-346">建立Microsoft Teams 會議室套件</span><span class="sxs-lookup"><span data-stu-id="87c90-346">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="87c90-347">在 Configuration Manager 主控台中，前往 **軟體文件庫** \> **應用程式管理** \> **套件**，然後選取建立 **套件**。</span><span class="sxs-lookup"><span data-stu-id="87c90-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="87c90-348">輸入下列資訊以建立套件：</span><span class="sxs-lookup"><span data-stu-id="87c90-348">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="87c90-349">名稱 **：SRS v2 - 設定 SRS 安裝套件**</span><span class="sxs-lookup"><span data-stu-id="87c90-349">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="87c90-350">製造商 **：Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="87c90-350">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="87c90-351">版本 **：1.0.0**</span><span class="sxs-lookup"><span data-stu-id="87c90-351">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="87c90-352">選取此 **套件包含來源檔案** 核取方塊，輸入 **SRS v2 - 設定 SRS 安裝程式** 資料夾的路徑，然後選取下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-352">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="87c90-353">選取 **不建立程式**，然後選取 下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-353">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="87c90-354">查看確認 **設定頁面** ，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-354">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="87c90-355">選取 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="87c90-355">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="87c90-356">發佈 Configuration Manager 套件</span><span class="sxs-lookup"><span data-stu-id="87c90-356">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="87c90-357">所有套件都必須分散到已在 Configuration Manager 階層中指派通訊點角色的伺服器。</span><span class="sxs-lookup"><span data-stu-id="87c90-357">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="87c90-358">請遵循下列指示來啟動套件發佈。</span><span class="sxs-lookup"><span data-stu-id="87c90-358">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="87c90-359">發佈軟體套件。</span><span class="sxs-lookup"><span data-stu-id="87c90-359">Distribute software packages.</span></span>

    1.  <span data-ttu-id="87c90-360">在 Configuration Manager 主控台中，前往 **軟體庫** \> **應用程式管理** \> **套件**。</span><span class="sxs-lookup"><span data-stu-id="87c90-360">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="87c90-361">選取要發佈的所有軟體套件，然後選取發佈 **內容**。</span><span class="sxs-lookup"><span data-stu-id="87c90-361">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="87c90-362">查看套件清單，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-362">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="87c90-363">視您的 Configuration Manager 階層 (將所有通訊點伺服器新) 到清單中，然後選取下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-363">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="87c90-364">選取 **下一** 步，然後 **選取** 關閉 。</span><span class="sxs-lookup"><span data-stu-id="87c90-364">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="87c90-365">發佈驅動程式套件。</span><span class="sxs-lookup"><span data-stu-id="87c90-365">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="87c90-366">在 Configuration Manager 主控台中，前往 **軟體庫** \> **作業系統** \> **驅動程式套件**。</span><span class="sxs-lookup"><span data-stu-id="87c90-366">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="87c90-367">選取所有要散發的驅動程式套件，然後選取發佈 **內容**。</span><span class="sxs-lookup"><span data-stu-id="87c90-367">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="87c90-368">查看套件清單，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-368">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="87c90-369">視您的 Configuration Manager 階層 (將所有通訊點伺服器新) 到清單中，然後選取下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-369">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="87c90-370">選取 **下一** 步，然後 **選取** 關閉 。</span><span class="sxs-lookup"><span data-stu-id="87c90-370">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="87c90-371">發佈作業系統套件。</span><span class="sxs-lookup"><span data-stu-id="87c90-371">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="87c90-372">在 Configuration Manager 主控台中，前往 **軟體文件庫** \> **作業系統** \> **映射**。</span><span class="sxs-lookup"><span data-stu-id="87c90-372">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="87c90-373">選取您想要發佈的所有作業系統影像，然後選取發佈 **內容**。</span><span class="sxs-lookup"><span data-stu-id="87c90-373">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="87c90-374">查看套件清單，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-374">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="87c90-375">視您的 Configuration Manager 階層 (將所有通訊點伺服器新) 到清單中，然後選取下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-375">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="87c90-376">選取 **下一** 步，然後 **選取** 關閉 。</span><span class="sxs-lookup"><span data-stu-id="87c90-376">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="87c90-377">套件發佈可能需要一些時間，視封裝大小、Configuration Manager 階層、通訊點伺服器數量，以及您的網路可用頻寬而不同。</span><span class="sxs-lookup"><span data-stu-id="87c90-377">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="87c90-378">您必須先發佈所有套件，才能開始部署Microsoft Teams 會議室裝置。</span><span class="sxs-lookup"><span data-stu-id="87c90-378">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="87c90-379">您可以到監控發佈狀態內容狀態，在 Configuration Manager 主控台中查看 \> **套件** \> **發佈的狀態**。</span><span class="sxs-lookup"><span data-stu-id="87c90-379">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="87c90-380">Configuration Manager 工作順序</span><span class="sxs-lookup"><span data-stu-id="87c90-380">Configuration Manager task sequences</span></span>

<span data-ttu-id="87c90-381">您可以使用任務順序與 Configuration Manager 自動化將作業系統映射部署到目的電腦的步驟。</span><span class="sxs-lookup"><span data-stu-id="87c90-381">You use task sequences with Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="87c90-382">若要以自動化的方式部署 Microsoft Teams 會議室 裝置，請建立參照啟動映射的工作順序，以啟動目標 Microsoft Teams 會議室 電腦、您想要安裝的 Windows 10 企業版 作業系統映射，以及任何其他內容 ，例如其他應用程式或軟體更新。</span><span class="sxs-lookup"><span data-stu-id="87c90-382">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="87c90-383">輸入範例工作順序</span><span class="sxs-lookup"><span data-stu-id="87c90-383">Import the sample task sequence</span></span>

<span data-ttu-id="87c90-384">您可以下載並輕鬆輸入範例工作順序，並自訂以滿足您的需求。</span><span class="sxs-lookup"><span data-stu-id="87c90-384">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="87c90-385">[**下載**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) 範例工作順序，然後將下載的 zip 檔案複製到共用位置。</span><span class="sxs-lookup"><span data-stu-id="87c90-385">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="87c90-386">在 Configuration Manager 主控台中，前往 **軟體文件庫** \> **作業系統** \> **工作順序**，然後選取匯出 **工作順序**。</span><span class="sxs-lookup"><span data-stu-id="87c90-386">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="87c90-387">選取 **流覽**，前往您用於步驟 1 的共用資料夾位置，選取 Microsoft Teams 會議室 部署 (**EN-US**) .zip檔案，然後選取下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-387">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="87c90-388">將 **動作** 設定 **為建立新**，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-388">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="87c90-389">確認設定，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-389">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="87c90-390">選取 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="87c90-390">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="87c90-391">驗證參考套件已正確連結至每個工作順序步驟。</span><span class="sxs-lookup"><span data-stu-id="87c90-391">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="87c90-392">選取已輸入的工作順序， **然後選取** 編輯 。</span><span class="sxs-lookup"><span data-stu-id="87c90-392">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="87c90-393">工作順序編輯器隨即開啟並顯示部署及設定工作單元所需的每個Microsoft Teams 會議室步驟。</span><span class="sxs-lookup"><span data-stu-id="87c90-393">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="87c90-394">逐步完成每個步驟並完成建議的更新：</span><span class="sxs-lookup"><span data-stu-id="87c90-394">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="87c90-395">**在 PE Windows** 重新開機：此步驟會重新開機，然後將電腦引導至 Windows PXE。</span><span class="sxs-lookup"><span data-stu-id="87c90-395">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="87c90-396">此步驟不需要變更。</span><span class="sxs-lookup"><span data-stu-id="87c90-396">No changes are required for this step.</span></span>

   2. <span data-ttu-id="87c90-397">**分區磁片 0 – UEFI：** 此步驟會抹掉磁片設定，並依據設定設定建立分區。</span><span class="sxs-lookup"><span data-stu-id="87c90-397">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="87c90-398">建議您不要對此步驟進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="87c90-398">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="87c90-399">**設定 SRS 電腦名稱稱**：此步驟包含 HTML 應用程式，提供 UI 以在部署期間為Microsoft Teams 會議室裝置設定電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="87c90-399">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="87c90-400">這是一個選擇性的步驟，但只有在您想要透過替代程式管理電腦命名時，才能停用此步驟。</span><span class="sxs-lookup"><span data-stu-id="87c90-400">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="87c90-401">確認已 **選取 SRS v2 - Set-SRSComputerName** 套件。</span><span class="sxs-lookup"><span data-stu-id="87c90-401">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="87c90-402">如果不是，請流覽至套件並選取它。</span><span class="sxs-lookup"><span data-stu-id="87c90-402">If it isn't, browse to the package and select it.</span></span>

   4. <span data-ttu-id="87c90-403">**應用程式作業系統**：此步驟會指定要部署的作業系統映射，以及要使用無人值守的 Sysprep 答案檔案。</span><span class="sxs-lookup"><span data-stu-id="87c90-403">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="87c90-404">確認已選取Windows 10 企業版圖像檔案的正確選項。</span><span class="sxs-lookup"><span data-stu-id="87c90-404">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="87c90-405">確認已啟用自訂安裝的無人值守或 **Sysprep** 答案檔案，且已選取 **SRS v2 - Sysprep 套件** 。</span><span class="sxs-lookup"><span data-stu-id="87c90-405">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="87c90-406">此外，也請確保 **將** 檔案名設為 **unattend.xml。**</span><span class="sxs-lookup"><span data-stu-id="87c90-406">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="87c90-407">**應用程式Windows 設定：** 此步驟會收集安裝Windows相關資訊。</span><span class="sxs-lookup"><span data-stu-id="87c90-407">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="87c90-408">根據您的需求提供授權和註冊資訊，包括產品金鑰、本地系統管理員帳戶密碼 (時區) 。</span><span class="sxs-lookup"><span data-stu-id="87c90-408">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="87c90-409">**將網路設定：** 此步驟可讓您指定工作組或 Active Directory 功能變數名稱和組織單位。</span><span class="sxs-lookup"><span data-stu-id="87c90-409">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="87c90-410">請參閱[Skype會議室系統](domain-joining-considerations.md)網域加入考慮，瞭解您以 Actve Directory 網域成員Microsoft Teams 會議室部署裝置時所需的建議動作。</span><span class="sxs-lookup"><span data-stu-id="87c90-410">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="87c90-411">**適用驅動程式：** 此步驟及其子步驟會依據您擁有的版本模型，Surface Pro部署適用的裝置驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="87c90-411">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="87c90-412">更新每個步驟以指定與此部署相關聯的相關驅動程式套件。</span><span class="sxs-lookup"><span data-stu-id="87c90-412">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="87c90-413">每個驅動程式套件都經過配置，Windows管理工具 (WMI) 篩選，根據產品與Surface Pro部署相關的驅動程式和Surface Pro。</span><span class="sxs-lookup"><span data-stu-id="87c90-413">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="87c90-414">我們強烈建議您不要變更這些驅動程式的組配置，否則部署可能會失敗。</span><span class="sxs-lookup"><span data-stu-id="87c90-414">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="87c90-415">**設定Windows和 Configuration Manager：** 此步驟會部署並設定 Configuration Manager 用戶端。</span><span class="sxs-lookup"><span data-stu-id="87c90-415">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="87c90-416">更新此步驟以指定內建的 Configuration Manager 用戶端套件。</span><span class="sxs-lookup"><span data-stu-id="87c90-416">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="87c90-417">**安裝根憑證**：此步驟會發佈未加入網域的裝置之根憑證，因此預設為選擇性且停用。</span><span class="sxs-lookup"><span data-stu-id="87c90-417">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="87c90-418">如果您需要將根憑證部署到每個單元，Microsoft Teams 會議室步驟。</span><span class="sxs-lookup"><span data-stu-id="87c90-418">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="87c90-419">如果您需要執行此步驟，請確認已選取 **SRS v2 -** 根憑證套件和停用 **64 位** 檔案系統重新導向。</span><span class="sxs-lookup"><span data-stu-id="87c90-419">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="87c90-420">**安裝和設定監控代理** 程式：此步驟會安裝 64 位版本的 Microsoft Azure 監視器代理程式，並設定代理程式以連接到您的記錄分析工作區。</span><span class="sxs-lookup"><span data-stu-id="87c90-420">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="87c90-421">此步驟預設為停用。</span><span class="sxs-lookup"><span data-stu-id="87c90-421">This step is disabled by default.</span></span> <span data-ttu-id="87c90-422">只有在您打算使用監控代理程式監控您的裝置健康情況時，才能Microsoft Teams 會議室步驟。</span><span class="sxs-lookup"><span data-stu-id="87c90-422">Enable this step only if you're going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="87c90-423">編輯此步驟並更新命令列參數，以指定 **您的工作區識別碼** 和 **工作區金鑰**。</span><span class="sxs-lookup"><span data-stu-id="87c90-423">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="87c90-424">請參閱 [設定 Azure](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) 監控的測試裝置，以取得操作管理套件工作區識別碼和主鍵詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="87c90-424">See [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="87c90-425">確認已 **選取 SRS v2 – Microsoft Monitoring Agent套件** 和 **停用 64 位檔案系統重新導向**。</span><span class="sxs-lookup"><span data-stu-id="87c90-425">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="87c90-426">有關監控您的 Microsoft Teams 會議室 部署健康情況詳細資訊，請參閱使用 Azure[監視器](azure-monitor-plan.md)規劃 Microsoft Teams 會議室 管理、使用[Azure 監視器](azure-monitor-deploy.md)部署 Microsoft Teams 會議室 管理，以及使用[Azure 監視器](azure-monitor-manage.md)管理 Microsoft Teams 會議室 裝置。</span><span class="sxs-lookup"><span data-stu-id="87c90-426">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span>

   11. <span data-ttu-id="87c90-427">**複製 SRS v2 組** Microsoft Teams 會議室：此步驟會從部署套件將所需的設定和組Microsoft Teams 會議室複製到本地硬碟。</span><span class="sxs-lookup"><span data-stu-id="87c90-427">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="87c90-428">此步驟不需要自訂。</span><span class="sxs-lookup"><span data-stu-id="87c90-428">No customization is required for this step.</span></span>
       -   <span data-ttu-id="87c90-429">確認已 **選取 SRS v2 - SRS 應用程式套件** 和 **停用 64 位檔案系統重新** 導向。</span><span class="sxs-lookup"><span data-stu-id="87c90-429">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="87c90-430">**Install-SRSv2-OS-Updates：** 此步驟會部署任何必要的作業系統更新，Microsoft Teams 會議室部署。</span><span class="sxs-lookup"><span data-stu-id="87c90-430">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="87c90-431">請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="87c90-431">Do the following:</span></span>
       -   <span data-ttu-id="87c90-432">檢查[設定Microsoft Teams 會議室主控台](console.md)以查看需要哪些更新。</span><span class="sxs-lookup"><span data-stu-id="87c90-432">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="87c90-433">確認您的 **SRS v2 – OS 更新套件** 包含所有必要的更新。</span><span class="sxs-lookup"><span data-stu-id="87c90-433">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="87c90-434">確認已 **選取 SRS v2 – OS 更新** 套件。</span><span class="sxs-lookup"><span data-stu-id="87c90-434">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="87c90-435">確認 PowerShell 執行策略設定為 **旁路**。</span><span class="sxs-lookup"><span data-stu-id="87c90-435">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="87c90-436">**重新開機電腦**：此步驟在安裝強制作業系統更新之後，會重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="87c90-436">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="87c90-437">此步驟不需要自訂。</span><span class="sxs-lookup"><span data-stu-id="87c90-437">No customization is required for this step.</span></span>

   14. <span data-ttu-id="87c90-438">**設定Windows元件**：此步驟會設定Windows功能。</span><span class="sxs-lookup"><span data-stu-id="87c90-438">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="87c90-439">此步驟不需要自訂。</span><span class="sxs-lookup"><span data-stu-id="87c90-439">No customization is required for this step.</span></span>

   15. <span data-ttu-id="87c90-440">**重新開機電腦**：此步驟會重新開機電腦，Windows功能之後。</span><span class="sxs-lookup"><span data-stu-id="87c90-440">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="87c90-441">此步驟不需要自訂。</span><span class="sxs-lookup"><span data-stu-id="87c90-441">No customization is required for this step.</span></span>

   16. <span data-ttu-id="87c90-442">**新增本地Skype** 使用者：此步驟會建立Skype帳戶，用來自動Windows並啟動Microsoft Teams 會議室應用程式。</span><span class="sxs-lookup"><span data-stu-id="87c90-442">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="87c90-443">此步驟沒有任何相關聯的軟體套件，而且不需要自訂。</span><span class="sxs-lookup"><span data-stu-id="87c90-443">This step doesn't have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="87c90-444">**設定及設定 SRS 應用程式**：此步驟會Microsoft Teams 會議室作業系統的下一次開機時設定應用程式安裝。</span><span class="sxs-lookup"><span data-stu-id="87c90-444">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="87c90-445">確認已 **選取 SRS v2 - 設定 SRS 設定套件** 和停用 **64 位檔案系統重新** 導向。</span><span class="sxs-lookup"><span data-stu-id="87c90-445">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87c90-446">工作順序步驟必須按照提供的順序進行，這一點非常重要。</span><span class="sxs-lookup"><span data-stu-id="87c90-446">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="87c90-447">修改步驟順序或配置其他步驟可能會中斷部署。</span><span class="sxs-lookup"><span data-stu-id="87c90-447">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="87c90-448">**設定及設定 SRS 應用程式** 步驟必須是工作順序的最後一個步驟，否則部署可能會失敗。</span><span class="sxs-lookup"><span data-stu-id="87c90-448">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="87c90-449">建立任務順序的部署</span><span class="sxs-lookup"><span data-stu-id="87c90-449">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="87c90-450">選取工作順序， **然後選取** 部署 。</span><span class="sxs-lookup"><span data-stu-id="87c90-450">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="87c90-451">選取 **流覽** 以選取要部署的目標集合。</span><span class="sxs-lookup"><span data-stu-id="87c90-451">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="87c90-452">選取 **所有未知電腦** ，然後選取 **確定**。</span><span class="sxs-lookup"><span data-stu-id="87c90-452">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="87c90-453">選取 下 **一個**。</span><span class="sxs-lookup"><span data-stu-id="87c90-453">Select **Next**.</span></span>

5. <span data-ttu-id="87c90-454">在 **用途** 下 **拉清單中** 選取可用的選項。</span><span class="sxs-lookup"><span data-stu-id="87c90-454">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="87c90-455">在下列清單中選取只有媒體和 **PXE，** 然後選取下一 **步**。 </span><span class="sxs-lookup"><span data-stu-id="87c90-455">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="87c90-456">將用途 **設定為可用\*\*\*\*非常重要。**</span><span class="sxs-lookup"><span data-stu-id="87c90-456">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="87c90-457">請確定用途 **未\*\*\*\*設定為\*\*\*\*必要的**。</span><span class="sxs-lookup"><span data-stu-id="87c90-457">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="87c90-458">此外，請確定您選取 **的只有媒體和 PXE** 在下列 **的可用。**</span><span class="sxs-lookup"><span data-stu-id="87c90-458">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="87c90-459">將這些值設定為其他專案可能會導致所有電腦在開機時Microsoft Teams 會議室部署映射。</span><span class="sxs-lookup"><span data-stu-id="87c90-459">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="87c90-460">請勿指定任何排程，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-460">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="87c90-461">請勿在使用者體驗區段內 **變更任何** 專案，並選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-461">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="87c90-462">請勿在通知 **區段內** 變更任何內容，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-462">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="87c90-463">請勿變更通訊點區段 **內的內容** ，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-463">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="87c90-464">確認設定，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-464">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="87c90-465">選取 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="87c90-465">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="87c90-466">驗證和疑難排解解決方案</span><span class="sxs-lookup"><span data-stu-id="87c90-466">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="87c90-467">完成任務順序Microsoft Endpoint Configuration Manager，您必須執行測試執行，以驗證任務順序可以部署及設定Microsoft Teams 會議室單位。</span><span class="sxs-lookup"><span data-stu-id="87c90-467">After you've completed the Microsoft Endpoint Configuration Manager task sequences, you'll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="87c90-468">連線其中一個支援的乙太網路介面卡，或使用 Surface Dock，將測試裝置連接到有線網路。</span><span class="sxs-lookup"><span data-stu-id="87c90-468">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="87c90-469">如果 PXE 啟動功能尚未針對您的環境進行配置，您可以使用您先前所建立 USB 快閃磁碟機上的啟動[](/configmgr/osd/deploy-use/create-bootable-media)映射，從 USB 啟動並連接到 Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="87c90-469">If PXE boot functionality hasn't been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](/configmgr/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="87c90-470">存取固件並啟動 PXE 啟動：</span><span class="sxs-lookup"><span data-stu-id="87c90-470">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="87c90-471">請確保 Surface 裝置已關閉電源。</span><span class="sxs-lookup"><span data-stu-id="87c90-471">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="87c90-472">按住向上 **音量** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="87c90-472">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="87c90-473">按並放開 **Power** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="87c90-473">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="87c90-474">裝置開始啟動後，放開 **音量增加** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="87c90-474">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="87c90-475">選取 **啟動組組**。</span><span class="sxs-lookup"><span data-stu-id="87c90-475">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="87c90-476">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="87c90-476">Do one of the following:</span></span>

        -   <span data-ttu-id="87c90-477">選取 **PXE 啟動**，然後將它拖曳到清單頂端。</span><span class="sxs-lookup"><span data-stu-id="87c90-477">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="87c90-478">或者，您也可以在網路介面卡上向左滑動，以立即啟動至裝置。</span><span class="sxs-lookup"><span data-stu-id="87c90-478">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="87c90-479">這不會影響啟動順序。</span><span class="sxs-lookup"><span data-stu-id="87c90-479">This won't affect the boot order.</span></span>
        -   <span data-ttu-id="87c90-480">選取保留啟動媒體的 USB 快閃磁碟機。</span><span class="sxs-lookup"><span data-stu-id="87c90-480">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="87c90-481">選取 **離開**，然後選取 立即 **重新開機**。</span><span class="sxs-lookup"><span data-stu-id="87c90-481">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="87c90-482">當系統提示時，選取 **Enter** 進行網路開機服務。</span><span class="sxs-lookup"><span data-stu-id="87c90-482">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="87c90-483">WindowsPE 會載入至記憶體，而工作順序精靈會啟動。</span><span class="sxs-lookup"><span data-stu-id="87c90-483">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="87c90-484">選取 **下一** 步以繼續。</span><span class="sxs-lookup"><span data-stu-id="87c90-484">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="87c90-485">選取您先前所輸入的工作順序，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="87c90-485">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="87c90-486">在已應用磁片組配置之後，系統會提示您指定裝置的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="87c90-486">After the disk configuration is applied, you'll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="87c90-487">使用者介面會根據裝置上的序號顯示Surface Pro名稱。</span><span class="sxs-lookup"><span data-stu-id="87c90-487">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="87c90-488">您可以接受建議的名稱，或指定新的名稱。</span><span class="sxs-lookup"><span data-stu-id="87c90-488">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="87c90-489">請遵循電腦名稱稱作業畫面上的指示。</span><span class="sxs-lookup"><span data-stu-id="87c90-489">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="87c90-490">當您選取接受 **時**，部署即會開始。</span><span class="sxs-lookup"><span data-stu-id="87c90-490">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="87c90-491">其餘的部署程式是自動的，不需要使用者輸入。</span><span class="sxs-lookup"><span data-stu-id="87c90-491">The rest of the deployment process is automatic and doesn't ask for any more user input.</span></span>

9.  <span data-ttu-id="87c90-492">部署工作順序設定完成裝置之後，會看到下列設定畫面，要求您設定Microsoft Teams 會議室設定。</span><span class="sxs-lookup"><span data-stu-id="87c90-492">After the deployment task sequence finishes configuring the device, you'll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![應用程式的初始設定Microsoft Teams 會議室畫面](../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="87c90-494">將Surface Pro插入Microsoft Teams 會議室主控台，然後設定應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="87c90-494">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="87c90-495">驗證已部署Microsoft Teams 會議室[中所列的](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)功能。</span><span class="sxs-lookup"><span data-stu-id="87c90-495">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="87c90-496">若要疑難排解安裝失敗的問題，請檢查 **SMSTS.log** 檔案，該檔案會記錄在 Configuration Manager 工作順序中執行的所有步驟。</span><span class="sxs-lookup"><span data-stu-id="87c90-496">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="87c90-497">SMSTS.log 檔案會儲存在多個路徑的其中一個，視建立程式階段而不同。</span><span class="sxs-lookup"><span data-stu-id="87c90-497">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="87c90-498">檢查下表，找出 SMSTS.log 檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="87c90-498">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="87c90-499">**部署階段**</span><span class="sxs-lookup"><span data-stu-id="87c90-499">**Deployment phase**</span></span>                                                            | <span data-ttu-id="87c90-500">**任務順序記錄路徑**</span><span class="sxs-lookup"><span data-stu-id="87c90-500">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="87c90-501">WINPE，在 HDD 格式之前</span><span class="sxs-lookup"><span data-stu-id="87c90-501">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="87c90-502">\\X：Windows temp \\ \\ smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="87c90-502">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="87c90-503">WINPE，在 HDD 格式之後</span><span class="sxs-lookup"><span data-stu-id="87c90-503">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="87c90-504">\\C：_SMSTaskSequence \\ \\ 記錄 Smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="87c90-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="87c90-505">在安裝 Configuration Manager 代理程式之前部署的作業系統</span><span class="sxs-lookup"><span data-stu-id="87c90-505">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="87c90-506">\\c：_SMSTaskSequence \\ \\ 記錄 Smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="87c90-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="87c90-507">已部署作業系統和 Configuration Manager 代理程式</span><span class="sxs-lookup"><span data-stu-id="87c90-507">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="87c90-508">%windir% \\ System32 \\ ccm \\ log \\ Smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="87c90-508">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="87c90-509">任務循序執行完成</span><span class="sxs-lookup"><span data-stu-id="87c90-509">Task sequence execution complete</span></span>                                                | <span data-ttu-id="87c90-510">%windir% \\ System32 \\ ccm \\ log \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="87c90-510">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="87c90-511">在工作順序期間，您隨時都可以選取 **F8** 以開啟命令主控台，然後存取 SMSTS.log 檔案。</span><span class="sxs-lookup"><span data-stu-id="87c90-511">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="87c90-512">若要疑難排解 PXE 啟動問題，請檢查 Configuration Manager 伺服器上 PXE 動作特有的兩個記錄檔案：</span><span class="sxs-lookup"><span data-stu-id="87c90-512">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="87c90-513">位於 Configuration Manager 安裝記錄目錄中的 **Pxcontrol.log**</span><span class="sxs-lookup"><span data-stu-id="87c90-513">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="87c90-514">**Smspxe.log**，位於 Configuration Manager Management Point (MP) 目錄</span><span class="sxs-lookup"><span data-stu-id="87c90-514">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="87c90-515">若要瞭解可用於進一步疑難排解 Configuration Manager 安裝疑難排解的完整記錄檔案清單，請參閱Microsoft Endpoint Configuration Manager[記錄檔案參照](/configmgr/core/plan-design/hierarchy/log-files)。</span><span class="sxs-lookup"><span data-stu-id="87c90-515">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see the Microsoft Endpoint Configuration Manager [Log file reference](/configmgr/core/plan-design/hierarchy/log-files).</span></span>

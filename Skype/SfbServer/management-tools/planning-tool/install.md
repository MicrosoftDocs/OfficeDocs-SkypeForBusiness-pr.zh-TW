---
title: 在商務用 Skype Server 2015 中安裝規劃工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: 在您使用商務用 Skype Server 2015 規劃工具開始設計及規劃商務用 Skype Server 2015 基礎結構之前，您必須先安裝規劃工具。 規劃工具不需要部署到屬於您計畫安裝商務用 Skype Server 2015 的網域或基礎結構中的工作站或伺服器上。 規劃工具附帶的讀我檔案詳細說明安裝及使用此工具的重要資訊。 為了清楚起見，自述檔中的部分資訊是重複的。
ms.openlocfilehash: 902249e042694a37594c6dc0b753b0c1388c0729
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834723"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a><span data-ttu-id="8f886-106">在商務用 Skype Server 2015 中安裝規劃工具</span><span class="sxs-lookup"><span data-stu-id="8f886-106">Install the Planning Tool in Skype for Business Server 2015</span></span>

<span data-ttu-id="8f886-107">在您使用商務用 Skype Server 2015 規劃工具開始設計及規劃商務用 Skype Server 2015 基礎結構之前，您必須先安裝規劃工具。</span><span class="sxs-lookup"><span data-stu-id="8f886-107">Before you begin designing and planning your Skype for Business Server 2015 infrastructure by using the Skype for Business Server 2015 Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="8f886-108">規劃工具不需要部署到屬於您計畫安裝商務用 Skype Server 2015 的網域或基礎結構中的工作站或伺服器上。</span><span class="sxs-lookup"><span data-stu-id="8f886-108">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Skype for Business Server 2015.</span></span> <span data-ttu-id="8f886-109">規劃工具附帶的讀我檔案詳細說明安裝及使用此工具的重要資訊。</span><span class="sxs-lookup"><span data-stu-id="8f886-109">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="8f886-110">為了清楚起見，自述檔中的部分資訊是重複的。</span><span class="sxs-lookup"><span data-stu-id="8f886-110">Some of the information in the Readme file is duplicated here for clarity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f886-111">規劃工具需要安裝要安裝該工具之電腦的系統管理員權利和許可權的使用者。</span><span class="sxs-lookup"><span data-stu-id="8f886-111">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>

<span data-ttu-id="8f886-112">規劃工具的安裝及作業支援的作業系統包括：</span><span class="sxs-lookup"><span data-stu-id="8f886-112">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

- <span data-ttu-id="8f886-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="8f886-113">Windows 10</span></span>

- <span data-ttu-id="8f886-114">Windows 8</span><span class="sxs-lookup"><span data-stu-id="8f886-114">Windows 8</span></span>

- <span data-ttu-id="8f886-115">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="8f886-115">Windows 8.1</span></span>

- <span data-ttu-id="8f886-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="8f886-116">Windows Server 2012</span></span>

- <span data-ttu-id="8f886-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="8f886-117">Windows Server 2012 R2</span></span>

- <span data-ttu-id="8f886-118">Windows 7、32位版本</span><span class="sxs-lookup"><span data-stu-id="8f886-118">Windows 7, 32-bit edition</span></span>

- <span data-ttu-id="8f886-119">使用 Windows on Win32 的 windows 7、64位版本 (WOW) </span><span class="sxs-lookup"><span data-stu-id="8f886-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

- <span data-ttu-id="8f886-120">Windows Server 2008 R2，使用 WOW</span><span class="sxs-lookup"><span data-stu-id="8f886-120">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="8f886-121">此外，規劃工具需要 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="8f886-121">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="8f886-122">符合預先安裝需求之後，即可安裝規劃工具。</span><span class="sxs-lookup"><span data-stu-id="8f886-122">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>



## <a name="to-install-the-planning-tool"></a><span data-ttu-id="8f886-123">安裝規劃工具</span><span class="sxs-lookup"><span data-stu-id="8f886-123">To install the Planning Tool</span></span>

1. <span data-ttu-id="8f886-124">以 Administrators 群組成員的身分登入本機電腦。</span><span class="sxs-lookup"><span data-stu-id="8f886-124">Log on to the local computer as a member of the Administrators group.</span></span>

2. <span data-ttu-id="8f886-125">使用 Windows Explorer 或命令視窗，找到您下載規劃工具安裝檔的目錄。</span><span class="sxs-lookup"><span data-stu-id="8f886-125">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3. <span data-ttu-id="8f886-126">找出 SkypeForBusinessPlanningTool.msi。</span><span class="sxs-lookup"><span data-stu-id="8f886-126">Locate the SkypeForBusinessPlanningTool.msi.</span></span> <span data-ttu-id="8f886-127">在 [Windows Explorer] 中，按兩下檔案。</span><span class="sxs-lookup"><span data-stu-id="8f886-127">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="8f886-128">在命令視窗中，輸入檔案名，然後按 **enter** 執行該檔案。</span><span class="sxs-lookup"><span data-stu-id="8f886-128">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4. <span data-ttu-id="8f886-129">在 [商務用 Skype 伺服器 2015] 的 [歡迎] 頁面上，按一下 [ **規劃工具安裝精靈]** 的 [ **下一步**]。</span><span class="sxs-lookup"><span data-stu-id="8f886-129">On the Welcome page of the **Skype for Business Server 2015, Planning Tool Setup Wizard**, click **Next**.</span></span>

5. <span data-ttu-id="8f886-130">檢查 **End-User 授權合約**，如果您選擇接受授權合約中的使用條款，請選取 [ **我接受授權合約中的條款** ]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8f886-130">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6. <span data-ttu-id="8f886-131">選擇安裝規劃工具檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="8f886-131">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="8f886-132">預設位置是 \Skype (x86) for Business Server 2015 \ 規劃工具的 C:\Program 檔案。</span><span class="sxs-lookup"><span data-stu-id="8f886-132">The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool.</span></span> <span data-ttu-id="8f886-133">若要變更安裝位置，請按一下 [ **變更**]。</span><span class="sxs-lookup"><span data-stu-id="8f886-133">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="8f886-134">在 [ **變更目的地資料夾**] 中，流覽或輸入要安裝盤案的位置，按一下 **[確定]**，然後按 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="8f886-134">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7. <span data-ttu-id="8f886-135">安裝程式現在已準備好安裝規劃工具。</span><span class="sxs-lookup"><span data-stu-id="8f886-135">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="8f886-136">按一下 [ **安裝** ] 以開始安裝程式。</span><span class="sxs-lookup"><span data-stu-id="8f886-136">Click **Install** to begin the installation process.</span></span>

8. <span data-ttu-id="8f886-137">安裝會開始，並會顯示進度。</span><span class="sxs-lookup"><span data-stu-id="8f886-137">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="8f886-138">安裝順利完成後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="8f886-138">After the installation is successfully completed, click **Finish**.</span></span>

9. <span data-ttu-id="8f886-139">規劃工具可供使用。</span><span class="sxs-lookup"><span data-stu-id="8f886-139">The Planning Tool is ready for use.</span></span>

## <a name="optional-software"></a><span data-ttu-id="8f886-140">選用軟體</span><span class="sxs-lookup"><span data-stu-id="8f886-140">Optional Software</span></span>
<span data-ttu-id="8f886-141"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="8f886-141"><a name="Optional_Software"> </a></span></span>

<span data-ttu-id="8f886-142">商務用 Skype Server 2015 規劃工具是設計用來匯出至 Microsoft Excel 和 Microsoft Visio。</span><span class="sxs-lookup"><span data-stu-id="8f886-142">The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="8f886-143">雖然不需要在規劃工具作業時執行這些應用程式，但是會為部署和設計的檔增加重要的價值。</span><span class="sxs-lookup"><span data-stu-id="8f886-143">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

### <a name="microsoft-excel"></a><span data-ttu-id="8f886-144">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="8f886-144">Microsoft Excel</span></span>

<span data-ttu-id="8f886-145">將設計匯出至 Microsoft Excel 會建立一個報告，該報告會顯示試算表中的七個索引標籤：</span><span class="sxs-lookup"><span data-stu-id="8f886-145">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

- <span data-ttu-id="8f886-146">摘要-顯示網站設定的資訊，包括使用者計數、容量設定和伺服器設定檔資訊。</span><span class="sxs-lookup"><span data-stu-id="8f886-146">Summary - Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

- <span data-ttu-id="8f886-147">硬體設定檔-針對拓撲中指定的伺服器（包括 CPU、記憶體、磁片及網路介面），顯示建議硬體設定的報告。</span><span class="sxs-lookup"><span data-stu-id="8f886-147">Hardware Profile - Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="8f886-148">此外，也包含伺服器元件的數量和建議規格。</span><span class="sxs-lookup"><span data-stu-id="8f886-148">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="8f886-149">此外，每個伺服器都是由網站定義，以透過網站提供伺服器需求的完整標記法。</span><span class="sxs-lookup"><span data-stu-id="8f886-149">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

- <span data-ttu-id="8f886-150">埠需求-顯示所有已啟用的埠報告，以及與網域名稱系統負載平衡關聯的 (DNS LB) 和硬體負載平衡器 (HLB) 。</span><span class="sxs-lookup"><span data-stu-id="8f886-150">Ports Requirements - Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="8f886-151">您應該使用此報告規劃您的防火牆和 DNS LB 和 HLB 設定。</span><span class="sxs-lookup"><span data-stu-id="8f886-151">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

- <span data-ttu-id="8f886-152">摘要報告-顯示設定 Edge Server 網路所需之設定的一般摘要。</span><span class="sxs-lookup"><span data-stu-id="8f886-152">Summary Report - Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

- <span data-ttu-id="8f886-153">憑證報告-顯示取得執行 Edge Server 所需之憑證所需的主體名稱和主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="8f886-153">Certificates Report - Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

- <span data-ttu-id="8f886-154">防火牆報告-顯示外部及內部介面的來源和目的地埠及 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8f886-154">Firewall Report - Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

- <span data-ttu-id="8f886-155">DNS 報告-顯示您所建立之每個 DNS 專案所需的完整功能變數名稱 (FQDN) 和 IP/VIP 位址。</span><span class="sxs-lookup"><span data-stu-id="8f886-155">DNS Report - Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

### <a name="microsoft-visio"></a><span data-ttu-id="8f886-156">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="8f886-156">Microsoft Visio</span></span>

<span data-ttu-id="8f886-157">將您的設計匯出至 Microsoft Visio，會建立圖表，以供您設定的拓撲和基礎結構的檔目的使用。</span><span class="sxs-lookup"><span data-stu-id="8f886-157">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure.</span></span> <span data-ttu-id="8f886-158">您可以編輯並重新排列已匯入的圖表，以符合您的檔需求。</span><span class="sxs-lookup"><span data-stu-id="8f886-158">The imported diagram can be edited and rearranged to meet your documentation needs.</span></span> <span data-ttu-id="8f886-159">典型的 Visio 圖表會包含：</span><span class="sxs-lookup"><span data-stu-id="8f886-159">The typical Visio diagram will include:</span></span>

> [!NOTE]
> <span data-ttu-id="8f886-160">如果您的設計足夠大，需要超過三部前端伺服器，則會為前端集區、前端伺服器、執行 SQL Server 的電腦、IP 位址和 Fqdn 建立額外的頁面。</span><span class="sxs-lookup"><span data-stu-id="8f886-160">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>

- <span data-ttu-id="8f886-161">已設定之商務用 Skype Server 2015 網站的全域拓撲圖表。</span><span class="sxs-lookup"><span data-stu-id="8f886-161">Global Topology - Diagram of configured Skype for Business Server 2015 sites.</span></span>

- <span data-ttu-id="8f886-162">[網站名稱] 索引標籤-顯示具有 Edge Server 的網站設定拓撲，防火牆，公用交換電話網路 (PSTN) 與閘道和內部伺服器部署。</span><span class="sxs-lookup"><span data-stu-id="8f886-162">Site Name tab - Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="8f886-163">內部部署包含已設定的伺服器及集區，包括前端集區、SQL Server 型伺服器、Active Directory 網域服務、Director、Exchange 整合通訊 (UM) 伺服器、Exchange 信箱伺服器、Office Web Apps Server、轉送伺服器及 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="8f886-163">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

- <span data-ttu-id="8f886-164">Edge Network 圖表-詳述具有關聯之 IP 位址和 Fqdn 之 Edge Server 設定的圖表。</span><span class="sxs-lookup"><span data-stu-id="8f886-164">Edge Network Diagram - Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="8f886-165">此外，也包含 DNS 負載平衡與硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="8f886-165">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="8f886-166">此外，會顯示 Director 和前端伺服器或前端集區，並有相關聯的 DNS LB 或 HLB，以及已指派的 IP 位址 (規劃工具可同時支援 IPv4 和 IPv6 位址) 和 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8f886-166">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f886-167">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8f886-167">See also</span></span>
<span data-ttu-id="8f886-168"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="8f886-168"><a name="Optional_Software"> </a></span></span>

[<span data-ttu-id="8f886-169">安裝規劃工具</span><span class="sxs-lookup"><span data-stu-id="8f886-169">Installing the Planning Tool</span></span>](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)

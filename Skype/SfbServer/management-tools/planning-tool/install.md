---
title: 在 Lync Server 2013 中安裝選用軟體
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 在您開始使用商務用 Skype Server 2015 規劃工具設計及規劃商務用 Skype Server 2015 基礎結構之前，您必須先安裝規劃工具。 規劃工具不需要部署到您打算安裝商務用 Skype Server 2015 的網域或基礎結構中的工作站或伺服器。 規劃工具隨附的 Readme 檔案會詳細說明有關安裝及使用工具的重要資訊。 讀我檔案中的部分資訊會在此重複，以清楚起見。
ms.openlocfilehash: 29cadae219faadb68a8a027de11309efc8e3f10b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816382"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a><span data-ttu-id="07a2c-106">在 Lync Server 2013 中安裝選用軟體</span><span class="sxs-lookup"><span data-stu-id="07a2c-106">Install the Planning Tool in Skype for Business Server 2015</span></span>

<span data-ttu-id="07a2c-107">在您開始使用商務用 Skype Server 2015 規劃工具設計及規劃商務用 Skype Server 2015 基礎結構之前，您必須先安裝規劃工具。</span><span class="sxs-lookup"><span data-stu-id="07a2c-107">Before you begin designing and planning your Skype for Business Server 2015 infrastructure by using the Skype for Business Server 2015 Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="07a2c-108">規劃工具不需要部署到您打算安裝商務用 Skype Server 2015 的網域或基礎結構中的工作站或伺服器。</span><span class="sxs-lookup"><span data-stu-id="07a2c-108">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Skype for Business Server 2015.</span></span> <span data-ttu-id="07a2c-109">規劃工具隨附的 Readme 檔案會詳細說明有關安裝及使用工具的重要資訊。</span><span class="sxs-lookup"><span data-stu-id="07a2c-109">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="07a2c-110">讀我檔案中的部分資訊會在此重複，以清楚起見。</span><span class="sxs-lookup"><span data-stu-id="07a2c-110">Some of the information in the Readme file is duplicated here for clarity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="07a2c-111">規劃工具必須由使用者在安裝該工具的電腦上擁有系統管理員權利和許可權，才能安裝。</span><span class="sxs-lookup"><span data-stu-id="07a2c-111">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>

<span data-ttu-id="07a2c-112">規劃工具所支援的安裝及作業作業系統包括：</span><span class="sxs-lookup"><span data-stu-id="07a2c-112">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

- <span data-ttu-id="07a2c-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="07a2c-113">Windows 10</span></span>

- <span data-ttu-id="07a2c-114">Windows 8</span><span class="sxs-lookup"><span data-stu-id="07a2c-114">Windows 8</span></span>

- <span data-ttu-id="07a2c-115">Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="07a2c-115">Windows 8.1</span></span>

- <span data-ttu-id="07a2c-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="07a2c-116">Windows Server 2012</span></span>

- <span data-ttu-id="07a2c-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="07a2c-117">Windows Server 2012 R2</span></span>

- <span data-ttu-id="07a2c-118">Windows 7、32位版本</span><span class="sxs-lookup"><span data-stu-id="07a2c-118">Windows 7, 32-bit edition</span></span>

- <span data-ttu-id="07a2c-119">Windows 7，64在 Win32 上使用 Windows （WOW）</span><span class="sxs-lookup"><span data-stu-id="07a2c-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

- <span data-ttu-id="07a2c-120">Windows Server 2008 R2，使用 WOW</span><span class="sxs-lookup"><span data-stu-id="07a2c-120">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="07a2c-121">此外，規劃工具需要 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="07a2c-121">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="07a2c-122">在符合預先安裝需求之後，您就可以安裝規劃工具。</span><span class="sxs-lookup"><span data-stu-id="07a2c-122">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>



## <a name="to-install-the-planning-tool"></a><span data-ttu-id="07a2c-123">若要安裝規劃工具</span><span class="sxs-lookup"><span data-stu-id="07a2c-123">To install the Planning Tool</span></span>

1. <span data-ttu-id="07a2c-124">以管理員群組的成員身分登入本機電腦。</span><span class="sxs-lookup"><span data-stu-id="07a2c-124">Log on to the local computer as a member of the Administrators group.</span></span>

2. <span data-ttu-id="07a2c-125">使用 Windows 資源管理器或命令視窗，找出您下載規劃工具安裝檔的目錄。</span><span class="sxs-lookup"><span data-stu-id="07a2c-125">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3. <span data-ttu-id="07a2c-126">找出 SkypeForBusinessPlanningTool。</span><span class="sxs-lookup"><span data-stu-id="07a2c-126">Locate the SkypeForBusinessPlanningTool.msi.</span></span> <span data-ttu-id="07a2c-127">在 Windows 資源管理器中，按兩下檔案。</span><span class="sxs-lookup"><span data-stu-id="07a2c-127">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="07a2c-128">在命令視窗中，輸入檔案名，然後按**enter**執行檔案。</span><span class="sxs-lookup"><span data-stu-id="07a2c-128">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4. <span data-ttu-id="07a2c-129">在商務用 Skype Server 2015 的 [歡迎] 頁面上，按一下 [**規劃工具設定向導]**，然後按 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="07a2c-129">On the Welcome page of the **Skype for Business Server 2015, Planning Tool Setup Wizard**, click **Next**.</span></span>

5. <span data-ttu-id="07a2c-130">查看 [**使用者授權合約**]，如果您選擇接受授權協定中的使用條款，請選取 [**我接受授權合約中的條款**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="07a2c-130">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6. <span data-ttu-id="07a2c-131">選擇安裝規劃工具檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="07a2c-131">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="07a2c-132">預設位置是商務用 Server 2015 \ 規劃工具的 C:\Program Files （x86） \Skype。</span><span class="sxs-lookup"><span data-stu-id="07a2c-132">The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool.</span></span> <span data-ttu-id="07a2c-133">如果您想要變更安裝位置，請按一下 [**變更**]。</span><span class="sxs-lookup"><span data-stu-id="07a2c-133">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="07a2c-134">在 [**變更目的地] 資料夾**中，流覽或輸入安裝盤案的位置，按一下 **[確定]**，然後按一下 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="07a2c-134">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7. <span data-ttu-id="07a2c-135">安裝程式現已準備好安裝規劃工具。</span><span class="sxs-lookup"><span data-stu-id="07a2c-135">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="07a2c-136">按一下 [**安裝**] 以開始安裝程式。</span><span class="sxs-lookup"><span data-stu-id="07a2c-136">Click **Install** to begin the installation process.</span></span>

8. <span data-ttu-id="07a2c-137">隨即會啟動安裝，並顯示進度。</span><span class="sxs-lookup"><span data-stu-id="07a2c-137">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="07a2c-138">成功完成安裝後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="07a2c-138">After the installation is successfully completed, click **Finish**.</span></span>

9. <span data-ttu-id="07a2c-139">規劃工具已就緒，可供使用。</span><span class="sxs-lookup"><span data-stu-id="07a2c-139">The Planning Tool is ready for use.</span></span>

## <a name="optional-software"></a><span data-ttu-id="07a2c-140">選用軟體</span><span class="sxs-lookup"><span data-stu-id="07a2c-140">Optional Software</span></span>
<span data-ttu-id="07a2c-141"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="07a2c-141"><a name="Optional_Software"> </a></span></span>

<span data-ttu-id="07a2c-142">商務用 Skype Server 2015 規劃工具的設計目的是匯出至 Microsoft Excel 和 Microsoft Visio。</span><span class="sxs-lookup"><span data-stu-id="07a2c-142">The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="07a2c-143">雖然這些應用程式不是規劃工具運作所必需的，但它們確實會為您設計的部署和檔加上重要的價值。</span><span class="sxs-lookup"><span data-stu-id="07a2c-143">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

### <a name="microsoft-excel"></a><span data-ttu-id="07a2c-144">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="07a2c-144">Microsoft Excel</span></span>

<span data-ttu-id="07a2c-145">將您的設計匯出至 Microsoft Excel 時，會建立一個顯示試算表中七個索引標籤的報表：</span><span class="sxs-lookup"><span data-stu-id="07a2c-145">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

- <span data-ttu-id="07a2c-146">摘要-顯示網站設定的相關資訊，包括使用者計數、容量設定和伺服器設定檔資訊。</span><span class="sxs-lookup"><span data-stu-id="07a2c-146">Summary - Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

- <span data-ttu-id="07a2c-147">硬體設定檔-顯示在拓撲中指定的伺服器硬體設定（包括 CPU、記憶體、磁片和網路介面）的報告。</span><span class="sxs-lookup"><span data-stu-id="07a2c-147">Hardware Profile - Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="07a2c-148">也包含伺服器元件的數量及建議的規格。</span><span class="sxs-lookup"><span data-stu-id="07a2c-148">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="07a2c-149">此外，每個伺服器都是由網站定義，以根據網站提供伺服器需求的完整表示。</span><span class="sxs-lookup"><span data-stu-id="07a2c-149">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

- <span data-ttu-id="07a2c-150">埠需求-顯示所有已啟用埠的報告，以及與網域名稱系統負載平衡（DNS LB）與硬體負載平衡器（HLB）的關聯。</span><span class="sxs-lookup"><span data-stu-id="07a2c-150">Ports Requirements - Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="07a2c-151">您應該使用這個報告來規劃您的防火牆和 DNS LB 及 HLB 設定。</span><span class="sxs-lookup"><span data-stu-id="07a2c-151">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

- <span data-ttu-id="07a2c-152">摘要報告-顯示設定 Edge 伺服器網路所需設定的一般摘要。</span><span class="sxs-lookup"><span data-stu-id="07a2c-152">Summary Report - Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

- <span data-ttu-id="07a2c-153">[憑證] 報告-顯示在執行邊緣伺服器所需的憑證所需的消費者名稱和消費者替代名稱。</span><span class="sxs-lookup"><span data-stu-id="07a2c-153">Certificates Report - Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

- <span data-ttu-id="07a2c-154">Firewall 報告-顯示外部和內部介面的來源和目的地埠和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="07a2c-154">Firewall Report - Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

- <span data-ttu-id="07a2c-155">DNS 報告-顯示您所建立之每個 DNS 專案所需的完整功能變數名稱（FQDN）和 IP/VIP 位址。</span><span class="sxs-lookup"><span data-stu-id="07a2c-155">DNS Report - Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

### <a name="microsoft-visio"></a><span data-ttu-id="07a2c-156">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="07a2c-156">Microsoft Visio</span></span>

<span data-ttu-id="07a2c-157">將您的設計匯出至 Microsoft Visio，就會建立圖表，以供您設定的拓撲和基礎結構的檔用途使用。</span><span class="sxs-lookup"><span data-stu-id="07a2c-157">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure.</span></span> <span data-ttu-id="07a2c-158">您可以編輯和重新排列已匯入的圖表，以符合您的檔需求。</span><span class="sxs-lookup"><span data-stu-id="07a2c-158">The imported diagram can be edited and rearranged to meet your documentation needs.</span></span> <span data-ttu-id="07a2c-159">典型的 Visio 圖表會包括：</span><span class="sxs-lookup"><span data-stu-id="07a2c-159">The typical Visio diagram will include:</span></span>

> [!NOTE]
> <span data-ttu-id="07a2c-160">如果您的設計足夠大，需要超過三個前端伺服器，則會針對前端池、前端伺服器、執行 SQL Server 的電腦、IP 位址及 Fqdn，建立額外的頁面。</span><span class="sxs-lookup"><span data-stu-id="07a2c-160">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>

- <span data-ttu-id="07a2c-161">[全域拓撲]-已設定商務用 Skype Server 2015 網站的圖表。</span><span class="sxs-lookup"><span data-stu-id="07a2c-161">Global Topology - Diagram of configured Skype for Business Server 2015 sites.</span></span>

- <span data-ttu-id="07a2c-162">[網站名稱] 索引標籤-顯示含 Edge 伺服器、防火牆、公開交換電話網絡（PSTN）與內部伺服器部署的網站配置拓撲。</span><span class="sxs-lookup"><span data-stu-id="07a2c-162">Site Name tab - Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="07a2c-163">內部部署由已設定的伺服器和池組成，包括前端池、SQL Server 服務器、Active Directory 網域服務、控制器、Exchange 整合通訊（UM）伺服器、Exchange 信箱伺服器、Office Web Apps 伺服器、中繼伺服器和持續聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="07a2c-163">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

- <span data-ttu-id="07a2c-164">Edge 網狀圖-詳細說明邊緣伺服器設定與相關聯的 IP 位址和 Fqdn 的圖表。</span><span class="sxs-lookup"><span data-stu-id="07a2c-164">Edge Network Diagram - Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="07a2c-165">也包含 DNS 負載平衡與硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="07a2c-165">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="07a2c-166">此外，會顯示 [控制器] 與 [前端伺服器] 或 [頂層端] 池，其中包含相關聯的 DNS LB 或 HLB 以及指派的 IP 位址（規劃工具支援 IPv4 與 IPv6 位址）和 FQDN。</span><span class="sxs-lookup"><span data-stu-id="07a2c-166">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

## <a name="see-also"></a><span data-ttu-id="07a2c-167">另請參閱</span><span class="sxs-lookup"><span data-stu-id="07a2c-167">See also</span></span>
<span data-ttu-id="07a2c-168"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="07a2c-168"><a name="Optional_Software"> </a></span></span>

[<span data-ttu-id="07a2c-169">安裝規劃工具</span><span class="sxs-lookup"><span data-stu-id="07a2c-169">Installing the Planning Tool</span></span>](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)

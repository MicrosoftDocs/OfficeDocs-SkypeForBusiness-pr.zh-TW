---
title: Lync Server 2013 資源套件工具檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1589285948bd9d3f82fae0ed7c7916029716514f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-resource-kit-tools-documentation"></a><span data-ttu-id="0fc61-102">Lync Server 2013 資源套件工具檔</span><span class="sxs-lookup"><span data-stu-id="0fc61-102">Lync Server 2013 Resource Kit Tools Documentation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0fc61-103">_**主題上次修改日期：** 2014-01-09_</span><span class="sxs-lookup"><span data-stu-id="0fc61-103">_**Topic Last Modified:** 2014-01-09_</span></span>

<span data-ttu-id="0fc61-104">本主題描述屬於 Lync Server 2013 資源套件的工具，包括每個工具的用途，以及其用法範例。Lync Server 2013、資源套件工具可協助您更輕鬆地部署和管理 Lync Server 2013 的 IT 系統管理員進行例行工作。</span><span class="sxs-lookup"><span data-stu-id="0fc61-104">This topic describes the tools that are part of the Lync Server 2013 Resource Kit, including the purpose of each tool, and examples of its use.The Lync Server 2013, Resource Kit Tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="0fc61-105">例如，網路會議**資料**工具可用於輕鬆控制使用者在線上會議期間上傳的資料。</span><span class="sxs-lookup"><span data-stu-id="0fc61-105">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="0fc61-106">**SEFAUtil**工具可用來設定代理人來電轉接及應答使用者。</span><span class="sxs-lookup"><span data-stu-id="0fc61-106">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="0fc61-107">我們鼓勵 IT 系統管理員使用這些工具來更有效率地管理 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="0fc61-107">We encourage IT administrators to use these tools to more effectively manage Lync Server 2013.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="0fc61-108">資源套件工具的安裝</span><span class="sxs-lookup"><span data-stu-id="0fc61-108">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="0fc61-109">若要安裝 Lync Server 2013、資源套件工具，請下載**OCSReskit**。</span><span class="sxs-lookup"><span data-stu-id="0fc61-109">To install the Lync Server 2013, Resource Kit Tools, download **OCSReskit.msi**.</span></span> <span data-ttu-id="0fc61-110">您可以從下載中心下載 [資源套件工具] 安裝程式[http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429)。</span><span class="sxs-lookup"><span data-stu-id="0fc61-110">You can download the Resource Kit Tools installer from the Download Center at [http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429).</span></span>

<span data-ttu-id="0fc61-111">執行**OCSResKit**以進行簡單的安裝。</span><span class="sxs-lookup"><span data-stu-id="0fc61-111">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="0fc61-112">.Msi 會安裝下列路徑中的所有工具： **% Program Files%\\Microsoft Lync Server 2013\\ResKit**。</span><span class="sxs-lookup"><span data-stu-id="0fc61-112">The .msi installs all the tools in the following path: **%Program Files%\\Microsoft Lync Server 2013\\ResKit**.</span></span> <span data-ttu-id="0fc61-113">可自包含的可執行檔的工具位於此資料夾中。</span><span class="sxs-lookup"><span data-stu-id="0fc61-113">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="0fc61-114">也有檔案的工具位於自己的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="0fc61-114">Tools that also have files are in their own subfolders.</span></span>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="0fc61-115">支援的環境</span><span class="sxs-lookup"><span data-stu-id="0fc61-115">Supported Environments</span></span>

<span data-ttu-id="0fc61-116">為了獲得最佳效能，Lync Server 2013、資源套件工具應該安裝在相同的環境中，且與 Lync Server 2013 所需的規格相同。</span><span class="sxs-lookup"><span data-stu-id="0fc61-116">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="0fc61-117">資源套件工具概述</span><span class="sxs-lookup"><span data-stu-id="0fc61-117">Resource Kit Tools Overview</span></span>

<span data-ttu-id="0fc61-118">下列清單說明 Lync Server 2013 資源套件中提供的工具。</span><span class="sxs-lookup"><span data-stu-id="0fc61-118">The following list describes the tools that are provided in the Lync Server 2013 Resource Kit.</span></span> <span data-ttu-id="0fc61-119">每個工具的描述，包括 [需求] 和 [範例] 用法在下一節中講述。</span><span class="sxs-lookup"><span data-stu-id="0fc61-119">A description of each tool, including the requirements and example usage is covered in the following section.</span></span>

  - <span data-ttu-id="0fc61-120">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="0fc61-120">ABSConfig</span></span>

  - <span data-ttu-id="0fc61-121">頻寬原則服務監視器</span><span class="sxs-lookup"><span data-stu-id="0fc61-121">Bandwidth Policy Service Monitor</span></span>

  - <span data-ttu-id="0fc61-122">頻寬利用率分析程式</span><span class="sxs-lookup"><span data-stu-id="0fc61-122">Bandwidth Utilization Analyzer</span></span>

  - <span data-ttu-id="0fc61-123">呼叫 Parkometer</span><span class="sxs-lookup"><span data-stu-id="0fc61-123">Call Parkometer</span></span>

  - <span data-ttu-id="0fc61-124">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="0fc61-124">CleanupStorageServiceData</span></span>

  - <span data-ttu-id="0fc61-125">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="0fc61-125">DBAnalyze</span></span>

  - <span data-ttu-id="0fc61-126">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="0fc61-126">ImportStorageServiceData</span></span>

  - <span data-ttu-id="0fc61-127">LCSSync</span><span class="sxs-lookup"><span data-stu-id="0fc61-127">LCSSync</span></span>

  - <span data-ttu-id="0fc61-128">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="0fc61-128">LookupUserConsole</span></span>

  - <span data-ttu-id="0fc61-129">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="0fc61-129">MsTurnPing</span></span>

  - <span data-ttu-id="0fc61-130">網路設定檢視器</span><span class="sxs-lookup"><span data-stu-id="0fc61-130">Network Configuration Viewer</span></span>

  - <span data-ttu-id="0fc61-131">回應群組代理程式即時</span><span class="sxs-lookup"><span data-stu-id="0fc61-131">Response Group Agent Live</span></span>

  - <span data-ttu-id="0fc61-132">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="0fc61-132">SEFAUtil</span></span>

  - <span data-ttu-id="0fc61-133">SYSPrep. ps1</span><span class="sxs-lookup"><span data-stu-id="0fc61-133">SYSPrep.ps1</span></span>

  - <span data-ttu-id="0fc61-134">未指定的數位宣告遷移</span><span class="sxs-lookup"><span data-stu-id="0fc61-134">Unassigned Number Announcements Migration</span></span>

  - <span data-ttu-id="0fc61-135">網路會議資料</span><span class="sxs-lookup"><span data-stu-id="0fc61-135">Web Conf Data</span></span>

</div>

<div>

## <a name="absconfig"></a><span data-ttu-id="0fc61-136">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="0fc61-136">ABSConfig</span></span>

<span data-ttu-id="0fc61-137">通訊錄服務設定工具（ABSConfig）是一種管理工具，可協助系統管理員在 Lync Server 2013 中自訂通訊錄服務設定。</span><span class="sxs-lookup"><span data-stu-id="0fc61-137">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Lync Server 2013.</span></span> <span data-ttu-id="0fc61-138">此工具也可讓 Lync Server 2013 系統管理員還原預設通訊錄服務設定。</span><span class="sxs-lookup"><span data-stu-id="0fc61-138">This tool also enables Lync Server 2013 administrators to restore the default Address Book Service settings.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="0fc61-139">描述</span><span class="sxs-lookup"><span data-stu-id="0fc61-139">Description</span></span>

<span data-ttu-id="0fc61-140">ABSConfig 是圖形使用者介面應用程式，可讓系統管理員設定與通訊錄服務相關的 Active Directory 網域服務屬性。</span><span class="sxs-lookup"><span data-stu-id="0fc61-140">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="0fc61-141">此工具的主要案例如下所示：</span><span class="sxs-lookup"><span data-stu-id="0fc61-141">The primary scenarios for the tool are the following:</span></span>

  - <span data-ttu-id="0fc61-142">若要讓系統管理員將 Active Directory 網域服務中的屬性對應至 Lync Server 2013 的屬性。</span><span class="sxs-lookup"><span data-stu-id="0fc61-142">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Lync Server 2013.</span></span>

  - <span data-ttu-id="0fc61-143">若要讓系統管理員指定要在通訊錄服務檔案中包含或排除的 Active Directory 網域服務屬性。</span><span class="sxs-lookup"><span data-stu-id="0fc61-143">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

  - <span data-ttu-id="0fc61-144">讓系統管理員還原預設通訊錄服務設定。</span><span class="sxs-lookup"><span data-stu-id="0fc61-144">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="0fc61-145">ABSConfig 工具可以使用 absConfig 檔案啟動。</span><span class="sxs-lookup"><span data-stu-id="0fc61-145">The ABSConfig tool can be started by using the absConfig.exe file.</span></span> <span data-ttu-id="0fc61-146">工具隨即開啟至 [**設定屬性**] 索引標籤。此表格有選項可將 Active Directory 網域服務屬性對應至 Lync Server 2013 的屬性欄位，並指定哪些使用者要在通訊錄服務檔案中根據特定的屬性篩選器來包含或排除這些屬性。</span><span class="sxs-lookup"><span data-stu-id="0fc61-146">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Lync Server 2013 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="0fc61-147">您也可以選擇自訂要在通訊錄檔案中包含的電話號碼值。</span><span class="sxs-lookup"><span data-stu-id="0fc61-147">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="0fc61-148">[**還原預設**值] 選項可讓系統管理員將通訊錄服務設定還原為預設值。</span><span class="sxs-lookup"><span data-stu-id="0fc61-148">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

</div>

<div>

## <a name="changes-from-lync-server-2010"></a><span data-ttu-id="0fc61-149">從 Lync Server 2010 所做的變更</span><span class="sxs-lookup"><span data-stu-id="0fc61-149">Changes from Lync Server 2010</span></span>

<span data-ttu-id="0fc61-150">在 Lync Server 2013 ABS 組態工具中，取消核取屬性的 [啟用] 核取方塊，即可移除屬性（列）。</span><span class="sxs-lookup"><span data-stu-id="0fc61-150">In Lync Server 2013 ABS Configuration tool, attributes (rows) may be removed by unchecking the “enable” checkbox for the attribute.</span></span> <span data-ttu-id="0fc61-151">這與刪除 Lync Server 2010 中的資料列效果一樣。</span><span class="sxs-lookup"><span data-stu-id="0fc61-151">This has the same effect as deleting the row in Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0fc61-152">[啟用] 核取方塊位於最右側的欄中;您可能需要向右滾動才能查看資料行</span><span class="sxs-lookup"><span data-stu-id="0fc61-152">The enable checkbox is in the far right column; you may need to scroll right to see the column</span></span>



</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="0fc61-153">收</span><span class="sxs-lookup"><span data-stu-id="0fc61-153">Output</span></span>

<span data-ttu-id="0fc61-154">ABSConfig 會將通訊錄服務配置儲存在資料庫中。</span><span class="sxs-lookup"><span data-stu-id="0fc61-154">ABSConfig stores the Address Book Service configuration in the database.</span></span>

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="0fc61-155">特殊</span><span class="sxs-lookup"><span data-stu-id="0fc61-155">Purpose</span></span>

<span data-ttu-id="0fc61-156">ABSConfig 提供快速且輕鬆地自訂 Lync Server 2013 通訊錄服務的方式。</span><span class="sxs-lookup"><span data-stu-id="0fc61-156">ABSConfig provides a quick and easy way to customize Lync Server 2013 Address Book Service.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="0fc61-157">需求</span><span class="sxs-lookup"><span data-stu-id="0fc61-157">Requirements</span></span>

<div>

## <a name="computer"></a><span data-ttu-id="0fc61-158">電腦</span><span class="sxs-lookup"><span data-stu-id="0fc61-158">Computer</span></span>

<span data-ttu-id="0fc61-159">ABSConfig 只能從已安裝 Lync Server 2013 的已加入網域的電腦執行。</span><span class="sxs-lookup"><span data-stu-id="0fc61-159">ABSConfig can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span> <span data-ttu-id="0fc61-160">在 Lync Server 2013 （企業版）的情況下，此工具可以在安裝期間啟用通訊錄服務的任何前端伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="0fc61-160">In the case of Lync Server 2013, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

</div>

<div>

## <a name="network"></a><span data-ttu-id="0fc61-161">網路</span><span class="sxs-lookup"><span data-stu-id="0fc61-161">Network</span></span>

<span data-ttu-id="0fc61-162">電腦應該能夠連線到前端池和後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="0fc61-162">The computer should be able to connect to the Front End pool and back-end database.</span></span>

</div>

<div>

## <a name="software"></a><span data-ttu-id="0fc61-163">軟體</span><span class="sxs-lookup"><span data-stu-id="0fc61-163">Software</span></span>

<span data-ttu-id="0fc61-164">在執行 ABSConfig 工具之前，必須先安裝下列軟體元件：</span><span class="sxs-lookup"><span data-stu-id="0fc61-164">The following software components must be installed before running the ABSConfig tool:</span></span>

  - <span data-ttu-id="0fc61-165">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fc61-165">Microsoft Lync Server 2013</span></span>

</div>

<div>

## <a name="users"></a><span data-ttu-id="0fc61-166">使用者</span><span class="sxs-lookup"><span data-stu-id="0fc61-166">Users</span></span>

<span data-ttu-id="0fc61-167">擁有更新 Lync Server 2013 部署所需許可權的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="0fc61-167">Administrators who have the permissions required to update the Lync Server 2013 deployment.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="0fc61-168">範例</span><span class="sxs-lookup"><span data-stu-id="0fc61-168">Examples</span></span>

<span data-ttu-id="0fc61-169">在命令提示字元中輸入**ABSConfig** ，即可開始 ABSConfig。</span><span class="sxs-lookup"><span data-stu-id="0fc61-169">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="0fc61-170">下面顯示的是 ABSConfig 工具使用者介面。</span><span class="sxs-lookup"><span data-stu-id="0fc61-170">Shown below is the ABSConfig tool user interface.</span></span>

<span data-ttu-id="0fc61-171">![ABSConfig 工具。](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "ABSConfig 工具。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-171">![The ABSConfig.exe tool.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "The ABSConfig.exe tool.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="0fc61-172">總結</span><span class="sxs-lookup"><span data-stu-id="0fc61-172">Summary</span></span>

<span data-ttu-id="0fc61-173">ABSConfig 工具可讓系統管理員快速且輕鬆地使用工具來自訂 Lync Server 2013 通訊錄服務。</span><span class="sxs-lookup"><span data-stu-id="0fc61-173">The ABSConfig tool provides administrators a quick and easy to use tool to customize Lync Server 2013 Address Book Service.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="0fc61-174">頻寬原則服務監視器</span><span class="sxs-lookup"><span data-stu-id="0fc61-174">Bandwidth Policy Service Monitor</span></span>

<span data-ttu-id="0fc61-175">[頻寬原則服務監視工具] 可讓系統管理員查看下列專案的清單：</span><span class="sxs-lookup"><span data-stu-id="0fc61-175">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1.  <span data-ttu-id="0fc61-176">拓撲中所有已設定的 Lync Server 2013 頻寬原則服務（驗證與核心）</span><span class="sxs-lookup"><span data-stu-id="0fc61-176">All the configured Lync Server 2013 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2.  <span data-ttu-id="0fc61-177">每個服務對其他頻寬原則服務及邊緣伺服器所做的連接</span><span class="sxs-lookup"><span data-stu-id="0fc61-177">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3.  <span data-ttu-id="0fc61-178">在網路設定檔中設定的所有連結，以及每個頻寬策略服務所報告的即時頻寬使用量</span><span class="sxs-lookup"><span data-stu-id="0fc61-178">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

<div>

## <a name="description"></a><span data-ttu-id="0fc61-179">描述</span><span class="sxs-lookup"><span data-stu-id="0fc61-179">Description</span></span>

<span data-ttu-id="0fc61-180">[頻寬原則服務監視工具] 是以 GUI 式應用程式的方式來實現。</span><span class="sxs-lookup"><span data-stu-id="0fc61-180">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="0fc61-181">系統管理員執行 PDPMonUI 來啟動該工具。</span><span class="sxs-lookup"><span data-stu-id="0fc61-181">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="0fc61-182">當工具啟動時，它會嘗試在拓撲中探索頻寬原則服務清單。</span><span class="sxs-lookup"><span data-stu-id="0fc61-182">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="0fc61-183">初次更新完成之後，視窗左側的窗格會以其所屬的群集來分組，並填入服務清單。</span><span class="sxs-lookup"><span data-stu-id="0fc61-183">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="0fc61-184">當管理員選取特定的頻寬原則服務時，右邊的窗格會顯示該特定服務的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0fc61-184">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="0fc61-185">該窗格還有兩個顯示資訊的主要索引標籤。</span><span class="sxs-lookup"><span data-stu-id="0fc61-185">That pane also has two main tabs that display information.</span></span>

<div>

## <a name="machine-info-tab"></a><span data-ttu-id="0fc61-186">[電腦資訊] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="0fc61-186">Machine Info Tab</span></span>

<span data-ttu-id="0fc61-187">[**電腦資訊**] 索引標籤會顯示已選取頻寬原則服務的詳細資料，以及由選取的頻寬策略服務所進行的所有連線的清單和狀態與其他服務。</span><span class="sxs-lookup"><span data-stu-id="0fc61-187">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

</div>

<div>

## <a name="topology-info-tab"></a><span data-ttu-id="0fc61-188">[拓撲資訊] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="0fc61-188">Topology Info Tab</span></span>

<span data-ttu-id="0fc61-189">[**拓撲資訊**] 索引標籤會顯示在 [網路設定] 中設定的所有連結的清單。</span><span class="sxs-lookup"><span data-stu-id="0fc61-189">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="0fc61-190">針對每個連結，會顯示 [音訊] 和 [影片頻寬] 的容量。</span><span class="sxs-lookup"><span data-stu-id="0fc61-190">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="0fc61-191">此外，目前使用的頻寬會以 Kbps 及容量百分比的方式顯示。</span><span class="sxs-lookup"><span data-stu-id="0fc61-191">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="0fc61-192">此工具使用色彩編碼來醒目提示具有接近產能之利用率的連結，這可讓系統管理員快速隔離這些連結。</span><span class="sxs-lookup"><span data-stu-id="0fc61-192">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0fc61-193">如果頻寬原則服務監視器工具在連線至任何已設定的頻寬原則服務時發生故障，<STRONG>電腦資訊</STRONG>和<STRONG>拓撲資訊</STRONG>索引標籤中的資訊將無法填入。</span><span class="sxs-lookup"><span data-stu-id="0fc61-193">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the <STRONG>Machine Info</STRONG> and the <STRONG>Topology Info</STRONG> tabs won’t be populated.</span></span> <span data-ttu-id="0fc61-194">不過，該工具可能會先連線，但隨後會失去與服務的連線。</span><span class="sxs-lookup"><span data-stu-id="0fc61-194">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="0fc61-195">在這種情況下，系統管理員可能會看到過時的資訊。</span><span class="sxs-lookup"><span data-stu-id="0fc61-195">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="0fc61-196">每個索引標籤上都有<STRONG>上次更新</STRONG>的時間戳記，這些索引標籤可讓系統管理員查看特定頻寬原則服務上次更新資料的時間。</span><span class="sxs-lookup"><span data-stu-id="0fc61-196">There is a <STRONG>Last Updated</STRONG> time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="0fc61-197">收</span><span class="sxs-lookup"><span data-stu-id="0fc61-197">Output</span></span>

<span data-ttu-id="0fc61-198">沒有命令列輸出;程式輸出包含在主要的圖形使用者介面（GUI）中。</span><span class="sxs-lookup"><span data-stu-id="0fc61-198">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="0fc61-199">特殊</span><span class="sxs-lookup"><span data-stu-id="0fc61-199">Purpose</span></span>

<span data-ttu-id="0fc61-200">[頻寬原則服務監視器] 工具的用途是，可讓系統管理員瞭解拓撲中定義的每個頻寬原則服務的狀態。</span><span class="sxs-lookup"><span data-stu-id="0fc61-200">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="0fc61-201">此外，管理員可以查看網路設定檔中定義的所有連結的即時頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="0fc61-201">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="0fc61-202">需求</span><span class="sxs-lookup"><span data-stu-id="0fc61-202">Requirements</span></span>

<span data-ttu-id="0fc61-203">[頻寬原則服務監視器] 工具必須在屬於 Lync Server 拓撲的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="0fc61-203">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Lync Server topology.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="0fc61-204">總結</span><span class="sxs-lookup"><span data-stu-id="0fc61-204">Summary</span></span>

<span data-ttu-id="0fc61-205">頻寬原則服務監視器工具可以是系統管理員的重要資源，讓他們能夠檢查拓撲中所有頻寬原則服務的狀態，更重要的是，它們可以取得連結的即時頻寬利用率，在 [網路設定] 中定義。</span><span class="sxs-lookup"><span data-stu-id="0fc61-205">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="0fc61-206">頻寬利用率分析程式</span><span class="sxs-lookup"><span data-stu-id="0fc61-206">Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="0fc61-207">[頻寬利用率分析] 是一種工具，可在商業網路中，透過廣域網路連結的 UC 端點，建立各種頻寬使用量的報告。</span><span class="sxs-lookup"><span data-stu-id="0fc61-207">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="0fc61-208">這些報告可用來瞭解目前的頻寬使用量模式，並協助您進行頻寬容量規劃。</span><span class="sxs-lookup"><span data-stu-id="0fc61-208">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="0fc61-209">描述</span><span class="sxs-lookup"><span data-stu-id="0fc61-209">Description</span></span>

<span data-ttu-id="0fc61-210">[頻寬利用率分析] 是以 GUI 式應用程式的方式來實現。</span><span class="sxs-lookup"><span data-stu-id="0fc61-210">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="0fc61-211">這個工具會針對網路上的音訊利用率專門產生報告，並協助您進行容量規劃。</span><span class="sxs-lookup"><span data-stu-id="0fc61-211">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="0fc61-212">它也會根據指派給各種連結的頻寬容量來反覆運算。</span><span class="sxs-lookup"><span data-stu-id="0fc61-212">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="0fc61-213">收</span><span class="sxs-lookup"><span data-stu-id="0fc61-213">Output</span></span>

<span data-ttu-id="0fc61-214">[頻寬利用率分析]：針對系統中設定的所有 WAN 連結，提供圖形 al 的頻寬容量與利用率。</span><span class="sxs-lookup"><span data-stu-id="0fc61-214">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="0fc61-215">特殊</span><span class="sxs-lookup"><span data-stu-id="0fc61-215">Purpose</span></span>

<span data-ttu-id="0fc61-216">在任何語音與視頻部署中，監視及瞭解整個商業網路中媒體流量的頻寬利用率趨勢是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="0fc61-216">In any voice and video deployment, it’s critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="0fc61-217">[頻寬利用率分析] 工具可讓系統管理員只取得該功能。</span><span class="sxs-lookup"><span data-stu-id="0fc61-217">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="0fc61-218">此工具會執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="0fc61-218">This tool does the following:</span></span>

  - <span data-ttu-id="0fc61-219">針對網路上的音訊利用率產生特定報告</span><span class="sxs-lookup"><span data-stu-id="0fc61-219">Generates specific reports for audio utilization across the network</span></span>

  - <span data-ttu-id="0fc61-220">協助更有效的容量規劃，以及在指派給各種連結的頻寬容量上進行反覆運算</span><span class="sxs-lookup"><span data-stu-id="0fc61-220">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="0fc61-221">[頻寬利用率分析] 可產生頻寬容量與利用率報告的圖形化圖形;它們如下所示：</span><span class="sxs-lookup"><span data-stu-id="0fc61-221">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

  - <span data-ttu-id="0fc61-222">商業網路中的所有 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="0fc61-222">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="0fc61-223">已選取已選取的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="0fc61-223">Filtered by selected WAN links that have been chosen</span></span>

  - <span data-ttu-id="0fc61-224">使用超過連結容量的 WAN 連結進行篩選</span><span class="sxs-lookup"><span data-stu-id="0fc61-224">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="0fc61-225">依已在使用預配頻寬的 WAN 連結進行篩選</span><span class="sxs-lookup"><span data-stu-id="0fc61-225">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

  - <span data-ttu-id="0fc61-226">依 WAN 連結達到關鍵性層級的 WAN 連結進行篩選（頻寬利用率大於 WAN 連結頻寬容量的90%）</span><span class="sxs-lookup"><span data-stu-id="0fc61-226">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="0fc61-227">依 WAN 連結類型進行篩選：網路網站連結、interregional 連結，以及網站內的連結</span><span class="sxs-lookup"><span data-stu-id="0fc61-227">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

  - <span data-ttu-id="0fc61-228">依網路區域篩選</span><span class="sxs-lookup"><span data-stu-id="0fc61-228">Filtered by network region</span></span>

<div>

## <a name="applications"></a><span data-ttu-id="0fc61-229">程式</span><span class="sxs-lookup"><span data-stu-id="0fc61-229">Applications</span></span>

<span data-ttu-id="0fc61-230">[頻寬利用率] Analyzer 有下列兩個應用程式（工具）：</span><span class="sxs-lookup"><span data-stu-id="0fc61-230">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

  - <span data-ttu-id="0fc61-231">**WanLinkLogCollector**   此工具可讓使用者輸入所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="0fc61-231">**WanLinkLogCollector.exe**   This tool enables its user to input the required information.</span></span>

  - <span data-ttu-id="0fc61-232">**BandwidthUtilizationAnalyzer. xlsm**  Microsoft Excel 試算表軟體報告會透過 WanLinkLogCollector 自動啟動。</span><span class="sxs-lookup"><span data-stu-id="0fc61-232">**BandwidthUtilizationAnalyzer.xlsm**  A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="0fc61-233">此應用程式可讓使用者將篩選套用至報表，如本文稍後所示。</span><span class="sxs-lookup"><span data-stu-id="0fc61-233">This application allows the user to apply filters to the report as shown later in this article.</span></span>

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="0fc61-234">使用頻寬利用率分析程式的階段</span><span class="sxs-lookup"><span data-stu-id="0fc61-234">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="0fc61-235">使用 [頻寬利用率] 分析程式有兩個階段：</span><span class="sxs-lookup"><span data-stu-id="0fc61-235">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

  - <span data-ttu-id="0fc61-236">收集使用 WanLinkLogCollector 執行的記錄</span><span class="sxs-lookup"><span data-stu-id="0fc61-236">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

  - <span data-ttu-id="0fc61-237">自訂報表，並使用 BandwidthUtilizationAnalyzer 進行 xlsm。</span><span class="sxs-lookup"><span data-stu-id="0fc61-237">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0fc61-238">我們強烈建議您不要由最終使用者手動啟動 BandwidthUtilizationAnalyzer。</span><span class="sxs-lookup"><span data-stu-id="0fc61-238">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="0fc61-239">啟動頻寬利用率分析程式</span><span class="sxs-lookup"><span data-stu-id="0fc61-239">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="0fc61-240">在命令提示字元中啟動 WanLinkLogCollector 或使用 Windows 資源管理器。</span><span class="sxs-lookup"><span data-stu-id="0fc61-240">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

<span data-ttu-id="0fc61-241">**使用 WanLinkLogCollector**</span><span class="sxs-lookup"><span data-stu-id="0fc61-241">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="0fc61-242">使用 WanLinkLogCollector 有三個步驟：</span><span class="sxs-lookup"><span data-stu-id="0fc61-242">There are three steps to using WanLinkLogCollector.exe:</span></span>

1.  <span data-ttu-id="0fc61-243">**記錄時程表**   提供報表需要產生的時程表</span><span class="sxs-lookup"><span data-stu-id="0fc61-243">**Log the timeline**   Provide the timeline that the report needs to be generated for</span></span>

2.  <span data-ttu-id="0fc61-244">**指定檔案目錄**   提供檔案位置資訊</span><span class="sxs-lookup"><span data-stu-id="0fc61-244">**Specify the file directories**   Provide file location information</span></span>

3.  <span data-ttu-id="0fc61-245">**收集記錄並啟動報表檢視器**  執行命令來產生報表</span><span class="sxs-lookup"><span data-stu-id="0fc61-245">**Collect the logs and launch the report viewer**  Execute the command to generate the report</span></span>

<div>

## <a name="step-1---log-the-timeline"></a><span data-ttu-id="0fc61-246">步驟 1-記錄時程表</span><span class="sxs-lookup"><span data-stu-id="0fc61-246">Step 1 - Log the timeline</span></span>

<span data-ttu-id="0fc61-247">記錄時間軸可讓工具使用者指定下列選項，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="0fc61-247">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1.  <span data-ttu-id="0fc61-248">**開始日期**這是要產生報告的時程表開始日期;例如，2010年8月1日。</span><span class="sxs-lookup"><span data-stu-id="0fc61-248">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2.  <span data-ttu-id="0fc61-249">**結束日期**這是要產生報告的時程表結束日期;例如，2010年9月30日。</span><span class="sxs-lookup"><span data-stu-id="0fc61-249">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>
    
    <span data-ttu-id="0fc61-250">[頻寬利用率]![中的 [開始] 和 [結束日期]](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "頻寬利用率中的開始和結束日期")</span><span class="sxs-lookup"><span data-stu-id="0fc61-250">![Start and End dates in the Bandwidth Utilization A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Start and End dates in the Bandwidth Utilization A")</span></span>  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="0fc61-251">步驟 2-指定檔案目錄</span><span class="sxs-lookup"><span data-stu-id="0fc61-251">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="0fc61-252">下列是可由使用者指定的檔案目錄，如所示。</span><span class="sxs-lookup"><span data-stu-id="0fc61-252">The following file directories can be specified by the user as shown.</span></span>

  - <span data-ttu-id="0fc61-253">**伺服器記錄檔位置**儲存頻寬原則伺服器記錄的資料夾位置。</span><span class="sxs-lookup"><span data-stu-id="0fc61-253">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="0fc61-254">這通常是在\<您\>\\\<選擇的 FE\>\\AppServerFiles\\PDP 中。</span><span class="sxs-lookup"><span data-stu-id="0fc61-254">This is typically in \<fileserver\>\\\<choice of FE\>\\AppServerFiles\\PDP.</span></span>

  - <span data-ttu-id="0fc61-255">**臨時檔案儲存位置**產生報告時儲存中間檔案的臨時檔案位置。</span><span class="sxs-lookup"><span data-stu-id="0fc61-255">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

<span data-ttu-id="0fc61-256">[頻寬利用率] 中![的檔案目錄 Anal](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "[頻寬利用率 Anal] 中")的檔案目錄</span><span class="sxs-lookup"><span data-stu-id="0fc61-256">![File directories in the Bandwidth Utilization Anal](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "File directories in the Bandwidth Utilization Anal")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0fc61-257">請確定有足夠的檔案存取伺服器記錄，並將 [臨時檔案存放區] 資料夾提供給工具使用者。</span><span class="sxs-lookup"><span data-stu-id="0fc61-257">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="0fc61-258">步驟 3-收集記錄並啟動報表檢視器</span><span class="sxs-lookup"><span data-stu-id="0fc61-258">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="0fc61-259">若要收集記錄並啟動報表檢視器，請按一下 [**執行**]，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0fc61-259">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="0fc61-260">此步驟會收集所需的資料。</span><span class="sxs-lookup"><span data-stu-id="0fc61-260">This step collects the required data.</span></span>

<span data-ttu-id="0fc61-261">![在頻寬利用率 Analy 中收集]資料(images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "在頻寬利用率 Analy 中收集資料")</span><span class="sxs-lookup"><span data-stu-id="0fc61-261">![Collecting data in the Bandwidth Utilization Analy](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Collecting data in the Bandwidth Utilization Analy")</span></span>

<span data-ttu-id="0fc61-262">輸入驗證成功後，會顯示下面所示的訊息。</span><span class="sxs-lookup"><span data-stu-id="0fc61-262">When the input validation is successful, the message shown below is displayed.</span></span>

<span data-ttu-id="0fc61-263">![在頻寬 Utili 記錄中收集的記錄]，在(images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "頻寬 Utili 中收集通知")</span><span class="sxs-lookup"><span data-stu-id="0fc61-263">![Logs collected notification in the Bandwidth Utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Logs collected notification in the Bandwidth Utili")</span></span>

<span data-ttu-id="0fc61-264">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0fc61-264">Click **OK**.</span></span> <span data-ttu-id="0fc61-265">BandwidthUtilizationAnalyzer。 xlsm 會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="0fc61-265">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="0fc61-266">依照訊息方塊中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="0fc61-266">Follow the instructions in the message box.</span></span> <span data-ttu-id="0fc61-267">如需詳細資訊，請參閱下一節中的 [**使用 BandwidthUtilizationAnalyzer xlsm** ]。</span><span class="sxs-lookup"><span data-stu-id="0fc61-267">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>

</div>

<div>


<span data-ttu-id="0fc61-268">**使用 BandwidthUtilizationAnalyzer xlsm**</span><span class="sxs-lookup"><span data-stu-id="0fc61-268">**Using BandwidthUtilizationAnalyzer.xlsm**</span></span>

1.  <span data-ttu-id="0fc61-269">當 xlsm 自動啟動時，請按一下 [重新整理] **，如下所**示。</span><span class="sxs-lookup"><span data-stu-id="0fc61-269">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>
    
    <span data-ttu-id="0fc61-270">![BandwidthUtilizationAnalyzer xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer. xlsm")</span><span class="sxs-lookup"><span data-stu-id="0fc61-270">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span></span>

2.  <span data-ttu-id="0fc61-271">開啟檔案資料夾時，請從訊息方塊中指定的位置選取 [合併] .csv，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0fc61-271">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="0fc61-272">它也會將位置顯示為**C\\： Temp**。</span><span class="sxs-lookup"><span data-stu-id="0fc61-272">It also shows the location as **C:\\Temp**.</span></span>
    
    <span data-ttu-id="0fc61-273">![開啟 BandwidthUtilizationAnalyzer 中的資料夾。](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "開啟 BandwidthUtilizationAnalyzer 中的資料夾。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-273">![Opening a folder in BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Opening a folder in BandwidthUtilizationAnalyzer.")</span></span>

3.  <span data-ttu-id="0fc61-274">按一下 [匯**入**]。</span><span class="sxs-lookup"><span data-stu-id="0fc61-274">Click **Import**.</span></span>

4.  <span data-ttu-id="0fc61-275">圖形化圖形就會自動產生。</span><span class="sxs-lookup"><span data-stu-id="0fc61-275">The graphical plot is automatically generated.</span></span> <span data-ttu-id="0fc61-276">當使用背景指標消失時，就可以使用它。</span><span class="sxs-lookup"><span data-stu-id="0fc61-276">It is available when the working-in-the-background pointer disappears.</span></span>
    
    <span data-ttu-id="0fc61-277">![在 [報表檢視] 中套用篩選。](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "在 [報表檢視] 中套用篩選。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-277">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="0fc61-278">將篩選套用至報表檢視</span><span class="sxs-lookup"><span data-stu-id="0fc61-278">Applying Filters to the Report View</span></span>

<span data-ttu-id="0fc61-279">以下說明可套用至報表檢視的篩選器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0fc61-279">The filters that can be applied to the report view as shown below are described as follows:</span></span>

<span data-ttu-id="0fc61-280">![在 [報表檢視] 中套用篩選。](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "在 [報表檢視] 中套用篩選。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-280">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

1.  <span data-ttu-id="0fc61-281">**名稱**依 WAN 連結篩選（篩選器位於圖形右側）。前置詞代表下列連結類型;請參閱 [垂直（藍色）] 方塊：</span><span class="sxs-lookup"><span data-stu-id="0fc61-281">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>
    
      - <span data-ttu-id="0fc61-282">**S 網站**從網路網站到網路區域的 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="0fc61-282">**S Site** The WAN link from a network site to a network region</span></span>
    
      - <span data-ttu-id="0fc61-283">**是站內網站**兩個網路網站之間的 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="0fc61-283">**IS Inter-Site** The WAN link between two network sites</span></span>
    
      - <span data-ttu-id="0fc61-284">**R 區域間**兩個網路區域之間的 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="0fc61-284">**R Inter-Region** The WAN link between two network region</span></span>

2.  <span data-ttu-id="0fc61-285">**超出限制**依頻寬利用率超過頻寬容量的 WAN 連結進行篩選</span><span class="sxs-lookup"><span data-stu-id="0fc61-285">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3.  <span data-ttu-id="0fc61-286">**重要等級**依頻寬利用率達到90% 或超過頻寬容量的 WAN 連結進行篩選</span><span class="sxs-lookup"><span data-stu-id="0fc61-286">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4.  <span data-ttu-id="0fc61-287">未**充分利用**依頻寬利用率小於頻寬容量25% 的 WAN 連結進行篩選</span><span class="sxs-lookup"><span data-stu-id="0fc61-287">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5.  <span data-ttu-id="0fc61-288">**連結類型**依下列 WAN 連結類型進行篩選：</span><span class="sxs-lookup"><span data-stu-id="0fc61-288">**Link type** Filter by the following WAN links types:</span></span>
    
      - <span data-ttu-id="0fc61-289">**網路網站**類型</span><span class="sxs-lookup"><span data-stu-id="0fc61-289">**Network site** type</span></span>
    
      - <span data-ttu-id="0fc61-290">**網站間**類型</span><span class="sxs-lookup"><span data-stu-id="0fc61-290">**Inter-site** type</span></span>
    
      - <span data-ttu-id="0fc61-291">**區域間連結**類型</span><span class="sxs-lookup"><span data-stu-id="0fc61-291">**Inter-Region link** type</span></span>

6.  <span data-ttu-id="0fc61-292">**地區**依網路區域篩選</span><span class="sxs-lookup"><span data-stu-id="0fc61-292">**Region** Filter by network region</span></span>

<span data-ttu-id="0fc61-293">下圖顯示前面所述的篩選。</span><span class="sxs-lookup"><span data-stu-id="0fc61-293">The following figures show the previously described filters.</span></span>

<span data-ttu-id="0fc61-294">依**名稱**篩選。</span><span class="sxs-lookup"><span data-stu-id="0fc61-294">Filter by **Name**.</span></span> <span data-ttu-id="0fc61-295">選取要在圖表中顯示的連結清單。</span><span class="sxs-lookup"><span data-stu-id="0fc61-295">Select the list of links that need to be displayed in the graph.</span></span>

<span data-ttu-id="0fc61-296">![依名稱在 BandwidthUtilizationAnalyzer 中篩選。](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "依名稱在 BandwidthUtilizationAnalyzer 中篩選。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-296">![Filtering by Name in BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtering by Name in BandwidthUtilizationAnalyzer.")</span></span>

<span data-ttu-id="0fc61-297">依**超出限制**進行篩選。</span><span class="sxs-lookup"><span data-stu-id="0fc61-297">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="0fc61-298">選取 [ **True** ]，強制執行篩選。</span><span class="sxs-lookup"><span data-stu-id="0fc61-298">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="0fc61-299">![依超過限制進行篩選。](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "依超過限制進行篩選。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-299">![Filtering by Exceeded Limit.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtering by Exceeded Limit.")</span></span>

<span data-ttu-id="0fc61-300">依**臨界層級**篩選。</span><span class="sxs-lookup"><span data-stu-id="0fc61-300">Filter by **Critical levels**.</span></span> <span data-ttu-id="0fc61-301">選取 [ **True** ]，強制執行篩選。</span><span class="sxs-lookup"><span data-stu-id="0fc61-301">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="0fc61-302">![依重要等級篩選。](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "依重要等級篩選。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-302">![Filtering by Critical Levels.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtering by Critical Levels.")</span></span>

<span data-ttu-id="0fc61-303">根據**利用率**情況進行篩選。</span><span class="sxs-lookup"><span data-stu-id="0fc61-303">Filter by **Under utilized**.</span></span> <span data-ttu-id="0fc61-304">選取 [ **True** ]，強制執行篩選。</span><span class="sxs-lookup"><span data-stu-id="0fc61-304">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="0fc61-305">![根據利用率進行篩選。](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "根據利用率進行篩選。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-305">![Filtering by Under Utilized.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtering by Under Utilized.")</span></span>

<span data-ttu-id="0fc61-306">依**連結類型**篩選。</span><span class="sxs-lookup"><span data-stu-id="0fc61-306">Filter by **Link Type**.</span></span> <span data-ttu-id="0fc61-307">選取需要顯示的一種或多種類型。</span><span class="sxs-lookup"><span data-stu-id="0fc61-307">Select the type or types that need to be displayed.</span></span>

<span data-ttu-id="0fc61-308">![依連結類型進行篩選。](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "依連結類型進行篩選。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-308">![Filtering by Link Type.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtering by Link Type.")</span></span>

<span data-ttu-id="0fc61-309">依**區域**篩選。</span><span class="sxs-lookup"><span data-stu-id="0fc61-309">Filter by **Region**.</span></span> <span data-ttu-id="0fc61-310">選取需要顯示其連結的地區清單。</span><span class="sxs-lookup"><span data-stu-id="0fc61-310">Select a list of regions whose links need to be displayed.</span></span>

<span data-ttu-id="0fc61-311">![依區域進行篩選。](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "依區域進行篩選。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-311">![Filtering by Region.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtering by Region.")</span></span>

</div>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="0fc61-312">需求</span><span class="sxs-lookup"><span data-stu-id="0fc61-312">Requirements</span></span>

  - <span data-ttu-id="0fc61-313">.NET Framework 3。5</span><span class="sxs-lookup"><span data-stu-id="0fc61-313">The .NET Framework 3.5</span></span>

  - <span data-ttu-id="0fc61-314">Microsoft Excel 2010 或 Excel 2007</span><span class="sxs-lookup"><span data-stu-id="0fc61-314">Microsoft Excel 2010 or Excel 2007</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="0fc61-315">總結</span><span class="sxs-lookup"><span data-stu-id="0fc61-315">Summary</span></span>

<span data-ttu-id="0fc61-316">頻寬利用率分析程式是用來繪製網路上 UC 流量的音訊頻寬利用率。</span><span class="sxs-lookup"><span data-stu-id="0fc61-316">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="0fc61-317">您也可以使用這個工具，來報告網路上的視頻頻寬利用率。</span><span class="sxs-lookup"><span data-stu-id="0fc61-317">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

</div>

</div>

<div>

## <a name="call-parkometer"></a><span data-ttu-id="0fc61-318">呼叫 Parkometer</span><span class="sxs-lookup"><span data-stu-id="0fc61-318">Call Parkometer</span></span>

<span data-ttu-id="0fc61-319">呼叫 Parkometer 是一種命令列應用程式，可讓您輕鬆存取 [通話駐留軌道] 資料庫。</span><span class="sxs-lookup"><span data-stu-id="0fc61-319">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="0fc61-320">描述</span><span class="sxs-lookup"><span data-stu-id="0fc61-320">Description</span></span>

<span data-ttu-id="0fc61-321">呼叫 Parkometer 是一種追蹤目前寄存通話的工具。</span><span class="sxs-lookup"><span data-stu-id="0fc61-321">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="0fc61-322">它也會收集有關軌道式及通話駐留伺服器（CPS）用法的統計資料。</span><span class="sxs-lookup"><span data-stu-id="0fc61-322">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="0fc61-323">這個命令列工具提供從本機或遠端連線的電腦對 CPS 軌道 SQL Server 資料庫的讀取和寫入存取權。</span><span class="sxs-lookup"><span data-stu-id="0fc61-323">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="0fc61-324">所有選項都是互相排斥的。</span><span class="sxs-lookup"><span data-stu-id="0fc61-324">All options are mutually exclusive.</span></span> <span data-ttu-id="0fc61-325">命令列語法如下所示：</span><span class="sxs-lookup"><span data-stu-id="0fc61-325">Command-line syntax is as follows:</span></span>

  - <span data-ttu-id="0fc61-326">**– o**參數-列出針對此池子設定的所有軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="0fc61-326">**–o** parameter—lists all orbit ranges configured for this pool.</span></span>

  - <span data-ttu-id="0fc61-327">**– n**參數：列出此池子中所有目前使用的軌道式。</span><span class="sxs-lookup"><span data-stu-id="0fc61-327">**–n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="0fc61-328">顯示的資訊如下所示：</span><span class="sxs-lookup"><span data-stu-id="0fc61-328">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="0fc61-329">Parkee 和 parker 的 SIP 統一資源識別項（URI）。</span><span class="sxs-lookup"><span data-stu-id="0fc61-329">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>
    
      - <span data-ttu-id="0fc61-330">停用通話的 CPS 主機名稱。</span><span class="sxs-lookup"><span data-stu-id="0fc61-330">Host name of the CPS where the call is parked.</span></span>
    
      - <span data-ttu-id="0fc61-331">通話停用的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="0fc61-331">Time stamp of when the call was parked.</span></span>

  - <span data-ttu-id="0fc61-332">**– f**參數：列出池中目前閒置的 [軌道式] 數目。</span><span class="sxs-lookup"><span data-stu-id="0fc61-332">**–f** parameter—lists the number of currently free orbits in the pool.</span></span>

  - <span data-ttu-id="0fc61-333">\*\*– r \<n\> \*\*參數：列出\<n\>個最後一個寄存通話。</span><span class="sxs-lookup"><span data-stu-id="0fc61-333">**–r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="0fc61-334">顯示的資訊如下所示：</span><span class="sxs-lookup"><span data-stu-id="0fc61-334">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="0fc61-335">Parkee SIP URI。</span><span class="sxs-lookup"><span data-stu-id="0fc61-335">Parkee SIP URI.</span></span>
    
      - <span data-ttu-id="0fc61-336">Parker SIP URI。</span><span class="sxs-lookup"><span data-stu-id="0fc61-336">Parker SIP URI.</span></span>
    
      - <span data-ttu-id="0fc61-337">停用通話的 CPS 主機名稱。</span><span class="sxs-lookup"><span data-stu-id="0fc61-337">Host name of the CPS where the call was parked.</span></span>
    
      - <span data-ttu-id="0fc61-338">檢索或丟棄通話的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="0fc61-338">Time stamp of when the call was retrieved or dropped.</span></span>

  - <span data-ttu-id="0fc61-339">\*\*-t\<n\> \*\*參數-測試在資料庫中保留軌道，以顯示指定的軌道編號的隨機性。</span><span class="sxs-lookup"><span data-stu-id="0fc61-339">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="0fc61-340">收</span><span class="sxs-lookup"><span data-stu-id="0fc61-340">Output</span></span>

<span data-ttu-id="0fc61-341">根據在命令提示字元中指定的輸入參數，呼叫 Parkometer 會顯示下列輸出：</span><span class="sxs-lookup"><span data-stu-id="0fc61-341">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

  - <span data-ttu-id="0fc61-342">針對此泳池設定的所有軌道範圍</span><span class="sxs-lookup"><span data-stu-id="0fc61-342">All orbit ranges that are configured for this pool</span></span>

  - <span data-ttu-id="0fc61-343">目前停用通話</span><span class="sxs-lookup"><span data-stu-id="0fc61-343">Currently parked calls</span></span>

  - <span data-ttu-id="0fc61-344">空閒（可用）軌道式的數目</span><span class="sxs-lookup"><span data-stu-id="0fc61-344">Number of free (available) orbits</span></span>

  - <span data-ttu-id="0fc61-345">最近寄存的通話</span><span class="sxs-lookup"><span data-stu-id="0fc61-345">Recently parked calls</span></span>

  - <span data-ttu-id="0fc61-346">用於測試均勻與隨機軌道值的保留軌道</span><span class="sxs-lookup"><span data-stu-id="0fc61-346">Reserved orbits for testing uniform and random orbit values</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="0fc61-347">特殊</span><span class="sxs-lookup"><span data-stu-id="0fc61-347">Purpose</span></span>

<span data-ttu-id="0fc61-348">CPS 工具的用途是提供對 CPS 資料庫的命令列存取權。</span><span class="sxs-lookup"><span data-stu-id="0fc61-348">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="0fc61-349">系統管理員可以查看 CPS 使用量，並決定指派給池子的軌道數。</span><span class="sxs-lookup"><span data-stu-id="0fc61-349">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="0fc61-350">需求</span><span class="sxs-lookup"><span data-stu-id="0fc61-350">Requirements</span></span>

<span data-ttu-id="0fc61-351">如果此工具是在執行 CPS 的同一部電腦上執行，就沒有任何需求。</span><span class="sxs-lookup"><span data-stu-id="0fc61-351">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="0fc61-352">如果此工具是在遠端電腦上執行，則必須將 Lync Server 2013 使用的 SQL Server 資料庫設定為允許遠端存取。</span><span class="sxs-lookup"><span data-stu-id="0fc61-352">If this tool is run on a remote computer, the SQL Server database used by Lync Server 2013 must be configured to allow remote access.</span></span> <span data-ttu-id="0fc61-353">必須使用 SQL Server 資料庫連線字串來設定呼叫 Parkometer，才能連線至該池的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="0fc61-353">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool’s SQL Server.</span></span> <span data-ttu-id="0fc61-354">這個 SQL Server 資料庫連線字串是在設定檔**parkometer .config**中定義。它必須放在 parkometer 所在的同一個目錄中。</span><span class="sxs-lookup"><span data-stu-id="0fc61-354">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="0fc61-355">下列 XML 檔案就是 parkometer 的範例。必須設定的參數為 user name （例如，mydomain\\系統管理員）、密碼（例如，mypassword），以及主機名稱（例如 myserver）。</span><span class="sxs-lookup"><span data-stu-id="0fc61-355">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
       <add key="SQL" value="server=myserver\RTC;
    database=cpsdyn;
    User Id=mydomain\Administrator;
    Password=mypassword.;
    Integrated Security=false;"/>
      </appSettings>
    </configuration>
```

</div>

<div>

## <a name="examples"></a><span data-ttu-id="0fc61-356">範例</span><span class="sxs-lookup"><span data-stu-id="0fc61-356">Examples</span></span>

<span data-ttu-id="0fc61-357">已部署的軌道範圍： o 參數會列出針對此池子設定的所有軌道範圍，如圖所示</span><span class="sxs-lookup"><span data-stu-id="0fc61-357">Deployed orbit ranges: the –o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

<span data-ttu-id="0fc61-358">[![呼叫 Parkometer] 中的軌道範圍。][(images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "呼叫 Parkometer] 中的軌道範圍。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-358">![Orbit ranges in Call Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Orbit ranges in Call Parkometer.")</span></span>

<span data-ttu-id="0fc61-359">目前停用的通話：-n 參數會列出此圖池中所有目前使用的軌道式，如圖所示</span><span class="sxs-lookup"><span data-stu-id="0fc61-359">Currently parked calls: the –n parameter lists all currently used orbits on this pool as shown</span></span>

<span data-ttu-id="0fc61-360">[![通話 Parkometer] 中目前停用的通話。][(images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "通話 Parkometer] 中目前停用的通話。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-360">![Currently-parked calls in Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Currently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="0fc61-361">[自由] 軌道式數： f 參數會列出池中目前可用的軌道式的數目，如圖所示</span><span class="sxs-lookup"><span data-stu-id="0fc61-361">Number of free orbits: the –f parameter lists the number of currently free orbits in the pool as shown</span></span>

<span data-ttu-id="0fc61-362">![在 [呼叫 Parkometer] 中釋放 [軌道式]。](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "在 [呼叫 Parkometer] 中釋放 [軌道式]。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-362">![Free orbits in Call Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Free orbits in Call Parkometer.")</span></span>

<span data-ttu-id="0fc61-363">最近寄存的通話：-r \<n\>參數會列出\<n\>個最後暫停的呼叫（如圖所示）</span><span class="sxs-lookup"><span data-stu-id="0fc61-363">Recently parked calls: the –r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

<span data-ttu-id="0fc61-364">[![通話 Parkometer] 中最近寄存的通話。][(images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "通話 Parkometer] 中最近寄存的通話。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-364">![Recently-parked calls in Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Recently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="0fc61-365">測試軌道保留： [t \<n\> ] 參數測試在資料庫中保留軌道，如圖所示</span><span class="sxs-lookup"><span data-stu-id="0fc61-365">Test orbit reservation: the –t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

<span data-ttu-id="0fc61-366">[![通話 Parkometer] 中的測試軌道保留。][(images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "通話 Parkometer] 中的測試軌道保留。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-366">![Test orbit reservations in Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Test orbit reservations in Call Parkometer.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="0fc61-367">總結</span><span class="sxs-lookup"><span data-stu-id="0fc61-367">Summary</span></span>

<span data-ttu-id="0fc61-368">呼叫 Parkometer 是一種命令列工具，可提供通話寄存伺服器的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="0fc61-368">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a><span data-ttu-id="0fc61-369">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="0fc61-369">CleanupStorageServiceData</span></span>

<span data-ttu-id="0fc61-370">CleanupStorageServiceData 資源套件工具可讓您從 Lync Server Storage Service （LYSS）所使用的資料庫中刪除孤立的資料。</span><span class="sxs-lookup"><span data-stu-id="0fc61-370">The CleanupStorageServiceData resource kit tool allows for deleting of orphaned data from the database used by the Lync Server Storage Service (LYSS).</span></span> <span data-ttu-id="0fc61-371">儲存服務的其中一個功能是在 Lync 伺服器與各種後端資料存儲端點（例如 SQL Server 和 Exchange）之間緩衝通訊。</span><span class="sxs-lookup"><span data-stu-id="0fc61-371">One function of the storage service is to buffer communication between Lync Server and various back-end data storage endpoints, like SQL Server and Exchange.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="0fc61-372">描述</span><span class="sxs-lookup"><span data-stu-id="0fc61-372">Description</span></span>

<span data-ttu-id="0fc61-373">為了支援高可用性，LYSS 會暫時在池中的多個前端伺服器上接受及儲存資料複本，並在資料傳送到其最終的長期儲存位置之後，移除該資料。</span><span class="sxs-lookup"><span data-stu-id="0fc61-373">To support high availability, LYSS accepts and saves copies of the data on multiple front end servers in the pool temporarily, and removes that data once it has been delivered to its final long-term storage location.</span></span> <span data-ttu-id="0fc61-374">在其他情況下，當伺服器可能當機或遇到處理問題，且某些資料可能無法正確清除時，可能會發生這種不尋常的情況。</span><span class="sxs-lookup"><span data-stu-id="0fc61-374">There are unusual situations which may occur during otherwise normal operation, when a server might crash or experience a processing issue, and some data might not get cleaned up properly.</span></span> <span data-ttu-id="0fc61-375">這個資料無害，但會佔用有限的處理資源。</span><span class="sxs-lookup"><span data-stu-id="0fc61-375">This data is harmless, but it does consume limited processing resources.</span></span> <span data-ttu-id="0fc61-376">一般需要的資料維護都是自動化的，但此工具可讓您在無法自動移除的情況下，以安全身分識別及移除這類孤立資料。</span><span class="sxs-lookup"><span data-stu-id="0fc61-376">Much of the normal required data maintenance is automated, but this tool allows for the safe identification and removal of such orphaned data when automated removal is not possible.</span></span> <span data-ttu-id="0fc61-377">在引發「健康情況監視系統中心」作業管理員（SCOM）警示時會顯示此工具的用法，要求系統管理員從池中的本機 LYSS 資料庫中移除不需要的資料。</span><span class="sxs-lookup"><span data-stu-id="0fc61-377">Usage of this tool is indicated when a health monitoring System Center Operations Manager (SCOM) alert is raised which asks the administrator to remove the unneeded data from the local LYSS databases in the pool.</span></span> <span data-ttu-id="0fc61-378">在觸發預警之前端的事件記錄中，將會有對應的事件。</span><span class="sxs-lookup"><span data-stu-id="0fc61-378">There will be a corresponding event in the event log on the front end which triggered the alert.</span></span> <span data-ttu-id="0fc61-379">事件詳細資料將會包含前端所含孤立資料量的相關資訊，且在該資料超過特定的預先判斷閾值時引發</span><span class="sxs-lookup"><span data-stu-id="0fc61-379">The event details will contain information about the amount of orphaned data contained on the front end, and is raised when that data exceeds certain pre-determine thresholds</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="0fc61-380">需求</span><span class="sxs-lookup"><span data-stu-id="0fc61-380">Requirements</span></span>

<span data-ttu-id="0fc61-381">安裝 Lync Server 2013、資源套件工具。</span><span class="sxs-lookup"><span data-stu-id="0fc61-381">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="0fc61-382">此工具會在安裝了 Lync Server 和 Lync Server 2013 管理命令介面的已加入網域的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="0fc61-382">The tool runs on domain-joined machines where Lync Server and Lync Server 2013 Management Shell are installed.</span></span> <span data-ttu-id="0fc61-383">此工具會使用來自管理命令介面的 Cmdlet 來找出池中的所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="0fc61-383">The tool uses a cmdlet from the management shell to identify all Front End servers in the pool.</span></span> <span data-ttu-id="0fc61-384">其次，您必須從已安裝**RtcLocal**資料庫的池中的電腦執行該工具。</span><span class="sxs-lookup"><span data-stu-id="0fc61-384">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="0fc61-385">CleanupStorageServiceData 工具會使用此資料庫，以取得與 Lync Server 路由服務通訊所需的連線詳細資料。最後，調用該工具的帳戶或憑證必須具備檔案共用的讀/寫許可權，才能寫入輸出記錄。此外，這個工具也會視池處於穩定狀態。</span><span class="sxs-lookup"><span data-stu-id="0fc61-385">This database is used by the CleanupStorageServiceData tool to get the connection details needed to communicate with the Lync Server Routing Service.Finally, the account or credential invoking the tool must have read/write permission to the file share to which they want to write the output log.Also, this tool depends on the pool being in a stable state.</span></span> <span data-ttu-id="0fc61-386">實質上，這表示每個前端伺服器都要啟動並執行，因此 SQL Server LYNCLOCAL 實例和 LYSS 資料庫必須能夠連線至，且每個路由群組都必須有一組完整的1個主要前端伺服器和2個副前端 servers.</span><span class="sxs-lookup"><span data-stu-id="0fc61-386">In essence this means that every Front End server is expected to be up and running, the SQL Server LYNCLOCAL instance and LYSS database must be able to be connected to, and each routing group must have a complete set of 1 primary Front End servers and 2 secondary Front End servers.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="0fc61-387">範例</span><span class="sxs-lookup"><span data-stu-id="0fc61-387">Examples</span></span>

<span data-ttu-id="0fc61-388">C：\\Program Files\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="0fc61-388">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData.exe</span></span>

    Description:
    This tool will remove orphaned data from the Storage Service database
    for a pool. You are required to run this tool on a machine inside the
    pool which has the Lync Server Management Shell installed and has RtcLocal database installed.
    Usage: Default behavior is to clean up orphaned data from the all the 
           Storage Service databases in the current pool.
    Additional Options:
    -Verbose    : Turn verbose output on.
    -LogPath    : The UNC path to which to write the log.
    ------------------------------------------------------------------------------
    Please wait while we initialize...
    Found 4 front end servers
    Replica Instances for LYSS Service
    Address: server2.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server1.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server3.vdomain.com - Primaries: 7 Secondaries: 14
    Primary Total Count = 28, Secondary Total Count = 56
    Finding and removing orphaned data for 28 routing groups
    Removing 1 stale groups from FE server.vdomain.com
    No stale routing groups detected on FE server2.vdomain.com
    No stale routing groups detected on FE server1.vdomain.com
    No stale routing groups detected on FE server3.vdomain.com
    Searching for stale queue items
    Removed 20 stale queue items for routing group 17D5435AE40259F7BBDF1866776386E4
    No stale queue items found for routing group 1975349662315F90B119DACB4F2AE3AD
    No stale queue items found for routing group 1A23E3D58BDB5A458A0B73F34AB7ACBE
    No stale queue items found for routing group 1AC91E3A1029535A80123121989CEADC
    No stale queue items found for routing group 3313935458E35B9B9759E08A15D251E6
    No stale queue items found for routing group 39BB0035B06B5427873FC6099720462A
    No stale queue items found for routing group 40721948E7B55CE893A53E911F76D185
    No stale queue items found for routing group 4501E04EAE4856059346949FF817C220
    No stale queue items found for routing group 4D833C98801F546F8E45E417EE028E2E
    No stale queue items found for routing group 5AD77443AD955A22A876749BE66D5317
    No stale queue items found for routing group 69844A271E6C5633A1F2B46A42287DD6
    No stale queue items found for routing group 69DA3BE407A95C7284EB4B1337718C93
    No stale queue items found for routing group 8437358AB34A5CC8967D5EF39494AB8D
    No stale queue items found for routing group 8ED455B1789655359816E1C5BF4C430F
    No stale queue items found for routing group 904F6C9B8AC951AE8B3C86684D3832E4
    No stale queue items found for routing group 90AAB3AE9A1950E0ADE7809A27021D63
    No stale queue items found for routing group 944F5724C65C5F93900DC1C8C898B102
    No stale queue items found for routing group 9E8A2630250C51769E39F63F0FB552BA
    No stale queue items found for routing group A11E27AE439A582288D4657EDA86B565
    No stale queue items found for routing group A9B10C76E764556FAEA3E47301EDF518
    No stale queue items found for routing group AEA2699E74ED59848ACEA7896699430D
    No stale queue items found for routing group B269961603E75065AFDA4F4F006DA5E4
    No stale queue items found for routing group BB873D9A3DA959DAB2FD743E5AA619F7
    No stale queue items found for routing group BCC6A48FBA2454B79B9EDB276657A404
    No stale queue items found for routing group C8EF4805722B5F6C876EBC0440B420FD
    No stale queue items found for routing group CA38EBDAC4845489ACE208C2240E4056
    No stale queue items found for routing group F5921887DB025C5F908CE42DB7F1AEE8
    No stale queue items found for routing group F9E606A825395422B3BF7A01ECBB7B1F
    Writing log: M:\Dev\Server\ResKit\StorageService\CleanupStorageServiceData.Log_20121009_151040
    Tool has finished execution.  Errors encountered: 0
    C:\Program Files\Microsoft Lync Server 2013\ResKit\StorageService>

</div>

</div>

<div>

## <a name="dbanalyze"></a><span data-ttu-id="0fc61-389">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="0fc61-389">DBAnalyze</span></span>

<div>

## <a name="description"></a><span data-ttu-id="0fc61-390">描述</span><span class="sxs-lookup"><span data-stu-id="0fc61-390">Description</span></span>

<span data-ttu-id="0fc61-391">DBAnalyze 是一種命令列工具，可協助管理員收集 Lync Server 2013 資料庫的分析報告。</span><span class="sxs-lookup"><span data-stu-id="0fc61-391">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Lync Server 2013 databases.</span></span> <span data-ttu-id="0fc61-392">DBAnalyze 具有下列模式： [診斷]、[使用者資料]、[會議]、[MCUs] 和 [磁片碎片]：</span><span class="sxs-lookup"><span data-stu-id="0fc61-392">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

  - <span data-ttu-id="0fc61-393">**診斷模式**   會建立包含資料表相關資訊的報表（記錄數、分段、資料大小及索引大小、資料和記錄檔大小、在執行 Microsoft Office 通訊伺服器的伺服器之間的連絡人分佈、每個使用者的平均許可權數、連絡人、容器、訂閱、發佈、每位使用者所整理的會議平均數，以及無法傳送的使用者數會議、活動會議和資料庫版本。</span><span class="sxs-lookup"><span data-stu-id="0fc61-393">**Diagnostic mode**   Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can’t be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0fc61-394">運行診斷模式可能會影響伺服器效能。</span><span class="sxs-lookup"><span data-stu-id="0fc61-394">Running diagnostic mode can affect server performance.</span></span>

    
    </div>

  - <span data-ttu-id="0fc61-395">**使用者資料模式**  ：針對指定使用者或在連絡人與許可權清單中擁有該使用者的使用者，報告連絡人、容器、訂閱、發佈、許可權和連絡人群組資料。</span><span class="sxs-lookup"><span data-stu-id="0fc61-395">**User data mode**  Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="0fc61-396">此模式也會報告使用者組織或受邀之會議的摘要資料。</span><span class="sxs-lookup"><span data-stu-id="0fc61-396">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

  - <span data-ttu-id="0fc61-397">**[會議模式]**   會報告特定會議的詳細資料，包括會議的所有排程時間詳細資料、受邀者清單、會議所允許的媒體類型清單、作用中 MCUs （multipoint 控制項單位）、作用中的參與者清單，以及每個參與者的寄件者狀態。</span><span class="sxs-lookup"><span data-stu-id="0fc61-397">**Conference mode**   Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant’s signaling state.</span></span>

  - <span data-ttu-id="0fc61-398">**[解碼會議 ID**  ] 會解碼由 **/pstnid**開關指定的公用交換電話網絡（PSTN）會議 ID，但不會連線到後端以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="0fc61-398">**Decode Meeting ID**  Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

  - <span data-ttu-id="0fc61-399">**解決會議**   解碼由 **/pstnid**開關指定的 PSTN 會議 ID，並顯示由識別碼所指示之會議的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0fc61-399">**Resolve conference**   Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

  - <span data-ttu-id="0fc61-400">**MCUs 模式**  會報告池中每個 MCU 的識別碼、媒體類型、URL、心跳狀態、會議載入以及參與者負載。</span><span class="sxs-lookup"><span data-stu-id="0fc61-400">**MCUs mode**  Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

  - <span data-ttu-id="0fc61-401">**[磁片分段模式]**  會顯示所有磁片的碎片狀態。</span><span class="sxs-lookup"><span data-stu-id="0fc61-401">**Disk fragmentation mode**  Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="0fc61-402">此工具可用於診斷各種問題，或協助系統管理員進行容量規劃。</span><span class="sxs-lookup"><span data-stu-id="0fc61-402">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="0fc61-403">例如，如果大多數駐留在伺服器上的使用者選擇的是伺服器 B 上的使用者作為其連絡人，系統管理員可以將伺服器 A 上的使用者移至伺服器 B，以減少跨伺服器的流量。</span><span class="sxs-lookup"><span data-stu-id="0fc61-403">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="0fc61-404">收</span><span class="sxs-lookup"><span data-stu-id="0fc61-404">Output</span></span>

<span data-ttu-id="0fc61-405">這個工具會輸出 Lync Server 2013 資料庫的預先定義報告。</span><span class="sxs-lookup"><span data-stu-id="0fc61-405">This tool outputs predefined reports about the Lync Server 2013 database.</span></span> <span data-ttu-id="0fc61-406">**路徑：** % ProgramFiles%\\Microsoft Lync Server 2013\\Reskit</span><span class="sxs-lookup"><span data-stu-id="0fc61-406">**Path:** %ProgramFiles%\\Microsoft Lync Server 2013\\Reskit</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="0fc61-407">特殊</span><span class="sxs-lookup"><span data-stu-id="0fc61-407">Purpose</span></span>

<span data-ttu-id="0fc61-408">若要安裝 Dbanalyze，請將它複製到本機資料夾，然後執行該工具。</span><span class="sxs-lookup"><span data-stu-id="0fc61-408">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="0fc61-409">若要使用該工具，請從命令列執行下列命令。`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span><span class="sxs-lookup"><span data-stu-id="0fc61-409">To use the tool, run the following command from the command line.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span></span> <span data-ttu-id="0fc61-410">命令列選項的描述如下所示。</span><span class="sxs-lookup"><span data-stu-id="0fc61-410">The descriptions for the command-line options are shown below.</span></span>

<span data-ttu-id="0fc61-411">![Dbanalyze 的命令列選項。](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Dbanalyze 的命令列選項。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-411">![Command line options for Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Command line options for Dbanalyze.exe.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="0fc61-412">需求</span><span class="sxs-lookup"><span data-stu-id="0fc61-412">Requirements</span></span>

<span data-ttu-id="0fc61-413">**電腦**DBAnalyze 只能從已安裝 Lync Server 2013 的已加入網域的電腦執行。</span><span class="sxs-lookup"><span data-stu-id="0fc61-413">**Computer** DBAnalyze can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span>

<span data-ttu-id="0fc61-414">**網路**電腦應該能夠連接到後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="0fc61-414">**Network** The computer should be able to connect to the back-end database.</span></span>

<span data-ttu-id="0fc61-415">**軟體**您必須先安裝 Lync Server 2013 軟體元件，才能執行 DBAnalyze。</span><span class="sxs-lookup"><span data-stu-id="0fc61-415">**Software** Lync Server 2013 software components must be installed before running DBAnalyze.</span></span>

<span data-ttu-id="0fc61-416">**使用者**下表顯示擁有存取 Lync Server 2013 資料庫所需許可權的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="0fc61-416">**Users**The table below shows the administrators who have the necessary permissions to access Lync Server 2013 databases.</span></span>

<span data-ttu-id="0fc61-417">![Dbanalyze 的 [許可權] 資料表。](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Dbanalyze 的 [許可權] 資料表。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-417">![Permissions table for Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Permissions table for Dbanalyze.exe.")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0fc61-418"><STRONG>/Report：磁片</STRONG>模式需要本機系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="0fc61-418">A local administrator account is required for <STRONG>/report:disk</STRONG> mode.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="0fc61-419">範例</span><span class="sxs-lookup"><span data-stu-id="0fc61-419">Examples</span></span>

<span data-ttu-id="0fc61-420">下列是有效 Dbanalyze 命令的範例：</span><span class="sxs-lookup"><span data-stu-id="0fc61-420">The following are examples of valid Dbanalyze.exe commands:</span></span>

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a><span data-ttu-id="0fc61-421">總結</span><span class="sxs-lookup"><span data-stu-id="0fc61-421">Summary</span></span>

<span data-ttu-id="0fc61-422">DBAnalyzer 可讓系統管理員快速且輕鬆地分析 Lync Server 2013 資料庫。</span><span class="sxs-lookup"><span data-stu-id="0fc61-422">DBAnalyzer provides administrators a quick and easy to analyze Lync Server 2013 databases.</span></span>

</div>

</div>

<div>

## <a name="importstorageservicedata"></a><span data-ttu-id="0fc61-423">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="0fc61-423">ImportStorageServiceData</span></span>

<span data-ttu-id="0fc61-424">ImportStorageServiceData 資源套件工具可讓您重新匯入儲存空間服務（LYSS）的佇列和端點資料，並傳回儲存服務。</span><span class="sxs-lookup"><span data-stu-id="0fc61-424">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="0fc61-425">描述</span><span class="sxs-lookup"><span data-stu-id="0fc61-425">Description</span></span>

<span data-ttu-id="0fc61-426">從存儲服務中清除的資料，可能會根據佇列專案狀態或資料庫大小，自動（定期）。</span><span class="sxs-lookup"><span data-stu-id="0fc61-426">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="0fc61-427">這可能是因為手動調用 pool 容錯移轉 Cmdlet，或 StorageServiceFullFlush Cmdlet （這是池容錯移轉 Cmdlet 的調用）。</span><span class="sxs-lookup"><span data-stu-id="0fc61-427">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="0fc61-428">請注意，如果前端的任何儲存服務（LYSS）資料庫大小都在 [標準] 層級之上，則最好不要重新匯入資料，因為這樣做可能只會導致更多資料匯出回來。此外，您應該先解決導致存儲服務佇列增長的錯誤所帶來的任何問題（例如 Exchange 端點錯誤、網路問題或其他問題）。</span><span class="sxs-lookup"><span data-stu-id="0fc61-428">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

<span data-ttu-id="0fc61-429">**案例1：** 在 pool 進行容錯移轉期間，可能會從每個前端的 storage services 中清除檔案。</span><span class="sxs-lookup"><span data-stu-id="0fc61-429">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="0fc61-430">容錯移轉完成後，應執行該工具，以重新匯入資料。</span><span class="sxs-lookup"><span data-stu-id="0fc61-430">After failover is completed, the tool should be run to re-import the data.</span></span>

<span data-ttu-id="0fc61-431">**案例2：** 每日自動刷新資料，或以回應超過特定大小閾值的儲存服務資料庫（例如60%、80%、90%）。</span><span class="sxs-lookup"><span data-stu-id="0fc61-431">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="0fc61-432">這個自動刷新的資料應該由系統管理員定期重新匯入。</span><span class="sxs-lookup"><span data-stu-id="0fc61-432">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="0fc61-433">在上述情況下，如果沒有部署監視 SCOM 套件，則會有與從儲存服務清除之資料相關的 Lync Server Storage 服務事件。</span><span class="sxs-lookup"><span data-stu-id="0fc61-433">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Lync Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="0fc61-434">32075（完整清除作業的啟動）、32076（完全清除已完成）、32082（維護層級清洗完成）、32083（維護層級清理完成）、32089（因填滿資料庫而發生清洗）等的事件 Id。</span><span class="sxs-lookup"><span data-stu-id="0fc61-434">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="0fc61-435">注意：這些事件識別碼與 RTM 版本相對應。</span><span class="sxs-lookup"><span data-stu-id="0fc61-435">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="0fc61-436">當管理員看到這些事件時，表示檔案中有已清除的檔案。這個資料應該使用這個工具（例如每週一次），重新匯入。</span><span class="sxs-lookup"><span data-stu-id="0fc61-436">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="0fc61-437">針對線上服務版本，如果已部署 Lync Server 的健康情況監視 SCOM 套件，可能會引發新的警示，要求系統管理員重新將清除的資料匯入儲存服務。</span><span class="sxs-lookup"><span data-stu-id="0fc61-437">For the Online Service release, if health monitoring SCOM pack for Lync Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="0fc61-438">在前端伺服器上的事件記錄中，會有對應的事件觸發警示。</span><span class="sxs-lookup"><span data-stu-id="0fc61-438">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="0fc61-439">事件將會提供所需的父路徑的描述，以及有多少個檔案會符合警報準則。</span><span class="sxs-lookup"><span data-stu-id="0fc61-439">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="0fc61-440">[警示準則] 是特定父路徑下的 X 或更多檔案，這些檔案至少是最早的 Y 天（在 StorageService 中，X 和 Y 是預先設定的，但可透過變更 APPCONFIG 檔案來覆寫）。下面顯示可觸發健全性警報的兩個事件範例，區別是其父路徑。</span><span class="sxs-lookup"><span data-stu-id="0fc61-440">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="0fc61-441">其中一個可能是在 Web 服務檔案共用下，另一個可能就是每個前端的本機應用程式資料目錄。</span><span class="sxs-lookup"><span data-stu-id="0fc61-441">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="0fc61-442">（例如，c：\\ProgramData\\Microsoft\\Lync Server\\StorageService）。</span><span class="sxs-lookup"><span data-stu-id="0fc61-442">( for example c:\\ProgramData\\Microsoft\\Lync Server\\StorageService ).</span></span> <span data-ttu-id="0fc61-443">然後，系統管理員會執行這個 reskit 工具。</span><span class="sxs-lookup"><span data-stu-id="0fc61-443">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="0fc61-444">這個工具會在所執行的前端（以及其他前端）上增加 CPU 和 IO 負荷，在此情況下，您的資料不會在執行該工具的前端所擁有。</span><span class="sxs-lookup"><span data-stu-id="0fc61-444">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="0fc61-445">我們建議您在前端不在 CPU 和 IO 負載（例如尖峰時間外）的情況下，runng 此工具。</span><span class="sxs-lookup"><span data-stu-id="0fc61-445">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="0fc61-446">其次，此工具可以2到3分鐘，匯入一個資料檔案。</span><span class="sxs-lookup"><span data-stu-id="0fc61-446">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="0fc61-447">在估計工具執行的時間長度時，請記住這一點。此工具所產生的詳細記錄檔預設會顯示在檔案存放區上。</span><span class="sxs-lookup"><span data-stu-id="0fc61-447">Keep this in mind when estimating how long tool will be running.The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="0fc61-448">如果沒有報告任何錯誤，請將它刪除，因為記錄檔可能是數十 MB 或更多。</span><span class="sxs-lookup"><span data-stu-id="0fc61-448">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

<span data-ttu-id="0fc61-449">![範例儲存伺服器事件記錄事件。](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "範例儲存伺服器事件記錄事件。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-449">![Sample Storage Server event log events.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Sample Storage Server event log events.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="0fc61-450">需求</span><span class="sxs-lookup"><span data-stu-id="0fc61-450">Requirements</span></span>

<span data-ttu-id="0fc61-451">安裝 Lync Server 2013、資源套件工具。</span><span class="sxs-lookup"><span data-stu-id="0fc61-451">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="0fc61-452">此工具會在安裝了 Lync Server 和 Lync Server 管理命令介面的已加入網域的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="0fc61-452">The tool runs on domain-joined machines where Lync Server and Lync Server Management Shell are installed.</span></span> <span data-ttu-id="0fc61-453">此工具會使用來自管理命令介面的 Cmdlet 來找出池中的所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="0fc61-453">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="0fc61-454">其次，您必須從已安裝**RtcLocal**資料庫的池中的電腦執行該工具。</span><span class="sxs-lookup"><span data-stu-id="0fc61-454">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="0fc61-455">此資料庫是由工具用來檢索池子的 WEBSERVICE 檔案共用位置。此外，在使用此工具之前，每個前端伺服器必須先在每個前端伺服器上使用**enable-PSRemoting**啟用 Windows PowerShell 遠端作業，以及執行該工具的電腦。</span><span class="sxs-lookup"><span data-stu-id="0fc61-455">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="0fc61-456">否則，此工具的遠端 Windows PowerShell 命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="0fc61-456">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="0fc61-457">完成後，就可以在池中的所有前端伺服器上關閉 Windows PowerShell 遠端處理功能。</span><span class="sxs-lookup"><span data-stu-id="0fc61-457">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="0fc61-458">最後，開啟此工具的帳戶或憑證必須擁有其在其上執行這個工具的 [webservice 檔案共用] 的 [讀取/寫入] 許可權。</span><span class="sxs-lookup"><span data-stu-id="0fc61-458">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="0fc61-459">否則，該工具會因 IO 許可權錯誤而失敗。</span><span class="sxs-lookup"><span data-stu-id="0fc61-459">Otherwise the tool will fail with IO Permission errors.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0fc61-460">在 Windows Server 2012 上，Windows PowerShell Remoting 預設為啟用，但在 Windows Server 2008 作業系統上則無法使用。</span><span class="sxs-lookup"><span data-stu-id="0fc61-460">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="0fc61-461">範例</span><span class="sxs-lookup"><span data-stu-id="0fc61-461">Examples</span></span>

    >  C:\StorageService>ImportStorageServiceData.exe
    Description:
    This tool will re-import Storage Service (LYSS) flushed queue data back in.  For a pool: you are required to run this tool on a machine inside the pool which has the Lync Server Management Shell installed.  Additionally, all front end machines need to have Windows Powershell Remoting enabled before executing this tool by executing Enable-PSRemoting.  Also, please ensure that all Storage Service instance DB Size are at the 'Normal' level (verify this by viewing Eventlog events). Otherwise re-importing may cause data to be flushed out again if any Storage Service instance DB size level goes above 'Normal'.
    Usage: Default behavior is to Import data from web service file share as well as any files on all Front End machines in pool.
    Additional Options:
    -Verbose                    : Turn verbose output on.
    
    -StorageServiceHostName     : Host Name of Storage Service WCF endpoint.  ( Default=localhost netnamedpipe binding. )
                                        
    -FileSharePath              : Import only all data from just under the UNC path specified.
    
    ActivityID: cc3b62ff-bb66-4e61-a6e2-96cb3626315c. <-- Use this to correlate with StorageService trace logs if troubleshooting.
    Type Server name (TCP binding) or press <enter> for localhost (NamePipe binding):
    Using NetNamedPipeBinding...
    OnTopologyChanged Event received
    Web Service File Share: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService
    
    Front Ends:
    server.vdomain.com
    server2.vdomain.com
    server1.vdomain.com
    server3.vdomain.com
    Looking under directory: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService for exported data.
    # Files found: 8
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    Items deserialized: 20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml
    
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d
    3832e4__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c
    86684d3832e4__0.xml
    
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml
    
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server2.vdom
    ain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42
    287dd6__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2
    b46a42287dd6__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml
    
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=1
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15
    d251e6__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759
    e08a15d251e6__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=1
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346949ff8
    17c220__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346
    949ff817c220__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml: succeeded: 20, failed: 0
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml
    
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=20
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be6
    6d5317__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876
    749be66d5317__0.xml
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml: succeeded: 20, failed: 0
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=20
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda
    86b565__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4
    657eda86b565__0.xml
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml: succeeded: 20, failed: 0
    All files have been imported into Storage Service for path: \\dc.vdomain.com\OcsFileStore\co1-WebSer
    vices-1\StorageService
    Importing files for: server.vdomain.com
    No files founds.
    Importing files for: server2.vdomain.com
    No files founds.
    Importing files for: server1.vdomain.com
    No files founds.
    Importing files for: server3.vdomain.com
    No files founds.
    Writing log: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\ImportStorageServiceData
    Log20120910_1609SS
    Tool has finished execution.
    >  C:\StorageService>

</div>

</div>

<div>

## <a name="lcssync"></a><span data-ttu-id="0fc61-462">LCSSync</span><span class="sxs-lookup"><span data-stu-id="0fc61-462">LCSSync</span></span>

<span data-ttu-id="0fc61-463">LCSSync 工具可協助您在多目錄林環境中部署 Lync Server 2013 通訊軟體。</span><span class="sxs-lookup"><span data-stu-id="0fc61-463">The LCSSync tool helps to deploy Lync Server 2013 communications software in a multi-forest environment.</span></span> <span data-ttu-id="0fc61-464">這個工具是用來將來自不同使用者目錄林的使用者和群組，作為 Active Directory 網域服務連絡人物件與安裝 Lync Server 2013 的中央林同步處理。</span><span class="sxs-lookup"><span data-stu-id="0fc61-464">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Lync Server 2013 is installed.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="0fc61-465">描述</span><span class="sxs-lookup"><span data-stu-id="0fc61-465">Description</span></span>

<span data-ttu-id="0fc61-466">LCSSync 會使用中央林中已同步處理的 Active Directory 網域服務連絡人物件來啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="0fc61-466">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Lync Server.</span></span> <span data-ttu-id="0fc61-467">若要提供單一登入，主要使用者帳戶必須對應到 Lync Server 2013 的中央林中的 Active Directory 網域服務連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="0fc61-467">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Lync Server 2013.</span></span> <span data-ttu-id="0fc61-468">此工具可協助執行該對應。</span><span class="sxs-lookup"><span data-stu-id="0fc61-468">This tool helps perform that mapping.</span></span> <span data-ttu-id="0fc61-469">此工具提供範本，可用於在 Microsoft 身分識別整合伺服器中建立管理代理程式。</span><span class="sxs-lookup"><span data-stu-id="0fc61-469">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="0fc61-470">總結</span><span class="sxs-lookup"><span data-stu-id="0fc61-470">Summary</span></span>

<span data-ttu-id="0fc61-471">LCSSync 工具可協助您在多目錄林環境中部署 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="0fc61-471">The LCSSync tool helps to deploy Lync Server in a multi-forest environment.</span></span>

</div>

</div>

<div>

## <a name="lookupuserconsole"></a><span data-ttu-id="0fc61-472">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="0fc61-472">LookupUserConsole</span></span>

<span data-ttu-id="0fc61-473">LookupUserConsole 工具會顯示特定使用者的內部 Lync Server 路由資訊。</span><span class="sxs-lookup"><span data-stu-id="0fc61-473">The LookupUserConsole tool displays internal Lync Server routing information about specific users.</span></span> <span data-ttu-id="0fc61-474">在診斷部署和路由問題時，Microsoft 支援個人資訊可能會很有用。</span><span class="sxs-lookup"><span data-stu-id="0fc61-474">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="0fc61-475">描述</span><span class="sxs-lookup"><span data-stu-id="0fc61-475">Description</span></span>

<span data-ttu-id="0fc61-476">執行 LookupUserConsole 會開啟一個接受 SIP 位址的命令提示字元，並嘗試顯示與它們相關的內部 Lync Server 路由資訊。</span><span class="sxs-lookup"><span data-stu-id="0fc61-476">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Lync Server routing information relating them.</span></span> <span data-ttu-id="0fc61-477">輸入**exit**以結束 LookupUserConsole 工具。</span><span class="sxs-lookup"><span data-stu-id="0fc61-477">Type **exit** to quit the LookupUserConsole tool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="0fc61-478">需求</span><span class="sxs-lookup"><span data-stu-id="0fc61-478">Requirements</span></span>

<span data-ttu-id="0fc61-479">安裝 Lync Server 2013、資源套件工具。</span><span class="sxs-lookup"><span data-stu-id="0fc61-479">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="0fc61-480">此工具會在安裝 Lync Server 的已加入網域的電腦上執行</span><span class="sxs-lookup"><span data-stu-id="0fc61-480">The tool runs on domain-joined machines where Lync Server is installed</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="0fc61-481">範例</span><span class="sxs-lookup"><span data-stu-id="0fc61-481">Examples</span></span>

<span data-ttu-id="0fc61-482">C：\\Program Files\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="0fc61-482">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole.exe</span></span>

    > sip:john.doe@vdomain.com
    
      Execution time (ms):                            171.094
      Exeuction result:                               Success
      SIP URI:                                        sip:john.doe@vdomain.com
      User info:
        SID:                                          S-1-5-21-2831376166-29632525...    Display name:                                     John Doe
        Grouping ID:                                  00000000-0000-0000-0000-...
        Line URI:                                     <null>
        Policy assignment:                            TenantId={00000000--0000-000....
        SIP enabled:                                  True
        UC enabled:                                   False
        Tenant ID:                                    00000000-0000-0000-0000-...  Cluster info:
        Active cluster:                               pool0.vdomain.com
        Backup registrar cluster:                     <null>
        Deployment location:                          <null>
        Home Front-End FQDN:                          SERVER.vdomain.com
        Primary Registrar cluster:                    pool0.vdomain.com
        Remote Director external SIP FQDN:            <null>
        Remote Director internal SIP FQDN:            <null>
        Remote Director Web FQDN:                     <null>
        Routing group ID:                             4501e04e-ae48-5605-9346...
        Service tag ID:                               1266953005
        User Front-End resolved:                      True
        User in local forest:                         True
        User in remote forest:                        False
        User in split domain:                         False
        User-Services cluster:                        pool0.vdomain.com
    
    > sip:nouser@vdomain.com
    
      Execution time (ms):                            948.7574
      Exeuction result:                               UserDoesNotExist
    
    > exit

</div>

</div>

<div>

## <a name="msturnping"></a><span data-ttu-id="0fc61-483">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="0fc61-483">MsTurnPing</span></span>

<span data-ttu-id="0fc61-484">MSTurnPing 工具可讓 Microsoft Lync Server 2013 通訊軟體的管理員檢查執行音訊/視頻邊緣和音訊/視頻驗證服務的伺服器狀態，以及在拓撲中執行頻寬原則服務的伺服器。</span><span class="sxs-lookup"><span data-stu-id="0fc61-484">The MSTurnPing tool allows an administrator of Microsoft Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="0fc61-485">描述</span><span class="sxs-lookup"><span data-stu-id="0fc61-485">Description</span></span>

<span data-ttu-id="0fc61-486">MSTurnPing 工具可讓 Lync Server 2013 通訊軟體的管理員檢查執行音訊/視頻邊緣和音訊/視頻驗證服務的伺服器狀態，以及在拓撲中執行頻寬原則服務的伺服器。</span><span class="sxs-lookup"><span data-stu-id="0fc61-486">The MSTurnPing tool allows an administrator of Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="0fc61-487">此工具可讓系統管理員執行下列測試：</span><span class="sxs-lookup"><span data-stu-id="0fc61-487">The tool allows the administrator to perform the following tests:</span></span>

1.  <span data-ttu-id="0fc61-488">A/V 邊緣伺服器測試：此工具會執行下列動作，針對拓撲中的所有 A/V 邊緣伺服器執行測試：</span><span class="sxs-lookup"><span data-stu-id="0fc61-488">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="0fc61-489">確認 Lync Server 音訊/視頻驗證服務已啟動，且可以發出適當的認證。</span><span class="sxs-lookup"><span data-stu-id="0fc61-489">Verifying that the Lync Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="0fc61-490">確認 Lync Server 音訊/視頻邊緣服務已啟動，且可以成功地在外部邊緣上配置資源。</span><span class="sxs-lookup"><span data-stu-id="0fc61-490">Verifying that the Lync Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2.  <span data-ttu-id="0fc61-491">頻寬原則服務測試：此工具會針對執行拓撲中的頻寬原則服務的所有伺服器執行測試，方法如下：</span><span class="sxs-lookup"><span data-stu-id="0fc61-491">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="0fc61-492">驗證 Lync Server 頻寬原則服務（驗證）是否已啟動，並可能發出適當的認證。</span><span class="sxs-lookup"><span data-stu-id="0fc61-492">Verifying that the Lync Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="0fc61-493">驗證 Lync Server 頻寬原則服務（核心）已啟動，且可以成功執行頻寬檢查。</span><span class="sxs-lookup"><span data-stu-id="0fc61-493">Verifying that the Lync Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="0fc61-494">此工具必須從屬於拓撲的電腦執行，且已安裝本機存儲區。</span><span class="sxs-lookup"><span data-stu-id="0fc61-494">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="0fc61-495">收</span><span class="sxs-lookup"><span data-stu-id="0fc61-495">Output</span></span>

<span data-ttu-id="0fc61-496">此工具會輸出每個作業的結果。</span><span class="sxs-lookup"><span data-stu-id="0fc61-496">The tool outputs the results of each of the operations.</span></span>

  - <span data-ttu-id="0fc61-497">如果執行**AudioVideoEdgeServer**測試，則工具輸出如下：</span><span class="sxs-lookup"><span data-stu-id="0fc61-497">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="0fc61-498">在拓撲中提供 Lync Server 音訊/視頻驗證服務之電腦的測試結果</span><span class="sxs-lookup"><span data-stu-id="0fc61-498">The test results of the computers that provide the Lync Server Audio/Video Authentication service in the topology</span></span>
    
      - <span data-ttu-id="0fc61-499">在拓撲中提供 Lync Server 音訊/視頻邊緣服務的電腦測試結果</span><span class="sxs-lookup"><span data-stu-id="0fc61-499">The test results of the computers that provide the Lync Server Audio/Video Edge service in the topology</span></span>

  - <span data-ttu-id="0fc61-500">如果執行**BandwidthPolicyServer**測試，則工具輸出如下：</span><span class="sxs-lookup"><span data-stu-id="0fc61-500">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="0fc61-501">在拓撲中提供 Lync Server 頻寬原則服務（驗證）的電腦測試結果</span><span class="sxs-lookup"><span data-stu-id="0fc61-501">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Authentication) in the topology</span></span>
    
      - <span data-ttu-id="0fc61-502">在拓撲中提供 Lync Server 頻寬原則服務（Core）之電腦的測試結果</span><span class="sxs-lookup"><span data-stu-id="0fc61-502">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Core) in the topology</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="0fc61-503">需求</span><span class="sxs-lookup"><span data-stu-id="0fc61-503">Requirements</span></span>

  - <span data-ttu-id="0fc61-504">此工具必須從拓撲中的電腦執行，且具有本機存放區。</span><span class="sxs-lookup"><span data-stu-id="0fc61-504">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

  - <span data-ttu-id="0fc61-505">此工具必須以擁有本機存放區存取權的管理員身分執行。</span><span class="sxs-lookup"><span data-stu-id="0fc61-505">The tool must be run as an administrator who has access to the local store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="0fc61-506">範例</span><span class="sxs-lookup"><span data-stu-id="0fc61-506">Examples</span></span>

<span data-ttu-id="0fc61-507">下列是工具輸入的範例。</span><span class="sxs-lookup"><span data-stu-id="0fc61-507">The following is an example of the tool input.</span></span>

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a><span data-ttu-id="0fc61-508">總結</span><span class="sxs-lookup"><span data-stu-id="0fc61-508">Summary</span></span>

<span data-ttu-id="0fc61-509">此工具可能是 Lync Server 2013 系統管理員要檢查執行音訊/視頻和頻寬原則服務之伺服器狀態的重要資源。</span><span class="sxs-lookup"><span data-stu-id="0fc61-509">This tool can be a valuable resource to Lync Server 2013 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a><span data-ttu-id="0fc61-510">網路設定檢視器</span><span class="sxs-lookup"><span data-stu-id="0fc61-510">Network Configuration Viewer</span></span>

<span data-ttu-id="0fc61-511">Microsoft Lync Server 2013 通訊軟體系統管理員可以使用網路設定檢視器來查看已設定為允許即時通訊會話（例如語音或您）的企業的通話許可控制（CAC）網路拓撲。根據指定的頻寬容量進行的視頻通話。</span><span class="sxs-lookup"><span data-stu-id="0fc61-511">Network Configuration Viewer can be used by Microsoft Lync Server 2013 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="0fc61-512">Lync Server 2013 系統管理員會定義 CAC 原則，這些原則是由使用 Lync Server 2013 安裝的頻寬原則服務所強制執行。</span><span class="sxs-lookup"><span data-stu-id="0fc61-512">Lync Server 2013 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Lync Server 2013.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="0fc61-513">描述</span><span class="sxs-lookup"><span data-stu-id="0fc61-513">Description</span></span>

<span data-ttu-id="0fc61-514">網路設定檢視器（NetworkConfigurationViewer）可讓系統管理員執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="0fc61-514">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

  - <span data-ttu-id="0fc61-515">從 Lync Server 2013 部署以圖形化格式載入並查看 CAC 網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="0fc61-515">Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format.</span></span>

  - <span data-ttu-id="0fc61-516">從頻寬原則伺服器記錄檔（以圖形化格式）載入和查看 CAC 網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="0fc61-516">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

  - <span data-ttu-id="0fc61-517">將 CAC 網路拓撲儲存並儲存在磁片上的 XML 格式中。</span><span class="sxs-lookup"><span data-stu-id="0fc61-517">Save and store CAC network topology in an XML format on the disk.</span></span>

  - <span data-ttu-id="0fc61-518">以 JPG 或 BMP 格式儲存及儲存 CAC 網路拓撲圖表。</span><span class="sxs-lookup"><span data-stu-id="0fc61-518">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

  - <span data-ttu-id="0fc61-519">查看 CAC 網路拓朴配置資料。</span><span class="sxs-lookup"><span data-stu-id="0fc61-519">View CAC network topology configuration data.</span></span>

  - <span data-ttu-id="0fc61-520">以樹狀檢視樣式查看 CAC 網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="0fc61-520">View CAC network topology in a tree-view style.</span></span>

  - <span data-ttu-id="0fc61-521">定義 CAC 網路拓撲連結的自訂連接器（例如，點對點、區域對區域及網站間連結）。</span><span class="sxs-lookup"><span data-stu-id="0fc61-521">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

  - <span data-ttu-id="0fc61-522">查看 CAC 網路拓撲網站資訊、區域資訊，以及已置備的頻寬原則和網路連結。</span><span class="sxs-lookup"><span data-stu-id="0fc61-522">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="0fc61-523">特殊</span><span class="sxs-lookup"><span data-stu-id="0fc61-523">Purpose</span></span>

<span data-ttu-id="0fc61-524">在圖形介面中，查看企業版 CAC 網路拓撲連結。</span><span class="sxs-lookup"><span data-stu-id="0fc61-524">View enterprise CAC network topology links in a graphical interface.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="0fc61-525">範例</span><span class="sxs-lookup"><span data-stu-id="0fc61-525">Examples</span></span>

<span data-ttu-id="0fc61-526">**從 Lync Server 2013 部署以圖形格式載入及查看 CAC 網路拓朴：** Lync Server 2013 系統管理員可以使用 [**下載網路**設定] 選項，在任何 Lync server 2013 電腦上載入並查看 CAC 網路拓撲設定，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="0fc61-526">**Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format:** Lync Server 2013 administrators can load and view CAC network topology configuration on any Lync Server 2013 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="0fc61-527">在沒有連線到 Lync 設定存放區的電腦上部署時，該工具將無法下載或查看此類設定。</span><span class="sxs-lookup"><span data-stu-id="0fc61-527">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Lync configuration store.</span></span>

<span data-ttu-id="0fc61-528">![下載網路設定。](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "下載網路設定。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-528">![Downloading the network configuration.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Downloading the network configuration.")</span></span>

<span data-ttu-id="0fc61-529">**從頻寬原則伺服器記錄檔，以圖形格式載入和查看 CAC 網路拓朴：** Lync Server 2013 頻寬原則伺服器會將 CAC 網路拓朴儲存為 Lync Server 2013 檔案共用位置下的記錄機制的一部分。</span><span class="sxs-lookup"><span data-stu-id="0fc61-529">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Lync Server 2013 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Lync Server 2013 file share location.</span></span> <span data-ttu-id="0fc61-530">Lync Server 系統管理員可以使用 [**開啟網路**設定] 選項，以圖形格式來查看此類檔案，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0fc61-530">Lync Server administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

<span data-ttu-id="0fc61-531">![開啟頻寬原則伺服器記錄檔。](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "開啟頻寬原則伺服器記錄檔。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-531">![Opening a Bandwidth Policy Server log file.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Opening a Bandwidth Policy Server log file.")</span></span>

<span data-ttu-id="0fc61-532">將 CAC 網路拓撲儲存並儲存在磁片上的 XML 格式： Lync Server 2013 系統管理員可以使用 [**儲存網路設定複本**] 選項，以 xml 格式儲存 cac 網路拓撲設定檔，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0fc61-532">Save and store CAC network topology in an XML format on the disk: Lync Server 2013 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="0fc61-533">然後，儲存的設定檔案可以在離線時使用，以進行圖形化查看。</span><span class="sxs-lookup"><span data-stu-id="0fc61-533">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

<span data-ttu-id="0fc61-534">![將網路設定儲存為 XML 檔案。](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "將網路設定儲存為 XML 檔案。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-534">![Saving the network configuration as an XML file.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Saving the network configuration as an XML file.")</span></span>

<span data-ttu-id="0fc61-535">以 JPG 或 BMP 格式儲存及儲存 CAC 網路拓撲圖： Lync Server 2013 系統管理員可以使用 [**另存網路設定圖表為圖片**] 選項，將 cac 網路拓撲設定儲存為圖形格式（JPG 和 BMP 檔案格式），如下所示。</span><span class="sxs-lookup"><span data-stu-id="0fc61-535">Save and Store CAC network topology diagram in JPG or BMP format: Lync Server 2013 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

<span data-ttu-id="0fc61-536">將![網路設定儲存為圖片。]將(images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "網路設定儲存為圖片。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-536">![Saving the network configuration as a picture.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Saving the network configuration as a picture.")</span></span>

<span data-ttu-id="0fc61-537">**查看 CAC 網路拓朴配置資料：** Lync Server 2013 系統管理員可以使用 [查看網路設定資料] 選項，以文字格式來查看相關的網路設定資料，例如網路區域、網路網站、頻寬設定檔，以及網站子網 IP 位址（如下所示）。</span><span class="sxs-lookup"><span data-stu-id="0fc61-537">**View CAC network topology configuration data:** Lync Server 2013 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

<span data-ttu-id="0fc61-538">![查看網路設定資料。](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "查看網路設定資料。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-538">![Viewing network configuration data.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Viewing network configuration data.")</span></span>

<span data-ttu-id="0fc61-539">**以樹狀檢視樣式查看 CAC 網路拓撲：** Lync Server 2013 系統管理員可以使用工具視窗左側的 [控制台]，以圖形樹狀結構視圖樣式來查看相關的網路設定資料，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0fc61-539">**View CAC network topology in a tree-view style:** Lync Server 2013 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

<span data-ttu-id="0fc61-540">![在樹狀結構視圖中查看網路設定資料。](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "在樹狀結構視圖中查看網路設定資料。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-540">![Viewing network configuration data in a tree-view.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Viewing network configuration data in a tree-view.")</span></span>

<span data-ttu-id="0fc61-541">**定義 CAC 網路拓撲連結的自訂連接器（例如點對點、區域對區域及網站到網站連結）：** Lync Server 2013 系統管理員可以使用 [設定] 選項來定義 CAC 網路設定 WAN 連結的自訂圖形連接器，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0fc61-541">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Lync Server 2013 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="0fc61-542">這有助於區分網路設定中提供的各種類型的網路連結。</span><span class="sxs-lookup"><span data-stu-id="0fc61-542">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

<span data-ttu-id="0fc61-543">![定義 cac 網路拓朴的自訂連接器](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "定義 cac 網路拓朴的自訂連接器")</span><span class="sxs-lookup"><span data-stu-id="0fc61-543">![Define custom connectors for CAC network topology](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Define custom connectors for CAC network topology")</span></span>

<span data-ttu-id="0fc61-544">**查看 CAC 網路拓撲網站資訊、區域資訊，以及已置備的頻寬原則：** Lync Server 2013 系統管理員可以使用下列選項，查看相關的 CAC 網路區域資訊、網站資訊和 CAC 頻寬提供資訊。</span><span class="sxs-lookup"><span data-stu-id="0fc61-544">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Lync Server 2013 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="0fc61-545">（例如，按一下 [網路區域] 或 [網路網站] 物件中的 [**資訊**]。）</span><span class="sxs-lookup"><span data-stu-id="0fc61-545">(For example, click **Info** in a network region or network site object.)</span></span>

<span data-ttu-id="0fc61-546">![為您的網路定義自訂連接器。](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "為您的網路定義自訂連接器。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-546">![Defining custom connectors for your network.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Defining custom connectors for your network.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="0fc61-547">總結</span><span class="sxs-lookup"><span data-stu-id="0fc61-547">Summary</span></span>

<span data-ttu-id="0fc61-548">此工具可以是 Lync Server 2013 系統管理員的重要資源，想要以圖形式格式來查看其部署的 CAC 網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="0fc61-548">This tool can be a valuable resource to Lync Server 2013 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

</div>

</div>

<div>

## <a name="response-group-agent-live"></a><span data-ttu-id="0fc61-549">回應群組代理程式即時</span><span class="sxs-lookup"><span data-stu-id="0fc61-549">Response Group Agent Live</span></span>

<span data-ttu-id="0fc61-550">回應群組應用程式讓代理能夠使用其內建的 Web 服務存取有用的即時資訊。</span><span class="sxs-lookup"><span data-stu-id="0fc61-550">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="0fc61-551">遺憾的是，在應用程式以外不提供此資料的圖形視圖。</span><span class="sxs-lookup"><span data-stu-id="0fc61-551">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="0fc61-552">回應群組代理程式動態資源套件工具可提供簡單且圖形化的方式來存取此資訊，並利用即時 Microsoft Lync 2013 通訊軟體資訊（例如其他代理的目前狀態）來加強這項問題的解決。</span><span class="sxs-lookup"><span data-stu-id="0fc61-552">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Microsoft Lync 2013 communications software information such as the presence of other agents.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="0fc61-553">描述</span><span class="sxs-lookup"><span data-stu-id="0fc61-553">Description</span></span>

<span data-ttu-id="0fc61-554">回應群組代理程式活是一種 Windows 應用程式，可提供登入和登出功能，以及一些即時資訊（例如，群組成員資格和目前的呼叫數量）到回應群組代理程式。</span><span class="sxs-lookup"><span data-stu-id="0fc61-554">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="0fc61-555">它應該是 [代理群組] 頁面的增強版本（可從 Lync 2013 存取）。</span><span class="sxs-lookup"><span data-stu-id="0fc61-555">It is meant to be an enhanced version of the Agent Groups page (accessible from Lync 2013.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="0fc61-556">特殊</span><span class="sxs-lookup"><span data-stu-id="0fc61-556">Purpose</span></span>

<span data-ttu-id="0fc61-557">回應群組應用程式會列隊來電，然後將它們路由到 [代理群組]。</span><span class="sxs-lookup"><span data-stu-id="0fc61-557">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="0fc61-558">若要對服務的呼叫作出明智的決定，agent 可以存取其代理群組的即時資訊，例如，還有哪些其他代理程式，以及每個佇列中等候多少通話。</span><span class="sxs-lookup"><span data-stu-id="0fc61-558">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="0fc61-559">此資訊最初隻能透過回應群組服務存取，以直觀的方式提供給回應群組代理程式。</span><span class="sxs-lookup"><span data-stu-id="0fc61-559">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

<div>

## <a name="features"></a><span data-ttu-id="0fc61-560">Features</span><span class="sxs-lookup"><span data-stu-id="0fc61-560">Features</span></span>

<span data-ttu-id="0fc61-561">回應群組代理程式動態工具是在回應群組服務和 Microsoft Lync 2013 SDK 上建立。</span><span class="sxs-lookup"><span data-stu-id="0fc61-561">The Response Group Agent Live tool is built on the Response Group service and the Microsoft Lync 2013 SDK.</span></span> <span data-ttu-id="0fc61-562">它提供回應群組的代理人：回應群組服務提供的資訊和功能（例如群組成員資格、其他代理程式的目前狀態，以及等待通話的次數）。</span><span class="sxs-lookup"><span data-stu-id="0fc61-562">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="0fc61-563">下圖說明回應群組代理程式的主要介面。</span><span class="sxs-lookup"><span data-stu-id="0fc61-563">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

<span data-ttu-id="0fc61-564">![[回應群組代理程式即時工具]。](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "[回應群組代理程式即時工具]。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-564">![The Response Group Agent Live tool.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "The Response Group Agent Live tool.")</span></span>

<span data-ttu-id="0fc61-565">下列三個主要功能適用于回應群組代理程式中的代理程式：</span><span class="sxs-lookup"><span data-stu-id="0fc61-565">The following three main features are available for agents in Response Group Agent Live:</span></span>

  - <span data-ttu-id="0fc61-566">登**入/取出：** 與 [代理群組] 頁面（可從 Lync 2013 存取）相反，回應群組代理程式即時只允許代理程式一次登入或登出所有的代理群組。</span><span class="sxs-lookup"><span data-stu-id="0fc61-566">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Lync 2013), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="0fc61-567">此應用程式提供三種快速代理程式登入或登出的方法：</span><span class="sxs-lookup"><span data-stu-id="0fc61-567">This application provides three quick ways for agents to sign in or out:</span></span>
    
      - <span data-ttu-id="0fc61-568">按一下應用程式內的 [登入/取出] （綠色和紅色）按鈕。</span><span class="sxs-lookup"><span data-stu-id="0fc61-568">Click the Sign-in/out (green and red) buttons within the application.</span></span>
    
      - <span data-ttu-id="0fc61-569">以滑鼠右鍵按一下系統工作列圖示，然後選取 [登入] 或 [登出]。</span><span class="sxs-lookup"><span data-stu-id="0fc61-569">Right-click the system tray icon, and select sign in or sign out.</span></span>
    
      - <span data-ttu-id="0fc61-570">使用可設定的鍵盤快速鍵。</span><span class="sxs-lookup"><span data-stu-id="0fc61-570">Using configurable keyboard shortcuts.</span></span>

  - <span data-ttu-id="0fc61-571">**群組成員資格：** 選取 [代理群組] 後，[回應群組代理程式即時] 會在右側窗格中顯示 [此群組中的 agent 清單]。</span><span class="sxs-lookup"><span data-stu-id="0fc61-571">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="0fc61-572">如果 Lync 2013 是在與此應用程式相同的電腦上執行，目前狀態資訊和連絡人卡片會顯示在回應群組代理程式中。</span><span class="sxs-lookup"><span data-stu-id="0fc61-572">If Lync 2013 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="0fc61-573">代理程式可以傳送 IM，或直接從該處呼叫其他的代理程式。</span><span class="sxs-lookup"><span data-stu-id="0fc61-573">Agents can send an IM or call other agents directly from there.</span></span>

  - <span data-ttu-id="0fc61-574">**即時統計資料：** 回應群組代理程式即時為所有代理群組提供即時統計資料。</span><span class="sxs-lookup"><span data-stu-id="0fc61-574">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="0fc61-575">更新頻率為1分鐘。</span><span class="sxs-lookup"><span data-stu-id="0fc61-575">The update frequency is one minute.</span></span> <span data-ttu-id="0fc61-576">當回應群組接聽來電時，會在組名旁加上目前已排隊通話的視覺指標。</span><span class="sxs-lookup"><span data-stu-id="0fc61-576">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="0fc61-577">將指標暫停在群組上也會顯示最長的等待時間。</span><span class="sxs-lookup"><span data-stu-id="0fc61-577">Pausing the pointer over a group also displays the longest waiting time.</span></span>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="0fc61-578">需求</span><span class="sxs-lookup"><span data-stu-id="0fc61-578">Requirements</span></span>

<span data-ttu-id="0fc61-579">回應群組代理程式即時需要 .NET Framework 4.0。</span><span class="sxs-lookup"><span data-stu-id="0fc61-579">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="0fc61-580">此外，若要充分利用目前狀態和連絡人卡片的功能，Lync 2013 必須安裝在本機（且正在執行）。</span><span class="sxs-lookup"><span data-stu-id="0fc61-580">In addition, to take advantage of the presence and contact card features, Lync 2013 must be installed locally (and be running).</span></span>

<div>

## <a name="configuration"></a><span data-ttu-id="0fc61-581">Configuration</span><span class="sxs-lookup"><span data-stu-id="0fc61-581">Configuration</span></span>

<span data-ttu-id="0fc61-582">您可以使用應用程式中的 [選項] 對話方塊，將回應群組代理程式即時自訂為個別的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="0fc61-582">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="0fc61-583">此外，管理員可以直接編輯 RGAgentLive 檔案的 defaultHostAddress 屬性，來定義預設的主機位址。</span><span class="sxs-lookup"><span data-stu-id="0fc61-583">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="0fc61-584">下圖說明代理程式可用來設定主機位址和快速鍵的 [選項] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="0fc61-584">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="0fc61-585">按一下主要介面右上方的 [選項] 按鈕，即可存取此對話方塊。</span><span class="sxs-lookup"><span data-stu-id="0fc61-585">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

<span data-ttu-id="0fc61-586">![[回應群組代理程式即時選項] 對話方塊。](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "[回應群組代理程式即時選項] 對話方塊。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-586">![The Response Group Agent Live Options dialog box.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "The Response Group Agent Live Options dialog box.")</span></span>

<span data-ttu-id="0fc61-587">在回應群組代理程式即時設定中，您可以自訂下列三個不同的設定：</span><span class="sxs-lookup"><span data-stu-id="0fc61-587">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

  - <span data-ttu-id="0fc61-588">主機位址：這通常是屬於代理的主池中的網頁池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="0fc61-588">Host address: This is typically the web pool FQDN belonging to the agent’s home pool.</span></span> <span data-ttu-id="0fc61-589">確切的回應群組服務位址會自動衍生於此資訊的背景中（透過在主機之後附加正確路徑）。</span><span class="sxs-lookup"><span data-stu-id="0fc61-589">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

  - <span data-ttu-id="0fc61-590">快速鍵：您可以自訂正確的登入/登出快速鍵。</span><span class="sxs-lookup"><span data-stu-id="0fc61-590">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="0fc61-591">唯一的限制是，兩個快速鍵都必須包含「Windows 標誌」金鑰（除了至少一個金鑰之外）。</span><span class="sxs-lookup"><span data-stu-id="0fc61-591">The only limitation is that both shortcuts must contain the “Windows Logo” key (in addition to at least another key).</span></span>

  - <span data-ttu-id="0fc61-592">從 Windows 開始：應用程式可以設定為使用 Windows 自動啟動。</span><span class="sxs-lookup"><span data-stu-id="0fc61-592">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="0fc61-593">範例</span><span class="sxs-lookup"><span data-stu-id="0fc61-593">Examples</span></span>

<span data-ttu-id="0fc61-594">下圖說明如何在右側窗格中，以滑鼠右鍵按一下連絡人，以呼叫或傳送 IM 給另一個代理程式。</span><span class="sxs-lookup"><span data-stu-id="0fc61-594">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

<span data-ttu-id="0fc61-595">![撥打電話或傳送即時消息。](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "撥打電話或傳送即時消息。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-595">![Making a call or sending an IM.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Making a call or sending an IM.")</span></span>

<span data-ttu-id="0fc61-596">下圖說明回應群組代理程式的即時顯示佇列中目前的通話數，以及所有這些來電間的最長等待時間。</span><span class="sxs-lookup"><span data-stu-id="0fc61-596">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

<span data-ttu-id="0fc61-597">![查看佇列資訊。](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "查看佇列資訊。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-597">![Viewing queue information.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Viewing queue information.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="0fc61-598">總結</span><span class="sxs-lookup"><span data-stu-id="0fc61-598">Summary</span></span>

<span data-ttu-id="0fc61-599">快速登入和登出、群組成員資格，以及基本的即時統計資料，只提供回應群組代理程式功能，且僅可在應用程式之外從回應群組服務存取。</span><span class="sxs-lookup"><span data-stu-id="0fc61-599">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="0fc61-600">使用 [回應群組代理程式即時資源套件] 工具，Lync 系統管理員可以為其代理提供 Windows 應用程式，讓他們能夠以更快速且圖形的方式執行工作。</span><span class="sxs-lookup"><span data-stu-id="0fc61-600">With the Response Group Agent Live Resource Kit tool, Lync administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

</div>

</div>

<div>

## <a name="sefautil"></a><span data-ttu-id="0fc61-601">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="0fc61-601">SEFAUtil</span></span>

<span data-ttu-id="0fc61-602">SEFAUtil （次要延伸功能啟用）是一種命令列工具，可讓 Microsoft Lync Server 2013 通訊軟體管理員與技術支援人員設定代理人響鈴、來電轉接、同時撥打，小組通話[設定] 和 [群組呼叫] 代表 Lync Server 2013 使用者。</span><span class="sxs-lookup"><span data-stu-id="0fc61-602">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Microsoft Lync Server 2013 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="0fc61-603">此工具也可讓系統管理員查詢針對特定使用者發佈的呼叫路由設定。SEFAUtil 工具可讓系統管理員自行啟用/停用/修改來電轉接或同時撥打給使用者。</span><span class="sxs-lookup"><span data-stu-id="0fc61-603">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="0fc61-604">系統管理員可以指定目標（以 SIP URI 的形式），或使用使用者已發佈的目標。</span><span class="sxs-lookup"><span data-stu-id="0fc61-604">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="0fc61-605">此工具也可讓系統管理員代表使用者新增或移除代理人或小組通話群組成員。此工具是在 Microsoft 整合通訊 Managed API （UCMA）3.0 上建立，且要求管理員在中央管理存儲區中建立信任的應用程式以進行 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="0fc61-605">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil</span></span>

<span data-ttu-id="0fc61-606">SEFAUtil （次要延伸功能啟用）可讓 Lync Server 2013 系統管理員和支援人員在 Lync Server 2013 使用者設定代理人響鈴、來電轉接、同時撥打、團隊通話設定和群組通話挑選.</span><span class="sxs-lookup"><span data-stu-id="0fc61-606">SEFAUtil (secondary extension feature activation) enables Lync Server 2013 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="0fc61-607">此工具也可讓系統管理員查詢針對特定使用者發佈的呼叫路由設定。</span><span class="sxs-lookup"><span data-stu-id="0fc61-607">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="0fc61-608">描述</span><span class="sxs-lookup"><span data-stu-id="0fc61-608">Description</span></span>

<span data-ttu-id="0fc61-609">目前的 SEFAUtil 版本只是一個命令列工具;沒有支援圖形使用者介面。</span><span class="sxs-lookup"><span data-stu-id="0fc61-609">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="0fc61-610">此工具是以 Microsoft 整合通訊管理 API （UCMA）3.0 為基礎。</span><span class="sxs-lookup"><span data-stu-id="0fc61-610">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="0fc61-611">此工具中的功能可讓系統管理員和支援人員執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="0fc61-611">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

  - <span data-ttu-id="0fc61-612">查看使用者的所有呼叫路由設定（包括來電轉接、委派、同時撥打、團隊通話和群組通話取貨）</span><span class="sxs-lookup"><span data-stu-id="0fc61-612">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

  - <span data-ttu-id="0fc61-613">啟用/停用/修改來電轉接設定（包括目的地和無應答計時器）</span><span class="sxs-lookup"><span data-stu-id="0fc61-613">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

  - <span data-ttu-id="0fc61-614">啟用/停用/修改來電轉接立即設定</span><span class="sxs-lookup"><span data-stu-id="0fc61-614">Enable/disable/modify call-forwarding immediate configurations</span></span>

  - <span data-ttu-id="0fc61-615">啟用/停用/修改委派設定</span><span class="sxs-lookup"><span data-stu-id="0fc61-615">Enable/disable/modify delegation settings</span></span>

  - <span data-ttu-id="0fc61-616">啟用/停用/修改小組通話群組設定</span><span class="sxs-lookup"><span data-stu-id="0fc61-616">Enable/disable/modify team-call group settings</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0fc61-617">Lync Server 2013 SEFAUtil 工具中的新功能</span><span class="sxs-lookup"><span data-stu-id="0fc61-617">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="0fc61-618">啟用/停用/修改同時震鈴設定（包括目的地）</span><span class="sxs-lookup"><span data-stu-id="0fc61-618">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0fc61-619">Lync Server 2013 SEFAUtil 工具中的新功能</span><span class="sxs-lookup"><span data-stu-id="0fc61-619">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="0fc61-620">啟用/停用/修改群組呼叫挑選設定</span><span class="sxs-lookup"><span data-stu-id="0fc61-620">Enable/disable/modify group call pickup settings</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="0fc61-621">Lync Server 2013 SEFAUtil 工具中的新功能</span><span class="sxs-lookup"><span data-stu-id="0fc61-621">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

<span data-ttu-id="0fc61-622">此工具有下列限制：</span><span class="sxs-lookup"><span data-stu-id="0fc61-622">This tool has the following limitations:</span></span>

  - <span data-ttu-id="0fc61-623">僅支援駐留在 Lync Server 池中的使用者</span><span class="sxs-lookup"><span data-stu-id="0fc61-623">Supported only for users homed in a Lync Server pool</span></span>

  - <span data-ttu-id="0fc61-624">不支援多個使用者的通話路由設定的大量編輯</span><span class="sxs-lookup"><span data-stu-id="0fc61-624">Bulk-edit of call routing settings for several users is not supported</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="0fc61-625">收</span><span class="sxs-lookup"><span data-stu-id="0fc61-625">Output</span></span>

<span data-ttu-id="0fc61-626">此工具的目前版本只會在命令提示字元視窗中提供輸出。</span><span class="sxs-lookup"><span data-stu-id="0fc61-626">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="0fc61-627">如需詳細資訊，請參閱本檔稍後的範例一節。</span><span class="sxs-lookup"><span data-stu-id="0fc61-627">For details, see the Examples section later in this document.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="0fc61-628">特殊</span><span class="sxs-lookup"><span data-stu-id="0fc61-628">Purpose</span></span>

<span data-ttu-id="0fc61-629">以下是可使用此工具的一些主要案例：</span><span class="sxs-lookup"><span data-stu-id="0fc61-629">Following are some of the key scenarios where this tool may be used:</span></span>

  - <span data-ttu-id="0fc61-630">Bob 是一個主管，並已移至 Lync Server 電話。</span><span class="sxs-lookup"><span data-stu-id="0fc61-630">Bob is an executive and has been moved to Lync Server telephony.</span></span> <span data-ttu-id="0fc61-631">他在現有的 PBX 系統上擁有委派。</span><span class="sxs-lookup"><span data-stu-id="0fc61-631">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="0fc61-632">當您移至 Lync 時，系統管理員可以設定 Bob 的路由，以反映其預先存在的委派設定。</span><span class="sxs-lookup"><span data-stu-id="0fc61-632">As part of the move to Lync, the administrator is able to configure Bob’s routing to reflect his pre-existing delegation configuration.</span></span>

  - <span data-ttu-id="0fc61-633">劉愛琳正在旅行，意識到她期待從她的一位客戶進行重要的通話。</span><span class="sxs-lookup"><span data-stu-id="0fc61-633">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="0fc61-634">不過，她是在賓館中，沒有電腦的存取權。</span><span class="sxs-lookup"><span data-stu-id="0fc61-634">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="0fc61-635">她撥打電話給支援人員，並要求他們轉寄給自己的手機電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0fc61-635">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="0fc61-636">技術支援人員可以代表自己進行設定。</span><span class="sxs-lookup"><span data-stu-id="0fc61-636">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

  - <span data-ttu-id="0fc61-637">Joe 在工作時，來電會傳送給他的行動電話語音信箱;不過，在大多數其他位置，情況看起來都能正常運作。</span><span class="sxs-lookup"><span data-stu-id="0fc61-637">Joe’s calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="0fc61-638">技術支援專家可以查看 Joe 的路線配置，並探索李先生已將來電設定為行動電話。</span><span class="sxs-lookup"><span data-stu-id="0fc61-638">The helpdesk technician is able to view Joe’s routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="0fc61-639">技術人員會在其辦公室向 Joe 提出有關行動裝置的詳細資料，並能判斷同時撥打的規則，在網路覆蓋品質較差的情況下，也會導致來電移至 Joe 的行動電話語音。</span><span class="sxs-lookup"><span data-stu-id="0fc61-639">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe’s mobile voicemail when his network coverage is poor.</span></span>

  - <span data-ttu-id="0fc61-640">Mike 是 Contoso 中的新員工，他正在加入一個新的小組，所有成員都是針對小組通話設定，當您為 Microsoft Lync 啟用時，系統管理員可以將其小組通話群組設定設為包含所有新的小組成員，此外，系統管理員會將 Mike 新增為小組中每個成員的小組通話群組成員。</span><span class="sxs-lookup"><span data-stu-id="0fc61-640">Mike is a new employee at Contoso and he’s joining a new team on which all members are configured for team-call, when being enabled for Microsoft Lync, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

  - <span data-ttu-id="0fc61-641">在 Contoso，在人力資源部門中的客戶服務慣例是在第一次呼叫後為所有的呼叫者提供個人服務。</span><span class="sxs-lookup"><span data-stu-id="0fc61-641">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="0fc61-642">假設整個部門中的所有成員都非常接近彼此，所以使用小組通話同時撥打所有電話，就會對小組造成很大的中斷。</span><span class="sxs-lookup"><span data-stu-id="0fc61-642">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="0fc61-643">若要在不中斷團隊成員的情況下提供最佳服務，Lync 管理員會利用群組呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="0fc61-643">To provide the best service without disrupting the team members, the Lync administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="0fc61-644">系統管理員會將所有部門成員新增到裝貨群組，並向該部門傳達挑選群組的編號。</span><span class="sxs-lookup"><span data-stu-id="0fc61-644">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="0fc61-645">如果 Samantha 不在她的辦公桌中，Joe 會通知她的電話響，他接著接聽她的通話。</span><span class="sxs-lookup"><span data-stu-id="0fc61-645">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="0fc61-646">需求</span><span class="sxs-lookup"><span data-stu-id="0fc61-646">Requirements</span></span>

<span data-ttu-id="0fc61-647">SEFAUtil 工具只能在屬於受信任的應用程式池的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="0fc61-647">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="0fc61-648">UCMA 3.0 必須安裝在該電腦上。</span><span class="sxs-lookup"><span data-stu-id="0fc61-648">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="0fc61-649">若要執行該工具，必須在該池中建立具有 SEFAUtil 應用程式識別碼的新信任應用程式。</span><span class="sxs-lookup"><span data-stu-id="0fc61-649">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

<span data-ttu-id="0fc61-650">**為 SEFAUtil 工具建立新的信任應用程式**</span><span class="sxs-lookup"><span data-stu-id="0fc61-650">**Creating a new Trusted Application for the SEFAUtil tool**</span></span>

1.  <span data-ttu-id="0fc61-651">SEFAUTil 工具只能在屬於受信任的應用程式池的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="0fc61-651">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="0fc61-652">如有需要，您可以透過 Lync Server 管理命令介面（含下列 Cmdlet）來將文件庫新增為新的受信任的應用程式池：</span><span class="sxs-lookup"><span data-stu-id="0fc61-652">If needed, adding a pool as a new trusted application pool can be done via the Lync Server Management Shell with the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0fc61-653">UCMA 3.0 必須安裝在任何將用來執行 SEFAUtil 工具的電腦上。</span><span class="sxs-lookup"><span data-stu-id="0fc61-653">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

    
    </div>

2.  <span data-ttu-id="0fc61-654">受信任的應用程式必須在 SEFAUtil 工具的拓撲中定義。</span><span class="sxs-lookup"><span data-stu-id="0fc61-654">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="0fc61-655">若要將 SEFAUtil 定義為新的受信任的應用程式，請使用 Lync Server 管理命令介面，並執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0fc61-655">To define SEFAUtil as a new trusted application, use the Lync Server Management Shell and execute the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0fc61-656">如有需要，您可以使用不同的埠。</span><span class="sxs-lookup"><span data-stu-id="0fc61-656">A different port can be used if needed.</span></span>

    
    </div>

3.  <span data-ttu-id="0fc61-657">需要啟用拓撲變更。</span><span class="sxs-lookup"><span data-stu-id="0fc61-657">The topology changes need to be enabled.</span></span> <span data-ttu-id="0fc61-658">您可以執行下列 Cmdlet，透過 Lync Server Management Shell 來啟用拓撲變更：</span><span class="sxs-lookup"><span data-stu-id="0fc61-658">Enabling the topology changes can be done via the Lync Server Management Shell by executing the following cmdlet:</span></span>
    
        Enable-CsToplogy

4.  <span data-ttu-id="0fc61-659">如有需要，請在伺服器中安裝 Lync Server 2013 資源套件工具，用來執行 SEFAUtil 工具（伺服器必須是受信任的應用程式池的一部分）。</span><span class="sxs-lookup"><span data-stu-id="0fc61-659">If needed, install the Lync Server 2013 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5.  <span data-ttu-id="0fc61-660">驗證 SEFAUtil 是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="0fc61-660">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="0fc61-661">若要這樣做，請從具有系統管理員許可權的 windows 命令提示字元執行該工具，以在部署中顯示使用者的來電轉接設定。</span><span class="sxs-lookup"><span data-stu-id="0fc61-661">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="0fc61-662">根據預設，該工具會位於： ".。。\\Program Files\\Microsoft Lync Server 2013\\Reskit "。</span><span class="sxs-lookup"><span data-stu-id="0fc61-662">By default the tool will be located in: “…\\Program Files\\Microsoft Lync Server 2013\\Reskit”.</span></span> <span data-ttu-id="0fc61-663">若要顯示使用者的來電轉接設定，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="0fc61-663">To display the call forwarding settings of a user, use the following command:</span></span>
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    <span data-ttu-id="0fc61-664">隨即會顯示使用者的來電轉接設定。</span><span class="sxs-lookup"><span data-stu-id="0fc61-664">The call forwarding settings of the user should be displayed.</span></span>

<div>

## <a name="group-call-pickup"></a><span data-ttu-id="0fc61-665">群組來電接聽</span><span class="sxs-lookup"><span data-stu-id="0fc61-665">Group Call Pickup</span></span>

<span data-ttu-id="0fc61-666">[群組通話挑選] 需要 Lync Server 中的其他設定，才能完全啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="0fc61-666">Group Call Pickup requires additional configuration in Lync Server for the capability to be fully enabled.</span></span> <span data-ttu-id="0fc61-667">將拾取群組指派給使用者之前，請參閱群組通話產品檔，瞭解此功能的規劃與部署步驟。</span><span class="sxs-lookup"><span data-stu-id="0fc61-667">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="0fc61-668">範例</span><span class="sxs-lookup"><span data-stu-id="0fc61-668">Examples</span></span>

<div>

## <a name="display-current-call-handling-settings"></a><span data-ttu-id="0fc61-669">顯示目前的通話處理設定</span><span class="sxs-lookup"><span data-stu-id="0fc61-669">Display Current Call Handling Settings</span></span>

<span data-ttu-id="0fc61-670">下列命令會顯示使用者的通話處理。</span><span class="sxs-lookup"><span data-stu-id="0fc61-670">The following command displays the call handling for the user.</span></span> `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> <span data-ttu-id="0fc61-671">這個範例使用<STRONG>/server</STRONG>開關來指定要連線的 Lync 伺服器。</span><span class="sxs-lookup"><span data-stu-id="0fc61-671">This example uses the <STRONG>/server</STRONG> switch to specify the Lync Server to connect to.</span></span>



</div>

<span data-ttu-id="0fc61-672">**收**</span><span class="sxs-lookup"><span data-stu-id="0fc61-672">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="0fc61-673">將呼叫轉寄/無應答目的地</span><span class="sxs-lookup"><span data-stu-id="0fc61-673">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="0fc61-674">這個範例會將呼叫轉寄/沒有應答目的地和響鈴延遲設定。</span><span class="sxs-lookup"><span data-stu-id="0fc61-674">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="0fc61-675">此處未提供/server 開關;SEFAUtil 嘗試自動探索 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="0fc61-675">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Lync Server.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

<span data-ttu-id="0fc61-676">**收**</span><span class="sxs-lookup"><span data-stu-id="0fc61-676">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="0fc61-677">立即啟用來電轉接</span><span class="sxs-lookup"><span data-stu-id="0fc61-677">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="0fc61-678">這個範例會立即啟用來電轉接給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="0fc61-678">This example immediately enables call-forwarding to another user.</span></span>

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

<span data-ttu-id="0fc61-679">**收**</span><span class="sxs-lookup"><span data-stu-id="0fc61-679">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="0fc61-680">立即停用來電轉接</span><span class="sxs-lookup"><span data-stu-id="0fc61-680">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="0fc61-681">這個範例會立即停用 [來電轉接]。</span><span class="sxs-lookup"><span data-stu-id="0fc61-681">This example immediately disables call forwarding.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

<span data-ttu-id="0fc61-682">**收**</span><span class="sxs-lookup"><span data-stu-id="0fc61-682">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="0fc61-683">將使用者新增為代理人，並設定同時撥打代理人</span><span class="sxs-lookup"><span data-stu-id="0fc61-683">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="0fc61-684">這個範例會將使用者新增為代理人，並設定同時撥打的代理人。</span><span class="sxs-lookup"><span data-stu-id="0fc61-684">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

<span data-ttu-id="0fc61-685">**收**</span><span class="sxs-lookup"><span data-stu-id="0fc61-685">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="0fc61-686">變更代理人的同時震鈴規則</span><span class="sxs-lookup"><span data-stu-id="0fc61-686">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="0fc61-687">這個範例會將在先前範例中設定的同時響鈴規則變更為 [延遲的響鈴] 規則。</span><span class="sxs-lookup"><span data-stu-id="0fc61-687">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

<span data-ttu-id="0fc61-688">**收**</span><span class="sxs-lookup"><span data-stu-id="0fc61-688">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a><span data-ttu-id="0fc61-689">移除代理人</span><span class="sxs-lookup"><span data-stu-id="0fc61-689">Remove the Delegate</span></span>

<span data-ttu-id="0fc61-690">這個範例會移除代理人。</span><span class="sxs-lookup"><span data-stu-id="0fc61-690">This example removes the delegate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0fc61-691">移除最後一個代理人時，系統會自動停用委派鈴聲。</span><span class="sxs-lookup"><span data-stu-id="0fc61-691">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

<span data-ttu-id="0fc61-692">**收**</span><span class="sxs-lookup"><span data-stu-id="0fc61-692">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="0fc61-693">新增代理人並設定來電-轉寄給代理人規則</span><span class="sxs-lookup"><span data-stu-id="0fc61-693">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="0fc61-694">這個範例會新增代理人，並設定 [來電轉接至代理人] 規則。</span><span class="sxs-lookup"><span data-stu-id="0fc61-694">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

<span data-ttu-id="0fc61-695">**收**</span><span class="sxs-lookup"><span data-stu-id="0fc61-695">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="0fc61-696">啟用同時震鈴及設定目的地號碼</span><span class="sxs-lookup"><span data-stu-id="0fc61-696">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="0fc61-697">這個範例可同時撥打並設定同時撥打的目的地號碼。</span><span class="sxs-lookup"><span data-stu-id="0fc61-697">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> <span data-ttu-id="0fc61-698">若要變更已啟用同時撥打之使用者的同時撥打的目的地號碼，請使用/enablesimulring 開關保留該命令，否則不會變更目的地號碼。</span><span class="sxs-lookup"><span data-stu-id="0fc61-698">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>



</div>

<span data-ttu-id="0fc61-699">**收**</span><span class="sxs-lookup"><span data-stu-id="0fc61-699">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a><span data-ttu-id="0fc61-700">停用同時撥打</span><span class="sxs-lookup"><span data-stu-id="0fc61-700">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="0fc61-701">這個範例會停用 [同時撥打]。</span><span class="sxs-lookup"><span data-stu-id="0fc61-701">This example disables simultaneous ringing.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

<span data-ttu-id="0fc61-702">**收**</span><span class="sxs-lookup"><span data-stu-id="0fc61-702">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="0fc61-703">新增小組通話的小組成員，並設定同時撥打給小組通話成員群組</span><span class="sxs-lookup"><span data-stu-id="0fc61-703">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="0fc61-704">這個範例會將小組成員新增至使用者的小組通話群組，並允許同時撥打給小組通話群組。</span><span class="sxs-lookup"><span data-stu-id="0fc61-704">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="0fc61-705">將成員新增到使用者的小組通話群組會自動切換使用者的同時撥打 settigs，以 simulring 其小組通話群組。</span><span class="sxs-lookup"><span data-stu-id="0fc61-705">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>



</div>

<span data-ttu-id="0fc61-706">**收**</span><span class="sxs-lookup"><span data-stu-id="0fc61-706">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="0fc61-707">移除團隊通話群組中的成員</span><span class="sxs-lookup"><span data-stu-id="0fc61-707">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="0fc61-708">這個範例會移除使用者小組通話群組的小組成員。</span><span class="sxs-lookup"><span data-stu-id="0fc61-708">This example removes a team member of the team-call group of a user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> <span data-ttu-id="0fc61-709">如果要移除的成員是團隊通話群組的唯一成員，同時撥打給小組通話群組會自動停用。</span><span class="sxs-lookup"><span data-stu-id="0fc61-709">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>



</div>

<span data-ttu-id="0fc61-710">**收**</span><span class="sxs-lookup"><span data-stu-id="0fc61-710">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="0fc61-711">將延遲的響鈴設定為小組通話群組</span><span class="sxs-lookup"><span data-stu-id="0fc61-711">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="0fc61-712">這個範例會將 [延遲] 響鈴變更為 [小組通話群組時間] 設定。</span><span class="sxs-lookup"><span data-stu-id="0fc61-712">This example changes the delayed ring to the team-call group time setting.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

<span data-ttu-id="0fc61-713">**收**</span><span class="sxs-lookup"><span data-stu-id="0fc61-713">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a><span data-ttu-id="0fc61-714">啟用小組通話</span><span class="sxs-lookup"><span data-stu-id="0fc61-714">Enable Team-Call</span></span>

<span data-ttu-id="0fc61-715">這個範例會為指定的使用者啟用團隊通話。</span><span class="sxs-lookup"><span data-stu-id="0fc61-715">This example enables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="0fc61-716">如果使用者的小組通話群組沒有成員，就不會啟用小組通話。</span><span class="sxs-lookup"><span data-stu-id="0fc61-716">If the team-call group of the user has no members, team-call won’t be enabled.</span></span>



</div>

<span data-ttu-id="0fc61-717">**收**</span><span class="sxs-lookup"><span data-stu-id="0fc61-717">**Output**</span></span>

</div>

<div>

## <a name="disable-team-call"></a><span data-ttu-id="0fc61-718">停用小組通話</span><span class="sxs-lookup"><span data-stu-id="0fc61-718">Disable Team-Call</span></span>

<span data-ttu-id="0fc61-719">這個範例會為指定的使用者停用小組通話。</span><span class="sxs-lookup"><span data-stu-id="0fc61-719">This example disables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

<span data-ttu-id="0fc61-720">**收**</span><span class="sxs-lookup"><span data-stu-id="0fc61-720">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="0fc61-721">啟用 [群組呼叫挑選]，並將分揀群組指派給使用者</span><span class="sxs-lookup"><span data-stu-id="0fc61-721">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="0fc61-722">這個範例會將分揀群組指派給使用者，並啟用群組呼叫挑選。</span><span class="sxs-lookup"><span data-stu-id="0fc61-722">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

<span data-ttu-id="0fc61-723">**收**</span><span class="sxs-lookup"><span data-stu-id="0fc61-723">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a><span data-ttu-id="0fc61-724">停用群組呼叫挑選</span><span class="sxs-lookup"><span data-stu-id="0fc61-724">Disable Group Call Pickup</span></span>

<span data-ttu-id="0fc61-725">這個範例會為指定的使用者停用 [群組呼叫挑選]。</span><span class="sxs-lookup"><span data-stu-id="0fc61-725">This example disables Group Call Pickup for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> <span data-ttu-id="0fc61-726">當您停用使用者的 [群組呼叫分揀] 時，系統不會保留指派給使用者的群組號碼。</span><span class="sxs-lookup"><span data-stu-id="0fc61-726">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="0fc61-727">如果您隨後想要重新啟用該使用者的群組呼叫分揀，您必須使用/enablegrouppickup 開關再次指派群組號碼。</span><span class="sxs-lookup"><span data-stu-id="0fc61-727">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a><span data-ttu-id="0fc61-728">SYSPrep. ps1</span><span class="sxs-lookup"><span data-stu-id="0fc61-728">SYSPrep.ps1</span></span>

<div>

## <a name="description"></a><span data-ttu-id="0fc61-729">描述</span><span class="sxs-lookup"><span data-stu-id="0fc61-729">Description</span></span>

<span data-ttu-id="0fc61-730">SYSPrep. ps1 是 Windows PowerShell 腳本，可在您的 Windows Server 2008 作業系統電腦上安裝下列 Lync Server 2013 先決條件。</span><span class="sxs-lookup"><span data-stu-id="0fc61-730">SYSPrep.ps1 is a Windows PowerShell script that will install the following Lync Server 2013 prerequisites on your Windows Server 2008 operating system machine.</span></span>

  - <span data-ttu-id="0fc61-731">Microsoft .Net Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="0fc61-731">Microsoft .Net Framework 4.5</span></span>

  - <span data-ttu-id="0fc61-732">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="0fc61-732">Microsoft SQL Server Express</span></span>

  - <span data-ttu-id="0fc61-733">Windows Powershell 版本3。0</span><span class="sxs-lookup"><span data-stu-id="0fc61-733">Windows Powershell version 3.0</span></span>

  - <span data-ttu-id="0fc61-734">Visual c + + 2010 可轉散發元件</span><span class="sxs-lookup"><span data-stu-id="0fc61-734">Visual C++ 2010 Redistributable</span></span>

  - <span data-ttu-id="0fc61-735">網際網路資訊伺服器更新</span><span class="sxs-lookup"><span data-stu-id="0fc61-735">Internet Information Server Updates</span></span>

  - <span data-ttu-id="0fc61-736">Windows 身分識別基礎</span><span class="sxs-lookup"><span data-stu-id="0fc61-736">Windows Identity Foundation</span></span>

  - <span data-ttu-id="0fc61-737">Lync Server 2013 核心轉儲檔</span><span class="sxs-lookup"><span data-stu-id="0fc61-737">Lync Server 2013 Core files</span></span>

<span data-ttu-id="0fc61-738">雖然腳本名稱與 Microsoft Windows 作業系統的系統準備工具類似，但它們是不同的。</span><span class="sxs-lookup"><span data-stu-id="0fc61-738">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="0fc61-739">此腳本只會安裝 Lync Server 2013 必要的先決條件。</span><span class="sxs-lookup"><span data-stu-id="0fc61-739">This script will only install the required prerequisites for Lync Server 2013.</span></span> <span data-ttu-id="0fc61-740">安裝這些必備元件之後，就可以使用 Windows SYSPrep 工具來建立伺服器的影像。</span><span class="sxs-lookup"><span data-stu-id="0fc61-740">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="0fc61-741">需求</span><span class="sxs-lookup"><span data-stu-id="0fc61-741">Requirements</span></span>

<span data-ttu-id="0fc61-742">在執行 SYSPrep. ps1 腳本之前，您必須先將必備檔案複製到 Windows Server 2008 作業系統電腦上的本機資料夾（例如**D：\\Setup）**。</span><span class="sxs-lookup"><span data-stu-id="0fc61-742">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\\Setup)**.</span></span> <span data-ttu-id="0fc61-743">這個資料夾也必須包含一份 Lync Server 2013 檔案（特別是 setup.exe）的複本 **。**</span><span class="sxs-lookup"><span data-stu-id="0fc61-743">This folder must also include a copy of the Lync Server 2013 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="0fc61-744">您可以從下列位置下載必備檔：</span><span class="sxs-lookup"><span data-stu-id="0fc61-744">The prerequisite files can be downloaded from the following locations:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0fc61-745">必備</span><span class="sxs-lookup"><span data-stu-id="0fc61-745">Prerequisite</span></span></th>
<th><span data-ttu-id="0fc61-746">位置</span><span class="sxs-lookup"><span data-stu-id="0fc61-746">Location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0fc61-747">Microsoft .Net Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="0fc61-747">Microsoft .Net Framework 4.5</span></span></p></td>
<td><p>http://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fc61-748">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="0fc61-748">Microsoft SQL Server Express 2008 R2</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fc61-749">Windows Powershell 版本3。0</span><span class="sxs-lookup"><span data-stu-id="0fc61-749">Windows Powershell version 3.0</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fc61-750">Visual c + + 2010 可轉散發元件</span><span class="sxs-lookup"><span data-stu-id="0fc61-750">Visual C++ 2010 Redistributable</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fc61-751">網際網路資訊伺服器更新</span><span class="sxs-lookup"><span data-stu-id="0fc61-751">Internet Information Server Updates</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fc61-752">Windows 身分識別基礎</span><span class="sxs-lookup"><span data-stu-id="0fc61-752">Windows Identity Foundation</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fc61-753">Lync Server 2013 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="0fc61-753">Lync Server 2013 Setup.exe</span></span></p></td>
<td><p><span data-ttu-id="0fc61-754">從 Lync Server 2013 媒體複製</span><span class="sxs-lookup"><span data-stu-id="0fc61-754">Copy from Lync Server 2013 media</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a><span data-ttu-id="0fc61-755">參數</span><span class="sxs-lookup"><span data-stu-id="0fc61-755">Parameter</span></span>

<span data-ttu-id="0fc61-756">**– SetupFolder**參數會將必備檔案的目錄位置做為引數。</span><span class="sxs-lookup"><span data-stu-id="0fc61-756">The **–SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="0fc61-757">範例</span><span class="sxs-lookup"><span data-stu-id="0fc61-757">Examples</span></span>

<span data-ttu-id="0fc61-758">若要執行 SYSPrep. ps1 腳本並安裝 Lync Server 2013 先決條件，請從提升許可權的命令提示字元執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0fc61-758">To run the SYSPrep.ps1 script and install the Lync Server 2013 prerequisites, run the following command from an elevated command prompt:</span></span>

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="0fc61-759">未指定的數位宣告遷移</span><span class="sxs-lookup"><span data-stu-id="0fc61-759">Unassigned Number Announcements Migration</span></span>

<span data-ttu-id="0fc61-760">[未指派的號碼宣告] 遷移工具可讓 Lync 系統管理員將宣告應用程式所提供的 [未指派的號碼] 設定從來源 Lync 伺服器或池中移至目的地 Lync 伺服器或文件庫。</span><span class="sxs-lookup"><span data-stu-id="0fc61-760">The Unassigned Number Announcements Migration tool enables a Lync administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Lync Server or Pool to a destination Lync Server or Pool.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="0fc61-761">描述</span><span class="sxs-lookup"><span data-stu-id="0fc61-761">Description</span></span>

<span data-ttu-id="0fc61-762">[取消指派的號碼宣告] 遷移工具是一個 Windows PowerShell 腳本，可將來源伺服器或池的宣告應用程式所提供的未指定編號設定移至不同的伺服器或池中。</span><span class="sxs-lookup"><span data-stu-id="0fc61-762">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="0fc61-763">執行時，[未指定的數位宣告] 遷移腳本會執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="0fc61-763">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1.  <span data-ttu-id="0fc61-764">將來源伺服器或池中託管之宣告應用程式的 [未指派的號碼] 宣告所使用的所有音訊檔案，移至目的地伺服器或池中的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="0fc61-764">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0fc61-765">當音訊檔案複製到目的地池之後，就會從來源池中移除。</span><span class="sxs-lookup"><span data-stu-id="0fc61-765">the audio files are removed from the source pool once they’re copied to the destination pool.</span></span>

    
    </div>

2.  <span data-ttu-id="0fc61-766">將針對來源伺服器或池中託管之宣告應用程式設定的所有未指派數位宣告移至目的伺服器或池。</span><span class="sxs-lookup"><span data-stu-id="0fc61-766">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3.  <span data-ttu-id="0fc61-767">將來源伺服器或池中託管的宣告應用程式所服務的所有未指派數位範圍重新指派至目的地伺服器或池中。</span><span class="sxs-lookup"><span data-stu-id="0fc61-767">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="0fc61-768">在成功執行腳本之後，由來源伺服器或池中託管之宣告應用程式所提供服務的所有未指派數位範圍，都將由目的地伺服器或池使用相同的設定來提供服務。</span><span class="sxs-lookup"><span data-stu-id="0fc61-768">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="0fc61-769">收</span><span class="sxs-lookup"><span data-stu-id="0fc61-769">Output</span></span>

<span data-ttu-id="0fc61-770">在 Lync 管理命令介面視窗中， **CsAnnouncementConfiguration**腳本會在執行遷移作業成功或失敗的位置中指示。</span><span class="sxs-lookup"><span data-stu-id="0fc61-770">The **Move-CsAnnouncementConfiguration** script indicates in the Lync Management Shell window from where it’s executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="0fc61-771">如果由於任何錯誤而中斷執行作業，則已順利移至目的地的未指派數位範圍將會保留在作業中，並將遷移的未指派數位範圍保留在來源以及工作表單中。</span><span class="sxs-lookup"><span data-stu-id="0fc61-771">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="0fc61-772">若要完全遷移其餘的設定，請在解決錯誤之後，重新執行腳本。</span><span class="sxs-lookup"><span data-stu-id="0fc61-772">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="0fc61-773">特殊</span><span class="sxs-lookup"><span data-stu-id="0fc61-773">Purpose</span></span>

<span data-ttu-id="0fc61-774">[未指定的數位宣告] 遷移腳本可以在下列三種案例中使用：</span><span class="sxs-lookup"><span data-stu-id="0fc61-774">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

  - <span data-ttu-id="0fc61-775">**將配置設定遷移至新版本的 Lync Server：** Contoso 是在遷移到 Lync Server 2013 的過程中，而作為遷移程式的一部分，Lync Server 管理員想要將宣告應用程式所提供的未指派號碼設定從 Lync Server 2010 部署移至新的 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="0fc61-775">**Migrating configuration settings to a new version of Lync Server:** Contoso is in the process of migrating to Lync Server 2013 and as part of the migration process the Lync Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2010 deployment to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="0fc61-776">若要移動設定，Lync Server 管理員會使用 [未指派的號碼宣告遷移工具]。</span><span class="sxs-lookup"><span data-stu-id="0fc61-776">To move the configuration settings, the Lync Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

  - <span data-ttu-id="0fc61-777">**從 Lync server 2013 將部署回退至 Lync server 2010：** 由於預期的意外因素，Contoso 必須將遷移回退到新的 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="0fc61-777">**Rolling back a deployment from Lync Server 2013 to Lync Server 2010:** Due unexpected factors, Contoso has to roll back the migration to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="0fc61-778">為了讓服務中斷降至最低，Lync Server 管理員會使用 [未指派的號碼宣告] 遷移工具，將 configuration 從 Lync Server 2013 部署回滾至 Lync Server 2010 部署。</span><span class="sxs-lookup"><span data-stu-id="0fc61-778">To minimize disruptions to the service, the Lync Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Lync Server 2013 deployment to the Lync Server 2010 deployment.</span></span>

  - <span data-ttu-id="0fc61-779">**在 Lync 部署之間移動資料：** Contoso 正處於使用較新的伺服器取代一個池的所有伺服器的程式中。</span><span class="sxs-lookup"><span data-stu-id="0fc61-779">**Moving data between Lync deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="0fc61-780">其戰略是部署新的 Lync Server 2013 池、將舊的資料移至新的資源池中，然後取代舊的資源區。</span><span class="sxs-lookup"><span data-stu-id="0fc61-780">Their strategy is to deploy a new Lync Server 2013 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="0fc61-781">部署新的資料庫池之後，就會使用 [取消指派的號碼宣告遷移工具]，將配置從舊的池中移至新的池中。</span><span class="sxs-lookup"><span data-stu-id="0fc61-781">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

<div>

## <a name="requirements"></a><span data-ttu-id="0fc61-782">需求</span><span class="sxs-lookup"><span data-stu-id="0fc61-782">Requirements</span></span>

<span data-ttu-id="0fc61-783">以下是成功執行此工具所需的主要需求：</span><span class="sxs-lookup"><span data-stu-id="0fc61-783">The following are the main requirements needed to successfully run the tool:</span></span>

1.  <span data-ttu-id="0fc61-784">此腳本必須從已安裝 Lync Server 2013 管理命令介面的電腦執行。</span><span class="sxs-lookup"><span data-stu-id="0fc61-784">The script must be run from a computer that has Lync Server 2013 Management Shell installed.</span></span>

2.  <span data-ttu-id="0fc61-785">宣告應用程式必須在來源和目的地 Lync 伺服器或池中成功部署。</span><span class="sxs-lookup"><span data-stu-id="0fc61-785">The announcement application has to be successfully deployed in the source and destination Lync Servers or Pools.</span></span>

<div>

## <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="0fc61-786">移動流覽 CsAnnouncementConfiguration 腳本</span><span class="sxs-lookup"><span data-stu-id="0fc61-786">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="0fc61-787">CsAnnouncementConfiguration 腳本需要下表所述的兩個參數。</span><span class="sxs-lookup"><span data-stu-id="0fc61-787">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

<span data-ttu-id="0fc61-788">![移動 CsAnnouncementConfiguration 參數。](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "移動 CsAnnouncementConfiguration 參數。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-788">![Move-CsAnnouncementConfiguration parameters.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration parameters.")</span></span>

</div>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="0fc61-789">範例</span><span class="sxs-lookup"><span data-stu-id="0fc61-789">Examples</span></span>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="0fc61-790">將 [未指派的號碼] 宣告配置從 Lync Server 2010 池中移至 Lync Server 2013 池</span><span class="sxs-lookup"><span data-stu-id="0fc61-790">Moving the Unassigned Number Announcements Configuration from a Lync Server 2010 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="0fc61-791">這個範例會將來源池（Lync Server 2010）的 [未指定的數位宣告]，移至目的地池（Lync Server 2013）。</span><span class="sxs-lookup"><span data-stu-id="0fc61-791">This example moves the unassigned number announcements from the source pool (Lync Server 2010) to the destination pool (Lync Server 2013).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a><span data-ttu-id="0fc61-792">將 [未指派的號碼] 宣告配置從 Lync Server 2013 池中移至 Lync Server 2010 池</span><span class="sxs-lookup"><span data-stu-id="0fc61-792">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Lync Server 2010 Pool</span></span>

<span data-ttu-id="0fc61-793">這個範例會將來源池（Lync Server 2013）的 [未指定的數位宣告]，移至目的地池（Lync Server 2010）。</span><span class="sxs-lookup"><span data-stu-id="0fc61-793">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Lync Server 2010).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a><span data-ttu-id="0fc61-794">網路會議資料</span><span class="sxs-lookup"><span data-stu-id="0fc61-794">Web Conf Data</span></span>

<span data-ttu-id="0fc61-795">網路會議資料工具可讓 Lync Server 2013 通訊軟體的管理員更容易控制與召集人的網路會議相關聯的資料。</span><span class="sxs-lookup"><span data-stu-id="0fc61-795">The Web Conf Data Tool allows an administrator of Lync Server 2013 communications software to have more control over the data associated with an organizer’s Web conferences.</span></span> <span data-ttu-id="0fc61-796">案例包括根據時間戳記準則刪除特定使用者的會議資料的功能。</span><span class="sxs-lookup"><span data-stu-id="0fc61-796">Scenarios include the ability to delete a specific user’s meeting data based on a time stamp criteria.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="0fc61-797">描述</span><span class="sxs-lookup"><span data-stu-id="0fc61-797">Description</span></span>

<span data-ttu-id="0fc61-798">這個工具可讓系統管理員執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="0fc61-798">This tool allows the administrator to perform the following operations:</span></span>

1.  <span data-ttu-id="0fc61-799">尋找與單一使用者相關聯的所有 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="0fc61-799">Find all Web conferencing data associated with a single user.</span></span>

2.  <span data-ttu-id="0fc61-800">刪除所有與單一使用者相關聯的 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="0fc61-800">Delete all Web conferencing data associated with a single user.</span></span>

3.  <span data-ttu-id="0fc61-801">刪除所有與特定日期舊的單一使用者相關聯的所有 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="0fc61-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4.  <span data-ttu-id="0fc61-802">當使用者從一個池移到另一個時，移動與單一使用者相關聯的所有 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="0fc61-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0fc61-803">在 Lync Server 2010 的資源工具組工具中，當使用者從一個中心移到另一個時，就能移動與單一使用者相關聯的所有 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="0fc61-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="0fc61-804">此功能現在已從這個工具中棄用，取而代之的是<STRONG>MoveConferenceData</STRONG>參數。</span><span class="sxs-lookup"><span data-stu-id="0fc61-804">That functionality is now deprecated from this tool in favor of the <STRONG>MoveConferenceData</STRONG> parameter.</span></span> <span data-ttu-id="0fc61-805">如需此參數的詳細資訊，請參閱<A href="https://technet.microsoft.com/en-us/library/gg398528(v=ocs.15)">move-csuser</A> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0fc61-805">For details about this parameter, see the <A href="https://technet.microsoft.com/en-us/library/gg398528(v=ocs.15)">Move-CsUser</A> cmdlet.</span></span>



</div>

<span data-ttu-id="0fc61-806">此工具只會刪除處於非作用中的會議的會議資料。</span><span class="sxs-lookup"><span data-stu-id="0fc61-806">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="0fc61-807">無法刪除使用中的會議（或會話中的會議）。</span><span class="sxs-lookup"><span data-stu-id="0fc61-807">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="0fc61-808">此工具必須從與目標使用者相同的同一個池中的電腦執行。</span><span class="sxs-lookup"><span data-stu-id="0fc61-808">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="0fc61-809">其會議內容資料由此工具管理的使用者必須駐留在相同的使用者池中。</span><span class="sxs-lookup"><span data-stu-id="0fc61-809">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="0fc61-810">收</span><span class="sxs-lookup"><span data-stu-id="0fc61-810">Output</span></span>

<span data-ttu-id="0fc61-811">這個工具會輸出每個作業的結果：</span><span class="sxs-lookup"><span data-stu-id="0fc61-811">This tool outputs the results of each of the operations:</span></span>

  - <span data-ttu-id="0fc61-812">如果執行查詢，該工具會將使用者作為召集人的所有非作用中會議資料資料夾清單輸出。</span><span class="sxs-lookup"><span data-stu-id="0fc61-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

  - <span data-ttu-id="0fc61-813">如果執行刪除，工具會將刪除其資料的所有會議資料資料夾清單輸出。</span><span class="sxs-lookup"><span data-stu-id="0fc61-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="0fc61-814">需求</span><span class="sxs-lookup"><span data-stu-id="0fc61-814">Requirements</span></span>

<span data-ttu-id="0fc61-815">此工具必須在召集人目前所駐留的同一個池中執行。</span><span class="sxs-lookup"><span data-stu-id="0fc61-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="0fc61-816">您必須使用具有內容檔案存放區存取權的系統管理員許可權來執行該工具。</span><span class="sxs-lookup"><span data-stu-id="0fc61-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="0fc61-817">範例</span><span class="sxs-lookup"><span data-stu-id="0fc61-817">Examples</span></span>

<span data-ttu-id="0fc61-818">下表說明一些在範例中使用的參數。</span><span class="sxs-lookup"><span data-stu-id="0fc61-818">The following table describes the parameters, some of which are used in the examples.</span></span>

<span data-ttu-id="0fc61-819">![網路會議資料工具參數。](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "網路會議資料工具參數。")</span><span class="sxs-lookup"><span data-stu-id="0fc61-819">![Web Conf Data Tool parameters.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web Conf Data Tool parameters.")</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

<span data-ttu-id="0fc61-820">前面的範例顯示查詢命令的運作方式。</span><span class="sxs-lookup"><span data-stu-id="0fc61-820">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="0fc61-821">這類命令的輸出會是受此工具影響之所有會議內容資料夾的清單。</span><span class="sxs-lookup"><span data-stu-id="0fc61-821">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

<span data-ttu-id="0fc61-822">上述是 [刪除] 命令的範例。</span><span class="sxs-lookup"><span data-stu-id="0fc61-822">The preceding is an example of a delete command.</span></span> <span data-ttu-id="0fc61-823">[刪除] 命令會從該使用者移除所有非作用中會議資料夾。</span><span class="sxs-lookup"><span data-stu-id="0fc61-823">The delete command will remove all inactive meeting folders from this user.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="0fc61-824">總結</span><span class="sxs-lookup"><span data-stu-id="0fc61-824">Summary</span></span>

<span data-ttu-id="0fc61-825">此工具對於需要更精確控制會議會議資料的管理員而言，是一種重要的資源。</span><span class="sxs-lookup"><span data-stu-id="0fc61-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

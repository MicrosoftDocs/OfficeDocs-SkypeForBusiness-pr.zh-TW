---
title: Lync Server 2013 資源工具組工具檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60c2260f5729c45455596f0ab2477f7a190ef520
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509220"
---
# <a name="lync-server-2013-resource-kit-tools-documentation"></a><span data-ttu-id="b7bb0-102">Lync Server 2013 資源工具組工具檔</span><span class="sxs-lookup"><span data-stu-id="b7bb0-102">Lync Server 2013 Resource Kit Tools Documentation</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7bb0-103">_**主題上次修改日期：** 2014-01-09_</span><span class="sxs-lookup"><span data-stu-id="b7bb0-103">_**Topic Last Modified:** 2014-01-09_</span></span>

<span data-ttu-id="b7bb0-104">本主題說明屬於 Lync Server 2013 資源套件的工具，包含每個工具的用途，以及其用途的範例。Lync Server 2013，資源工具組工具可協助您簡化部署及管理 Lync Server 2013 的 IT 系統管理員的日常工作。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-104">This topic describes the tools that are part of the Lync Server 2013 Resource Kit, including the purpose of each tool, and examples of its use.The Lync Server 2013, Resource Kit Tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="b7bb0-105">例如，網路會議 **資料** 工具可以用來輕鬆控制使用者在線上會議期間上傳的資料。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-105">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="b7bb0-106">**SEFAUtil**工具可以用來設定使用者的代理人來電轉接和應答。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-106">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="b7bb0-107">我們鼓勵 IT 管理員使用這些工具，更有效率地管理 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-107">We encourage IT administrators to use these tools to more effectively manage Lync Server 2013.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="b7bb0-108">安裝資源工具組工具</span><span class="sxs-lookup"><span data-stu-id="b7bb0-108">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="b7bb0-109">若要安裝 Lync Server 2013，資源工具組工具，請下載 **OCSReskit.msi**。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-109">To install the Lync Server 2013, Resource Kit Tools, download **OCSReskit.msi**.</span></span> <span data-ttu-id="b7bb0-110">您可以從下載中心下載 Resource 工具組工具安裝程式 [https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429) 。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-110">You can download the Resource Kit Tools installer from the Download Center at [https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429).</span></span>

<span data-ttu-id="b7bb0-111">執行 **OCSResKit.msi** 以執行簡單安裝。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-111">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="b7bb0-112">.Msi 會安裝下列路徑中的所有工具： **% Program Files% \\ Microsoft Lync Server 2013 \\ ResKit**。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-112">The .msi installs all the tools in the following path: **%Program Files%\\Microsoft Lync Server 2013\\ResKit**.</span></span> <span data-ttu-id="b7bb0-113">屬於自包含可執行檔的工具位於此資料夾中。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-113">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="b7bb0-114">也有檔案的工具位於自己的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-114">Tools that also have files are in their own subfolders.</span></span>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="b7bb0-115">支援的環境</span><span class="sxs-lookup"><span data-stu-id="b7bb0-115">Supported Environments</span></span>

<span data-ttu-id="b7bb0-116">為了達到最佳效能，Lync Server 2013，資源工具組工具應該安裝在相同的環境中，且使用 Lync Server 2013 所需的相同規格。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-116">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="b7bb0-117">資源工具組工具概述</span><span class="sxs-lookup"><span data-stu-id="b7bb0-117">Resource Kit Tools Overview</span></span>

<span data-ttu-id="b7bb0-118">下列清單說明 Lync Server 2013 資源套件中所提供的工具。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-118">The following list describes the tools that are provided in the Lync Server 2013 Resource Kit.</span></span> <span data-ttu-id="b7bb0-119">下一節將說明每個工具，包括需求和範例用法。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-119">A description of each tool, including the requirements and example usage is covered in the following section.</span></span>

  - <span data-ttu-id="b7bb0-120">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="b7bb0-120">ABSConfig</span></span>

  - <span data-ttu-id="b7bb0-121">頻寬原則服務監視器</span><span class="sxs-lookup"><span data-stu-id="b7bb0-121">Bandwidth Policy Service Monitor</span></span>

  - <span data-ttu-id="b7bb0-122">頻寬流量分析程式</span><span class="sxs-lookup"><span data-stu-id="b7bb0-122">Bandwidth Utilization Analyzer</span></span>

  - <span data-ttu-id="b7bb0-123">呼叫 Call parkometer</span><span class="sxs-lookup"><span data-stu-id="b7bb0-123">Call Parkometer</span></span>

  - <span data-ttu-id="b7bb0-124">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="b7bb0-124">CleanupStorageServiceData</span></span>

  - <span data-ttu-id="b7bb0-125">Dbanalyze.exe</span><span class="sxs-lookup"><span data-stu-id="b7bb0-125">DBAnalyze</span></span>

  - <span data-ttu-id="b7bb0-126">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="b7bb0-126">ImportStorageServiceData</span></span>

  - <span data-ttu-id="b7bb0-127">LCSSync</span><span class="sxs-lookup"><span data-stu-id="b7bb0-127">LCSSync</span></span>

  - <span data-ttu-id="b7bb0-128">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="b7bb0-128">LookupUserConsole</span></span>

  - <span data-ttu-id="b7bb0-129">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="b7bb0-129">MsTurnPing</span></span>

  - <span data-ttu-id="b7bb0-130">網路設定檢視器</span><span class="sxs-lookup"><span data-stu-id="b7bb0-130">Network Configuration Viewer</span></span>

  - <span data-ttu-id="b7bb0-131">回應群組代理程式 Live</span><span class="sxs-lookup"><span data-stu-id="b7bb0-131">Response Group Agent Live</span></span>

  - <span data-ttu-id="b7bb0-132">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="b7bb0-132">SEFAUtil</span></span>

  - <span data-ttu-id="b7bb0-133">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="b7bb0-133">SYSPrep.ps1</span></span>

  - <span data-ttu-id="b7bb0-134">未指派號碼宣告遷移</span><span class="sxs-lookup"><span data-stu-id="b7bb0-134">Unassigned Number Announcements Migration</span></span>

  - <span data-ttu-id="b7bb0-135">網路會議資料</span><span class="sxs-lookup"><span data-stu-id="b7bb0-135">Web Conf Data</span></span>

</div>

<div>

## <a name="absconfig"></a><span data-ttu-id="b7bb0-136">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="b7bb0-136">ABSConfig</span></span>

<span data-ttu-id="b7bb0-137">通訊錄服務設定工具 (ABSConfig) 是一種系統管理工具，可協助系統管理員在 Lync Server 2013 中自訂通訊錄服務設定。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-137">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Lync Server 2013.</span></span> <span data-ttu-id="b7bb0-138">此工具也可讓 Lync Server 2013 系統管理員還原預設通訊錄服務設定。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-138">This tool also enables Lync Server 2013 administrators to restore the default Address Book Service settings.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b7bb0-139">描述</span><span class="sxs-lookup"><span data-stu-id="b7bb0-139">Description</span></span>

<span data-ttu-id="b7bb0-140">ABSConfig 是一種圖形使用者介面應用程式，可讓系統管理員設定與通訊錄服務相關的 Active Directory 網域服務屬性。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-140">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="b7bb0-141">工具的主要案例如下：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-141">The primary scenarios for the tool are the following:</span></span>

  - <span data-ttu-id="b7bb0-142">讓系統管理員能夠將 Active Directory 網域服務中的屬性對應至 Lync Server 2013 的屬性。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-142">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Lync Server 2013.</span></span>

  - <span data-ttu-id="b7bb0-143">讓系統管理員指定要在通訊錄服務檔案中包含或排除的 Active Directory 網域服務屬性。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-143">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

  - <span data-ttu-id="b7bb0-144">讓系統管理員能夠還原預設的通訊錄服務設定。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-144">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="b7bb0-145">您可以使用 absConfig.exe 檔啟動 ABSConfig 工具。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-145">The ABSConfig tool can be started by using the absConfig.exe file.</span></span> <span data-ttu-id="b7bb0-146">工具隨即開啟至 [ **設定屬性** ] 索引標籤。此表格中的選項可將 Active Directory 網域服務屬性對應至 Lync Server 2013 的屬性欄位，並指定哪些使用者要在通訊錄服務檔案中包含或排除，以特定的屬性篩選器為基礎。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-146">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Lync Server 2013 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="b7bb0-147">也可以選擇自訂要包含在通訊錄檔案中的電話號碼值。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-147">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="b7bb0-148">[ **還原預設** 值] 選項可讓系統管理員將通訊錄服務設定還原為預設值。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-148">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

</div>

<div>

## <a name="changes-from-lync-server-2010"></a><span data-ttu-id="b7bb0-149">Lync Server 2010 的變更</span><span class="sxs-lookup"><span data-stu-id="b7bb0-149">Changes from Lync Server 2010</span></span>

<span data-ttu-id="b7bb0-150">在 [Lync Server 2013 ABS 設定工具] 中，可取消勾選屬性 (列) 屬性。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-150">In Lync Server 2013 ABS Configuration tool, attributes (rows) may be removed by unchecking the “enable” checkbox for the attribute.</span></span> <span data-ttu-id="b7bb0-151">這與在 Lync Server 2010 中刪除列的效果相同。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-151">This has the same effect as deleting the row in Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b7bb0-152">啟用核取方塊位於最右邊的欄位;您可能需要向右滾動才能看到欄</span><span class="sxs-lookup"><span data-stu-id="b7bb0-152">The enable checkbox is in the far right column; you may need to scroll right to see the column</span></span>



</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="b7bb0-153">輸出</span><span class="sxs-lookup"><span data-stu-id="b7bb0-153">Output</span></span>

<span data-ttu-id="b7bb0-154">ABSConfig 會將通訊錄服務設定儲存在資料庫中。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-154">ABSConfig stores the Address Book Service configuration in the database.</span></span>

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="b7bb0-155">用途</span><span class="sxs-lookup"><span data-stu-id="b7bb0-155">Purpose</span></span>

<span data-ttu-id="b7bb0-156">ABSConfig 提供快速快捷的方式，以自訂 Lync Server 2013 Address Book Service。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-156">ABSConfig provides a quick and easy way to customize Lync Server 2013 Address Book Service.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b7bb0-157">需求</span><span class="sxs-lookup"><span data-stu-id="b7bb0-157">Requirements</span></span>

<div>

## <a name="computer"></a><span data-ttu-id="b7bb0-158">電腦</span><span class="sxs-lookup"><span data-stu-id="b7bb0-158">Computer</span></span>

<span data-ttu-id="b7bb0-159">ABSConfig 只能從已安裝 Lync Server 2013 的已加入網域的電腦執行。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-159">ABSConfig can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span> <span data-ttu-id="b7bb0-160">在 [Lync Server 2013，Enterprise Edition] 的情況下，此工具可以在安裝期間啟用通訊錄服務的任何前端伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-160">In the case of Lync Server 2013, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

</div>

<div>

## <a name="network"></a><span data-ttu-id="b7bb0-161">網路</span><span class="sxs-lookup"><span data-stu-id="b7bb0-161">Network</span></span>

<span data-ttu-id="b7bb0-162">電腦應該能夠連線至前端集區和後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-162">The computer should be able to connect to the Front End pool and back-end database.</span></span>

</div>

<div>

## <a name="software"></a><span data-ttu-id="b7bb0-163">軟體</span><span class="sxs-lookup"><span data-stu-id="b7bb0-163">Software</span></span>

<span data-ttu-id="b7bb0-164">在執行 ABSConfig 工具之前，必須先安裝下列軟體元件：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-164">The following software components must be installed before running the ABSConfig tool:</span></span>

  - <span data-ttu-id="b7bb0-165">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7bb0-165">Microsoft Lync Server 2013</span></span>

</div>

<div>

## <a name="users"></a><span data-ttu-id="b7bb0-166">使用者</span><span class="sxs-lookup"><span data-stu-id="b7bb0-166">Users</span></span>

<span data-ttu-id="b7bb0-167">具備更新 Lync Server 2013 部署所需之許可權的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-167">Administrators who have the permissions required to update the Lync Server 2013 deployment.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b7bb0-168">範例</span><span class="sxs-lookup"><span data-stu-id="b7bb0-168">Examples</span></span>

<span data-ttu-id="b7bb0-169">您可以在命令提示字元處輸入 **ABSConfig.exe** ，以啟動 ABSConfig。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-169">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="b7bb0-170">如下所示為 ABSConfig 工具使用者介面。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-170">Shown below is the ABSConfig tool user interface.</span></span>

<span data-ttu-id="b7bb0-171">![ABSConfig.exe 工具。](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "ABSConfig.exe 工具。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-171">![The ABSConfig.exe tool.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "The ABSConfig.exe tool.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="b7bb0-172">摘要</span><span class="sxs-lookup"><span data-stu-id="b7bb0-172">Summary</span></span>

<span data-ttu-id="b7bb0-173">ABSConfig 工具可讓系統管理員快速快捷地使用工具，以自訂 Lync Server 2013 Address Book 服務。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-173">The ABSConfig tool provides administrators a quick and easy to use tool to customize Lync Server 2013 Address Book Service.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="b7bb0-174">頻寬原則服務監視器</span><span class="sxs-lookup"><span data-stu-id="b7bb0-174">Bandwidth Policy Service Monitor</span></span>

<span data-ttu-id="b7bb0-175">「頻寬原則服務監視」工具的目的是讓系統管理員可以查看下列專案的清單：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-175">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1.  <span data-ttu-id="b7bb0-176">拓撲中所有已設定的 Lync Server 2013 頻寬原則服務 (驗證及核心) </span><span class="sxs-lookup"><span data-stu-id="b7bb0-176">All the configured Lync Server 2013 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2.  <span data-ttu-id="b7bb0-177">每個服務對其他頻寬原則服務和 Edge server 所進行的連接</span><span class="sxs-lookup"><span data-stu-id="b7bb0-177">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3.  <span data-ttu-id="b7bb0-178">網路設定檔中所設定的所有連結，以及每個頻寬原則服務所報告的即時頻寬使用量</span><span class="sxs-lookup"><span data-stu-id="b7bb0-178">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b7bb0-179">描述</span><span class="sxs-lookup"><span data-stu-id="b7bb0-179">Description</span></span>

<span data-ttu-id="b7bb0-180">頻寬原則服務監視工具是以 GUI 型應用程式的形式來執行。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-180">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="b7bb0-181">管理員會透過執行 PDPMonUI.exe 來啟動工具。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-181">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="b7bb0-182">當工具開始時，它會嘗試探索拓撲中的頻寬原則服務清單。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-182">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="b7bb0-183">完成初始更新後，視窗左側的窗格會以所隸屬的群組為群組的服務清單填入。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-183">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="b7bb0-184">當管理員選擇特定頻寬原則服務時，右側窗格會顯示該特定服務的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-184">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="b7bb0-185">該窗格也有兩個主要索引標籤可顯示資訊。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-185">That pane also has two main tabs that display information.</span></span>

<div>

## <a name="machine-info-tab"></a><span data-ttu-id="b7bb0-186">電腦資訊] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="b7bb0-186">Machine Info Tab</span></span>

<span data-ttu-id="b7bb0-187">[ **機器資訊** ] 索引標籤會顯示所選頻寬原則服務的詳細資料，以及選取的頻寬原則服務對其他服務所做的所有連線清單和狀態。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-187">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

</div>

<div>

## <a name="topology-info-tab"></a><span data-ttu-id="b7bb0-188">拓撲資訊] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="b7bb0-188">Topology Info Tab</span></span>

<span data-ttu-id="b7bb0-189">**拓撲資訊**索引標籤顯示網路設定中所設定之所有連結的清單。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-189">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="b7bb0-190">針對每個連結，會顯示音訊和影片頻寬容量。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-190">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="b7bb0-191">此外，目前使用的頻寬會顯示，以 Kbps 為單位的容量百分比顯示。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-191">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="b7bb0-192">工具使用色彩編碼，強調具有接近容量之使用率的連結，這可讓系統管理員快速隔離這類連結。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-192">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b7bb0-193">如果頻寬原則服務監視工具在連線至任何設定的頻寬原則服務時失敗，將不會填入 <STRONG>機器資訊</STRONG> 和 <STRONG>拓撲資訊</STRONG> 索引標籤中的資訊。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-193">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the <STRONG>Machine Info</STRONG> and the <STRONG>Topology Info</STRONG> tabs won’t be populated.</span></span> <span data-ttu-id="b7bb0-194">不過，此工具最初可能會連線，但後來會失去與服務的連線。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-194">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="b7bb0-195">在這種情況下，系統管理員可能會看到過時的資訊。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-195">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="b7bb0-196">每個索引標籤上都有最後一次 <STRONG>更新</STRONG> 的時間戳記，可讓系統管理員看到上次更新特定頻寬原則服務的資料的時間。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-196">There is a <STRONG>Last Updated</STRONG> time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="b7bb0-197">輸出</span><span class="sxs-lookup"><span data-stu-id="b7bb0-197">Output</span></span>

<span data-ttu-id="b7bb0-198">無命令列輸出;程式輸出包含在主要圖形使用者介面 (GUI) 中。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-198">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="b7bb0-199">用途</span><span class="sxs-lookup"><span data-stu-id="b7bb0-199">Purpose</span></span>

<span data-ttu-id="b7bb0-200">「頻寬原則服務監視」工具的目的是讓系統管理員能看到拓撲中所定義的每個頻寬原則服務的狀態。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-200">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="b7bb0-201">此外，系統管理員可以查看網路設定檔中所定義之所有連結的即時頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-201">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b7bb0-202">需求</span><span class="sxs-lookup"><span data-stu-id="b7bb0-202">Requirements</span></span>

<span data-ttu-id="b7bb0-203">[！注意] 在屬於 Lync Server 拓撲的電腦上，必須執行頻寬原則服務監視器工具。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-203">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Lync Server topology.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="b7bb0-204">摘要</span><span class="sxs-lookup"><span data-stu-id="b7bb0-204">Summary</span></span>

<span data-ttu-id="b7bb0-205">頻寬原則服務監視器工具對管理員來說可能是一項寶貴資源，讓他們能夠檢查拓撲中所有頻寬原則服務的狀態，更重要的是，他們可以取得網路設定設定中所定義之連結的即時頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-205">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="b7bb0-206">頻寬流量分析程式</span><span class="sxs-lookup"><span data-stu-id="b7bb0-206">Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="b7bb0-207">頻寬流量分析程式是一種工具，它會針對商業網路中 WAN 連結的 UC 端點，建立各種頻寬使用量的報告。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-207">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="b7bb0-208">這些報告可用於瞭解目前的頻寬消耗模式，以及協助進行頻寬容量規劃。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-208">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b7bb0-209">描述</span><span class="sxs-lookup"><span data-stu-id="b7bb0-209">Description</span></span>

<span data-ttu-id="b7bb0-210">頻寬使用量分析器是以 GUI 型應用程式的形式來執行。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-210">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="b7bb0-211">這個工具專為網路上的音訊使用量產生報告，並協助進行容量規劃。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-211">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="b7bb0-212">它也會在指派給各種連結的頻寬容量上進行迴圈。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-212">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="b7bb0-213">輸出</span><span class="sxs-lookup"><span data-stu-id="b7bb0-213">Output</span></span>

<span data-ttu-id="b7bb0-214">頻寬流量分析程式可為系統中所設定的所有 WAN 連結，提供圖形 al 的頻寬容量及音訊使用方式。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-214">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="b7bb0-215">用途</span><span class="sxs-lookup"><span data-stu-id="b7bb0-215">Purpose</span></span>

<span data-ttu-id="b7bb0-216">在任何語音和影片部署中，監控和瞭解整個商業網路中媒體流量的頻寬利用率，都很重要。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-216">In any voice and video deployment, it’s critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="b7bb0-217">頻寬使用狀況分析工具可讓系統管理員只取得這種方式。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-217">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="b7bb0-218">此工具會執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-218">This tool does the following:</span></span>

  - <span data-ttu-id="b7bb0-219">針對整個網路產生音訊使用量的特定報告</span><span class="sxs-lookup"><span data-stu-id="b7bb0-219">Generates specific reports for audio utilization across the network</span></span>

  - <span data-ttu-id="b7bb0-220">協助在指派給各種連結的頻寬容量上進行更有效的容量規劃和反覆運算</span><span class="sxs-lookup"><span data-stu-id="b7bb0-220">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="b7bb0-221">頻寬流量分析程式可以產生頻寬容量和使用方式報告的圖形圖形它們如下：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-221">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

  - <span data-ttu-id="b7bb0-222">商業網路中的所有 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="b7bb0-222">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="b7bb0-223">依選取的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="b7bb0-223">Filtered by selected WAN links that have been chosen</span></span>

  - <span data-ttu-id="b7bb0-224">由超過連結容量的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="b7bb0-224">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="b7bb0-225">使用已在使用中布建的頻寬來篩選的 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="b7bb0-225">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

  - <span data-ttu-id="b7bb0-226">依 WAN 連結的頻寬使用量超過90% 的頻寬使用量，篩選已達到關鍵性層級的 WAN 連結 () </span><span class="sxs-lookup"><span data-stu-id="b7bb0-226">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="b7bb0-227">依 WAN 連結類型篩選—網路網站連結、interregional 連結，以及網站內的連結</span><span class="sxs-lookup"><span data-stu-id="b7bb0-227">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

  - <span data-ttu-id="b7bb0-228">依網路地區篩選</span><span class="sxs-lookup"><span data-stu-id="b7bb0-228">Filtered by network region</span></span>

<div>

## <a name="applications"></a><span data-ttu-id="b7bb0-229">應用程式</span><span class="sxs-lookup"><span data-stu-id="b7bb0-229">Applications</span></span>

<span data-ttu-id="b7bb0-230">頻寬使用狀況分析器具有下列兩個應用程式 (工具) ：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-230">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

  - <span data-ttu-id="b7bb0-231">**WanLinkLogCollector.exe**    此工具可讓其使用者輸入必要的資訊。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-231">**WanLinkLogCollector.exe**   This tool enables its user to input the required information.</span></span>

  - <span data-ttu-id="b7bb0-232">**BandwidthUtilizationAnalyzer.xlsm**   Microsoft Excel 試算表軟體報告會由 WanLinkLogCollector.exe 自動啟動。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-232">**BandwidthUtilizationAnalyzer.xlsm**  A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="b7bb0-233">此應用程式可讓使用者將篩選器套用至報告（如本文稍後所示）。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-233">This application allows the user to apply filters to the report as shown later in this article.</span></span>

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="b7bb0-234">使用頻寬流量分析程式的階段</span><span class="sxs-lookup"><span data-stu-id="b7bb0-234">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="b7bb0-235">使用頻寬使用量分析器時，有兩個階段：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-235">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

  - <span data-ttu-id="b7bb0-236">收集使用 WanLinkLogCollector.exe 所執行的記錄</span><span class="sxs-lookup"><span data-stu-id="b7bb0-236">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

  - <span data-ttu-id="b7bb0-237">使用 BandwidthUtilizationAnalyzer.xlsm 進行自訂報告</span><span class="sxs-lookup"><span data-stu-id="b7bb0-237">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b7bb0-238">強烈建議您不要由使用者手動啟動 BandwidthUtilizationAnalyzer.xlsm。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-238">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="b7bb0-239">啟動頻寬流量分析程式</span><span class="sxs-lookup"><span data-stu-id="b7bb0-239">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="b7bb0-240">在命令提示字元處或使用 Windows Explorer 開始 WanLinkLogCollector.exe。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-240">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

<span data-ttu-id="b7bb0-241">**使用 WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-241">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="b7bb0-242">使用 WanLinkLogCollector.exe 有三個步驟：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-242">There are three steps to using WanLinkLogCollector.exe:</span></span>

1.  <span data-ttu-id="b7bb0-243">**記錄時程表**    提供報表需要產生的時程表</span><span class="sxs-lookup"><span data-stu-id="b7bb0-243">**Log the timeline**   Provide the timeline that the report needs to be generated for</span></span>

2.  <span data-ttu-id="b7bb0-244">**指定檔目錄**    提供檔案位置資訊</span><span class="sxs-lookup"><span data-stu-id="b7bb0-244">**Specify the file directories**   Provide file location information</span></span>

3.  <span data-ttu-id="b7bb0-245">**收集記錄檔並啟動報告檢視器**   執行命令以產生報告</span><span class="sxs-lookup"><span data-stu-id="b7bb0-245">**Collect the logs and launch the report viewer**  Execute the command to generate the report</span></span>

<div>

## <a name="step-1---log-the-timeline"></a><span data-ttu-id="b7bb0-246">步驟 1-記錄時程表</span><span class="sxs-lookup"><span data-stu-id="b7bb0-246">Step 1 - Log the timeline</span></span>

<span data-ttu-id="b7bb0-247">記錄時程表可讓工具使用者指定下列，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-247">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1.  <span data-ttu-id="b7bb0-248">**開始日期** 這是要產生報告的時程表開始日期;例如，2010年8月1日。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-248">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2.  <span data-ttu-id="b7bb0-249">**結束日期** 這是要產生報告的時程表結束日期;例如，2010年9月30日。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-249">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>
    
    <span data-ttu-id="b7bb0-250">![頻寬使用狀況 A 的開始和結束日期](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "頻寬使用狀況 A 的開始和結束日期")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-250">![Start and End dates in the Bandwidth Utilization A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Start and End dates in the Bandwidth Utilization A")</span></span>  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="b7bb0-251">步驟 2-指定檔目錄</span><span class="sxs-lookup"><span data-stu-id="b7bb0-251">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="b7bb0-252">下列是使用者可以指定的檔案目錄，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-252">The following file directories can be specified by the user as shown.</span></span>

  - <span data-ttu-id="b7bb0-253">**伺服器記錄檔位置** 儲存頻寬原則伺服器記錄的資料夾位置。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-253">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="b7bb0-254">這通常是在 \<fileserver\> \\ \<choice of FE\> \\ AppServerFiles \\ PDP 中。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-254">This is typically in \<fileserver\>\\\<choice of FE\>\\AppServerFiles\\PDP.</span></span>

  - <span data-ttu-id="b7bb0-255">**暫存檔儲存位置** 產生報告時儲存中間檔案的暫存檔案位置。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-255">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

<span data-ttu-id="b7bb0-256">![頻寬使用量分析中的檔案目錄](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "頻寬使用量分析中的檔案目錄")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-256">![File directories in the Bandwidth Utilization Anal](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "File directories in the Bandwidth Utilization Anal")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b7bb0-257">確定已將對伺服器記錄和暫存檔存放區資料夾的足夠存取權提供給工具使用者。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-257">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="b7bb0-258">步驟 3-收集記錄檔並啟動報告檢視器</span><span class="sxs-lookup"><span data-stu-id="b7bb0-258">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="b7bb0-259">若要收集記錄檔並啟動報告檢視器，請按一下 [ **執行** ]，如下所示。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-259">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="b7bb0-260">此步驟會收集必要的資料。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-260">This step collects the required data.</span></span>

<span data-ttu-id="b7bb0-261">![在頻寬利用率 Analy 中收集資料](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "在頻寬利用率 Analy 中收集資料")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-261">![Collecting data in the Bandwidth Utilization Analy](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Collecting data in the Bandwidth Utilization Analy")</span></span>

<span data-ttu-id="b7bb0-262">當輸入驗證成功時，會顯示如下所示的訊息。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-262">When the input validation is successful, the message shown below is displayed.</span></span>

<span data-ttu-id="b7bb0-263">![在頻寬 Utili 中收集的記錄通知](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "在頻寬 Utili 中收集的記錄通知")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-263">![Logs collected notification in the Bandwidth Utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Logs collected notification in the Bandwidth Utili")</span></span>

<span data-ttu-id="b7bb0-264">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-264">Click **OK**.</span></span> <span data-ttu-id="b7bb0-265">BandwidthUtilizationAnalyzer.xlsm 會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-265">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="b7bb0-266">依照訊息方塊中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-266">Follow the instructions in the message box.</span></span> <span data-ttu-id="b7bb0-267">如需詳細資訊，請參閱下一節中的 **Using BandwidthUtilizationAnalyzer.xlsm** 。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-267">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>

</div>

<div>


<span data-ttu-id="b7bb0-268">**使用 BandwidthUtilizationAnalyzer.xlsm**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-268">**Using BandwidthUtilizationAnalyzer.xlsm**</span></span>

1.  <span data-ttu-id="b7bb0-269">自動啟動 BandwidthUtilizationAnalyzer.xlsm 時，請按一下 [重新整理] **，如下所** 示。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-269">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>
    
    <span data-ttu-id="b7bb0-270">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-270">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span></span>

2.  <span data-ttu-id="b7bb0-271">開啟檔案資料夾時，請選取訊息方塊中所指定的位置 consolidated.csv，如下所示。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-271">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="b7bb0-272">它也會顯示 **C： \\ Temp**的位置。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-272">It also shows the location as **C:\\Temp**.</span></span>
    
    <span data-ttu-id="b7bb0-273">![在 BandwidthUtilizationAnalyzer 中開啟資料夾。](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "在 BandwidthUtilizationAnalyzer 中開啟資料夾。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-273">![Opening a folder in BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Opening a folder in BandwidthUtilizationAnalyzer.")</span></span>

3.  <span data-ttu-id="b7bb0-274">按一下 **[匯入]**。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-274">Click **Import**.</span></span>

4.  <span data-ttu-id="b7bb0-275">會自動產生圖形化圖形。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-275">The graphical plot is automatically generated.</span></span> <span data-ttu-id="b7bb0-276">當工作的背景指標消失時，即可使用此功能。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-276">It is available when the working-in-the-background pointer disappears.</span></span>
    
    <span data-ttu-id="b7bb0-277">![在報表檢視中套用篩選器。](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "在報表檢視中套用篩選器。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-277">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="b7bb0-278">將篩選器套用至報表檢視</span><span class="sxs-lookup"><span data-stu-id="b7bb0-278">Applying Filters to the Report View</span></span>

<span data-ttu-id="b7bb0-279">如下所示，可套用到報表檢視的篩選，如下所述：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-279">The filters that can be applied to the report view as shown below are described as follows:</span></span>

<span data-ttu-id="b7bb0-280">![在報表檢視中套用篩選器。](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "在報表檢視中套用篩選器。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-280">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

1.  <span data-ttu-id="b7bb0-281">**名稱** 依 WAN 連結篩選 (篩選位於圖形) 右側。前置詞表示下列連結類型;請參閱垂直 (blue) 方塊：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-281">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>
    
      - <span data-ttu-id="b7bb0-282">**S 網站** 從網路網站到網路地區的 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="b7bb0-282">**S Site** The WAN link from a network site to a network region</span></span>
    
      - <span data-ttu-id="b7bb0-283">**為網站間** 兩個網路網站間的 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="b7bb0-283">**IS Inter-Site** The WAN link between two network sites</span></span>
    
      - <span data-ttu-id="b7bb0-284">**R 區域間** 兩個網路地區之間的 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="b7bb0-284">**R Inter-Region** The WAN link between two network region</span></span>

2.  <span data-ttu-id="b7bb0-285">**超出限制** 依頻寬使用量超過頻寬容量的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="b7bb0-285">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3.  <span data-ttu-id="b7bb0-286">**重要層級** 依頻寬利用率達到90% 或以上頻寬容量的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="b7bb0-286">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4.  <span data-ttu-id="b7bb0-287">**低利用率** 依頻寬利用率低於頻寬容量25% 的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="b7bb0-287">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5.  <span data-ttu-id="b7bb0-288">**連結類型** 依下列 WAN 連結類型進行篩選：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-288">**Link type** Filter by the following WAN links types:</span></span>
    
      - <span data-ttu-id="b7bb0-289">**網路網站** 類型</span><span class="sxs-lookup"><span data-stu-id="b7bb0-289">**Network site** type</span></span>
    
      - <span data-ttu-id="b7bb0-290">**網站間** 類型</span><span class="sxs-lookup"><span data-stu-id="b7bb0-290">**Inter-site** type</span></span>
    
      - <span data-ttu-id="b7bb0-291">**地區間連結** 類型</span><span class="sxs-lookup"><span data-stu-id="b7bb0-291">**Inter-Region link** type</span></span>

6.  <span data-ttu-id="b7bb0-292">**地區** 依網路地區篩選</span><span class="sxs-lookup"><span data-stu-id="b7bb0-292">**Region** Filter by network region</span></span>

<span data-ttu-id="b7bb0-293">下圖顯示先前所述的篩選。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-293">The following figures show the previously described filters.</span></span>

<span data-ttu-id="b7bb0-294">依 **名稱**篩選。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-294">Filter by **Name**.</span></span> <span data-ttu-id="b7bb0-295">選取需要顯示在圖表中的連結清單。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-295">Select the list of links that need to be displayed in the graph.</span></span>

<span data-ttu-id="b7bb0-296">![在 BandwidthUtilizationAnalyzer 中以名稱篩選。](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "在 BandwidthUtilizationAnalyzer 中以名稱篩選。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-296">![Filtering by Name in BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtering by Name in BandwidthUtilizationAnalyzer.")</span></span>

<span data-ttu-id="b7bb0-297">篩選依據 **超出限制**。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-297">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="b7bb0-298">選取 [ **True** ] 以強制執行篩選。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-298">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="b7bb0-299">![以超出限制篩選。](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "以超出限制篩選。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-299">![Filtering by Exceeded Limit.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtering by Exceeded Limit.")</span></span>

<span data-ttu-id="b7bb0-300">依 **重要層級**篩選。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-300">Filter by **Critical levels**.</span></span> <span data-ttu-id="b7bb0-301">選取 [ **True** ] 以強制執行篩選。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-301">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="b7bb0-302">![依重要層級篩選。](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "依重要層級篩選。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-302">![Filtering by Critical Levels.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtering by Critical Levels.")</span></span>

<span data-ttu-id="b7bb0-303">根據 **使用**中的篩選。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-303">Filter by **Under utilized**.</span></span> <span data-ttu-id="b7bb0-304">選取 [ **True** ] 以強制執行篩選。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-304">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="b7bb0-305">![按使用中的篩選。](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "按使用中的篩選。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-305">![Filtering by Under Utilized.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtering by Under Utilized.")</span></span>

<span data-ttu-id="b7bb0-306">依 **連結類型**篩選。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-306">Filter by **Link Type**.</span></span> <span data-ttu-id="b7bb0-307">選取需要顯示的類型或類型。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-307">Select the type or types that need to be displayed.</span></span>

<span data-ttu-id="b7bb0-308">![依連結類型篩選。](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "依連結類型篩選。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-308">![Filtering by Link Type.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtering by Link Type.")</span></span>

<span data-ttu-id="b7bb0-309">依 **地區**篩選。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-309">Filter by **Region**.</span></span> <span data-ttu-id="b7bb0-310">選取需要顯示其連結的區域清單。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-310">Select a list of regions whose links need to be displayed.</span></span>

<span data-ttu-id="b7bb0-311">![依地區篩選。](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "依地區篩選。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-311">![Filtering by Region.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtering by Region.")</span></span>

</div>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b7bb0-312">需求</span><span class="sxs-lookup"><span data-stu-id="b7bb0-312">Requirements</span></span>

  - <span data-ttu-id="b7bb0-313">.NET Framework 3。5</span><span class="sxs-lookup"><span data-stu-id="b7bb0-313">The .NET Framework 3.5</span></span>

  - <span data-ttu-id="b7bb0-314">Microsoft Excel 2010 或 Excel 2007</span><span class="sxs-lookup"><span data-stu-id="b7bb0-314">Microsoft Excel 2010 or Excel 2007</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="b7bb0-315">摘要</span><span class="sxs-lookup"><span data-stu-id="b7bb0-315">Summary</span></span>

<span data-ttu-id="b7bb0-316">頻寬流量分析程式可用來繪製網路上 UC 流量的音訊頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-316">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="b7bb0-317">您也可以使用此工具來報告網路上的視頻頻寬使用方式。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-317">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

</div>

</div>

<div>

## <a name="call-parkometer"></a><span data-ttu-id="b7bb0-318">呼叫 Call parkometer</span><span class="sxs-lookup"><span data-stu-id="b7bb0-318">Call Parkometer</span></span>

<span data-ttu-id="b7bb0-319">「呼叫 Call parkometer」是一種命令列應用程式，可讓您輕鬆存取通話駐留軌道資料庫。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-319">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b7bb0-320">描述</span><span class="sxs-lookup"><span data-stu-id="b7bb0-320">Description</span></span>

<span data-ttu-id="b7bb0-321">「呼叫 Call parkometer 是一種可追蹤目前寄存通話的工具。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-321">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="b7bb0-322">它也會收集有關軌道和通話駐留伺服器 (CPS) 使用狀況的統計資料。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-322">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="b7bb0-323">這個命令列工具既可以從本機或遠端連線的電腦，提供對 CPS 軌道 SQL Server 資料庫的讀取和寫入存取權。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-323">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="b7bb0-324">所有選項都是互斥的。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-324">All options are mutually exclusive.</span></span> <span data-ttu-id="b7bb0-325">命令列語法如下：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-325">Command-line syntax is as follows:</span></span>

  - <span data-ttu-id="b7bb0-326">**– o** 參數--列出為此集區設定的所有軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-326">**–o** parameter—lists all orbit ranges configured for this pool.</span></span>

  - <span data-ttu-id="b7bb0-327">**– n** 參數-列出此集區中所有目前使用的軌道。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-327">**–n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="b7bb0-328">顯示的資訊如下：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-328">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="b7bb0-329">SIP 統一資源識別項 (parkee 和 parker 的 URI) 。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-329">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>
    
      - <span data-ttu-id="b7bb0-330">寄存通話之 CPS 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-330">Host name of the CPS where the call is parked.</span></span>
    
      - <span data-ttu-id="b7bb0-331">寄存通話的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-331">Time stamp of when the call was parked.</span></span>

  - <span data-ttu-id="b7bb0-332">**– f** 參數-列出集區中目前可用的軌道的數目。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-332">**–f** parameter—lists the number of currently free orbits in the pool.</span></span>

  - <span data-ttu-id="b7bb0-333">\*\*– r \<n\> \*\*參數-列出 \<n\> 最後一個寄存的呼叫。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-333">**–r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="b7bb0-334">顯示的資訊如下：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-334">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="b7bb0-335">Parkee SIP URI。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-335">Parkee SIP URI.</span></span>
    
      - <span data-ttu-id="b7bb0-336">Parker SIP URI。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-336">Parker SIP URI.</span></span>
    
      - <span data-ttu-id="b7bb0-337">寄存通話之 CPS 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-337">Host name of the CPS where the call was parked.</span></span>
    
      - <span data-ttu-id="b7bb0-338">檢索或丟棄通話的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-338">Time stamp of when the call was retrieved or dropped.</span></span>

  - <span data-ttu-id="b7bb0-339">\*\*-t \<n\> \*\*參數-測試在資料庫中保留軌道，以顯示指定之軌道編號的隨機性。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-339">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="b7bb0-340">輸出</span><span class="sxs-lookup"><span data-stu-id="b7bb0-340">Output</span></span>

<span data-ttu-id="b7bb0-341">根據在命令提示字元中指定的輸入參數，「呼叫 Call parkometer」會顯示下列輸出：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-341">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

  - <span data-ttu-id="b7bb0-342">為此集區設定的所有軌道範圍</span><span class="sxs-lookup"><span data-stu-id="b7bb0-342">All orbit ranges that are configured for this pool</span></span>

  - <span data-ttu-id="b7bb0-343">目前寄存通話</span><span class="sxs-lookup"><span data-stu-id="b7bb0-343">Currently parked calls</span></span>

  - <span data-ttu-id="b7bb0-344">) 軌道中可用的可用 (數目</span><span class="sxs-lookup"><span data-stu-id="b7bb0-344">Number of free (available) orbits</span></span>

  - <span data-ttu-id="b7bb0-345">最近寄存的通話</span><span class="sxs-lookup"><span data-stu-id="b7bb0-345">Recently parked calls</span></span>

  - <span data-ttu-id="b7bb0-346">用於測試均勻及隨機軌道值的保留軌道</span><span class="sxs-lookup"><span data-stu-id="b7bb0-346">Reserved orbits for testing uniform and random orbit values</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="b7bb0-347">用途</span><span class="sxs-lookup"><span data-stu-id="b7bb0-347">Purpose</span></span>

<span data-ttu-id="b7bb0-348">CPS 工具的目的是提供 CPS 資料庫的命令列存取權。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-348">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="b7bb0-349">管理員可以查看 CPS 使用狀況，並決定指派至集區的軌道數目。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-349">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b7bb0-350">需求</span><span class="sxs-lookup"><span data-stu-id="b7bb0-350">Requirements</span></span>

<span data-ttu-id="b7bb0-351">如果此工具在執行 CPS 的同一部電腦上執行，則不會有任何需求。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-351">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="b7bb0-352">若要在遠端電腦上執行此工具，Lync Server 2013 所使用的 SQL Server 資料庫必須設定為允許遠端存取。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-352">If this tool is run on a remote computer, the SQL Server database used by Lync Server 2013 must be configured to allow remote access.</span></span> <span data-ttu-id="b7bb0-353">必須使用 SQL Server 資料庫連接字串設定 Call parkometer，以連線至集區的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-353">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool’s SQL Server.</span></span> <span data-ttu-id="b7bb0-354">此 SQL Server 資料庫連接字串是定義在設定檔案中 **parkometer.exe.config**。它必須放在 parkometer.exe 所在的相同目錄中。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-354">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="b7bb0-355">下列 XML 檔案是 parkometer.exe.config 的範例。必須設定的參數是「使用者名稱」 (例如，mydomain \\ 系統管理員) 、密碼 (例如，mypassword) 及主機名稱 (例如 myserver) 。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-355">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

## <a name="examples"></a><span data-ttu-id="b7bb0-356">範例</span><span class="sxs-lookup"><span data-stu-id="b7bb0-356">Examples</span></span>

<span data-ttu-id="b7bb0-357">已部署軌道範圍：– o 參數會列出為此集區設定的所有軌道範圍（如圖所示）。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-357">Deployed orbit ranges: the –o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

<span data-ttu-id="b7bb0-358">![「呼叫 Call parkometer 中的軌道範圍。](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "「呼叫 Call parkometer 中的軌道範圍。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-358">![Orbit ranges in Call Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Orbit ranges in Call Parkometer.")</span></span>

<span data-ttu-id="b7bb0-359">目前寄存的呼叫：– n 參數會列出此集區上所有目前使用的軌道（如圖所示）。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-359">Currently parked calls: the –n parameter lists all currently used orbits on this pool as shown</span></span>

<span data-ttu-id="b7bb0-360">![呼叫 Call parkometer 中的目前寄存通話。](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "呼叫 Call parkometer 中的目前寄存通話。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-360">![Currently-parked calls in Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Currently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="b7bb0-361">[自由] 軌道的數目： f 參數會列出集區中目前可用的軌道（如圖所示）數目。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-361">Number of free orbits: the –f parameter lists the number of currently free orbits in the pool as shown</span></span>

<span data-ttu-id="b7bb0-362">![空閒的軌道式按呼叫 Call parkometer。](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "空閒的軌道式按呼叫 Call parkometer。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-362">![Free orbits in Call Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Free orbits in Call Parkometer.")</span></span>

<span data-ttu-id="b7bb0-363">最近寄存的通話：-r \<n\> 參數會列出 \<n\> 最後一個寄存的呼叫，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-363">Recently parked calls: the –r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

<span data-ttu-id="b7bb0-364">![通話 Call parkometer 中最近寄存的通話。](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "通話 Call parkometer 中最近寄存的通話。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-364">![Recently-parked calls in Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Recently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="b7bb0-365">測試軌道保留：– t \<n\> 參數會測試在資料庫中保留軌道（如圖所示）。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-365">Test orbit reservation: the –t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

<span data-ttu-id="b7bb0-366">![在 [呼叫 Call parkometer] 中測試軌道保留。](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "在 [呼叫 Call parkometer] 中測試軌道保留。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-366">![Test orbit reservations in Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Test orbit reservations in Call Parkometer.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="b7bb0-367">摘要</span><span class="sxs-lookup"><span data-stu-id="b7bb0-367">Summary</span></span>

<span data-ttu-id="b7bb0-368">「呼叫 Call parkometer」是一種命令列工具，提供通話駐留伺服器的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-368">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a><span data-ttu-id="b7bb0-369">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="b7bb0-369">CleanupStorageServiceData</span></span>

<span data-ttu-id="b7bb0-370">CleanupStorageServiceData resource 工具組工具可讓您從 Lync Server Storage Service (LYSS) 所使用的資料庫中刪除孤立的資料。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-370">The CleanupStorageServiceData resource kit tool allows for deleting of orphaned data from the database used by the Lync Server Storage Service (LYSS).</span></span> <span data-ttu-id="b7bb0-371">儲存服務的一個功能是緩衝 Lync Server 與各種後端資料儲存端點之間的通訊，如 SQL Server 與 Exchange。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-371">One function of the storage service is to buffer communication between Lync Server and various back-end data storage endpoints, like SQL Server and Exchange.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b7bb0-372">描述</span><span class="sxs-lookup"><span data-stu-id="b7bb0-372">Description</span></span>

<span data-ttu-id="b7bb0-373">為了支援高可用性，LYSS 會暫時接受並儲存集區中多部前端伺服器上的資料複本，並在該資料傳遞至其最終長期儲存位置後，將其移除。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-373">To support high availability, LYSS accepts and saves copies of the data on multiple front end servers in the pool temporarily, and removes that data once it has been delivered to its final long-term storage location.</span></span> <span data-ttu-id="b7bb0-374">在其他情況下，可能會發生一般的情況，當伺服器可能當伺服器損毀或經歷處理問題時，有些資料可能無法正確清除。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-374">There are unusual situations which may occur during otherwise normal operation, when a server might crash or experience a processing issue, and some data might not get cleaned up properly.</span></span> <span data-ttu-id="b7bb0-375">這種資料是無害的，但是會消耗有限的處理資源。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-375">This data is harmless, but it does consume limited processing resources.</span></span> <span data-ttu-id="b7bb0-376">許多正常的必要資料維護都是自動化的，但是此工具允許在無法自動移除時，安全識別及移除這類孤立資料。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-376">Much of the normal required data maintenance is automated, but this tool allows for the safe identification and removal of such orphaned data when automated removal is not possible.</span></span> <span data-ttu-id="b7bb0-377">當健康情況監控 System Center Operations Manager (SCOM) 警示會產生，要求管理員從集區中的本機 LYSS 資料庫中移除不需要的資料時，就會指出使用此工具。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-377">Usage of this tool is indicated when a health monitoring System Center Operations Manager (SCOM) alert is raised which asks the administrator to remove the unneeded data from the local LYSS databases in the pool.</span></span> <span data-ttu-id="b7bb0-378">在觸發警示的前端，事件記錄檔中會有對應的事件。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-378">There will be a corresponding event in the event log on the front end which triggered the alert.</span></span> <span data-ttu-id="b7bb0-379">事件詳細資料會包含前端所包含之孤立資料量的相關資訊，並在該資料超過某些預先決定閾值時引發</span><span class="sxs-lookup"><span data-stu-id="b7bb0-379">The event details will contain information about the amount of orphaned data contained on the front end, and is raised when that data exceeds certain pre-determine thresholds</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b7bb0-380">需求</span><span class="sxs-lookup"><span data-stu-id="b7bb0-380">Requirements</span></span>

<span data-ttu-id="b7bb0-381">安裝 Lync Server 2013，資源工具組工具。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-381">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="b7bb0-382">在已加入網域的機器上，此工具會在安裝 Lync Server 和 Lync Server 2013 管理命令介面的機器上執行。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-382">The tool runs on domain-joined machines where Lync Server and Lync Server 2013 Management Shell are installed.</span></span> <span data-ttu-id="b7bb0-383">此工具使用管理命令介面中的 Cmdlet 來識別集區中的所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-383">The tool uses a cmdlet from the management shell to identify all Front End servers in the pool.</span></span> <span data-ttu-id="b7bb0-384">其次，必須從已安裝 **RtcLocal** 資料庫的集區中的機器執行工具。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-384">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="b7bb0-385">CleanupStorageServiceData 工具使用此資料庫來取得與 Lync Server 路由服務通訊所需的連線詳細資料。最後，呼叫工具的帳戶或憑證必須具有要寫入其輸出記錄檔之檔案共用的讀取/寫入權限。此外，此工具也取決於集區處於穩定狀態。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-385">This database is used by the CleanupStorageServiceData tool to get the connection details needed to communicate with the Lync Server Routing Service.Finally, the account or credential invoking the tool must have read/write permission to the file share to which they want to write the output log.Also, this tool depends on the pool being in a stable state.</span></span> <span data-ttu-id="b7bb0-386">實質上，這表示每一部前端伺服器都預計會啟動並執行，則 SQL Server LYNCLOCAL 實例和 LYSS 資料庫必須能夠連線，且每個路由群組都必須有一組完整的1部前端伺服器和2個次要前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-386">In essence this means that every Front End server is expected to be up and running, the SQL Server LYNCLOCAL instance and LYSS database must be able to be connected to, and each routing group must have a complete set of 1 primary Front End servers and 2 secondary Front End servers.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b7bb0-387">範例</span><span class="sxs-lookup"><span data-stu-id="b7bb0-387">Examples</span></span>

<span data-ttu-id="b7bb0-388">C： \\ Program Files \\ Microsoft Lync Server 2013 \\ ResKit \\ StorageService \> ImportStorageServiceData.exe</span><span class="sxs-lookup"><span data-stu-id="b7bb0-388">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData.exe</span></span>

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

## <a name="dbanalyze"></a><span data-ttu-id="b7bb0-389">Dbanalyze.exe</span><span class="sxs-lookup"><span data-stu-id="b7bb0-389">DBAnalyze</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b7bb0-390">描述</span><span class="sxs-lookup"><span data-stu-id="b7bb0-390">Description</span></span>

<span data-ttu-id="b7bb0-391">Dbanalyze.exe 是一種命令列工具，可協助系統管理員收集 Lync Server 2013 資料庫的分析報告。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-391">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Lync Server 2013 databases.</span></span> <span data-ttu-id="b7bb0-392">Dbanalyze.exe 具有下列模式：診斷、使用者資料、會議、MCUs 和磁片分段：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-392">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

  - <span data-ttu-id="b7bb0-393">**診斷模式**    會建立報表，其中包含資料表 (記錄數目、分散、資料大小及索引大小) 的相關資訊。資料和記錄檔大小、最後的備份時間、執行 Microsoft Office 通訊伺服器的伺服器之間的連絡人散佈、每位使用者的許可權總數、連絡人、容器、訂閱、發佈、每位使用者的端點、預定會議、使用中會議的平均會議數目、每位使用者的排程會議、使用中會議，以及資料庫版本。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-393">**Diagnostic mode**   Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can’t be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b7bb0-394">執行診斷模式可能會影響伺服器效能。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-394">Running diagnostic mode can affect server performance.</span></span>

    
    </div>

  - <span data-ttu-id="b7bb0-395">**使用者資料模式**  針對指定的使用者或使用者在其連絡人及許可權清單中的使用者，報告連絡人、容器、訂閱、發佈、許可權及連絡人群組資料。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-395">**User data mode**  Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="b7bb0-396">這種模式也會報告使用者組織或受到邀之會議的摘要資料。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-396">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

  - <span data-ttu-id="b7bb0-397">**會議模式**    報告特定會議的詳細資料，包括會議、被邀請者清單、會議所允許的媒體類型清單、active MCUs (multipoint 控制項單位) 、作用中的參與者清單，以及每個參與者的信號狀態。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-397">**Conference mode**   Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant’s signaling state.</span></span>

  - <span data-ttu-id="b7bb0-398">**解碼會議識別碼**   會解碼 **/pstnid**參數所指定的公用交換電話網路 (PSTN) 會議識別碼，但不會連線至後端以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-398">**Decode Meeting ID**  Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

  - <span data-ttu-id="b7bb0-399">**解決會議**    會解碼 **/pstnid**參數所指定的 PSTN 會議 ID，並顯示識別碼所指定之會議的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-399">**Resolve conference**   Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

  - <span data-ttu-id="b7bb0-400">**MCUs 模式**   針對集區中的每個 MCU 報告識別碼、媒體類型、URL、心跳狀態、會議載入和參與者負載。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-400">**MCUs mode**  Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

  - <span data-ttu-id="b7bb0-401">**磁片分段模式**   顯示所有磁片的分段狀態。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-401">**Disk fragmentation mode**  Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="b7bb0-402">此工具可用於診斷各種問題，或協助系統管理員進行容量規劃。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-402">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="b7bb0-403">例如，如果在伺服器 A 上大多數的使用者都選擇以伺服器 B 為其連絡人的使用者，則系統管理員可以將伺服器 A 上的使用者移至伺服器 B，以減少跨伺服器的流量。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-403">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="b7bb0-404">輸出</span><span class="sxs-lookup"><span data-stu-id="b7bb0-404">Output</span></span>

<span data-ttu-id="b7bb0-405">此工具會輸出 Lync Server 2013 資料庫的預先定義報告。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-405">This tool outputs predefined reports about the Lync Server 2013 database.</span></span> <span data-ttu-id="b7bb0-406">**路徑：** %ProgramFiles% \\ Microsoft Lync Server 2013 \\ Reskit</span><span class="sxs-lookup"><span data-stu-id="b7bb0-406">**Path:** %ProgramFiles%\\Microsoft Lync Server 2013\\Reskit</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="b7bb0-407">用途</span><span class="sxs-lookup"><span data-stu-id="b7bb0-407">Purpose</span></span>

<span data-ttu-id="b7bb0-408">若要安裝 Dbanalyze.exe，請將它複製到本機資料夾，然後執行工具。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-408">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="b7bb0-409">若要使用此工具，請從命令列執行下列命令。`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span><span class="sxs-lookup"><span data-stu-id="b7bb0-409">To use the tool, run the following command from the command line.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span></span> <span data-ttu-id="b7bb0-410">命令列選項的描述如下所示。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-410">The descriptions for the command-line options are shown below.</span></span>

<span data-ttu-id="b7bb0-411">![Dbanalyze.exe 的命令列選項。](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Dbanalyze.exe 的命令列選項。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-411">![Command line options for Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Command line options for Dbanalyze.exe.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b7bb0-412">需求</span><span class="sxs-lookup"><span data-stu-id="b7bb0-412">Requirements</span></span>

<span data-ttu-id="b7bb0-413">**電腦** Dbanalyze.exe 只能從已安裝 Lync Server 2013 的已加入網域的電腦執行。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-413">**Computer** DBAnalyze can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span>

<span data-ttu-id="b7bb0-414">**網路** 電腦應該可以連接至後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-414">**Network** The computer should be able to connect to the back-end database.</span></span>

<span data-ttu-id="b7bb0-415">**軟體** 在執行 Dbanalyze.exe 之前，必須先安裝 Lync Server 2013 軟體元件。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-415">**Software** Lync Server 2013 software components must be installed before running DBAnalyze.</span></span>

<span data-ttu-id="b7bb0-416">**使用者**下表顯示具有存取 Lync Server 2013 資料庫之必要許可權的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-416">**Users**The table below shows the administrators who have the necessary permissions to access Lync Server 2013 databases.</span></span>

<span data-ttu-id="b7bb0-417">![Dbanalyze.exe 的許可權表格。](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Dbanalyze.exe 的許可權表格。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-417">![Permissions table for Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Permissions table for Dbanalyze.exe.")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b7bb0-418"><STRONG>/Report：磁片</STRONG>模式需要本機系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-418">A local administrator account is required for <STRONG>/report:disk</STRONG> mode.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b7bb0-419">範例</span><span class="sxs-lookup"><span data-stu-id="b7bb0-419">Examples</span></span>

<span data-ttu-id="b7bb0-420">以下是有效 Dbanalyze.exe 命令的範例：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-420">The following are examples of valid Dbanalyze.exe commands:</span></span>

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a><span data-ttu-id="b7bb0-421">摘要</span><span class="sxs-lookup"><span data-stu-id="b7bb0-421">Summary</span></span>

<span data-ttu-id="b7bb0-422">DBAnalyzer 可讓系統管理員快速且容易地分析 Lync Server 2013 資料庫。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-422">DBAnalyzer provides administrators a quick and easy to analyze Lync Server 2013 databases.</span></span>

</div>

</div>

<div>

## <a name="importstorageservicedata"></a><span data-ttu-id="b7bb0-423">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="b7bb0-423">ImportStorageServiceData</span></span>

<span data-ttu-id="b7bb0-424">ImportStorageServiceData 資源工具組工具可讓您重新匯入儲存服務 (LYSS) 回儲存體服務的佇列和端點資料。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-424">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b7bb0-425">描述</span><span class="sxs-lookup"><span data-stu-id="b7bb0-425">Description</span></span>

<span data-ttu-id="b7bb0-426">根據佇列專案狀態或資料庫大小而定，儲存服務所清除的資料可能會自動 (定期) 。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-426">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="b7bb0-427">這可能是因為手動呼叫集區容錯移轉指令 StorageServiceFullFlush，或是集區容錯移轉指令) 所呼叫的 Cmdlet (。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-427">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="b7bb0-428">請注意，如果前端的任何儲存服務 (LYSS ) 資料庫大小高於一般層級以上，則理想情況下不會重新匯入資料，因為這樣做可能只會造成更多資料可傳回輸出。此外，任何可能會導致儲存服務佇列成長之錯誤的問題，都應該先加以解析 (例如 Exchange 端點錯誤、網路問題或其他問題) 。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-428">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

<span data-ttu-id="b7bb0-429">**案例1：** 集區容錯移轉期間，每個前端的檔案可能會從儲存體服務上清除。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-429">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="b7bb0-430">容錯移轉完成後，應執行該工具，以重新匯入資料。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-430">After failover is completed, the tool should be run to re-import the data.</span></span>

<span data-ttu-id="b7bb0-431">**案例2：** 每日自動清除資料，或回應儲存服務資料庫超過一定大小的閾值 ( 例如60%、80%、90% full ) 。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-431">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="b7bb0-432">這會自動清除的資料應該由系統管理員定期重新匯入。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-432">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="b7bb0-433">在上述情況下，如果未部署監控 SCOM 套件，則會有與從儲存體服務刷新之資料相關的 Lync Server Storage Service 事件。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-433">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Lync Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="b7bb0-434">已啟動 32075 (完整清除作業的事件 IDs) ，32076 (完全清除已完成) ，32082 (維護層級清理已開始) ，32083 (維護層級清理完成) ，32089 (因填滿資料庫) 而發生清理。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-434">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="b7bb0-435">請注意，這些事件識別碼會對應至 RTM 版本。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-435">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="b7bb0-436">當系統管理員看到這些事件時，表示已清除的檔案。此資料應該定期使用此工具（例如每週一次）匯入回來。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-436">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="b7bb0-437">在線上服務發行時，如果部署了 Lync Server 的 health monitoring SCOM 套件，則可能會引發新的警示，讓系統管理員將清除的資料重新匯入儲存體服務。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-437">For the Online Service release, if health monitoring SCOM pack for Lync Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="b7bb0-438">在觸發警示的前端伺服器上，事件記錄檔中會有對應的事件。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-438">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="b7bb0-439">此事件會提供清除資料檔案所在之父路徑的描述，以及有多少個可滿足警示準則的檔。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-439">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="b7bb0-440">警示準則是指在特定的父路徑下有 X 個或多個檔案，該預設路徑至少是 Y 天的舊 ( 版本，StorageService 中的 X 和 Y 是預先預置的，但是可以透過變更 APPCONFIG 檔加以覆寫。 ) 下列兩個可能觸發狀況警示的事件範例，其差異是其父項路徑。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-440">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="b7bb0-441">有一種可能的情況是在 Web 服務檔案共用下，另一種可能性是每個前端的本機應用程式資料目錄。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-441">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="b7bb0-442"> ( 例如，c： \\ ProgramData \\ Microsoft \\ Lync Server \\ StorageService ) 。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-442">( for example c:\\ProgramData\\Microsoft\\Lync Server\\StorageService ).</span></span> <span data-ttu-id="b7bb0-443">然後，系統管理員會執行此 reskit 工具。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-443">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="b7bb0-444">此工具會在執行的前端上增加 CPU 和 IO 負載，以及其他前端，在此情況下，資料不是由執行該工具的前端所擁有。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-444">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="b7bb0-445">我們建議您在前端不低於大量 CPU 和 IO 負載（例如峰值時段外）時，runng 此工具。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-445">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="b7bb0-446">其次，此工具可以2到3分鐘，匯入一個資料檔案。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-446">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="b7bb0-447">在評估工具的執行時間時，請務必記住這一點。預設會在檔存放區上顯示工具所產生的詳細記錄檔。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-447">Keep this in mind when estimating how long tool will be running.The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="b7bb0-448">如果沒有報告錯誤，請將其刪除，因為記錄檔可能會是數十 MB 或更多。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-448">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

<span data-ttu-id="b7bb0-449">![儲存區伺服器事件記錄事件範例。](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "儲存區伺服器事件記錄事件範例。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-449">![Sample Storage Server event log events.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Sample Storage Server event log events.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b7bb0-450">需求</span><span class="sxs-lookup"><span data-stu-id="b7bb0-450">Requirements</span></span>

<span data-ttu-id="b7bb0-451">安裝 Lync Server 2013，資源工具組工具。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-451">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="b7bb0-452">工具會在安裝了 Lync Server 和 Lync Server 管理命令介面的已加入網域的機器上執行。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-452">The tool runs on domain-joined machines where Lync Server and Lync Server Management Shell are installed.</span></span> <span data-ttu-id="b7bb0-453">該工具會使用來自管理命令介面的 Cmdlet，識別集區中的所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-453">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="b7bb0-454">其次，必須從已安裝 **RtcLocal** 資料庫的集區中的機器執行工具。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-454">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="b7bb0-455">此資料庫由工具使用，以取得集區的 WEBSERVICE 檔案共用的位置。此外，在使用此工具之前，每一部前端伺服器都必須先在每一部前端伺服器上使用 **Enable-PSRemoting** 啟用 Windows PowerShell 遠端處理，以及執行該工具的機器。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-455">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="b7bb0-456">否則，來自此工具的遠端 Windows PowerShell 命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-456">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="b7bb0-457">在集區完成後，您可以在集區中的所有前端伺服器上關閉 Windows PowerShell 遠端處理。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-457">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="b7bb0-458">最後，開啟工具的帳戶或憑證必須具有可讀取/寫入權限給其在其上執行此工具的集區。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-458">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="b7bb0-459">否則，該工具會失敗，並顯示 IO 許可權錯誤。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-459">Otherwise the tool will fail with IO Permission errors.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b7bb0-460">在 Windows Server 2012 上，Windows PowerShell 遠端處理會預設為啟用，但不會在 Windows Server 2008 作業系統上啟用。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-460">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b7bb0-461">範例</span><span class="sxs-lookup"><span data-stu-id="b7bb0-461">Examples</span></span>

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

## <a name="lcssync"></a><span data-ttu-id="b7bb0-462">LCSSync</span><span class="sxs-lookup"><span data-stu-id="b7bb0-462">LCSSync</span></span>

<span data-ttu-id="b7bb0-463">LCSSync 工具可協助您在多樹系環境中部署 Lync Server 2013 通訊軟體。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-463">The LCSSync tool helps to deploy Lync Server 2013 communications software in a multi-forest environment.</span></span> <span data-ttu-id="b7bb0-464">此工具是用來將不同使用者樹系中的使用者和群組，當作 Active Directory 網域服務連絡人物件同步處理，以安裝 Lync Server 2013 的中央樹系。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-464">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Lync Server 2013 is installed.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b7bb0-465">描述</span><span class="sxs-lookup"><span data-stu-id="b7bb0-465">Description</span></span>

<span data-ttu-id="b7bb0-466">LCSSync 使用中央樹系中的 [同步處理 Active Directory 網域服務] 連絡人物件，以啟用使用者的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-466">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Lync Server.</span></span> <span data-ttu-id="b7bb0-467">若要提供單一登入，主要使用者帳戶必須對應至 Lync Server 2013 中央樹系中的 Active Directory 網域服務連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-467">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Lync Server 2013.</span></span> <span data-ttu-id="b7bb0-468">這個工具可協助您執行該對應。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-468">This tool helps perform that mapping.</span></span> <span data-ttu-id="b7bb0-469">此工具提供範本，以在 Microsoft Identity Integration Server 中建立管理代理程式。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-469">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="b7bb0-470">摘要</span><span class="sxs-lookup"><span data-stu-id="b7bb0-470">Summary</span></span>

<span data-ttu-id="b7bb0-471">LCSSync 工具可協助您在多樹系環境中部署 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-471">The LCSSync tool helps to deploy Lync Server in a multi-forest environment.</span></span>

</div>

</div>

<div>

## <a name="lookupuserconsole"></a><span data-ttu-id="b7bb0-472">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="b7bb0-472">LookupUserConsole</span></span>

<span data-ttu-id="b7bb0-473">LookupUserConsole 工具會顯示特定使用者的內部 Lync Server 路由資訊。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-473">The LookupUserConsole tool displays internal Lync Server routing information about specific users.</span></span> <span data-ttu-id="b7bb0-474">此資訊對 Microsoft 支援個人在診斷部署和路由問題時可能十分有用。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-474">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b7bb0-475">描述</span><span class="sxs-lookup"><span data-stu-id="b7bb0-475">Description</span></span>

<span data-ttu-id="b7bb0-476">執行 LookupUserConsole.exe 會開啟接收 SIP 位址的命令提示字元，並嘗試顯示與其相關的內部 Lync Server 路由資訊。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-476">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Lync Server routing information relating them.</span></span> <span data-ttu-id="b7bb0-477">若要結束 LookupUserConsole 工具，請輸入 **exit** 。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-477">Type **exit** to quit the LookupUserConsole tool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b7bb0-478">需求</span><span class="sxs-lookup"><span data-stu-id="b7bb0-478">Requirements</span></span>

<span data-ttu-id="b7bb0-479">安裝 Lync Server 2013，資源工具組工具。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-479">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="b7bb0-480">在安裝 Lync Server 的已加入網域的機器上執行工具</span><span class="sxs-lookup"><span data-stu-id="b7bb0-480">The tool runs on domain-joined machines where Lync Server is installed</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b7bb0-481">範例</span><span class="sxs-lookup"><span data-stu-id="b7bb0-481">Examples</span></span>

<span data-ttu-id="b7bb0-482">C： \\ Program Files \\ Microsoft Lync Server 2013 \\ ResKit \>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="b7bb0-482">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole.exe</span></span>

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

## <a name="msturnping"></a><span data-ttu-id="b7bb0-483">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="b7bb0-483">MsTurnPing</span></span>

<span data-ttu-id="b7bb0-484">MSTurnPing 工具可讓 Microsoft Lync Server 2013 通訊軟體的系統管理員檢查執行 Audio/Video Edge 的伺服器狀態，並 Audio/Video 驗證服務，以及在拓撲中執行頻寬原則服務的伺服器。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-484">The MSTurnPing tool allows an administrator of Microsoft Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b7bb0-485">描述</span><span class="sxs-lookup"><span data-stu-id="b7bb0-485">Description</span></span>

<span data-ttu-id="b7bb0-486">MSTurnPing 工具可讓 Lync Server 2013 通訊軟體的系統管理員檢查執行 Audio/Video Edge 的伺服器狀態，以及 Audio/Video 驗證服務，以及在拓撲中執行頻寬原則服務的伺服器。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-486">The MSTurnPing tool allows an administrator of Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="b7bb0-487">工具可讓系統管理員執行下列測試：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-487">The tool allows the administrator to perform the following tests:</span></span>

1.  <span data-ttu-id="b7bb0-488">A/V Edge Server 測試：此工具會執行下列作業，針對拓撲中的所有 A/V Edge server 執行測試：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-488">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="b7bb0-489">確認 Lync Server Audio/Video 驗證服務已啟動，且可以發出適當的認證。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-489">Verifying that the Lync Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="b7bb0-490">確認 Lync Server Audio/Video Edge service 已啟動，且可成功地在外部 Edge 上指派資源。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-490">Verifying that the Lync Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2.  <span data-ttu-id="b7bb0-491">頻寬原則服務測試：此工具會透過執行下列動作，對拓撲中執行頻寬原則服務的所有伺服器執行測試：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-491">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="b7bb0-492">驗證 Lync Server 頻寬原則服務 (驗證) 是否已啟動，且可發出適當的認證。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-492">Verifying that the Lync Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="b7bb0-493">驗證 Lync Server 頻寬原則服務 (核心) 是否已啟動，且可成功執行頻寬檢查。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-493">Verifying that the Lync Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="b7bb0-494">此工具必須從屬於拓撲的電腦上執行，且已安裝本機儲存區。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-494">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="b7bb0-495">輸出</span><span class="sxs-lookup"><span data-stu-id="b7bb0-495">Output</span></span>

<span data-ttu-id="b7bb0-496">工具會輸出每個作業的結果。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-496">The tool outputs the results of each of the operations.</span></span>

  - <span data-ttu-id="b7bb0-497">如果執行 **AudioVideoEdgeServer** 測試，則會輸出下列工具：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-497">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="b7bb0-498">在拓撲中提供 Lync Server Audio/Video 驗證服務之電腦的測試結果</span><span class="sxs-lookup"><span data-stu-id="b7bb0-498">The test results of the computers that provide the Lync Server Audio/Video Authentication service in the topology</span></span>
    
      - <span data-ttu-id="b7bb0-499">在拓撲中提供 Lync Server Audio/Video Edge service 之電腦的測試結果</span><span class="sxs-lookup"><span data-stu-id="b7bb0-499">The test results of the computers that provide the Lync Server Audio/Video Edge service in the topology</span></span>

  - <span data-ttu-id="b7bb0-500">如果執行 **BandwidthPolicyServer** 測試，則會輸出下列工具：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-500">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="b7bb0-501">在拓撲中提供 Lync Server 頻寬原則服務 (驗證) 的電腦測試結果</span><span class="sxs-lookup"><span data-stu-id="b7bb0-501">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Authentication) in the topology</span></span>
    
      - <span data-ttu-id="b7bb0-502">在拓撲中提供 Lync Server 頻寬原則服務 (核心) 之電腦的測試結果</span><span class="sxs-lookup"><span data-stu-id="b7bb0-502">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Core) in the topology</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b7bb0-503">需求</span><span class="sxs-lookup"><span data-stu-id="b7bb0-503">Requirements</span></span>

  - <span data-ttu-id="b7bb0-504">此工具必須從拓撲中的電腦執行，且具有本機儲存區。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-504">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

  - <span data-ttu-id="b7bb0-505">您必須以具有本機儲存區存取權的系統管理員身分執行工具。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-505">The tool must be run as an administrator who has access to the local store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b7bb0-506">範例</span><span class="sxs-lookup"><span data-stu-id="b7bb0-506">Examples</span></span>

<span data-ttu-id="b7bb0-507">下列為工具輸入的範例。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-507">The following is an example of the tool input.</span></span>

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a><span data-ttu-id="b7bb0-508">摘要</span><span class="sxs-lookup"><span data-stu-id="b7bb0-508">Summary</span></span>

<span data-ttu-id="b7bb0-509">這項工具對於 Lync Server 2013 系統管理員而言是一項寶貴資源，可供您檢查執行音訊/影片和頻寬原則服務之伺服器的狀態。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-509">This tool can be a valuable resource to Lync Server 2013 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a><span data-ttu-id="b7bb0-510">網路設定檢視器</span><span class="sxs-lookup"><span data-stu-id="b7bb0-510">Network Configuration Viewer</span></span>

<span data-ttu-id="b7bb0-511">Microsoft Lync Server 2013 通訊軟體管理員可以使用網路設定檢視器來查看已布建的企業的通話許可控制 (CAC) 網路拓撲，以允許即時通訊會話，例如根據指定的頻寬容量進行語音或視頻通話。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-511">Network Configuration Viewer can be used by Microsoft Lync Server 2013 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="b7bb0-512">Lync Server 2013 系統管理員會定義 CAC 原則，這些原則是由隨 Lync Server 2013 一起安裝的頻寬原則服務所強制執行。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-512">Lync Server 2013 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Lync Server 2013.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b7bb0-513">描述</span><span class="sxs-lookup"><span data-stu-id="b7bb0-513">Description</span></span>

<span data-ttu-id="b7bb0-514">網路設定檢視器 ( # A0) 可讓系統管理員執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-514">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

  - <span data-ttu-id="b7bb0-515">從 Lync Server 2013 部署中，以圖形格式載入和查看 CAC 網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-515">Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format.</span></span>

  - <span data-ttu-id="b7bb0-516">從頻寬原則伺服器記錄檔以圖形格式載入和查看 CAC 網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-516">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

  - <span data-ttu-id="b7bb0-517">以 XML 格式將 CAC 網路拓撲儲存及儲存在磁片上。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-517">Save and store CAC network topology in an XML format on the disk.</span></span>

  - <span data-ttu-id="b7bb0-518">以 JPG 或 BMP 格式儲存和儲存 CAC 網路拓撲圖表。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-518">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

  - <span data-ttu-id="b7bb0-519">查看 CAC 網路拓撲設定資料。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-519">View CAC network topology configuration data.</span></span>

  - <span data-ttu-id="b7bb0-520">以樹狀目錄模式顯示 CAC 網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-520">View CAC network topology in a tree-view style.</span></span>

  - <span data-ttu-id="b7bb0-521">針對 CAC 網路拓撲連結定義自訂連接器 (例如，網站對地區、區域對地區及網站對站台連結) 。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-521">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

  - <span data-ttu-id="b7bb0-522">流覽 CAC 網路拓撲網站資訊、地區資訊，以及布建的頻寬原則和網路連結。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-522">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="b7bb0-523">用途</span><span class="sxs-lookup"><span data-stu-id="b7bb0-523">Purpose</span></span>

<span data-ttu-id="b7bb0-524">在圖形化介面中查看企業 CAC 網路拓撲連結。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-524">View enterprise CAC network topology links in a graphical interface.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b7bb0-525">範例</span><span class="sxs-lookup"><span data-stu-id="b7bb0-525">Examples</span></span>

<span data-ttu-id="b7bb0-526">**從 Lync Server 2013 部署中，以圖形格式載入和查看 CAC 網路拓撲：** Lync Server 2013 系統管理員可以使用 [ **下載網路** 設定] 選項，在任何 Lync server 2013 電腦上載入及流覽 CAC 網路拓撲設定，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-526">**Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format:** Lync Server 2013 administrators can load and view CAC network topology configuration on any Lync Server 2013 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="b7bb0-527">在未連接至 Lync 設定存放區的電腦上部署時，工具將無法下載或查看此類設定。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-527">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Lync configuration store.</span></span>

<span data-ttu-id="b7bb0-528">![下載網路設定。](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "下載網路設定。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-528">![Downloading the network configuration.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Downloading the network configuration.")</span></span>

<span data-ttu-id="b7bb0-529">**從頻寬原則伺服器記錄檔以圖形格式載入和查看 CAC 網路拓撲：** Lync Server 2013 頻寬原則伺服器會將 CAC 網路拓撲儲存為 Lync Server 2013 檔案共用位置的記錄機制的一部分。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-529">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Lync Server 2013 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Lync Server 2013 file share location.</span></span> <span data-ttu-id="b7bb0-530">Lync Server 系統管理員可以使用如下所示的「 **開放網路** 設定」選項，以圖形格式來查看這類檔案。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-530">Lync Server administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

<span data-ttu-id="b7bb0-531">![開啟頻寬原則伺服器記錄檔。](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "開啟頻寬原則伺服器記錄檔。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-531">![Opening a Bandwidth Policy Server log file.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Opening a Bandwidth Policy Server log file.")</span></span>

<span data-ttu-id="b7bb0-532">在磁片上以 XML 格式儲存及儲存 CAC 網路拓撲： Lync Server 2013 系統管理員可以使用 [ **儲存網路設定的副本** ] 選項，以 xml 格式儲存 cac 網路拓撲設定檔，如下所示。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-532">Save and store CAC network topology in an XML format on the disk: Lync Server 2013 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="b7bb0-533">然後，已儲存的設定檔便可供離線使用，以供圖形化查看之用。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-533">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

<span data-ttu-id="b7bb0-534">![將網路設定儲存為 XML 檔案。](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "將網路設定儲存為 XML 檔案。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-534">![Saving the network configuration as an XML file.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Saving the network configuration as an XML file.")</span></span>

<span data-ttu-id="b7bb0-535">以 JPG 或 BMP 格式儲存及儲存 CAC 網路拓撲圖表： Lync Server 2013 系統管理員可以使用 [ **另存網路設定圖表為圖片** ] 選項，將 cac 網路拓撲設定儲存為圖形格式 (JPG 及 bmp 檔案格式) ，如下所示。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-535">Save and Store CAC network topology diagram in JPG or BMP format: Lync Server 2013 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

<span data-ttu-id="b7bb0-536">![將網路設定儲存為圖片。](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "將網路設定儲存為圖片。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-536">![Saving the network configuration as a picture.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Saving the network configuration as a picture.")</span></span>

<span data-ttu-id="b7bb0-537">**查看 CAC 網路拓撲設定資料：** Lync Server 2013 系統管理員可以使用如下所示的 [查看網路設定資料] 選項，以文字格式查看相關網路設定資料，例如網路地區、網路網站、頻寬設定檔及網站子網 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-537">**View CAC network topology configuration data:** Lync Server 2013 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

<span data-ttu-id="b7bb0-538">![查看網路設定資料。](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "查看網路設定資料。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-538">![Viewing network configuration data.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Viewing network configuration data.")</span></span>

<span data-ttu-id="b7bb0-539">**以樹狀目錄查看樣式中的 CAC 網路拓朴模式：** Lync Server 2013 系統管理員可以使用工具視窗左邊的 [控制台]，以圖形樹狀檢視樣式來查看相關的網路設定資料，如下所示。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-539">**View CAC network topology in a tree-view style:** Lync Server 2013 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

<span data-ttu-id="b7bb0-540">![以樹狀目錄查看網路設定資料。](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "以樹狀目錄查看網路設定資料。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-540">![Viewing network configuration data in a tree-view.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Viewing network configuration data in a tree-view.")</span></span>

<span data-ttu-id="b7bb0-541">**針對 CAC 網路拓撲連結定義自訂連接器， (例如「點對點」、「地區對** 地區」及「點對點」連結) ：Lync Server 2013 系統管理員可以使用如下所示的 [設定] 選項，定義 CAC 網路設定 WAN 連結的自訂圖形連接器。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-541">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Lync Server 2013 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="b7bb0-542">這有助於區分網路設定中布建的各種網路連結類型。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-542">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

<span data-ttu-id="b7bb0-543">![定義 CAC 網路拓朴的自訂連接器](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "定義 CAC 網路拓朴的自訂連接器")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-543">![Define custom connectors for CAC network topology](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Define custom connectors for CAC network topology")</span></span>

<span data-ttu-id="b7bb0-544">**查看 CAC 網路拓撲網站資訊、區域資訊，以及布建的頻寬原則：** Lync Server 2013 系統管理員可以使用如下所示的選項，查看相關 CAC 網路地區資訊、網站資訊和 CAC 頻寬布建資訊。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-544">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Lync Server 2013 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="b7bb0-545"> (例如，按一下 [網路地區] 或 [網路網站物件] 中的 [ **資訊** ]。 ) </span><span class="sxs-lookup"><span data-stu-id="b7bb0-545">(For example, click **Info** in a network region or network site object.)</span></span>

<span data-ttu-id="b7bb0-546">![為您的網路定義自訂連接器。](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "為您的網路定義自訂連接器。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-546">![Defining custom connectors for your network.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Defining custom connectors for your network.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="b7bb0-547">摘要</span><span class="sxs-lookup"><span data-stu-id="b7bb0-547">Summary</span></span>

<span data-ttu-id="b7bb0-548">此工具對於 Lync Server 2013 系統管理員而言是一項寶貴資源，想要以圖形格式查看其部署的 CAC 網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-548">This tool can be a valuable resource to Lync Server 2013 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

</div>

</div>

<div>

## <a name="response-group-agent-live"></a><span data-ttu-id="b7bb0-549">回應群組代理程式 Live</span><span class="sxs-lookup"><span data-stu-id="b7bb0-549">Response Group Agent Live</span></span>

<span data-ttu-id="b7bb0-550">回應群組應用程式讓代理人能夠使用內建的 Web 服務來存取有用的即時資訊。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-550">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="b7bb0-551">不幸的是，在應用程式外沒有此資料的圖形視圖。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-551">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="b7bb0-552">回應群組代理程式 Live Resource tool 工具可提供一種簡單且圖形的方式來存取此資訊，並利用即時 Microsoft Lync 2013 通訊軟體資訊（例如其他代理程式的存在性）進行增強，以解決此問題。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-552">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Microsoft Lync 2013 communications software information such as the presence of other agents.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b7bb0-553">描述</span><span class="sxs-lookup"><span data-stu-id="b7bb0-553">Description</span></span>

<span data-ttu-id="b7bb0-554">回應群組代理程式 Live 是一種 Windows 應用程式，可提供登入和登出功能，以及一些即時資訊 (例如群組成員資格和目前的呼叫數目，) 回應群組代理程式。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-554">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="b7bb0-555">它應為增強版本的「代理群組」頁面 (可從 Lync 2013 存取。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-555">It is meant to be an enhanced version of the Agent Groups page (accessible from Lync 2013.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="b7bb0-556">用途</span><span class="sxs-lookup"><span data-stu-id="b7bb0-556">Purpose</span></span>

<span data-ttu-id="b7bb0-557">回應群組應用程式會對來電進行佇列，然後將來電路由傳送至代理人群組。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-557">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="b7bb0-558">若要對服務叫用的相關決策做出合理決策，代理人可以存取有關其代理群組的即時資訊，例如哪些其他代理程式可用，以及每個佇列中有多少來電等候。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-558">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="b7bb0-559">此資訊最初隻會透過回應群組服務進行存取，可透過回應群組代理程式即時以直觀方式取得。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-559">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

<div>

## <a name="features"></a><span data-ttu-id="b7bb0-560">功能</span><span class="sxs-lookup"><span data-stu-id="b7bb0-560">Features</span></span>

<span data-ttu-id="b7bb0-561">回應群組代理程式 Live tool 是在回應群組服務和 Microsoft Lync 2013 SDK 上建立的。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-561">The Response Group Agent Live tool is built on the Response Group service and the Microsoft Lync 2013 SDK.</span></span> <span data-ttu-id="b7bb0-562">它提供回應群組代理程式所提供的資訊和功能 (例如群組成員資格、其他代理程式的狀態，以及等候通話的數目) 。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-562">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="b7bb0-563">下圖顯示回應群組代理程式的主要介面。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-563">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

<span data-ttu-id="b7bb0-564">![回應群組代理程式 Live 工具。](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "回應群組代理程式 Live 工具。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-564">![The Response Group Agent Live tool.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "The Response Group Agent Live tool.")</span></span>

<span data-ttu-id="b7bb0-565">下列三個主要功能適用于回應群組代理程式 Live 中的代理程式：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-565">The following three main features are available for agents in Response Group Agent Live:</span></span>

  - <span data-ttu-id="b7bb0-566">登**入/登出：** 相反于「代理人群組」頁面 (可從 Lync 2013 存取) ，回應群組代理程式 Live 只允許代理程式一次登入或登出所有代理程式群組。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-566">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Lync 2013), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="b7bb0-567">此應用程式提供三種快速的代理人登入或登出方式：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-567">This application provides three quick ways for agents to sign in or out:</span></span>
    
      - <span data-ttu-id="b7bb0-568">在應用程式內，按一下登入/簽出 (綠色和紅色) 按鈕。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-568">Click the Sign-in/out (green and red) buttons within the application.</span></span>
    
      - <span data-ttu-id="b7bb0-569">以滑鼠右鍵按一下系統工作列圖示，然後選取 [登入] 或 [登出]。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-569">Right-click the system tray icon, and select sign in or sign out.</span></span>
    
      - <span data-ttu-id="b7bb0-570">使用可設定的鍵盤快速鍵。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-570">Using configurable keyboard shortcuts.</span></span>

  - <span data-ttu-id="b7bb0-571">**群組成員資格：** 當選中代理人群組時，回應群組代理程式 Live 會在右側窗格中顯示此群組中的代理程式清單。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-571">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="b7bb0-572">如果 Lync 2013 與此應用程式在同一部電腦上執行，顯示狀態資訊和連絡人卡片會顯示在 [回應群組代理程式 Live] 中。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-572">If Lync 2013 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="b7bb0-573">代理程式可以直接從那裡傳送 IM 或呼叫其他代理程式。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-573">Agents can send an IM or call other agents directly from there.</span></span>

  - <span data-ttu-id="b7bb0-574">**即時統計資料：** 回應群組代理程式 Live 為所有代理程式群組提供即時統計資料。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-574">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="b7bb0-575">更新頻率為一分鐘。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-575">The update frequency is one minute.</span></span> <span data-ttu-id="b7bb0-576">當回應群組接聽來電時，會在具有目前佇列通話數目的組名旁邊新增視覺指示器。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-576">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="b7bb0-577">在群組上暫停指標也會顯示最長的等待時間。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-577">Pausing the pointer over a group also displays the longest waiting time.</span></span>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b7bb0-578">需求</span><span class="sxs-lookup"><span data-stu-id="b7bb0-578">Requirements</span></span>

<span data-ttu-id="b7bb0-579">回應群組代理程式 Live 需要 .NET Framework 4.0。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-579">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="b7bb0-580">此外，若要利用目前狀態和連絡人卡片的功能，必須在本機安裝 Lync 2013 (並執行) 。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-580">In addition, to take advantage of the presence and contact card features, Lync 2013 must be installed locally (and be running).</span></span>

<div>

## <a name="configuration"></a><span data-ttu-id="b7bb0-581">組態</span><span class="sxs-lookup"><span data-stu-id="b7bb0-581">Configuration</span></span>

<span data-ttu-id="b7bb0-582">回應群組代理程式 Live 可透過應用程式中的 [選項] 對話方塊，自訂為個別喜好設定。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-582">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="b7bb0-583">此外，管理員可以直接編輯 RGAgentLive.exe.config 檔案的 defaultHostAddress 屬性，來定義預設的主機位址。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-583">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="b7bb0-584">下圖說明代理可用於設定主機位址及快速鍵的 [選項] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-584">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="b7bb0-585">按一下主介面右上方的 [選項] 按鈕即可存取此對話方塊。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-585">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

<span data-ttu-id="b7bb0-586">![[回應群組代理程式即時選項] 對話方塊。](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "[回應群組代理程式即時選項] 對話方塊。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-586">![The Response Group Agent Live Options dialog box.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "The Response Group Agent Live Options dialog box.")</span></span>

<span data-ttu-id="b7bb0-587">在回應群組代理程式 Live 設定中，可以自訂下列三個不同的設定：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-587">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

  - <span data-ttu-id="b7bb0-588">主機位址：這通常是屬於代理人主集區的網頁集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-588">Host address: This is typically the web pool FQDN belonging to the agent’s home pool.</span></span> <span data-ttu-id="b7bb0-589">在此資訊的背景中，會自動派生確切的回應群組服務位址 (方式是在主機) 之後附加正確路徑。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-589">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

  - <span data-ttu-id="b7bb0-590">快捷方式：可以自訂登入/登出的確切快捷方式。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-590">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="b7bb0-591">唯一的限制是兩個快捷方式除了至少要包含另一個按鍵) 之外，都必須包含 "Windows 徽標鍵" 金鑰 (。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-591">The only limitation is that both shortcuts must contain the “Windows Logo” key (in addition to at least another key).</span></span>

  - <span data-ttu-id="b7bb0-592">開始使用 Windows：應用程式可以設定為以 Windows 自動啟動。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-592">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b7bb0-593">範例</span><span class="sxs-lookup"><span data-stu-id="b7bb0-593">Examples</span></span>

<span data-ttu-id="b7bb0-594">下圖說明如何使用滑鼠右鍵按一下右窗格中的連絡人，撥打或傳送 IM 給另一個代理。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-594">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

<span data-ttu-id="b7bb0-595">![進行通話或傳送 IM。](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "進行通話或傳送 IM。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-595">![Making a call or sending an IM.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Making a call or sending an IM.")</span></span>

<span data-ttu-id="b7bb0-596">下圖說明回應群組代理程式 Live 如何顯示目前佇列中的呼叫數目，以及所有來電間的最長等待時間。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-596">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

<span data-ttu-id="b7bb0-597">![查看佇列資訊。](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "查看佇列資訊。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-597">![Viewing queue information.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Viewing queue information.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="b7bb0-598">摘要</span><span class="sxs-lookup"><span data-stu-id="b7bb0-598">Summary</span></span>

<span data-ttu-id="b7bb0-599">快登入和登出、群組成員資格及基本即時統計資料，都是只會在應用程式從回應群組服務外使用的回應群組代理功能。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-599">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="b7bb0-600">透過「回應群組代理程式 Live Resource 工具組」工具，Lync 系統管理員可以透過 Windows 應用程式提供其代理程式，讓他們能夠以更快速且圖形的方式執行工作。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-600">With the Response Group Agent Live Resource Kit tool, Lync administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

</div>

</div>

<div>

## <a name="sefautil"></a><span data-ttu-id="b7bb0-601">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="b7bb0-601">SEFAUtil</span></span>

<span data-ttu-id="b7bb0-602">SEFAUtil (次要擴充功能啟動) 是一種命令列工具，可讓 Microsoft Lync Server 2013 通訊軟體管理員和技術支援人員代理程式代表 Lync Server 2013 使用者設定代理人震鈴、來電轉接、同時震鈴、小組通話設定和群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-602">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Microsoft Lync Server 2013 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="b7bb0-603">工具也可讓系統管理員查詢特定使用者所發佈的呼叫路由設定。SEFAUtil 工具可讓系統管理員為使用者啟用/停用/修改來電轉接或同時震鈴。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-603">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="b7bb0-604">管理員可以指定目標 (，格式為 SIP URI) 或使用已由使用者所發佈的目標。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-604">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="b7bb0-605">這個工具也可讓系統管理員代表使用者新增或移除代理人或小組通話群組成員。此工具是在 Microsoft 整合通訊 Managed API (UCMA) 3.0，並要求系統管理員在中央管理存放區中為 SEFAUtil 建立信任的應用程式</span><span class="sxs-lookup"><span data-stu-id="b7bb0-605">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil</span></span>

<span data-ttu-id="b7bb0-606">SEFAUtil (次要擴充功能啟動) 可讓 Lync Server 2013 系統管理員和支援人員代理程式，以 Lync Server 2013 使用者的身分，設定代理人震鈴、來電轉接、同時震鈴、小組通話設定和群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-606">SEFAUtil (secondary extension feature activation) enables Lync Server 2013 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="b7bb0-607">這個工具也可讓系統管理員查詢針對特定使用者所發佈的呼叫路由設定。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-607">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b7bb0-608">描述</span><span class="sxs-lookup"><span data-stu-id="b7bb0-608">Description</span></span>

<span data-ttu-id="b7bb0-609">目前的 SEFAUtil 版本只是一個命令列工具;沒有支援的圖形使用者介面。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-609">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="b7bb0-610">此工具是以 Microsoft 整合通訊 Managed API (UCMA) 3.0 為基礎。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-610">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="b7bb0-611">此工具中的功能可讓系統管理員和支援人員執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-611">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

  - <span data-ttu-id="b7bb0-612">View a user 的所有通話路由設定 (包括來電轉接、委派、同時震鈴、小組通話和群組通話收取) </span><span class="sxs-lookup"><span data-stu-id="b7bb0-612">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

  - <span data-ttu-id="b7bb0-613">啟用/停用/修改來電轉接設定 (包括目的地及無回應計時器) </span><span class="sxs-lookup"><span data-stu-id="b7bb0-613">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

  - <span data-ttu-id="b7bb0-614">啟用/停用/修改來電轉接立即設定</span><span class="sxs-lookup"><span data-stu-id="b7bb0-614">Enable/disable/modify call-forwarding immediate configurations</span></span>

  - <span data-ttu-id="b7bb0-615">啟用/停用/修改委派設定</span><span class="sxs-lookup"><span data-stu-id="b7bb0-615">Enable/disable/modify delegation settings</span></span>

  - <span data-ttu-id="b7bb0-616">啟用/停用/修改小組-通話群組設定</span><span class="sxs-lookup"><span data-stu-id="b7bb0-616">Enable/disable/modify team-call group settings</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b7bb0-617">Lync Server 2013 SEFAUtil 工具中的新增功能</span><span class="sxs-lookup"><span data-stu-id="b7bb0-617">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="b7bb0-618">啟用/停用/修改同時震鈴設定 (包括目的地) </span><span class="sxs-lookup"><span data-stu-id="b7bb0-618">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b7bb0-619">Lync Server 2013 SEFAUtil 工具中的新增功能</span><span class="sxs-lookup"><span data-stu-id="b7bb0-619">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="b7bb0-620">啟用/停用/修改群組呼叫收取設定</span><span class="sxs-lookup"><span data-stu-id="b7bb0-620">Enable/disable/modify group call pickup settings</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="b7bb0-621">Lync Server 2013 SEFAUtil 工具中的新增功能</span><span class="sxs-lookup"><span data-stu-id="b7bb0-621">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

<span data-ttu-id="b7bb0-622">此工具具有下列限制：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-622">This tool has the following limitations:</span></span>

  - <span data-ttu-id="b7bb0-623">僅支援駐留在 Lync Server 集區中的使用者</span><span class="sxs-lookup"><span data-stu-id="b7bb0-623">Supported only for users homed in a Lync Server pool</span></span>

  - <span data-ttu-id="b7bb0-624">不支援多個使用者的通話路由設定的大量編輯</span><span class="sxs-lookup"><span data-stu-id="b7bb0-624">Bulk-edit of call routing settings for several users is not supported</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="b7bb0-625">輸出</span><span class="sxs-lookup"><span data-stu-id="b7bb0-625">Output</span></span>

<span data-ttu-id="b7bb0-626">這個工具目前的版本只會在命令提示字元視窗中提供輸出。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-626">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="b7bb0-627">如需詳細資訊，請參閱本檔稍後的範例一節。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-627">For details, see the Examples section later in this document.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="b7bb0-628">用途</span><span class="sxs-lookup"><span data-stu-id="b7bb0-628">Purpose</span></span>

<span data-ttu-id="b7bb0-629">以下是一些可能使用此工具的主要案例：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-629">Following are some of the key scenarios where this tool may be used:</span></span>

  - <span data-ttu-id="b7bb0-630">王俊元是一種主管，已移至 Lync Server 電話語音。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-630">Bob is an executive and has been moved to Lync Server telephony.</span></span> <span data-ttu-id="b7bb0-631">他已在現有的 PBX 系統上進行委派。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-631">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="b7bb0-632">在移動至 Lync 時，系統管理員可以設定王俊元的路由，以反映其預先存在的委派設定。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-632">As part of the move to Lync, the administrator is able to configure Bob’s routing to reflect his pre-existing delegation configuration.</span></span>

  - <span data-ttu-id="b7bb0-633">劉愛琳正在行動，意識到她期望來自他客戶的一項重要通話。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-633">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="b7bb0-634">不過，她位於酒店，而且無法存取電腦。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-634">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="b7bb0-635">她撥打説明台，並要求他們將來電轉接給她的行動電話號碼。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-635">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="b7bb0-636">服務台人員可以代表她執行設定。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-636">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

  - <span data-ttu-id="b7bb0-637">Joe 在工作時，他們的工作號碼會進入行動語音信箱。不過，在大多數其他位置中看起來似乎正常運作。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-637">Joe’s calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="b7bb0-638">説明台技術人員可以查看 Joe 的路由設定，並探索李先生已設定為行動電話的同時震鈴。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-638">The helpdesk technician is able to view Joe’s routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="b7bb0-639">技術人員會詢問 Joe 有關其辦公室內行動覆蓋率的資訊，並且能夠判斷同時響鈴的規則，也就是當網路服務品質不良的情況時，會導致來電進入 Joe 的行動電話語音信箱。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-639">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe’s mobile voicemail when his network coverage is poor.</span></span>

  - <span data-ttu-id="b7bb0-640">Mike 是 Contoso 的新員工，他加入新的小組，其所有成員皆為「小組通話」，當為 Microsoft Lync 啟用時，系統管理員可以將他的小組通話群組設定設定為包含所有的新小組成員，此外，系統管理員也會新增 Mike 作為小組中每個成員的小組通話群組成員。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-640">Mike is a new employee at Contoso and he’s joining a new team on which all members are configured for team-call, when being enabled for Microsoft Lync, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

  - <span data-ttu-id="b7bb0-641">在 Contoso 的人力資源部門中，客戶服務實踐是為自第一次呼叫後的所有來電者提供個人服務。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-641">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="b7bb0-642">假設部門的所有成員都非常接近對方，當小組通話同時撥打所有電話時，就會對小組造成中斷。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-642">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="b7bb0-643">為了提供最佳服務，而不中斷團隊成員的使用，Lync 系統管理員會利用「群組呼叫收取」功能。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-643">To provide the best service without disrupting the team members, the Lync administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="b7bb0-644">系統管理員會將所有部門成員新增至收取群組，並與該部門通訊收取群組編號。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-644">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="b7bb0-645">當她的辦公桌沒有 Samantha 時，Joe 會通知她的電話鈴聲，他會繼續接聽他的電話。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-645">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b7bb0-646">需求</span><span class="sxs-lookup"><span data-stu-id="b7bb0-646">Requirements</span></span>

<span data-ttu-id="b7bb0-647">SEFAUtil 工具只能在屬於受信任應用程式集區一部分的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-647">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="b7bb0-648">UCMA 3.0 必須安裝在該電腦上。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-648">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="b7bb0-649">若要執行此工具，必須在該集區上建立具有 SEFAUtil 應用程式識別碼的新信任應用程式。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-649">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

<span data-ttu-id="b7bb0-650">**為 SEFAUtil 工具建立新的信任應用程式**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-650">**Creating a new Trusted Application for the SEFAUtil tool**</span></span>

1.  <span data-ttu-id="b7bb0-651">SEFAUTil 工具只能在屬於受信任應用程式集區一部分的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-651">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="b7bb0-652">如有需要，您可以透過 Lync Server 管理命令介面將集區新增至新的受信任應用程式集區，其 Cmdlet 如下：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-652">If needed, adding a pool as a new trusted application pool can be done via the Lync Server Management Shell with the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b7bb0-653">UCMA 3.0 必須安裝在將用來執行 SEFAUtil 工具的任何電腦上。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-653">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

    
    </div>

2.  <span data-ttu-id="b7bb0-654">在 SEFAUtil 工具的拓撲中，必須定義信任的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-654">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="b7bb0-655">若要將 SEFAUtil 定義為新的受信任應用程式，請使用 Lync Server 管理命令介面，並執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-655">To define SEFAUtil as a new trusted application, use the Lync Server Management Shell and execute the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b7bb0-656">您可以視需要使用不同的埠。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-656">A different port can be used if needed.</span></span>

    
    </div>

3.  <span data-ttu-id="b7bb0-657">需要啟用拓撲變更。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-657">The topology changes need to be enabled.</span></span> <span data-ttu-id="b7bb0-658">您可以執行下列 Cmdlet，透過 Lync Server 管理命令介面來啟用拓撲變更：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-658">Enabling the topology changes can be done via the Lync Server Management Shell by executing the following cmdlet:</span></span>
    
        Enable-CsToplogy

4.  <span data-ttu-id="b7bb0-659">如有需要，在伺服器上安裝 Lync Server 2013 資源工具組工具，以用於執行 SEFAUtil 工具 (伺服器必須是信任的應用程式集區) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-659">If needed, install the Lync Server 2013 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5.  <span data-ttu-id="b7bb0-660">驗證 SEFAUtil 是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-660">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="b7bb0-661">若要執行此動作，請從使用管理員許可權的 windows 命令提示字元執行工具，以顯示部署中使用者的「來電轉接」設定。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-661">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="b7bb0-662">依預設，工具將位於： "... \\Program Files \\ Microsoft Lync Server 2013 \\ Reskit "。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-662">By default the tool will be located in: “…\\Program Files\\Microsoft Lync Server 2013\\Reskit”.</span></span> <span data-ttu-id="b7bb0-663">若要顯示使用者的「來電轉接」設定，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-663">To display the call forwarding settings of a user, use the following command:</span></span>
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    <span data-ttu-id="b7bb0-664">應該顯示使用者的「來電轉接」設定。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-664">The call forwarding settings of the user should be displayed.</span></span>

<div>

## <a name="group-call-pickup"></a><span data-ttu-id="b7bb0-665">群組來電接聽</span><span class="sxs-lookup"><span data-stu-id="b7bb0-665">Group Call Pickup</span></span>

<span data-ttu-id="b7bb0-666">群組呼叫收取需要在 Lync Server 中進行其他設定，才能充分啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-666">Group Call Pickup requires additional configuration in Lync Server for the capability to be fully enabled.</span></span> <span data-ttu-id="b7bb0-667">在指派收取群組給使用者之前，請參閱群組的「呼叫收取產品檔」，以取得這項功能的規劃及部署步驟。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-667">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b7bb0-668">範例</span><span class="sxs-lookup"><span data-stu-id="b7bb0-668">Examples</span></span>

<div>

## <a name="display-current-call-handling-settings"></a><span data-ttu-id="b7bb0-669">顯示目前的通話處理設定</span><span class="sxs-lookup"><span data-stu-id="b7bb0-669">Display Current Call Handling Settings</span></span>

<span data-ttu-id="b7bb0-670">下列命令會顯示使用者的通話處理。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-670">The following command displays the call handling for the user.</span></span> `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> <span data-ttu-id="b7bb0-671">本範例會使用 <STRONG>/server</STRONG> 參數來指定要連接的 Lync server。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-671">This example uses the <STRONG>/server</STRONG> switch to specify the Lync Server to connect to.</span></span>



</div>

<span data-ttu-id="b7bb0-672">**輸出**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-672">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="b7bb0-673">設定來電轉接/無應答目的地</span><span class="sxs-lookup"><span data-stu-id="b7bb0-673">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="b7bb0-674">本範例會設定來電轉寄/無應答目的地和震鈴延遲。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-674">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="b7bb0-675">這裡未提供/server 參數;SEFAUtil 會嘗試自動探索 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-675">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Lync Server.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

<span data-ttu-id="b7bb0-676">**輸出**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-676">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="b7bb0-677">立即啟用來電轉接</span><span class="sxs-lookup"><span data-stu-id="b7bb0-677">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="b7bb0-678">本範例會立即對其他使用者啟用來電轉接。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-678">This example immediately enables call-forwarding to another user.</span></span>

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

<span data-ttu-id="b7bb0-679">**輸出**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-679">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="b7bb0-680">立即停用來電轉接</span><span class="sxs-lookup"><span data-stu-id="b7bb0-680">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="b7bb0-681">本範例會立即停用來電轉接。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-681">This example immediately disables call forwarding.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

<span data-ttu-id="b7bb0-682">**輸出**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-682">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="b7bb0-683">將使用者新增為代理人，並設定代理人同時震鈴</span><span class="sxs-lookup"><span data-stu-id="b7bb0-683">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="b7bb0-684">這則範例會將使用者新增為代理人，並設定同時響鈴的代理人。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-684">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

<span data-ttu-id="b7bb0-685">**輸出**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-685">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="b7bb0-686">變更代理人的同時震鈴規則</span><span class="sxs-lookup"><span data-stu-id="b7bb0-686">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="b7bb0-687">這個範例會將上一個範例中設定的同時震鈴規則變更為延遲的震鈴規則。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-687">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

<span data-ttu-id="b7bb0-688">**輸出**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-688">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a><span data-ttu-id="b7bb0-689">移除代理人</span><span class="sxs-lookup"><span data-stu-id="b7bb0-689">Remove the Delegate</span></span>

<span data-ttu-id="b7bb0-690">本範例會移除代理人。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-690">This example removes the delegate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b7bb0-691">移除最後一個代理人時，會自動停用代理人震鈴。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-691">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

<span data-ttu-id="b7bb0-692">**輸出**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-692">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="b7bb0-693">新增代理人並設定 Call-Forward 至代理人規則</span><span class="sxs-lookup"><span data-stu-id="b7bb0-693">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="b7bb0-694">這則範例會新增代理人，並設定「呼叫轉寄至代理人規則。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-694">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

<span data-ttu-id="b7bb0-695">**輸出**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-695">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="b7bb0-696">啟用同時震鈴和設定目的地號碼</span><span class="sxs-lookup"><span data-stu-id="b7bb0-696">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="b7bb0-697">本範例啟用同時震鈴，並設定同時震鈴目的地號碼。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-697">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> <span data-ttu-id="b7bb0-698">若要變更已啟用同時震鈴之使用者的同時震鈴目的地數目，請使用/enablesimulring 參數保留該命令，否則將不會變更目的地號碼。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-698">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>



</div>

<span data-ttu-id="b7bb0-699">**輸出**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-699">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a><span data-ttu-id="b7bb0-700">停用同時震鈴</span><span class="sxs-lookup"><span data-stu-id="b7bb0-700">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="b7bb0-701">本範例會停用同時震鈴。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-701">This example disables simultaneous ringing.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

<span data-ttu-id="b7bb0-702">**輸出**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-702">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="b7bb0-703">新增 Team-Call 的團隊成員，並設定同時響鈴至 Team-Call 成員群組</span><span class="sxs-lookup"><span data-stu-id="b7bb0-703">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="b7bb0-704">這則範例會將小組成員新增至使用者的「小組通話群組」，並啟用對小組通話群組的同時震鈴。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-704">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="b7bb0-705">將成員新增至使用者的小組通話群組，會自動切換使用者的同時震鈴 settigs，以 simulring 他的小組通話群組。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-705">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>



</div>

<span data-ttu-id="b7bb0-706">**輸出**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-706">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="b7bb0-707">從 Team-Call 群組中移除成員</span><span class="sxs-lookup"><span data-stu-id="b7bb0-707">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="b7bb0-708">此範例會移除使用者之團隊通話群組的小組成員。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-708">This example removes a team member of the team-call group of a user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> <span data-ttu-id="b7bb0-709">若要移除的成員是小組通話群組的唯一成員，同時震鈴到小組通話群組將會自動停用。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-709">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>



</div>

<span data-ttu-id="b7bb0-710">**輸出**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-710">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="b7bb0-711">將延遲的環設定為 Team-Call 群組</span><span class="sxs-lookup"><span data-stu-id="b7bb0-711">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="b7bb0-712">本範例會將延遲的環變更為「小組通話群組時間」設定。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-712">This example changes the delayed ring to the team-call group time setting.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

<span data-ttu-id="b7bb0-713">**輸出**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-713">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a><span data-ttu-id="b7bb0-714">啟用 Team-Call</span><span class="sxs-lookup"><span data-stu-id="b7bb0-714">Enable Team-Call</span></span>

<span data-ttu-id="b7bb0-715">本範例會為指定的使用者啟用小組通話。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-715">This example enables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="b7bb0-716">如果使用者的小組通話群組沒有成員，將不會啟用小組通話。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-716">If the team-call group of the user has no members, team-call won’t be enabled.</span></span>



</div>

<span data-ttu-id="b7bb0-717">**輸出**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-717">**Output**</span></span>

</div>

<div>

## <a name="disable-team-call"></a><span data-ttu-id="b7bb0-718">停用 Team-Call</span><span class="sxs-lookup"><span data-stu-id="b7bb0-718">Disable Team-Call</span></span>

<span data-ttu-id="b7bb0-719">本範例會停用指定使用者的「小組通話」。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-719">This example disables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

<span data-ttu-id="b7bb0-720">**輸出**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-720">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="b7bb0-721">啟用群組呼叫收取並指派收取群組給使用者</span><span class="sxs-lookup"><span data-stu-id="b7bb0-721">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="b7bb0-722">這則範例會將收取群組指派給使用者，並啟用群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-722">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

<span data-ttu-id="b7bb0-723">**輸出**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-723">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a><span data-ttu-id="b7bb0-724">停用組來電收取</span><span class="sxs-lookup"><span data-stu-id="b7bb0-724">Disable Group Call Pickup</span></span>

<span data-ttu-id="b7bb0-725">本範例會停用指定使用者的群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-725">This example disables Group Call Pickup for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> <span data-ttu-id="b7bb0-726">當您停用使用者的群組呼叫收取時，指派給使用者的群組號碼不會保留。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-726">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="b7bb0-727">如果您後來想要為該使用者重新啟用群組呼叫收取，您必須使用/enablegrouppickup 參數再次指派群組號碼。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-727">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a><span data-ttu-id="b7bb0-728">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="b7bb0-728">SYSPrep.ps1</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b7bb0-729">描述</span><span class="sxs-lookup"><span data-stu-id="b7bb0-729">Description</span></span>

<span data-ttu-id="b7bb0-730">SYSPrep.ps1 是一種 Windows PowerShell 腳本，可在您的 Windows Server 2008 作業系統機器上安裝下列 Lync Server 2013 必要條件。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-730">SYSPrep.ps1 is a Windows PowerShell script that will install the following Lync Server 2013 prerequisites on your Windows Server 2008 operating system machine.</span></span>

  - <span data-ttu-id="b7bb0-731">Microsoft .Net Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="b7bb0-731">Microsoft .Net Framework 4.5</span></span>

  - <span data-ttu-id="b7bb0-732">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="b7bb0-732">Microsoft SQL Server Express</span></span>

  - <span data-ttu-id="b7bb0-733">Windows Powershell 版本3。0</span><span class="sxs-lookup"><span data-stu-id="b7bb0-733">Windows Powershell version 3.0</span></span>

  - <span data-ttu-id="b7bb0-734">Visual c + + 2010 可轉散發元件</span><span class="sxs-lookup"><span data-stu-id="b7bb0-734">Visual C++ 2010 Redistributable</span></span>

  - <span data-ttu-id="b7bb0-735">網際網路資訊伺服器更新</span><span class="sxs-lookup"><span data-stu-id="b7bb0-735">Internet Information Server Updates</span></span>

  - <span data-ttu-id="b7bb0-736">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="b7bb0-736">Windows Identity Foundation</span></span>

  - <span data-ttu-id="b7bb0-737">Lync Server 2013 核心檔案</span><span class="sxs-lookup"><span data-stu-id="b7bb0-737">Lync Server 2013 Core files</span></span>

<span data-ttu-id="b7bb0-738">雖然腳本名稱與 Microsoft Windows 作業系統的系統準備工具類似，但它們是不同的。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-738">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="b7bb0-739">此腳本只會安裝 Lync Server 2013 所需的必要條件。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-739">This script will only install the required prerequisites for Lync Server 2013.</span></span> <span data-ttu-id="b7bb0-740">安裝這些必要條件後，即可使用 Windows SYSPrep 工具建立伺服器的映射。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-740">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b7bb0-741">需求</span><span class="sxs-lookup"><span data-stu-id="b7bb0-741">Requirements</span></span>

<span data-ttu-id="b7bb0-742">在執行 SYSPrep.ps1 腳本之前，您必須將必要條件檔案複製到 Windows Server 2008 作業系統電腦上的本機資料夾中 (例如 \*\*D： \\ Setup) \*\*。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-742">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\\Setup)**.</span></span> <span data-ttu-id="b7bb0-743">此資料夾也必須包含 Lync Server 2013 檔案的複本，尤其是 **Setup.exe。**</span><span class="sxs-lookup"><span data-stu-id="b7bb0-743">This folder must also include a copy of the Lync Server 2013 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="b7bb0-744">您可以從下列位置下載必要檔：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-744">The prerequisite files can be downloaded from the following locations:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7bb0-745">前提</span><span class="sxs-lookup"><span data-stu-id="b7bb0-745">Prerequisite</span></span></th>
<th><span data-ttu-id="b7bb0-746">位置</span><span class="sxs-lookup"><span data-stu-id="b7bb0-746">Location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7bb0-747">Microsoft .Net Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="b7bb0-747">Microsoft .Net Framework 4.5</span></span></p></td>
<td><p>https://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7bb0-748">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="b7bb0-748">Microsoft SQL Server Express 2008 R2</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7bb0-749">Windows Powershell 版本3。0</span><span class="sxs-lookup"><span data-stu-id="b7bb0-749">Windows Powershell version 3.0</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7bb0-750">Visual c + + 2010 可轉散發元件</span><span class="sxs-lookup"><span data-stu-id="b7bb0-750">Visual C++ 2010 Redistributable</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7bb0-751">網際網路資訊伺服器更新</span><span class="sxs-lookup"><span data-stu-id="b7bb0-751">Internet Information Server Updates</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7bb0-752">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="b7bb0-752">Windows Identity Foundation</span></span></p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7bb0-753">Lync Server 2013 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="b7bb0-753">Lync Server 2013 Setup.exe</span></span></p></td>
<td><p><span data-ttu-id="b7bb0-754">從 Lync Server 2013 媒體複製</span><span class="sxs-lookup"><span data-stu-id="b7bb0-754">Copy from Lync Server 2013 media</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a><span data-ttu-id="b7bb0-755">參數</span><span class="sxs-lookup"><span data-stu-id="b7bb0-755">Parameter</span></span>

<span data-ttu-id="b7bb0-756">**– SetupFolder**參數會將必要條件檔案的目錄位置當作引數。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-756">The **–SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b7bb0-757">範例</span><span class="sxs-lookup"><span data-stu-id="b7bb0-757">Examples</span></span>

<span data-ttu-id="b7bb0-758">若要執行 SYSPrep.ps1 腳本，並安裝 Lync Server 2013 必要條件，請從提升許可權的命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-758">To run the SYSPrep.ps1 script and install the Lync Server 2013 prerequisites, run the following command from an elevated command prompt:</span></span>

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="b7bb0-759">未指派號碼宣告遷移</span><span class="sxs-lookup"><span data-stu-id="b7bb0-759">Unassigned Number Announcements Migration</span></span>

<span data-ttu-id="b7bb0-760">未指派號碼宣告遷移工具可讓 Lync 系統管理員將宣告應用程式所提供的未指派號碼設定從來源 Lync Server 或集區移至目的地 Lync Server 或集區。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-760">The Unassigned Number Announcements Migration tool enables a Lync administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Lync Server or Pool to a destination Lync Server or Pool.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b7bb0-761">描述</span><span class="sxs-lookup"><span data-stu-id="b7bb0-761">Description</span></span>

<span data-ttu-id="b7bb0-762">未指派號碼宣告遷移工具是一種 Windows PowerShell 腳本，可將來源伺服器或集區之宣告應用程式所提供的未指派號碼設定移至不同的伺服器或集區。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-762">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="b7bb0-763">執行時，未指派的號碼宣告遷移腳本會執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-763">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1.  <span data-ttu-id="b7bb0-764">將來源伺服器或集區中主控之宣告應用程式的未指派號碼宣告所使用的所有音訊檔，移至目的地伺服器或集區的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-764">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b7bb0-765">將音訊檔複製到目的地集區之後，會從來源集區中移除。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-765">the audio files are removed from the source pool once they’re copied to the destination pool.</span></span>

    
    </div>

2.  <span data-ttu-id="b7bb0-766">將來源伺服器或集區中主控的宣告應用程式設定的所有未指派號碼的宣告移至目的地伺服器或集區。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-766">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3.  <span data-ttu-id="b7bb0-767">將來源伺服器或集區中主控的宣告應用程式所提供的所有未指派號碼範圍重新指派給目的地伺服器或集區。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-767">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="b7bb0-768">順利執行腳本後，來源伺服器或集區中所主控的宣告應用程式所提供的所有未指派號碼範圍，都將會以目標伺服器或集區的相同設定進行服務。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-768">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="b7bb0-769">輸出</span><span class="sxs-lookup"><span data-stu-id="b7bb0-769">Output</span></span>

<span data-ttu-id="b7bb0-770">**Move-CsAnnouncementConfiguration**腳本會指出在 Lync 管理命令介面視窗中執行遷移作業成功或失敗的地方。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-770">The **Move-CsAnnouncementConfiguration** script indicates in the Lync Management Shell window from where it’s executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="b7bb0-771">如果執行作業時因任何錯誤而中斷，已順利移至目的地的未指派號碼範圍仍會保留在操作表單的目的地中，而且其他未指派的號碼範圍仍會保留在來源中，也就是在運作表單中。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-771">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="b7bb0-772">若要完全遷移其他設定，請在解決錯誤之後重新執行腳本。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-772">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="b7bb0-773">用途</span><span class="sxs-lookup"><span data-stu-id="b7bb0-773">Purpose</span></span>

<span data-ttu-id="b7bb0-774">未指派號碼宣告遷移腳本可用於下列三種情況：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-774">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

  - <span data-ttu-id="b7bb0-775">**將配置設定遷移至新版本的 Lync Server：** Contoso 正在遷移至 Lync Server 2013，並做為遷移程式的一部分，Lync Server 系統管理員想要將宣告應用程式所提供的未指派號碼設定從 Lync Server 2010 部署移動至新的 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-775">**Migrating configuration settings to a new version of Lync Server:** Contoso is in the process of migrating to Lync Server 2013 and as part of the migration process the Lync Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2010 deployment to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="b7bb0-776">若要移動設定設定，Lync Server 系統管理員會使用「未指派的號碼宣告遷移」工具。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-776">To move the configuration settings, the Lync Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

  - <span data-ttu-id="b7bb0-777">**將部署從 Lync server 2013 復原至 Lync server 2010：** 由於非預期的因素，Contoso 必須將遷移移至新的 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-777">**Rolling back a deployment from Lync Server 2013 to Lync Server 2010:** Due unexpected factors, Contoso has to roll back the migration to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="b7bb0-778">為了將中斷服務的中斷降至最低，Lync Server 系統管理員會使用「未指派的號碼宣告遷移」工具，將設定從 Lync Server 2013 部署復原至 Lync Server 2010 部署。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-778">To minimize disruptions to the service, the Lync Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Lync Server 2013 deployment to the Lync Server 2010 deployment.</span></span>

  - <span data-ttu-id="b7bb0-779">**在 Lync 部署之間移動資料：** Contoso 正在將一個集區的所有伺服器取代為更新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-779">**Moving data between Lync deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="b7bb0-780">其策略是部署新的 Lync Server 2013 集區、將舊資料移至新集區，然後取代舊的集區。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-780">Their strategy is to deploy a new Lync Server 2013 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="b7bb0-781">部署新集區之後，就會使用「未指派號碼宣告」遷移工具，將設定從舊集區移至新集區。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-781">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

<div>

## <a name="requirements"></a><span data-ttu-id="b7bb0-782">需求</span><span class="sxs-lookup"><span data-stu-id="b7bb0-782">Requirements</span></span>

<span data-ttu-id="b7bb0-783">以下是成功執行工具所需的主要需求：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-783">The following are the main requirements needed to successfully run the tool:</span></span>

1.  <span data-ttu-id="b7bb0-784">必須在已安裝 Lync Server 2013 管理命令介面的電腦上執行該腳本。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-784">The script must be run from a computer that has Lync Server 2013 Management Shell installed.</span></span>

2.  <span data-ttu-id="b7bb0-785">宣告應用程式必須成功部署于來源和目的地 Lync 伺服器或集區中。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-785">The announcement application has to be successfully deployed in the source and destination Lync Servers or Pools.</span></span>

<div>

## <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="b7bb0-786">Move-CsAnnouncementConfiguration 腳本</span><span class="sxs-lookup"><span data-stu-id="b7bb0-786">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="b7bb0-787">Move-CsAnnouncementConfiguration 腳本需要下表中所述的兩個參數。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-787">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

<span data-ttu-id="b7bb0-788">![Move-CsAnnouncementConfiguration 參數。](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration 參數。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-788">![Move-CsAnnouncementConfiguration parameters.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration parameters.")</span></span>

</div>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b7bb0-789">範例</span><span class="sxs-lookup"><span data-stu-id="b7bb0-789">Examples</span></span>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="b7bb0-790">將未指派號碼的宣告配置從 Lync Server 2010 集區移至 Lync Server 2013 集區</span><span class="sxs-lookup"><span data-stu-id="b7bb0-790">Moving the Unassigned Number Announcements Configuration from a Lync Server 2010 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="b7bb0-791">這個範例會將來源集區中未指派的號碼宣告 (Lync Server 2010) ，移至目的地集區 (Lync Server 2013) 。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-791">This example moves the unassigned number announcements from the source pool (Lync Server 2010) to the destination pool (Lync Server 2013).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a><span data-ttu-id="b7bb0-792">將未指派號碼的宣告配置從 Lync Server 2013 集區移至 Lync Server 2010 集區</span><span class="sxs-lookup"><span data-stu-id="b7bb0-792">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Lync Server 2010 Pool</span></span>

<span data-ttu-id="b7bb0-793">這個範例會將來源集區中未指派的號碼宣告 (Lync Server 2013) ，移至目的地集區 (Lync Server 2010) 。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-793">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Lync Server 2010).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a><span data-ttu-id="b7bb0-794">網路會議資料</span><span class="sxs-lookup"><span data-stu-id="b7bb0-794">Web Conf Data</span></span>

<span data-ttu-id="b7bb0-795">Web 會議資料工具可讓 Lync Server 2013 通訊軟體的管理員能夠更好地控制與召集人的 Web 會議相關聯的資料。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-795">The Web Conf Data Tool allows an administrator of Lync Server 2013 communications software to have more control over the data associated with an organizer’s Web conferences.</span></span> <span data-ttu-id="b7bb0-796">案例包括根據時間戳記準則刪除特定使用者的會議資料的功能。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-796">Scenarios include the ability to delete a specific user’s meeting data based on a time stamp criteria.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b7bb0-797">描述</span><span class="sxs-lookup"><span data-stu-id="b7bb0-797">Description</span></span>

<span data-ttu-id="b7bb0-798">此工具可讓系統管理員執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-798">This tool allows the administrator to perform the following operations:</span></span>

1.  <span data-ttu-id="b7bb0-799">尋找與單一使用者相關聯的所有 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-799">Find all Web conferencing data associated with a single user.</span></span>

2.  <span data-ttu-id="b7bb0-800">刪除所有與單一使用者相關聯的 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-800">Delete all Web conferencing data associated with a single user.</span></span>

3.  <span data-ttu-id="b7bb0-801">刪除與特定日期舊的單一使用者相關聯的所有 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4.  <span data-ttu-id="b7bb0-802">當使用者從一個集區移至另一個集區時，移動所有與單一使用者相關聯的 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b7bb0-803">Lync Server 2010 的資源工具組工具支援在使用者從一個集區移至另一個集區時，移動所有與單一使用者相關聯的 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="b7bb0-804">這項功能現在已被取代為此工具，取而代之的 <STRONG>MoveConferenceData</STRONG> 參數。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-804">That functionality is now deprecated from this tool in favor of the <STRONG>MoveConferenceData</STRONG> parameter.</span></span> <span data-ttu-id="b7bb0-805">如需此參數的詳細資訊，請參閱 <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">Move-CsUser</A> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-805">For details about this parameter, see the <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">Move-CsUser</A> cmdlet.</span></span>



</div>

<span data-ttu-id="b7bb0-806">工具只會刪除非使用中會議的會議資料。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-806">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="b7bb0-807">無法刪除會話) 中的使用中會議 (或會議。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-807">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="b7bb0-808">此工具必須從與目標使用者位於相同集區的電腦執行。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-808">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="b7bb0-809">使用此工具管理其會議內容資料的使用者，必須位於相同的使用者集區中。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-809">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="b7bb0-810">輸出</span><span class="sxs-lookup"><span data-stu-id="b7bb0-810">Output</span></span>

<span data-ttu-id="b7bb0-811">此工具會輸出各項作業的結果：</span><span class="sxs-lookup"><span data-stu-id="b7bb0-811">This tool outputs the results of each of the operations:</span></span>

  - <span data-ttu-id="b7bb0-812">如果執行查詢，則該工具會將所有非使用中會議資料檔案夾的清單，輸出為召集人。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

  - <span data-ttu-id="b7bb0-813">若執行刪除，該工具會輸出其資料將被刪除的所有會議資料資料夾清單。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b7bb0-814">需求</span><span class="sxs-lookup"><span data-stu-id="b7bb0-814">Requirements</span></span>

<span data-ttu-id="b7bb0-815">需要在召集人目前所在的相同集區中執行工具。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="b7bb0-816">您必須使用管理員許可權執行該工具，才能存取內容檔存放區。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="b7bb0-817">範例</span><span class="sxs-lookup"><span data-stu-id="b7bb0-817">Examples</span></span>

<span data-ttu-id="b7bb0-818">下表說明這些參數，其中一些是範例中使用的參數。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-818">The following table describes the parameters, some of which are used in the examples.</span></span>

<span data-ttu-id="b7bb0-819">![Web 會議資料工具參數。](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web 會議資料工具參數。")</span><span class="sxs-lookup"><span data-stu-id="b7bb0-819">![Web Conf Data Tool parameters.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web Conf Data Tool parameters.")</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

<span data-ttu-id="b7bb0-820">上述範例顯示查詢命令的運作方式。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-820">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="b7bb0-821">這類命令的輸出會是受此工具影響的所有會議內容資料夾清單。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-821">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

<span data-ttu-id="b7bb0-822">上述為刪除命令的範例。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-822">The preceding is an example of a delete command.</span></span> <span data-ttu-id="b7bb0-823">[刪除] 命令將從此使用者移除所有非使用中的會議資料夾。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-823">The delete command will remove all inactive meeting folders from this user.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="b7bb0-824">摘要</span><span class="sxs-lookup"><span data-stu-id="b7bb0-824">Summary</span></span>

<span data-ttu-id="b7bb0-825">對於需要更精確控制會議會議資料的系統管理員，此工具是一種重要資源。</span><span class="sxs-lookup"><span data-stu-id="b7bb0-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

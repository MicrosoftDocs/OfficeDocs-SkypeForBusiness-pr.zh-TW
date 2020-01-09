---
title: 商務用 Skype Server 2015 資源套件工具檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: 本主題描述商務用 Skype Server 2015 資源套件中的工具，包括每個工具的用途，以及其用法範例。 商務用 Skype Server 2015 資源套件能讓部署及管理商務用 Skype Server 2015 的 IT 系統管理員更容易進行例行工作。 例如，網路會議資料工具可用於輕鬆控制使用者在線上會議期間上傳的資料。 SEFAUtil 工具可用來設定代理人來電轉接及應答使用者。 我們鼓勵 IT 系統管理員使用這些工具來更有效率地管理商務用 Skype Server 2015。
ms.openlocfilehash: 0087f4286246833f0266ad0c78636bad00167756
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992530"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="c5da4-107">商務用 Skype Server 2015 資源套件工具檔</span><span class="sxs-lookup"><span data-stu-id="c5da4-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>

<span data-ttu-id="c5da4-108">本主題描述商務用 Skype Server 2015 資源套件中的工具，包括每個工具的用途，以及其用法範例。</span><span class="sxs-lookup"><span data-stu-id="c5da4-108">This topic describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="c5da4-109">商務用 Skype Server 2015 資源套件能讓部署及管理商務用 Skype Server 2015 的 IT 系統管理員更容易進行例行工作。</span><span class="sxs-lookup"><span data-stu-id="c5da4-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="c5da4-110">例如，網路會議**資料**工具可用於輕鬆控制使用者在線上會議期間上傳的資料。</span><span class="sxs-lookup"><span data-stu-id="c5da4-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="c5da4-111">**SEFAUtil**工具可用來設定代理人來電轉接及應答使用者。</span><span class="sxs-lookup"><span data-stu-id="c5da4-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="c5da4-112">我們鼓勵 IT 系統管理員使用這些工具來更有效率地管理商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="c5da4-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="c5da4-113">資源套件工具的安裝</span><span class="sxs-lookup"><span data-stu-id="c5da4-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="c5da4-114">若要安裝商務用 Skype Server 2015 資源套件，請從下載中心下載[OCSReskit](https://www.microsoft.com/en-us/download/details.aspx?id=52631) 。</span><span class="sxs-lookup"><span data-stu-id="c5da4-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) from the Download Center.</span></span>

<span data-ttu-id="c5da4-115">執行**OCSResKit**以進行簡單的安裝。</span><span class="sxs-lookup"><span data-stu-id="c5da4-115">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="c5da4-116">.Msi 會安裝下列路徑中的所有工具： **% 程式 Files%\Skype 商務伺服器 2015 \ ResKit**。</span><span class="sxs-lookup"><span data-stu-id="c5da4-116">The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**.</span></span> <span data-ttu-id="c5da4-117">可自包含的可執行檔的工具位於此資料夾中。</span><span class="sxs-lookup"><span data-stu-id="c5da4-117">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="c5da4-118">也有支援檔案的工具位於自己的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="c5da4-118">Tools that also have supporting files are in their own subfolders.</span></span>

## <a name="supported-environments"></a><span data-ttu-id="c5da4-119">支援的環境</span><span class="sxs-lookup"><span data-stu-id="c5da4-119">Supported Environments</span></span>

<span data-ttu-id="c5da4-120">商務用 Skype Server 2015 資源套件應該安裝在符合商務用 Skype Server 2015 所需規格的伺服器上，通常是用來執行商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="c5da4-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="c5da4-121">資源套件工具概述</span><span class="sxs-lookup"><span data-stu-id="c5da4-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="c5da4-122">以下是商務用 Skype Server 2015 資源套件中提供的工具清單。</span><span class="sxs-lookup"><span data-stu-id="c5da4-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="c5da4-123">每個工具的描述，包括 [需求] 與 [範例] 的用法在下列各節中講述。</span><span class="sxs-lookup"><span data-stu-id="c5da4-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>

- [<span data-ttu-id="c5da4-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="c5da4-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)

- [<span data-ttu-id="c5da4-125">頻寬原則服務監視器</span><span class="sxs-lookup"><span data-stu-id="c5da4-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)

- [<span data-ttu-id="c5da4-126">頻寬利用率分析程式</span><span class="sxs-lookup"><span data-stu-id="c5da4-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)

- [<span data-ttu-id="c5da4-127">呼叫 Parkometer</span><span class="sxs-lookup"><span data-stu-id="c5da4-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)

- [<span data-ttu-id="c5da4-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="c5da4-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)

- [<span data-ttu-id="c5da4-129">匯入儲存服務資料</span><span class="sxs-lookup"><span data-stu-id="c5da4-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)

- [<span data-ttu-id="c5da4-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="c5da4-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)

- [<span data-ttu-id="c5da4-131">查閱使用者主控台</span><span class="sxs-lookup"><span data-stu-id="c5da4-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)

- [<span data-ttu-id="c5da4-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="c5da4-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)

- [<span data-ttu-id="c5da4-133">網路設定檢視器</span><span class="sxs-lookup"><span data-stu-id="c5da4-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)

- [<span data-ttu-id="c5da4-134">回應群組代理程式即時</span><span class="sxs-lookup"><span data-stu-id="c5da4-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)

- [<span data-ttu-id="c5da4-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="c5da4-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)

- [<span data-ttu-id="c5da4-136">SYSPrep. ps1</span><span class="sxs-lookup"><span data-stu-id="c5da4-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)

- [<span data-ttu-id="c5da4-137">未指定的數位宣告遷移</span><span class="sxs-lookup"><span data-stu-id="c5da4-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)

- [<span data-ttu-id="c5da4-138">網路會議資料</span><span class="sxs-lookup"><span data-stu-id="c5da4-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a><span data-ttu-id="c5da4-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="c5da4-139">ABSConfig</span></span>
<span data-ttu-id="c5da4-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="c5da4-140"></span></span>

<span data-ttu-id="c5da4-141">通訊錄服務設定工具（ABSConfig）是一種管理工具，可協助系統管理員在商務用 Skype Server 2015 中自訂通訊錄服務設定。</span><span class="sxs-lookup"><span data-stu-id="c5da4-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="c5da4-142">這個工具也能讓商務用 Skype Server 2015 系統管理員還原預設通訊錄服務設定。</span><span class="sxs-lookup"><span data-stu-id="c5da4-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>

### <a name="description"></a><span data-ttu-id="c5da4-143">描述</span><span class="sxs-lookup"><span data-stu-id="c5da4-143">Description</span></span>

<span data-ttu-id="c5da4-144">ABSConfig 是圖形使用者介面應用程式，可讓系統管理員設定與通訊錄服務相關的 Active Directory 網域服務屬性。</span><span class="sxs-lookup"><span data-stu-id="c5da4-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="c5da4-145">此工具的主要案例如下所示：</span><span class="sxs-lookup"><span data-stu-id="c5da4-145">The primary scenarios for the tool are the following:</span></span>

- <span data-ttu-id="c5da4-146">若要讓系統管理員將 Active Directory 網域服務中的屬性對應至商務用 Skype Server 2015 的屬性。</span><span class="sxs-lookup"><span data-stu-id="c5da4-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>

- <span data-ttu-id="c5da4-147">若要讓系統管理員指定要在通訊錄服務檔案中包含或排除的 Active Directory 網域服務屬性。</span><span class="sxs-lookup"><span data-stu-id="c5da4-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

- <span data-ttu-id="c5da4-148">讓系統管理員還原預設通訊錄服務設定。</span><span class="sxs-lookup"><span data-stu-id="c5da4-148">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="c5da4-149">ABSConfig 工具可以使用 ABSConfig 檔案啟動。</span><span class="sxs-lookup"><span data-stu-id="c5da4-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="c5da4-150">工具隨即開啟至 [**設定屬性**] 索引標籤。此表格有選項可將 Active Directory 網域服務屬性對應到商務用 Skype Server 2015 的屬性欄位，以及指定哪些使用者要在通訊錄服務檔案中根據特定的屬性篩選器來包含或排除這些屬性。</span><span class="sxs-lookup"><span data-stu-id="c5da4-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="c5da4-151">您也可以選擇自訂要在通訊錄檔案中包含的電話號碼值。</span><span class="sxs-lookup"><span data-stu-id="c5da4-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="c5da4-152">[**還原預設**值] 選項可讓系統管理員將通訊錄服務設定還原為預設值。</span><span class="sxs-lookup"><span data-stu-id="c5da4-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

> [!NOTE]
> <span data-ttu-id="c5da4-153">將廣告屬性重新對應至不同的 OC 欄位名稱，只適用于通訊錄檔案下載，且不受通訊錄 Web 查詢支援。</span><span class="sxs-lookup"><span data-stu-id="c5da4-153">Re-mapping of AD attributes to different OC Field Names will only work for Address Book File Download, and is not supported by Address Book Web Query.</span></span>

### <a name="output"></a><span data-ttu-id="c5da4-154">收</span><span class="sxs-lookup"><span data-stu-id="c5da4-154">Output</span></span>

<span data-ttu-id="c5da4-155">ABSConfig 會將通訊錄服務配置儲存在資料庫中。</span><span class="sxs-lookup"><span data-stu-id="c5da4-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

```PowerShell
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="c5da4-156">特殊</span><span class="sxs-lookup"><span data-stu-id="c5da4-156">Purpose</span></span>

<span data-ttu-id="c5da4-157">ABSConfig 提供一種快速且簡易的自訂商務用 Skype Server 2015 通訊錄服務的方式。</span><span class="sxs-lookup"><span data-stu-id="c5da4-157">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>

### <a name="requirements"></a><span data-ttu-id="c5da4-158">需求</span><span class="sxs-lookup"><span data-stu-id="c5da4-158">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="c5da4-159">電腦</span><span class="sxs-lookup"><span data-stu-id="c5da4-159">Computer</span></span>

<span data-ttu-id="c5da4-160">ABSConfig 只能從已安裝商務用 Skype Server 2015 的網域加入電腦執行。</span><span class="sxs-lookup"><span data-stu-id="c5da4-160">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="c5da4-161">在商務用 Skype Server 2015、Enterprise Edition 中，此工具可以在安裝期間啟用通訊錄服務的任何前端伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="c5da4-161">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

#### <a name="network"></a><span data-ttu-id="c5da4-162">網路</span><span class="sxs-lookup"><span data-stu-id="c5da4-162">Network</span></span>

<span data-ttu-id="c5da4-163">電腦應該能夠連線到前端池和後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="c5da4-163">The computer should be able to connect to the Front End pool and back-end database.</span></span>

#### <a name="software"></a><span data-ttu-id="c5da4-164">軟體</span><span class="sxs-lookup"><span data-stu-id="c5da4-164">Software</span></span>

<span data-ttu-id="c5da4-165">在執行 ABSConfig 工具之前，必須先安裝下列軟體元件：</span><span class="sxs-lookup"><span data-stu-id="c5da4-165">The following software components must be installed before running the ABSConfig tool:</span></span>

- <span data-ttu-id="c5da4-166">商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="c5da4-166">Skype for Business Server 2015</span></span>

#### <a name="users"></a><span data-ttu-id="c5da4-167">使用者</span><span class="sxs-lookup"><span data-stu-id="c5da4-167">Users</span></span>

<span data-ttu-id="c5da4-168">擁有更新商務用 Skype Server 2015 部署所需許可權的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="c5da4-168">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>

### <a name="examples"></a><span data-ttu-id="c5da4-169">範例</span><span class="sxs-lookup"><span data-stu-id="c5da4-169">Examples</span></span>

<span data-ttu-id="c5da4-170">在命令提示字元中輸入**ABSConfig** ，即可開始 ABSConfig。</span><span class="sxs-lookup"><span data-stu-id="c5da4-170">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="c5da4-171">下面顯示的是 ABSConfig 工具使用者介面。</span><span class="sxs-lookup"><span data-stu-id="c5da4-171">Shown below is the ABSConfig tool user interface.</span></span>

![ABSConfig.exe 工具。](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a><span data-ttu-id="c5da4-173">總結</span><span class="sxs-lookup"><span data-stu-id="c5da4-173">Summary</span></span>

<span data-ttu-id="c5da4-174">ABSConfig 工具可讓系統管理員快速且輕鬆地使用工具來自訂商務用 Skype Server 2015 通訊錄服務。</span><span class="sxs-lookup"><span data-stu-id="c5da4-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="c5da4-175">頻寬原則服務監視器</span><span class="sxs-lookup"><span data-stu-id="c5da4-175">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="c5da4-176"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="c5da4-176"></span></span>

<span data-ttu-id="c5da4-177">[頻寬原則服務監視工具] 可讓系統管理員查看下列專案的清單：</span><span class="sxs-lookup"><span data-stu-id="c5da4-177">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1. <span data-ttu-id="c5da4-178">拓撲中所有已設定的商務用 Skype Server 2015 頻寬原則服務（驗證與核心）</span><span class="sxs-lookup"><span data-stu-id="c5da4-178">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2. <span data-ttu-id="c5da4-179">每個服務對其他頻寬原則服務及邊緣伺服器所做的連接</span><span class="sxs-lookup"><span data-stu-id="c5da4-179">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3. <span data-ttu-id="c5da4-180">在網路設定檔中設定的所有連結，以及每個頻寬策略服務所報告的即時頻寬使用量</span><span class="sxs-lookup"><span data-stu-id="c5da4-180">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

### <a name="description"></a><span data-ttu-id="c5da4-181">描述</span><span class="sxs-lookup"><span data-stu-id="c5da4-181">Description</span></span>

<span data-ttu-id="c5da4-182">[頻寬原則服務監視工具] 是以 GUI 式應用程式的方式來實現。</span><span class="sxs-lookup"><span data-stu-id="c5da4-182">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="c5da4-183">系統管理員執行 PDPMonUI 來啟動該工具。</span><span class="sxs-lookup"><span data-stu-id="c5da4-183">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="c5da4-184">當工具啟動時，它會嘗試在拓撲中探索頻寬原則服務清單。</span><span class="sxs-lookup"><span data-stu-id="c5da4-184">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="c5da4-185">初次更新完成之後，視窗左側的窗格會以其所屬的群集來分組，並填入服務清單。</span><span class="sxs-lookup"><span data-stu-id="c5da4-185">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="c5da4-186">當管理員選取特定的頻寬原則服務時，右邊的窗格會顯示該特定服務的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c5da4-186">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="c5da4-187">該窗格還有兩個顯示資訊的主要索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c5da4-187">That pane also has two main tabs that display information.</span></span>

#### <a name="machine-info-tab"></a><span data-ttu-id="c5da4-188">[電腦資訊] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="c5da4-188">Machine Info Tab</span></span>

<span data-ttu-id="c5da4-189">[**電腦資訊**] 索引標籤會顯示已選取頻寬原則服務的詳細資料，以及由選取的頻寬策略服務所進行的所有連線的清單和狀態與其他服務。</span><span class="sxs-lookup"><span data-stu-id="c5da4-189">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

#### <a name="topology-info-tab"></a><span data-ttu-id="c5da4-190">[拓撲資訊] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="c5da4-190">Topology Info Tab</span></span>

<span data-ttu-id="c5da4-191">[**拓撲資訊**] 索引標籤會顯示在 [網路設定] 中設定的所有連結的清單。</span><span class="sxs-lookup"><span data-stu-id="c5da4-191">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="c5da4-192">針對每個連結，會顯示 [音訊] 和 [影片頻寬] 的容量。</span><span class="sxs-lookup"><span data-stu-id="c5da4-192">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="c5da4-193">此外，目前使用的頻寬會以 Kbps 及容量百分比的方式顯示。</span><span class="sxs-lookup"><span data-stu-id="c5da4-193">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="c5da4-194">此工具使用色彩編碼來醒目提示具有接近產能之利用率的連結，這可讓系統管理員快速隔離這些連結。</span><span class="sxs-lookup"><span data-stu-id="c5da4-194">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

> [!NOTE]
>  <span data-ttu-id="c5da4-195">如果頻寬原則服務監視器工具在連線至任何已設定的頻寬原則服務時發生故障，**電腦資訊**和**拓撲資訊**索引標籤中的資訊將無法填入。</span><span class="sxs-lookup"><span data-stu-id="c5da4-195">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="c5da4-196">不過，該工具可能會先連線，但隨後會失去與服務的連線。</span><span class="sxs-lookup"><span data-stu-id="c5da4-196">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="c5da4-197">在這種情況下，系統管理員可能會看到過時的資訊。</span><span class="sxs-lookup"><span data-stu-id="c5da4-197">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="c5da4-198">每個索引標籤上都有**上次更新**的時間戳記，這些索引標籤可讓系統管理員查看特定頻寬原則服務上次更新資料的時間。</span><span class="sxs-lookup"><span data-stu-id="c5da4-198">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>

### <a name="output"></a><span data-ttu-id="c5da4-199">收</span><span class="sxs-lookup"><span data-stu-id="c5da4-199">Output</span></span>

<span data-ttu-id="c5da4-200">沒有命令列輸出;程式輸出包含在主要的圖形使用者介面（GUI）中。</span><span class="sxs-lookup"><span data-stu-id="c5da4-200">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

### <a name="purpose"></a><span data-ttu-id="c5da4-201">特殊</span><span class="sxs-lookup"><span data-stu-id="c5da4-201">Purpose</span></span>

<span data-ttu-id="c5da4-202">[頻寬原則服務監視器] 工具的用途是，可讓系統管理員瞭解拓撲中定義的每個頻寬原則服務的狀態。</span><span class="sxs-lookup"><span data-stu-id="c5da4-202">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="c5da4-203">此外，管理員可以查看網路設定檔中定義的所有連結的即時頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="c5da4-203">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

### <a name="requirements"></a><span data-ttu-id="c5da4-204">需求</span><span class="sxs-lookup"><span data-stu-id="c5da4-204">Requirements</span></span>

<span data-ttu-id="c5da4-205">[頻寬原則服務監視器] 工具必須在屬於商務用 Skype Server 拓撲的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="c5da4-205">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>

### <a name="summary"></a><span data-ttu-id="c5da4-206">總結</span><span class="sxs-lookup"><span data-stu-id="c5da4-206">Summary</span></span>

<span data-ttu-id="c5da4-207">頻寬原則服務監視器工具可以是系統管理員的重要資源，讓他們能夠檢查拓撲中所有頻寬原則服務的狀態，更重要的是，它們可以取得連結的即時頻寬利用率，在 [網路設定] 中定義。</span><span class="sxs-lookup"><span data-stu-id="c5da4-207">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="c5da4-208">頻寬利用率分析程式</span><span class="sxs-lookup"><span data-stu-id="c5da4-208">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="c5da4-209"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="c5da4-209"></span></span>

<span data-ttu-id="c5da4-210">[頻寬利用率分析] 是一種工具，可在商業網路中，透過廣域網路連結的 UC 端點，建立各種頻寬使用量的報告。</span><span class="sxs-lookup"><span data-stu-id="c5da4-210">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="c5da4-211">這些報告可用來瞭解目前的頻寬使用量模式，並協助您進行頻寬容量規劃。</span><span class="sxs-lookup"><span data-stu-id="c5da4-211">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

### <a name="description"></a><span data-ttu-id="c5da4-212">描述</span><span class="sxs-lookup"><span data-stu-id="c5da4-212">Description</span></span>

<span data-ttu-id="c5da4-213">[頻寬利用率分析] 是以 GUI 式應用程式的方式來實現。</span><span class="sxs-lookup"><span data-stu-id="c5da4-213">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="c5da4-214">這個工具會針對網路上的音訊利用率專門產生報告，並協助您進行容量規劃。</span><span class="sxs-lookup"><span data-stu-id="c5da4-214">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="c5da4-215">它也會根據指派給各種連結的頻寬容量來反覆運算。</span><span class="sxs-lookup"><span data-stu-id="c5da4-215">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

### <a name="output"></a><span data-ttu-id="c5da4-216">收</span><span class="sxs-lookup"><span data-stu-id="c5da4-216">Output</span></span>

<span data-ttu-id="c5da4-217">[頻寬利用率分析]：針對系統中設定的所有 WAN 連結，提供圖形 al 的頻寬容量與利用率。</span><span class="sxs-lookup"><span data-stu-id="c5da4-217">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

### <a name="purpose"></a><span data-ttu-id="c5da4-218">特殊</span><span class="sxs-lookup"><span data-stu-id="c5da4-218">Purpose</span></span>

<span data-ttu-id="c5da4-219">在任何語音與視頻部署中，監視及瞭解整個商業網路中媒體流量的頻寬利用率趨勢是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="c5da4-219">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="c5da4-220">[頻寬利用率分析] 工具可讓系統管理員只取得該功能。</span><span class="sxs-lookup"><span data-stu-id="c5da4-220">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="c5da4-221">此工具會執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c5da4-221">This tool does the following:</span></span>

- <span data-ttu-id="c5da4-222">針對網路上的音訊利用率產生特定報告</span><span class="sxs-lookup"><span data-stu-id="c5da4-222">Generates specific reports for audio utilization across the network</span></span>

- <span data-ttu-id="c5da4-223">協助更有效的容量規劃，以及在指派給各種連結的頻寬容量上進行反覆運算</span><span class="sxs-lookup"><span data-stu-id="c5da4-223">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="c5da4-224">[頻寬利用率分析] 可產生頻寬容量與利用率報告的圖形化圖形;它們如下所示：</span><span class="sxs-lookup"><span data-stu-id="c5da4-224">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

- <span data-ttu-id="c5da4-225">商業網路中的所有 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="c5da4-225">All the WAN links in the enterprise network</span></span>

- <span data-ttu-id="c5da4-226">已選取已選取的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="c5da4-226">Filtered by selected WAN links that have been chosen</span></span>

- <span data-ttu-id="c5da4-227">使用超過連結容量的 WAN 連結進行篩選</span><span class="sxs-lookup"><span data-stu-id="c5da4-227">Filtered by WAN links that have exceeded link capacity</span></span>

- <span data-ttu-id="c5da4-228">依已在使用預配頻寬的 WAN 連結進行篩選</span><span class="sxs-lookup"><span data-stu-id="c5da4-228">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

- <span data-ttu-id="c5da4-229">依 WAN 連結達到關鍵性層級的 WAN 連結進行篩選（頻寬利用率大於 WAN 連結頻寬容量的90%）</span><span class="sxs-lookup"><span data-stu-id="c5da4-229">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

- <span data-ttu-id="c5da4-230">依 WAN 連結類型進行篩選：網路網站連結、interregional 連結，以及網站內的連結</span><span class="sxs-lookup"><span data-stu-id="c5da4-230">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

- <span data-ttu-id="c5da4-231">依網路區域篩選</span><span class="sxs-lookup"><span data-stu-id="c5da4-231">Filtered by network region</span></span>

#### <a name="applications"></a><span data-ttu-id="c5da4-232">程式</span><span class="sxs-lookup"><span data-stu-id="c5da4-232">Applications</span></span>

<span data-ttu-id="c5da4-233">[頻寬利用率] Analyzer 有下列兩個應用程式（工具）：</span><span class="sxs-lookup"><span data-stu-id="c5da4-233">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

- <span data-ttu-id="c5da4-234">**WanLinkLogCollector**此工具可讓使用者輸入所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="c5da4-234">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>

- <span data-ttu-id="c5da4-235">**BandwidthUtilizationAnalyzer. Xlsm** Microsoft Excel 試算表軟體報告會透過 WanLinkLogCollector 自動啟動。</span><span class="sxs-lookup"><span data-stu-id="c5da4-235">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="c5da4-236">此應用程式可讓使用者將篩選套用至報表，如本文稍後所示。</span><span class="sxs-lookup"><span data-stu-id="c5da4-236">This application allows the user to apply filters to the report as shown later in this article.</span></span>

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="c5da4-237">使用頻寬利用率分析程式的階段</span><span class="sxs-lookup"><span data-stu-id="c5da4-237">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="c5da4-238">使用 [頻寬利用率] 分析程式有兩個階段：</span><span class="sxs-lookup"><span data-stu-id="c5da4-238">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

- <span data-ttu-id="c5da4-239">收集使用 WanLinkLogCollector 執行的記錄</span><span class="sxs-lookup"><span data-stu-id="c5da4-239">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

- <span data-ttu-id="c5da4-240">自訂報表，並使用 BandwidthUtilizationAnalyzer 進行 xlsm。</span><span class="sxs-lookup"><span data-stu-id="c5da4-240">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5da4-241">我們強烈建議您不要由最終使用者手動啟動 BandwidthUtilizationAnalyzer。</span><span class="sxs-lookup"><span data-stu-id="c5da4-241">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>

#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="c5da4-242">啟動頻寬利用率分析程式</span><span class="sxs-lookup"><span data-stu-id="c5da4-242">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="c5da4-243">在命令提示字元中啟動 WanLinkLogCollector 或使用 Windows 資源管理器。</span><span class="sxs-lookup"><span data-stu-id="c5da4-243">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

 <span data-ttu-id="c5da4-244">**使用 WanLinkLogCollector**</span><span class="sxs-lookup"><span data-stu-id="c5da4-244">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="c5da4-245">使用 WanLinkLogCollector 有三個步驟：</span><span class="sxs-lookup"><span data-stu-id="c5da4-245">There are three steps to using WanLinkLogCollector.exe:</span></span>

1. <span data-ttu-id="c5da4-246">**記錄時程表**提供報表需要產生的時程表</span><span class="sxs-lookup"><span data-stu-id="c5da4-246">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>

2. <span data-ttu-id="c5da4-247">**指定檔案目錄**提供檔案位置資訊</span><span class="sxs-lookup"><span data-stu-id="c5da4-247">**Specify the file directories** Provide file location information</span></span>

3. <span data-ttu-id="c5da4-248">**收集記錄並啟動報表檢視器**執行命令來產生報告</span><span class="sxs-lookup"><span data-stu-id="c5da4-248">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>

#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="c5da4-249">步驟 1-記錄時程表</span><span class="sxs-lookup"><span data-stu-id="c5da4-249">Step 1 - Log the timeline</span></span>

<span data-ttu-id="c5da4-250">記錄時間軸可讓工具使用者指定下列選項，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="c5da4-250">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1. <span data-ttu-id="c5da4-251">**開始日期**這是要產生報告的時程表開始日期;例如，2010年8月1日。</span><span class="sxs-lookup"><span data-stu-id="c5da4-251">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2. <span data-ttu-id="c5da4-252">**結束日期**這是要產生報告的時程表結束日期;例如，2010年9月30日。</span><span class="sxs-lookup"><span data-stu-id="c5da4-252">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>

     ![頻寬使用量分析中的開始與結束日期](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="c5da4-254">步驟 2-指定檔案目錄</span><span class="sxs-lookup"><span data-stu-id="c5da4-254">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="c5da4-255">下列是可由使用者指定的檔案目錄，如所示。</span><span class="sxs-lookup"><span data-stu-id="c5da4-255">The following file directories can be specified by the user as shown.</span></span>

- <span data-ttu-id="c5da4-256">**伺服器記錄檔位置**儲存頻寬原則伺服器記錄的資料夾位置。</span><span class="sxs-lookup"><span data-stu-id="c5da4-256">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="c5da4-257">這通常在 [ \<\AppServerFiles\PDP.\> \\ ] 中，<\>選擇的 FE</span><span class="sxs-lookup"><span data-stu-id="c5da4-257">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>

- <span data-ttu-id="c5da4-258">**臨時檔案儲存位置**產生報告時儲存中間檔案的臨時檔案位置。</span><span class="sxs-lookup"><span data-stu-id="c5da4-258">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

![頻寬使用量分析中的檔案目錄](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

> [!NOTE]
> <span data-ttu-id="c5da4-260">請確定有足夠的檔案存取伺服器記錄，並將 [臨時檔案存放區] 資料夾提供給工具使用者。</span><span class="sxs-lookup"><span data-stu-id="c5da4-260">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="c5da4-261">步驟 3-收集記錄並啟動報表檢視器</span><span class="sxs-lookup"><span data-stu-id="c5da4-261">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="c5da4-262">若要收集記錄並啟動報表檢視器，請按一下 [**執行**]，如下所示。</span><span class="sxs-lookup"><span data-stu-id="c5da4-262">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="c5da4-263">此步驟會收集所需的資料。</span><span class="sxs-lookup"><span data-stu-id="c5da4-263">This step collects the required data.</span></span>

![收集頻寬使用量分析中的資料](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

<span data-ttu-id="c5da4-265">輸入驗證成功後，會顯示下面所示的訊息。</span><span class="sxs-lookup"><span data-stu-id="c5da4-265">When the input validation is successful, the message shown below is displayed.</span></span>

![Bandwidth Utilization Analyser 的記錄收集完畢通知](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

<span data-ttu-id="c5da4-267">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c5da4-267">Click **OK**.</span></span> <span data-ttu-id="c5da4-268">BandwidthUtilizationAnalyzer。 xlsm 會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="c5da4-268">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="c5da4-269">依照訊息方塊中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="c5da4-269">Follow the instructions in the message box.</span></span> <span data-ttu-id="c5da4-270">如需詳細資訊，請參閱下一節中的 [**使用 BandwidthUtilizationAnalyzer xlsm** ]。</span><span class="sxs-lookup"><span data-stu-id="c5da4-270">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>


### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="c5da4-271">使用 BandwidthUtilizationAnalyzer xlsm</span><span class="sxs-lookup"><span data-stu-id="c5da4-271">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="c5da4-272">當 xlsm 自動啟動時，請按一下 [重新整理] **，如下所**示。</span><span class="sxs-lookup"><span data-stu-id="c5da4-272">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. <span data-ttu-id="c5da4-274">開啟檔案資料夾時，請從訊息方塊中指定的位置選取 [合併] .csv，如下所示。</span><span class="sxs-lookup"><span data-stu-id="c5da4-274">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="c5da4-275">它也會將位置顯示為**C：\Temp**。</span><span class="sxs-lookup"><span data-stu-id="c5da4-275">It also shows the location as **C:\Temp**.</span></span>

     ![在 BandwidthUtilizationAnalyzer 中開啟資料夾。](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. <span data-ttu-id="c5da4-277">按一下 [匯**入**]。</span><span class="sxs-lookup"><span data-stu-id="c5da4-277">Click **Import**.</span></span>

4. <span data-ttu-id="c5da4-278">圖形化圖形就會自動產生。</span><span class="sxs-lookup"><span data-stu-id="c5da4-278">The graphical plot is automatically generated.</span></span> <span data-ttu-id="c5da4-279">當使用背景指標消失時，就可以使用它。</span><span class="sxs-lookup"><span data-stu-id="c5da4-279">It is available when the working-in-the-background pointer disappears.</span></span>

     ![在報表檢視中套用篩選。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="c5da4-281">將篩選套用至報表檢視</span><span class="sxs-lookup"><span data-stu-id="c5da4-281">Applying Filters to the Report View</span></span>

<span data-ttu-id="c5da4-282">以下說明可套用至報表檢視的篩選器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c5da4-282">The filters that can be applied to the report view as shown below are described as follows:</span></span>

![在報表檢視中套用篩選。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. <span data-ttu-id="c5da4-284">**名稱**依 WAN 連結篩選（篩選器位於圖形右側）。前置詞代表下列連結類型;請參閱 [垂直（藍色）] 方塊：</span><span class="sxs-lookup"><span data-stu-id="c5da4-284">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>

   - <span data-ttu-id="c5da4-285">**S 網站**從網路網站到網路區域的 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="c5da4-285">**S Site** The WAN link from a network site to a network region</span></span>

   - <span data-ttu-id="c5da4-286">**是站內網站**兩個網路網站之間的 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="c5da4-286">**IS Inter-Site** The WAN link between two network sites</span></span>

   - <span data-ttu-id="c5da4-287">**R 區域間**兩個網路區域之間的 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="c5da4-287">**R Inter-Region** The WAN link between two network region</span></span>

2. <span data-ttu-id="c5da4-288">**超出限制**依頻寬利用率超過頻寬容量的 WAN 連結進行篩選</span><span class="sxs-lookup"><span data-stu-id="c5da4-288">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3. <span data-ttu-id="c5da4-289">**重要等級**依頻寬利用率達到90% 或超過頻寬容量的 WAN 連結進行篩選</span><span class="sxs-lookup"><span data-stu-id="c5da4-289">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4. <span data-ttu-id="c5da4-290">未**充分利用**依頻寬利用率小於頻寬容量25% 的 WAN 連結進行篩選</span><span class="sxs-lookup"><span data-stu-id="c5da4-290">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5. <span data-ttu-id="c5da4-291">**連結類型**依下列 WAN 連結類型進行篩選：</span><span class="sxs-lookup"><span data-stu-id="c5da4-291">**Link type** Filter by the following WAN links types:</span></span>

   - <span data-ttu-id="c5da4-292">**網路網站**類型</span><span class="sxs-lookup"><span data-stu-id="c5da4-292">**Network site** type</span></span>

   - <span data-ttu-id="c5da4-293">**網站間**類型</span><span class="sxs-lookup"><span data-stu-id="c5da4-293">**Inter-site** type</span></span>

   - <span data-ttu-id="c5da4-294">**區域間連結**類型</span><span class="sxs-lookup"><span data-stu-id="c5da4-294">**Inter-Region link** type</span></span>

6. <span data-ttu-id="c5da4-295">**地區**依網路區域篩選</span><span class="sxs-lookup"><span data-stu-id="c5da4-295">**Region** Filter by network region</span></span>

<span data-ttu-id="c5da4-296">下圖顯示前面所述的篩選。</span><span class="sxs-lookup"><span data-stu-id="c5da4-296">The following figures show the previously described filters.</span></span>

<span data-ttu-id="c5da4-297">依**名稱**篩選。</span><span class="sxs-lookup"><span data-stu-id="c5da4-297">Filter by **Name**.</span></span> <span data-ttu-id="c5da4-298">選取要在圖表中顯示的連結清單。</span><span class="sxs-lookup"><span data-stu-id="c5da4-298">Select the list of links that need to be displayed in the graph.</span></span>

![在 BandwidthUtilizationAnalyzer 中依 [Name] (名稱) 篩選。](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

<span data-ttu-id="c5da4-300">依**超出限制**進行篩選。</span><span class="sxs-lookup"><span data-stu-id="c5da4-300">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="c5da4-301">選取 [ **True** ]，強制執行篩選。</span><span class="sxs-lookup"><span data-stu-id="c5da4-301">Select **True** to enforce the filter.</span></span>

![依 [Exceeded Limit] (已超出限制) 篩選。](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

<span data-ttu-id="c5da4-303">依**臨界層級**篩選。</span><span class="sxs-lookup"><span data-stu-id="c5da4-303">Filter by **Critical levels**.</span></span> <span data-ttu-id="c5da4-304">選取 [ **True** ]，強制執行篩選。</span><span class="sxs-lookup"><span data-stu-id="c5da4-304">Select **True** to enforce the filter.</span></span>

![依 [Critical Levels] (重大層級) 篩選。](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

<span data-ttu-id="c5da4-306">根據**利用率**情況進行篩選。</span><span class="sxs-lookup"><span data-stu-id="c5da4-306">Filter by **Under utilized**.</span></span> <span data-ttu-id="c5da4-307">選取 [ **True** ]，強制執行篩選。</span><span class="sxs-lookup"><span data-stu-id="c5da4-307">Select **True** to enforce the filter.</span></span>

![依 [Under Utilized] (低度使用) 篩選。](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

<span data-ttu-id="c5da4-309">依**連結類型**篩選。</span><span class="sxs-lookup"><span data-stu-id="c5da4-309">Filter by **Link Type**.</span></span> <span data-ttu-id="c5da4-310">選取需要顯示的一種或多種類型。</span><span class="sxs-lookup"><span data-stu-id="c5da4-310">Select the type or types that need to be displayed.</span></span>

![依 [Link Type] (連結類型) 篩選。](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

<span data-ttu-id="c5da4-312">依**區域**篩選。</span><span class="sxs-lookup"><span data-stu-id="c5da4-312">Filter by **Region**.</span></span> <span data-ttu-id="c5da4-313">選取需要顯示其連結的地區清單。</span><span class="sxs-lookup"><span data-stu-id="c5da4-313">Select a list of regions whose links need to be displayed.</span></span>

![依 [Region] (地區) 篩選。](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a><span data-ttu-id="c5da4-315">需求</span><span class="sxs-lookup"><span data-stu-id="c5da4-315">Requirements</span></span>

- <span data-ttu-id="c5da4-316">.NET Framework 3。5</span><span class="sxs-lookup"><span data-stu-id="c5da4-316">The .NET Framework 3.5</span></span>

- <span data-ttu-id="c5da4-317">Microsoft Excel 2010 或 Excel 2007</span><span class="sxs-lookup"><span data-stu-id="c5da4-317">Microsoft Excel 2010 or Excel 2007</span></span>

### <a name="summary"></a><span data-ttu-id="c5da4-318">總結</span><span class="sxs-lookup"><span data-stu-id="c5da4-318">Summary</span></span>

<span data-ttu-id="c5da4-319">頻寬利用率分析程式是用來繪製網路上 UC 流量的音訊頻寬利用率。</span><span class="sxs-lookup"><span data-stu-id="c5da4-319">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="c5da4-320">您也可以使用這個工具，來報告網路上的視頻頻寬利用率。</span><span class="sxs-lookup"><span data-stu-id="c5da4-320">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

## <a name="call-parkometer"></a><span data-ttu-id="c5da4-321">呼叫 Parkometer</span><span class="sxs-lookup"><span data-stu-id="c5da4-321">Call Parkometer</span></span>
<span data-ttu-id="c5da4-322"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="c5da4-322"></span></span>

<span data-ttu-id="c5da4-323">呼叫 Parkometer 是一種命令列應用程式，可讓您輕鬆存取 [通話駐留軌道] 資料庫。</span><span class="sxs-lookup"><span data-stu-id="c5da4-323">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

### <a name="description"></a><span data-ttu-id="c5da4-324">描述</span><span class="sxs-lookup"><span data-stu-id="c5da4-324">Description</span></span>

<span data-ttu-id="c5da4-325">呼叫 Parkometer 是一種追蹤目前寄存通話的工具。</span><span class="sxs-lookup"><span data-stu-id="c5da4-325">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="c5da4-326">它也會收集有關軌道式及通話駐留伺服器（CPS）用法的統計資料。</span><span class="sxs-lookup"><span data-stu-id="c5da4-326">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="c5da4-327">這個命令列工具提供從本機或遠端連線的電腦對 CPS 軌道 SQL Server 資料庫的讀取和寫入存取權。</span><span class="sxs-lookup"><span data-stu-id="c5da4-327">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="c5da4-328">所有選項都是互相排斥的。</span><span class="sxs-lookup"><span data-stu-id="c5da4-328">All options are mutually exclusive.</span></span> <span data-ttu-id="c5da4-329">命令列語法如下所示：</span><span class="sxs-lookup"><span data-stu-id="c5da4-329">Command-line syntax is as follows:</span></span>

- <span data-ttu-id="c5da4-330">**-o**參數-列出針對此池子設定的所有軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="c5da4-330">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>

- <span data-ttu-id="c5da4-331">**-n**參數：列出此池子中所有目前使用的軌道式。</span><span class="sxs-lookup"><span data-stu-id="c5da4-331">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="c5da4-332">顯示的資訊如下所示：</span><span class="sxs-lookup"><span data-stu-id="c5da4-332">The information displayed is as follows:</span></span>

  - <span data-ttu-id="c5da4-333">Parkee 和 parker 的 SIP 統一資源識別項（URI）。</span><span class="sxs-lookup"><span data-stu-id="c5da4-333">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>

  - <span data-ttu-id="c5da4-334">停用通話的 CPS 主機名稱。</span><span class="sxs-lookup"><span data-stu-id="c5da4-334">Host name of the CPS where the call is parked.</span></span>

  - <span data-ttu-id="c5da4-335">通話停用的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="c5da4-335">Time stamp of when the call was parked.</span></span>

- <span data-ttu-id="c5da4-336">**-f**參數：列出池中目前閒置的 [軌道式] 數目。</span><span class="sxs-lookup"><span data-stu-id="c5da4-336">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>

- <span data-ttu-id="c5da4-337">\*\*-r \<n\> \*\*參數：列出\<n\>個最後一個寄存通話。</span><span class="sxs-lookup"><span data-stu-id="c5da4-337">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="c5da4-338">顯示的資訊如下所示：</span><span class="sxs-lookup"><span data-stu-id="c5da4-338">The information displayed is as follows:</span></span>

  - <span data-ttu-id="c5da4-339">Parkee SIP URI。</span><span class="sxs-lookup"><span data-stu-id="c5da4-339">Parkee SIP URI.</span></span>

  - <span data-ttu-id="c5da4-340">Parker SIP URI。</span><span class="sxs-lookup"><span data-stu-id="c5da4-340">Parker SIP URI.</span></span>

  - <span data-ttu-id="c5da4-341">停用通話的 CPS 主機名稱。</span><span class="sxs-lookup"><span data-stu-id="c5da4-341">Host name of the CPS where the call was parked.</span></span>

  - <span data-ttu-id="c5da4-342">檢索或丟棄通話的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="c5da4-342">Time stamp of when the call was retrieved or dropped.</span></span>

- <span data-ttu-id="c5da4-343">\*\*-t\<n\> \*\*參數-測試在資料庫中保留軌道，以顯示指定的軌道編號的隨機性。</span><span class="sxs-lookup"><span data-stu-id="c5da4-343">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

### <a name="output"></a><span data-ttu-id="c5da4-344">收</span><span class="sxs-lookup"><span data-stu-id="c5da4-344">Output</span></span>

<span data-ttu-id="c5da4-345">根據在命令提示字元中指定的輸入參數，呼叫 Parkometer 會顯示下列輸出：</span><span class="sxs-lookup"><span data-stu-id="c5da4-345">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

- <span data-ttu-id="c5da4-346">針對此泳池設定的所有軌道範圍</span><span class="sxs-lookup"><span data-stu-id="c5da4-346">All orbit ranges that are configured for this pool</span></span>

- <span data-ttu-id="c5da4-347">目前停用通話</span><span class="sxs-lookup"><span data-stu-id="c5da4-347">Currently parked calls</span></span>

- <span data-ttu-id="c5da4-348">空閒（可用）軌道式的數目</span><span class="sxs-lookup"><span data-stu-id="c5da4-348">Number of free (available) orbits</span></span>

- <span data-ttu-id="c5da4-349">最近寄存的通話</span><span class="sxs-lookup"><span data-stu-id="c5da4-349">Recently parked calls</span></span>

- <span data-ttu-id="c5da4-350">用於測試均勻與隨機軌道值的保留軌道</span><span class="sxs-lookup"><span data-stu-id="c5da4-350">Reserved orbits for testing uniform and random orbit values</span></span>

### <a name="purpose"></a><span data-ttu-id="c5da4-351">特殊</span><span class="sxs-lookup"><span data-stu-id="c5da4-351">Purpose</span></span>

<span data-ttu-id="c5da4-352">CPS 工具的用途是提供對 CPS 資料庫的命令列存取權。</span><span class="sxs-lookup"><span data-stu-id="c5da4-352">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="c5da4-353">系統管理員可以查看 CPS 使用量，並決定指派給池子的軌道數。</span><span class="sxs-lookup"><span data-stu-id="c5da4-353">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

### <a name="requirements"></a><span data-ttu-id="c5da4-354">需求</span><span class="sxs-lookup"><span data-stu-id="c5da4-354">Requirements</span></span>

<span data-ttu-id="c5da4-355">如果此工具是在執行 CPS 的同一部電腦上執行，就沒有任何需求。</span><span class="sxs-lookup"><span data-stu-id="c5da4-355">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="c5da4-356">如果此工具是在遠端電腦上執行，商務用 Skype Server 2015 所使用的 SQL Server 資料庫必須設定為允許遠端存取。</span><span class="sxs-lookup"><span data-stu-id="c5da4-356">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="c5da4-357">必須使用 SQL Server 資料庫連線字串來設定呼叫 Parkometer，才能連線至該池的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="c5da4-357">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="c5da4-358">這個 SQL Server 資料庫連線字串是在設定檔**parkometer .config**中定義。它必須放在 parkometer 所在的同一個目錄中。</span><span class="sxs-lookup"><span data-stu-id="c5da4-358">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="c5da4-359">下列 XML 檔案就是 parkometer 的範例。必須設定的參數為使用者名稱（例如，mydomain\Administrator）、密碼（例如，mypassword），以及主機名稱（例如 myserver）。</span><span class="sxs-lookup"><span data-stu-id="c5da4-359">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

### <a name="examples"></a><span data-ttu-id="c5da4-360">範例</span><span class="sxs-lookup"><span data-stu-id="c5da4-360">Examples</span></span>

<span data-ttu-id="c5da4-361">已部署的軌道範圍：-o 參數會列出針對此池子設定的所有軌道範圍，如圖所示</span><span class="sxs-lookup"><span data-stu-id="c5da4-361">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

![Call Parkometer 中的軌道範圍。](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

<span data-ttu-id="c5da4-363">目前停用的通話：-n 參數會列出此圖池中所有目前使用的軌道式，如下所示</span><span class="sxs-lookup"><span data-stu-id="c5da4-363">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>

![Call Parkometer 中的目前駐留通話。](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

<span data-ttu-id="c5da4-365">[自由] 軌道式數： f 參數會列出池中目前可用的 [軌道式] 的數目，如圖所示</span><span class="sxs-lookup"><span data-stu-id="c5da4-365">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>

![Call Parkometer 中的可用軌道。](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

<span data-ttu-id="c5da4-367">最近寄存的通話：-r \<n\>參數會列出\<n\>個最後暫停的呼叫（如圖所示）</span><span class="sxs-lookup"><span data-stu-id="c5da4-367">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

![Call Parkometer 中的最近駐留通話。](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

<span data-ttu-id="c5da4-369">測試軌道保留：-t \< \>參數測試在資料庫中保留軌道，如圖所示</span><span class="sxs-lookup"><span data-stu-id="c5da4-369">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

![Call Parkometer 中的測試軌道保留。](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a><span data-ttu-id="c5da4-371">總結</span><span class="sxs-lookup"><span data-stu-id="c5da4-371">Summary</span></span>

<span data-ttu-id="c5da4-372">呼叫 Parkometer 是一種命令列工具，可提供通話寄存伺服器的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="c5da4-372">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

## <a name="dbanalyze"></a><span data-ttu-id="c5da4-373">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="c5da4-373">DBAnalyze</span></span>
<span data-ttu-id="c5da4-374"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="c5da4-374"></span></span>

### <a name="description"></a><span data-ttu-id="c5da4-375">描述</span><span class="sxs-lookup"><span data-stu-id="c5da4-375">Description</span></span>

<span data-ttu-id="c5da4-376">DBAnalyze 是一種命令列工具，可協助管理員收集有關商務用 Skype Server 2015 資料庫的分析報告。</span><span class="sxs-lookup"><span data-stu-id="c5da4-376">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="c5da4-377">DBAnalyze 具有下列模式： [診斷]、[使用者資料]、[會議]、[MCUs] 和 [磁片碎片]：</span><span class="sxs-lookup"><span data-stu-id="c5da4-377">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

- <span data-ttu-id="c5da4-378">**診斷模式**建立包含資料表相關資訊的報表（記錄數、分段、[資料大小]、[索引大小]、[資料及記錄大小]、[每個執行 Microsoft Office 通訊伺服器的伺服器]、[許可權]、[連絡人]、[訂閱]、[發佈]、[每位使用者]、[排程會議]、[使用中會議]，以及無法傳送的會議平均數以及資料庫版本。</span><span class="sxs-lookup"><span data-stu-id="c5da4-378">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c5da4-379">運行診斷模式可能會影響伺服器效能。</span><span class="sxs-lookup"><span data-stu-id="c5da4-379">Running diagnostic mode can affect server performance.</span></span>

- <span data-ttu-id="c5da4-380">**使用者資料模式**針對指定使用者或在連絡人與許可權清單中擁有該使用者的使用者，報告連絡人、容器、訂閱、發佈、許可權和連絡人群組資料。</span><span class="sxs-lookup"><span data-stu-id="c5da4-380">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="c5da4-381">此模式也會報告使用者組織或受邀之會議的摘要資料。</span><span class="sxs-lookup"><span data-stu-id="c5da4-381">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

- <span data-ttu-id="c5da4-382">**會議模式**報告特定會議的詳細資料，包括會議的所有排程時間詳細資料、被邀請者清單、會議所允許的媒體類型清單、作用中 MCUs （multipoint 控制單元）、作用中的參與者清單，以及每個參與者的寄件者狀態。</span><span class="sxs-lookup"><span data-stu-id="c5da4-382">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>

- <span data-ttu-id="c5da4-383">**解碼會議 ID**解碼由 **/pstnid**開關指定的公用交換電話網絡（PSTN）會議 ID，但不會連線到後端以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="c5da4-383">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

- <span data-ttu-id="c5da4-384">**解決會議**解碼由 **/pstnid**開關指定的 PSTN 會議 ID，並顯示由識別碼所指示之會議的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c5da4-384">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

- <span data-ttu-id="c5da4-385">**MCUs 模式**報告池中每個 MCU 的識別碼、媒體類型、URL、心跳狀態、會議載入以及參與者負載。</span><span class="sxs-lookup"><span data-stu-id="c5da4-385">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

- <span data-ttu-id="c5da4-386">**磁片分段模式**顯示所有磁片的碎片狀態。</span><span class="sxs-lookup"><span data-stu-id="c5da4-386">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="c5da4-387">此工具可用於診斷各種問題，或協助系統管理員進行容量規劃。</span><span class="sxs-lookup"><span data-stu-id="c5da4-387">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="c5da4-388">例如，如果大多數駐留在伺服器上的使用者選擇的是伺服器 B 上的使用者作為其連絡人，系統管理員可以將伺服器 A 上的使用者移至伺服器 B，以減少跨伺服器的流量。</span><span class="sxs-lookup"><span data-stu-id="c5da4-388">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

### <a name="output"></a><span data-ttu-id="c5da4-389">收</span><span class="sxs-lookup"><span data-stu-id="c5da4-389">Output</span></span>

<span data-ttu-id="c5da4-390">這個工具會輸出商務用 Skype Server 2015 資料庫的預先定義報告。</span><span class="sxs-lookup"><span data-stu-id="c5da4-390">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="c5da4-391">**路徑**：%ProgramFiles%\Skype For Business Server 2015 \ Reskit</span><span class="sxs-lookup"><span data-stu-id="c5da4-391">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>

### <a name="purpose"></a><span data-ttu-id="c5da4-392">特殊</span><span class="sxs-lookup"><span data-stu-id="c5da4-392">Purpose</span></span>

<span data-ttu-id="c5da4-393">若要安裝 Dbanalyze，請將它複製到本機資料夾，然後執行該工具。</span><span class="sxs-lookup"><span data-stu-id="c5da4-393">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="c5da4-394">若要使用該工具，請從命令列執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="c5da4-394">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="c5da4-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`命令列選項的描述如下所示。</span><span class="sxs-lookup"><span data-stu-id="c5da4-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>

![Dbanalyze.exe 的命令列選項。](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a><span data-ttu-id="c5da4-397">需求</span><span class="sxs-lookup"><span data-stu-id="c5da4-397">Requirements</span></span>

 <span data-ttu-id="c5da4-398">**電腦**DBAnalyze 只能從已安裝商務用 Skype Server 2015 的網域加入電腦執行。</span><span class="sxs-lookup"><span data-stu-id="c5da4-398">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>

 <span data-ttu-id="c5da4-399">**網路**電腦應該能夠連接到後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="c5da4-399">**Network** The computer should be able to connect to the back-end database.</span></span>

 <span data-ttu-id="c5da4-400">**軟體**在執行 DBAnalyze 之前，必須先安裝商務用 Skype Server 2015 軟體元件。</span><span class="sxs-lookup"><span data-stu-id="c5da4-400">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>

 <span data-ttu-id="c5da4-401">**使用者**下表顯示擁有存取商務用 Skype Server 2015 資料庫所需許可權的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="c5da4-401">**Users**The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>

![Dbanalyze.exe 的權限表。](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> <span data-ttu-id="c5da4-403">**/Report：磁片**模式需要本機系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="c5da4-403">A local administrator account is required for **/report:disk** mode.</span></span>

### <a name="examples"></a><span data-ttu-id="c5da4-404">範例</span><span class="sxs-lookup"><span data-stu-id="c5da4-404">Examples</span></span>

<span data-ttu-id="c5da4-405">下列是有效 Dbanalyze 命令的範例：</span><span class="sxs-lookup"><span data-stu-id="c5da4-405">The following are examples of valid Dbanalyze.exe commands:</span></span>

```
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="c5da4-406">總結</span><span class="sxs-lookup"><span data-stu-id="c5da4-406">Summary</span></span>

<span data-ttu-id="c5da4-407">DBAnalyzer 可讓系統管理員快速且輕鬆地分析商務用 Skype Server 2015 資料庫。</span><span class="sxs-lookup"><span data-stu-id="c5da4-407">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>

## <a name="import-storage-service-data"></a><span data-ttu-id="c5da4-408">匯入儲存服務資料</span><span class="sxs-lookup"><span data-stu-id="c5da4-408">Import Storage Service Data</span></span>
<span data-ttu-id="c5da4-409"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="c5da4-409"></span></span>

<span data-ttu-id="c5da4-410">ImportStorageServiceData 資源套件工具可讓您重新匯入儲存空間服務（LYSS）的佇列和端點資料，並傳回儲存服務。</span><span class="sxs-lookup"><span data-stu-id="c5da4-410">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

### <a name="description"></a><span data-ttu-id="c5da4-411">描述</span><span class="sxs-lookup"><span data-stu-id="c5da4-411">Description</span></span>

<span data-ttu-id="c5da4-412">從存儲服務中清除的資料，可能會根據佇列專案狀態或資料庫大小，自動（定期）。</span><span class="sxs-lookup"><span data-stu-id="c5da4-412">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="c5da4-413">這可能是因為手動調用 pool 容錯移轉 Cmdlet，或 StorageServiceFullFlush Cmdlet （這是池容錯移轉 Cmdlet 的調用）。</span><span class="sxs-lookup"><span data-stu-id="c5da4-413">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="c5da4-414">請注意，如果前端的任何儲存服務（LYSS）資料庫大小都在 [標準] 層級之上，則最好不要重新匯入資料，因為這樣做可能只會導致更多資料匯出回來。此外，您應該先解決導致存儲服務佇列增長的錯誤所帶來的任何問題（例如 Exchange 端點錯誤、網路問題或其他問題）。</span><span class="sxs-lookup"><span data-stu-id="c5da4-414">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

 <span data-ttu-id="c5da4-415">**案例1：** 在 pool 進行容錯移轉期間，可能會從每個前端的 storage services 中清除檔案。</span><span class="sxs-lookup"><span data-stu-id="c5da4-415">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="c5da4-416">容錯移轉完成後，應執行該工具，以重新匯入資料。</span><span class="sxs-lookup"><span data-stu-id="c5da4-416">After failover is completed, the tool should be run to re-import the data.</span></span>

 <span data-ttu-id="c5da4-417">**案例2：** 每日自動刷新資料，或以回應超過特定大小閾值的儲存服務資料庫（例如60%、80%、90%）。</span><span class="sxs-lookup"><span data-stu-id="c5da4-417">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="c5da4-418">這個自動刷新的資料應該由系統管理員定期重新匯入。</span><span class="sxs-lookup"><span data-stu-id="c5da4-418">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="c5da4-419">在上述情況下，如果未部署監視 SCOM 套件，則會出現與從儲存服務清除資料相關的商務用 Skype Server Storage 服務事件。</span><span class="sxs-lookup"><span data-stu-id="c5da4-419">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="c5da4-420">32075（完整清除作業的啟動）、32076（完全清除已完成）、32082（維護層級清洗完成）、32083（維護層級清理完成）、32089（因填滿資料庫而發生清洗）等的事件 Id。</span><span class="sxs-lookup"><span data-stu-id="c5da4-420">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="c5da4-421">注意：這些事件識別碼與 RTM 版本相對應。</span><span class="sxs-lookup"><span data-stu-id="c5da4-421">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="c5da4-422">當管理員看到這些事件時，表示檔案中有已清除的檔案。這個資料應該使用這個工具（例如每週一次），重新匯入。</span><span class="sxs-lookup"><span data-stu-id="c5da4-422">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="c5da4-423">如果您是在線上服務版本中部署商務用 Skype Server 的健康情況監視 SCOM 套件，可能會引發新的警示，要求系統管理員重新將清除的資料匯入儲存服務。</span><span class="sxs-lookup"><span data-stu-id="c5da4-423">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="c5da4-424">在前端伺服器上的事件記錄中，會有對應的事件觸發警示。</span><span class="sxs-lookup"><span data-stu-id="c5da4-424">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="c5da4-425">事件將會提供所需的父路徑的描述，以及有多少個檔案會符合警報準則。</span><span class="sxs-lookup"><span data-stu-id="c5da4-425">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="c5da4-426">[警示準則] 是特定父路徑下的 X 或更多檔案，這些檔案至少是最早的 Y 天（在 StorageService 中，X 和 Y 是預先設定的，但可透過變更 APPCONFIG 檔案來覆寫）。下面顯示可觸發健全性警報的兩個事件範例，區別是其父路徑。</span><span class="sxs-lookup"><span data-stu-id="c5da4-426">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="c5da4-427">其中一個可能是在 Web 服務檔案共用下，另一個可能就是每個前端的本機應用程式資料目錄。</span><span class="sxs-lookup"><span data-stu-id="c5da4-427">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="c5da4-428">（例如 c:\ProgramData\Microsoft\Skype Business Server 2015 \ StorageService）。</span><span class="sxs-lookup"><span data-stu-id="c5da4-428">( for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ).</span></span> <span data-ttu-id="c5da4-429">然後，系統管理員會執行這個 reskit 工具。</span><span class="sxs-lookup"><span data-stu-id="c5da4-429">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="c5da4-430">這個工具會在所執行的前端（以及其他前端）上增加 CPU 和 IO 負荷，在此情況下，您的資料不會在執行該工具的前端所擁有。</span><span class="sxs-lookup"><span data-stu-id="c5da4-430">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="c5da4-431">我們建議您在前端不在 CPU 和 IO 負載（例如尖峰時間外）的情況下，runng 此工具。</span><span class="sxs-lookup"><span data-stu-id="c5da4-431">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="c5da4-432">其次，此工具可以2到3分鐘，匯入一個資料檔案。</span><span class="sxs-lookup"><span data-stu-id="c5da4-432">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="c5da4-433">在估計工具執行的時間長度時，請記住這一點。</span><span class="sxs-lookup"><span data-stu-id="c5da4-433">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="c5da4-434">此工具所產生的詳細記錄檔預設會顯示在檔案存放區上。</span><span class="sxs-lookup"><span data-stu-id="c5da4-434">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="c5da4-435">如果沒有報告任何錯誤，請將它刪除，因為記錄檔可能是數十 MB 或更多。</span><span class="sxs-lookup"><span data-stu-id="c5da4-435">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

![Storage Server 事件記錄事件範例。](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a><span data-ttu-id="c5da4-437">需求</span><span class="sxs-lookup"><span data-stu-id="c5da4-437">Requirements</span></span>

<span data-ttu-id="c5da4-438">安裝商務用 Skype Server 2015 資源套件工具。</span><span class="sxs-lookup"><span data-stu-id="c5da4-438">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="c5da4-439">此工具會在已安裝商務用 Skype Server 和商務用 Skype Server Management Shell 的網域加入電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="c5da4-439">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="c5da4-440">此工具會使用來自管理命令介面的 Cmdlet 來找出池中的所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="c5da4-440">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="c5da4-441">其次，您必須從已安裝**RtcLocal**資料庫的池中的電腦執行該工具。</span><span class="sxs-lookup"><span data-stu-id="c5da4-441">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="c5da4-442">此資料庫是由工具用來檢索池子的 WEBSERVICE 檔案共用位置。</span><span class="sxs-lookup"><span data-stu-id="c5da4-442">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="c5da4-443">此外，在使用此工具之前，每個前端伺服器必須先在每個前端伺服器上使用**enable-PSRemoting**啟用 Windows PowerShell 遠端作業，以及執行該工具的電腦。</span><span class="sxs-lookup"><span data-stu-id="c5da4-443">Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="c5da4-444">否則，此工具的遠端 Windows PowerShell 命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="c5da4-444">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="c5da4-445">完成後，就可以在池中的所有前端伺服器上關閉 Windows PowerShell 遠端處理功能。</span><span class="sxs-lookup"><span data-stu-id="c5da4-445">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="c5da4-446">最後，開啟此工具的帳戶或憑證必須擁有其在其上執行這個工具的 [webservice 檔案共用] 的 [讀取/寫入] 許可權。</span><span class="sxs-lookup"><span data-stu-id="c5da4-446">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="c5da4-447">否則，該工具會因 IO 許可權錯誤而失敗。</span><span class="sxs-lookup"><span data-stu-id="c5da4-447">Otherwise the tool will fail with IO Permission errors.</span></span>

> [!NOTE]
> <span data-ttu-id="c5da4-448">在 Windows Server 2012 上，Windows PowerShell Remoting 預設為啟用，但在 Windows Server 2008 作業系統上則無法使用。</span><span class="sxs-lookup"><span data-stu-id="c5da4-448">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>

### <a name="examples"></a><span data-ttu-id="c5da4-449">範例</span><span class="sxs-lookup"><span data-stu-id="c5da4-449">Examples</span></span>

```
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
```

## <a name="lcssync"></a><span data-ttu-id="c5da4-450">LCSSync</span><span class="sxs-lookup"><span data-stu-id="c5da4-450">LCSSync</span></span>
<span data-ttu-id="c5da4-451"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="c5da4-451"></span></span>

<span data-ttu-id="c5da4-452">LCSSync 工具可協助您在多目錄林環境中部署商務用 Skype Server 2015 通訊軟體。</span><span class="sxs-lookup"><span data-stu-id="c5da4-452">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="c5da4-453">這個工具是用來將來自不同使用者目錄林的使用者和群組，作為 Active Directory 網域服務連絡人物件與已安裝商務用 Skype Server 2015 的中央目錄林同步處理。</span><span class="sxs-lookup"><span data-stu-id="c5da4-453">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>

### <a name="description"></a><span data-ttu-id="c5da4-454">描述</span><span class="sxs-lookup"><span data-stu-id="c5da4-454">Description</span></span>

 <span data-ttu-id="c5da4-455">LCSSync 會使用中央林中的同步處理 Active Directory 網域服務連絡人物件，讓使用者使用商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="c5da4-455">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="c5da4-456">若要提供單一登入，主要使用者帳戶必須對應到商務用 Skype Server 2015 的中央林中的 Active Directory 網域服務連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="c5da4-456">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="c5da4-457">此工具可協助執行該對應。</span><span class="sxs-lookup"><span data-stu-id="c5da4-457">This tool helps perform that mapping.</span></span> <span data-ttu-id="c5da4-458">此工具提供範本，可用於在 Microsoft 身分識別整合伺服器中建立管理代理程式。</span><span class="sxs-lookup"><span data-stu-id="c5da4-458">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

### <a name="summary"></a><span data-ttu-id="c5da4-459">總結</span><span class="sxs-lookup"><span data-stu-id="c5da4-459">Summary</span></span>

<span data-ttu-id="c5da4-460">LCSSync 工具可協助您在多目錄林環境中部署商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="c5da4-460">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>

## <a name="lookup-user-console"></a><span data-ttu-id="c5da4-461">查閱使用者主控台</span><span class="sxs-lookup"><span data-stu-id="c5da4-461">Lookup User Console</span></span>
<span data-ttu-id="c5da4-462"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="c5da4-462"></span></span>

<span data-ttu-id="c5da4-463">LookupUserConsole 工具會顯示特定使用者的內部商務用 Skype 伺服器路由資訊。</span><span class="sxs-lookup"><span data-stu-id="c5da4-463">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="c5da4-464">在診斷部署和路由問題時，Microsoft 支援個人資訊可能會很有用。</span><span class="sxs-lookup"><span data-stu-id="c5da4-464">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

### <a name="description"></a><span data-ttu-id="c5da4-465">描述</span><span class="sxs-lookup"><span data-stu-id="c5da4-465">Description</span></span>

 <span data-ttu-id="c5da4-466">執行 LookupUserConsole 會開啟接受 SIP 位址的命令提示字元，並嘗試顯示與它們相關的內部商務用 Skype Server 路由資訊。</span><span class="sxs-lookup"><span data-stu-id="c5da4-466">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="c5da4-467">輸入**exit**以結束 LookupUserConsole 工具。</span><span class="sxs-lookup"><span data-stu-id="c5da4-467">Type **exit** to quit the LookupUserConsole tool.</span></span>

### <a name="requirements"></a><span data-ttu-id="c5da4-468">需求</span><span class="sxs-lookup"><span data-stu-id="c5da4-468">Requirements</span></span>

<span data-ttu-id="c5da4-469">安裝商務用 Skype Server 2015 資源套件。</span><span class="sxs-lookup"><span data-stu-id="c5da4-469">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="c5da4-470">此工具會在安裝商務用 Skype Server 的已加入網域的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="c5da4-470">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>

### <a name="examples"></a><span data-ttu-id="c5da4-471">範例</span><span class="sxs-lookup"><span data-stu-id="c5da4-471">Examples</span></span>

<span data-ttu-id="c5da4-472">C:\Program Files\Skype for Business Server 2015 \ ResKit\>LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="c5da4-472">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>

```
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
```

## <a name="msturnping"></a><span data-ttu-id="c5da4-473">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="c5da4-473">MsTurnPing</span></span>
<span data-ttu-id="c5da4-474"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="c5da4-474"></span></span>

<span data-ttu-id="c5da4-475">MSTurnPing 工具可讓商務用 Skype Server 2015 通訊軟體的管理員檢查執行音訊/視頻邊緣和音訊/視頻驗證服務的伺服器狀態，以及在拓撲中執行頻寬原則服務的伺服器。</span><span class="sxs-lookup"><span data-stu-id="c5da4-475">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

### <a name="description"></a><span data-ttu-id="c5da4-476">描述</span><span class="sxs-lookup"><span data-stu-id="c5da4-476">Description</span></span>

<span data-ttu-id="c5da4-477">MSTurnPing 工具可讓商務用 Skype Server 2015 通訊軟體的管理員檢查執行音訊/視頻邊緣和音訊/視頻驗證服務的伺服器狀態，以及在拓撲中執行頻寬原則服務的伺服器。</span><span class="sxs-lookup"><span data-stu-id="c5da4-477">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="c5da4-478">此工具可讓系統管理員執行下列測試：</span><span class="sxs-lookup"><span data-stu-id="c5da4-478">The tool allows the administrator to perform the following tests:</span></span>

1. <span data-ttu-id="c5da4-479">A/V 邊緣伺服器測試：此工具會執行下列動作，針對拓撲中的所有 A/V 邊緣伺服器執行測試：</span><span class="sxs-lookup"><span data-stu-id="c5da4-479">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>

   - <span data-ttu-id="c5da4-480">驗證已啟動商務用 Skype Server 音訊/視頻驗證服務，並可能發出適當的認證。</span><span class="sxs-lookup"><span data-stu-id="c5da4-480">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="c5da4-481">確認已啟動商務用 Skype Server 音訊/視頻邊緣服務，且可以成功地在外部邊緣上配置資源。</span><span class="sxs-lookup"><span data-stu-id="c5da4-481">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2. <span data-ttu-id="c5da4-482">頻寬原則服務測試：此工具會針對執行拓撲中的頻寬原則服務的所有伺服器執行測試，方法如下：</span><span class="sxs-lookup"><span data-stu-id="c5da4-482">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>

   - <span data-ttu-id="c5da4-483">驗證已啟動商務用 Skype Server 頻寬原則服務（驗證），並可能發出適當的認證。</span><span class="sxs-lookup"><span data-stu-id="c5da4-483">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="c5da4-484">驗證已啟動商務用 Skype Server 頻寬原則服務（核心），並且能夠成功執行頻寬檢查。</span><span class="sxs-lookup"><span data-stu-id="c5da4-484">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="c5da4-485">此工具必須從屬於拓撲的電腦執行，且已安裝本機存儲區。</span><span class="sxs-lookup"><span data-stu-id="c5da4-485">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

### <a name="output"></a><span data-ttu-id="c5da4-486">收</span><span class="sxs-lookup"><span data-stu-id="c5da4-486">Output</span></span>

<span data-ttu-id="c5da4-487">此工具會輸出每個作業的結果。</span><span class="sxs-lookup"><span data-stu-id="c5da4-487">The tool outputs the results of each of the operations.</span></span>

- <span data-ttu-id="c5da4-488">如果執行**AudioVideoEdgeServer**測試，則工具輸出如下：</span><span class="sxs-lookup"><span data-stu-id="c5da4-488">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="c5da4-489">在拓撲中供應商務用 Skype Server 2015 音訊/視頻驗證服務的電腦測試結果</span><span class="sxs-lookup"><span data-stu-id="c5da4-489">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>

  - <span data-ttu-id="c5da4-490">在拓撲中供應商務用 Skype Server 2015 音訊/視頻邊緣服務的電腦測試結果</span><span class="sxs-lookup"><span data-stu-id="c5da4-490">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>

- <span data-ttu-id="c5da4-491">如果執行**BandwidthPolicyServer**測試，則工具輸出如下：</span><span class="sxs-lookup"><span data-stu-id="c5da4-491">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="c5da4-492">在拓撲中供應商務用 Skype Server 2015 頻寬原則服務（驗證）的電腦測試結果</span><span class="sxs-lookup"><span data-stu-id="c5da4-492">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>

  - <span data-ttu-id="c5da4-493">在拓撲中供應商務用 Skype Server 2015 頻寬原則服務（Core）之電腦的測試結果</span><span class="sxs-lookup"><span data-stu-id="c5da4-493">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>

### <a name="requirements"></a><span data-ttu-id="c5da4-494">需求</span><span class="sxs-lookup"><span data-stu-id="c5da4-494">Requirements</span></span>

- <span data-ttu-id="c5da4-495">此工具必須從拓撲中的電腦執行，且具有本機存放區。</span><span class="sxs-lookup"><span data-stu-id="c5da4-495">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

- <span data-ttu-id="c5da4-496">此工具必須以擁有本機存放區存取權的管理員身分執行。</span><span class="sxs-lookup"><span data-stu-id="c5da4-496">The tool must be run as an administrator who has access to the local store.</span></span>

### <a name="examples"></a><span data-ttu-id="c5da4-497">範例</span><span class="sxs-lookup"><span data-stu-id="c5da4-497">Examples</span></span>

<span data-ttu-id="c5da4-498">下列是工具輸入的範例。</span><span class="sxs-lookup"><span data-stu-id="c5da4-498">The following is an example of the tool input.</span></span>

```
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="c5da4-499">總結</span><span class="sxs-lookup"><span data-stu-id="c5da4-499">Summary</span></span>

<span data-ttu-id="c5da4-500">此工具可以是商務用 Skype Server 2015 系統管理員的重要資源，您想要檢查執行音訊/視頻和頻寬原則服務之伺服器的狀態。</span><span class="sxs-lookup"><span data-stu-id="c5da4-500">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

## <a name="network-configuration-viewer"></a><span data-ttu-id="c5da4-501">網路設定檢視器</span><span class="sxs-lookup"><span data-stu-id="c5da4-501">Network Configuration Viewer</span></span>
<span data-ttu-id="c5da4-502"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="c5da4-502"></span></span>

<span data-ttu-id="c5da4-503">商務用 Skype Server 2015 通訊軟體系統管理員可以使用網路設定檢視器來查看已設定為允許即時通訊會話的企業的通話許可控制（CAC）網路拓朴，例如根據指定的頻寬容量進行語音或視頻通話。</span><span class="sxs-lookup"><span data-stu-id="c5da4-503">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="c5da4-504">商務用 skype Server 2015 系統管理員會定義 CAC 原則，這些原則是由使用商務用 Skype Server 2015 所安裝的頻寬原則服務所強制執行。</span><span class="sxs-lookup"><span data-stu-id="c5da4-504">Skype for Business Server 2015 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>

### <a name="description"></a><span data-ttu-id="c5da4-505">描述</span><span class="sxs-lookup"><span data-stu-id="c5da4-505">Description</span></span>

<span data-ttu-id="c5da4-506">網路設定檢視器（NetworkConfigurationViewer）可讓系統管理員執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="c5da4-506">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

- <span data-ttu-id="c5da4-507">從商務用 Skype Server 2015 部署以圖形化格式載入並查看 CAC 網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="c5da4-507">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>

- <span data-ttu-id="c5da4-508">從頻寬原則伺服器記錄檔（以圖形化格式）載入和查看 CAC 網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="c5da4-508">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

- <span data-ttu-id="c5da4-509">將 CAC 網路拓撲儲存並儲存在磁片上的 XML 格式中。</span><span class="sxs-lookup"><span data-stu-id="c5da4-509">Save and store CAC network topology in an XML format on the disk.</span></span>

- <span data-ttu-id="c5da4-510">以 JPG 或 BMP 格式儲存及儲存 CAC 網路拓撲圖表。</span><span class="sxs-lookup"><span data-stu-id="c5da4-510">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

- <span data-ttu-id="c5da4-511">查看 CAC 網路拓朴配置資料。</span><span class="sxs-lookup"><span data-stu-id="c5da4-511">View CAC network topology configuration data.</span></span>

- <span data-ttu-id="c5da4-512">以樹狀檢視樣式查看 CAC 網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="c5da4-512">View CAC network topology in a tree-view style.</span></span>

- <span data-ttu-id="c5da4-513">定義 CAC 網路拓撲連結的自訂連接器（例如，點對點、區域對區域及網站間連結）。</span><span class="sxs-lookup"><span data-stu-id="c5da4-513">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

- <span data-ttu-id="c5da4-514">查看 CAC 網路拓撲網站資訊、區域資訊，以及已置備的頻寬原則和網路連結。</span><span class="sxs-lookup"><span data-stu-id="c5da4-514">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

### <a name="purpose"></a><span data-ttu-id="c5da4-515">特殊</span><span class="sxs-lookup"><span data-stu-id="c5da4-515">Purpose</span></span>

<span data-ttu-id="c5da4-516">在圖形介面中，查看企業版 CAC 網路拓撲連結。</span><span class="sxs-lookup"><span data-stu-id="c5da4-516">View enterprise CAC network topology links in a graphical interface.</span></span>

### <a name="examples"></a><span data-ttu-id="c5da4-517">範例</span><span class="sxs-lookup"><span data-stu-id="c5da4-517">Examples</span></span>

 <span data-ttu-id="c5da4-518">**從商務用 Skype server 2015 部署（以圖形化格式）載入及查看 cac 網路拓朴**：商務用 skype server 2015 系統管理員可以使用 [**下載網路**設定] 選項，在任何商務用 skype server 2015 電腦上載入並查看 cac 網路拓撲設定，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="c5da4-518">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="c5da4-519">當您在未連線至商務用 Skype Server 2015 配置存放區的電腦上部署時，工具將無法下載或查看此類設定。</span><span class="sxs-lookup"><span data-stu-id="c5da4-519">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>

![下載網路設定。](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 <span data-ttu-id="c5da4-521">**從頻寬原則伺服器記錄檔，以圖形格式載入和查看 CAC 網路拓朴：** 商務用 skype Server 2015 頻寬原則伺服器會將 CAC 網路拓朴儲存為在商務用 Skype Server 2015 檔案共用位置下的記錄機制的一部分。</span><span class="sxs-lookup"><span data-stu-id="c5da4-521">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="c5da4-522">商務用 Skype Server 2015 系統管理員可以使用 [**開啟網路**設定] 選項，以圖形格式來查看此類檔案，如下所示。</span><span class="sxs-lookup"><span data-stu-id="c5da4-522">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

![開啟 Bandwidth Policy Server 記錄檔。](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

<span data-ttu-id="c5da4-524">將 CAC 網路拓撲儲存並儲存在磁片上的 XML 格式：商務用 Skype Server 2015 系統管理員可以使用 [**儲存網路設定複本**] 選項，以 xml 格式儲存 cac 網路拓撲設定檔，如下所示。</span><span class="sxs-lookup"><span data-stu-id="c5da4-524">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="c5da4-525">然後，儲存的設定檔案可以在離線時使用，以進行圖形化查看。</span><span class="sxs-lookup"><span data-stu-id="c5da4-525">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

![將網路設定儲存為 XML 檔。](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

<span data-ttu-id="c5da4-527">以 JPG 或 BMP 格式儲存及儲存 CAC 網路拓撲圖：商務用 Skype Server 2015 系統管理員可以使用 [**另存網路設定圖表為圖片**] 選項，將 cac 網路拓撲設定儲存為圖形格式（JPG 和 BMP 檔案格式），如下所示。</span><span class="sxs-lookup"><span data-stu-id="c5da4-527">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

![將網路設定儲存為圖片。](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <span data-ttu-id="c5da4-529"><strong>查看 CAC 網路拓朴配置資料：</strong>商務用 Skype Server 2015 系統管理員可以使用 [查看網路設定資料] 選項，以文字格式來查看相關的網路設定資料，例如網路區域、網路網站、頻寬設定檔，以及網站子網 IP 位址（如下所示）。</span><span class="sxs-lookup"><span data-stu-id="c5da4-529"><strong>View CAC network topology configuration data:</strong>Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

![檢視網路設定資料。](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 <span data-ttu-id="c5da4-531">**以樹狀檢視樣式查看 CAC 網路拓撲：** 商務用 Skype Server 2015 系統管理員可以使用工具視窗左側的 [控制台]，以圖形樹狀結構視圖樣式來查看相關的網路設定資料，如下所示。</span><span class="sxs-lookup"><span data-stu-id="c5da4-531">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

![以樹狀檢視的形式檢視網路設定資料。](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 <span data-ttu-id="c5da4-533">**定義 CAC 網路拓撲連結的自訂連接器（例如點對點、區域對區域及網站到網站連結）：** 商務用 Skype Server 2015 系統管理員可以使用 [設定] 選項來定義 CAC 網路設定 WAN 連結的自訂圖形連接器，如下所示。</span><span class="sxs-lookup"><span data-stu-id="c5da4-533">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="c5da4-534">這有助於區分網路設定中提供的各種類型的網路連結。</span><span class="sxs-lookup"><span data-stu-id="c5da4-534">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

![工具箱](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 <span data-ttu-id="c5da4-536">**查看 CAC 網路拓撲網站資訊、區域資訊，以及已置備的頻寬原則：** 商務用 Skype Server 2015 系統管理員可以使用下列選項，查看相關的 CAC 網路區域資訊、網站資訊和 CAC 頻寬提供資訊。</span><span class="sxs-lookup"><span data-stu-id="c5da4-536">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="c5da4-537">（例如，按一下 [網路區域] 或 [網路網站] 物件中的 [**資訊**]。）</span><span class="sxs-lookup"><span data-stu-id="c5da4-537">(For example, click **Info** in a network region or network site object.)</span></span>

![為您的網路定義自訂連接器。](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a><span data-ttu-id="c5da4-539">總結</span><span class="sxs-lookup"><span data-stu-id="c5da4-539">Summary</span></span>

<span data-ttu-id="c5da4-540">此工具可能是商務用 Skype Server 2015 系統管理員的重要資源，想要以圖形式格式來查看其部署的 CAC 網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="c5da4-540">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

## <a name="response-group-agent-live"></a><span data-ttu-id="c5da4-541">回應群組代理程式即時</span><span class="sxs-lookup"><span data-stu-id="c5da4-541">Response Group Agent Live</span></span>
<span data-ttu-id="c5da4-542"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="c5da4-542"></span></span>

<span data-ttu-id="c5da4-543">回應群組應用程式讓代理能夠使用其內建的 Web 服務存取有用的即時資訊。</span><span class="sxs-lookup"><span data-stu-id="c5da4-543">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="c5da4-544">遺憾的是，在應用程式以外不提供此資料的圖形視圖。</span><span class="sxs-lookup"><span data-stu-id="c5da4-544">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="c5da4-545">回應群組代理程式動態資源套件工具可提供一種簡單且圖形化的方式來存取此資訊，並使用即時 Skype 通訊軟體資訊（例如其他代理的目前狀態）加強。</span><span class="sxs-lookup"><span data-stu-id="c5da4-545">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>

### <a name="description"></a><span data-ttu-id="c5da4-546">描述</span><span class="sxs-lookup"><span data-stu-id="c5da4-546">Description</span></span>

<span data-ttu-id="c5da4-547">回應群組代理程式活是一種 Windows 應用程式，可提供登入和登出功能，以及一些即時資訊（例如，群組成員資格和目前的呼叫數量）到回應群組代理程式。</span><span class="sxs-lookup"><span data-stu-id="c5da4-547">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="c5da4-548">它應該是 [代理群組] 頁面的增強版本（可從商務用 Skype 存取）。</span><span class="sxs-lookup"><span data-stu-id="c5da4-548">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>

### <a name="purpose"></a><span data-ttu-id="c5da4-549">特殊</span><span class="sxs-lookup"><span data-stu-id="c5da4-549">Purpose</span></span>

<span data-ttu-id="c5da4-550">回應群組應用程式會列隊來電，然後將它們路由到 [代理群組]。</span><span class="sxs-lookup"><span data-stu-id="c5da4-550">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="c5da4-551">若要對服務的呼叫作出明智的決定，agent 可以存取其代理群組的即時資訊，例如，還有哪些其他代理程式，以及每個佇列中等候多少通話。</span><span class="sxs-lookup"><span data-stu-id="c5da4-551">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="c5da4-552">此資訊最初隻能透過回應群組服務存取，以直觀的方式提供給回應群組代理程式。</span><span class="sxs-lookup"><span data-stu-id="c5da4-552">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

#### <a name="features"></a><span data-ttu-id="c5da4-553">Features</span><span class="sxs-lookup"><span data-stu-id="c5da4-553">Features</span></span>

<span data-ttu-id="c5da4-554">回應群組代理程式即時工具是在回應群組服務和商務用 Skype Server 2015 SDK 中建立。</span><span class="sxs-lookup"><span data-stu-id="c5da4-554">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="c5da4-555">它提供回應群組的代理人：回應群組服務提供的資訊和功能（例如群組成員資格、其他代理程式的目前狀態，以及等待通話的次數）。</span><span class="sxs-lookup"><span data-stu-id="c5da4-555">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="c5da4-556">下圖說明回應群組代理程式的主要介面。</span><span class="sxs-lookup"><span data-stu-id="c5da4-556">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

![Response Group Agent Live 工具。](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

<span data-ttu-id="c5da4-558">下列三個主要功能適用于回應群組代理程式中的代理程式：</span><span class="sxs-lookup"><span data-stu-id="c5da4-558">The following three main features are available for agents in Response Group Agent Live:</span></span>

- <span data-ttu-id="c5da4-559">登**入/取出：** 與 [代理群組] 頁面相反（可從商務用 Skype Server 2015 存取），回應群組代理程式即時只允許代理程式一次登入或登出所有的代理群組。</span><span class="sxs-lookup"><span data-stu-id="c5da4-559">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="c5da4-560">此應用程式提供三種快速代理程式登入或登出的方法：</span><span class="sxs-lookup"><span data-stu-id="c5da4-560">This application provides three quick ways for agents to sign in or out:</span></span>

  - <span data-ttu-id="c5da4-561">按一下應用程式內的 [登入/取出] （綠色和紅色）按鈕。</span><span class="sxs-lookup"><span data-stu-id="c5da4-561">Click the Sign-in/out (green and red) buttons within the application.</span></span>

  - <span data-ttu-id="c5da4-562">以滑鼠右鍵按一下系統工作列圖示，然後選取 [登入] 或 [登出]。</span><span class="sxs-lookup"><span data-stu-id="c5da4-562">Right-click the system tray icon, and select sign in or sign out.</span></span>

  - <span data-ttu-id="c5da4-563">使用可設定的鍵盤快速鍵。</span><span class="sxs-lookup"><span data-stu-id="c5da4-563">Using configurable keyboard shortcuts.</span></span>

- <span data-ttu-id="c5da4-564">**群組成員資格：** 選取 [代理群組] 後，[回應群組代理程式即時] 會在右側窗格中顯示 [此群組中的 agent 清單]。</span><span class="sxs-lookup"><span data-stu-id="c5da4-564">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="c5da4-565">如果商務用 Skype Server 2015 是在與此應用程式相同的電腦上執行，目前狀態資訊和連絡人卡片會顯示在回應群組代理程式中。</span><span class="sxs-lookup"><span data-stu-id="c5da4-565">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="c5da4-566">代理程式可以傳送 IM，或直接從該處呼叫其他的代理程式。</span><span class="sxs-lookup"><span data-stu-id="c5da4-566">Agents can send an IM or call other agents directly from there.</span></span>

- <span data-ttu-id="c5da4-567">**即時統計資料：** 回應群組代理程式即時為所有代理群組提供即時統計資料。</span><span class="sxs-lookup"><span data-stu-id="c5da4-567">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="c5da4-568">更新頻率為1分鐘。</span><span class="sxs-lookup"><span data-stu-id="c5da4-568">The update frequency is one minute.</span></span> <span data-ttu-id="c5da4-569">當回應群組接聽來電時，會在組名旁加上目前已排隊通話的視覺指標。</span><span class="sxs-lookup"><span data-stu-id="c5da4-569">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="c5da4-570">將指標暫停在群組上也會顯示最長的等待時間。</span><span class="sxs-lookup"><span data-stu-id="c5da4-570">Pausing the pointer over a group also displays the longest waiting time.</span></span>

### <a name="requirements"></a><span data-ttu-id="c5da4-571">需求</span><span class="sxs-lookup"><span data-stu-id="c5da4-571">Requirements</span></span>

<span data-ttu-id="c5da4-572">回應群組代理程式即時需要 .NET Framework 4.0。</span><span class="sxs-lookup"><span data-stu-id="c5da4-572">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="c5da4-573">此外，若要充分利用目前狀態與連絡人卡片的功能，必須在本機安裝商務用 Skype （且正在執行）。</span><span class="sxs-lookup"><span data-stu-id="c5da4-573">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>

#### <a name="configuration"></a><span data-ttu-id="c5da4-574">Configuration</span><span class="sxs-lookup"><span data-stu-id="c5da4-574">Configuration</span></span>

<span data-ttu-id="c5da4-575">您可以使用應用程式中的 [選項] 對話方塊，將回應群組代理程式即時自訂為個別的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="c5da4-575">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="c5da4-576">此外，管理員可以直接編輯 RGAgentLive 檔案的 defaultHostAddress 屬性，來定義預設的主機位址。</span><span class="sxs-lookup"><span data-stu-id="c5da4-576">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="c5da4-577">下圖說明代理程式可用來設定主機位址和快速鍵的 [選項] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="c5da4-577">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="c5da4-578">按一下主要介面右上方的 [選項] 按鈕，即可存取此對話方塊。</span><span class="sxs-lookup"><span data-stu-id="c5da4-578">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

![Response Group Agent Live [Options] (選項) 對話方塊。](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

<span data-ttu-id="c5da4-580">在回應群組代理程式即時設定中，您可以自訂下列三個不同的設定：</span><span class="sxs-lookup"><span data-stu-id="c5da4-580">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

- <span data-ttu-id="c5da4-581">主機位址：這通常是屬於代理的主池中的網頁池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c5da4-581">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="c5da4-582">確切的回應群組服務位址會自動衍生於此資訊的背景中（透過在主機之後附加正確路徑）。</span><span class="sxs-lookup"><span data-stu-id="c5da4-582">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

- <span data-ttu-id="c5da4-583">快速鍵：您可以自訂正確的登入/登出快速鍵。</span><span class="sxs-lookup"><span data-stu-id="c5da4-583">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="c5da4-584">唯一的限制是，兩個快速鍵都必須包含「Windows 標誌」金鑰（除了至少一個金鑰之外）。</span><span class="sxs-lookup"><span data-stu-id="c5da4-584">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>

- <span data-ttu-id="c5da4-585">從 Windows 開始：應用程式可以設定為使用 Windows 自動啟動。</span><span class="sxs-lookup"><span data-stu-id="c5da4-585">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

### <a name="examples"></a><span data-ttu-id="c5da4-586">範例</span><span class="sxs-lookup"><span data-stu-id="c5da4-586">Examples</span></span>

<span data-ttu-id="c5da4-587">下圖說明如何在右側窗格中，以滑鼠右鍵按一下連絡人，以呼叫或傳送 IM 給另一個代理程式。</span><span class="sxs-lookup"><span data-stu-id="c5da4-587">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

![撥打電話或傳送 IM。](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

<span data-ttu-id="c5da4-589">下圖說明回應群組代理程式的即時顯示佇列中目前的通話數，以及所有這些來電間的最長等待時間。</span><span class="sxs-lookup"><span data-stu-id="c5da4-589">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

![檢視佇列資訊。](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a><span data-ttu-id="c5da4-591">總結</span><span class="sxs-lookup"><span data-stu-id="c5da4-591">Summary</span></span>

<span data-ttu-id="c5da4-592">快速登入和登出、群組成員資格，以及基本的即時統計資料，只提供回應群組代理程式功能，且僅可在應用程式之外從回應群組服務存取。</span><span class="sxs-lookup"><span data-stu-id="c5da4-592">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="c5da4-593">使用 [回應] 群組代理程式即時資源套件工具時，商務用 Skype Server 2015 系統管理員可以使用 Windows 應用程式提供其代理程式，讓他們能夠以更快速且圖形的方式執行工作。</span><span class="sxs-lookup"><span data-stu-id="c5da4-593">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

## <a name="sefautil"></a><span data-ttu-id="c5da4-594">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="c5da4-594">SEFAUtil</span></span>
<span data-ttu-id="c5da4-595"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="c5da4-595"></span></span>

<span data-ttu-id="c5da4-596">SEFAUtil （次要延伸功能啟用）是一種命令列工具，可讓商務用 Skype Server 2015 通訊軟體管理員與技術支援人員設定代理人撥打、來電轉接、同時撥打[小組通話] 設定和 [代表商務用 Skype Server 2015] 使用者撥打電話給 [群組]。</span><span class="sxs-lookup"><span data-stu-id="c5da4-596">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="c5da4-597">此工具也可讓系統管理員查詢針對特定使用者發佈的呼叫路由設定。SEFAUtil 工具可讓系統管理員自行啟用/停用/修改來電轉接或同時撥打給使用者。</span><span class="sxs-lookup"><span data-stu-id="c5da4-597">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="c5da4-598">系統管理員可以指定目標（以 SIP URI 的形式），或使用使用者已發佈的目標。</span><span class="sxs-lookup"><span data-stu-id="c5da4-598">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="c5da4-599">此工具也可讓系統管理員代表使用者新增或移除代理人或小組通話群組成員。此工具是在 Microsoft 整合通訊 Managed API （UCMA）3.0 上建立，且要求管理員在中央管理儲存體中建立 SEFAUtil 的信任應用程式。</span><span class="sxs-lookup"><span data-stu-id="c5da4-599">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>

<span data-ttu-id="c5da4-600">SEFAUtil （次要延伸功能啟用）可讓商務用 Skype Server 2015 系統管理員和支援人員在 Skype 中設定代理人響鈴、來電轉接、同時撥打、團隊通話設定和群組通話提貨商務用伺服器2015使用者。</span><span class="sxs-lookup"><span data-stu-id="c5da4-600">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="c5da4-601">此工具也可讓系統管理員查詢針對特定使用者發佈的呼叫路由設定。</span><span class="sxs-lookup"><span data-stu-id="c5da4-601">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

### <a name="description"></a><span data-ttu-id="c5da4-602">描述</span><span class="sxs-lookup"><span data-stu-id="c5da4-602">Description</span></span>

<span data-ttu-id="c5da4-603">目前的 SEFAUtil 版本只是一個命令列工具;沒有支援圖形使用者介面。</span><span class="sxs-lookup"><span data-stu-id="c5da4-603">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="c5da4-604">此工具是以 Microsoft 整合通訊管理 API （UCMA）3.0 為基礎。</span><span class="sxs-lookup"><span data-stu-id="c5da4-604">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="c5da4-605">此工具中的功能可讓系統管理員和支援人員執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="c5da4-605">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

- <span data-ttu-id="c5da4-606">查看使用者的所有呼叫路由設定（包括來電轉接、委派、同時撥打、團隊通話和群組通話取貨）</span><span class="sxs-lookup"><span data-stu-id="c5da4-606">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

- <span data-ttu-id="c5da4-607">啟用/停用/修改來電轉接設定（包括目的地和無應答計時器）</span><span class="sxs-lookup"><span data-stu-id="c5da4-607">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

- <span data-ttu-id="c5da4-608">啟用/停用/修改來電轉接立即設定</span><span class="sxs-lookup"><span data-stu-id="c5da4-608">Enable/disable/modify call-forwarding immediate configurations</span></span>

- <span data-ttu-id="c5da4-609">啟用/停用/修改委派設定</span><span class="sxs-lookup"><span data-stu-id="c5da4-609">Enable/disable/modify delegation settings</span></span>

- <span data-ttu-id="c5da4-610">啟用/停用/修改小組通話群組設定</span><span class="sxs-lookup"><span data-stu-id="c5da4-610">Enable/disable/modify team-call group settings</span></span>

    > [!NOTE]
    > <span data-ttu-id="c5da4-611">商務用 Skype Server 2015 SEFAUtil 工具的新功能</span><span class="sxs-lookup"><span data-stu-id="c5da4-611">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="c5da4-612">啟用/停用/修改同時震鈴設定（包括目的地）</span><span class="sxs-lookup"><span data-stu-id="c5da4-612">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>

    > [!NOTE]
    > <span data-ttu-id="c5da4-613">商務用 Skype Server 2015 SEFAUtil 工具的新功能</span><span class="sxs-lookup"><span data-stu-id="c5da4-613">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="c5da4-614">啟用/停用/修改群組呼叫挑選設定</span><span class="sxs-lookup"><span data-stu-id="c5da4-614">Enable/disable/modify group call pickup settings</span></span>

    > [!CAUTION]
    > <span data-ttu-id="c5da4-615">商務用 Skype Server 2015 SEFAUtil 工具的新功能</span><span class="sxs-lookup"><span data-stu-id="c5da4-615">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

<span data-ttu-id="c5da4-616">此工具有下列限制：</span><span class="sxs-lookup"><span data-stu-id="c5da4-616">This tool has the following limitations:</span></span>

- <span data-ttu-id="c5da4-617">僅支援駐留在商務用 Skype 伺服器池中的使用者</span><span class="sxs-lookup"><span data-stu-id="c5da4-617">Supported only for users homed in a Skype for Business Server pool</span></span>

- <span data-ttu-id="c5da4-618">不支援多個使用者的通話路由設定的大量編輯</span><span class="sxs-lookup"><span data-stu-id="c5da4-618">Bulk-edit of call routing settings for several users is not supported</span></span>

### <a name="output"></a><span data-ttu-id="c5da4-619">收</span><span class="sxs-lookup"><span data-stu-id="c5da4-619">Output</span></span>

<span data-ttu-id="c5da4-620">此工具的目前版本只會在命令提示字元視窗中提供輸出。</span><span class="sxs-lookup"><span data-stu-id="c5da4-620">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="c5da4-621">如需詳細資訊，請參閱本檔稍後的範例一節。</span><span class="sxs-lookup"><span data-stu-id="c5da4-621">For details, see the Examples section later in this document.</span></span>

### <a name="purpose"></a><span data-ttu-id="c5da4-622">特殊</span><span class="sxs-lookup"><span data-stu-id="c5da4-622">Purpose</span></span>

<span data-ttu-id="c5da4-623">以下是可使用此工具的一些主要案例：</span><span class="sxs-lookup"><span data-stu-id="c5da4-623">Following are some of the key scenarios where this tool may be used:</span></span>

- <span data-ttu-id="c5da4-624">Bob 是一個主管，並已移至商務用 Skype Server 電話。</span><span class="sxs-lookup"><span data-stu-id="c5da4-624">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="c5da4-625">他在現有的 PBX 系統上擁有委派。</span><span class="sxs-lookup"><span data-stu-id="c5da4-625">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="c5da4-626">在 [移至商務用 Skype Server 2015] 中，管理員可以設定 Bob 的路由，以反映其預先存在的委派設定。</span><span class="sxs-lookup"><span data-stu-id="c5da4-626">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>

- <span data-ttu-id="c5da4-627">劉愛琳正在旅行，意識到她期待從她的一位客戶進行重要的通話。</span><span class="sxs-lookup"><span data-stu-id="c5da4-627">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="c5da4-628">不過，她是在賓館中，沒有電腦的存取權。</span><span class="sxs-lookup"><span data-stu-id="c5da4-628">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="c5da4-629">她撥打電話給支援人員，並要求他們轉寄給自己的手機電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c5da4-629">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="c5da4-630">技術支援人員可以代表自己進行設定。</span><span class="sxs-lookup"><span data-stu-id="c5da4-630">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

- <span data-ttu-id="c5da4-631">Joe 在工作時，來電會傳送給他的行動電話語音信箱;不過，在大多數其他位置，情況看起來都能正常運作。</span><span class="sxs-lookup"><span data-stu-id="c5da4-631">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="c5da4-632">技術支援專家可以查看 Joe 的路線配置，並探索李先生已將來電設定為行動電話。</span><span class="sxs-lookup"><span data-stu-id="c5da4-632">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="c5da4-633">技術人員會在其辦公室向 Joe 提出有關行動裝置的詳細資料，並能判斷同時撥打的規則，在網路覆蓋品質較差的情況下，也會導致來電移至 Joe 的行動電話語音。</span><span class="sxs-lookup"><span data-stu-id="c5da4-633">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>

- <span data-ttu-id="c5da4-634">Mike 是 Contoso 中的新員工，他正在加入一個新的小組，在該小組中，所有成員都是針對小組通話設定，當您啟用商務用 Skype Server 2015 時，系統管理員可以設定其小組通話群組設定，以包含所有新的團隊成員此外，系統管理員會將 Mike 新增為小組中每個成員的小組通話群組成員。</span><span class="sxs-lookup"><span data-stu-id="c5da4-634">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

- <span data-ttu-id="c5da4-635">在 Contoso，在人力資源部門中的客戶服務慣例是在第一次呼叫後為所有的呼叫者提供個人服務。</span><span class="sxs-lookup"><span data-stu-id="c5da4-635">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="c5da4-636">假設整個部門中的所有成員都非常接近彼此，所以使用小組通話同時撥打所有電話，就會對小組造成很大的中斷。</span><span class="sxs-lookup"><span data-stu-id="c5da4-636">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="c5da4-637">若要在不中斷團隊成員的情況下提供最佳服務，商務用 Skype Server 2015 管理員會利用群組呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="c5da4-637">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="c5da4-638">系統管理員會將所有部門成員新增到裝貨群組，並向該部門傳達挑選群組的編號。</span><span class="sxs-lookup"><span data-stu-id="c5da4-638">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="c5da4-639">如果 Samantha 不在她的辦公桌中，Joe 會通知她的電話響，他接著接聽她的通話。</span><span class="sxs-lookup"><span data-stu-id="c5da4-639">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

### <a name="requirements"></a><span data-ttu-id="c5da4-640">需求</span><span class="sxs-lookup"><span data-stu-id="c5da4-640">Requirements</span></span>

<span data-ttu-id="c5da4-641">SEFAUtil 工具只能在屬於受信任的應用程式池的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="c5da4-641">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="c5da4-642">UCMA 3.0 必須安裝在該電腦上。</span><span class="sxs-lookup"><span data-stu-id="c5da4-642">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="c5da4-643">若要執行該工具，必須在該池中建立具有 SEFAUtil 應用程式識別碼的新信任應用程式。</span><span class="sxs-lookup"><span data-stu-id="c5da4-643">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="c5da4-644">為 SEFAUtil 工具建立新的信任應用程式</span><span class="sxs-lookup"><span data-stu-id="c5da4-644">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="c5da4-645">SEFAUTil 工具只能在屬於受信任的應用程式池的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="c5da4-645">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="c5da4-646">如有需要，您可以透過商務用 Skype Server Management 命令介面（含下列 Cmdlet）來將池新增為新的受信任的應用程式池：</span><span class="sxs-lookup"><span data-stu-id="c5da4-646">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>

   ```PowerShell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > <span data-ttu-id="c5da4-647">UCMA 3.0 必須安裝在任何將用來執行 SEFAUtil 工具的電腦上。</span><span class="sxs-lookup"><span data-stu-id="c5da4-647">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

2. <span data-ttu-id="c5da4-648">受信任的應用程式必須在 SEFAUtil 工具的拓撲中定義。</span><span class="sxs-lookup"><span data-stu-id="c5da4-648">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="c5da4-649">若要將 SEFAUtil 定義為新的受信任的應用程式，請使用商務用 Skype Server 管理命令介面，並執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c5da4-649">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span>

   ```PowerShell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="c5da4-650">如有需要，您可以使用不同的埠。</span><span class="sxs-lookup"><span data-stu-id="c5da4-650">A different port can be used if needed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c5da4-651">[池 FQDN]：將裝載 SEFAUtil 應用程式的伺服器或池的 FQDN （通常是商務用 Skype 前端伺服器 > 或 pool）。</span><span class="sxs-lookup"><span data-stu-id="c5da4-651">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server     > or pool).</span></span>
    > <span data-ttu-id="c5da4-652">Pool 註冊機構 FQDN：與此應用程式池關聯的商務用 Skype 前端伺服器或池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c5da4-652">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="c5da4-653">[文件庫網站]：此池所駐留的網站的 [網站識別碼]。</span><span class="sxs-lookup"><span data-stu-id="c5da4-653">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

3. <span data-ttu-id="c5da4-654">需要啟用拓撲變更。</span><span class="sxs-lookup"><span data-stu-id="c5da4-654">The topology changes need to be enabled.</span></span> <span data-ttu-id="c5da4-655">您可以透過執行下列 Cmdlet，透過商務用 Skype Server Management Shell 來啟用拓撲變更：</span><span class="sxs-lookup"><span data-stu-id="c5da4-655">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span>

   ```PowerShell
   Enable-CsToplogy
   ```

4. <span data-ttu-id="c5da4-656">如有需要，請在將用來執行 SEFAUtil 工具的伺服器中，安裝商務用 Skype Server 2015 資源套件工具（伺服器必須是受信任的應用程式池的一部分）。</span><span class="sxs-lookup"><span data-stu-id="c5da4-656">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5. <span data-ttu-id="c5da4-657">驗證 SEFAUtil 是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="c5da4-657">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="c5da4-658">若要這樣做，請從具有系統管理員許可權的 windows 命令提示字元執行該工具，以在部署中顯示使用者的來電轉接設定。</span><span class="sxs-lookup"><span data-stu-id="c5da4-658">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="c5da4-659">根據預設，該工具會位於： "Business Server 2015 \ Reskit 中的 ..\Program Files\Skype]。</span><span class="sxs-lookup"><span data-stu-id="c5da4-659">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="c5da4-660">若要顯示使用者的來電轉接設定，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="c5da4-660">To display the call forwarding settings of a user, use the following command:</span></span>

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    <span data-ttu-id="c5da4-661">隨即會顯示使用者的來電轉接設定。</span><span class="sxs-lookup"><span data-stu-id="c5da4-661">The call forwarding settings of the user should be displayed.</span></span>

#### <a name="group-call-pickup"></a><span data-ttu-id="c5da4-662">群組來電接聽</span><span class="sxs-lookup"><span data-stu-id="c5da4-662">Group Call Pickup</span></span>

<span data-ttu-id="c5da4-663">[群組通話挑選] 需要在商務用 Skype Server 2015 中進行其他設定，才能完全啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="c5da4-663">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="c5da4-664">將拾取群組指派給使用者之前，請參閱群組通話產品檔，瞭解此功能的規劃與部署步驟。</span><span class="sxs-lookup"><span data-stu-id="c5da4-664">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

### <a name="examples"></a><span data-ttu-id="c5da4-665">範例</span><span class="sxs-lookup"><span data-stu-id="c5da4-665">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="c5da4-666">顯示目前的通話處理設定</span><span class="sxs-lookup"><span data-stu-id="c5da4-666">Display Current Call Handling Settings</span></span>

<span data-ttu-id="c5da4-667">下列命令會顯示使用者的通話處理。</span><span class="sxs-lookup"><span data-stu-id="c5da4-667">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> <span data-ttu-id="c5da4-668">這個範例使用 **/server**開關來指定要連線的商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="c5da4-668">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>

 <span data-ttu-id="c5da4-669">**收**</span><span class="sxs-lookup"><span data-stu-id="c5da4-669">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="c5da4-670">將呼叫轉寄/無應答目的地</span><span class="sxs-lookup"><span data-stu-id="c5da4-670">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="c5da4-671">這個範例會將呼叫轉寄/沒有應答目的地和響鈴延遲設定。</span><span class="sxs-lookup"><span data-stu-id="c5da4-671">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="c5da4-672">此處未提供/server 開關;SEFAUtil 嘗試自動探索商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="c5da4-672">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 <span data-ttu-id="c5da4-673">**收**</span><span class="sxs-lookup"><span data-stu-id="c5da4-673">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="c5da4-674">立即啟用來電轉接</span><span class="sxs-lookup"><span data-stu-id="c5da4-674">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="c5da4-675">這個範例會立即啟用來電轉接給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="c5da4-675">This example immediately enables call-forwarding to another user.</span></span>

```
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="c5da4-676">**收**</span><span class="sxs-lookup"><span data-stu-id="c5da4-676">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="c5da4-677">立即停用來電轉接</span><span class="sxs-lookup"><span data-stu-id="c5da4-677">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="c5da4-678">這個範例會立即停用 [來電轉接]。</span><span class="sxs-lookup"><span data-stu-id="c5da4-678">This example immediately disables call forwarding.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
```

 <span data-ttu-id="c5da4-679">**收**</span><span class="sxs-lookup"><span data-stu-id="c5da4-679">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="c5da4-680">將使用者新增為代理人，並設定同時撥打代理人</span><span class="sxs-lookup"><span data-stu-id="c5da4-680">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="c5da4-681">這個範例會將使用者新增為代理人，並設定同時撥打的代理人。</span><span class="sxs-lookup"><span data-stu-id="c5da4-681">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="c5da4-682">**收**</span><span class="sxs-lookup"><span data-stu-id="c5da4-682">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="c5da4-683">變更代理人的同時震鈴規則</span><span class="sxs-lookup"><span data-stu-id="c5da4-683">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="c5da4-684">這個範例會將在先前範例中設定的同時響鈴規則變更為 [延遲的響鈴] 規則。</span><span class="sxs-lookup"><span data-stu-id="c5da4-684">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="c5da4-685">**收**</span><span class="sxs-lookup"><span data-stu-id="c5da4-685">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="c5da4-686">移除代理人</span><span class="sxs-lookup"><span data-stu-id="c5da4-686">Remove the Delegate</span></span>

<span data-ttu-id="c5da4-687">這個範例會移除代理人。</span><span class="sxs-lookup"><span data-stu-id="c5da4-687">This example removes the delegate.</span></span>

> [!NOTE]
> <span data-ttu-id="c5da4-688">移除最後一個代理人時，系統會自動停用委派鈴聲。</span><span class="sxs-lookup"><span data-stu-id="c5da4-688">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="c5da4-689">**收**</span><span class="sxs-lookup"><span data-stu-id="c5da4-689">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="c5da4-690">新增代理人並設定來電-轉寄給代理人規則</span><span class="sxs-lookup"><span data-stu-id="c5da4-690">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="c5da4-691">這個範例會新增代理人，並設定 [來電轉接至代理人] 規則。</span><span class="sxs-lookup"><span data-stu-id="c5da4-691">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="c5da4-692">**收**</span><span class="sxs-lookup"><span data-stu-id="c5da4-692">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="c5da4-693">啟用同時震鈴及設定目的地號碼</span><span class="sxs-lookup"><span data-stu-id="c5da4-693">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="c5da4-694">這個範例可同時撥打並設定同時撥打的目的地號碼。</span><span class="sxs-lookup"><span data-stu-id="c5da4-694">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="c5da4-695">若要變更已啟用同時撥打之使用者的同時撥打的目的地號碼，請使用/enablesimulring 開關保留該命令，否則不會變更目的地號碼。</span><span class="sxs-lookup"><span data-stu-id="c5da4-695">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>

 <span data-ttu-id="c5da4-696">**收**</span><span class="sxs-lookup"><span data-stu-id="c5da4-696">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="c5da4-697">停用同時撥打</span><span class="sxs-lookup"><span data-stu-id="c5da4-697">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="c5da4-698">這個範例會停用 [同時撥打]。</span><span class="sxs-lookup"><span data-stu-id="c5da4-698">This example disables simultaneous ringing.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="c5da4-699">**收**</span><span class="sxs-lookup"><span data-stu-id="c5da4-699">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="c5da4-700">新增小組通話的小組成員，並設定同時撥打給小組通話成員群組</span><span class="sxs-lookup"><span data-stu-id="c5da4-700">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="c5da4-701">這個範例會將小組成員新增至使用者的小組通話群組，並允許同時撥打給小組通話群組。</span><span class="sxs-lookup"><span data-stu-id="c5da4-701">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="c5da4-702">將成員新增到使用者的小組通話群組會自動切換使用者的同時撥打 settigs，以 simulring 其小組通話群組。</span><span class="sxs-lookup"><span data-stu-id="c5da4-702">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>

 <span data-ttu-id="c5da4-703">**收**</span><span class="sxs-lookup"><span data-stu-id="c5da4-703">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="c5da4-704">移除團隊通話群組中的成員</span><span class="sxs-lookup"><span data-stu-id="c5da4-704">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="c5da4-705">這個範例會移除使用者小組通話群組的小組成員。</span><span class="sxs-lookup"><span data-stu-id="c5da4-705">This example removes a team member of the team-call group of a user.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="c5da4-706">如果要移除的成員是團隊通話群組的唯一成員，同時撥打給小組通話群組會自動停用。</span><span class="sxs-lookup"><span data-stu-id="c5da4-706">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>

 <span data-ttu-id="c5da4-707">**收**</span><span class="sxs-lookup"><span data-stu-id="c5da4-707">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="c5da4-708">將延遲的響鈴設定為小組通話群組</span><span class="sxs-lookup"><span data-stu-id="c5da4-708">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="c5da4-709">這個範例會將 [延遲] 響鈴變更為 [小組通話群組時間] 設定。</span><span class="sxs-lookup"><span data-stu-id="c5da4-709">This example changes the delayed ring to the team-call group time setting.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="c5da4-710">**收**</span><span class="sxs-lookup"><span data-stu-id="c5da4-710">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="c5da4-711">啟用小組通話</span><span class="sxs-lookup"><span data-stu-id="c5da4-711">Enable Team-Call</span></span>

<span data-ttu-id="c5da4-712">這個範例會為指定的使用者啟用團隊通話。</span><span class="sxs-lookup"><span data-stu-id="c5da4-712">This example enables team-call for a given user.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="c5da4-713">如果使用者的小組通話群組沒有成員，就不會啟用小組通話。</span><span class="sxs-lookup"><span data-stu-id="c5da4-713">If the team-call group of the user has no members, team-call won't be enabled.</span></span>

 <span data-ttu-id="c5da4-714">**收**</span><span class="sxs-lookup"><span data-stu-id="c5da4-714">**Output**</span></span>

#### <a name="disable-team-call"></a><span data-ttu-id="c5da4-715">停用小組通話</span><span class="sxs-lookup"><span data-stu-id="c5da4-715">Disable Team-Call</span></span>

<span data-ttu-id="c5da4-716">這個範例會為指定的使用者停用小組通話。</span><span class="sxs-lookup"><span data-stu-id="c5da4-716">This example disables team-call for a given user.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="c5da4-717">**收**</span><span class="sxs-lookup"><span data-stu-id="c5da4-717">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="c5da4-718">啟用 [群組呼叫挑選]，並將分揀群組指派給使用者</span><span class="sxs-lookup"><span data-stu-id="c5da4-718">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="c5da4-719">這個範例會將分揀群組指派給使用者，並啟用群組呼叫挑選。</span><span class="sxs-lookup"><span data-stu-id="c5da4-719">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="c5da4-720">**收**</span><span class="sxs-lookup"><span data-stu-id="c5da4-720">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="c5da4-721">停用群組呼叫挑選</span><span class="sxs-lookup"><span data-stu-id="c5da4-721">Disable Group Call Pickup</span></span>

<span data-ttu-id="c5da4-722">這個範例會為指定的使用者停用 [群組呼叫挑選]。</span><span class="sxs-lookup"><span data-stu-id="c5da4-722">This example disables Group Call Pickup for a given user.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="c5da4-723">當您停用使用者的 [群組呼叫分揀] 時，系統不會保留指派給使用者的群組號碼。</span><span class="sxs-lookup"><span data-stu-id="c5da4-723">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="c5da4-724">如果您隨後想要重新啟用該使用者的群組呼叫分揀，您必須使用/enablegrouppickup 開關再次指派群組號碼。</span><span class="sxs-lookup"><span data-stu-id="c5da4-724">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="c5da4-725">SYSPrep. ps1</span><span class="sxs-lookup"><span data-stu-id="c5da4-725">SYSPrep.ps1</span></span>
<span data-ttu-id="c5da4-726"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="c5da4-726"></span></span>

### <a name="description"></a><span data-ttu-id="c5da4-727">描述</span><span class="sxs-lookup"><span data-stu-id="c5da4-727">Description</span></span>

<span data-ttu-id="c5da4-728">SYSPrep. ps1 是 Windows PowerShell 腳本，可在您的 Windows Server 2008 作業系統電腦上安裝下列商務用 Skype Server 2015 先決條件。</span><span class="sxs-lookup"><span data-stu-id="c5da4-728">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>

- <span data-ttu-id="c5da4-729">Microsoft .Net Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="c5da4-729">Microsoft .Net Framework 4.5</span></span>

- <span data-ttu-id="c5da4-730">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="c5da4-730">Microsoft SQL Server Express</span></span>

- <span data-ttu-id="c5da4-731">Windows Powershell 版本3。0</span><span class="sxs-lookup"><span data-stu-id="c5da4-731">Windows Powershell version 3.0</span></span>

- <span data-ttu-id="c5da4-732">Visual c + + 2010 可轉散發元件</span><span class="sxs-lookup"><span data-stu-id="c5da4-732">Visual C++ 2010 Redistributable</span></span>

- <span data-ttu-id="c5da4-733">網際網路資訊伺服器更新</span><span class="sxs-lookup"><span data-stu-id="c5da4-733">Internet Information Server Updates</span></span>

- <span data-ttu-id="c5da4-734">Windows 身分識別基礎</span><span class="sxs-lookup"><span data-stu-id="c5da4-734">Windows Identity Foundation</span></span>

- <span data-ttu-id="c5da4-735">商務用 Skype Server 2015 核心轉儲檔</span><span class="sxs-lookup"><span data-stu-id="c5da4-735">Skype for Business Server 2015 Core files</span></span>

  <span data-ttu-id="c5da4-736">雖然腳本名稱與 Microsoft Windows 作業系統的系統準備工具類似，但它們是不同的。</span><span class="sxs-lookup"><span data-stu-id="c5da4-736">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="c5da4-737">此腳本只會安裝商務用 Skype Server 2015 所需的先決條件。</span><span class="sxs-lookup"><span data-stu-id="c5da4-737">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="c5da4-738">安裝這些必備元件之後，就可以使用 Windows SYSPrep 工具來建立伺服器的影像。</span><span class="sxs-lookup"><span data-stu-id="c5da4-738">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

### <a name="requirements"></a><span data-ttu-id="c5da4-739">需求</span><span class="sxs-lookup"><span data-stu-id="c5da4-739">Requirements</span></span>

<span data-ttu-id="c5da4-740">在執行 Sysprep.inf 腳本之前，您必須先將必備檔案複製到 Windows Server 2008 作業系統電腦上的本機資料夾（例如**D:\Setup）**。</span><span class="sxs-lookup"><span data-stu-id="c5da4-740">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="c5da4-741">此資料夾也必須包含商務用 Skype Server 2015 檔案（特別是 setup.exe）的複本 **。**</span><span class="sxs-lookup"><span data-stu-id="c5da4-741">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="c5da4-742">您可以從下列位置下載必備檔：</span><span class="sxs-lookup"><span data-stu-id="c5da4-742">The prerequisite files can be downloaded from the following locations:</span></span>


| <span data-ttu-id="c5da4-743">**必備**</span><span class="sxs-lookup"><span data-stu-id="c5da4-743">**Prerequisite**</span></span>                                | <span data-ttu-id="c5da4-744">**位置**</span><span class="sxs-lookup"><span data-stu-id="c5da4-744">**Location**</span></span>                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| <span data-ttu-id="c5da4-745">Microsoft .Net Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="c5da4-745">Microsoft .Net Framework 4.5</span></span>  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| <span data-ttu-id="c5da4-746">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="c5da4-746">Microsoft SQL Server Express 2008 R2</span></span>  <br/>     | <https://www.microsoft.com/en-us/download/details.aspx?id=23650>  <br/> |
| <span data-ttu-id="c5da4-747">Windows Powershell 版本3。0</span><span class="sxs-lookup"><span data-stu-id="c5da4-747">Windows Powershell version 3.0</span></span>  <br/>           | <https://www.microsoft.com/en-us/download/details.aspx?id=34595>  <br/> |
| <span data-ttu-id="c5da4-748">Visual c + + 2010 可轉散發元件</span><span class="sxs-lookup"><span data-stu-id="c5da4-748">Visual C++ 2010 Redistributable</span></span>  <br/>          | <https://www.microsoft.com/en-us/download/details.aspx?id=5555>  <br/>  |
| <span data-ttu-id="c5da4-749">網際網路資訊伺服器更新</span><span class="sxs-lookup"><span data-stu-id="c5da4-749">Internet Information Server Updates</span></span>  <br/>      | <https://www.microsoft.com/en-us/download/details.aspx?id=34869>  <br/> |
| <span data-ttu-id="c5da4-750">Windows 身分識別基礎</span><span class="sxs-lookup"><span data-stu-id="c5da4-750">Windows Identity Foundation</span></span>  <br/>              | <https://www.microsoft.com/en-us/download/details.aspx?id=17331>  <br/> |
| <span data-ttu-id="c5da4-751">商務用 Skype Server 2015 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="c5da4-751">Skype for Business Server 2015 Setup.exe</span></span>  <br/> | <span data-ttu-id="c5da4-752">從商務用 Skype Server 2015 媒體複製</span><span class="sxs-lookup"><span data-stu-id="c5da4-752">Copy from Skype for Business Server 2015 media</span></span>  <br/>                   |

### <a name="parameter"></a><span data-ttu-id="c5da4-753">參數</span><span class="sxs-lookup"><span data-stu-id="c5da4-753">Parameter</span></span>

<span data-ttu-id="c5da4-754">**-SetupFolder**參數會將必備檔案的目錄位置做為引數。</span><span class="sxs-lookup"><span data-stu-id="c5da4-754">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

### <a name="examples"></a><span data-ttu-id="c5da4-755">範例</span><span class="sxs-lookup"><span data-stu-id="c5da4-755">Examples</span></span>

<span data-ttu-id="c5da4-756">若要執行 SYSPrep. ps1 腳本並安裝商務用 Skype Server 2015 的先決條件，請從提升許可權的命令提示字元執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c5da4-756">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="c5da4-757">未指定的數位宣告遷移</span><span class="sxs-lookup"><span data-stu-id="c5da4-757">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="c5da4-758"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="c5da4-758"></span></span>

<span data-ttu-id="c5da4-759">[未指派的號碼宣告] 遷移工具可讓商務用 Skype Server 2015 系統管理員將宣告應用程式所提供的 [未指派的號碼] 設定從來源 Skype 伺服器或池中移至[目的地商務用 Skype 伺服器] 或 [池]。</span><span class="sxs-lookup"><span data-stu-id="c5da4-759">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>

### <a name="description"></a><span data-ttu-id="c5da4-760">描述</span><span class="sxs-lookup"><span data-stu-id="c5da4-760">Description</span></span>

<span data-ttu-id="c5da4-761">[取消指派的號碼宣告] 遷移工具是一個 Windows PowerShell 腳本，可將來源伺服器或池的宣告應用程式所提供的未指定編號設定移至不同的伺服器或池中。</span><span class="sxs-lookup"><span data-stu-id="c5da4-761">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="c5da4-762">執行時，[未指定的數位宣告] 遷移腳本會執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="c5da4-762">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1. <span data-ttu-id="c5da4-763">將來源伺服器或池中託管之宣告應用程式的 [未指派的號碼] 宣告所使用的所有音訊檔案，移至目的地伺服器或池中的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="c5da4-763">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c5da4-764">當音訊檔案複製到目的地池之後，就會從來源池中移除。</span><span class="sxs-lookup"><span data-stu-id="c5da4-764">The audio files are removed from the source pool once they're copied to the destination pool.</span></span>

2. <span data-ttu-id="c5da4-765">將針對來源伺服器或池中託管之宣告應用程式設定的所有未指派數位宣告移至目的伺服器或池。</span><span class="sxs-lookup"><span data-stu-id="c5da4-765">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3. <span data-ttu-id="c5da4-766">將來源伺服器或池中託管的宣告應用程式所服務的所有未指派數位範圍重新指派至目的地伺服器或池中。</span><span class="sxs-lookup"><span data-stu-id="c5da4-766">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="c5da4-767">在成功執行腳本之後，由來源伺服器或池中託管之宣告應用程式所提供服務的所有未指派數位範圍，都將由目的地伺服器或池使用相同的設定來提供服務。</span><span class="sxs-lookup"><span data-stu-id="c5da4-767">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

### <a name="output"></a><span data-ttu-id="c5da4-768">收</span><span class="sxs-lookup"><span data-stu-id="c5da4-768">Output</span></span>

<span data-ttu-id="c5da4-769">**CsAnnouncementConfiguration**腳本會在商務用 Skype Server Management 命令介面視窗中指出，其已執行遷移作業的成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="c5da4-769">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="c5da4-770">如果由於任何錯誤而中斷執行作業，則已順利移至目的地的未指派數位範圍將會保留在作業中，並將遷移的未指派數位範圍保留在來源以及工作表單中。</span><span class="sxs-lookup"><span data-stu-id="c5da4-770">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="c5da4-771">若要完全遷移其餘的設定，請在解決錯誤之後，重新執行腳本。</span><span class="sxs-lookup"><span data-stu-id="c5da4-771">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

### <a name="purpose"></a><span data-ttu-id="c5da4-772">特殊</span><span class="sxs-lookup"><span data-stu-id="c5da4-772">Purpose</span></span>

<span data-ttu-id="c5da4-773">[未指定的數位宣告] 遷移腳本可以在下列三種案例中使用：</span><span class="sxs-lookup"><span data-stu-id="c5da4-773">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

- <span data-ttu-id="c5da4-774">**將配置設定遷移至新版本的商務用 Skype Server：** Contoso 正在遷移到商務用 Skype Server 2015，並做為遷移程式的一部分，商務用 Skype 伺服器管理員想要將宣告應用程式所提供的未指派號碼設定從 Lync Server 2013 部署移至新的商務用 Skype Server 2015 部署。</span><span class="sxs-lookup"><span data-stu-id="c5da4-774">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="c5da4-775">若要移動設定，商務用 Skype 伺服器管理員會使用 [未指派的號碼宣告] 遷移工具。</span><span class="sxs-lookup"><span data-stu-id="c5da4-775">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

- <span data-ttu-id="c5da4-776">**從商務用 Skype server 2015 回退部署到 Lync Server 2013：** 由於預期的意外因素，Contoso 必須將遷移回退至新的商務用 Skype Server 2015 部署。</span><span class="sxs-lookup"><span data-stu-id="c5da4-776">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="c5da4-777">若要儘量減少中斷服務的中斷，商務用 Skype Server 管理員會使用 [未指派的號碼宣告] 遷移工具，將設定從商務用 Skype Server 2015 部署回滾到 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="c5da4-777">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>

- <span data-ttu-id="c5da4-778">**在部署之間移動資料：** Contoso 正處於使用較新的伺服器取代一個池的所有伺服器的程式中。</span><span class="sxs-lookup"><span data-stu-id="c5da4-778">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="c5da4-779">其戰略是部署新的商務用 Skype Server 2015 池、將舊的資料移至新的池中，然後取代舊的資源池。</span><span class="sxs-lookup"><span data-stu-id="c5da4-779">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="c5da4-780">部署新的資料庫池之後，就會使用 [取消指派的號碼宣告遷移工具]，將配置從舊的池中移至新的池中。</span><span class="sxs-lookup"><span data-stu-id="c5da4-780">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

#### <a name="requirements"></a><span data-ttu-id="c5da4-781">需求</span><span class="sxs-lookup"><span data-stu-id="c5da4-781">Requirements</span></span>

<span data-ttu-id="c5da4-782">以下是成功執行此工具所需的主要需求：</span><span class="sxs-lookup"><span data-stu-id="c5da4-782">The following are the main requirements needed to successfully run the tool:</span></span>

1. <span data-ttu-id="c5da4-783">此腳本必須從已安裝商務用 Skype Server Management Shell 的電腦執行。</span><span class="sxs-lookup"><span data-stu-id="c5da4-783">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>

2. <span data-ttu-id="c5da4-784">必須在 [來源] 和 [目的地商務用 Skype 伺服器] 或 [池] 中成功部署宣告應用程式。</span><span class="sxs-lookup"><span data-stu-id="c5da4-784">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>

#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="c5da4-785">移動流覽 CsAnnouncementConfiguration 腳本</span><span class="sxs-lookup"><span data-stu-id="c5da4-785">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="c5da4-786">CsAnnouncementConfiguration 腳本需要下表所述的兩個參數。</span><span class="sxs-lookup"><span data-stu-id="c5da4-786">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

![Move-CsAnnouncementConfiguration 參數。](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a><span data-ttu-id="c5da4-788">範例</span><span class="sxs-lookup"><span data-stu-id="c5da4-788">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="c5da4-789">將 [未指定的數位宣告] 配置從 Lync Server 2013 文件庫移至商務用 Skype Server 2015 池</span><span class="sxs-lookup"><span data-stu-id="c5da4-789">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="c5da4-790">這個範例會將來源池（Lync Server 2013）的 [未指定的數位宣告]，移至目的地池（商務用 Skype Server 2015）。</span><span class="sxs-lookup"><span data-stu-id="c5da4-790">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>

```PowerShell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="c5da4-791">從商務用 Skype Server 2015 池中將 [未指定的數位宣告] 配置移至 Lync Server 2013 池</span><span class="sxs-lookup"><span data-stu-id="c5da4-791">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="c5da4-792">這個範例會將來源池（商務用 Skype Server 2015）的 [未指定的數目宣告]，移至目的地池（Lync Server 2013）。</span><span class="sxs-lookup"><span data-stu-id="c5da4-792">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>

```PowerShell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="c5da4-793">網路會議資料</span><span class="sxs-lookup"><span data-stu-id="c5da4-793">Web Conf Data</span></span>
<span data-ttu-id="c5da4-794"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="c5da4-794"></span></span>

<span data-ttu-id="c5da4-795">網路會議資料工具可讓商務用 Skype Server 2015 通訊軟體的系統管理員對與召集人的網路會議相關的資料進行更多的控制。</span><span class="sxs-lookup"><span data-stu-id="c5da4-795">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="c5da4-796">案例包括根據時間戳記準則刪除特定使用者的會議資料的功能。</span><span class="sxs-lookup"><span data-stu-id="c5da4-796">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>

### <a name="description"></a><span data-ttu-id="c5da4-797">描述</span><span class="sxs-lookup"><span data-stu-id="c5da4-797">Description</span></span>

<span data-ttu-id="c5da4-798">這個工具可讓系統管理員執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="c5da4-798">This tool allows the administrator to perform the following operations:</span></span>

1. <span data-ttu-id="c5da4-799">尋找與單一使用者相關聯的所有 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="c5da4-799">Find all Web conferencing data associated with a single user.</span></span>

2. <span data-ttu-id="c5da4-800">刪除所有與單一使用者相關聯的 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="c5da4-800">Delete all Web conferencing data associated with a single user.</span></span>

3. <span data-ttu-id="c5da4-801">刪除所有與特定日期舊的單一使用者相關聯的所有 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="c5da4-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4. <span data-ttu-id="c5da4-802">當使用者從一個池移到另一個時，移動與單一使用者相關聯的所有 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="c5da4-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

> [!NOTE]
> <span data-ttu-id="c5da4-803">在 Lync Server 2010 的資源工具組工具中，當使用者從一個中心移到另一個時，就能移動與單一使用者相關聯的所有 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="c5da4-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="c5da4-804">此功能現在已從這個工具中棄用，取而代之的是**MoveConferenceData**參數。</span><span class="sxs-lookup"><span data-stu-id="c5da4-804">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="c5da4-805">如需此參數的詳細資訊，請參閱[move-csuser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c5da4-805">For details about this parameter, see the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="c5da4-806">此工具只會刪除處於非作用中的會議的會議資料。</span><span class="sxs-lookup"><span data-stu-id="c5da4-806">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="c5da4-807">無法刪除使用中的會議（或會話中的會議）。</span><span class="sxs-lookup"><span data-stu-id="c5da4-807">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="c5da4-808">此工具必須從與目標使用者相同的同一個池中的電腦執行。</span><span class="sxs-lookup"><span data-stu-id="c5da4-808">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="c5da4-809">其會議內容資料由此工具管理的使用者必須駐留在相同的使用者池中。</span><span class="sxs-lookup"><span data-stu-id="c5da4-809">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

### <a name="output"></a><span data-ttu-id="c5da4-810">收</span><span class="sxs-lookup"><span data-stu-id="c5da4-810">Output</span></span>

<span data-ttu-id="c5da4-811">這個工具會輸出每個作業的結果：</span><span class="sxs-lookup"><span data-stu-id="c5da4-811">This tool outputs the results of each of the operations:</span></span>

- <span data-ttu-id="c5da4-812">如果執行查詢，該工具會將使用者作為召集人的所有非作用中會議資料資料夾清單輸出。</span><span class="sxs-lookup"><span data-stu-id="c5da4-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

- <span data-ttu-id="c5da4-813">如果執行刪除，工具會將刪除其資料的所有會議資料資料夾清單輸出。</span><span class="sxs-lookup"><span data-stu-id="c5da4-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

### <a name="requirements"></a><span data-ttu-id="c5da4-814">需求</span><span class="sxs-lookup"><span data-stu-id="c5da4-814">Requirements</span></span>

<span data-ttu-id="c5da4-815">此工具必須在召集人目前所駐留的同一個池中執行。</span><span class="sxs-lookup"><span data-stu-id="c5da4-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="c5da4-816">您必須使用具有內容檔案存放區存取權的系統管理員許可權來執行該工具。</span><span class="sxs-lookup"><span data-stu-id="c5da4-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

### <a name="examples"></a><span data-ttu-id="c5da4-817">範例</span><span class="sxs-lookup"><span data-stu-id="c5da4-817">Examples</span></span>

<span data-ttu-id="c5da4-818">下表說明一些在範例中使用的參數。</span><span class="sxs-lookup"><span data-stu-id="c5da4-818">The following table describes the parameters, some of which are used in the examples.</span></span>

![Web Conf Data 工具參數。](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="c5da4-820">前面的範例顯示查詢命令的運作方式。</span><span class="sxs-lookup"><span data-stu-id="c5da4-820">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="c5da4-821">這類命令的輸出會是受此工具影響之所有會議內容資料夾的清單。</span><span class="sxs-lookup"><span data-stu-id="c5da4-821">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

```
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="c5da4-822">上述是 [刪除] 命令的範例。</span><span class="sxs-lookup"><span data-stu-id="c5da4-822">The preceding is an example of a delete command.</span></span> <span data-ttu-id="c5da4-823">[刪除] 命令會從該使用者移除所有非作用中會議資料夾。</span><span class="sxs-lookup"><span data-stu-id="c5da4-823">The delete command will remove all inactive meeting folders from this user.</span></span>

### <a name="summary"></a><span data-ttu-id="c5da4-824">總結</span><span class="sxs-lookup"><span data-stu-id="c5da4-824">Summary</span></span>

<span data-ttu-id="c5da4-825">此工具對於需要更精確控制會議會議資料的管理員而言，是一種重要的資源。</span><span class="sxs-lookup"><span data-stu-id="c5da4-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>



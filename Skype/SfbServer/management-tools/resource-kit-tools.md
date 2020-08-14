---
title: 商務用 Skype Server 2015 資源工具組工具檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: 本主題說明商務用 Skype Server 2015 資源套件中的工具，包含每個工具的用途，以及其用途的範例。 商務用 Skype Server 2015 資源套件可協助 IT 系統管理員部署及管理商務用 Skype Server 2015，使日常工作變得更容易。 例如，網路會議資料工具可以用來輕鬆控制使用者在線上會議期間上傳的資料。 SEFAUtil 工具可以用來設定使用者的代理人來電轉接和應答。 我們鼓勵 IT 管理員使用這些工具，更有效地管理商務用 Skype Server 2015。
ms.openlocfilehash: 7269d7c82736be8e533a0782548a94d14aafcfb5
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2020
ms.locfileid: "42160767"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="02730-107">商務用 Skype Server 2015 資源工具組工具檔</span><span class="sxs-lookup"><span data-stu-id="02730-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>

<span data-ttu-id="02730-108">本主題說明商務用 Skype Server 2015 資源套件中的工具，包含每個工具的用途，以及其用途的範例。</span><span class="sxs-lookup"><span data-stu-id="02730-108">This topic describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="02730-109">商務用 Skype Server 2015 資源套件可協助 IT 系統管理員部署及管理商務用 Skype Server 2015，使日常工作變得更容易。</span><span class="sxs-lookup"><span data-stu-id="02730-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="02730-110">例如，網路會議 **資料** 工具可以用來輕鬆控制使用者在線上會議期間上傳的資料。</span><span class="sxs-lookup"><span data-stu-id="02730-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="02730-111">**SEFAUtil**工具可以用來設定使用者的代理人來電轉接和應答。</span><span class="sxs-lookup"><span data-stu-id="02730-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="02730-112">我們鼓勵 IT 管理員使用這些工具，更有效地管理商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="02730-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="02730-113">安裝資源工具組工具</span><span class="sxs-lookup"><span data-stu-id="02730-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="02730-114">若要安裝商務用 Skype Server 2015 資源套件，請從下載中心下載 [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) 。</span><span class="sxs-lookup"><span data-stu-id="02730-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) from the Download Center.</span></span>

<span data-ttu-id="02730-115">執行 **OCSResKit.msi** 以執行簡單安裝。</span><span class="sxs-lookup"><span data-stu-id="02730-115">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="02730-116">.Msi 會安裝下列路徑中的所有工具： **% Program Files%\Skype For Business Server 2015 \ ResKit**。</span><span class="sxs-lookup"><span data-stu-id="02730-116">The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**.</span></span> <span data-ttu-id="02730-117">屬於自包含可執行檔的工具位於此資料夾中。</span><span class="sxs-lookup"><span data-stu-id="02730-117">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="02730-118">也有支援檔案的工具位於自己的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="02730-118">Tools that also have supporting files are in their own subfolders.</span></span>

## <a name="supported-environments"></a><span data-ttu-id="02730-119">支援的環境</span><span class="sxs-lookup"><span data-stu-id="02730-119">Supported Environments</span></span>

<span data-ttu-id="02730-120">商務用 Skype Server 2015 資源套件應該安裝在符合商務用 Skype Server 2015 （通常是用來執行商務用 Skype Server 2015）所需規格的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="02730-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="02730-121">資源工具組工具概述</span><span class="sxs-lookup"><span data-stu-id="02730-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="02730-122">以下是商務用 Skype Server 2015 資源套件中所提供的工具清單。</span><span class="sxs-lookup"><span data-stu-id="02730-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="02730-123">下列各節涵蓋每個工具的描述（包括需求和範例用法）。</span><span class="sxs-lookup"><span data-stu-id="02730-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>

- [<span data-ttu-id="02730-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="02730-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)

- [<span data-ttu-id="02730-125">頻寬原則服務監視器</span><span class="sxs-lookup"><span data-stu-id="02730-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)

- [<span data-ttu-id="02730-126">頻寬流量分析程式</span><span class="sxs-lookup"><span data-stu-id="02730-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)

- [<span data-ttu-id="02730-127">呼叫 Call parkometer</span><span class="sxs-lookup"><span data-stu-id="02730-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)

- [<span data-ttu-id="02730-128">Dbanalyze.exe</span><span class="sxs-lookup"><span data-stu-id="02730-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)

- [<span data-ttu-id="02730-129">匯入儲存體服務資料</span><span class="sxs-lookup"><span data-stu-id="02730-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)

- [<span data-ttu-id="02730-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="02730-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)

- [<span data-ttu-id="02730-131">查閱使用者主控台</span><span class="sxs-lookup"><span data-stu-id="02730-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)

- [<span data-ttu-id="02730-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="02730-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)

- [<span data-ttu-id="02730-133">網路設定檢視器</span><span class="sxs-lookup"><span data-stu-id="02730-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)

- [<span data-ttu-id="02730-134">回應群組代理程式 Live</span><span class="sxs-lookup"><span data-stu-id="02730-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)

- [<span data-ttu-id="02730-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="02730-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)

- [<span data-ttu-id="02730-136">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="02730-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)

- [<span data-ttu-id="02730-137">未指派號碼宣告遷移</span><span class="sxs-lookup"><span data-stu-id="02730-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)

- [<span data-ttu-id="02730-138">網路會議資料</span><span class="sxs-lookup"><span data-stu-id="02730-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a><span data-ttu-id="02730-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="02730-139">ABSConfig</span></span>
<span data-ttu-id="02730-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="02730-140"><a name="ABSConfig"> </a></span></span>

<span data-ttu-id="02730-141">通訊錄服務設定工具 (ABSConfig) 是一種系統管理工具，可協助系統管理員在商務用 Skype Server 2015 中自訂通訊錄服務設定。</span><span class="sxs-lookup"><span data-stu-id="02730-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="02730-142">此工具也可讓商務用 Skype Server 2015 系統管理員還原預設通訊錄服務設定。</span><span class="sxs-lookup"><span data-stu-id="02730-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>

### <a name="description"></a><span data-ttu-id="02730-143">描述</span><span class="sxs-lookup"><span data-stu-id="02730-143">Description</span></span>

<span data-ttu-id="02730-144">ABSConfig 是一種圖形使用者介面應用程式，可讓系統管理員設定與通訊錄服務相關的 Active Directory 網域服務屬性。</span><span class="sxs-lookup"><span data-stu-id="02730-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="02730-145">工具的主要案例如下：</span><span class="sxs-lookup"><span data-stu-id="02730-145">The primary scenarios for the tool are the following:</span></span>

- <span data-ttu-id="02730-146">讓系統管理員能夠將 Active Directory 網域服務中的屬性對應至商務用 Skype Server 2015 的屬性。</span><span class="sxs-lookup"><span data-stu-id="02730-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>

- <span data-ttu-id="02730-147">讓系統管理員指定要在通訊錄服務檔案中包含或排除的 Active Directory 網域服務屬性。</span><span class="sxs-lookup"><span data-stu-id="02730-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

- <span data-ttu-id="02730-148">讓系統管理員能夠還原預設的通訊錄服務設定。</span><span class="sxs-lookup"><span data-stu-id="02730-148">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="02730-149">您可以使用 ABSConfig.exe 檔啟動 ABSConfig 工具。</span><span class="sxs-lookup"><span data-stu-id="02730-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="02730-150">工具隨即開啟至 [ **設定屬性** ] 索引標籤。此表格中的選項可將 Active Directory 網域服務屬性對應至商務用 Skype Server 2015 的屬性欄位，以及指定哪些使用者要在通訊錄服務檔案中包含或排除，以特定的屬性篩選器為基礎。</span><span class="sxs-lookup"><span data-stu-id="02730-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="02730-151">也可以選擇自訂要包含在通訊錄檔案中的電話號碼值。</span><span class="sxs-lookup"><span data-stu-id="02730-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="02730-152">[ **還原預設** 值] 選項可讓系統管理員將通訊錄服務設定還原為預設值。</span><span class="sxs-lookup"><span data-stu-id="02730-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

> [!NOTE]
> <span data-ttu-id="02730-153">將 AD 屬性重新對應至不同的 OC 功能變數名稱只會在通訊錄檔案下載時運作，且不受通訊錄 Web 查詢的支援。</span><span class="sxs-lookup"><span data-stu-id="02730-153">Re-mapping of AD attributes to different OC Field Names will only work for Address Book File Download, and is not supported by Address Book Web Query.</span></span>

### <a name="output"></a><span data-ttu-id="02730-154">輸出</span><span class="sxs-lookup"><span data-stu-id="02730-154">Output</span></span>

<span data-ttu-id="02730-155">ABSConfig 會將通訊錄服務設定儲存在資料庫中。</span><span class="sxs-lookup"><span data-stu-id="02730-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="02730-156">用途</span><span class="sxs-lookup"><span data-stu-id="02730-156">Purpose</span></span>

<span data-ttu-id="02730-157">ABSConfig 提供一種快速快捷的方式，可自訂商務用 Skype Server 2015 Address Book 服務。</span><span class="sxs-lookup"><span data-stu-id="02730-157">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>

### <a name="requirements"></a><span data-ttu-id="02730-158">需求</span><span class="sxs-lookup"><span data-stu-id="02730-158">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="02730-159">電腦</span><span class="sxs-lookup"><span data-stu-id="02730-159">Computer</span></span>

<span data-ttu-id="02730-160">ABSConfig 只能在已安裝商務用 Skype Server 2015 的已加入網域的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="02730-160">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="02730-161">在商務用 Skype Server 2015，Enterprise Edition 的情況下，此工具可以在安裝期間啟用通訊錄服務的所有前端伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="02730-161">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

#### <a name="network"></a><span data-ttu-id="02730-162">網路</span><span class="sxs-lookup"><span data-stu-id="02730-162">Network</span></span>

<span data-ttu-id="02730-163">電腦應該能夠連線至前端集區和後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="02730-163">The computer should be able to connect to the Front End pool and back-end database.</span></span>

#### <a name="software"></a><span data-ttu-id="02730-164">軟體</span><span class="sxs-lookup"><span data-stu-id="02730-164">Software</span></span>

<span data-ttu-id="02730-165">在執行 ABSConfig 工具之前，必須先安裝下列軟體元件：</span><span class="sxs-lookup"><span data-stu-id="02730-165">The following software components must be installed before running the ABSConfig tool:</span></span>

- <span data-ttu-id="02730-166">商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="02730-166">Skype for Business Server 2015</span></span>

#### <a name="users"></a><span data-ttu-id="02730-167">使用者</span><span class="sxs-lookup"><span data-stu-id="02730-167">Users</span></span>

<span data-ttu-id="02730-168">具備更新商務用 Skype Server 2015 部署所需許可權的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="02730-168">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>

### <a name="examples"></a><span data-ttu-id="02730-169">範例</span><span class="sxs-lookup"><span data-stu-id="02730-169">Examples</span></span>

<span data-ttu-id="02730-170">您可以在命令提示字元處輸入 **ABSConfig.exe** ，以啟動 ABSConfig。</span><span class="sxs-lookup"><span data-stu-id="02730-170">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="02730-171">如下所示為 ABSConfig 工具使用者介面。</span><span class="sxs-lookup"><span data-stu-id="02730-171">Shown below is the ABSConfig tool user interface.</span></span>

![ABSConfig.exe 工具。](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a><span data-ttu-id="02730-173">摘要</span><span class="sxs-lookup"><span data-stu-id="02730-173">Summary</span></span>

<span data-ttu-id="02730-174">ABSConfig 工具為系統管理員提供快速易用的工具，以自訂商務用 Skype Server 2015 通訊錄服務。</span><span class="sxs-lookup"><span data-stu-id="02730-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="02730-175">頻寬原則服務監視器</span><span class="sxs-lookup"><span data-stu-id="02730-175">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="02730-176"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="02730-176"><a name="bpsm"> </a></span></span>

<span data-ttu-id="02730-177">「頻寬原則服務監視」工具的目的是讓系統管理員可以查看下列專案的清單：</span><span class="sxs-lookup"><span data-stu-id="02730-177">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1. <span data-ttu-id="02730-178">拓撲中所有已設定的商務用 Skype Server 2015 頻寬原則服務 (驗證及核心) </span><span class="sxs-lookup"><span data-stu-id="02730-178">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2. <span data-ttu-id="02730-179">每個服務對其他頻寬原則服務和 Edge server 所進行的連接</span><span class="sxs-lookup"><span data-stu-id="02730-179">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3. <span data-ttu-id="02730-180">網路設定檔中所設定的所有連結，以及每個頻寬原則服務所報告的即時頻寬使用量</span><span class="sxs-lookup"><span data-stu-id="02730-180">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

### <a name="description"></a><span data-ttu-id="02730-181">描述</span><span class="sxs-lookup"><span data-stu-id="02730-181">Description</span></span>

<span data-ttu-id="02730-182">頻寬原則服務監視工具是以 GUI 型應用程式的形式來執行。</span><span class="sxs-lookup"><span data-stu-id="02730-182">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="02730-183">管理員會透過執行 PDPMonUI.exe 來啟動工具。</span><span class="sxs-lookup"><span data-stu-id="02730-183">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="02730-184">當工具開始時，它會嘗試探索拓撲中的頻寬原則服務清單。</span><span class="sxs-lookup"><span data-stu-id="02730-184">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="02730-185">完成初始更新後，視窗左側的窗格會以所隸屬的群組為群組的服務清單填入。</span><span class="sxs-lookup"><span data-stu-id="02730-185">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="02730-186">當管理員選擇特定頻寬原則服務時，右側窗格會顯示該特定服務的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="02730-186">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="02730-187">該窗格也有兩個主要索引標籤可顯示資訊。</span><span class="sxs-lookup"><span data-stu-id="02730-187">That pane also has two main tabs that display information.</span></span>

#### <a name="machine-info-tab"></a><span data-ttu-id="02730-188">電腦資訊] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="02730-188">Machine Info Tab</span></span>

<span data-ttu-id="02730-189">[ **機器資訊** ] 索引標籤會顯示所選頻寬原則服務的詳細資料，以及選取的頻寬原則服務對其他服務所做的所有連線清單和狀態。</span><span class="sxs-lookup"><span data-stu-id="02730-189">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

#### <a name="topology-info-tab"></a><span data-ttu-id="02730-190">拓撲資訊] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="02730-190">Topology Info Tab</span></span>

<span data-ttu-id="02730-191">**拓撲資訊**索引標籤顯示網路設定中所設定之所有連結的清單。</span><span class="sxs-lookup"><span data-stu-id="02730-191">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="02730-192">針對每個連結，會顯示音訊和影片頻寬容量。</span><span class="sxs-lookup"><span data-stu-id="02730-192">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="02730-193">此外，目前使用的頻寬會顯示，以 Kbps 為單位的容量百分比顯示。</span><span class="sxs-lookup"><span data-stu-id="02730-193">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="02730-194">工具使用色彩編碼，強調具有接近容量之使用率的連結，這可讓系統管理員快速隔離這類連結。</span><span class="sxs-lookup"><span data-stu-id="02730-194">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

> [!NOTE]
>  <span data-ttu-id="02730-195">如果頻寬原則服務監視工具在連線至任何設定的頻寬原則服務時失敗，將不會填入 **機器資訊** 和 **拓撲資訊** 索引標籤中的資訊。</span><span class="sxs-lookup"><span data-stu-id="02730-195">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="02730-196">不過，此工具最初可能會連線，但後來會失去與服務的連線。</span><span class="sxs-lookup"><span data-stu-id="02730-196">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="02730-197">在這種情況下，系統管理員可能會看到過時的資訊。</span><span class="sxs-lookup"><span data-stu-id="02730-197">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="02730-198">每個索引標籤上都有最後一次 **更新** 的時間戳記，可讓系統管理員看到上次更新特定頻寬原則服務的資料的時間。</span><span class="sxs-lookup"><span data-stu-id="02730-198">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>

### <a name="output"></a><span data-ttu-id="02730-199">輸出</span><span class="sxs-lookup"><span data-stu-id="02730-199">Output</span></span>

<span data-ttu-id="02730-200">無命令列輸出;程式輸出包含在主要圖形使用者介面 (GUI) 中。</span><span class="sxs-lookup"><span data-stu-id="02730-200">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

### <a name="purpose"></a><span data-ttu-id="02730-201">用途</span><span class="sxs-lookup"><span data-stu-id="02730-201">Purpose</span></span>

<span data-ttu-id="02730-202">「頻寬原則服務監視」工具的目的是讓系統管理員能看到拓撲中所定義的每個頻寬原則服務的狀態。</span><span class="sxs-lookup"><span data-stu-id="02730-202">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="02730-203">此外，系統管理員可以查看網路設定檔中所定義之所有連結的即時頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="02730-203">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

### <a name="requirements"></a><span data-ttu-id="02730-204">需求</span><span class="sxs-lookup"><span data-stu-id="02730-204">Requirements</span></span>

<span data-ttu-id="02730-205">在屬於商務用 Skype 伺服器拓撲的電腦上，必須執行頻寬原則服務監視器工具。</span><span class="sxs-lookup"><span data-stu-id="02730-205">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>

### <a name="summary"></a><span data-ttu-id="02730-206">摘要</span><span class="sxs-lookup"><span data-stu-id="02730-206">Summary</span></span>

<span data-ttu-id="02730-207">頻寬原則服務監視器工具對管理員來說可能是一項寶貴資源，讓他們能夠檢查拓撲中所有頻寬原則服務的狀態，更重要的是，他們可以取得網路設定設定中所定義之連結的即時頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="02730-207">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="02730-208">頻寬流量分析程式</span><span class="sxs-lookup"><span data-stu-id="02730-208">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="02730-209"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="02730-209"><a name="bua"> </a></span></span>

<span data-ttu-id="02730-210">頻寬流量分析程式是一種工具，它會針對商業網路中 WAN 連結的 UC 端點，建立各種頻寬使用量的報告。</span><span class="sxs-lookup"><span data-stu-id="02730-210">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="02730-211">這些報告可用於瞭解目前的頻寬消耗模式，以及協助進行頻寬容量規劃。</span><span class="sxs-lookup"><span data-stu-id="02730-211">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

### <a name="description"></a><span data-ttu-id="02730-212">描述</span><span class="sxs-lookup"><span data-stu-id="02730-212">Description</span></span>

<span data-ttu-id="02730-213">頻寬使用量分析器是以 GUI 型應用程式的形式來執行。</span><span class="sxs-lookup"><span data-stu-id="02730-213">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="02730-214">這個工具專為網路上的音訊使用量產生報告，並協助進行容量規劃。</span><span class="sxs-lookup"><span data-stu-id="02730-214">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="02730-215">它也會在指派給各種連結的頻寬容量上進行迴圈。</span><span class="sxs-lookup"><span data-stu-id="02730-215">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

### <a name="output"></a><span data-ttu-id="02730-216">輸出</span><span class="sxs-lookup"><span data-stu-id="02730-216">Output</span></span>

<span data-ttu-id="02730-217">頻寬流量分析程式可為系統中所設定的所有 WAN 連結，提供圖形 al 的頻寬容量及音訊使用方式。</span><span class="sxs-lookup"><span data-stu-id="02730-217">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

### <a name="purpose"></a><span data-ttu-id="02730-218">用途</span><span class="sxs-lookup"><span data-stu-id="02730-218">Purpose</span></span>

<span data-ttu-id="02730-219">在任何語音和影片部署中，監控和瞭解整個商業網路中媒體流量的頻寬利用率，都很重要。</span><span class="sxs-lookup"><span data-stu-id="02730-219">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="02730-220">頻寬使用狀況分析工具可讓系統管理員只取得這種方式。</span><span class="sxs-lookup"><span data-stu-id="02730-220">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="02730-221">此工具會執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="02730-221">This tool does the following:</span></span>

- <span data-ttu-id="02730-222">針對整個網路產生音訊使用量的特定報告</span><span class="sxs-lookup"><span data-stu-id="02730-222">Generates specific reports for audio utilization across the network</span></span>

- <span data-ttu-id="02730-223">協助在指派給各種連結的頻寬容量上進行更有效的容量規劃和反覆運算</span><span class="sxs-lookup"><span data-stu-id="02730-223">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="02730-224">頻寬流量分析程式可以產生頻寬容量和使用方式報告的圖形圖形它們如下：</span><span class="sxs-lookup"><span data-stu-id="02730-224">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

- <span data-ttu-id="02730-225">商業網路中的所有 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="02730-225">All the WAN links in the enterprise network</span></span>

- <span data-ttu-id="02730-226">依選取的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="02730-226">Filtered by selected WAN links that have been chosen</span></span>

- <span data-ttu-id="02730-227">由超過連結容量的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="02730-227">Filtered by WAN links that have exceeded link capacity</span></span>

- <span data-ttu-id="02730-228">使用已在使用中布建的頻寬來篩選的 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="02730-228">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

- <span data-ttu-id="02730-229">依 WAN 連結的頻寬使用量超過90% 的頻寬使用量，篩選已達到關鍵性層級的 WAN 連結 () </span><span class="sxs-lookup"><span data-stu-id="02730-229">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

- <span data-ttu-id="02730-230">依 WAN 連結類型篩選—網路網站連結、interregional 連結，以及網站內的連結</span><span class="sxs-lookup"><span data-stu-id="02730-230">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

- <span data-ttu-id="02730-231">依網路地區篩選</span><span class="sxs-lookup"><span data-stu-id="02730-231">Filtered by network region</span></span>

#### <a name="applications"></a><span data-ttu-id="02730-232">應用程式</span><span class="sxs-lookup"><span data-stu-id="02730-232">Applications</span></span>

<span data-ttu-id="02730-233">頻寬使用狀況分析器具有下列兩個應用程式 (工具) ：</span><span class="sxs-lookup"><span data-stu-id="02730-233">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

- <span data-ttu-id="02730-234">**WanLinkLogCollector.exe** 此工具可讓其使用者輸入必要的資訊。</span><span class="sxs-lookup"><span data-stu-id="02730-234">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>

- <span data-ttu-id="02730-235">**BandwidthUtilizationAnalyzer.xlsm** Microsoft Excel 試算表軟體報告會由 WanLinkLogCollector.exe 自動啟動。</span><span class="sxs-lookup"><span data-stu-id="02730-235">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="02730-236">此應用程式可讓使用者將篩選器套用至報告（如本文稍後所示）。</span><span class="sxs-lookup"><span data-stu-id="02730-236">This application allows the user to apply filters to the report as shown later in this article.</span></span>

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="02730-237">使用頻寬流量分析程式的階段</span><span class="sxs-lookup"><span data-stu-id="02730-237">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="02730-238">使用頻寬使用量分析器時，有兩個階段：</span><span class="sxs-lookup"><span data-stu-id="02730-238">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

- <span data-ttu-id="02730-239">收集使用 WanLinkLogCollector.exe 所執行的記錄</span><span class="sxs-lookup"><span data-stu-id="02730-239">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

- <span data-ttu-id="02730-240">使用 BandwidthUtilizationAnalyzer.xlsm 進行自訂報告</span><span class="sxs-lookup"><span data-stu-id="02730-240">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="02730-241">強烈建議您不要由使用者手動啟動 BandwidthUtilizationAnalyzer.xlsm。</span><span class="sxs-lookup"><span data-stu-id="02730-241">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>

#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="02730-242">啟動頻寬流量分析程式</span><span class="sxs-lookup"><span data-stu-id="02730-242">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="02730-243">在命令提示字元處或使用 Windows Explorer 開始 WanLinkLogCollector.exe。</span><span class="sxs-lookup"><span data-stu-id="02730-243">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

 <span data-ttu-id="02730-244">**使用 WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="02730-244">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="02730-245">使用 WanLinkLogCollector.exe 有三個步驟：</span><span class="sxs-lookup"><span data-stu-id="02730-245">There are three steps to using WanLinkLogCollector.exe:</span></span>

1. <span data-ttu-id="02730-246">**記錄時程表** 提供報表需要產生的時程表</span><span class="sxs-lookup"><span data-stu-id="02730-246">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>

2. <span data-ttu-id="02730-247">**指定檔目錄** 提供檔案位置資訊</span><span class="sxs-lookup"><span data-stu-id="02730-247">**Specify the file directories** Provide file location information</span></span>

3. <span data-ttu-id="02730-248">**收集記錄檔並啟動報告檢視器** 執行命令以產生報告</span><span class="sxs-lookup"><span data-stu-id="02730-248">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>

#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="02730-249">步驟 1-記錄時程表</span><span class="sxs-lookup"><span data-stu-id="02730-249">Step 1 - Log the timeline</span></span>

<span data-ttu-id="02730-250">記錄時程表可讓工具使用者指定下列，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="02730-250">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1. <span data-ttu-id="02730-251">**開始日期** 這是要產生報告的時程表開始日期;例如，2010年8月1日。</span><span class="sxs-lookup"><span data-stu-id="02730-251">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2. <span data-ttu-id="02730-252">**結束日期** 這是要產生報告的時程表結束日期;例如，2010年9月30日。</span><span class="sxs-lookup"><span data-stu-id="02730-252">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>

     ![頻寬使用狀況 A 的開始和結束日期](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="02730-254">步驟 2-指定檔目錄</span><span class="sxs-lookup"><span data-stu-id="02730-254">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="02730-255">下列是使用者可以指定的檔案目錄，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="02730-255">The following file directories can be specified by the user as shown.</span></span>

- <span data-ttu-id="02730-256">**伺服器記錄檔位置** 儲存頻寬原則伺服器記錄的資料夾位置。</span><span class="sxs-lookup"><span data-stu-id="02730-256">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="02730-257">這通常是 \<<在 \> \\ \AppServerFiles\PDP. 中選擇的 FE \></span><span class="sxs-lookup"><span data-stu-id="02730-257">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>

- <span data-ttu-id="02730-258">**暫存檔儲存位置** 產生報告時儲存中間檔案的暫存檔案位置。</span><span class="sxs-lookup"><span data-stu-id="02730-258">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

    ![頻寬使用量分析中的檔案目錄](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > <span data-ttu-id="02730-260">確定已將對伺服器記錄和暫存檔存放區資料夾的足夠存取權提供給工具使用者。</span><span class="sxs-lookup"><span data-stu-id="02730-260">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="02730-261">步驟 3-收集記錄檔並啟動報告檢視器</span><span class="sxs-lookup"><span data-stu-id="02730-261">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="02730-262">若要收集記錄檔並啟動報告檢視器，請按一下 [ **執行** ]，如下所示。</span><span class="sxs-lookup"><span data-stu-id="02730-262">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="02730-263">此步驟會收集必要的資料。</span><span class="sxs-lookup"><span data-stu-id="02730-263">This step collects the required data.</span></span>

![在頻寬利用率 Analy 中收集資料](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

<span data-ttu-id="02730-265">當輸入驗證成功時，會顯示如下所示的訊息。</span><span class="sxs-lookup"><span data-stu-id="02730-265">When the input validation is successful, the message shown below is displayed.</span></span>

![在頻寬 Utili 中收集的記錄通知](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

<span data-ttu-id="02730-267">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="02730-267">Click **OK**.</span></span> <span data-ttu-id="02730-268">BandwidthUtilizationAnalyzer.xlsm 會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="02730-268">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="02730-269">依照訊息方塊中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="02730-269">Follow the instructions in the message box.</span></span> <span data-ttu-id="02730-270">如需詳細資訊，請參閱下一節中的 **Using BandwidthUtilizationAnalyzer.xlsm** 。</span><span class="sxs-lookup"><span data-stu-id="02730-270">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>


### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="02730-271">使用 BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="02730-271">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="02730-272">自動啟動 BandwidthUtilizationAnalyzer.xlsm 時，請按一下 [重新整理] **，如下所** 示。</span><span class="sxs-lookup"><span data-stu-id="02730-272">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. <span data-ttu-id="02730-274">開啟檔案資料夾時，請選取訊息方塊中所指定的位置 consolidated.csv，如下所示。</span><span class="sxs-lookup"><span data-stu-id="02730-274">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="02730-275">它也會顯示為 **C：\Temp**的位置。</span><span class="sxs-lookup"><span data-stu-id="02730-275">It also shows the location as **C:\Temp**.</span></span>

     ![在 BandwidthUtilizationAnalyzer 中開啟資料夾。](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. <span data-ttu-id="02730-277">按一下 [匯入]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="02730-277">Click **Import**.</span></span>

4. <span data-ttu-id="02730-278">會自動產生圖形化圖形。</span><span class="sxs-lookup"><span data-stu-id="02730-278">The graphical plot is automatically generated.</span></span> <span data-ttu-id="02730-279">當工作的背景指標消失時，即可使用此功能。</span><span class="sxs-lookup"><span data-stu-id="02730-279">It is available when the working-in-the-background pointer disappears.</span></span>

     ![在報表檢視中套用篩選器。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="02730-281">將篩選器套用至報表檢視</span><span class="sxs-lookup"><span data-stu-id="02730-281">Applying Filters to the Report View</span></span>

<span data-ttu-id="02730-282">如下所示，可套用到報表檢視的篩選，如下所述：</span><span class="sxs-lookup"><span data-stu-id="02730-282">The filters that can be applied to the report view as shown below are described as follows:</span></span>

![在報表檢視中套用篩選器。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. <span data-ttu-id="02730-284">**名稱** 依 WAN 連結篩選 (篩選位於圖形) 右側。前置詞表示下列連結類型;請參閱垂直 (blue) 方塊：</span><span class="sxs-lookup"><span data-stu-id="02730-284">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>

   - <span data-ttu-id="02730-285">**S 網站** 從網路網站到網路地區的 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="02730-285">**S Site** The WAN link from a network site to a network region</span></span>

   - <span data-ttu-id="02730-286">**為網站間** 兩個網路網站間的 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="02730-286">**IS Inter-Site** The WAN link between two network sites</span></span>

   - <span data-ttu-id="02730-287">**R 區域間** 兩個網路地區之間的 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="02730-287">**R Inter-Region** The WAN link between two network region</span></span>

2. <span data-ttu-id="02730-288">**超出限制** 依頻寬使用量超過頻寬容量的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="02730-288">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3. <span data-ttu-id="02730-289">**重要層級** 依頻寬利用率達到90% 或以上頻寬容量的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="02730-289">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4. <span data-ttu-id="02730-290">**低利用率** 依頻寬利用率低於頻寬容量25% 的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="02730-290">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5. <span data-ttu-id="02730-291">**連結類型** 依下列 WAN 連結類型進行篩選：</span><span class="sxs-lookup"><span data-stu-id="02730-291">**Link type** Filter by the following WAN links types:</span></span>

   - <span data-ttu-id="02730-292">**網路網站** 類型</span><span class="sxs-lookup"><span data-stu-id="02730-292">**Network site** type</span></span>

   - <span data-ttu-id="02730-293">**網站間** 類型</span><span class="sxs-lookup"><span data-stu-id="02730-293">**Inter-site** type</span></span>

   - <span data-ttu-id="02730-294">**地區間連結** 類型</span><span class="sxs-lookup"><span data-stu-id="02730-294">**Inter-Region link** type</span></span>

6. <span data-ttu-id="02730-295">**地區** 依網路地區篩選</span><span class="sxs-lookup"><span data-stu-id="02730-295">**Region** Filter by network region</span></span>

<span data-ttu-id="02730-296">下圖顯示先前所述的篩選。</span><span class="sxs-lookup"><span data-stu-id="02730-296">The following figures show the previously described filters.</span></span>

<span data-ttu-id="02730-297">依 **名稱**篩選。</span><span class="sxs-lookup"><span data-stu-id="02730-297">Filter by **Name**.</span></span> <span data-ttu-id="02730-298">選取需要顯示在圖表中的連結清單。</span><span class="sxs-lookup"><span data-stu-id="02730-298">Select the list of links that need to be displayed in the graph.</span></span>

![在 BandwidthUtilizationAnalyzer 中以名稱篩選。](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

<span data-ttu-id="02730-300">篩選依據 **超出限制**。</span><span class="sxs-lookup"><span data-stu-id="02730-300">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="02730-301">選取 [ **True** ] 以強制執行篩選。</span><span class="sxs-lookup"><span data-stu-id="02730-301">Select **True** to enforce the filter.</span></span>

![以超出限制篩選。](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

<span data-ttu-id="02730-303">依 **重要層級**篩選。</span><span class="sxs-lookup"><span data-stu-id="02730-303">Filter by **Critical levels**.</span></span> <span data-ttu-id="02730-304">選取 [ **True** ] 以強制執行篩選。</span><span class="sxs-lookup"><span data-stu-id="02730-304">Select **True** to enforce the filter.</span></span>

![依重要層級篩選。](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

<span data-ttu-id="02730-306">根據 **使用**中的篩選。</span><span class="sxs-lookup"><span data-stu-id="02730-306">Filter by **Under utilized**.</span></span> <span data-ttu-id="02730-307">選取 [ **True** ] 以強制執行篩選。</span><span class="sxs-lookup"><span data-stu-id="02730-307">Select **True** to enforce the filter.</span></span>

![按使用中的篩選。](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

<span data-ttu-id="02730-309">依 **連結類型**篩選。</span><span class="sxs-lookup"><span data-stu-id="02730-309">Filter by **Link Type**.</span></span> <span data-ttu-id="02730-310">選取需要顯示的類型或類型。</span><span class="sxs-lookup"><span data-stu-id="02730-310">Select the type or types that need to be displayed.</span></span>

![依連結類型篩選。](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

<span data-ttu-id="02730-312">依 **地區**篩選。</span><span class="sxs-lookup"><span data-stu-id="02730-312">Filter by **Region**.</span></span> <span data-ttu-id="02730-313">選取需要顯示其連結的區域清單。</span><span class="sxs-lookup"><span data-stu-id="02730-313">Select a list of regions whose links need to be displayed.</span></span>

![依地區篩選。](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a><span data-ttu-id="02730-315">需求</span><span class="sxs-lookup"><span data-stu-id="02730-315">Requirements</span></span>

- <span data-ttu-id="02730-316">.NET Framework 3。5</span><span class="sxs-lookup"><span data-stu-id="02730-316">The .NET Framework 3.5</span></span>

- <span data-ttu-id="02730-317">Microsoft Excel 2010 或 Excel 2007</span><span class="sxs-lookup"><span data-stu-id="02730-317">Microsoft Excel 2010 or Excel 2007</span></span>

### <a name="summary"></a><span data-ttu-id="02730-318">摘要</span><span class="sxs-lookup"><span data-stu-id="02730-318">Summary</span></span>

<span data-ttu-id="02730-319">頻寬流量分析程式可用來繪製網路上 UC 流量的音訊頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="02730-319">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="02730-320">您也可以使用此工具來報告網路上的視頻頻寬使用方式。</span><span class="sxs-lookup"><span data-stu-id="02730-320">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

## <a name="call-parkometer"></a><span data-ttu-id="02730-321">呼叫 Call parkometer</span><span class="sxs-lookup"><span data-stu-id="02730-321">Call Parkometer</span></span>
<span data-ttu-id="02730-322"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="02730-322"><a name="callpark"> </a></span></span>

<span data-ttu-id="02730-323">「呼叫 Call parkometer」是一種命令列應用程式，可讓您輕鬆存取通話駐留軌道資料庫。</span><span class="sxs-lookup"><span data-stu-id="02730-323">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

### <a name="description"></a><span data-ttu-id="02730-324">描述</span><span class="sxs-lookup"><span data-stu-id="02730-324">Description</span></span>

<span data-ttu-id="02730-325">「呼叫 Call parkometer 是一種可追蹤目前寄存通話的工具。</span><span class="sxs-lookup"><span data-stu-id="02730-325">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="02730-326">它也會收集有關軌道和通話駐留伺服器 (CPS) 使用狀況的統計資料。</span><span class="sxs-lookup"><span data-stu-id="02730-326">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="02730-327">這個命令列工具既可以從本機或遠端連線的電腦，提供對 CPS 軌道 SQL Server 資料庫的讀取和寫入存取權。</span><span class="sxs-lookup"><span data-stu-id="02730-327">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="02730-328">所有選項都是互斥的。</span><span class="sxs-lookup"><span data-stu-id="02730-328">All options are mutually exclusive.</span></span> <span data-ttu-id="02730-329">命令列語法如下：</span><span class="sxs-lookup"><span data-stu-id="02730-329">Command-line syntax is as follows:</span></span>

- <span data-ttu-id="02730-330">**-o** 參數--列出為此集區設定的所有軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="02730-330">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>

- <span data-ttu-id="02730-331">**-n** 參數-列出此集區中所有目前使用的軌道。</span><span class="sxs-lookup"><span data-stu-id="02730-331">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="02730-332">顯示的資訊如下：</span><span class="sxs-lookup"><span data-stu-id="02730-332">The information displayed is as follows:</span></span>

  - <span data-ttu-id="02730-333">SIP 統一資源識別項 (parkee 和 parker 的 URI) 。</span><span class="sxs-lookup"><span data-stu-id="02730-333">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>

  - <span data-ttu-id="02730-334">寄存通話之 CPS 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="02730-334">Host name of the CPS where the call is parked.</span></span>

  - <span data-ttu-id="02730-335">寄存通話的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="02730-335">Time stamp of when the call was parked.</span></span>

- <span data-ttu-id="02730-336">**-f** 參數--列出集區中目前可用的軌道的數目。</span><span class="sxs-lookup"><span data-stu-id="02730-336">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>

- <span data-ttu-id="02730-337">\*\*-r \< n \> \*\*參數-列出 \< n \> 最後一個寄存的呼叫。</span><span class="sxs-lookup"><span data-stu-id="02730-337">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="02730-338">顯示的資訊如下：</span><span class="sxs-lookup"><span data-stu-id="02730-338">The information displayed is as follows:</span></span>

  - <span data-ttu-id="02730-339">Parkee SIP URI。</span><span class="sxs-lookup"><span data-stu-id="02730-339">Parkee SIP URI.</span></span>

  - <span data-ttu-id="02730-340">Parker SIP URI。</span><span class="sxs-lookup"><span data-stu-id="02730-340">Parker SIP URI.</span></span>

  - <span data-ttu-id="02730-341">寄存通話之 CPS 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="02730-341">Host name of the CPS where the call was parked.</span></span>

  - <span data-ttu-id="02730-342">檢索或丟棄通話的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="02730-342">Time stamp of when the call was retrieved or dropped.</span></span>

- <span data-ttu-id="02730-343">\*\*-t \< n \> \*\*參數-測試在資料庫中保留軌道，以顯示所指派軌道編號的隨機性。</span><span class="sxs-lookup"><span data-stu-id="02730-343">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

### <a name="output"></a><span data-ttu-id="02730-344">輸出</span><span class="sxs-lookup"><span data-stu-id="02730-344">Output</span></span>

<span data-ttu-id="02730-345">根據在命令提示字元中指定的輸入參數，「呼叫 Call parkometer」會顯示下列輸出：</span><span class="sxs-lookup"><span data-stu-id="02730-345">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

- <span data-ttu-id="02730-346">為此集區設定的所有軌道範圍</span><span class="sxs-lookup"><span data-stu-id="02730-346">All orbit ranges that are configured for this pool</span></span>

- <span data-ttu-id="02730-347">目前寄存通話</span><span class="sxs-lookup"><span data-stu-id="02730-347">Currently parked calls</span></span>

- <span data-ttu-id="02730-348">) 軌道中可用的可用 (數目</span><span class="sxs-lookup"><span data-stu-id="02730-348">Number of free (available) orbits</span></span>

- <span data-ttu-id="02730-349">最近寄存的通話</span><span class="sxs-lookup"><span data-stu-id="02730-349">Recently parked calls</span></span>

- <span data-ttu-id="02730-350">用於測試均勻及隨機軌道值的保留軌道</span><span class="sxs-lookup"><span data-stu-id="02730-350">Reserved orbits for testing uniform and random orbit values</span></span>

### <a name="purpose"></a><span data-ttu-id="02730-351">用途</span><span class="sxs-lookup"><span data-stu-id="02730-351">Purpose</span></span>

<span data-ttu-id="02730-352">CPS 工具的目的是提供 CPS 資料庫的命令列存取權。</span><span class="sxs-lookup"><span data-stu-id="02730-352">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="02730-353">管理員可以查看 CPS 使用狀況，並決定指派至集區的軌道數目。</span><span class="sxs-lookup"><span data-stu-id="02730-353">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

### <a name="requirements"></a><span data-ttu-id="02730-354">需求</span><span class="sxs-lookup"><span data-stu-id="02730-354">Requirements</span></span>

<span data-ttu-id="02730-355">如果此工具在執行 CPS 的同一部電腦上執行，則不會有任何需求。</span><span class="sxs-lookup"><span data-stu-id="02730-355">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="02730-356">若要在遠端電腦上執行此工具，商務用 Skype Server 2015 所使用的 SQL Server 資料庫必須設定為允許遠端存取。</span><span class="sxs-lookup"><span data-stu-id="02730-356">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="02730-357">必須使用 SQL Server 資料庫連接字串設定 Call parkometer，以連線至集區的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="02730-357">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="02730-358">此 SQL Server 資料庫連接字串是定義在設定檔案中 **parkometer.exe.config**。它必須放在 parkometer.exe 所在的相同目錄中。</span><span class="sxs-lookup"><span data-stu-id="02730-358">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="02730-359">下列 XML 檔案是 parkometer.exe.config 的範例。必須設定的參數為 [使用者名稱] (例如，mydomain\Administrator) 、密碼 (例如，mypassword) 及主機名稱 (例如，myserver) 。</span><span class="sxs-lookup"><span data-stu-id="02730-359">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

### <a name="examples"></a><span data-ttu-id="02730-360">範例</span><span class="sxs-lookup"><span data-stu-id="02730-360">Examples</span></span>

<span data-ttu-id="02730-361">已部署軌道範圍：-o 參數會列出為此集區設定的所有軌道範圍（如圖所示）。</span><span class="sxs-lookup"><span data-stu-id="02730-361">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

![「呼叫 Call parkometer 中的軌道範圍。](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

<span data-ttu-id="02730-363">目前寄存通話：-n 參數會列出此集區上所有目前使用的軌道（如圖所示）。</span><span class="sxs-lookup"><span data-stu-id="02730-363">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>

![呼叫 Call parkometer 中的目前寄存通話。](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

<span data-ttu-id="02730-365">[自由] 軌道的數目：-f 參數會列出集區中目前可用的軌道式的數目（如圖所示）。</span><span class="sxs-lookup"><span data-stu-id="02730-365">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>

![空閒的軌道式按呼叫 Call parkometer。](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

<span data-ttu-id="02730-367">最近寄存的通話：-r \< n \> 參數會列出 \< n \> 最後一個寄存的呼叫，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="02730-367">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

![通話 Call parkometer 中最近寄存的通話。](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

<span data-ttu-id="02730-369">測試軌道保留：-t \< n \> 參數會測試在資料庫中保留軌道（如圖所示）。</span><span class="sxs-lookup"><span data-stu-id="02730-369">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

![在 [呼叫 Call parkometer] 中測試軌道保留。](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a><span data-ttu-id="02730-371">摘要</span><span class="sxs-lookup"><span data-stu-id="02730-371">Summary</span></span>

<span data-ttu-id="02730-372">「呼叫 Call parkometer」是一種命令列工具，提供通話駐留伺服器的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="02730-372">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

## <a name="dbanalyze"></a><span data-ttu-id="02730-373">Dbanalyze.exe</span><span class="sxs-lookup"><span data-stu-id="02730-373">DBAnalyze</span></span>
<span data-ttu-id="02730-374"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="02730-374"><a name="dba"> </a></span></span>

### <a name="description"></a><span data-ttu-id="02730-375">描述</span><span class="sxs-lookup"><span data-stu-id="02730-375">Description</span></span>

<span data-ttu-id="02730-376">Dbanalyze.exe 是一種命令列工具，可協助系統管理員收集有關商務用 Skype Server 2015 資料庫的分析報告。</span><span class="sxs-lookup"><span data-stu-id="02730-376">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="02730-377">Dbanalyze.exe 具有下列模式：診斷、使用者資料、會議、MCUs 和磁片分段：</span><span class="sxs-lookup"><span data-stu-id="02730-377">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

- <span data-ttu-id="02730-378">**診斷模式** 會建立報表，其中包含資料表 (記錄數目、分散、資料大小及索引大小) 的相關資訊。資料和記錄檔大小、最後的備份時間、執行 Microsoft Office 通訊伺服器的伺服器之間的連絡人散佈、每位使用者的許可權總數、連絡人、容器、訂閱、發佈、每位使用者的端點、預定會議、使用中會議的平均會議數目、每位使用者的排程會議、使用中會議，以及資料庫版本。</span><span class="sxs-lookup"><span data-stu-id="02730-378">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>

    > [!NOTE]
    > <span data-ttu-id="02730-379">執行診斷模式可能會影響伺服器效能。</span><span class="sxs-lookup"><span data-stu-id="02730-379">Running diagnostic mode can affect server performance.</span></span>

- <span data-ttu-id="02730-380">**使用者資料模式** 針對指定的使用者或使用者在其連絡人及許可權清單中的使用者，報告連絡人、容器、訂閱、發佈、許可權及連絡人群組資料。</span><span class="sxs-lookup"><span data-stu-id="02730-380">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="02730-381">這種模式也會報告使用者組織或受到邀之會議的摘要資料。</span><span class="sxs-lookup"><span data-stu-id="02730-381">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

- <span data-ttu-id="02730-382">**會議模式** 報告特定會議的詳細資料，包括會議、被邀請者清單、會議所允許的媒體類型清單、active MCUs (multipoint 控制項單位) 、作用中的參與者清單，以及每個參與者的信號狀態。</span><span class="sxs-lookup"><span data-stu-id="02730-382">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>

- <span data-ttu-id="02730-383">**解碼會議識別碼** 會解碼 **/pstnid** 參數所指定的公用交換電話網路 (PSTN) 會議識別碼，但不會連線至後端以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="02730-383">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

- <span data-ttu-id="02730-384">**解決會議** 會解碼 **/pstnid** 參數所指定的 PSTN 會議 ID，並顯示識別碼所指定之會議的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="02730-384">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

- <span data-ttu-id="02730-385">**MCUs 模式** 針對集區中的每個 MCU 報告識別碼、媒體類型、URL、心跳狀態、會議載入和參與者負載。</span><span class="sxs-lookup"><span data-stu-id="02730-385">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

- <span data-ttu-id="02730-386">**磁片分段模式** 顯示所有磁片的分段狀態。</span><span class="sxs-lookup"><span data-stu-id="02730-386">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="02730-387">此工具可用於診斷各種問題，或協助系統管理員進行容量規劃。</span><span class="sxs-lookup"><span data-stu-id="02730-387">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="02730-388">例如，如果在伺服器 A 上大多數的使用者都選擇以伺服器 B 為其連絡人的使用者，則系統管理員可以將伺服器 A 上的使用者移至伺服器 B，以減少跨伺服器的流量。</span><span class="sxs-lookup"><span data-stu-id="02730-388">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

### <a name="output"></a><span data-ttu-id="02730-389">輸出</span><span class="sxs-lookup"><span data-stu-id="02730-389">Output</span></span>

<span data-ttu-id="02730-390">此工具會輸出商務用 Skype Server 2015 資料庫的預先定義報告。</span><span class="sxs-lookup"><span data-stu-id="02730-390">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="02730-391">**路徑**：商務用 skype Server 2015 \ Reskit 的%ProgramFiles%\Skype</span><span class="sxs-lookup"><span data-stu-id="02730-391">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>

### <a name="purpose"></a><span data-ttu-id="02730-392">用途</span><span class="sxs-lookup"><span data-stu-id="02730-392">Purpose</span></span>

<span data-ttu-id="02730-393">若要安裝 Dbanalyze.exe，請將它複製到本機資料夾，然後執行工具。</span><span class="sxs-lookup"><span data-stu-id="02730-393">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="02730-394">若要使用此工具，請從命令列執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="02730-394">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="02730-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` 命令列選項的描述如下所示。</span><span class="sxs-lookup"><span data-stu-id="02730-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>

![Dbanalyze.exe 的命令列選項。](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a><span data-ttu-id="02730-397">需求</span><span class="sxs-lookup"><span data-stu-id="02730-397">Requirements</span></span>

 <span data-ttu-id="02730-398">**電腦** Dbanalyze.exe 只能在已安裝商務用 Skype Server 2015 的已加入網域的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="02730-398">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>

 <span data-ttu-id="02730-399">**網路** 電腦應該可以連接至後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="02730-399">**Network** The computer should be able to connect to the back-end database.</span></span>

 <span data-ttu-id="02730-400">**軟體** 在執行 Dbanalyze.exe 之前，必須先安裝商務用 Skype Server 2015 軟體元件。</span><span class="sxs-lookup"><span data-stu-id="02730-400">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>

 <span data-ttu-id="02730-401">**使用者**下表顯示具有存取商務用 Skype Server 2015 資料庫之必要許可權的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="02730-401">**Users**The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>

![Dbanalyze.exe 的許可權表格。](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> <span data-ttu-id="02730-403">**/Report：磁片**模式需要本機系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="02730-403">A local administrator account is required for **/report:disk** mode.</span></span>

### <a name="examples"></a><span data-ttu-id="02730-404">範例</span><span class="sxs-lookup"><span data-stu-id="02730-404">Examples</span></span>

<span data-ttu-id="02730-405">以下是有效 Dbanalyze.exe 命令的範例：</span><span class="sxs-lookup"><span data-stu-id="02730-405">The following are examples of valid Dbanalyze.exe commands:</span></span>

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="02730-406">摘要</span><span class="sxs-lookup"><span data-stu-id="02730-406">Summary</span></span>

<span data-ttu-id="02730-407">DBAnalyzer 可讓系統管理員快速且容易地分析商務用 Skype Server 2015 資料庫。</span><span class="sxs-lookup"><span data-stu-id="02730-407">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>

## <a name="import-storage-service-data"></a><span data-ttu-id="02730-408">匯入儲存體服務資料</span><span class="sxs-lookup"><span data-stu-id="02730-408">Import Storage Service Data</span></span>
<span data-ttu-id="02730-409"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="02730-409"><a name="Issd"> </a></span></span>

<span data-ttu-id="02730-410">ImportStorageServiceData 資源工具組工具可讓您重新匯入儲存服務 (LYSS) 回儲存體服務的佇列和端點資料。</span><span class="sxs-lookup"><span data-stu-id="02730-410">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

### <a name="description"></a><span data-ttu-id="02730-411">描述</span><span class="sxs-lookup"><span data-stu-id="02730-411">Description</span></span>

<span data-ttu-id="02730-412">根據佇列專案狀態或資料庫大小而定，儲存服務所清除的資料可能會自動 (定期) 。</span><span class="sxs-lookup"><span data-stu-id="02730-412">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="02730-413">這可能是因為手動呼叫集區容錯移轉指令 StorageServiceFullFlush，或是集區容錯移轉指令) 所呼叫的 Cmdlet (。</span><span class="sxs-lookup"><span data-stu-id="02730-413">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="02730-414">請注意，如果前端的任何儲存服務 (LYSS ) 資料庫大小高於一般層級以上，則理想情況下不會重新匯入資料，因為這樣做可能只會造成更多資料可傳回輸出。此外，任何可能會導致儲存服務佇列成長之錯誤的問題，都應該先加以解析 (例如 Exchange 端點錯誤、網路問題或其他問題) 。</span><span class="sxs-lookup"><span data-stu-id="02730-414">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

 <span data-ttu-id="02730-415">**案例1：** 集區容錯移轉期間，每個前端的檔案可能會從儲存體服務上清除。</span><span class="sxs-lookup"><span data-stu-id="02730-415">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="02730-416">容錯移轉完成後，應執行該工具，以重新匯入資料。</span><span class="sxs-lookup"><span data-stu-id="02730-416">After failover is completed, the tool should be run to re-import the data.</span></span>

 <span data-ttu-id="02730-417">**案例2：** 每日自動清除資料，或回應儲存服務資料庫超過一定大小的閾值 ( 例如60%、80%、90% full ) 。</span><span class="sxs-lookup"><span data-stu-id="02730-417">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="02730-418">這會自動清除的資料應該由系統管理員定期重新匯入。</span><span class="sxs-lookup"><span data-stu-id="02730-418">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="02730-419">在上述情況下，如果不是部署監控 SCOM 套件，則會有商務用 Skype Server Storage Service 的事件，這些事件與從儲存體服務清除的資料相關。</span><span class="sxs-lookup"><span data-stu-id="02730-419">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="02730-420">已啟動 32075 (完整清除作業的事件 IDs) ，32076 (完全清除已完成) ，32082 (維護層級清理已開始) ，32083 (維護層級清理完成) ，32089 (因填滿資料庫) 而發生清理。</span><span class="sxs-lookup"><span data-stu-id="02730-420">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="02730-421">請注意，這些事件識別碼會對應至 RTM 版本。</span><span class="sxs-lookup"><span data-stu-id="02730-421">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="02730-422">當系統管理員看到這些事件時，表示已清除的檔案。此資料應該定期使用此工具（例如每週一次）匯入回來。</span><span class="sxs-lookup"><span data-stu-id="02730-422">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="02730-423">在線上服務發行時，如果部署了商務用 Skype Server 的 health monitoring SCOM 套件，則可能會引發新的警示，讓系統管理員將清除的資料重新匯入儲存體服務。</span><span class="sxs-lookup"><span data-stu-id="02730-423">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="02730-424">在觸發警示的前端伺服器上，事件記錄檔中會有對應的事件。</span><span class="sxs-lookup"><span data-stu-id="02730-424">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="02730-425">此事件會提供清除資料檔案所在之父路徑的描述，以及有多少個可滿足警示準則的檔。</span><span class="sxs-lookup"><span data-stu-id="02730-425">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="02730-426">警示準則是指在特定的父路徑下有 X 個或多個檔案，該預設路徑至少是 Y 天的舊 ( 版本，StorageService 中的 X 和 Y 是預先預置的，但是可以透過變更 APPCONFIG 檔加以覆寫。 ) 下列兩個可能觸發狀況警示的事件範例，其差異是其父項路徑。</span><span class="sxs-lookup"><span data-stu-id="02730-426">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="02730-427">有一種可能的情況是在 Web 服務檔案共用下，另一種可能性是每個前端的本機應用程式資料目錄。</span><span class="sxs-lookup"><span data-stu-id="02730-427">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="02730-428"> ( 例如，Business Server 2015 \ StorageService ) 的 c:\ProgramData\Microsoft\Skype。</span><span class="sxs-lookup"><span data-stu-id="02730-428">( for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ).</span></span> <span data-ttu-id="02730-429">然後，系統管理員會執行此 reskit 工具。</span><span class="sxs-lookup"><span data-stu-id="02730-429">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="02730-430">此工具會在執行的前端上增加 CPU 和 IO 負載，以及其他前端，在此情況下，資料不是由執行該工具的前端所擁有。</span><span class="sxs-lookup"><span data-stu-id="02730-430">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="02730-431">我們建議您在前端不低於大量 CPU 和 IO 負載（例如峰值時段外）時，runng 此工具。</span><span class="sxs-lookup"><span data-stu-id="02730-431">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="02730-432">其次，此工具可以2到3分鐘，匯入一個資料檔案。</span><span class="sxs-lookup"><span data-stu-id="02730-432">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="02730-433">在評估工具的執行時間時，請務必記住這一點。</span><span class="sxs-lookup"><span data-stu-id="02730-433">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="02730-434">預設會在檔存放區上顯示工具所產生的詳細記錄檔。</span><span class="sxs-lookup"><span data-stu-id="02730-434">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="02730-435">如果沒有報告錯誤，請將其刪除，因為記錄檔可能會是數十 MB 或更多。</span><span class="sxs-lookup"><span data-stu-id="02730-435">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

![儲存區伺服器事件記錄事件範例。](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a><span data-ttu-id="02730-437">需求</span><span class="sxs-lookup"><span data-stu-id="02730-437">Requirements</span></span>

<span data-ttu-id="02730-438">安裝商務用 Skype Server 2015 資源套件工具。</span><span class="sxs-lookup"><span data-stu-id="02730-438">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="02730-439">工具會在已加入網域的電腦上執行，其中會安裝商務用 Skype Server 和商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="02730-439">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="02730-440">該工具會使用來自管理命令介面的 Cmdlet，識別集區中的所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="02730-440">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="02730-441">其次，必須從已安裝 **RtcLocal** 資料庫的集區中的機器執行工具。</span><span class="sxs-lookup"><span data-stu-id="02730-441">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="02730-442">此資料庫由工具使用，以取得集區的 WEBSERVICE 檔案共用的位置。</span><span class="sxs-lookup"><span data-stu-id="02730-442">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="02730-443">此外，在使用此工具之前，每一部前端伺服器都必須先在每一部前端伺服器上使用 **Enable-PSRemoting** 啟用 Windows PowerShell 遠端處理，以及執行該工具的機器。</span><span class="sxs-lookup"><span data-stu-id="02730-443">Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="02730-444">否則，來自此工具的遠端 Windows PowerShell 命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="02730-444">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="02730-445">在集區完成後，您可以在集區中的所有前端伺服器上關閉 Windows PowerShell 遠端處理。</span><span class="sxs-lookup"><span data-stu-id="02730-445">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="02730-446">最後，開啟工具的帳戶或憑證必須具有可讀取/寫入權限給其在其上執行此工具的集區。</span><span class="sxs-lookup"><span data-stu-id="02730-446">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="02730-447">否則，該工具會失敗，並顯示 IO 許可權錯誤。</span><span class="sxs-lookup"><span data-stu-id="02730-447">Otherwise the tool will fail with IO Permission errors.</span></span>

> [!NOTE]
> <span data-ttu-id="02730-448">在 Windows Server 2012 上，Windows PowerShell 遠端處理會預設為啟用，但不會在 Windows Server 2008 作業系統上啟用。</span><span class="sxs-lookup"><span data-stu-id="02730-448">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>

### <a name="examples"></a><span data-ttu-id="02730-449">範例</span><span class="sxs-lookup"><span data-stu-id="02730-449">Examples</span></span>

```console
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

## <a name="lcssync"></a><span data-ttu-id="02730-450">LCSSync</span><span class="sxs-lookup"><span data-stu-id="02730-450">LCSSync</span></span>
<span data-ttu-id="02730-451"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="02730-451"><a name="LCSSync"> </a></span></span>

<span data-ttu-id="02730-452">LCSSync 工具可協助您在多樹系環境中部署商務用 Skype Server 2015 通訊軟體。</span><span class="sxs-lookup"><span data-stu-id="02730-452">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="02730-453">此工具是用來將不同使用者樹系中的使用者和群組，當作 Active Directory 網域服務連絡人物件同步處理到安裝商務用 Skype Server 2015 的中央樹系。</span><span class="sxs-lookup"><span data-stu-id="02730-453">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>

### <a name="description"></a><span data-ttu-id="02730-454">描述</span><span class="sxs-lookup"><span data-stu-id="02730-454">Description</span></span>

 <span data-ttu-id="02730-455">LCSSync 使用中央樹系中的 [同步處理 Active Directory 網域服務] 連絡人物件，為商務用 Skype Server 啟用使用者。</span><span class="sxs-lookup"><span data-stu-id="02730-455">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="02730-456">若要提供單一登入，主要使用者帳戶必須對應至中央樹系中的 Active Directory 網域服務連絡人物件，以供商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="02730-456">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="02730-457">這個工具可協助您執行該對應。</span><span class="sxs-lookup"><span data-stu-id="02730-457">This tool helps perform that mapping.</span></span> <span data-ttu-id="02730-458">此工具提供範本，以在 Microsoft Identity Integration Server 中建立管理代理程式。</span><span class="sxs-lookup"><span data-stu-id="02730-458">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

### <a name="summary"></a><span data-ttu-id="02730-459">摘要</span><span class="sxs-lookup"><span data-stu-id="02730-459">Summary</span></span>

<span data-ttu-id="02730-460">LCSSync 工具可協助您在多樹系環境中部署商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="02730-460">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>

## <a name="lookup-user-console"></a><span data-ttu-id="02730-461">查閱使用者主控台</span><span class="sxs-lookup"><span data-stu-id="02730-461">Lookup User Console</span></span>
<span data-ttu-id="02730-462"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="02730-462"><a name="LUC"> </a></span></span>

<span data-ttu-id="02730-463">LookupUserConsole 工具會顯示特定使用者的內部商務用 Skype 伺服器路由資訊。</span><span class="sxs-lookup"><span data-stu-id="02730-463">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="02730-464">此資訊對 Microsoft 支援個人在診斷部署和路由問題時可能十分有用。</span><span class="sxs-lookup"><span data-stu-id="02730-464">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

### <a name="description"></a><span data-ttu-id="02730-465">描述</span><span class="sxs-lookup"><span data-stu-id="02730-465">Description</span></span>

 <span data-ttu-id="02730-466">執行 LookupUserConsole.exe 會開啟接收 SIP 位址的命令提示字元，並嘗試顯示與其相關的內部商務用 Skype 伺服器路由資訊。</span><span class="sxs-lookup"><span data-stu-id="02730-466">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="02730-467">若要結束 LookupUserConsole 工具，請輸入 **exit** 。</span><span class="sxs-lookup"><span data-stu-id="02730-467">Type **exit** to quit the LookupUserConsole tool.</span></span>

### <a name="requirements"></a><span data-ttu-id="02730-468">需求</span><span class="sxs-lookup"><span data-stu-id="02730-468">Requirements</span></span>

<span data-ttu-id="02730-469">安裝商務用 Skype Server 2015 資源套件。</span><span class="sxs-lookup"><span data-stu-id="02730-469">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="02730-470">工具會在安裝商務用 Skype 伺服器的已加入網域的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="02730-470">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>

### <a name="examples"></a><span data-ttu-id="02730-471">範例</span><span class="sxs-lookup"><span data-stu-id="02730-471">Examples</span></span>

<span data-ttu-id="02730-472">C:\Program Files\Skype for Business Server 2015 \ ResKit \>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="02730-472">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>

```console
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

## <a name="msturnping"></a><span data-ttu-id="02730-473">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="02730-473">MsTurnPing</span></span>
<span data-ttu-id="02730-474"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="02730-474"><a name="MsTurnPing"> </a></span></span>

<span data-ttu-id="02730-475">MSTurnPing 工具可讓商務用 Skype Server 2015 通訊軟體的系統管理員檢查執行 Audio/Video Edge 的伺服器狀態，以及 Audio/Video 驗證服務，以及在拓撲中執行頻寬原則服務的伺服器。</span><span class="sxs-lookup"><span data-stu-id="02730-475">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

### <a name="description"></a><span data-ttu-id="02730-476">描述</span><span class="sxs-lookup"><span data-stu-id="02730-476">Description</span></span>

<span data-ttu-id="02730-477">MSTurnPing 工具可讓商務用 Skype Server 2015 通訊軟體的系統管理員檢查執行 Audio/Video Edge 的伺服器狀態，以及 Audio/Video 驗證服務，以及在拓撲中執行頻寬原則服務的伺服器。</span><span class="sxs-lookup"><span data-stu-id="02730-477">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="02730-478">工具可讓系統管理員執行下列測試：</span><span class="sxs-lookup"><span data-stu-id="02730-478">The tool allows the administrator to perform the following tests:</span></span>

1. <span data-ttu-id="02730-479">A/V Edge Server 測試：此工具會執行下列作業，針對拓撲中的所有 A/V Edge server 執行測試：</span><span class="sxs-lookup"><span data-stu-id="02730-479">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>

   - <span data-ttu-id="02730-480">確認已啟動商務用 Skype Server Audio/Video 驗證服務，且可以發出適當的認證。</span><span class="sxs-lookup"><span data-stu-id="02730-480">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="02730-481">確認已啟動商務用 Skype Server Audio/Video Edge service，且可成功地在外部 Edge 上分攤資源。</span><span class="sxs-lookup"><span data-stu-id="02730-481">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2. <span data-ttu-id="02730-482">頻寬原則服務測試：此工具會透過執行下列動作，對拓撲中執行頻寬原則服務的所有伺服器執行測試：</span><span class="sxs-lookup"><span data-stu-id="02730-482">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>

   - <span data-ttu-id="02730-483">確認已啟動商務用 Skype Server 頻寬原則服務 (驗證) ，且可發出適當的認證。</span><span class="sxs-lookup"><span data-stu-id="02730-483">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="02730-484">確認已啟動商務用 Skype Server 頻寬原則服務 (核心) ，且可成功執行頻寬檢查。</span><span class="sxs-lookup"><span data-stu-id="02730-484">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="02730-485">此工具必須從屬於拓撲的電腦上執行，且已安裝本機儲存區。</span><span class="sxs-lookup"><span data-stu-id="02730-485">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

### <a name="output"></a><span data-ttu-id="02730-486">輸出</span><span class="sxs-lookup"><span data-stu-id="02730-486">Output</span></span>

<span data-ttu-id="02730-487">工具會輸出每個作業的結果。</span><span class="sxs-lookup"><span data-stu-id="02730-487">The tool outputs the results of each of the operations.</span></span>

- <span data-ttu-id="02730-488">如果執行 **AudioVideoEdgeServer** 測試，則會輸出下列工具：</span><span class="sxs-lookup"><span data-stu-id="02730-488">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="02730-489">在拓撲中供應商務用 Skype Server 2015 Audio/Video 驗證服務之電腦的測試結果</span><span class="sxs-lookup"><span data-stu-id="02730-489">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>

  - <span data-ttu-id="02730-490">在拓撲中供應商務用 Skype Server 2015 Audio/Video Edge service 之電腦的測試結果</span><span class="sxs-lookup"><span data-stu-id="02730-490">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>

- <span data-ttu-id="02730-491">如果執行 **BandwidthPolicyServer** 測試，則會輸出下列工具：</span><span class="sxs-lookup"><span data-stu-id="02730-491">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="02730-492">在拓撲中供應商務用 Skype Server 2015 頻寬原則服務的電腦測試結果 (驗證) </span><span class="sxs-lookup"><span data-stu-id="02730-492">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>

  - <span data-ttu-id="02730-493">供應商務用 Skype Server 2015 頻寬原則服務之電腦的測試結果，在拓撲中 (核心) </span><span class="sxs-lookup"><span data-stu-id="02730-493">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>

### <a name="requirements"></a><span data-ttu-id="02730-494">需求</span><span class="sxs-lookup"><span data-stu-id="02730-494">Requirements</span></span>

- <span data-ttu-id="02730-495">此工具必須從拓撲中的電腦執行，且具有本機儲存區。</span><span class="sxs-lookup"><span data-stu-id="02730-495">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

- <span data-ttu-id="02730-496">您必須以具有本機儲存區存取權的系統管理員身分執行工具。</span><span class="sxs-lookup"><span data-stu-id="02730-496">The tool must be run as an administrator who has access to the local store.</span></span>

### <a name="examples"></a><span data-ttu-id="02730-497">範例</span><span class="sxs-lookup"><span data-stu-id="02730-497">Examples</span></span>

<span data-ttu-id="02730-498">下列為工具輸入的範例。</span><span class="sxs-lookup"><span data-stu-id="02730-498">The following is an example of the tool input.</span></span>

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="02730-499">摘要</span><span class="sxs-lookup"><span data-stu-id="02730-499">Summary</span></span>

<span data-ttu-id="02730-500">此工具對於商務用 Skype Server 2015 系統管理員而言是一種重要資源，您想要檢查執行音訊/視頻和頻寬原則服務之伺服器的狀態。</span><span class="sxs-lookup"><span data-stu-id="02730-500">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

## <a name="network-configuration-viewer"></a><span data-ttu-id="02730-501">網路設定檢視器</span><span class="sxs-lookup"><span data-stu-id="02730-501">Network Configuration Viewer</span></span>
<span data-ttu-id="02730-502"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="02730-502"><a name="NCV"> </a></span></span>

<span data-ttu-id="02730-503">商務用 Skype Server 2015 通訊軟體管理員可以使用網路設定檢視器來查看已布建的企業的通話許可控制 (CAC) 網路拓朴，以允許即時通訊會話，例如根據指定的頻寬容量進行語音或視頻通話。</span><span class="sxs-lookup"><span data-stu-id="02730-503">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="02730-504">商務用 skype Server 2015 系統管理員會定義 CAC 原則，這些原則是隨商務用 Skype Server 2015 一起安裝的頻寬原則服務所強制執行。</span><span class="sxs-lookup"><span data-stu-id="02730-504">Skype for Business Server 2015 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>

### <a name="description"></a><span data-ttu-id="02730-505">描述</span><span class="sxs-lookup"><span data-stu-id="02730-505">Description</span></span>

<span data-ttu-id="02730-506">網路設定檢視器 ( # A0) 可讓系統管理員執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="02730-506">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

- <span data-ttu-id="02730-507">從商務用 Skype Server 2015 部署中，以圖形格式載入和查看 CAC 網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="02730-507">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>

- <span data-ttu-id="02730-508">從頻寬原則伺服器記錄檔以圖形格式載入和查看 CAC 網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="02730-508">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

- <span data-ttu-id="02730-509">以 XML 格式將 CAC 網路拓撲儲存及儲存在磁片上。</span><span class="sxs-lookup"><span data-stu-id="02730-509">Save and store CAC network topology in an XML format on the disk.</span></span>

- <span data-ttu-id="02730-510">以 JPG 或 BMP 格式儲存和儲存 CAC 網路拓撲圖表。</span><span class="sxs-lookup"><span data-stu-id="02730-510">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

- <span data-ttu-id="02730-511">查看 CAC 網路拓撲設定資料。</span><span class="sxs-lookup"><span data-stu-id="02730-511">View CAC network topology configuration data.</span></span>

- <span data-ttu-id="02730-512">以樹狀目錄模式顯示 CAC 網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="02730-512">View CAC network topology in a tree-view style.</span></span>

- <span data-ttu-id="02730-513">針對 CAC 網路拓撲連結定義自訂連接器 (例如，網站對地區、區域對地區及網站對站台連結) 。</span><span class="sxs-lookup"><span data-stu-id="02730-513">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

- <span data-ttu-id="02730-514">流覽 CAC 網路拓撲網站資訊、地區資訊，以及布建的頻寬原則和網路連結。</span><span class="sxs-lookup"><span data-stu-id="02730-514">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

### <a name="purpose"></a><span data-ttu-id="02730-515">用途</span><span class="sxs-lookup"><span data-stu-id="02730-515">Purpose</span></span>

<span data-ttu-id="02730-516">在圖形化介面中查看企業 CAC 網路拓撲連結。</span><span class="sxs-lookup"><span data-stu-id="02730-516">View enterprise CAC network topology links in a graphical interface.</span></span>

### <a name="examples"></a><span data-ttu-id="02730-517">範例</span><span class="sxs-lookup"><span data-stu-id="02730-517">Examples</span></span>

 <span data-ttu-id="02730-518">**從商務用 Skype server 2015 部署中，以圖形格式載入和查看 cac 網路拓撲**：商務用 skype server 2015 管理員可以使用 [ **下載網路** 設定] 選項，在任何商務用 skype server 2015 電腦上載入和查看 cac 網路拓撲設定，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="02730-518">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="02730-519">在未連接至商務用 Skype Server 2015 設定儲存區的電腦上部署時，工具將無法下載或查看此類設定。</span><span class="sxs-lookup"><span data-stu-id="02730-519">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>

![下載網路設定。](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 <span data-ttu-id="02730-521">**從頻寬原則伺服器記錄檔以圖形格式載入和查看 CAC 網路拓撲：** 商務用 skype Server 2015 頻寬原則伺服器將 CAC 網路拓撲儲存為商務用 Skype Server 2015 檔案共用位置的記錄機制部分。</span><span class="sxs-lookup"><span data-stu-id="02730-521">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="02730-522">商務用 Skype Server 2015 系統管理員可以使用如下所示的 [ **開放網路** 設定] 選項，以圖形格式來查看這類檔案。</span><span class="sxs-lookup"><span data-stu-id="02730-522">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

![開啟頻寬原則伺服器記錄檔。](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

<span data-ttu-id="02730-524">在磁片上以 XML 格式儲存及儲存 CAC 網路拓撲：商務用 Skype Server 2015 系統管理員可以使用 [ **儲存網路設定的副本** ] 選項，以 xml 格式儲存 cac 網路拓撲設定檔，如下所示。</span><span class="sxs-lookup"><span data-stu-id="02730-524">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="02730-525">然後，已儲存的設定檔便可供離線使用，以供圖形化查看之用。</span><span class="sxs-lookup"><span data-stu-id="02730-525">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

![將網路設定儲存為 XML 檔案。](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

<span data-ttu-id="02730-527">以 JPG 或 BMP 格式儲存及儲存 CAC 網路拓撲圖表：商務用 Skype Server 2015 系統管理員可以使用 [ **將網路設定圖表儲存為圖片** ] 選項，將 cac 網路拓撲設定儲存為圖形格式 (JPG 和 bmp 檔案格式) ，如下所示。</span><span class="sxs-lookup"><span data-stu-id="02730-527">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

![將網路設定儲存為圖片。](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <span data-ttu-id="02730-529"><strong>查看 CAC 網路拓撲設定資料：</strong>商務用 Skype Server 2015 系統管理員可以使用如下所示的 [查看網路設定資料] 選項，以文字格式查看相關網路設定資料，例如網路地區、網路網站、頻寬設定檔及網站子網 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="02730-529"><strong>View CAC network topology configuration data:</strong>Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

![查看網路設定資料。](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 <span data-ttu-id="02730-531">**以樹狀目錄查看樣式中的 CAC 網路拓朴模式：** 商務用 Skype Server 2015 系統管理員可以使用工具視窗左邊的 [控制台]，以圖形樹狀檢視樣式來查看相關的網路設定資料，如下所示。</span><span class="sxs-lookup"><span data-stu-id="02730-531">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

![以樹狀目錄查看網路設定資料。](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 <span data-ttu-id="02730-533">**針對 CAC 網路拓撲連結定義自訂連接器， (例如「點對點」、「地區對** 地區」及「點對點」連結) ：商務用 Skype Server 2015 系統管理員可以使用如下所示的 [設定] 選項，定義 CAC 網路設定 WAN 連結的自訂圖形連接器。</span><span class="sxs-lookup"><span data-stu-id="02730-533">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="02730-534">這有助於區分網路設定中布建的各種網路連結類型。</span><span class="sxs-lookup"><span data-stu-id="02730-534">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

![工具](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 <span data-ttu-id="02730-536">**查看 CAC 網路拓撲網站資訊、區域資訊，以及布建的頻寬原則：** 商務用 Skype Server 2015 系統管理員可以使用下列的選項，查看相關 CAC 網路地區資訊、網站資訊和 CAC 頻寬布建資訊。</span><span class="sxs-lookup"><span data-stu-id="02730-536">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="02730-537"> (例如，按一下 [網路地區] 或 [網路網站物件] 中的 [ **資訊** ]。 ) </span><span class="sxs-lookup"><span data-stu-id="02730-537">(For example, click **Info** in a network region or network site object.)</span></span>

![為您的網路定義自訂連接器。](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a><span data-ttu-id="02730-539">摘要</span><span class="sxs-lookup"><span data-stu-id="02730-539">Summary</span></span>

<span data-ttu-id="02730-540">這項工具對於商務用 Skype Server 2015 系統管理員而言是一種重要資源，想要以圖形格式查看其部署的 CAC 網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="02730-540">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

## <a name="response-group-agent-live"></a><span data-ttu-id="02730-541">回應群組代理程式 Live</span><span class="sxs-lookup"><span data-stu-id="02730-541">Response Group Agent Live</span></span>
<span data-ttu-id="02730-542"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="02730-542"><a name="RGAL"> </a></span></span>

<span data-ttu-id="02730-543">回應群組應用程式讓代理人能夠使用內建的 Web 服務來存取有用的即時資訊。</span><span class="sxs-lookup"><span data-stu-id="02730-543">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="02730-544">不幸的是，在應用程式外沒有此資料的圖形視圖。</span><span class="sxs-lookup"><span data-stu-id="02730-544">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="02730-545">回應群組代理程式 Live Resource tool 工具可提供一種簡單的圖形方式，以存取此資訊，並利用即時商務用 Skype 通訊軟體資訊（例如，其他代理程式的存在性）進行增強，以解決此問題。</span><span class="sxs-lookup"><span data-stu-id="02730-545">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>

### <a name="description"></a><span data-ttu-id="02730-546">描述</span><span class="sxs-lookup"><span data-stu-id="02730-546">Description</span></span>

<span data-ttu-id="02730-547">回應群組代理程式 Live 是一種 Windows 應用程式，可提供登入和登出功能，以及一些即時資訊 (例如群組成員資格和目前的呼叫數目，) 回應群組代理程式。</span><span class="sxs-lookup"><span data-stu-id="02730-547">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="02730-548">它應是可從商務用 Skype 存取的「代理群組」頁面的增強版本 (。</span><span class="sxs-lookup"><span data-stu-id="02730-548">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>

### <a name="purpose"></a><span data-ttu-id="02730-549">用途</span><span class="sxs-lookup"><span data-stu-id="02730-549">Purpose</span></span>

<span data-ttu-id="02730-550">回應群組應用程式會對來電進行佇列，然後將來電路由傳送至代理人群組。</span><span class="sxs-lookup"><span data-stu-id="02730-550">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="02730-551">若要對服務叫用的相關決策做出合理決策，代理人可以存取有關其代理群組的即時資訊，例如哪些其他代理程式可用，以及每個佇列中有多少來電等候。</span><span class="sxs-lookup"><span data-stu-id="02730-551">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="02730-552">此資訊最初隻會透過回應群組服務進行存取，可透過回應群組代理程式即時以直觀方式取得。</span><span class="sxs-lookup"><span data-stu-id="02730-552">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

#### <a name="features"></a><span data-ttu-id="02730-553">功能</span><span class="sxs-lookup"><span data-stu-id="02730-553">Features</span></span>

<span data-ttu-id="02730-554">回應群組代理程式 Live tool 是在回應群組服務和商務用 Skype Server 2015 SDK 上建立的。</span><span class="sxs-lookup"><span data-stu-id="02730-554">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="02730-555">它提供回應群組代理程式所提供的資訊和功能 (例如群組成員資格、其他代理程式的狀態，以及等候通話的數目) 。</span><span class="sxs-lookup"><span data-stu-id="02730-555">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="02730-556">下圖顯示回應群組代理程式的主要介面。</span><span class="sxs-lookup"><span data-stu-id="02730-556">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

![回應群組代理程式 Live 工具。](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

<span data-ttu-id="02730-558">下列三個主要功能適用于回應群組代理程式 Live 中的代理程式：</span><span class="sxs-lookup"><span data-stu-id="02730-558">The following three main features are available for agents in Response Group Agent Live:</span></span>

- <span data-ttu-id="02730-559">登**入/登出：** 相反于「代理人群組」頁面 (可從商務用 Skype Server 2015) ，回應群組代理程式 Live 只允許代理程式同時登入或登出所有代理程式群組。</span><span class="sxs-lookup"><span data-stu-id="02730-559">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="02730-560">此應用程式提供三種快速的代理人登入或登出方式：</span><span class="sxs-lookup"><span data-stu-id="02730-560">This application provides three quick ways for agents to sign in or out:</span></span>

  - <span data-ttu-id="02730-561">在應用程式內，按一下登入/簽出 (綠色和紅色) 按鈕。</span><span class="sxs-lookup"><span data-stu-id="02730-561">Click the Sign-in/out (green and red) buttons within the application.</span></span>

  - <span data-ttu-id="02730-562">以滑鼠右鍵按一下系統工作列圖示，然後選取 [登入] 或 [登出]。</span><span class="sxs-lookup"><span data-stu-id="02730-562">Right-click the system tray icon, and select sign in or sign out.</span></span>

  - <span data-ttu-id="02730-563">使用可設定的鍵盤快速鍵。</span><span class="sxs-lookup"><span data-stu-id="02730-563">Using configurable keyboard shortcuts.</span></span>

- <span data-ttu-id="02730-564">**群組成員資格：** 當選中代理人群組時，回應群組代理程式 Live 會在右側窗格中顯示此群組中的代理程式清單。</span><span class="sxs-lookup"><span data-stu-id="02730-564">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="02730-565">如果商務用 Skype Server 2015 與此應用程式在同一部電腦上執行，顯示狀態資訊和連絡人卡片會顯示在 [回應群組代理程式 Live] 中。</span><span class="sxs-lookup"><span data-stu-id="02730-565">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="02730-566">代理程式可以直接從那裡傳送 IM 或呼叫其他代理程式。</span><span class="sxs-lookup"><span data-stu-id="02730-566">Agents can send an IM or call other agents directly from there.</span></span>

- <span data-ttu-id="02730-567">**即時統計資料：** 回應群組代理程式 Live 為所有代理程式群組提供即時統計資料。</span><span class="sxs-lookup"><span data-stu-id="02730-567">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="02730-568">更新頻率為一分鐘。</span><span class="sxs-lookup"><span data-stu-id="02730-568">The update frequency is one minute.</span></span> <span data-ttu-id="02730-569">當回應群組接聽來電時，會在具有目前佇列通話數目的組名旁邊新增視覺指示器。</span><span class="sxs-lookup"><span data-stu-id="02730-569">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="02730-570">在群組上暫停指標也會顯示最長的等待時間。</span><span class="sxs-lookup"><span data-stu-id="02730-570">Pausing the pointer over a group also displays the longest waiting time.</span></span>

### <a name="requirements"></a><span data-ttu-id="02730-571">需求</span><span class="sxs-lookup"><span data-stu-id="02730-571">Requirements</span></span>

<span data-ttu-id="02730-572">回應群組代理程式 Live 需要 .NET Framework 4.0。</span><span class="sxs-lookup"><span data-stu-id="02730-572">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="02730-573">此外，若要利用目前狀態和連絡人卡片功能，必須在本機安裝商務用 Skype (並執行) 。</span><span class="sxs-lookup"><span data-stu-id="02730-573">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>

#### <a name="configuration"></a><span data-ttu-id="02730-574">組態</span><span class="sxs-lookup"><span data-stu-id="02730-574">Configuration</span></span>

<span data-ttu-id="02730-575">回應群組代理程式 Live 可透過應用程式中的 [選項] 對話方塊，自訂為個別喜好設定。</span><span class="sxs-lookup"><span data-stu-id="02730-575">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="02730-576">此外，管理員可以直接編輯 RGAgentLive.exe.config 檔案的 defaultHostAddress 屬性，來定義預設的主機位址。</span><span class="sxs-lookup"><span data-stu-id="02730-576">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="02730-577">下圖說明代理可用於設定主機位址及快速鍵的 [選項] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="02730-577">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="02730-578">按一下主介面右上方的 [選項] 按鈕即可存取此對話方塊。</span><span class="sxs-lookup"><span data-stu-id="02730-578">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

![[回應群組代理程式即時選項] 對話方塊。](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

<span data-ttu-id="02730-580">在回應群組代理程式 Live 設定中，可以自訂下列三個不同的設定：</span><span class="sxs-lookup"><span data-stu-id="02730-580">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

- <span data-ttu-id="02730-581">主機位址：這通常是屬於代理人主集區的網頁集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="02730-581">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="02730-582">在此資訊的背景中，會自動派生確切的回應群組服務位址 (方式是在主機) 之後附加正確路徑。</span><span class="sxs-lookup"><span data-stu-id="02730-582">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

- <span data-ttu-id="02730-583">快捷方式：可以自訂登入/登出的確切快捷方式。</span><span class="sxs-lookup"><span data-stu-id="02730-583">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="02730-584">唯一的限制是兩個快捷方式除了至少要包含另一個按鍵) 之外，都必須包含 "Windows 徽標鍵" 金鑰 (。</span><span class="sxs-lookup"><span data-stu-id="02730-584">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>

- <span data-ttu-id="02730-585">開始使用 Windows：應用程式可以設定為以 Windows 自動啟動。</span><span class="sxs-lookup"><span data-stu-id="02730-585">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

### <a name="examples"></a><span data-ttu-id="02730-586">範例</span><span class="sxs-lookup"><span data-stu-id="02730-586">Examples</span></span>

<span data-ttu-id="02730-587">下圖說明如何使用滑鼠右鍵按一下右窗格中的連絡人，撥打或傳送 IM 給另一個代理。</span><span class="sxs-lookup"><span data-stu-id="02730-587">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

![進行通話或傳送 IM。](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

<span data-ttu-id="02730-589">下圖說明回應群組代理程式 Live 如何顯示目前佇列中的呼叫數目，以及所有來電間的最長等待時間。</span><span class="sxs-lookup"><span data-stu-id="02730-589">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

![查看佇列資訊。](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a><span data-ttu-id="02730-591">摘要</span><span class="sxs-lookup"><span data-stu-id="02730-591">Summary</span></span>

<span data-ttu-id="02730-592">快登入和登出、群組成員資格及基本即時統計資料，都是只會在應用程式從回應群組服務外使用的回應群組代理功能。</span><span class="sxs-lookup"><span data-stu-id="02730-592">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="02730-593">使用 [回應群組代理程式 Live Resource 工具組] 工具，商務用 Skype Server 2015 系統管理員可以使用 Windows 應用程式提供其代理程式，讓他們能夠以更快速且圖形的方式執行工作。</span><span class="sxs-lookup"><span data-stu-id="02730-593">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

## <a name="sefautil"></a><span data-ttu-id="02730-594">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="02730-594">SEFAUtil</span></span>
<span data-ttu-id="02730-595"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="02730-595"><a name="SEFAUtil"> </a></span></span>

<span data-ttu-id="02730-596">SEFAUtil (次要擴充功能啟用) 是一種命令列工具，可讓商務用 Skype Server 2015 通訊軟體管理員和支援人員的代理商設定代理程式震鈴、呼叫轉寄、同時震鈴、小組通話設定，以及代表商務用 Skype Server 2015 使用者的群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="02730-596">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="02730-597">工具也可讓系統管理員查詢特定使用者所發佈的呼叫路由設定。SEFAUtil 工具可讓系統管理員為使用者啟用/停用/修改來電轉接或同時震鈴。</span><span class="sxs-lookup"><span data-stu-id="02730-597">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="02730-598">管理員可以指定目標 (，格式為 SIP URI) 或使用已由使用者所發佈的目標。</span><span class="sxs-lookup"><span data-stu-id="02730-598">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="02730-599">這個工具也可讓系統管理員代表使用者新增或移除代理人或小組通話群組成員。此工具是在 Microsoft 整合通訊 Managed API (UCMA) 3.0 上建立，並且要求系統管理員在 SEFAUtil 的中央管理存放區中建立信任的應用程式。</span><span class="sxs-lookup"><span data-stu-id="02730-599">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>

<span data-ttu-id="02730-600">SEFAUtil (次要擴充功能啟動) 可讓商務用 Skype Server 2015 系統管理員和支援人員的代理商，以商務用 Skype Server 2015 使用者的身分，設定「代理人來電」、「呼叫轉寄」、「同時震鈴」、「小組來電設定」和「群組呼叫挑選」。</span><span class="sxs-lookup"><span data-stu-id="02730-600">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="02730-601">這個工具也可讓系統管理員查詢針對特定使用者所發佈的呼叫路由設定。</span><span class="sxs-lookup"><span data-stu-id="02730-601">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

### <a name="description"></a><span data-ttu-id="02730-602">描述</span><span class="sxs-lookup"><span data-stu-id="02730-602">Description</span></span>

<span data-ttu-id="02730-603">目前的 SEFAUtil 版本只是一個命令列工具;沒有支援的圖形使用者介面。</span><span class="sxs-lookup"><span data-stu-id="02730-603">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="02730-604">此工具是以 Microsoft 整合通訊 Managed API (UCMA) 3.0 為基礎。</span><span class="sxs-lookup"><span data-stu-id="02730-604">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="02730-605">此工具中的功能可讓系統管理員和支援人員執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="02730-605">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

- <span data-ttu-id="02730-606">View a user 的所有通話路由設定 (包括來電轉接、委派、同時震鈴、小組通話和群組通話收取) </span><span class="sxs-lookup"><span data-stu-id="02730-606">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

- <span data-ttu-id="02730-607">啟用/停用/修改來電轉接設定 (包括目的地及無回應計時器) </span><span class="sxs-lookup"><span data-stu-id="02730-607">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

- <span data-ttu-id="02730-608">啟用/停用/修改來電轉接立即設定</span><span class="sxs-lookup"><span data-stu-id="02730-608">Enable/disable/modify call-forwarding immediate configurations</span></span>

- <span data-ttu-id="02730-609">啟用/停用/修改委派設定</span><span class="sxs-lookup"><span data-stu-id="02730-609">Enable/disable/modify delegation settings</span></span>

- <span data-ttu-id="02730-610">啟用/停用/修改小組-通話群組設定</span><span class="sxs-lookup"><span data-stu-id="02730-610">Enable/disable/modify team-call group settings</span></span>

    > [!NOTE]
    > <span data-ttu-id="02730-611">商務用 Skype Server 2015 SEFAUtil 工具的新增功能</span><span class="sxs-lookup"><span data-stu-id="02730-611">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="02730-612">啟用/停用/修改同時震鈴設定 (包括目的地) </span><span class="sxs-lookup"><span data-stu-id="02730-612">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>

    > [!NOTE]
    > <span data-ttu-id="02730-613">商務用 Skype Server 2015 SEFAUtil 工具的新增功能</span><span class="sxs-lookup"><span data-stu-id="02730-613">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="02730-614">啟用/停用/修改群組呼叫收取設定</span><span class="sxs-lookup"><span data-stu-id="02730-614">Enable/disable/modify group call pickup settings</span></span>

    > [!CAUTION]
    > <span data-ttu-id="02730-615">商務用 Skype Server 2015 SEFAUtil 工具的新增功能</span><span class="sxs-lookup"><span data-stu-id="02730-615">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

<span data-ttu-id="02730-616">此工具具有下列限制：</span><span class="sxs-lookup"><span data-stu-id="02730-616">This tool has the following limitations:</span></span>

- <span data-ttu-id="02730-617">僅支援位於商務用 Skype 伺服器集區中的使用者</span><span class="sxs-lookup"><span data-stu-id="02730-617">Supported only for users homed in a Skype for Business Server pool</span></span>

- <span data-ttu-id="02730-618">不支援多個使用者的通話路由設定的大量編輯</span><span class="sxs-lookup"><span data-stu-id="02730-618">Bulk-edit of call routing settings for several users is not supported</span></span>

### <a name="output"></a><span data-ttu-id="02730-619">輸出</span><span class="sxs-lookup"><span data-stu-id="02730-619">Output</span></span>

<span data-ttu-id="02730-620">這個工具目前的版本只會在命令提示字元視窗中提供輸出。</span><span class="sxs-lookup"><span data-stu-id="02730-620">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="02730-621">如需詳細資訊，請參閱本檔稍後的範例一節。</span><span class="sxs-lookup"><span data-stu-id="02730-621">For details, see the Examples section later in this document.</span></span>

### <a name="purpose"></a><span data-ttu-id="02730-622">用途</span><span class="sxs-lookup"><span data-stu-id="02730-622">Purpose</span></span>

<span data-ttu-id="02730-623">以下是一些可能使用此工具的主要案例：</span><span class="sxs-lookup"><span data-stu-id="02730-623">Following are some of the key scenarios where this tool may be used:</span></span>

- <span data-ttu-id="02730-624">王俊元是一種主管，已移至商務用 Skype Server 電話語音。</span><span class="sxs-lookup"><span data-stu-id="02730-624">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="02730-625">他已在現有的 PBX 系統上進行委派。</span><span class="sxs-lookup"><span data-stu-id="02730-625">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="02730-626">在 [移至商務用 Skype Server 2015] 的一部分，管理員可以設定王俊元的路由，以反映其預先存在的委派設定。</span><span class="sxs-lookup"><span data-stu-id="02730-626">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>

- <span data-ttu-id="02730-627">劉愛琳正在行動，意識到她期望來自他客戶的一項重要通話。</span><span class="sxs-lookup"><span data-stu-id="02730-627">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="02730-628">不過，她位於酒店，而且無法存取電腦。</span><span class="sxs-lookup"><span data-stu-id="02730-628">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="02730-629">她撥打説明台，並要求他們將來電轉接給她的行動電話號碼。</span><span class="sxs-lookup"><span data-stu-id="02730-629">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="02730-630">服務台人員可以代表她執行設定。</span><span class="sxs-lookup"><span data-stu-id="02730-630">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

- <span data-ttu-id="02730-631">Joe 在工作時，他們的工作號碼會進入行動語音信箱。不過，在大多數其他位置中看起來似乎正常運作。</span><span class="sxs-lookup"><span data-stu-id="02730-631">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="02730-632">説明台技術人員可以查看 Joe 的路由設定，並探索李先生已設定為行動電話的同時震鈴。</span><span class="sxs-lookup"><span data-stu-id="02730-632">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="02730-633">技術人員會詢問 Joe 有關其辦公室內行動覆蓋率的資訊，並且能夠判斷同時響鈴的規則，也就是當網路服務品質不良的情況時，會導致來電進入 Joe 的行動電話語音信箱。</span><span class="sxs-lookup"><span data-stu-id="02730-633">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>

- <span data-ttu-id="02730-634">Mike 是 Contoso 的新員工，他加入新的小組，所有成員皆為「小組通話」，當啟用商務用 Skype Server 2015 時，系統管理員可以設定他的小組通話群組設定，以包含所有新的小組成員，此外，系統管理員也會新增 Mike 做為小組中每個成員的小組通話群組成員。</span><span class="sxs-lookup"><span data-stu-id="02730-634">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

- <span data-ttu-id="02730-635">在 Contoso 的人力資源部門中，客戶服務實踐是為自第一次呼叫後的所有來電者提供個人服務。</span><span class="sxs-lookup"><span data-stu-id="02730-635">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="02730-636">假設部門的所有成員都非常接近對方，當小組通話同時撥打所有電話時，就會對小組造成中斷。</span><span class="sxs-lookup"><span data-stu-id="02730-636">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="02730-637">若要在不中斷小組成員的情況下提供最佳服務，商務用 Skype Server 2015 系統管理員會利用「群組呼叫收取」功能。</span><span class="sxs-lookup"><span data-stu-id="02730-637">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="02730-638">系統管理員會將所有部門成員新增至收取群組，並與該部門通訊收取群組編號。</span><span class="sxs-lookup"><span data-stu-id="02730-638">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="02730-639">當她的辦公桌沒有 Samantha 時，Joe 會通知她的電話鈴聲，他會繼續接聽他的電話。</span><span class="sxs-lookup"><span data-stu-id="02730-639">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

### <a name="requirements"></a><span data-ttu-id="02730-640">需求</span><span class="sxs-lookup"><span data-stu-id="02730-640">Requirements</span></span>

<span data-ttu-id="02730-641">SEFAUtil 工具只能在屬於受信任應用程式集區一部分的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="02730-641">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="02730-642">UCMA 3.0 必須安裝在該電腦上。</span><span class="sxs-lookup"><span data-stu-id="02730-642">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="02730-643">若要執行此工具，必須在該集區上建立具有 SEFAUtil 應用程式識別碼的新信任應用程式。</span><span class="sxs-lookup"><span data-stu-id="02730-643">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="02730-644">為 SEFAUtil 工具建立新的信任應用程式</span><span class="sxs-lookup"><span data-stu-id="02730-644">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="02730-645">SEFAUTil 工具只能在屬於受信任應用程式集區一部分的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="02730-645">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="02730-646">如有需要，您可以透過商務用 Skype Server 管理命令介面，將集區新增為新的受信任應用程式集區，其 Cmdlet 如下：</span><span class="sxs-lookup"><span data-stu-id="02730-646">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > <span data-ttu-id="02730-647">UCMA 3.0 必須安裝在將用來執行 SEFAUtil 工具的任何電腦上。</span><span class="sxs-lookup"><span data-stu-id="02730-647">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

2. <span data-ttu-id="02730-648">在 SEFAUtil 工具的拓撲中，必須定義信任的應用程式。</span><span class="sxs-lookup"><span data-stu-id="02730-648">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="02730-649">若要將 SEFAUtil 定義為新的受信任應用程式，請使用商務用 Skype Server 管理命令介面，並執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="02730-649">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="02730-650">您可以視需要使用不同的埠。</span><span class="sxs-lookup"><span data-stu-id="02730-650">A different port can be used if needed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="02730-651">集區 FQDN：將主控 SEFAUtil 應用程式之伺服器或集區的 FQDN (通常是商務用 Skype 前端伺服器 > 或集區) 。</span><span class="sxs-lookup"><span data-stu-id="02730-651">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server     > or pool).</span></span>
    > <span data-ttu-id="02730-652">集區註冊機 FQDN：與此應用程式集區相關聯之商務用 Skype 前端伺服器或集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="02730-652">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="02730-653">集區網站：此集區所在之網站的網站識別碼。</span><span class="sxs-lookup"><span data-stu-id="02730-653">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

3. <span data-ttu-id="02730-654">需要啟用拓撲變更。</span><span class="sxs-lookup"><span data-stu-id="02730-654">The topology changes need to be enabled.</span></span> <span data-ttu-id="02730-655">您可以透過執行下列 Cmdlet，透過商務用 Skype Server 管理命令介面來啟用拓撲變更：</span><span class="sxs-lookup"><span data-stu-id="02730-655">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span>

   ```powershell
   Enable-CsToplogy
   ```

4. <span data-ttu-id="02730-656">如有需要，在伺服器上安裝用來執行 SEFAUtil 工具的商務用 Skype Server 2015 資源工具組工具 (伺服器必須是信任的應用程式集區) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="02730-656">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5. <span data-ttu-id="02730-657">驗證 SEFAUtil 是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="02730-657">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="02730-658">若要執行此動作，請從使用管理員許可權的 windows 命令提示字元執行工具，以顯示部署中使用者的「來電轉接」設定。</span><span class="sxs-lookup"><span data-stu-id="02730-658">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="02730-659">依預設，此工具會位於： "..\Program Files\Skype for Business Server 2015 \ Reskit"。</span><span class="sxs-lookup"><span data-stu-id="02730-659">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="02730-660">若要顯示使用者的「來電轉接」設定，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="02730-660">To display the call forwarding settings of a user, use the following command:</span></span>

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    <span data-ttu-id="02730-661">應該顯示使用者的「來電轉接」設定。</span><span class="sxs-lookup"><span data-stu-id="02730-661">The call forwarding settings of the user should be displayed.</span></span>

#### <a name="group-call-pickup"></a><span data-ttu-id="02730-662">群組來電接聽</span><span class="sxs-lookup"><span data-stu-id="02730-662">Group Call Pickup</span></span>

<span data-ttu-id="02730-663">群組呼叫收取需要在商務用 Skype Server 2015 中進行其他設定，才能充分啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="02730-663">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="02730-664">在指派收取群組給使用者之前，請參閱群組的「呼叫收取產品檔」，以取得這項功能的規劃及部署步驟。</span><span class="sxs-lookup"><span data-stu-id="02730-664">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

### <a name="examples"></a><span data-ttu-id="02730-665">範例</span><span class="sxs-lookup"><span data-stu-id="02730-665">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="02730-666">顯示目前的通話處理設定</span><span class="sxs-lookup"><span data-stu-id="02730-666">Display Current Call Handling Settings</span></span>

<span data-ttu-id="02730-667">下列命令會顯示使用者的通話處理。</span><span class="sxs-lookup"><span data-stu-id="02730-667">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> <span data-ttu-id="02730-668">本範例會使用 **/server** 參數來指定要連接的商務用 Skype server。</span><span class="sxs-lookup"><span data-stu-id="02730-668">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>

 <span data-ttu-id="02730-669">**輸出**</span><span class="sxs-lookup"><span data-stu-id="02730-669">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="02730-670">設定來電轉接/無應答目的地</span><span class="sxs-lookup"><span data-stu-id="02730-670">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="02730-671">本範例會設定來電轉寄/無應答目的地和震鈴延遲。</span><span class="sxs-lookup"><span data-stu-id="02730-671">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="02730-672">這裡未提供/server 參數;SEFAUtil 會嘗試自動探索商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="02730-672">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+14255550126@contoso.com;user=phone
```

 <span data-ttu-id="02730-673">**輸出**</span><span class="sxs-lookup"><span data-stu-id="02730-673">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="02730-674">立即啟用來電轉接</span><span class="sxs-lookup"><span data-stu-id="02730-674">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="02730-675">本範例會立即對其他使用者啟用來電轉接。</span><span class="sxs-lookup"><span data-stu-id="02730-675">This example immediately enables call-forwarding to another user.</span></span>

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="02730-676">**輸出**</span><span class="sxs-lookup"><span data-stu-id="02730-676">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="02730-677">立即停用來電轉接</span><span class="sxs-lookup"><span data-stu-id="02730-677">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="02730-678">本範例會立即停用來電轉接。</span><span class="sxs-lookup"><span data-stu-id="02730-678">This example immediately disables call forwarding.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com /disablefwdimmediate
```

 <span data-ttu-id="02730-679">**輸出**</span><span class="sxs-lookup"><span data-stu-id="02730-679">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="02730-680">將使用者新增為代理人，並設定代理人同時震鈴</span><span class="sxs-lookup"><span data-stu-id="02730-680">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="02730-681">這則範例會將使用者新增為代理人，並設定同時響鈴的代理人。</span><span class="sxs-lookup"><span data-stu-id="02730-681">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="02730-682">**輸出**</span><span class="sxs-lookup"><span data-stu-id="02730-682">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="02730-683">變更代理人的同時震鈴規則</span><span class="sxs-lookup"><span data-stu-id="02730-683">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="02730-684">這個範例會將上一個範例中設定的同時震鈴規則變更為延遲的震鈴規則。</span><span class="sxs-lookup"><span data-stu-id="02730-684">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="02730-685">**輸出**</span><span class="sxs-lookup"><span data-stu-id="02730-685">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="02730-686">移除代理人</span><span class="sxs-lookup"><span data-stu-id="02730-686">Remove the Delegate</span></span>

<span data-ttu-id="02730-687">本範例會移除代理人。</span><span class="sxs-lookup"><span data-stu-id="02730-687">This example removes the delegate.</span></span>

> [!NOTE]
> <span data-ttu-id="02730-688">移除最後一個代理人時，會自動停用代理人震鈴。</span><span class="sxs-lookup"><span data-stu-id="02730-688">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="02730-689">**輸出**</span><span class="sxs-lookup"><span data-stu-id="02730-689">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="02730-690">新增代理人並設定對代理人規則的呼叫轉寄</span><span class="sxs-lookup"><span data-stu-id="02730-690">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="02730-691">這則範例會新增代理人，並設定「呼叫轉寄至代理人規則。</span><span class="sxs-lookup"><span data-stu-id="02730-691">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="02730-692">**輸出**</span><span class="sxs-lookup"><span data-stu-id="02730-692">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="02730-693">啟用同時震鈴和設定目的地號碼</span><span class="sxs-lookup"><span data-stu-id="02730-693">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="02730-694">本範例啟用同時震鈴，並設定同時震鈴目的地號碼。</span><span class="sxs-lookup"><span data-stu-id="02730-694">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="02730-695">若要變更已啟用同時震鈴之使用者的同時震鈴目的地數目，請使用/enablesimulring 參數保留該命令，否則將不會變更目的地號碼。</span><span class="sxs-lookup"><span data-stu-id="02730-695">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>

 <span data-ttu-id="02730-696">**輸出**</span><span class="sxs-lookup"><span data-stu-id="02730-696">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="02730-697">停用同時震鈴</span><span class="sxs-lookup"><span data-stu-id="02730-697">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="02730-698">本範例會停用同時震鈴。</span><span class="sxs-lookup"><span data-stu-id="02730-698">This example disables simultaneous ringing.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="02730-699">**輸出**</span><span class="sxs-lookup"><span data-stu-id="02730-699">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="02730-700">新增小組通話的小組成員，並設定同時響鈴至「小組來電成員群組」</span><span class="sxs-lookup"><span data-stu-id="02730-700">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="02730-701">這則範例會將小組成員新增至使用者的「小組通話群組」，並啟用對小組通話群組的同時震鈴。</span><span class="sxs-lookup"><span data-stu-id="02730-701">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="02730-702">將成員新增至使用者的小組通話群組，會自動切換使用者的同時震鈴 settigs，以 simulring 他的小組通話群組。</span><span class="sxs-lookup"><span data-stu-id="02730-702">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>

 <span data-ttu-id="02730-703">**輸出**</span><span class="sxs-lookup"><span data-stu-id="02730-703">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="02730-704">從小組通話群組中移除成員</span><span class="sxs-lookup"><span data-stu-id="02730-704">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="02730-705">此範例會移除使用者之團隊通話群組的小組成員。</span><span class="sxs-lookup"><span data-stu-id="02730-705">This example removes a team member of the team-call group of a user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="02730-706">若要移除的成員是小組通話群組的唯一成員，同時震鈴到小組通話群組將會自動停用。</span><span class="sxs-lookup"><span data-stu-id="02730-706">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>

 <span data-ttu-id="02730-707">**輸出**</span><span class="sxs-lookup"><span data-stu-id="02730-707">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="02730-708">將延遲的環設定為小組通話群組</span><span class="sxs-lookup"><span data-stu-id="02730-708">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="02730-709">本範例會將延遲的環變更為「小組通話群組時間」設定。</span><span class="sxs-lookup"><span data-stu-id="02730-709">This example changes the delayed ring to the team-call group time setting.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="02730-710">**輸出**</span><span class="sxs-lookup"><span data-stu-id="02730-710">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="02730-711">啟用小組通話</span><span class="sxs-lookup"><span data-stu-id="02730-711">Enable Team-Call</span></span>

<span data-ttu-id="02730-712">本範例會為指定的使用者啟用小組通話。</span><span class="sxs-lookup"><span data-stu-id="02730-712">This example enables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="02730-713">如果使用者的小組通話群組沒有成員，將不會啟用小組通話。</span><span class="sxs-lookup"><span data-stu-id="02730-713">If the team-call group of the user has no members, team-call won't be enabled.</span></span>

 <span data-ttu-id="02730-714">**輸出**</span><span class="sxs-lookup"><span data-stu-id="02730-714">**Output**</span></span>

#### <a name="disable-team-call"></a><span data-ttu-id="02730-715">停用小組通話</span><span class="sxs-lookup"><span data-stu-id="02730-715">Disable Team-Call</span></span>

<span data-ttu-id="02730-716">本範例會停用指定使用者的「小組通話」。</span><span class="sxs-lookup"><span data-stu-id="02730-716">This example disables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="02730-717">**輸出**</span><span class="sxs-lookup"><span data-stu-id="02730-717">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="02730-718">啟用群組呼叫收取並指派收取群組給使用者</span><span class="sxs-lookup"><span data-stu-id="02730-718">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="02730-719">這則範例會將收取群組指派給使用者，並啟用群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="02730-719">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="02730-720">**輸出**</span><span class="sxs-lookup"><span data-stu-id="02730-720">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="02730-721">停用組來電收取</span><span class="sxs-lookup"><span data-stu-id="02730-721">Disable Group Call Pickup</span></span>

<span data-ttu-id="02730-722">本範例會停用指定使用者的群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="02730-722">This example disables Group Call Pickup for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="02730-723">當您停用使用者的群組呼叫收取時，指派給使用者的群組號碼不會保留。</span><span class="sxs-lookup"><span data-stu-id="02730-723">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="02730-724">如果您後來想要為該使用者重新啟用群組呼叫收取，您必須使用/enablegrouppickup 參數再次指派群組號碼。</span><span class="sxs-lookup"><span data-stu-id="02730-724">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="02730-725">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="02730-725">SYSPrep.ps1</span></span>
<span data-ttu-id="02730-726"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="02730-726"><a name="SYSPrep"> </a></span></span>

### <a name="description"></a><span data-ttu-id="02730-727">描述</span><span class="sxs-lookup"><span data-stu-id="02730-727">Description</span></span>

<span data-ttu-id="02730-728">SYSPrep.ps1 是一種 Windows PowerShell 腳本，可在您的 Windows Server 2008 作業系統機器上安裝下列商務用 Skype Server 2015 必要條件。</span><span class="sxs-lookup"><span data-stu-id="02730-728">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>

- <span data-ttu-id="02730-729">Microsoft .Net Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="02730-729">Microsoft .Net Framework 4.5</span></span>

- <span data-ttu-id="02730-730">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="02730-730">Microsoft SQL Server Express</span></span>

- <span data-ttu-id="02730-731">Windows Powershell 版本3。0</span><span class="sxs-lookup"><span data-stu-id="02730-731">Windows Powershell version 3.0</span></span>

- <span data-ttu-id="02730-732">Visual c + + 2010 可轉散發元件</span><span class="sxs-lookup"><span data-stu-id="02730-732">Visual C++ 2010 Redistributable</span></span>

- <span data-ttu-id="02730-733">網際網路資訊伺服器更新</span><span class="sxs-lookup"><span data-stu-id="02730-733">Internet Information Server Updates</span></span>

- <span data-ttu-id="02730-734">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="02730-734">Windows Identity Foundation</span></span>

- <span data-ttu-id="02730-735">商務用 Skype Server 2015 核心檔案</span><span class="sxs-lookup"><span data-stu-id="02730-735">Skype for Business Server 2015 Core files</span></span>

  <span data-ttu-id="02730-736">雖然腳本名稱與 Microsoft Windows 作業系統的系統準備工具類似，但它們是不同的。</span><span class="sxs-lookup"><span data-stu-id="02730-736">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="02730-737">此腳本只會為商務用 Skype Server 2015 安裝必要的必要條件。</span><span class="sxs-lookup"><span data-stu-id="02730-737">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="02730-738">安裝這些必要條件後，即可使用 Windows SYSPrep 工具建立伺服器的映射。</span><span class="sxs-lookup"><span data-stu-id="02730-738">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

### <a name="requirements"></a><span data-ttu-id="02730-739">需求</span><span class="sxs-lookup"><span data-stu-id="02730-739">Requirements</span></span>

<span data-ttu-id="02730-740">在執行 SYSPrep.ps1 腳本之前，您必須將必要條件檔案複製到 Windows Server 2008 作業系統電腦上的本機資料夾中 (例如 \*\*D:\Setup) \*\*。</span><span class="sxs-lookup"><span data-stu-id="02730-740">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="02730-741">此資料夾也必須包含商務用 Skype Server 2015 檔案的複本，尤其是 **Setup.exe。**</span><span class="sxs-lookup"><span data-stu-id="02730-741">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="02730-742">您可以從下列位置下載必要檔：</span><span class="sxs-lookup"><span data-stu-id="02730-742">The prerequisite files can be downloaded from the following locations:</span></span>


| <span data-ttu-id="02730-743">**前提**</span><span class="sxs-lookup"><span data-stu-id="02730-743">**Prerequisite**</span></span>                                | <span data-ttu-id="02730-744">**位置**</span><span class="sxs-lookup"><span data-stu-id="02730-744">**Location**</span></span>                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| <span data-ttu-id="02730-745">Microsoft .Net Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="02730-745">Microsoft .Net Framework 4.5</span></span>  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| <span data-ttu-id="02730-746">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="02730-746">Microsoft SQL Server Express 2008 R2</span></span>  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| <span data-ttu-id="02730-747">Windows Powershell 版本3。0</span><span class="sxs-lookup"><span data-stu-id="02730-747">Windows Powershell version 3.0</span></span>  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| <span data-ttu-id="02730-748">Visual c + + 2010 可轉散發元件</span><span class="sxs-lookup"><span data-stu-id="02730-748">Visual C++ 2010 Redistributable</span></span>  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| <span data-ttu-id="02730-749">網際網路資訊伺服器更新</span><span class="sxs-lookup"><span data-stu-id="02730-749">Internet Information Server Updates</span></span>  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| <span data-ttu-id="02730-750">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="02730-750">Windows Identity Foundation</span></span>  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| <span data-ttu-id="02730-751">商務用 Skype Server 2015 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="02730-751">Skype for Business Server 2015 Setup.exe</span></span>  <br/> | <span data-ttu-id="02730-752">從商務用 Skype Server 2015 媒體複製</span><span class="sxs-lookup"><span data-stu-id="02730-752">Copy from Skype for Business Server 2015 media</span></span>  <br/>                   |

### <a name="parameter"></a><span data-ttu-id="02730-753">參數</span><span class="sxs-lookup"><span data-stu-id="02730-753">Parameter</span></span>

<span data-ttu-id="02730-754">**-SetupFolder**參數會將必要條件檔案的目錄位置當作引數。</span><span class="sxs-lookup"><span data-stu-id="02730-754">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

### <a name="examples"></a><span data-ttu-id="02730-755">範例</span><span class="sxs-lookup"><span data-stu-id="02730-755">Examples</span></span>

<span data-ttu-id="02730-756">若要執行 SYSPrep.ps1 腳本，並安裝商務用 Skype Server 2015 必要條件，請從提升許可權的命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="02730-756">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="02730-757">未指派號碼宣告遷移</span><span class="sxs-lookup"><span data-stu-id="02730-757">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="02730-758"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="02730-758"><a name="UNAM"> </a></span></span>

<span data-ttu-id="02730-759">未指派號碼宣告遷移工具可讓商務用 Skype Server 2015 系統管理員將宣告應用程式所提供的未指派號碼設定從來源商務用 Skype Server 或集區移至目的地商務用 Skype 伺服器或集區。</span><span class="sxs-lookup"><span data-stu-id="02730-759">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>

### <a name="description"></a><span data-ttu-id="02730-760">描述</span><span class="sxs-lookup"><span data-stu-id="02730-760">Description</span></span>

<span data-ttu-id="02730-761">未指派號碼宣告遷移工具是一種 Windows PowerShell 腳本，可將來源伺服器或集區之宣告應用程式所提供的未指派號碼設定移至不同的伺服器或集區。</span><span class="sxs-lookup"><span data-stu-id="02730-761">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="02730-762">執行時，未指派的號碼宣告遷移腳本會執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="02730-762">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1. <span data-ttu-id="02730-763">將來源伺服器或集區中主控之宣告應用程式的未指派號碼宣告所使用的所有音訊檔，移至目的地伺服器或集區的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="02730-763">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="02730-764">將音訊檔複製到目的地集區之後，會從來源集區中移除。</span><span class="sxs-lookup"><span data-stu-id="02730-764">The audio files are removed from the source pool once they're copied to the destination pool.</span></span>

2. <span data-ttu-id="02730-765">將來源伺服器或集區中主控的宣告應用程式設定的所有未指派號碼的宣告移至目的地伺服器或集區。</span><span class="sxs-lookup"><span data-stu-id="02730-765">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3. <span data-ttu-id="02730-766">將來源伺服器或集區中主控的宣告應用程式所提供的所有未指派號碼範圍重新指派給目的地伺服器或集區。</span><span class="sxs-lookup"><span data-stu-id="02730-766">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="02730-767">順利執行腳本後，來源伺服器或集區中所主控的宣告應用程式所提供的所有未指派號碼範圍，都將會以目標伺服器或集區的相同設定進行服務。</span><span class="sxs-lookup"><span data-stu-id="02730-767">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

### <a name="output"></a><span data-ttu-id="02730-768">輸出</span><span class="sxs-lookup"><span data-stu-id="02730-768">Output</span></span>

<span data-ttu-id="02730-769">**Move-CsAnnouncementConfiguration**腳本會指出商務用 Skype Server 管理命令介面視窗，從該視窗執行遷移作業的成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="02730-769">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="02730-770">如果執行作業時因任何錯誤而中斷，已順利移至目的地的未指派號碼範圍仍會保留在操作表單的目的地中，而且其他未指派的號碼範圍仍會保留在來源中，也就是在運作表單中。</span><span class="sxs-lookup"><span data-stu-id="02730-770">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="02730-771">若要完全遷移其他設定，請在解決錯誤之後重新執行腳本。</span><span class="sxs-lookup"><span data-stu-id="02730-771">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

### <a name="purpose"></a><span data-ttu-id="02730-772">用途</span><span class="sxs-lookup"><span data-stu-id="02730-772">Purpose</span></span>

<span data-ttu-id="02730-773">未指派號碼宣告遷移腳本可用於下列三種情況：</span><span class="sxs-lookup"><span data-stu-id="02730-773">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

- <span data-ttu-id="02730-774">**將設定設定遷移至新版本的商務用 Skype Server：** Contoso 正在遷移至商務用 Skype Server 2015，並做為遷移程式的一部分，商務用 Skype 伺服器管理員想要將宣告應用程式所提供的未指派號碼設定從 Lync Server 2013 部署移至新的商務用 Skype Server 2015 部署。</span><span class="sxs-lookup"><span data-stu-id="02730-774">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="02730-775">若要移動設定設定，商務用 Skype 伺服器管理員使用「未指派的號碼宣告遷移」工具。</span><span class="sxs-lookup"><span data-stu-id="02730-775">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

- <span data-ttu-id="02730-776">**從商務用 Skype server 2015 復原部署至 Lync Server 2013：** 由於非預期的因素，Contoso 必須將遷移移至新的商務用 Skype Server 2015 部署。</span><span class="sxs-lookup"><span data-stu-id="02730-776">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="02730-777">為使服務中斷降至最低，商務用 Skype 伺服器管理員使用「未指派的號碼宣告遷移」工具，將設定從商務用 Skype Server 2015 部署復原為 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="02730-777">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>

- <span data-ttu-id="02730-778">**在部署之間移動資料：** Contoso 正在將一個集區的所有伺服器取代為更新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="02730-778">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="02730-779">其策略是部署新的商務用 Skype Server 2015 集區，將舊資料從舊集區移至新集區，然後取代舊的集區。</span><span class="sxs-lookup"><span data-stu-id="02730-779">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="02730-780">部署新集區之後，就會使用「未指派號碼宣告」遷移工具，將設定從舊集區移至新集區。</span><span class="sxs-lookup"><span data-stu-id="02730-780">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

#### <a name="requirements"></a><span data-ttu-id="02730-781">需求</span><span class="sxs-lookup"><span data-stu-id="02730-781">Requirements</span></span>

<span data-ttu-id="02730-782">以下是成功執行工具所需的主要需求：</span><span class="sxs-lookup"><span data-stu-id="02730-782">The following are the main requirements needed to successfully run the tool:</span></span>

1. <span data-ttu-id="02730-783">必須在已安裝商務用 Skype Server 管理命令介面的電腦上執行該腳本。</span><span class="sxs-lookup"><span data-stu-id="02730-783">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>

2. <span data-ttu-id="02730-784">必須在來源和目的地商務用 Skype 伺服器或集區中成功部署宣告應用程式。</span><span class="sxs-lookup"><span data-stu-id="02730-784">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>

#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="02730-785">Move-CsAnnouncementConfiguration 腳本</span><span class="sxs-lookup"><span data-stu-id="02730-785">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="02730-786">Move-CsAnnouncementConfiguration 腳本需要下表中所述的兩個參數。</span><span class="sxs-lookup"><span data-stu-id="02730-786">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

![Move-CsAnnouncementConfiguration 參數。](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a><span data-ttu-id="02730-788">範例</span><span class="sxs-lookup"><span data-stu-id="02730-788">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="02730-789">將未指派號碼的宣告設定從 Lync Server 2013 集區移至商務用 Skype Server 2015 集區</span><span class="sxs-lookup"><span data-stu-id="02730-789">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="02730-790">這個範例會將來源集區中未指派的號碼宣告 (Lync Server 2013) ，移至目的地集區 (商務用 Skype Server 2015) 。</span><span class="sxs-lookup"><span data-stu-id="02730-790">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="02730-791">將未指派號碼的宣告設定從商務用 Skype Server 2015 集區移至 Lync Server 2013 集區</span><span class="sxs-lookup"><span data-stu-id="02730-791">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="02730-792">這則範例會將來源集區的未指派號碼宣告從來源集區 (商務用 Skype Server 2015) ，移至目的地集區 (Lync Server 2013) 。</span><span class="sxs-lookup"><span data-stu-id="02730-792">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="02730-793">網路會議資料</span><span class="sxs-lookup"><span data-stu-id="02730-793">Web Conf Data</span></span>
<span data-ttu-id="02730-794"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="02730-794"><a name="WebConfData"> </a></span></span>

<span data-ttu-id="02730-795">Web 會議資料工具可讓商務用 Skype Server 2015 通訊軟體的系統管理員，對與召集人的 Web 會議相關聯的資料進行更多控制。</span><span class="sxs-lookup"><span data-stu-id="02730-795">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="02730-796">案例包括根據時間戳記準則刪除特定使用者的會議資料的功能。</span><span class="sxs-lookup"><span data-stu-id="02730-796">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>

### <a name="description"></a><span data-ttu-id="02730-797">描述</span><span class="sxs-lookup"><span data-stu-id="02730-797">Description</span></span>

<span data-ttu-id="02730-798">此工具可讓系統管理員執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="02730-798">This tool allows the administrator to perform the following operations:</span></span>

1. <span data-ttu-id="02730-799">尋找與單一使用者相關聯的所有 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="02730-799">Find all Web conferencing data associated with a single user.</span></span>

2. <span data-ttu-id="02730-800">刪除所有與單一使用者相關聯的 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="02730-800">Delete all Web conferencing data associated with a single user.</span></span>

3. <span data-ttu-id="02730-801">刪除與特定日期舊的單一使用者相關聯的所有 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="02730-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4. <span data-ttu-id="02730-802">當使用者從一個集區移至另一個集區時，移動所有與單一使用者相關聯的 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="02730-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

    > [!NOTE]
    > <span data-ttu-id="02730-803">Lync Server 2010 的資源工具組工具支援在使用者從一個集區移至另一個集區時，移動所有與單一使用者相關聯的 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="02730-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="02730-804">這項功能現在已被取代為此工具，取而代之的 **MoveConferenceData** 參數。</span><span class="sxs-lookup"><span data-stu-id="02730-804">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="02730-805">如需此參數的詳細資訊，請參閱 [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="02730-805">For details about this parameter, see the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="02730-806">工具只會刪除非使用中會議的會議資料。</span><span class="sxs-lookup"><span data-stu-id="02730-806">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="02730-807">無法刪除會話) 中的使用中會議 (或會議。</span><span class="sxs-lookup"><span data-stu-id="02730-807">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="02730-808">此工具必須從與目標使用者位於相同集區的電腦執行。</span><span class="sxs-lookup"><span data-stu-id="02730-808">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="02730-809">使用此工具管理其會議內容資料的使用者，必須位於相同的使用者集區中。</span><span class="sxs-lookup"><span data-stu-id="02730-809">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

### <a name="output"></a><span data-ttu-id="02730-810">輸出</span><span class="sxs-lookup"><span data-stu-id="02730-810">Output</span></span>

<span data-ttu-id="02730-811">此工具會輸出各項作業的結果：</span><span class="sxs-lookup"><span data-stu-id="02730-811">This tool outputs the results of each of the operations:</span></span>

- <span data-ttu-id="02730-812">如果執行查詢，則該工具會將所有非使用中會議資料檔案夾的清單，輸出為召集人。</span><span class="sxs-lookup"><span data-stu-id="02730-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

- <span data-ttu-id="02730-813">若執行刪除，該工具會輸出其資料將被刪除的所有會議資料資料夾清單。</span><span class="sxs-lookup"><span data-stu-id="02730-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

### <a name="requirements"></a><span data-ttu-id="02730-814">需求</span><span class="sxs-lookup"><span data-stu-id="02730-814">Requirements</span></span>

<span data-ttu-id="02730-815">需要在召集人目前所在的相同集區中執行工具。</span><span class="sxs-lookup"><span data-stu-id="02730-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="02730-816">您必須使用管理員許可權執行該工具，才能存取內容檔存放區。</span><span class="sxs-lookup"><span data-stu-id="02730-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

### <a name="examples"></a><span data-ttu-id="02730-817">範例</span><span class="sxs-lookup"><span data-stu-id="02730-817">Examples</span></span>

<span data-ttu-id="02730-818">下表說明這些參數，其中一些是範例中使用的參數。</span><span class="sxs-lookup"><span data-stu-id="02730-818">The following table describes the parameters, some of which are used in the examples.</span></span>

![Web 會議資料工具參數。](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="02730-820">上述範例顯示查詢命令的運作方式。</span><span class="sxs-lookup"><span data-stu-id="02730-820">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="02730-821">這類命令的輸出會是受此工具影響的所有會議內容資料夾清單。</span><span class="sxs-lookup"><span data-stu-id="02730-821">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="02730-822">上述為刪除命令的範例。</span><span class="sxs-lookup"><span data-stu-id="02730-822">The preceding is an example of a delete command.</span></span> <span data-ttu-id="02730-823">[刪除] 命令將從此使用者移除所有非使用中的會議資料夾。</span><span class="sxs-lookup"><span data-stu-id="02730-823">The delete command will remove all inactive meeting folders from this user.</span></span>

### <a name="summary"></a><span data-ttu-id="02730-824">摘要</span><span class="sxs-lookup"><span data-stu-id="02730-824">Summary</span></span>

<span data-ttu-id="02730-825">對於需要更精確控制會議會議資料的系統管理員，此工具是一種重要資源。</span><span class="sxs-lookup"><span data-stu-id="02730-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>



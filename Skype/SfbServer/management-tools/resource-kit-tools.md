---
title: 商務用 Skype Server 2015 資源套件工具檔
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: 本文說明商務用 Skype Server 2015 資源套件中的工具，包含每個工具的目的，以及其用途的範例。 商務用 Skype Server 2015 資源套件可協助 IT 系統管理員部署及管理商務用 Skype Server 2015，使日常工作變得更容易。 例如，網路會議資料工具可以用來輕鬆控制使用者在線上會議期間上傳的資料。 SEFAUtil 工具可以用來設定使用者的代理人來電轉接和應答。 我們鼓勵 IT 管理員使用這些工具更有效率地管理商務用 Skype Server 2015。
ms.openlocfilehash: 6c68a94d331f2ad5f9ffaa169228aa9d64e41293
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52629042"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="caac7-107">商務用 Skype Server 2015 資源套件工具檔</span><span class="sxs-lookup"><span data-stu-id="caac7-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>

<span data-ttu-id="caac7-108">本文說明商務用 Skype Server 2015 資源套件中的工具，包含每個工具的目的，以及其用途的範例。</span><span class="sxs-lookup"><span data-stu-id="caac7-108">This article describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="caac7-109">商務用 Skype Server 2015 資源套件可協助 IT 系統管理員部署及管理商務用 Skype Server 2015，使日常工作變得更容易。</span><span class="sxs-lookup"><span data-stu-id="caac7-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="caac7-110">例如，網路會議 **資料** 工具可以用來輕鬆控制使用者在線上會議期間上傳的資料。</span><span class="sxs-lookup"><span data-stu-id="caac7-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="caac7-111">**SEFAUtil** 工具可以用來設定使用者的代理人來電轉接和應答。</span><span class="sxs-lookup"><span data-stu-id="caac7-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="caac7-112">我們鼓勵 IT 管理員使用這些工具更有效率地管理商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="caac7-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="caac7-113">安裝資源工具組工具</span><span class="sxs-lookup"><span data-stu-id="caac7-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="caac7-114">若要安裝商務用 Skype Server 2015 資源套件，請從下載中心下載[OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) 。</span><span class="sxs-lookup"><span data-stu-id="caac7-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) from the Download Center.</span></span>

<span data-ttu-id="caac7-115">執行 **OCSResKit.msi** 以執行簡單安裝。</span><span class="sxs-lookup"><span data-stu-id="caac7-115">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="caac7-116">.msi 會安裝下列路徑中的所有工具： **% Program Files% \ 商務用 Skype Server 2015 \ ResKit**。</span><span class="sxs-lookup"><span data-stu-id="caac7-116">The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**.</span></span> <span data-ttu-id="caac7-117">屬於自包含可執行檔的工具位於此資料夾中。</span><span class="sxs-lookup"><span data-stu-id="caac7-117">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="caac7-118">也有支援檔案的工具位於自己的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="caac7-118">Tools that also have supporting files are in their own subfolders.</span></span>

## <a name="supported-environments"></a><span data-ttu-id="caac7-119">支援的環境</span><span class="sxs-lookup"><span data-stu-id="caac7-119">Supported Environments</span></span>

<span data-ttu-id="caac7-120">商務用 Skype Server 2015 資源套件應該安裝在符合商務用 Skype Server 2015 所需規格的伺服器上，通常是用來執行商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="caac7-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="caac7-121">資源工具組工具概述</span><span class="sxs-lookup"><span data-stu-id="caac7-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="caac7-122">以下是商務用 Skype Server 2015 資源套件中所提供的工具清單。</span><span class="sxs-lookup"><span data-stu-id="caac7-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="caac7-123">下列各節涵蓋每個工具的描述（包括需求和範例用法）。</span><span class="sxs-lookup"><span data-stu-id="caac7-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>

- [<span data-ttu-id="caac7-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="caac7-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)

- [<span data-ttu-id="caac7-125">頻寬原則服務監視器</span><span class="sxs-lookup"><span data-stu-id="caac7-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)

- [<span data-ttu-id="caac7-126">頻寬流量分析程式</span><span class="sxs-lookup"><span data-stu-id="caac7-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)

- [<span data-ttu-id="caac7-127">呼叫 Call parkometer</span><span class="sxs-lookup"><span data-stu-id="caac7-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)

- [<span data-ttu-id="caac7-128">Dbanalyze.exe</span><span class="sxs-lookup"><span data-stu-id="caac7-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)

- [<span data-ttu-id="caac7-129">匯入儲存體服務資料</span><span class="sxs-lookup"><span data-stu-id="caac7-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)

- [<span data-ttu-id="caac7-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="caac7-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)

- [<span data-ttu-id="caac7-131">查閱使用者主控台</span><span class="sxs-lookup"><span data-stu-id="caac7-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)

- [<span data-ttu-id="caac7-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="caac7-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)

- [<span data-ttu-id="caac7-133">網路設定檢視器</span><span class="sxs-lookup"><span data-stu-id="caac7-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)

- [<span data-ttu-id="caac7-134">回應群組代理程式 Live</span><span class="sxs-lookup"><span data-stu-id="caac7-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)

- [<span data-ttu-id="caac7-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="caac7-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)

- [<span data-ttu-id="caac7-136">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="caac7-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)

- [<span data-ttu-id="caac7-137">未指派號碼宣告遷移</span><span class="sxs-lookup"><span data-stu-id="caac7-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)

- [<span data-ttu-id="caac7-138">網路會議資料</span><span class="sxs-lookup"><span data-stu-id="caac7-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a><span data-ttu-id="caac7-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="caac7-139">ABSConfig</span></span>
<span data-ttu-id="caac7-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="caac7-140"><a name="ABSConfig"> </a></span></span>

<span data-ttu-id="caac7-141">通訊錄服務設定工具 (ABSConfig) 是一種系統管理工具，可協助系統管理員自訂商務用 Skype Server 2015 中的通訊錄服務設定。</span><span class="sxs-lookup"><span data-stu-id="caac7-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="caac7-142">此工具也可讓商務用 Skype Server 2015 系統管理員還原預設通訊錄服務設定。</span><span class="sxs-lookup"><span data-stu-id="caac7-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>

### <a name="description"></a><span data-ttu-id="caac7-143">描述</span><span class="sxs-lookup"><span data-stu-id="caac7-143">Description</span></span>

<span data-ttu-id="caac7-144">ABSConfig 是一種圖形使用者介面應用程式，可讓系統管理員設定與通訊錄服務相關的 Active Directory 網域服務屬性。</span><span class="sxs-lookup"><span data-stu-id="caac7-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="caac7-145">工具的主要案例如下：</span><span class="sxs-lookup"><span data-stu-id="caac7-145">The primary scenarios for the tool are the following:</span></span>

- <span data-ttu-id="caac7-146">讓系統管理員能夠將 Active Directory 網域服務中的屬性對應至商務用 Skype Server 2015 的屬性。</span><span class="sxs-lookup"><span data-stu-id="caac7-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>

- <span data-ttu-id="caac7-147">讓系統管理員指定要在通訊錄服務檔案中包含或排除的 Active Directory 網域服務屬性。</span><span class="sxs-lookup"><span data-stu-id="caac7-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

- <span data-ttu-id="caac7-148">若要讓系統管理員能夠還原，請預設的通訊錄服務設定。</span><span class="sxs-lookup"><span data-stu-id="caac7-148">To enable administrators to restore,  default Address Book Service settings.</span></span>

<span data-ttu-id="caac7-149">您可以使用 ABSConfig.exe 檔啟動 ABSConfig 工具。</span><span class="sxs-lookup"><span data-stu-id="caac7-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="caac7-150">工具隨即開啟至 [**設定屬性**] 索引標籤。此表格中的選項可將 Active Directory 網域服務屬性對應至商務用 Skype Server 2015 的屬性欄位，並指定哪些使用者在通訊錄服務檔案中包含或排除根據特定的屬性篩選器。</span><span class="sxs-lookup"><span data-stu-id="caac7-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="caac7-151">也可以選擇自訂要包含在通訊錄檔案中的電話號碼值。</span><span class="sxs-lookup"><span data-stu-id="caac7-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="caac7-152">[ **還原預設** 值] 選項可讓系統管理員將通訊錄服務設定還原為預設值。</span><span class="sxs-lookup"><span data-stu-id="caac7-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

> [!NOTE]
> <span data-ttu-id="caac7-153">將 AD 屬性重新對應至不同的 OC 功能變數名稱只會在通訊錄檔案下載時運作，且不受通訊錄 Web 查詢的支援。</span><span class="sxs-lookup"><span data-stu-id="caac7-153">Re-mapping of AD attributes to different OC Field Names will only work for Address Book File Download, and is not supported by Address Book Web Query.</span></span>

### <a name="output"></a><span data-ttu-id="caac7-154">輸出</span><span class="sxs-lookup"><span data-stu-id="caac7-154">Output</span></span>

<span data-ttu-id="caac7-155">ABSConfig 會將通訊錄服務設定儲存在資料庫中。</span><span class="sxs-lookup"><span data-stu-id="caac7-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="caac7-156">用途</span><span class="sxs-lookup"><span data-stu-id="caac7-156">Purpose</span></span>

<span data-ttu-id="caac7-157">ABSConfig 提供一種快速快捷的方式，可自訂商務用 Skype Server 2015 通訊錄服務。</span><span class="sxs-lookup"><span data-stu-id="caac7-157">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>

### <a name="requirements"></a><span data-ttu-id="caac7-158">需求</span><span class="sxs-lookup"><span data-stu-id="caac7-158">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="caac7-159">電腦</span><span class="sxs-lookup"><span data-stu-id="caac7-159">Computer</span></span>

<span data-ttu-id="caac7-160">ABSConfig 只能從已安裝商務用 Skype Server 2015 的已加入網域的電腦執行。</span><span class="sxs-lookup"><span data-stu-id="caac7-160">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="caac7-161">在商務用 Skype Server 2015 的情況下 Enterprise Edition，此工具可以在安裝期間啟用通訊錄服務的任何 Front-End 伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="caac7-161">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front-End servers that have the Address Book Service enabled during setup.</span></span>

#### <a name="network"></a><span data-ttu-id="caac7-162">網路</span><span class="sxs-lookup"><span data-stu-id="caac7-162">Network</span></span>

<span data-ttu-id="caac7-163">電腦應該可以連接至 Front-End 集區和後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="caac7-163">The computer should be able to connect to the Front-End pool and back-end database.</span></span>

#### <a name="software"></a><span data-ttu-id="caac7-164">軟體</span><span class="sxs-lookup"><span data-stu-id="caac7-164">Software</span></span>

<span data-ttu-id="caac7-165">在執行 ABSConfig 工具之前，必須先安裝下列軟體元件：</span><span class="sxs-lookup"><span data-stu-id="caac7-165">The following software components must be installed before running the ABSConfig tool:</span></span>

- <span data-ttu-id="caac7-166">商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="caac7-166">Skype for Business Server 2015</span></span>

#### <a name="users"></a><span data-ttu-id="caac7-167">使用者</span><span class="sxs-lookup"><span data-stu-id="caac7-167">Users</span></span>

<span data-ttu-id="caac7-168">具備更新商務用 Skype Server 2015 部署所需之許可權的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="caac7-168">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>

### <a name="examples"></a><span data-ttu-id="caac7-169">範例</span><span class="sxs-lookup"><span data-stu-id="caac7-169">Examples</span></span>

<span data-ttu-id="caac7-170">您可以在命令提示字元處輸入 **ABSConfig.exe** ，以啟動 ABSConfig。</span><span class="sxs-lookup"><span data-stu-id="caac7-170">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="caac7-171">如下所示為 ABSConfig 工具使用者介面。</span><span class="sxs-lookup"><span data-stu-id="caac7-171">Shown below is the ABSConfig tool user interface.</span></span>

![ABSConfig.exe 工具。](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a><span data-ttu-id="caac7-173">摘要</span><span class="sxs-lookup"><span data-stu-id="caac7-173">Summary</span></span>

<span data-ttu-id="caac7-174">ABSConfig 工具可讓系統管理員快速快捷地使用工具，以自訂商務用 Skype Server 2015 通訊錄服務。</span><span class="sxs-lookup"><span data-stu-id="caac7-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="caac7-175">頻寬原則服務監視器</span><span class="sxs-lookup"><span data-stu-id="caac7-175">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="caac7-176"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="caac7-176"><a name="bpsm"> </a></span></span>

<span data-ttu-id="caac7-177">「頻寬原則服務監視」工具的目的是讓系統管理員可以查看下列專案的清單：</span><span class="sxs-lookup"><span data-stu-id="caac7-177">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1. <span data-ttu-id="caac7-178">拓撲中所有設定的商務用 Skype Server 2015 頻寬原則服務 (驗證與核心) </span><span class="sxs-lookup"><span data-stu-id="caac7-178">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2. <span data-ttu-id="caac7-179">每個服務對其他頻寬原則服務和 Edge server 所進行的連接</span><span class="sxs-lookup"><span data-stu-id="caac7-179">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3. <span data-ttu-id="caac7-180">網路設定檔中所設定的所有連結，以及每個頻寬原則服務所報告的即時頻寬使用量</span><span class="sxs-lookup"><span data-stu-id="caac7-180">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

### <a name="description"></a><span data-ttu-id="caac7-181">描述</span><span class="sxs-lookup"><span data-stu-id="caac7-181">Description</span></span>

<span data-ttu-id="caac7-182">頻寬原則服務監視工具是以 GUI 型應用程式的形式來執行。</span><span class="sxs-lookup"><span data-stu-id="caac7-182">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="caac7-183">管理員會透過執行 PDPMonUI.exe 來啟動工具。</span><span class="sxs-lookup"><span data-stu-id="caac7-183">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="caac7-184">當工具開始時，它會嘗試探索拓撲中的頻寬原則服務清單。</span><span class="sxs-lookup"><span data-stu-id="caac7-184">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="caac7-185">完成初始更新後，視窗左側的窗格會以所隸屬的群組為群組的服務清單填入。</span><span class="sxs-lookup"><span data-stu-id="caac7-185">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="caac7-186">當管理員選擇特定頻寬原則服務時，右側窗格會顯示該特定服務的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="caac7-186">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="caac7-187">該窗格也有兩個主要索引標籤可顯示資訊。</span><span class="sxs-lookup"><span data-stu-id="caac7-187">That pane also has two main tabs that display information.</span></span>

#### <a name="machine-info-tab"></a><span data-ttu-id="caac7-188">電腦資訊] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="caac7-188">Machine Info Tab</span></span>

<span data-ttu-id="caac7-189">[ **機器資訊** ] 索引標籤會顯示所選頻寬原則服務的詳細資料，以及選取的頻寬原則服務對其他服務所做的所有連線清單和狀態。</span><span class="sxs-lookup"><span data-stu-id="caac7-189">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

#### <a name="topology-info-tab"></a><span data-ttu-id="caac7-190">拓撲資訊] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="caac7-190">Topology Info Tab</span></span>

<span data-ttu-id="caac7-191">**拓撲資訊** 索引標籤顯示網路設定中所設定之所有連結的清單。</span><span class="sxs-lookup"><span data-stu-id="caac7-191">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="caac7-192">針對每個連結，會顯示音訊和影片頻寬容量。</span><span class="sxs-lookup"><span data-stu-id="caac7-192">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="caac7-193">此外，目前使用的頻寬會顯示，以 Kbps 為單位的容量百分比顯示。</span><span class="sxs-lookup"><span data-stu-id="caac7-193">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="caac7-194">工具使用色彩編碼，強調具有接近容量之使用率的連結，這可讓系統管理員快速隔離這類連結。</span><span class="sxs-lookup"><span data-stu-id="caac7-194">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

> [!NOTE]
>  <span data-ttu-id="caac7-195">如果頻寬原則服務監視工具在連線至任何設定的頻寬原則服務時失敗，將不會填入 **機器資訊** 和 **拓撲資訊** 索引標籤中的資訊。</span><span class="sxs-lookup"><span data-stu-id="caac7-195">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="caac7-196">不過，此工具最初可能會連線，但後來會失去與服務的連線。</span><span class="sxs-lookup"><span data-stu-id="caac7-196">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="caac7-197">在這種情況下，系統管理員可能會看到過時的資訊。</span><span class="sxs-lookup"><span data-stu-id="caac7-197">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="caac7-198">每個索引標籤上都有最後一次 **更新** 的時間戳記，可讓系統管理員看到上次更新特定頻寬原則服務的資料的時間。</span><span class="sxs-lookup"><span data-stu-id="caac7-198">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>

### <a name="output"></a><span data-ttu-id="caac7-199">輸出</span><span class="sxs-lookup"><span data-stu-id="caac7-199">Output</span></span>

<span data-ttu-id="caac7-200">無命令列輸出;程式輸出包含在主要圖形使用者介面 (GUI) 中。</span><span class="sxs-lookup"><span data-stu-id="caac7-200">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

### <a name="purpose"></a><span data-ttu-id="caac7-201">用途</span><span class="sxs-lookup"><span data-stu-id="caac7-201">Purpose</span></span>

<span data-ttu-id="caac7-202">「頻寬原則服務監視」工具的目的是讓系統管理員能看到拓撲中所定義的每個頻寬原則服務的狀態。</span><span class="sxs-lookup"><span data-stu-id="caac7-202">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="caac7-203">此外，系統管理員可以查看網路設定檔中所定義之所有連結的即時頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="caac7-203">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

### <a name="requirements"></a><span data-ttu-id="caac7-204">需求</span><span class="sxs-lookup"><span data-stu-id="caac7-204">Requirements</span></span>

<span data-ttu-id="caac7-205">[！注意] 在屬於商務用 Skype Server 拓撲的電腦上，頻寬原則服務監視器工具必須執行。</span><span class="sxs-lookup"><span data-stu-id="caac7-205">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>

### <a name="summary"></a><span data-ttu-id="caac7-206">摘要</span><span class="sxs-lookup"><span data-stu-id="caac7-206">Summary</span></span>

<span data-ttu-id="caac7-207">頻寬原則服務監視器工具對管理員來說可能是一項寶貴資源，讓他們能夠檢查拓撲中所有頻寬原則服務的狀態，更重要的是，他們可以取得網路設定設定中所定義之連結的即時頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="caac7-207">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="caac7-208">頻寬流量分析程式</span><span class="sxs-lookup"><span data-stu-id="caac7-208">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="caac7-209"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="caac7-209"><a name="bua"> </a></span></span>

<span data-ttu-id="caac7-210">頻寬流量分析程式是一種工具，它會針對商業網路中 WAN 連結的 UC 端點，建立各種頻寬使用量的報告。</span><span class="sxs-lookup"><span data-stu-id="caac7-210">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="caac7-211">這些報告可用於瞭解目前的頻寬消耗模式，以及協助進行頻寬容量規劃。</span><span class="sxs-lookup"><span data-stu-id="caac7-211">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

### <a name="description"></a><span data-ttu-id="caac7-212">描述</span><span class="sxs-lookup"><span data-stu-id="caac7-212">Description</span></span>

<span data-ttu-id="caac7-213">頻寬使用量分析器是以 GUI 型應用程式的形式來執行。</span><span class="sxs-lookup"><span data-stu-id="caac7-213">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="caac7-214">這個工具專為網路上的音訊使用量產生報告，並協助進行容量規劃。</span><span class="sxs-lookup"><span data-stu-id="caac7-214">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="caac7-215">它也會在指派給各種連結的頻寬容量上進行迴圈。</span><span class="sxs-lookup"><span data-stu-id="caac7-215">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

### <a name="output"></a><span data-ttu-id="caac7-216">輸出</span><span class="sxs-lookup"><span data-stu-id="caac7-216">Output</span></span>

<span data-ttu-id="caac7-217">頻寬使用狀況分析器提供系統中所設定之所有 WAN 連結的頻寬容量及音訊使用方式的圖形圖形。</span><span class="sxs-lookup"><span data-stu-id="caac7-217">Bandwidth Utilization Analyzer provides graphical plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

### <a name="purpose"></a><span data-ttu-id="caac7-218">用途</span><span class="sxs-lookup"><span data-stu-id="caac7-218">Purpose</span></span>

<span data-ttu-id="caac7-219">在任何語音和影片部署中，監控和瞭解整個商業網路中媒體流量的頻寬利用率，都很重要。</span><span class="sxs-lookup"><span data-stu-id="caac7-219">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="caac7-220">頻寬使用狀況分析工具可讓系統管理員只取得這種方式。</span><span class="sxs-lookup"><span data-stu-id="caac7-220">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="caac7-221">此工具會執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="caac7-221">This tool does the following:</span></span>

- <span data-ttu-id="caac7-222">針對整個網路產生音訊使用量的特定報告</span><span class="sxs-lookup"><span data-stu-id="caac7-222">Generates specific reports for audio utilization across the network</span></span>

- <span data-ttu-id="caac7-223">協助在指派給各種連結的頻寬容量上進行更有效的容量規劃和反覆運算</span><span class="sxs-lookup"><span data-stu-id="caac7-223">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="caac7-224">頻寬流量分析程式可以產生頻寬容量和使用方式報告的圖形圖形它們如下：</span><span class="sxs-lookup"><span data-stu-id="caac7-224">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

- <span data-ttu-id="caac7-225">商業網路中的所有 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="caac7-225">All the WAN links in the enterprise network</span></span>

- <span data-ttu-id="caac7-226">依選取的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="caac7-226">Filtered by selected WAN links that have been chosen</span></span>

- <span data-ttu-id="caac7-227">由超過連結容量的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="caac7-227">Filtered by WAN links that have exceeded link capacity</span></span>

- <span data-ttu-id="caac7-228">使用已在使用中布建的頻寬來篩選的 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="caac7-228">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

- <span data-ttu-id="caac7-229">依 WAN 連結的頻寬使用量超過90% 的頻寬使用量，篩選已達到關鍵性層級的 WAN 連結 () </span><span class="sxs-lookup"><span data-stu-id="caac7-229">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

- <span data-ttu-id="caac7-230">依 WAN 連結類型篩選—網路網站連結、interregional 連結，以及網站內的連結</span><span class="sxs-lookup"><span data-stu-id="caac7-230">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

- <span data-ttu-id="caac7-231">依網路地區篩選</span><span class="sxs-lookup"><span data-stu-id="caac7-231">Filtered by network region</span></span>

#### <a name="applications"></a><span data-ttu-id="caac7-232">應用程式</span><span class="sxs-lookup"><span data-stu-id="caac7-232">Applications</span></span>

<span data-ttu-id="caac7-233">頻寬使用狀況分析器具有下列兩個應用程式 (工具) ：</span><span class="sxs-lookup"><span data-stu-id="caac7-233">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

- <span data-ttu-id="caac7-234">**WanLinkLogCollector.exe** 此工具可讓其使用者輸入必要的資訊。</span><span class="sxs-lookup"><span data-stu-id="caac7-234">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>

- <span data-ttu-id="caac7-235">**BandwidthUtilizationAnalyzer.xlsm** Microsoft Excel 試算表軟體報告會由 WanLinkLogCollector.exe 自動啟動。</span><span class="sxs-lookup"><span data-stu-id="caac7-235">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="caac7-236">此應用程式可讓使用者將篩選器套用至報告（如本文稍後所示）。</span><span class="sxs-lookup"><span data-stu-id="caac7-236">This application allows the user to apply filters to the report as shown later in this article.</span></span>

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="caac7-237">使用頻寬流量分析程式的階段</span><span class="sxs-lookup"><span data-stu-id="caac7-237">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="caac7-238">使用頻寬使用量分析器時，有兩個階段：</span><span class="sxs-lookup"><span data-stu-id="caac7-238">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

- <span data-ttu-id="caac7-239">收集使用 WanLinkLogCollector.exe 執行的記錄</span><span class="sxs-lookup"><span data-stu-id="caac7-239">Collect logs, which are performed by using WanLinkLogCollector.exe</span></span>

- <span data-ttu-id="caac7-240">使用 BandwidthUtilizationAnalyzer.xlsm 進行自訂報告</span><span class="sxs-lookup"><span data-stu-id="caac7-240">Customize reports, which are performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="caac7-241">強烈建議您不要由使用者手動啟動 BandwidthUtilizationAnalyzer.xlsm。</span><span class="sxs-lookup"><span data-stu-id="caac7-241">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>

#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="caac7-242">啟動頻寬流量分析程式</span><span class="sxs-lookup"><span data-stu-id="caac7-242">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="caac7-243">在命令提示字元處或使用 Windows Explorer 開始 WanLinkLogCollector.exe。</span><span class="sxs-lookup"><span data-stu-id="caac7-243">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

 <span data-ttu-id="caac7-244">**使用 WanLinkLogCollector.exe**</span><span class="sxs-lookup"><span data-stu-id="caac7-244">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="caac7-245">使用 WanLinkLogCollector.exe 有三個步驟：</span><span class="sxs-lookup"><span data-stu-id="caac7-245">There are three steps to using WanLinkLogCollector.exe:</span></span>

1. <span data-ttu-id="caac7-246">**記錄時程表** 提供報表需要產生的時程表</span><span class="sxs-lookup"><span data-stu-id="caac7-246">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>

2. <span data-ttu-id="caac7-247">**指定檔目錄** 提供檔案位置資訊</span><span class="sxs-lookup"><span data-stu-id="caac7-247">**Specify the file directories** Provide file location information</span></span>

3. <span data-ttu-id="caac7-248">**收集記錄檔並啟動報告檢視器** 執行命令以產生報告</span><span class="sxs-lookup"><span data-stu-id="caac7-248">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>

#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="caac7-249">步驟 1-記錄時程表</span><span class="sxs-lookup"><span data-stu-id="caac7-249">Step 1 - Log the timeline</span></span>

<span data-ttu-id="caac7-250">記錄時程表可讓工具使用者指定下列，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="caac7-250">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1. <span data-ttu-id="caac7-251">**開始日期** 這是要產生報告的時程表開始日期;例如，2010年8月1日。</span><span class="sxs-lookup"><span data-stu-id="caac7-251">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2. <span data-ttu-id="caac7-252">**結束日期** 這是要產生報告的時程表結束日期;例如，2010年9月30日。</span><span class="sxs-lookup"><span data-stu-id="caac7-252">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>

     ![頻寬使用狀況 A 的開始和結束日期](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="caac7-254">步驟 2-指定檔目錄</span><span class="sxs-lookup"><span data-stu-id="caac7-254">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="caac7-255">下列是使用者可以指定的檔案目錄，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="caac7-255">The following file directories can be specified by the user as shown.</span></span>

- <span data-ttu-id="caac7-256">**伺服器記錄檔位置** 儲存頻寬原則伺服器記錄的資料夾位置。</span><span class="sxs-lookup"><span data-stu-id="caac7-256">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="caac7-257">這通常是 \<fileserver\> \\<選擇的 FE \> \AppServerFiles\PDP。</span><span class="sxs-lookup"><span data-stu-id="caac7-257">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>

- <span data-ttu-id="caac7-258">**暫存檔儲存位置** 產生報告時儲存中間檔案的暫存檔案位置。</span><span class="sxs-lookup"><span data-stu-id="caac7-258">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

    ![頻寬使用量分析中的檔案目錄](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > <span data-ttu-id="caac7-260">確定已將對伺服器記錄和暫存檔存放區資料夾的足夠存取權提供給工具使用者。</span><span class="sxs-lookup"><span data-stu-id="caac7-260">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="caac7-261">步驟 3-收集記錄檔並啟動報告檢視器</span><span class="sxs-lookup"><span data-stu-id="caac7-261">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="caac7-262">若要收集記錄檔並啟動報告檢視器，請按一下 [ **執行** ]，如下所示。</span><span class="sxs-lookup"><span data-stu-id="caac7-262">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="caac7-263">此步驟會收集必要的資料。</span><span class="sxs-lookup"><span data-stu-id="caac7-263">This step collects the required data.</span></span>

![在頻寬利用率 Analy 中收集資料](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

<span data-ttu-id="caac7-265">當輸入驗證成功時，會顯示如下所示的訊息。</span><span class="sxs-lookup"><span data-stu-id="caac7-265">When the input validation is successful, the message shown below is displayed.</span></span>

![在頻寬 Utili 中收集的記錄通知](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

<span data-ttu-id="caac7-267">按一下 \*\*\*\*[確定]。</span><span class="sxs-lookup"><span data-stu-id="caac7-267">Click **OK**.</span></span> <span data-ttu-id="caac7-268">BandwidthUtilizationAnalyzer.xlsm 會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="caac7-268">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="caac7-269">依照訊息方塊中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="caac7-269">Follow the instructions in the message box.</span></span> <span data-ttu-id="caac7-270">如需詳細資訊，請參閱下一節中的 **Using BandwidthUtilizationAnalyzer.xlsm** 。</span><span class="sxs-lookup"><span data-stu-id="caac7-270">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>


### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="caac7-271">使用 BandwidthUtilizationAnalyzer.xlsm</span><span class="sxs-lookup"><span data-stu-id="caac7-271">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="caac7-272">自動啟動 BandwidthUtilizationAnalyzer.xlsm 時，請按一下 [重新整理] **，如下所** 示。</span><span class="sxs-lookup"><span data-stu-id="caac7-272">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. <span data-ttu-id="caac7-274">開啟檔案資料夾時，請選取訊息方塊中所指定的位置 consolidated.csv，如下所示。</span><span class="sxs-lookup"><span data-stu-id="caac7-274">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="caac7-275">它也會顯示為 **C：\Temp** 的位置。</span><span class="sxs-lookup"><span data-stu-id="caac7-275">It also shows the location as **C:\Temp**.</span></span>

     ![在 BandwidthUtilizationAnalyzer 中開啟資料夾。](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. <span data-ttu-id="caac7-277">按一下 **[匯入]**。</span><span class="sxs-lookup"><span data-stu-id="caac7-277">Click **Import**.</span></span>

4. <span data-ttu-id="caac7-278">會自動產生圖形化圖形。</span><span class="sxs-lookup"><span data-stu-id="caac7-278">The graphical plot is automatically generated.</span></span> <span data-ttu-id="caac7-279">當工作的背景指標消失時，即可使用此功能。</span><span class="sxs-lookup"><span data-stu-id="caac7-279">It is available when the working-in-the-background pointer disappears.</span></span>

     ![在報表檢視中套用篩選器。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="caac7-281">將篩選器套用至報表檢視</span><span class="sxs-lookup"><span data-stu-id="caac7-281">Applying Filters to the Report View</span></span>

<span data-ttu-id="caac7-282">如下所示，可套用到報表檢視的篩選，如下所述：</span><span class="sxs-lookup"><span data-stu-id="caac7-282">The filters that can be applied to the report view as shown below are described as follows:</span></span>

![在報表檢視中套用篩選器。](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. <span data-ttu-id="caac7-284">**名稱** 依 WAN 連結篩選 (篩選位於圖形) 右側。</span><span class="sxs-lookup"><span data-stu-id="caac7-284">**Name** Filter by WAN links (the filter is on the right side of the graph).</span></span> <span data-ttu-id="caac7-285">前置詞表示下列連結類型;請參閱垂直 (blue) 方塊：</span><span class="sxs-lookup"><span data-stu-id="caac7-285">The prefix denotes the following link types; see the vertical (blue) box:</span></span>

   - <span data-ttu-id="caac7-286">**S 網站** 從網路網站到網路地區的 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="caac7-286">**S Site** The WAN link from a network site to a network region</span></span>

   - <span data-ttu-id="caac7-287">**為網站間** 兩個網路網站間的 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="caac7-287">**IS Inter-Site** The WAN link between two network sites</span></span>

   - <span data-ttu-id="caac7-288">**R 區域間** 兩個網路地區之間的 WAN 連結</span><span class="sxs-lookup"><span data-stu-id="caac7-288">**R Inter-Region** The WAN link between two network region</span></span>

2. <span data-ttu-id="caac7-289">**超出限制** 依頻寬使用量超過頻寬容量的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="caac7-289">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3. <span data-ttu-id="caac7-290">**重要層級** 依頻寬利用率達到90% 或以上頻寬容量的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="caac7-290">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4. <span data-ttu-id="caac7-291">**低利用率** 依頻寬利用率低於頻寬容量25% 的 WAN 連結篩選</span><span class="sxs-lookup"><span data-stu-id="caac7-291">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5. <span data-ttu-id="caac7-292">**連結類型** 依下列 WAN 連結類型進行篩選：</span><span class="sxs-lookup"><span data-stu-id="caac7-292">**Link type** Filter by the following WAN links types:</span></span>

   - <span data-ttu-id="caac7-293">**網路網站** 類型</span><span class="sxs-lookup"><span data-stu-id="caac7-293">**Network site** type</span></span>

   - <span data-ttu-id="caac7-294">**網站間** 類型</span><span class="sxs-lookup"><span data-stu-id="caac7-294">**Inter-site** type</span></span>

   - <span data-ttu-id="caac7-295">**地區間連結** 類型</span><span class="sxs-lookup"><span data-stu-id="caac7-295">**Inter-Region link** type</span></span>

6. <span data-ttu-id="caac7-296">**地區** 依網路地區篩選</span><span class="sxs-lookup"><span data-stu-id="caac7-296">**Region** Filter by network region</span></span>

<span data-ttu-id="caac7-297">下圖顯示先前所述的篩選。</span><span class="sxs-lookup"><span data-stu-id="caac7-297">The following figures show the previously described filters.</span></span>

<span data-ttu-id="caac7-298">依 **名稱** 篩選。</span><span class="sxs-lookup"><span data-stu-id="caac7-298">Filter by **Name**.</span></span> <span data-ttu-id="caac7-299">選取需要顯示在圖表中的連結清單。</span><span class="sxs-lookup"><span data-stu-id="caac7-299">Select the list of links that need to be displayed in the graph.</span></span>

![在 BandwidthUtilizationAnalyzer 中以名稱篩選。](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

<span data-ttu-id="caac7-301">篩選依據 **超出限制**。</span><span class="sxs-lookup"><span data-stu-id="caac7-301">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="caac7-302">選取 [ **True** ] 以強制執行篩選。</span><span class="sxs-lookup"><span data-stu-id="caac7-302">Select **True** to enforce the filter.</span></span>

![以超出限制篩選。](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

<span data-ttu-id="caac7-304">依 **重要層級** 篩選。</span><span class="sxs-lookup"><span data-stu-id="caac7-304">Filter by **Critical levels**.</span></span> <span data-ttu-id="caac7-305">選取 [ **True** ] 以強制執行篩選。</span><span class="sxs-lookup"><span data-stu-id="caac7-305">Select **True** to enforce the filter.</span></span>

![依重要層級篩選。](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

<span data-ttu-id="caac7-307">根據 **使用** 中的篩選。</span><span class="sxs-lookup"><span data-stu-id="caac7-307">Filter by **Under utilized**.</span></span> <span data-ttu-id="caac7-308">選取 [ **True** ] 以強制執行篩選。</span><span class="sxs-lookup"><span data-stu-id="caac7-308">Select **True** to enforce the filter.</span></span>

![按使用中的篩選。](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

<span data-ttu-id="caac7-310">依 **連結類型** 篩選。</span><span class="sxs-lookup"><span data-stu-id="caac7-310">Filter by **Link Type**.</span></span> <span data-ttu-id="caac7-311">選取需要顯示的類型或類型。</span><span class="sxs-lookup"><span data-stu-id="caac7-311">Select the type or types that need to be displayed.</span></span>

![依連結類型篩選。](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

<span data-ttu-id="caac7-313">依 **地區** 篩選。</span><span class="sxs-lookup"><span data-stu-id="caac7-313">Filter by **Region**.</span></span> <span data-ttu-id="caac7-314">選取需要顯示其連結的區域清單。</span><span class="sxs-lookup"><span data-stu-id="caac7-314">Select a list of regions whose links need to be displayed.</span></span>

![依地區篩選。](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a><span data-ttu-id="caac7-316">需求</span><span class="sxs-lookup"><span data-stu-id="caac7-316">Requirements</span></span>

- <span data-ttu-id="caac7-317">.NET Framework 3。5</span><span class="sxs-lookup"><span data-stu-id="caac7-317">The .NET Framework 3.5</span></span>

- <span data-ttu-id="caac7-318">Microsoft Excel 2010 或 Excel 2007</span><span class="sxs-lookup"><span data-stu-id="caac7-318">Microsoft Excel 2010 or Excel 2007</span></span>

### <a name="summary"></a><span data-ttu-id="caac7-319">摘要</span><span class="sxs-lookup"><span data-stu-id="caac7-319">Summary</span></span>

<span data-ttu-id="caac7-320">頻寬流量分析程式可用來繪製網路上 UC 流量的音訊頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="caac7-320">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="caac7-321">您也可以使用此工具來報告網路上的視頻頻寬使用方式。</span><span class="sxs-lookup"><span data-stu-id="caac7-321">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

## <a name="call-parkometer"></a><span data-ttu-id="caac7-322">呼叫 Call parkometer</span><span class="sxs-lookup"><span data-stu-id="caac7-322">Call Parkometer</span></span>
<span data-ttu-id="caac7-323"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="caac7-323"><a name="callpark"> </a></span></span>

<span data-ttu-id="caac7-324">「呼叫 Call parkometer」是一種命令列應用程式，可讓您輕鬆存取通話駐留軌道資料庫。</span><span class="sxs-lookup"><span data-stu-id="caac7-324">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

### <a name="description"></a><span data-ttu-id="caac7-325">描述</span><span class="sxs-lookup"><span data-stu-id="caac7-325">Description</span></span>

<span data-ttu-id="caac7-326">「呼叫 Call parkometer 是一種可追蹤目前寄存通話的工具。</span><span class="sxs-lookup"><span data-stu-id="caac7-326">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="caac7-327">它也會收集有關軌道和通話駐留伺服器 (CPS) 使用狀況的統計資料。</span><span class="sxs-lookup"><span data-stu-id="caac7-327">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="caac7-328">這個命令列工具既可以從本機或遠端連線的電腦，為 CPS 軌道 SQL Server 資料庫提供讀取和寫入權存取權。</span><span class="sxs-lookup"><span data-stu-id="caac7-328">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="caac7-329">所有選項都是互斥的。</span><span class="sxs-lookup"><span data-stu-id="caac7-329">All options are mutually exclusive.</span></span> <span data-ttu-id="caac7-330">命令列語法如下：</span><span class="sxs-lookup"><span data-stu-id="caac7-330">Command-line syntax is as follows:</span></span>

- <span data-ttu-id="caac7-331">**-o** 參數--列出為此集區設定的所有軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="caac7-331">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>

- <span data-ttu-id="caac7-332">**-n** 參數-列出此集區中所有目前使用的軌道。</span><span class="sxs-lookup"><span data-stu-id="caac7-332">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="caac7-333">顯示的資訊如下：</span><span class="sxs-lookup"><span data-stu-id="caac7-333">The information displayed is as follows:</span></span>

  - <span data-ttu-id="caac7-334">SIP 統一資源識別項 (parkee 和 parker 的 URI) 。</span><span class="sxs-lookup"><span data-stu-id="caac7-334">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>

  - <span data-ttu-id="caac7-335">寄存通話之 CPS 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="caac7-335">Host name of the CPS where the call is parked.</span></span>

  - <span data-ttu-id="caac7-336">寄存通話的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="caac7-336">Time stamp of when the call was parked.</span></span>

- <span data-ttu-id="caac7-337">**-f** 參數--列出集區中目前可用的軌道的數目。</span><span class="sxs-lookup"><span data-stu-id="caac7-337">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>

- <span data-ttu-id="caac7-338">**-r \<n\>** 參數-列出 \<n\> 最後一個寄存的呼叫。</span><span class="sxs-lookup"><span data-stu-id="caac7-338">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="caac7-339">顯示的資訊如下：</span><span class="sxs-lookup"><span data-stu-id="caac7-339">The information displayed is as follows:</span></span>

  - <span data-ttu-id="caac7-340">Parkee SIP URI。</span><span class="sxs-lookup"><span data-stu-id="caac7-340">Parkee SIP URI.</span></span>

  - <span data-ttu-id="caac7-341">Parker SIP URI。</span><span class="sxs-lookup"><span data-stu-id="caac7-341">Parker SIP URI.</span></span>

  - <span data-ttu-id="caac7-342">寄存通話之 CPS 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="caac7-342">Host name of the CPS where the call was parked.</span></span>

  - <span data-ttu-id="caac7-343">檢索或丟棄通話的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="caac7-343">Time stamp of when the call was retrieved or dropped.</span></span>

- <span data-ttu-id="caac7-344">**-t \<n\>** 參數-測試在資料庫中保留軌道，以顯示指定之軌道編號的隨機性。</span><span class="sxs-lookup"><span data-stu-id="caac7-344">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

### <a name="output"></a><span data-ttu-id="caac7-345">輸出</span><span class="sxs-lookup"><span data-stu-id="caac7-345">Output</span></span>

<span data-ttu-id="caac7-346">根據在命令提示字元中指定的輸入參數，「呼叫 Call parkometer」會顯示下列輸出：</span><span class="sxs-lookup"><span data-stu-id="caac7-346">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

- <span data-ttu-id="caac7-347">為此集區設定的所有軌道範圍</span><span class="sxs-lookup"><span data-stu-id="caac7-347">All orbit ranges that are configured for this pool</span></span>

- <span data-ttu-id="caac7-348">目前寄存通話</span><span class="sxs-lookup"><span data-stu-id="caac7-348">Currently parked calls</span></span>

- <span data-ttu-id="caac7-349">) 軌道中可用的可用 (數目</span><span class="sxs-lookup"><span data-stu-id="caac7-349">Number of free (available) orbits</span></span>

- <span data-ttu-id="caac7-350">最近寄存的通話</span><span class="sxs-lookup"><span data-stu-id="caac7-350">Recently parked calls</span></span>

- <span data-ttu-id="caac7-351">用於測試均勻及隨機軌道值的保留軌道</span><span class="sxs-lookup"><span data-stu-id="caac7-351">Reserved orbits for testing uniform and random orbit values</span></span>

### <a name="purpose"></a><span data-ttu-id="caac7-352">用途</span><span class="sxs-lookup"><span data-stu-id="caac7-352">Purpose</span></span>

<span data-ttu-id="caac7-353">CPS 工具的目的是提供 CPS 資料庫的命令列存取權。</span><span class="sxs-lookup"><span data-stu-id="caac7-353">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="caac7-354">管理員可以查看 CPS 使用狀況，並決定指派至集區的軌道數目。</span><span class="sxs-lookup"><span data-stu-id="caac7-354">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

### <a name="requirements"></a><span data-ttu-id="caac7-355">需求</span><span class="sxs-lookup"><span data-stu-id="caac7-355">Requirements</span></span>

<span data-ttu-id="caac7-356">如果此工具在執行 CPS 的同一部電腦上執行，則不會有任何需求。</span><span class="sxs-lookup"><span data-stu-id="caac7-356">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="caac7-357">若在遠端電腦上執行此工具，則商務用 Skype Server 2015 所用的 SQL Server 資料庫必須設定為允許遠端存取。</span><span class="sxs-lookup"><span data-stu-id="caac7-357">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="caac7-358">必須使用 SQL Server 資料庫連接字串來設定 Call call parkometer，以連接到集區的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="caac7-358">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="caac7-359">此 SQL Server 資料庫連接字串是在設定檔中定義 **parkometer.exe.config**。它必須放在 parkometer.exe 所在的相同目錄中。</span><span class="sxs-lookup"><span data-stu-id="caac7-359">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="caac7-360">下列 XML 檔案是 parkometer.exe.config 的範例。必須設定的參數為 [使用者名稱] (例如，mydomain\Administrator) 、密碼 (例如，mypassword) 及主機名稱 (例如，myserver) 。</span><span class="sxs-lookup"><span data-stu-id="caac7-360">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

### <a name="examples"></a><span data-ttu-id="caac7-361">範例</span><span class="sxs-lookup"><span data-stu-id="caac7-361">Examples</span></span>

<span data-ttu-id="caac7-362">已部署軌道範圍：-o 參數會列出為此集區設定的所有軌道範圍（如圖所示）。</span><span class="sxs-lookup"><span data-stu-id="caac7-362">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

![「呼叫 Call parkometer 中的軌道範圍。](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

<span data-ttu-id="caac7-364">目前寄存通話：-n 參數會列出此集區上所有目前使用的軌道（如圖所示）。</span><span class="sxs-lookup"><span data-stu-id="caac7-364">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>

![呼叫 Call parkometer 中的目前寄存通話。](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

<span data-ttu-id="caac7-366">[自由] 軌道的數目：-f 參數會列出集區中目前可用的軌道式的數目（如圖所示）。</span><span class="sxs-lookup"><span data-stu-id="caac7-366">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>

![空閒的軌道式按呼叫 Call parkometer。](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

<span data-ttu-id="caac7-368">最近寄存的通話：-r \<n\> 參數會列出 \<n\> 最後一個寄存的呼叫，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="caac7-368">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

![通話 Call parkometer 中最近寄存的通話。](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

<span data-ttu-id="caac7-370">測試軌道保留：-t \<n\> 參數會測試在資料庫中保留軌道（如圖所示）。</span><span class="sxs-lookup"><span data-stu-id="caac7-370">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

![在 [呼叫 Call parkometer] 中測試軌道保留。](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a><span data-ttu-id="caac7-372">摘要</span><span class="sxs-lookup"><span data-stu-id="caac7-372">Summary</span></span>

<span data-ttu-id="caac7-373">「呼叫 Call parkometer」是一種命令列工具，提供通話駐留伺服器的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="caac7-373">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

## <a name="dbanalyze"></a><span data-ttu-id="caac7-374">Dbanalyze.exe</span><span class="sxs-lookup"><span data-stu-id="caac7-374">DBAnalyze</span></span>
<span data-ttu-id="caac7-375"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="caac7-375"><a name="dba"> </a></span></span>

### <a name="description"></a><span data-ttu-id="caac7-376">描述</span><span class="sxs-lookup"><span data-stu-id="caac7-376">Description</span></span>

<span data-ttu-id="caac7-377">dbanalyze.exe 是一種命令列工具，可協助系統管理員收集有關商務用 Skype Server 2015 資料庫的分析報告。</span><span class="sxs-lookup"><span data-stu-id="caac7-377">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="caac7-378">Dbanalyze.exe 具有下列模式：診斷、使用者資料、會議、MCUs 和磁片分段：</span><span class="sxs-lookup"><span data-stu-id="caac7-378">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

- <span data-ttu-id="caac7-379">**診斷模式** 會建立報表，其中包含資料表 (記錄數目、分散、資料大小及索引大小) 的相關資訊。資料和記錄檔大小、最後的備份時間、在執行 Microsoft Office 通訊伺服器的伺服器之間的連絡人散佈、每位使用者的許可權數目、連絡人、容器、訂閱、發佈、每一位使用者的端點，以及無法路由傳送的使用者，每一位使用者、排程的會議、使用中會議，以及資料庫版本的平均組織會議數目。</span><span class="sxs-lookup"><span data-stu-id="caac7-379">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>

    > [!NOTE]
    > <span data-ttu-id="caac7-380">執行診斷模式可能會影響伺服器效能。</span><span class="sxs-lookup"><span data-stu-id="caac7-380">Running diagnostic mode can affect server performance.</span></span>

- <span data-ttu-id="caac7-381">**使用者資料模式** 針對指定的使用者或使用者在其連絡人及許可權清單中的使用者，報告連絡人、容器、訂閱、發佈、許可權及連絡人群組資料。</span><span class="sxs-lookup"><span data-stu-id="caac7-381">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="caac7-382">這種模式也會報告使用者組織或受到邀之會議的摘要資料。</span><span class="sxs-lookup"><span data-stu-id="caac7-382">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

- <span data-ttu-id="caac7-383">**會議模式** 報告特定會議的詳細資料，包括會議、被邀請者清單、會議所允許的媒體類型清單、active MCUs (multipoint 控制項單位) 、作用中的參與者清單，以及每個參與者的信號狀態。</span><span class="sxs-lookup"><span data-stu-id="caac7-383">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>

- <span data-ttu-id="caac7-384">**解碼會議識別碼** 會解碼 **/pstnid** 參數所指定的公用交換電話網路 (PSTN) 會議識別碼，但不會連線至後端以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="caac7-384">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

- <span data-ttu-id="caac7-385">**解決會議** 會解碼 **/pstnid** 參數所指定的 PSTN 會議 ID，並顯示識別碼所指定之會議的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="caac7-385">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

- <span data-ttu-id="caac7-386">**MCUs 模式** 針對集區中的每個 MCU 報告識別碼、媒體類型、URL、心跳狀態、會議載入和參與者負載。</span><span class="sxs-lookup"><span data-stu-id="caac7-386">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

- <span data-ttu-id="caac7-387">**磁片分段模式** 顯示所有磁片的分段狀態。</span><span class="sxs-lookup"><span data-stu-id="caac7-387">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="caac7-388">此工具可用於診斷各種問題，或協助系統管理員進行容量規劃。</span><span class="sxs-lookup"><span data-stu-id="caac7-388">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="caac7-389">例如，如果在伺服器 A 上大多數的使用者都選擇以伺服器 B 為其連絡人的使用者，則系統管理員可以將伺服器 A 上的使用者移至伺服器 B，以減少跨伺服器的流量。</span><span class="sxs-lookup"><span data-stu-id="caac7-389">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

### <a name="output"></a><span data-ttu-id="caac7-390">輸出</span><span class="sxs-lookup"><span data-stu-id="caac7-390">Output</span></span>

<span data-ttu-id="caac7-391">此工具會輸出商務用 Skype Server 2015 資料庫的預先定義報告。</span><span class="sxs-lookup"><span data-stu-id="caac7-391">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="caac7-392">**路徑**：%ProgramFiles% \ 商務用 Skype Server 2015 \ Reskit</span><span class="sxs-lookup"><span data-stu-id="caac7-392">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>

### <a name="purpose"></a><span data-ttu-id="caac7-393">用途</span><span class="sxs-lookup"><span data-stu-id="caac7-393">Purpose</span></span>

<span data-ttu-id="caac7-394">若要安裝 Dbanalyze.exe，請將它複製到本機資料夾，然後執行工具。</span><span class="sxs-lookup"><span data-stu-id="caac7-394">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="caac7-395">若要使用此工具，請從命令列執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="caac7-395">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="caac7-396">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` 命令列選項的描述如下所示。</span><span class="sxs-lookup"><span data-stu-id="caac7-396">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>

![Dbanalyze.exe 的命令列選項。](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a><span data-ttu-id="caac7-398">需求</span><span class="sxs-lookup"><span data-stu-id="caac7-398">Requirements</span></span>

 <span data-ttu-id="caac7-399">**電腦** dbanalyze.exe 只能從已安裝商務用 Skype Server 2015 的已加入網域的電腦執行。</span><span class="sxs-lookup"><span data-stu-id="caac7-399">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>

 <span data-ttu-id="caac7-400">**網路** 電腦應該可以連接至後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="caac7-400">**Network** The computer should be able to connect to the back-end database.</span></span>

 <span data-ttu-id="caac7-401">在執行 dbanalyze.exe 之前，必須先安裝 **軟體** 商務用 Skype Server 2015 軟體元件。</span><span class="sxs-lookup"><span data-stu-id="caac7-401">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>

 <span data-ttu-id="caac7-402">**使用者** 下表顯示具有存取商務用 Skype Server 2015 資料庫之必要許可權的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="caac7-402">**Users** The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>

![Dbanalyze.exe 的許可權表格。](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> <span data-ttu-id="caac7-404">**/Report：磁片** 模式需要本機系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="caac7-404">A local administrator account is required for **/report:disk** mode.</span></span>

### <a name="examples"></a><span data-ttu-id="caac7-405">範例</span><span class="sxs-lookup"><span data-stu-id="caac7-405">Examples</span></span>

<span data-ttu-id="caac7-406">以下是有效 Dbanalyze.exe 命令的範例：</span><span class="sxs-lookup"><span data-stu-id="caac7-406">The following are examples of valid Dbanalyze.exe commands:</span></span>

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="caac7-407">摘要</span><span class="sxs-lookup"><span data-stu-id="caac7-407">Summary</span></span>

<span data-ttu-id="caac7-408">DBAnalyzer 可讓系統管理員快速且容易地分析商務用 Skype Server 2015 資料庫。</span><span class="sxs-lookup"><span data-stu-id="caac7-408">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>

## <a name="import-storage-service-data"></a><span data-ttu-id="caac7-409">匯入儲存體服務資料</span><span class="sxs-lookup"><span data-stu-id="caac7-409">Import Storage Service Data</span></span>
<span data-ttu-id="caac7-410"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="caac7-410"><a name="Issd"> </a></span></span>

<span data-ttu-id="caac7-411">ImportStorageServiceData 資源工具組工具允許從儲存體服務中清除的重新佇列和端點資料， (LYSS) 回儲存體服務。</span><span class="sxs-lookup"><span data-stu-id="caac7-411">The ImportStorageServiceData resource kit tool allows for reimporting Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

### <a name="description"></a><span data-ttu-id="caac7-412">描述</span><span class="sxs-lookup"><span data-stu-id="caac7-412">Description</span></span>

<span data-ttu-id="caac7-413">儲存體服務所清除的資料，可能會根據佇列專案狀態或資料庫大小，定期 (定期) 。</span><span class="sxs-lookup"><span data-stu-id="caac7-413">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="caac7-414">這可能是因為手動呼叫集區容錯移轉指令 StorageServiceFullFlush，或是集區容錯移轉指令) 所呼叫的 Cmdlet (。</span><span class="sxs-lookup"><span data-stu-id="caac7-414">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="caac7-415">請注意，如果前端上的任何儲存體服務 (LYSS ) 的資料庫大小高於一般層級以上，則理想情況下不會 reimported 資料，因為這樣做可能只會導致傳回更多資料。此外，針對導致儲存體服務佇列增加的錯誤，必須先解決的任何問題，都應該先加以解決 (例如 Exchange 端點錯誤、網路問題或其他問題) 。</span><span class="sxs-lookup"><span data-stu-id="caac7-415">Note that data should ideally not be reimported if any of the Storage Service (LYSS ) database sizes on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems that could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

 <span data-ttu-id="caac7-416">**案例1：** 集區容錯移轉期間，每個前端的檔案可能會從儲存體服務上清除。</span><span class="sxs-lookup"><span data-stu-id="caac7-416">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="caac7-417">容錯移轉完成後，應執行工具以重新導入資料。</span><span class="sxs-lookup"><span data-stu-id="caac7-417">After failover is completed, the tool should be run to reimport the data.</span></span>

 <span data-ttu-id="caac7-418">**案例2：** 每日自動清除資料，或回應儲存體的服務資料庫超過特定大小的閾值 (例如60%、80%、90% full) 。</span><span class="sxs-lookup"><span data-stu-id="caac7-418">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds (for example 60%, 80%, 90% full).</span></span> <span data-ttu-id="caac7-419">這個自動清除的資料應該是由系統管理員定期 reimported。</span><span class="sxs-lookup"><span data-stu-id="caac7-419">This automatically flushed data should be reimported routinely by the administrator.</span></span> <span data-ttu-id="caac7-420">在上述情況下，如果未部署監控 SCOM 套件，則會有商務用 Skype Server 與從儲存體服務清除的資料相關的儲存體服務的事件。</span><span class="sxs-lookup"><span data-stu-id="caac7-420">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="caac7-421">已啟動 32075 (完整清除作業的事件 IDs) ，32076 (完全清除已完成) ，32082 (維護層級清理已開始) ，32083 (維護層級清理完成) ，32089 (因填滿資料庫) 而發生清理。</span><span class="sxs-lookup"><span data-stu-id="caac7-421">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="caac7-422">請注意，這些事件識別碼會對應至 RTM 版本。</span><span class="sxs-lookup"><span data-stu-id="caac7-422">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="caac7-423">當系統管理員看到這些事件時，表示已清除的檔案。此資料應該定期使用此工具（例如每週一次）匯入回來。</span><span class="sxs-lookup"><span data-stu-id="caac7-423">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="caac7-424">在線上服務發行時，如果部署了商務用 Skype Server 的 health monitoring SCOM 套件，則可能會引發新的警示，讓系統管理員將清除的資料重新引入儲存體服務。</span><span class="sxs-lookup"><span data-stu-id="caac7-424">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts that may be raised which ask the administrator to reimport the flushed data back into Storage Service.</span></span> <span data-ttu-id="caac7-425">在觸發警示的 Front-End 伺服器上，事件記錄中會有對應的事件。</span><span class="sxs-lookup"><span data-stu-id="caac7-425">There will be a corresponding event in the event log on the Front-End server that triggered the alert.</span></span> <span data-ttu-id="caac7-426">此事件會提供清除資料檔案所在之父路徑的描述，以及有多少個可滿足警示準則的檔。</span><span class="sxs-lookup"><span data-stu-id="caac7-426">The event will give a description of the Parent path under which the flushed data files are located, and how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="caac7-427">警示準則是指在特定上層路徑下的 X 個或多個檔案，該位置至少是 Y (天的 StorageService，但可以透過變更 APPCONFIG 檔來覆寫。 ) 下列兩個可能觸發狀況警示的事件範例，其差異是其父項路徑。</span><span class="sxs-lookup"><span data-stu-id="caac7-427">The alert criteria is that there are X or more files under the particular parent path that are at least Y days old (where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events that can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="caac7-428">有一種可能的情況是在 Web 服務檔案共用下，另一種可能性是每個前端的本機應用程式資料目錄。</span><span class="sxs-lookup"><span data-stu-id="caac7-428">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="caac7-429"> (例如 c:\ProgramData\Microsoft\ 商務用 Skype Server 2015 \ StorageService) 。</span><span class="sxs-lookup"><span data-stu-id="caac7-429">(for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService).</span></span> <span data-ttu-id="caac7-430">然後，系統管理員會執行此 reskit 工具。</span><span class="sxs-lookup"><span data-stu-id="caac7-430">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="caac7-431">此工具會在其執行的前端上增加 CPU 和 IO 負載，而在其他前端，也就是資料不是由執行該工具的前端所擁有的情況。</span><span class="sxs-lookup"><span data-stu-id="caac7-431">This tool will increase CPU and IO load on the front end it is running on, and other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="caac7-432">建議您在前端未低於大量 CPU 和 IO 負載時執行此工具，例如峰值時段外。</span><span class="sxs-lookup"><span data-stu-id="caac7-432">We recommend running this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="caac7-433">其次，此工具可以2到3分鐘，匯入一個資料檔案。</span><span class="sxs-lookup"><span data-stu-id="caac7-433">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="caac7-434">在評估工具的執行時間時，請務必記住這一點。</span><span class="sxs-lookup"><span data-stu-id="caac7-434">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="caac7-435">預設會在檔存放區上顯示工具所產生的詳細記錄檔。</span><span class="sxs-lookup"><span data-stu-id="caac7-435">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="caac7-436">如果沒有報告錯誤，請將其刪除，因為記錄檔可能會是數十 MB 或更多。</span><span class="sxs-lookup"><span data-stu-id="caac7-436">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

![儲存體伺服器事件記錄事件範例。](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a><span data-ttu-id="caac7-438">需求</span><span class="sxs-lookup"><span data-stu-id="caac7-438">Requirements</span></span>

<span data-ttu-id="caac7-439">安裝2015資源套件工具商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="caac7-439">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="caac7-440">工具會在已加入網域的電腦上執行，並安裝商務用 Skype Server 和商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="caac7-440">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="caac7-441">該工具會使用來自管理命令介面的 Cmdlet，識別集區中的所有 Front-End 伺服器。</span><span class="sxs-lookup"><span data-stu-id="caac7-441">The tool uses a cmdlet from the management shell to identify all the Front-End servers in the pool.</span></span> <span data-ttu-id="caac7-442">其次，必須從已安裝 **RtcLocal** 資料庫的集區中的機器執行工具。</span><span class="sxs-lookup"><span data-stu-id="caac7-442">Secondly, the tool must be executed from a machine in the pool that has the **RtcLocal** database installed.</span></span> <span data-ttu-id="caac7-443">此資料庫由工具使用，以取得集區的 WEBSERVICE 檔案共用的位置。</span><span class="sxs-lookup"><span data-stu-id="caac7-443">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="caac7-444">此外，在使用此工具之前，每個 Front-End 伺服器都必須先在每個 Front-End 伺服器上使用 **Enable-PSRemoting** 來啟用 Windows PowerShell 遠端，以及執行該工具的機器。</span><span class="sxs-lookup"><span data-stu-id="caac7-444">Additionally, before using the tool, each Front-End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front-End server, and the machine that the tool is executed from.</span></span> <span data-ttu-id="caac7-445">否則，來自此工具的遠端 Windows PowerShell 命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="caac7-445">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="caac7-446">Windows PowerShell完成後，集區中的所有 Front-End 伺服器都可以關閉遠端處理。</span><span class="sxs-lookup"><span data-stu-id="caac7-446">Windows PowerShell Remoting can be turned off on all Front-End servers in the pool after it is finished.</span></span> <span data-ttu-id="caac7-447">最後，開啟工具的帳戶或憑證必須具有可讀取/寫入權限給其在其上執行此工具的集區。</span><span class="sxs-lookup"><span data-stu-id="caac7-447">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="caac7-448">否則，該工具會失敗，並顯示 IO 許可權錯誤。</span><span class="sxs-lookup"><span data-stu-id="caac7-448">Otherwise the tool will fail with IO Permission errors.</span></span>

> [!NOTE]
> <span data-ttu-id="caac7-449">在 Windows Server 2012 上，Windows PowerShell 遠端處理會預設為啟用，但不會在 Windows Server 2008 作業系統上啟用。</span><span class="sxs-lookup"><span data-stu-id="caac7-449">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>

### <a name="examples"></a><span data-ttu-id="caac7-450">範例</span><span class="sxs-lookup"><span data-stu-id="caac7-450">Examples</span></span>

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

## <a name="lcssync"></a><span data-ttu-id="caac7-451">LCSSync</span><span class="sxs-lookup"><span data-stu-id="caac7-451">LCSSync</span></span>
<span data-ttu-id="caac7-452"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="caac7-452"><a name="LCSSync"> </a></span></span>

<span data-ttu-id="caac7-453">LCSSync 工具可協助您在多樹系環境中部署商務用 Skype Server 2015 通訊軟體。</span><span class="sxs-lookup"><span data-stu-id="caac7-453">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="caac7-454">此工具是用來將不同使用者樹系中的使用者和群組，當作 Active Directory 網域服務連絡人物件，同步處理商務用 Skype Server 2015 安裝所在的中央樹系。</span><span class="sxs-lookup"><span data-stu-id="caac7-454">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>

### <a name="description"></a><span data-ttu-id="caac7-455">描述</span><span class="sxs-lookup"><span data-stu-id="caac7-455">Description</span></span>

 <span data-ttu-id="caac7-456">LCSSync 使用中央樹系中的 [同步處理 Active Directory 網域服務] 連絡人物件，讓使用者能夠商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="caac7-456">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="caac7-457">若要提供單一登入，主要使用者帳戶必須對應至中央樹系中的 Active Directory 網域服務連絡人物件，以供商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="caac7-457">To provide single sign in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="caac7-458">這個工具可協助您執行該對應。</span><span class="sxs-lookup"><span data-stu-id="caac7-458">This tool helps perform that mapping.</span></span> <span data-ttu-id="caac7-459">此工具提供範本，以在 Microsoft Identity Integration Server 中建立管理代理程式。</span><span class="sxs-lookup"><span data-stu-id="caac7-459">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

### <a name="summary"></a><span data-ttu-id="caac7-460">摘要</span><span class="sxs-lookup"><span data-stu-id="caac7-460">Summary</span></span>

<span data-ttu-id="caac7-461">LCSSync 工具可協助您在多樹系環境中部署商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="caac7-461">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>

## <a name="lookup-user-console"></a><span data-ttu-id="caac7-462">查閱使用者主控台</span><span class="sxs-lookup"><span data-stu-id="caac7-462">Lookup User Console</span></span>
<span data-ttu-id="caac7-463"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="caac7-463"><a name="LUC"> </a></span></span>

<span data-ttu-id="caac7-464">LookupUserConsole 工具會顯示特定使用者的內部商務用 Skype Server 路由資訊。</span><span class="sxs-lookup"><span data-stu-id="caac7-464">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="caac7-465">此資訊對 Microsoft 支援個人在診斷部署和路由問題時可能十分有用。</span><span class="sxs-lookup"><span data-stu-id="caac7-465">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

### <a name="description"></a><span data-ttu-id="caac7-466">描述</span><span class="sxs-lookup"><span data-stu-id="caac7-466">Description</span></span>

 <span data-ttu-id="caac7-467">執行 LookupUserConsole.exe 會開啟接收 SIP 位址的命令提示字元，並嘗試顯示與其相關的內部商務用 Skype Server 路由資訊。</span><span class="sxs-lookup"><span data-stu-id="caac7-467">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="caac7-468">若要結束 LookupUserConsole 工具，請輸入 **exit** 。</span><span class="sxs-lookup"><span data-stu-id="caac7-468">Type **exit** to quit the LookupUserConsole tool.</span></span>

### <a name="requirements"></a><span data-ttu-id="caac7-469">需求</span><span class="sxs-lookup"><span data-stu-id="caac7-469">Requirements</span></span>

<span data-ttu-id="caac7-470">安裝商務用 Skype Server 2015 資源套件。</span><span class="sxs-lookup"><span data-stu-id="caac7-470">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="caac7-471">工具會在安裝商務用 Skype Server 的已加入網域的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="caac7-471">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>

### <a name="examples"></a><span data-ttu-id="caac7-472">範例</span><span class="sxs-lookup"><span data-stu-id="caac7-472">Examples</span></span>

<span data-ttu-id="caac7-473">C:\Program Files \ 商務用 Skype Server 2015 \ ResKit \>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="caac7-473">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>

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

## <a name="msturnping"></a><span data-ttu-id="caac7-474">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="caac7-474">MsTurnPing</span></span>
<span data-ttu-id="caac7-475"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="caac7-475"><a name="MsTurnPing"> </a></span></span>

<span data-ttu-id="caac7-476">MSTurnPing 工具可讓商務用 Skype Server 2015 通訊軟體的系統管理員檢查執行 Audio/Video Edge 的伺服器狀態、Audio/Video 驗證服務，以及拓撲中執行頻寬原則服務的伺服器。</span><span class="sxs-lookup"><span data-stu-id="caac7-476">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge, Audio/Video Authentication services, and the servers that are running Bandwidth Policy Services in the topology.</span></span>

### <a name="description"></a><span data-ttu-id="caac7-477">描述</span><span class="sxs-lookup"><span data-stu-id="caac7-477">Description</span></span>

<span data-ttu-id="caac7-478">MSTurnPing 工具可讓商務用 Skype Server 2015 通訊軟體的系統管理員檢查執行 Audio/Video Edge 的伺服器狀態、Audio/Video 驗證服務，以及拓撲中執行頻寬原則服務的伺服器。</span><span class="sxs-lookup"><span data-stu-id="caac7-478">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge, Audio/Video Authentication services, and the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="caac7-479">工具可讓系統管理員執行下列測試：</span><span class="sxs-lookup"><span data-stu-id="caac7-479">The tool allows the administrator to perform the following tests:</span></span>

1. <span data-ttu-id="caac7-480">A/V Edge Server 測試：此工具會執行下列作業，針對拓撲中的所有 A/V Edge server 執行測試：</span><span class="sxs-lookup"><span data-stu-id="caac7-480">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>

   - <span data-ttu-id="caac7-481">確認商務用 Skype Server Audio/Video 驗證服務已啟動，且可以發出適當的認證。</span><span class="sxs-lookup"><span data-stu-id="caac7-481">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="caac7-482">驗證商務用 Skype Server Audio/Video Edge service 是否已啟動，且是否可成功地在外部 Edge 上分攤資源。</span><span class="sxs-lookup"><span data-stu-id="caac7-482">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2. <span data-ttu-id="caac7-483">頻寬原則服務測試：此工具會透過執行下列動作，對拓撲中執行頻寬原則服務的所有伺服器執行測試：</span><span class="sxs-lookup"><span data-stu-id="caac7-483">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>

   - <span data-ttu-id="caac7-484">驗證商務用 Skype Server 頻寬原則服務 (驗證) 是否已啟動，且可發出適當的認證。</span><span class="sxs-lookup"><span data-stu-id="caac7-484">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="caac7-485">驗證商務用 Skype Server 頻寬原則服務 (核心) 已啟動，且可成功執行頻寬檢查。</span><span class="sxs-lookup"><span data-stu-id="caac7-485">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="caac7-486">此工具必須從屬於拓撲的電腦上執行，且已安裝本機儲存區。</span><span class="sxs-lookup"><span data-stu-id="caac7-486">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

### <a name="output"></a><span data-ttu-id="caac7-487">輸出</span><span class="sxs-lookup"><span data-stu-id="caac7-487">Output</span></span>

<span data-ttu-id="caac7-488">工具會輸出每個作業的結果。</span><span class="sxs-lookup"><span data-stu-id="caac7-488">The tool outputs the results of each of the operations.</span></span>

- <span data-ttu-id="caac7-489">如果執行 **AudioVideoEdgeServer** 測試，則會輸出下列工具：</span><span class="sxs-lookup"><span data-stu-id="caac7-489">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="caac7-490">在拓撲中供應商務用 Skype Server 2015 Audio/Video 驗證服務之電腦的測試結果</span><span class="sxs-lookup"><span data-stu-id="caac7-490">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>

  - <span data-ttu-id="caac7-491">在拓撲中供應商務用 Skype Server 2015 Audio/Video Edge service 之電腦的測試結果</span><span class="sxs-lookup"><span data-stu-id="caac7-491">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>

- <span data-ttu-id="caac7-492">如果執行 **BandwidthPolicyServer** 測試，則會輸出下列工具：</span><span class="sxs-lookup"><span data-stu-id="caac7-492">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="caac7-493">在拓撲中供應商務用 Skype Server 2015 頻寬原則服務 (驗證) 的電腦測試結果</span><span class="sxs-lookup"><span data-stu-id="caac7-493">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>

  - <span data-ttu-id="caac7-494">在拓撲中供應商務用 Skype Server 2015 頻寬原則服務 (核心) 的電腦測試結果</span><span class="sxs-lookup"><span data-stu-id="caac7-494">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>

### <a name="requirements"></a><span data-ttu-id="caac7-495">需求</span><span class="sxs-lookup"><span data-stu-id="caac7-495">Requirements</span></span>

- <span data-ttu-id="caac7-496">此工具必須從拓撲中的電腦執行，且具有本機儲存區。</span><span class="sxs-lookup"><span data-stu-id="caac7-496">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

- <span data-ttu-id="caac7-497">您必須以具有本機儲存區存取權的系統管理員身分執行工具。</span><span class="sxs-lookup"><span data-stu-id="caac7-497">The tool must be run as an administrator who has access to the local store.</span></span>

### <a name="examples"></a><span data-ttu-id="caac7-498">範例</span><span class="sxs-lookup"><span data-stu-id="caac7-498">Examples</span></span>

<span data-ttu-id="caac7-499">下列為工具輸入的範例。</span><span class="sxs-lookup"><span data-stu-id="caac7-499">The following is an example of the tool input.</span></span>

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="caac7-500">摘要</span><span class="sxs-lookup"><span data-stu-id="caac7-500">Summary</span></span>

<span data-ttu-id="caac7-501">若要檢查執行音訊/影片和頻寬原則服務之伺服器的狀態，此工具可能是一項寶貴的資源，可供商務用 Skype Server 2015 系統管理員使用。</span><span class="sxs-lookup"><span data-stu-id="caac7-501">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

## <a name="network-configuration-viewer"></a><span data-ttu-id="caac7-502">網路設定檢視器</span><span class="sxs-lookup"><span data-stu-id="caac7-502">Network Configuration Viewer</span></span>
<span data-ttu-id="caac7-503"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="caac7-503"><a name="NCV"> </a></span></span>

<span data-ttu-id="caac7-504">商務用 Skype Server 2015 通訊軟體管理員可以使用網路設定檢視器來查看已布建的商業網路拓朴的通話許可控制 (CAC) 網路拓朴，以允許即時通訊會話，例如根據指定的頻寬容量進行語音或視頻通話。</span><span class="sxs-lookup"><span data-stu-id="caac7-504">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="caac7-505">商務用 Skype Server 2015 系統管理員會定義 CAC 原則，這些原則是由隨商務用 Skype Server 2015 一起安裝的頻寬原則服務所強制執行。</span><span class="sxs-lookup"><span data-stu-id="caac7-505">Skype for Business Server 2015 administrators defines CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>

### <a name="description"></a><span data-ttu-id="caac7-506">描述</span><span class="sxs-lookup"><span data-stu-id="caac7-506">Description</span></span>

<span data-ttu-id="caac7-507">網路設定檢視器 (NetworkConfigurationViewer.exe) 可讓系統管理員執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="caac7-507">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

- <span data-ttu-id="caac7-508">以圖形格式從商務用 Skype Server 2015 部署中載入和查看 CAC 網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="caac7-508">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>

- <span data-ttu-id="caac7-509">從頻寬原則伺服器記錄檔以圖形格式載入和查看 CAC 網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="caac7-509">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

- <span data-ttu-id="caac7-510">以 XML 格式將 CAC 網路拓撲儲存及儲存在磁片上。</span><span class="sxs-lookup"><span data-stu-id="caac7-510">Save and store CAC network topology in an XML format on the disk.</span></span>

- <span data-ttu-id="caac7-511">以 JPG 或 BMP 格式儲存和儲存 CAC 網路拓撲圖表。</span><span class="sxs-lookup"><span data-stu-id="caac7-511">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

- <span data-ttu-id="caac7-512">查看 CAC 網路拓撲設定資料。</span><span class="sxs-lookup"><span data-stu-id="caac7-512">View CAC network topology configuration data.</span></span>

- <span data-ttu-id="caac7-513">以樹狀目錄模式顯示 CAC 網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="caac7-513">View CAC network topology in a tree-view style.</span></span>

- <span data-ttu-id="caac7-514">針對 CAC 網路拓撲連結定義自訂連接器 (例如，網站對地區、區域對地區及網站對站台連結) 。</span><span class="sxs-lookup"><span data-stu-id="caac7-514">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

- <span data-ttu-id="caac7-515">流覽 CAC 網路拓撲網站資訊、地區資訊，以及布建的頻寬原則和網路連結。</span><span class="sxs-lookup"><span data-stu-id="caac7-515">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

### <a name="purpose"></a><span data-ttu-id="caac7-516">用途</span><span class="sxs-lookup"><span data-stu-id="caac7-516">Purpose</span></span>

<span data-ttu-id="caac7-517">在圖形化介面中查看企業 CAC 網路拓撲連結。</span><span class="sxs-lookup"><span data-stu-id="caac7-517">View enterprise CAC network topology links in a graphical interface.</span></span>

### <a name="examples"></a><span data-ttu-id="caac7-518">範例</span><span class="sxs-lookup"><span data-stu-id="caac7-518">Examples</span></span>

 <span data-ttu-id="caac7-519">**以圖形格式從商務用 Skype Server 2015 部署中載入和查看 cac 網路拓撲**：商務用 Skype Server 2015 系統管理員可以使用 **下載網路** 設定選項，在任何商務用 Skype Server 2015 電腦上載入和查看 cac 網路拓撲設定，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="caac7-519">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="caac7-520">在未連接至商務用 Skype Server 2015 設定儲存區的電腦上部署時，工具將無法下載或查看此類設定。</span><span class="sxs-lookup"><span data-stu-id="caac7-520">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>

![下載網路設定。](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 <span data-ttu-id="caac7-522">**從頻寬原則伺服器記錄檔，以圖形格式載入和查看 cac 網路拓撲：** 商務用 Skype Server 2015 頻寬原則伺服器會將 CAC 網路拓撲儲存為商務用 Skype Server 2015 檔案共用位置的一部分記錄機制。</span><span class="sxs-lookup"><span data-stu-id="caac7-522">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers saves the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="caac7-523">商務用 Skype Server 2015 系統管理員可以使用如下所示的 [**開放網路** 設定] 選項，以圖形格式來查看這類檔案。</span><span class="sxs-lookup"><span data-stu-id="caac7-523">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

![開啟頻寬原則伺服器記錄檔。](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

<span data-ttu-id="caac7-525">在磁片上以 xml 格式儲存並儲存 cac 網路拓撲：商務用 Skype Server 2015 系統管理員可以使用 [**儲存網路設定的副本**] 選項，以 xml 格式儲存 cac 網路拓撲設定檔，如下所示。</span><span class="sxs-lookup"><span data-stu-id="caac7-525">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="caac7-526">然後，已儲存的設定檔便可供離線使用，以供圖形化查看之用。</span><span class="sxs-lookup"><span data-stu-id="caac7-526">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

![將網路設定儲存為 XML 檔案。](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

<span data-ttu-id="caac7-528">以 jpg 或 bmp 格式儲存及儲存 cac 網路拓撲圖：商務用 Skype Server 2015 系統管理員可以使用 [**另存網路設定圖表為圖片**] 選項，以圖形格式儲存 cac 網路拓撲 (設定，) 方式如下所示。</span><span class="sxs-lookup"><span data-stu-id="caac7-528">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

![將網路設定儲存為圖片。](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <span data-ttu-id="caac7-530"><strong>View CAC 網路拓撲設定資料：</strong>商務用 Skype Server 2015 系統管理員可以使用如下所示的 [查看網路設定資料] 選項，以文字格式查看相關的網路設定資料，例如網路地區、網路網站、頻寬設定檔及網站子網 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="caac7-530"><strong>View CAC network topology configuration data:</strong>Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

![查看網路設定資料。](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 <span data-ttu-id="caac7-532">**以樹狀模式顯示 CAC 網路拓撲：** 商務用 Skype Server 2015 系統管理員可以使用工具視窗左邊的 [控制台]，透過工具視窗左邊的 [控制台]，以查看圖形樹狀檢視樣式中的相關網路設定資料，如下所示。</span><span class="sxs-lookup"><span data-stu-id="caac7-532">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

![以樹狀目錄查看網路設定資料。](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 <span data-ttu-id="caac7-534">**針對 cac 網路拓撲連結定義自訂連接器， (例如「點對點」、「地區對地區」及「網站對網站」連結) ：** 商務用 Skype Server 2015 系統管理員可以使用如下所示的 [設定] 選項，來定義 cac 網路設定 WAN 連結的自訂圖形連接器。</span><span class="sxs-lookup"><span data-stu-id="caac7-534">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="caac7-535">這有助於區分網路設定中布建的各種網路連結類型。</span><span class="sxs-lookup"><span data-stu-id="caac7-535">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

![工具](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 <span data-ttu-id="caac7-537">**View CAC 網路拓撲網站資訊，地區資訊，以及布建的頻寬原則：** 商務用 Skype Server 2015 系統管理員可以使用下列的選項，查看相關 cac 網路地區資訊、網站資訊和 CAC 頻寬布建資訊。</span><span class="sxs-lookup"><span data-stu-id="caac7-537">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="caac7-538"> (例如，按一下 [網路地區] 或 [網路網站物件] 中的 [ **資訊** ]。 ) </span><span class="sxs-lookup"><span data-stu-id="caac7-538">(For example, click **Info** in a network region or network site object.)</span></span>

![為您的網路定義自訂連接器。](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a><span data-ttu-id="caac7-540">摘要</span><span class="sxs-lookup"><span data-stu-id="caac7-540">Summary</span></span>

<span data-ttu-id="caac7-541">這項工具可以是商務用 Skype Server 2015 系統管理員的重要資源，想要以圖形格式查看其部署的 CAC 網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="caac7-541">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

## <a name="response-group-agent-live"></a><span data-ttu-id="caac7-542">回應群組代理程式 Live</span><span class="sxs-lookup"><span data-stu-id="caac7-542">Response Group Agent Live</span></span>
<span data-ttu-id="caac7-543"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="caac7-543"><a name="RGAL"> </a></span></span>

<span data-ttu-id="caac7-544">回應群組應用程式讓代理人能夠使用內建的 Web 服務來存取有用的即時資訊。</span><span class="sxs-lookup"><span data-stu-id="caac7-544">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="caac7-545">不幸的是，在應用程式外沒有此資料的圖形視圖。</span><span class="sxs-lookup"><span data-stu-id="caac7-545">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="caac7-546">「回應群組代理程式 Live Resource 工具組」工具可提供一種簡單且圖形的方式來存取這項資訊，並以即時商務用 Skype 通訊軟體資訊（例如，其他代理程式的存在）進行增強，以解決此問題。</span><span class="sxs-lookup"><span data-stu-id="caac7-546">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>

### <a name="description"></a><span data-ttu-id="caac7-547">描述</span><span class="sxs-lookup"><span data-stu-id="caac7-547">Description</span></span>

<span data-ttu-id="caac7-548">回應群組代理程式 Live 是一 Windows 的應用程式，提供登入和登出功能，以及一些即時資訊 (例如群組成員資格和目前的呼叫數目) 回應群組代理程式。</span><span class="sxs-lookup"><span data-stu-id="caac7-548">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="caac7-549">它應為增強版本的「代理群組」頁面 (可從商務用 Skype 進行存取。</span><span class="sxs-lookup"><span data-stu-id="caac7-549">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>

### <a name="purpose"></a><span data-ttu-id="caac7-550">用途</span><span class="sxs-lookup"><span data-stu-id="caac7-550">Purpose</span></span>

<span data-ttu-id="caac7-551">回應群組應用程式會對來電進行佇列，然後將來電路由傳送至代理人群組。</span><span class="sxs-lookup"><span data-stu-id="caac7-551">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="caac7-552">若要對服務叫用的相關決策做出合理決策，代理人可以存取有關其代理群組的即時資訊，例如哪些其他代理程式可用，以及每個佇列中有多少來電等候。</span><span class="sxs-lookup"><span data-stu-id="caac7-552">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="caac7-553">此資訊最初隻會透過回應群組服務進行存取，可透過回應群組代理程式即時以直觀方式取得。</span><span class="sxs-lookup"><span data-stu-id="caac7-553">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

#### <a name="features"></a><span data-ttu-id="caac7-554">功能</span><span class="sxs-lookup"><span data-stu-id="caac7-554">Features</span></span>

<span data-ttu-id="caac7-555">回應群組代理程式 Live tool 是在回應群組服務和商務用 Skype Server 2015 SDK 上建立的。</span><span class="sxs-lookup"><span data-stu-id="caac7-555">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="caac7-556">它提供回應群組代理程式所提供的資訊和功能 (例如群組成員資格、其他代理程式的狀態，以及等候通話的數目) 。</span><span class="sxs-lookup"><span data-stu-id="caac7-556">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="caac7-557">下圖顯示回應群組代理程式的主要介面。</span><span class="sxs-lookup"><span data-stu-id="caac7-557">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

![回應群組代理程式 Live 工具。](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

<span data-ttu-id="caac7-559">下列三個主要功能適用于回應群組代理程式 Live 中的代理程式：</span><span class="sxs-lookup"><span data-stu-id="caac7-559">The following three main features are available for agents in Response Group Agent Live:</span></span>

- <span data-ttu-id="caac7-560">登 **入/登出：** 相反于「代理人群組」頁面 (可從商務用 Skype Server 2015) 存取，回應群組代理程式 Live 只允許代理程式一次登入或登出所有代理人群組。</span><span class="sxs-lookup"><span data-stu-id="caac7-560">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign in or out of all agent groups at once.</span></span> <span data-ttu-id="caac7-561">此應用程式提供三種快速的代理人登入或登出方式：</span><span class="sxs-lookup"><span data-stu-id="caac7-561">This application provides three quick ways for agents to sign in or out:</span></span>

  - <span data-ttu-id="caac7-562">在應用程式內，按一下登入/簽出 (綠色和紅色) 按鈕。</span><span class="sxs-lookup"><span data-stu-id="caac7-562">Click the Sign-in/out (green and red) buttons within the application.</span></span>

  - <span data-ttu-id="caac7-563">以滑鼠右鍵按一下系統工作列圖示，然後選取 [登入] 或 [登出]。</span><span class="sxs-lookup"><span data-stu-id="caac7-563">Right-click the system tray icon, and select sign in or sign out.</span></span>

  - <span data-ttu-id="caac7-564">使用可設定的鍵盤快速鍵。</span><span class="sxs-lookup"><span data-stu-id="caac7-564">Using configurable keyboard shortcuts.</span></span>

- <span data-ttu-id="caac7-565">**群組成員資格：** 當選中代理人群組時，回應群組代理程式 Live 會在右側窗格中顯示此群組中的代理程式清單。</span><span class="sxs-lookup"><span data-stu-id="caac7-565">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="caac7-566">如果商務用 Skype Server 2015 在與此應用程式相同的電腦上執行，則回應群組代理程式會顯示目前狀態資訊和連絡人卡片。</span><span class="sxs-lookup"><span data-stu-id="caac7-566">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="caac7-567">代理程式可以直接從那裡傳送 IM 或呼叫其他代理程式。</span><span class="sxs-lookup"><span data-stu-id="caac7-567">Agents can send an IM or call other agents directly from there.</span></span>

- <span data-ttu-id="caac7-568">**即時統計資料：** 回應群組代理程式 Live 為所有代理程式群組提供即時統計資料。</span><span class="sxs-lookup"><span data-stu-id="caac7-568">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="caac7-569">更新頻率為一分鐘。</span><span class="sxs-lookup"><span data-stu-id="caac7-569">The update frequency is one minute.</span></span> <span data-ttu-id="caac7-570">當回應群組接聽來電時，會在具有目前佇列通話數目的組名旁邊新增視覺指示器。</span><span class="sxs-lookup"><span data-stu-id="caac7-570">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="caac7-571">在群組上暫停指標也會顯示最長的等待時間。</span><span class="sxs-lookup"><span data-stu-id="caac7-571">Pausing the pointer over a group also displays the longest waiting time.</span></span>

### <a name="requirements"></a><span data-ttu-id="caac7-572">需求</span><span class="sxs-lookup"><span data-stu-id="caac7-572">Requirements</span></span>

<span data-ttu-id="caac7-573">回應群組代理程式 Live 需要 .NET Framework 4.0。</span><span class="sxs-lookup"><span data-stu-id="caac7-573">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="caac7-574">此外，若要利用目前狀態和連絡人卡片的功能，必須在本機安裝商務用 Skype (並在) 執行。</span><span class="sxs-lookup"><span data-stu-id="caac7-574">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>

#### <a name="configuration"></a><span data-ttu-id="caac7-575">設定</span><span class="sxs-lookup"><span data-stu-id="caac7-575">Configuration</span></span>

<span data-ttu-id="caac7-576">回應群組代理程式 Live 可透過應用程式中的 [選項] 對話方塊，自訂為個別喜好設定。</span><span class="sxs-lookup"><span data-stu-id="caac7-576">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="caac7-577">此外，管理員可以直接編輯 RGAgentLive.exe.config 檔案的 defaultHostAddress 屬性，來定義預設的主機位址。</span><span class="sxs-lookup"><span data-stu-id="caac7-577">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="caac7-578">下圖說明代理可用於設定主機位址及快速鍵的 [選項] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="caac7-578">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="caac7-579">按一下主介面右上方的 [選項] 按鈕即可存取此對話方塊。</span><span class="sxs-lookup"><span data-stu-id="caac7-579">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

![[回應群組代理程式即時選項] 對話方塊。](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

<span data-ttu-id="caac7-581">在回應群組代理程式 Live 設定中，可以自訂下列三個不同的設定：</span><span class="sxs-lookup"><span data-stu-id="caac7-581">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

- <span data-ttu-id="caac7-582">主機位址：這通常是屬於代理人主集區的網頁集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="caac7-582">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="caac7-583">在此資訊的背景中，會自動派生確切的回應群組服務位址 (方式是在主機) 之後附加正確路徑。</span><span class="sxs-lookup"><span data-stu-id="caac7-583">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

- <span data-ttu-id="caac7-584">快捷方式：可以自訂登入/登出的確切快捷方式。</span><span class="sxs-lookup"><span data-stu-id="caac7-584">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="caac7-585">唯一的限制是兩個快捷方式都必須包含 "Windows 標誌" 金鑰 (除了至少另一個金鑰) 。</span><span class="sxs-lookup"><span data-stu-id="caac7-585">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>

- <span data-ttu-id="caac7-586">開始使用 Windows：可以將應用程式設定為使用 Windows 自動啟動。</span><span class="sxs-lookup"><span data-stu-id="caac7-586">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

### <a name="examples"></a><span data-ttu-id="caac7-587">範例</span><span class="sxs-lookup"><span data-stu-id="caac7-587">Examples</span></span>

<span data-ttu-id="caac7-588">下圖說明如何使用滑鼠右鍵按一下右窗格中的連絡人，撥打或傳送 IM 給另一個代理。</span><span class="sxs-lookup"><span data-stu-id="caac7-588">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

![進行通話或傳送 IM。](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

<span data-ttu-id="caac7-590">下圖說明回應群組代理程式 Live 如何顯示目前佇列中的呼叫數目，以及所有來電間的最長等待時間。</span><span class="sxs-lookup"><span data-stu-id="caac7-590">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

![查看佇列資訊。](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a><span data-ttu-id="caac7-592">摘要</span><span class="sxs-lookup"><span data-stu-id="caac7-592">Summary</span></span>

<span data-ttu-id="caac7-593">Fast 登入和登出、群組成員資格及基本即時統計資料，都是只會在應用程式從回應群組服務外使用的回應群組代理功能。</span><span class="sxs-lookup"><span data-stu-id="caac7-593">Fast sign in and sign out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="caac7-594">透過「回應群組代理程式 Live Resource 工具組」工具，商務用 Skype Server 2015 系統管理員可以為其代理提供 Windows 應用程式，讓他們能夠以更快速且圖形的方式執行工作。</span><span class="sxs-lookup"><span data-stu-id="caac7-594">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

## <a name="sefautil"></a><span data-ttu-id="caac7-595">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="caac7-595">SEFAUtil</span></span>
<span data-ttu-id="caac7-596"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="caac7-596"><a name="SEFAUtil"> </a></span></span>

<span data-ttu-id="caac7-597">SEFAUtil (次要擴充功能啟動) 是一種命令列工具，可讓商務用 Skype Server 2015 通訊軟體管理員和技術支援人員代理程式，以設定代理人震鈴、呼叫轉寄、同時震鈴、「小組通話」設定和「群組呼叫」（「呼叫」設定和「群組通話」）代表商務用 Skype Server 2015 使用者。</span><span class="sxs-lookup"><span data-stu-id="caac7-597">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="caac7-598">工具也可讓系統管理員查詢特定使用者所發佈的呼叫路由設定。</span><span class="sxs-lookup"><span data-stu-id="caac7-598">The tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="caac7-599">SEFAUtil 工具可讓系統管理員為使用者啟用/停用/修改來電轉接或同時震鈴。</span><span class="sxs-lookup"><span data-stu-id="caac7-599">The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="caac7-600">管理員可以指定目標 (，格式為 SIP URI) 或使用已由使用者所發佈的目標。</span><span class="sxs-lookup"><span data-stu-id="caac7-600">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="caac7-601">這個工具也可讓系統管理員代表使用者新增或移除代理人或小組通話群組成員。</span><span class="sxs-lookup"><span data-stu-id="caac7-601">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.</span></span> <span data-ttu-id="caac7-602">此工具是在 Microsoft 整合通訊 Managed API (UCMA) 3.0 上建立，並且要求系統管理員在 SEFAUtil 的中央管理存放區中建立信任的應用程式。</span><span class="sxs-lookup"><span data-stu-id="caac7-602">This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>

<span data-ttu-id="caac7-603">SEFAUtil (次要擴充功能啟動) 可讓商務用 Skype Server 2015 系統管理員和技術支援人員，設定代理程式震鈴、呼叫轉寄、同時震鈴、「小組通話」設定和「群組呼叫」（「呼叫」設定和「群組呼叫」）代表一個商務用 Skype Server 2015 使用者</span><span class="sxs-lookup"><span data-stu-id="caac7-603">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="caac7-604">這個工具也可讓系統管理員查詢針對特定使用者所發佈的呼叫路由設定。</span><span class="sxs-lookup"><span data-stu-id="caac7-604">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

### <a name="description"></a><span data-ttu-id="caac7-605">描述</span><span class="sxs-lookup"><span data-stu-id="caac7-605">Description</span></span>

<span data-ttu-id="caac7-606">目前的 SEFAUtil 版本只是一個命令列工具;沒有支援的圖形使用者介面。</span><span class="sxs-lookup"><span data-stu-id="caac7-606">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="caac7-607">此工具是以 Microsoft 整合通訊 Managed API (UCMA) 3.0 為基礎。</span><span class="sxs-lookup"><span data-stu-id="caac7-607">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="caac7-608">此工具中的功能可讓系統管理員和支援人員執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="caac7-608">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

- <span data-ttu-id="caac7-609">View a user 的所有通話路由設定 (包括來電轉接、委派、同時震鈴、小組通話和群組通話收取) </span><span class="sxs-lookup"><span data-stu-id="caac7-609">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call, and group call pickup)</span></span>

- <span data-ttu-id="caac7-610">啟用/停用/修改來電轉接設定 (包括目的地及無回應計時器) </span><span class="sxs-lookup"><span data-stu-id="caac7-610">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

- <span data-ttu-id="caac7-611">啟用/停用/修改來電轉接立即設定</span><span class="sxs-lookup"><span data-stu-id="caac7-611">Enable/disable/modify call-forwarding immediate configurations</span></span>

- <span data-ttu-id="caac7-612">啟用/停用/修改委派設定</span><span class="sxs-lookup"><span data-stu-id="caac7-612">Enable/disable/modify delegation settings</span></span>

- <span data-ttu-id="caac7-613">啟用/停用/修改小組-通話群組設定</span><span class="sxs-lookup"><span data-stu-id="caac7-613">Enable/disable/modify team-call group settings</span></span>

    > [!NOTE]
    > <span data-ttu-id="caac7-614">商務用 Skype Server 2015 SEFAUtil 工具的新增功能</span><span class="sxs-lookup"><span data-stu-id="caac7-614">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="caac7-615">啟用/停用/修改同時震鈴設定 (包括目的地) </span><span class="sxs-lookup"><span data-stu-id="caac7-615">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>

    > [!NOTE]
    > <span data-ttu-id="caac7-616">商務用 Skype Server 2015 SEFAUtil 工具的新增功能</span><span class="sxs-lookup"><span data-stu-id="caac7-616">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="caac7-617">啟用/停用/修改群組呼叫收取設定</span><span class="sxs-lookup"><span data-stu-id="caac7-617">Enable/disable/modify group call pickup settings</span></span>

    > [!CAUTION]
    > <span data-ttu-id="caac7-618">商務用 Skype Server 2015 SEFAUtil 工具的新增功能</span><span class="sxs-lookup"><span data-stu-id="caac7-618">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

<span data-ttu-id="caac7-619">此工具具有下列限制：</span><span class="sxs-lookup"><span data-stu-id="caac7-619">This tool has the following limitations:</span></span>

- <span data-ttu-id="caac7-620">僅支援駐留在商務用 Skype Server 集區中的使用者</span><span class="sxs-lookup"><span data-stu-id="caac7-620">Supported only for users homed in a Skype for Business Server pool</span></span>

- <span data-ttu-id="caac7-621">不支援多個使用者的通話路由設定的大量編輯</span><span class="sxs-lookup"><span data-stu-id="caac7-621">Bulk-edit of call routing settings for several users is not supported</span></span>

### <a name="output"></a><span data-ttu-id="caac7-622">輸出</span><span class="sxs-lookup"><span data-stu-id="caac7-622">Output</span></span>

<span data-ttu-id="caac7-623">這個工具目前的版本只會在命令提示字元視窗中提供輸出。</span><span class="sxs-lookup"><span data-stu-id="caac7-623">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="caac7-624">如需詳細資訊，請參閱本檔稍後的範例一節。</span><span class="sxs-lookup"><span data-stu-id="caac7-624">For details, see the Examples section later in this document.</span></span>

### <a name="purpose"></a><span data-ttu-id="caac7-625">用途</span><span class="sxs-lookup"><span data-stu-id="caac7-625">Purpose</span></span>

<span data-ttu-id="caac7-626">以下是一些可能使用此工具的主要案例：</span><span class="sxs-lookup"><span data-stu-id="caac7-626">Following are some of the key scenarios where this tool may be used:</span></span>

- <span data-ttu-id="caac7-627">王俊元是執行程式，已移至商務用 Skype Server 電話語音。</span><span class="sxs-lookup"><span data-stu-id="caac7-627">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="caac7-628">他已在現有的 PBX 系統上進行委派。</span><span class="sxs-lookup"><span data-stu-id="caac7-628">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="caac7-629">在移動商務用 Skype Server 2015 時，系統管理員可以設定王俊元的路由，以反映其預先存在的委派設定。</span><span class="sxs-lookup"><span data-stu-id="caac7-629">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>

- <span data-ttu-id="caac7-630">劉愛琳在旅行中，意識到她期望來自他客戶的一項重要通話。</span><span class="sxs-lookup"><span data-stu-id="caac7-630">Alice is traveling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="caac7-631">不過，她位於酒店，而且無法存取電腦。</span><span class="sxs-lookup"><span data-stu-id="caac7-631">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="caac7-632">她撥打説明台，並要求他們將來電轉接給她的行動電話號碼。</span><span class="sxs-lookup"><span data-stu-id="caac7-632">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="caac7-633">服務台人員可以代表她執行設定。</span><span class="sxs-lookup"><span data-stu-id="caac7-633">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

- <span data-ttu-id="caac7-634">Joe 在工作時，他們的工作號碼會進入行動語音信箱。不過，在大多數其他位置中看起來似乎正常運作。</span><span class="sxs-lookup"><span data-stu-id="caac7-634">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="caac7-635">説明台技術人員可以查看 Joe 的路由設定，並探索李先生已設定為行動電話的同時震鈴。</span><span class="sxs-lookup"><span data-stu-id="caac7-635">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="caac7-636">技術人員會詢問 Joe 有關其辦公室內行動覆蓋率的資訊，並且能夠判斷同時響鈴的規則，也就是當網路服務品質不良的情況時，會導致來電進入 Joe 的行動電話語音信箱。</span><span class="sxs-lookup"><span data-stu-id="caac7-636">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>

- <span data-ttu-id="caac7-637">Mike 是 Contoso 的新員工，他加入新的小組，其所有成員皆為「小組通話」，當為商務用 Skype Server 2015 啟用時，系統管理員可以設定他的小組通話群組設定，以包含所有新的小組成員，此外，系統管理員會新增 Mike 作為小組中每個成員的小組通話群組成員。</span><span class="sxs-lookup"><span data-stu-id="caac7-637">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

- <span data-ttu-id="caac7-638">在 Contoso 的人力資源部門中，客戶服務實踐是為自第一次呼叫後的所有來電者提供個人服務。</span><span class="sxs-lookup"><span data-stu-id="caac7-638">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="caac7-639">假設部門的所有成員都非常接近對方，當小組通話中斷時，小組通話的所有電話都會中斷。</span><span class="sxs-lookup"><span data-stu-id="caac7-639">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is disruptive for the team.</span></span> <span data-ttu-id="caac7-640">若要提供最佳服務，而不中斷團隊成員，商務用 Skype Server 2015 系統管理員會利用群組呼叫收取功能。</span><span class="sxs-lookup"><span data-stu-id="caac7-640">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="caac7-641">系統管理員會將所有部門成員新增至收取群組，並與該部門通訊收取群組編號。</span><span class="sxs-lookup"><span data-stu-id="caac7-641">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="caac7-642">當她的辦公桌沒有 Samantha 時，Joe 會通知她的電話鈴聲，他會繼續接聽他的電話。</span><span class="sxs-lookup"><span data-stu-id="caac7-642">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

### <a name="requirements"></a><span data-ttu-id="caac7-643">需求</span><span class="sxs-lookup"><span data-stu-id="caac7-643">Requirements</span></span>

<span data-ttu-id="caac7-644">SEFAUtil 工具只能在屬於受信任應用程式集區一部分的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="caac7-644">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="caac7-645">UCMA 3.0 必須安裝在該電腦上。</span><span class="sxs-lookup"><span data-stu-id="caac7-645">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="caac7-646">若要執行此工具，必須在該集區上建立具有 SEFAUtil 應用程式識別碼的新信任應用程式。</span><span class="sxs-lookup"><span data-stu-id="caac7-646">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="caac7-647">為 SEFAUtil 工具建立新的信任應用程式</span><span class="sxs-lookup"><span data-stu-id="caac7-647">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="caac7-648">SEFAUTil 工具只能在屬於受信任應用程式集區一部分的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="caac7-648">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="caac7-649">如有需要，將集區新增為新的受信任應用程式集區，可透過使用下列 Cmdlet 的商務用 Skype Server 管理命令介面進行：</span><span class="sxs-lookup"><span data-stu-id="caac7-649">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > <span data-ttu-id="caac7-650">UCMA 3.0 必須安裝在將用來執行 SEFAUtil 工具的任何電腦上。</span><span class="sxs-lookup"><span data-stu-id="caac7-650">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

2. <span data-ttu-id="caac7-651">在 SEFAUtil 工具的拓撲中，必須定義信任的應用程式。</span><span class="sxs-lookup"><span data-stu-id="caac7-651">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="caac7-652">若要將 SEFAUtil 定義為新的受信任應用程式，請使用商務用 Skype Server 管理命令介面，並執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="caac7-652">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="caac7-653">您可以視需要使用不同的埠。</span><span class="sxs-lookup"><span data-stu-id="caac7-653">A different port can be used if needed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="caac7-654">集區 FQDN：將主控 SEFAUtil 應用程式之伺服器或集區的 fqdn (通常是商務用 Skype 前端伺服器 > 或集區) 。</span><span class="sxs-lookup"><span data-stu-id="caac7-654">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server     > or pool).</span></span>
    > <span data-ttu-id="caac7-655">集區報名者 fqdn：與此應用程式集區關聯的商務用 Skype 前端伺服器或集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="caac7-655">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="caac7-656">集區網站：此集區所在之網站的網站識別碼。</span><span class="sxs-lookup"><span data-stu-id="caac7-656">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

3. <span data-ttu-id="caac7-657">需要啟用拓撲變更。</span><span class="sxs-lookup"><span data-stu-id="caac7-657">The topology changes need to be enabled.</span></span> <span data-ttu-id="caac7-658">您可以透過執行下列 Cmdlet，透過商務用 Skype Server 管理命令介面來啟用拓撲變更：</span><span class="sxs-lookup"><span data-stu-id="caac7-658">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span>

   ```powershell
   Enable-CsToplogy
   ```

4. <span data-ttu-id="caac7-659">如有需要，請在伺服器上安裝商務用 Skype Server 2015 資源套件工具，以用於執行 SEFAUtil 工具 (伺服器必須是信任的應用程式集區) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="caac7-659">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5. <span data-ttu-id="caac7-660">驗證 SEFAUtil 是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="caac7-660">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="caac7-661">若要執行此動作，請從使用管理員許可權的 windows 命令提示字元執行工具，以顯示部署中使用者的「來電轉接」設定。</span><span class="sxs-lookup"><span data-stu-id="caac7-661">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="caac7-662">依預設，工具將位於： "..\Program Files \ 商務用 Skype Server 2015 \ Reskit"。</span><span class="sxs-lookup"><span data-stu-id="caac7-662">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="caac7-663">若要顯示使用者的「來電轉接」設定，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="caac7-663">To display the call forwarding settings of a user, use the following command:</span></span>

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    <span data-ttu-id="caac7-664">應該顯示使用者的「來電轉接」設定。</span><span class="sxs-lookup"><span data-stu-id="caac7-664">The call forwarding settings of the user should be displayed.</span></span>

#### <a name="group-call-pickup"></a><span data-ttu-id="caac7-665">群組來電接聽</span><span class="sxs-lookup"><span data-stu-id="caac7-665">Group Call Pickup</span></span>

<span data-ttu-id="caac7-666">群組呼叫收取需要在商務用 Skype Server 2015 中進行其他設定，才能充分啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="caac7-666">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="caac7-667">在指派收取群組給使用者之前，請參閱群組的「呼叫收取產品檔」，以取得這項功能的規劃及部署步驟。</span><span class="sxs-lookup"><span data-stu-id="caac7-667">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

### <a name="examples"></a><span data-ttu-id="caac7-668">範例</span><span class="sxs-lookup"><span data-stu-id="caac7-668">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="caac7-669">顯示目前的通話處理設定</span><span class="sxs-lookup"><span data-stu-id="caac7-669">Display Current Call Handling Settings</span></span>

<span data-ttu-id="caac7-670">下列命令會顯示使用者的通話處理。</span><span class="sxs-lookup"><span data-stu-id="caac7-670">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> <span data-ttu-id="caac7-671">這個範例會使用 **/server** 參數來指定要連接的商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="caac7-671">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>

 <span data-ttu-id="caac7-672">**輸出**</span><span class="sxs-lookup"><span data-stu-id="caac7-672">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="caac7-673">設定來電轉接/無應答目的地</span><span class="sxs-lookup"><span data-stu-id="caac7-673">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="caac7-674">本範例會設定來電轉寄/無應答目的地和震鈴延遲。</span><span class="sxs-lookup"><span data-stu-id="caac7-674">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="caac7-675">這裡未提供/server 參數;SEFAUtil 會嘗試自動探索商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="caac7-675">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+14255550126@contoso.com;user=phone
```

 <span data-ttu-id="caac7-676">**輸出**</span><span class="sxs-lookup"><span data-stu-id="caac7-676">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="caac7-677">立即啟用來電轉接</span><span class="sxs-lookup"><span data-stu-id="caac7-677">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="caac7-678">本範例會立即對其他使用者啟用來電轉接。</span><span class="sxs-lookup"><span data-stu-id="caac7-678">This example immediately enables call-forwarding to another user.</span></span>

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="caac7-679">**輸出**</span><span class="sxs-lookup"><span data-stu-id="caac7-679">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="caac7-680">立即停用來電轉接</span><span class="sxs-lookup"><span data-stu-id="caac7-680">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="caac7-681">本範例會立即停用來電轉接。</span><span class="sxs-lookup"><span data-stu-id="caac7-681">This example immediately disables call forwarding.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com /disablefwdimmediate
```

 <span data-ttu-id="caac7-682">**輸出**</span><span class="sxs-lookup"><span data-stu-id="caac7-682">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="caac7-683">將使用者新增為代理人，並設定代理人同時震鈴</span><span class="sxs-lookup"><span data-stu-id="caac7-683">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="caac7-684">這則範例會將使用者新增為代理人，並設定同時響鈴的代理人。</span><span class="sxs-lookup"><span data-stu-id="caac7-684">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="caac7-685">**輸出**</span><span class="sxs-lookup"><span data-stu-id="caac7-685">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="caac7-686">變更代理人的同時震鈴規則</span><span class="sxs-lookup"><span data-stu-id="caac7-686">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="caac7-687">這個範例會將上一個範例中設定的同時震鈴規則變更為延遲的震鈴規則。</span><span class="sxs-lookup"><span data-stu-id="caac7-687">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="caac7-688">**輸出**</span><span class="sxs-lookup"><span data-stu-id="caac7-688">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="caac7-689">移除代理人</span><span class="sxs-lookup"><span data-stu-id="caac7-689">Remove the Delegate</span></span>

<span data-ttu-id="caac7-690">本範例會移除代理人。</span><span class="sxs-lookup"><span data-stu-id="caac7-690">This example removes the delegate.</span></span>

> [!NOTE]
> <span data-ttu-id="caac7-691">移除最後一個代理人時，會自動停用代理人震鈴。</span><span class="sxs-lookup"><span data-stu-id="caac7-691">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="caac7-692">**輸出**</span><span class="sxs-lookup"><span data-stu-id="caac7-692">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="caac7-693">新增代理人並設定 Call-Forward 至代理人規則</span><span class="sxs-lookup"><span data-stu-id="caac7-693">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="caac7-694">這則範例會新增代理人，並設定「呼叫轉寄至代理人規則。</span><span class="sxs-lookup"><span data-stu-id="caac7-694">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="caac7-695">**輸出**</span><span class="sxs-lookup"><span data-stu-id="caac7-695">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="caac7-696">啟用同時震鈴和設定目的地號碼</span><span class="sxs-lookup"><span data-stu-id="caac7-696">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="caac7-697">本範例啟用同時震鈴，並設定同時震鈴目的地號碼。</span><span class="sxs-lookup"><span data-stu-id="caac7-697">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="caac7-698">若要變更已啟用同時震鈴之使用者的同時震鈴目的地數目，請使用/enablesimulring 參數保留該命令，否則將不會變更目的地號碼。</span><span class="sxs-lookup"><span data-stu-id="caac7-698">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>

 <span data-ttu-id="caac7-699">**輸出**</span><span class="sxs-lookup"><span data-stu-id="caac7-699">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="caac7-700">停用同時震鈴</span><span class="sxs-lookup"><span data-stu-id="caac7-700">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="caac7-701">本範例會停用同時震鈴。</span><span class="sxs-lookup"><span data-stu-id="caac7-701">This example disables simultaneous ringing.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="caac7-702">**輸出**</span><span class="sxs-lookup"><span data-stu-id="caac7-702">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="caac7-703">新增 Team-Call 的團隊成員，並設定同時響鈴至 Team-Call 成員群組</span><span class="sxs-lookup"><span data-stu-id="caac7-703">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="caac7-704">這則範例會將小組成員新增至使用者的「小組通話群組」，並啟用對小組通話群組的同時震鈴。</span><span class="sxs-lookup"><span data-stu-id="caac7-704">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="caac7-705">將成員新增至使用者的小組通話群組，會自動切換使用者的同時振鈴 settigs，以便同時振鈴其團隊通話群組。</span><span class="sxs-lookup"><span data-stu-id="caac7-705">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simultaneous ring his team-call group.</span></span>

 <span data-ttu-id="caac7-706">**輸出**</span><span class="sxs-lookup"><span data-stu-id="caac7-706">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="caac7-707">從 Team-Call 群組中移除成員</span><span class="sxs-lookup"><span data-stu-id="caac7-707">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="caac7-708">此範例會移除使用者之團隊通話群組的小組成員。</span><span class="sxs-lookup"><span data-stu-id="caac7-708">This example removes a team member of the team-call group of a user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="caac7-709">若要移除的成員是小組通話群組的唯一成員，同時震鈴到小組通話群組將會自動停用。</span><span class="sxs-lookup"><span data-stu-id="caac7-709">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>

 <span data-ttu-id="caac7-710">**輸出**</span><span class="sxs-lookup"><span data-stu-id="caac7-710">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="caac7-711">將延遲的環設定為 Team-Call 群組</span><span class="sxs-lookup"><span data-stu-id="caac7-711">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="caac7-712">本範例會將延遲的環變更為「小組通話群組時間」設定。</span><span class="sxs-lookup"><span data-stu-id="caac7-712">This example changes the delayed ring to the team-call group time setting.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="caac7-713">**輸出**</span><span class="sxs-lookup"><span data-stu-id="caac7-713">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="caac7-714">啟用 Team-Call</span><span class="sxs-lookup"><span data-stu-id="caac7-714">Enable Team-Call</span></span>

<span data-ttu-id="caac7-715">本範例會為指定的使用者啟用小組通話。</span><span class="sxs-lookup"><span data-stu-id="caac7-715">This example enables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="caac7-716">如果使用者的小組通話群組沒有成員，將不會啟用小組通話。</span><span class="sxs-lookup"><span data-stu-id="caac7-716">If the team-call group of the user has no members, team-call won't be enabled.</span></span>

 <span data-ttu-id="caac7-717">**輸出**</span><span class="sxs-lookup"><span data-stu-id="caac7-717">**Output**</span></span>

#### <a name="disable-team-call"></a><span data-ttu-id="caac7-718">停用 Team-Call</span><span class="sxs-lookup"><span data-stu-id="caac7-718">Disable Team-Call</span></span>

<span data-ttu-id="caac7-719">本範例會停用指定使用者的「小組通話」。</span><span class="sxs-lookup"><span data-stu-id="caac7-719">This example disables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="caac7-720">**輸出**</span><span class="sxs-lookup"><span data-stu-id="caac7-720">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="caac7-721">啟用群組呼叫收取並指派收取群組給使用者</span><span class="sxs-lookup"><span data-stu-id="caac7-721">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="caac7-722">這則範例會將收取群組指派給使用者，並啟用群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="caac7-722">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="caac7-723">**輸出**</span><span class="sxs-lookup"><span data-stu-id="caac7-723">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="caac7-724">停用組來電收取</span><span class="sxs-lookup"><span data-stu-id="caac7-724">Disable Group Call Pickup</span></span>

<span data-ttu-id="caac7-725">本範例會停用指定使用者的群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="caac7-725">This example disables Group Call Pickup for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="caac7-726">當您停用使用者的群組呼叫收取時，指派給使用者的群組號碼不會保留。</span><span class="sxs-lookup"><span data-stu-id="caac7-726">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="caac7-727">如果您後來想要為該使用者重新啟用群組呼叫收取，您必須使用/enablegrouppickup 參數再次指派群組號碼。</span><span class="sxs-lookup"><span data-stu-id="caac7-727">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="caac7-728">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="caac7-728">SYSPrep.ps1</span></span>
<span data-ttu-id="caac7-729"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="caac7-729"><a name="SYSPrep"> </a></span></span>

### <a name="description"></a><span data-ttu-id="caac7-730">描述</span><span class="sxs-lookup"><span data-stu-id="caac7-730">Description</span></span>

<span data-ttu-id="caac7-731">SYSPrep.ps1 是 Windows PowerShell 腳本，它會在您的 Windows Server 2008 作業系統機器上安裝下列商務用 Skype Server 2015 必要條件。</span><span class="sxs-lookup"><span data-stu-id="caac7-731">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>

- <span data-ttu-id="caac7-732">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="caac7-732">Microsoft .NET Framework 4.5</span></span>

- <span data-ttu-id="caac7-733">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="caac7-733">Microsoft SQL Server Express</span></span>

- <span data-ttu-id="caac7-734">Windows PowerShell 版本3。0</span><span class="sxs-lookup"><span data-stu-id="caac7-734">Windows PowerShell version 3.0</span></span>

- <span data-ttu-id="caac7-735">Visual c + + 2010 可轉散發元件</span><span class="sxs-lookup"><span data-stu-id="caac7-735">Visual C++ 2010 Redistributable</span></span>

- <span data-ttu-id="caac7-736">網際網路資訊伺服器更新</span><span class="sxs-lookup"><span data-stu-id="caac7-736">Internet Information Server Updates</span></span>

- <span data-ttu-id="caac7-737">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="caac7-737">Windows Identity Foundation</span></span>

- <span data-ttu-id="caac7-738">商務用 Skype Server 2015 核心檔案</span><span class="sxs-lookup"><span data-stu-id="caac7-738">Skype for Business Server 2015 Core files</span></span>

  <span data-ttu-id="caac7-739">雖然腳本名稱類似 Microsoft Windows 作業系統的系統準備工具，但它們是不同的。</span><span class="sxs-lookup"><span data-stu-id="caac7-739">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="caac7-740">此腳本只會為商務用 Skype Server 2015 安裝必要的必要條件。</span><span class="sxs-lookup"><span data-stu-id="caac7-740">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="caac7-741">安裝這些必要條件之後，Windows SYSPrep 工具可以用來建立伺服器的影像。</span><span class="sxs-lookup"><span data-stu-id="caac7-741">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

### <a name="requirements"></a><span data-ttu-id="caac7-742">需求</span><span class="sxs-lookup"><span data-stu-id="caac7-742">Requirements</span></span>

<span data-ttu-id="caac7-743">在執行 SYSPrep.ps1 腳本之前，您必須將必要條件檔案複製到 Windows Server 2008 作業系統機 (上的本機資料夾，例如 **D:\Setup)**。</span><span class="sxs-lookup"><span data-stu-id="caac7-743">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="caac7-744">這個資料夾還必須包括商務用 Skype Server 2015 檔案的複本，特別是 **Setup.exe。**</span><span class="sxs-lookup"><span data-stu-id="caac7-744">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="caac7-745">您可以從下列位置下載必要檔：</span><span class="sxs-lookup"><span data-stu-id="caac7-745">The prerequisite files can be downloaded from the following locations:</span></span>


| <span data-ttu-id="caac7-746">**先決條件**</span><span class="sxs-lookup"><span data-stu-id="caac7-746">**Prerequisite**</span></span>                                | <span data-ttu-id="caac7-747">**位置**</span><span class="sxs-lookup"><span data-stu-id="caac7-747">**Location**</span></span>                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| <span data-ttu-id="caac7-748">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="caac7-748">Microsoft .NET Framework 4.5</span></span>  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| <span data-ttu-id="caac7-749">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="caac7-749">Microsoft SQL Server Express 2008 R2</span></span>  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| <span data-ttu-id="caac7-750">Windows PowerShell 版本3。0</span><span class="sxs-lookup"><span data-stu-id="caac7-750">Windows PowerShell version 3.0</span></span>  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| <span data-ttu-id="caac7-751">Visual c + + 2010 可轉散發元件</span><span class="sxs-lookup"><span data-stu-id="caac7-751">Visual C++ 2010 Redistributable</span></span>  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| <span data-ttu-id="caac7-752">網際網路資訊伺服器更新</span><span class="sxs-lookup"><span data-stu-id="caac7-752">Internet Information Server Updates</span></span>  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| <span data-ttu-id="caac7-753">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="caac7-753">Windows Identity Foundation</span></span>  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| <span data-ttu-id="caac7-754">商務用 Skype Server 2015 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="caac7-754">Skype for Business Server 2015 Setup.exe</span></span>  <br/> | <span data-ttu-id="caac7-755">從商務用 Skype Server 2015 媒體複製</span><span class="sxs-lookup"><span data-stu-id="caac7-755">Copy from Skype for Business Server 2015 media</span></span>  <br/>                   |

### <a name="parameter"></a><span data-ttu-id="caac7-756">參數</span><span class="sxs-lookup"><span data-stu-id="caac7-756">Parameter</span></span>

<span data-ttu-id="caac7-757">**-SetupFolder** 參數會將必要條件檔案的目錄位置當作引數。</span><span class="sxs-lookup"><span data-stu-id="caac7-757">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

### <a name="examples"></a><span data-ttu-id="caac7-758">範例</span><span class="sxs-lookup"><span data-stu-id="caac7-758">Examples</span></span>

<span data-ttu-id="caac7-759">若要執行 SYSPrep.ps1 腳本，並安裝商務用 Skype Server 2015 必要條件，請從提升許可權的命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="caac7-759">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="caac7-760">未指派號碼宣告遷移</span><span class="sxs-lookup"><span data-stu-id="caac7-760">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="caac7-761"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="caac7-761"><a name="UNAM"> </a></span></span>

<span data-ttu-id="caac7-762">「未指派的號碼宣告」遷移工具可讓商務用 Skype Server 2015 系統管理員將宣告應用程式所提供的未指派號碼設定從來源商務用 Skype Server 或集區移至目的地商務用 Skype Server 或集區。</span><span class="sxs-lookup"><span data-stu-id="caac7-762">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>

### <a name="description"></a><span data-ttu-id="caac7-763">描述</span><span class="sxs-lookup"><span data-stu-id="caac7-763">Description</span></span>

<span data-ttu-id="caac7-764">「未指派號碼宣告」遷移工具是一 Windows PowerShell 腳本，可將來源伺服器或集區之宣告應用程式所提供的未指派號碼設定移至不同的伺服器或集區。</span><span class="sxs-lookup"><span data-stu-id="caac7-764">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="caac7-765">執行時，未指派的號碼宣告遷移腳本會執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="caac7-765">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1. <span data-ttu-id="caac7-766">將來源伺服器或集區中主控之宣告應用程式的未指派號碼宣告所使用的所有音訊檔，移至目的地伺服器或集區的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="caac7-766">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="caac7-767">將音訊檔複製到目的地集區之後，會從來源集區中移除。</span><span class="sxs-lookup"><span data-stu-id="caac7-767">The audio files are removed from the source pool once they're copied to the destination pool.</span></span>

2. <span data-ttu-id="caac7-768">將來源伺服器或集區中主控的宣告應用程式設定的所有未指派號碼的宣告移至目的地伺服器或集區。</span><span class="sxs-lookup"><span data-stu-id="caac7-768">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3. <span data-ttu-id="caac7-769">將來源伺服器或集區中主控的宣告應用程式所提供的所有未指派號碼範圍重新指派給目的地伺服器或集區。</span><span class="sxs-lookup"><span data-stu-id="caac7-769">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="caac7-770">順利執行腳本後，來源伺服器或集區中所主控的宣告應用程式所提供的所有未指派號碼範圍，都將會以目標伺服器或集區的相同設定進行服務。</span><span class="sxs-lookup"><span data-stu-id="caac7-770">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

### <a name="output"></a><span data-ttu-id="caac7-771">輸出</span><span class="sxs-lookup"><span data-stu-id="caac7-771">Output</span></span>

<span data-ttu-id="caac7-772">**Move-CsAnnouncementConfiguration** 腳本會指出商務用 Skype Server 管理命令介面視窗中執行遷移作業成功或失敗的地方。</span><span class="sxs-lookup"><span data-stu-id="caac7-772">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="caac7-773">如果執行作業時因任何錯誤而中斷，已順利移至目的地的未指派號碼範圍仍會保留在操作表單的目的地中，而且其他未指派的號碼範圍仍會保留在來源中，也就是在運作表單中。</span><span class="sxs-lookup"><span data-stu-id="caac7-773">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="caac7-774">若要完全遷移其他設定，請在解決錯誤之後重新執行腳本。</span><span class="sxs-lookup"><span data-stu-id="caac7-774">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

### <a name="purpose"></a><span data-ttu-id="caac7-775">用途</span><span class="sxs-lookup"><span data-stu-id="caac7-775">Purpose</span></span>

<span data-ttu-id="caac7-776">未指派號碼宣告遷移腳本可用於下列三種情況：</span><span class="sxs-lookup"><span data-stu-id="caac7-776">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

- <span data-ttu-id="caac7-777">**將設定設定遷移至新版本的商務用 Skype Server：** Contoso 正在遷移至商務用 Skype Server 2015，並做為遷移程式的一部分，商務用 Skype Server 管理員想要將宣告應用程式所提供的未指派號碼設定從 Lync Server 2013 部署移動到新的商務用 Skype Server 2015 部署。</span><span class="sxs-lookup"><span data-stu-id="caac7-777">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="caac7-778">商務用 Skype Server 管理員使用「未指派的號碼宣告遷移」工具來移動設定設定。</span><span class="sxs-lookup"><span data-stu-id="caac7-778">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

- <span data-ttu-id="caac7-779">**從商務用 Skype Server 2015 向 Lync Server 2013 復原部署：** 由於非預期的因素，Contoso 必須將遷移移至新的商務用 Skype Server 2015 部署。</span><span class="sxs-lookup"><span data-stu-id="caac7-779">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="caac7-780">為了將中斷服務的中斷降至最低，商務用 Skype Server 管理員會使用「未指派的號碼宣告遷移」工具，將設定從商務用 Skype Server 2015 部署復原至 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="caac7-780">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>

- <span data-ttu-id="caac7-781">**在部署之間移動資料：** Contoso 正在將一個集區的所有伺服器取代為更新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="caac7-781">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="caac7-782">其策略是部署新的商務用 Skype Server 2015 集區、將舊資料移至新集區，然後取代舊的集區。</span><span class="sxs-lookup"><span data-stu-id="caac7-782">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="caac7-783">部署新集區之後，就會使用「未指派號碼宣告」遷移工具，將設定從舊集區移至新集區。</span><span class="sxs-lookup"><span data-stu-id="caac7-783">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

#### <a name="requirements"></a><span data-ttu-id="caac7-784">需求</span><span class="sxs-lookup"><span data-stu-id="caac7-784">Requirements</span></span>

<span data-ttu-id="caac7-785">以下是成功執行工具所需的主要需求：</span><span class="sxs-lookup"><span data-stu-id="caac7-785">The following are the main requirements needed to successfully run the tool:</span></span>

1. <span data-ttu-id="caac7-786">腳本必須從已安裝商務用 Skype Server 管理命令介面的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="caac7-786">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>

2. <span data-ttu-id="caac7-787">必須在來源和目的地商務用 Skype 伺服器或集區中成功部署宣告應用程式。</span><span class="sxs-lookup"><span data-stu-id="caac7-787">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>

#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="caac7-788">Move-CsAnnouncementConfiguration 腳本</span><span class="sxs-lookup"><span data-stu-id="caac7-788">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="caac7-789">Move-CsAnnouncementConfiguration 腳本需要下表中所述的兩個參數。</span><span class="sxs-lookup"><span data-stu-id="caac7-789">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

![Move-CsAnnouncementConfiguration 參數。](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a><span data-ttu-id="caac7-791">範例</span><span class="sxs-lookup"><span data-stu-id="caac7-791">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="caac7-792">將未指派號碼的宣告設定從 Lync Server 2013 集區移至商務用 Skype Server 2015 集區</span><span class="sxs-lookup"><span data-stu-id="caac7-792">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="caac7-793">這個範例會將來源集區中未指派的號碼宣告 (Lync Server 2013) 移至目的地集區 (商務用 Skype Server 2015) 。</span><span class="sxs-lookup"><span data-stu-id="caac7-793">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="caac7-794">將未指派號碼的宣告設定從商務用 Skype Server 2015 集區移至 Lync Server 2013 集區</span><span class="sxs-lookup"><span data-stu-id="caac7-794">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="caac7-795">這個範例會將來源集區 (商務用 Skype Server 2015) 的未指派號碼宣告，移至目的地集區 (Lync Server 2013) 。</span><span class="sxs-lookup"><span data-stu-id="caac7-795">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="caac7-796">網路會議資料</span><span class="sxs-lookup"><span data-stu-id="caac7-796">Web Conf Data</span></span>
<span data-ttu-id="caac7-797"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="caac7-797"><a name="WebConfData"> </a></span></span>

<span data-ttu-id="caac7-798">Web 會議資料工具可讓商務用 Skype Server 2015 通訊軟體的系統管理員，對與召集人的 Web 會議相關聯的資料進行更多控制。</span><span class="sxs-lookup"><span data-stu-id="caac7-798">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="caac7-799">案例包括根據時間戳記準則刪除特定使用者的會議資料的功能。</span><span class="sxs-lookup"><span data-stu-id="caac7-799">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>

### <a name="description"></a><span data-ttu-id="caac7-800">描述</span><span class="sxs-lookup"><span data-stu-id="caac7-800">Description</span></span>

<span data-ttu-id="caac7-801">此工具可讓系統管理員執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="caac7-801">This tool allows the administrator to perform the following operations:</span></span>

1. <span data-ttu-id="caac7-802">尋找與單一使用者相關聯的所有 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="caac7-802">Find all Web conferencing data associated with a single user.</span></span>

2. <span data-ttu-id="caac7-803">刪除所有與單一使用者相關聯的 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="caac7-803">Delete all Web conferencing data associated with a single user.</span></span>

3. <span data-ttu-id="caac7-804">刪除與特定日期舊的單一使用者相關聯的所有 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="caac7-804">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4. <span data-ttu-id="caac7-805">當使用者從一個集區移至另一個集區時，移動所有與單一使用者相關聯的 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="caac7-805">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

    > [!NOTE]
    > <span data-ttu-id="caac7-806">Lync Server 2010 的資源工具組工具支援在使用者從一個集區移至另一個集區時，移動所有與單一使用者相關聯的 Web 會議資料。</span><span class="sxs-lookup"><span data-stu-id="caac7-806">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="caac7-807">這項功能現在已被取代為此工具，取而代之的 **MoveConferenceData** 參數。</span><span class="sxs-lookup"><span data-stu-id="caac7-807">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="caac7-808">如需此參數的詳細資訊，請參閱 [Move-CsUser](/powershell/module/skype/move-csuser?) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="caac7-808">For details about this parameter, see the [Move-CsUser](/powershell/module/skype/move-csuser?) cmdlet.</span></span>

<span data-ttu-id="caac7-809">工具只會刪除非使用中會議的會議資料。</span><span class="sxs-lookup"><span data-stu-id="caac7-809">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="caac7-810">無法刪除會話) 中的使用中會議 (或會議。</span><span class="sxs-lookup"><span data-stu-id="caac7-810">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="caac7-811">此工具必須從與目標使用者位於相同集區的電腦執行。</span><span class="sxs-lookup"><span data-stu-id="caac7-811">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="caac7-812">使用此工具管理其會議內容資料的使用者，必須位於相同的使用者集區中。</span><span class="sxs-lookup"><span data-stu-id="caac7-812">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

### <a name="output"></a><span data-ttu-id="caac7-813">輸出</span><span class="sxs-lookup"><span data-stu-id="caac7-813">Output</span></span>

<span data-ttu-id="caac7-814">此工具會輸出各項作業的結果：</span><span class="sxs-lookup"><span data-stu-id="caac7-814">This tool outputs the results of each of the operations:</span></span>

- <span data-ttu-id="caac7-815">如果執行查詢，則該工具會將所有非使用中會議資料檔案夾的清單，輸出為召集人。</span><span class="sxs-lookup"><span data-stu-id="caac7-815">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

- <span data-ttu-id="caac7-816">若執行刪除，該工具會輸出其資料將被刪除的所有會議資料資料夾清單。</span><span class="sxs-lookup"><span data-stu-id="caac7-816">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

### <a name="requirements"></a><span data-ttu-id="caac7-817">需求</span><span class="sxs-lookup"><span data-stu-id="caac7-817">Requirements</span></span>

<span data-ttu-id="caac7-818">需要在召集人目前所在的相同集區中執行工具。</span><span class="sxs-lookup"><span data-stu-id="caac7-818">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="caac7-819">您必須使用管理員許可權執行該工具，才能存取內容檔存放區。</span><span class="sxs-lookup"><span data-stu-id="caac7-819">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

### <a name="examples"></a><span data-ttu-id="caac7-820">範例</span><span class="sxs-lookup"><span data-stu-id="caac7-820">Examples</span></span>

<span data-ttu-id="caac7-821">下表說明這些參數，其中一些是範例中使用的參數。</span><span class="sxs-lookup"><span data-stu-id="caac7-821">The following table describes the parameters, some of which are used in the examples.</span></span>

![Web 會議資料工具參數。](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="caac7-823">上述範例顯示查詢命令的運作方式。</span><span class="sxs-lookup"><span data-stu-id="caac7-823">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="caac7-824">這類命令的輸出會是受此工具影響的所有會議內容資料夾清單。</span><span class="sxs-lookup"><span data-stu-id="caac7-824">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="caac7-825">上述為刪除命令的範例。</span><span class="sxs-lookup"><span data-stu-id="caac7-825">The preceding is an example of a delete command.</span></span> <span data-ttu-id="caac7-826">[刪除] 命令將從此使用者移除所有非使用中的會議資料夾。</span><span class="sxs-lookup"><span data-stu-id="caac7-826">The delete command will remove all inactive meeting folders from this user.</span></span>

### <a name="summary"></a><span data-ttu-id="caac7-827">摘要</span><span class="sxs-lookup"><span data-stu-id="caac7-827">Summary</span></span>

<span data-ttu-id="caac7-828">對於需要更精確控制會議會議資料的系統管理員，此工具是一種重要資源。</span><span class="sxs-lookup"><span data-stu-id="caac7-828">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>

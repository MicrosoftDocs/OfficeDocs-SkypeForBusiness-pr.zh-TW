---
title: 瞭解集中式記錄服務配置設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Centralized Logging Service configuration settings
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49733619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a766756f082e6666d37dff793c457cb335736fe0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="72732-102">瞭解 Lync Server 2013 中的集中式記錄服務配置設定</span><span class="sxs-lookup"><span data-stu-id="72732-102">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72732-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="72732-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="72732-104">集中式記錄服務會設定為定義記錄服務的預期收集方式、收集方式、收集來源，以及記錄設定的位置。</span><span class="sxs-lookup"><span data-stu-id="72732-104">The Centralized Logging Service is configured to define what the logging service is intended to collect, how it collects, where it will collect from, and what the log settings are.</span></span> <span data-ttu-id="72732-105">您可以全域定義這些設定（也就是整個部署）或網站（也就是您部署中的命名網站）。</span><span class="sxs-lookup"><span data-stu-id="72732-105">You define these settings globally (that is, for the entire deployment) or for a site (that is, a named site in your deployment).</span></span> <span data-ttu-id="72732-106">您定義的任何記錄，都會使用適合用來啟動、停止、清除及搜尋記錄的身分識別的設定。</span><span class="sxs-lookup"><span data-stu-id="72732-106">Any logging that you define will use the settings that are appropriate for the identity that you use for commands to start, stop, flush, and search logs.</span></span>

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="72732-107">顯示目前的集中式記錄服務設定</span><span class="sxs-lookup"><span data-stu-id="72732-107">To display the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="72732-108">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="72732-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="72732-109">在命令列提示處輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="72732-109">Type the following at a command-line prompt:</span></span>
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > <span data-ttu-id="72732-110">您可以縮小或擴大由定義<CODE>-Identity</CODE>和範圍（例如「Site：北京」）傳回的設定設定範圍，只傳回網站雷蒙德的 CsClsConfiguration。</span><span class="sxs-lookup"><span data-stu-id="72732-110">You can narrow or expand the scope of the configuration settings that are returned by defining <CODE>-Identity</CODE> and a scope, such as "Site:Redmond" to return only the CsClsConfiguration for the site Redmond.</span></span> <span data-ttu-id="72732-111">如果您想要有關設定的指定部分的詳細資料，您可以將輸出輸送至另一個 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="72732-111">If you want details about a given portion of the configuration, you can pipe the output into another Windows PowerShell cmdlet.</span></span> <span data-ttu-id="72732-112">例如，若要取得網站「雷蒙德」設定中所定義之案例的詳細資料，請輸入：<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span><span class="sxs-lookup"><span data-stu-id="72732-112">For example, to get details about the scenarios defined in the configuration for site "Redmond", type: <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span></span>

    
    </div>
    
    <span data-ttu-id="72732-113">![Get-CsClsConfiguration 輸出範例。](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Get-CsClsConfiguration 輸出範例。")</span><span class="sxs-lookup"><span data-stu-id="72732-113">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>
    
    <span data-ttu-id="72732-114">此 Cmdlet 的結果會顯示集中式記錄服務的目前設定。</span><span class="sxs-lookup"><span data-stu-id="72732-114">The result from the cmdlet displays the current configuration of the Centralized Logging Service.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="72732-115">配置設定</span><span class="sxs-lookup"><span data-stu-id="72732-115">Configuration Setting</span></span></th>
    <th><span data-ttu-id="72732-116">說明</span><span class="sxs-lookup"><span data-stu-id="72732-116">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="72732-117"><strong>Identity</strong></span><span class="sxs-lookup"><span data-stu-id="72732-117"><strong>Identity</strong></span></span></p></td>
    <td><p><span data-ttu-id="72732-118">識別此設定的範圍和名稱。</span><span class="sxs-lookup"><span data-stu-id="72732-118">Identifies the scope and name for this configuration.</span></span> <span data-ttu-id="72732-119">只有一個全域配置，且每個網站都有一個設定。</span><span class="sxs-lookup"><span data-stu-id="72732-119">There is only one Global configuration, and one configuration per site.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="72732-120"><strong>案例</strong></span><span class="sxs-lookup"><span data-stu-id="72732-120"><strong>Scenarios</strong></span></span></p></td>
    <td><p><span data-ttu-id="72732-121">此設定所定義之所有案例的清單。</span><span class="sxs-lookup"><span data-stu-id="72732-121">Listing of all scenarios that are defined for this configuration.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="72732-122"><strong>SearchTerms</strong></span><span class="sxs-lookup"><span data-stu-id="72732-122"><strong>SearchTerms</strong></span></span></p></td>
    <td><p><span data-ttu-id="72732-123">已定義配置的搜尋字詞。</span><span class="sxs-lookup"><span data-stu-id="72732-123">Defined search terms for the configuration.</span></span> <span data-ttu-id="72732-124">Office 365，而非內部部署。</span><span class="sxs-lookup"><span data-stu-id="72732-124">Office 365, not on-premises deployments.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="72732-125"><strong>SecurityGroups</strong></span><span class="sxs-lookup"><span data-stu-id="72732-125"><strong>SecurityGroups</strong></span></span></p></td>
    <td><p><span data-ttu-id="72732-126">已定義的安全性群組可控制誰（也就是安全性群組的成員）可以查看以他們所在的網站為基礎的電腦。</span><span class="sxs-lookup"><span data-stu-id="72732-126">Defined security groups that control who (that is, members of the security groups) can see computers based on the site they are located in.</span></span> <span data-ttu-id="72732-127">在此內容中，網站是在拓撲建立器中定義的網站。</span><span class="sxs-lookup"><span data-stu-id="72732-127">Site, in this context, is the site as defined in Topology Builder.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="72732-128"><strong>地區</strong></span><span class="sxs-lookup"><span data-stu-id="72732-128"><strong>Regions</strong></span></span></p></td>
    <td><p><span data-ttu-id="72732-129">已定義的區域是用來將 SecurityGroups 收集到某個地區（例如 EMEA）。</span><span class="sxs-lookup"><span data-stu-id="72732-129">Defined regions are used to collect SecurityGroups into a region, for example EMEA.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="72732-130"><strong>EtlFileFolder</strong></span><span class="sxs-lookup"><span data-stu-id="72732-130"><strong>EtlFileFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="72732-131">已定義在電腦上寫入記錄檔案之位置的路徑。</span><span class="sxs-lookup"><span data-stu-id="72732-131">Defined path to the location where log files are written on computers.</span></span> <span data-ttu-id="72732-132">CLSAgent 會寫入記錄檔，並在網路服務的內容下執行。</span><span class="sxs-lookup"><span data-stu-id="72732-132">CLSAgent writes the log files and runs under the context of the Network Service.</span></span> <span data-ttu-id="72732-133">在此案例中，% TEMP% 會展開為%WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span><span class="sxs-lookup"><span data-stu-id="72732-133">In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="72732-134"><strong>EtlFileRolloverSizeMB</strong></span><span class="sxs-lookup"><span data-stu-id="72732-134"><strong>EtlFileRolloverSizeMB</strong></span></span></p></td>
    <td><p><span data-ttu-id="72732-135">在建立新的事件追蹤記錄（.etl）檔案之前，此參數會指出記錄檔的大小上限。</span><span class="sxs-lookup"><span data-stu-id="72732-135">The parameter indicates the maximum size of the log file before a new event trace log (.etl) file is created.</span></span> <span data-ttu-id="72732-136">即使在 EtlFileRolloverMinutes 中設定的最大時間尚未達到，也會在已定義的大小達到時建立新的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="72732-136">A new log file is created when the defined size is reached even if the maximum time set in EtlFileRolloverMinutes has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="72732-137"><strong>EtlFileRolloverMinutes</strong></span><span class="sxs-lookup"><span data-stu-id="72732-137"><strong>EtlFileRolloverMinutes</strong></span></span></p></td>
    <td><p><span data-ttu-id="72732-138">已定義在建立新的 .etl 檔案之前可以經過的最大時間長度（以分鐘為單位）。</span><span class="sxs-lookup"><span data-stu-id="72732-138">Defined maximum amount of time, in minutes, that a log can elapse before a new .etl file is created.</span></span> <span data-ttu-id="72732-139">當計時器過期時，即使已在 EtlFileRolloverSizeMB 中設定的大小上限尚未達到，新的記錄檔案也會建立。</span><span class="sxs-lookup"><span data-stu-id="72732-139">A new log file is created when the timer expires even if the maximum size set in EtlFileRolloverSizeMB has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="72732-140"><strong>TmfFileSearchPath</strong></span><span class="sxs-lookup"><span data-stu-id="72732-140"><strong>TmfFileSearchPath</strong></span></span></p></td>
    <td><p><span data-ttu-id="72732-141">[追蹤郵件格式] 檔案的搜尋位置。</span><span class="sxs-lookup"><span data-stu-id="72732-141">Location to search for the trace message format files.</span></span> <span data-ttu-id="72732-142">[追蹤郵件格式] 檔案是用來將二進位檔案轉換成人類可讀格式。</span><span class="sxs-lookup"><span data-stu-id="72732-142">The trace message format files are used to convert the binary files into a human readable format.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="72732-143"><strong>CacheFileLocalFolders</strong></span><span class="sxs-lookup"><span data-stu-id="72732-143"><strong>CacheFileLocalFolders</strong></span></span></p></td>
    <td><p><span data-ttu-id="72732-144">已定義在電腦上寫入快取檔案之位置的路徑。</span><span class="sxs-lookup"><span data-stu-id="72732-144">Defined path to the location where cache files are written on computers.</span></span> <span data-ttu-id="72732-145">CLSAgent 會寫入快取檔案，並在網路服務的內容下執行。</span><span class="sxs-lookup"><span data-stu-id="72732-145">CLSAgent writes the cache files and runs under the context of the Network Service.</span></span> <span data-ttu-id="72732-146">在此案例中，% TEMP% 會展開為%WINDIR%\ServiceProfiles\NetworkService\AppData\Local。</span><span class="sxs-lookup"><span data-stu-id="72732-146">In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span> <span data-ttu-id="72732-147">根據預設，會將緩存檔案和記錄檔寫入相同的目錄。</span><span class="sxs-lookup"><span data-stu-id="72732-147">By default, cache files and log files are written to the same directory.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="72732-148"><strong>CacheFileNetworkFolder</strong></span><span class="sxs-lookup"><span data-stu-id="72732-148"><strong>CacheFileNetworkFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="72732-149">您可以定義通用命名慣例（UNC）路徑，以在記錄作業期間接收快取檔案。</span><span class="sxs-lookup"><span data-stu-id="72732-149">You can define a universal naming convention (UNC) path to receive the cache files during logging operations.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="72732-150"><strong>CacheFileLocalRetentionPeriod</strong></span><span class="sxs-lookup"><span data-stu-id="72732-150"><strong>CacheFileLocalRetentionPeriod</strong></span></span></p></td>
    <td><p><span data-ttu-id="72732-151">定義為保留快取檔案的最長時間（以天為單位）。</span><span class="sxs-lookup"><span data-stu-id="72732-151">Defined as the maximum time, in days, that cache files are retained.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="72732-152"><strong>CacheFileMaxDiskUsage</strong></span><span class="sxs-lookup"><span data-stu-id="72732-152"><strong>CacheFileMaxDiskUsage</strong></span></span></p></td>
    <td><p><span data-ttu-id="72732-153">定義為快取檔案可以使用的磁碟空間百分比。</span><span class="sxs-lookup"><span data-stu-id="72732-153">Defined as the percentage of disk space that can be used by the cache files.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="72732-154"><strong>ComponentThrottleLimit</strong></span><span class="sxs-lookup"><span data-stu-id="72732-154"><strong>ComponentThrottleLimit</strong></span></span></p></td>
    <td><p><span data-ttu-id="72732-155">在觸發自動節流 limiter 前，定義為每秒可產生的追蹤數上限。</span><span class="sxs-lookup"><span data-stu-id="72732-155">Defined as the maximum number of traces per second that a component can produce before the automatic throttle limiter is triggered.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="72732-156"><strong>ComponentThrottleSample</strong></span><span class="sxs-lookup"><span data-stu-id="72732-156"><strong>ComponentThrottleSample</strong></span></span></p></td>
    <td><p><span data-ttu-id="72732-157">ComponentThrottleLimit 可超過60秒數的次數。</span><span class="sxs-lookup"><span data-stu-id="72732-157">Number of times in 60 seconds that the ComponentThrottleLimit can be exceeded.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="72732-158"><strong>MinimumClsAgentServiceVersion</strong></span><span class="sxs-lookup"><span data-stu-id="72732-158"><strong>MinimumClsAgentServiceVersion</strong></span></span></p></td>
    <td><p><span data-ttu-id="72732-159">允許執行的 CLSAgent 最低版本。</span><span class="sxs-lookup"><span data-stu-id="72732-159">The minimum version of the CLSAgent allowed to run.</span></span> <span data-ttu-id="72732-160">此元素適用于 Office 365。</span><span class="sxs-lookup"><span data-stu-id="72732-160">This element is intended for Office 365.</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="72732-161">請參閱</span><span class="sxs-lookup"><span data-stu-id="72732-161">See Also</span></span>


[<span data-ttu-id="72732-162">Lync Server 2013 中的集中式記錄服務概覽</span><span class="sxs-lookup"><span data-stu-id="72732-162">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


<span data-ttu-id="72732-163">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="72732-163">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="72732-164">[移除-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="72732-164">[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span></span>  
<span data-ttu-id="72732-165">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="72732-165">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="72732-166">[CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="72732-166">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


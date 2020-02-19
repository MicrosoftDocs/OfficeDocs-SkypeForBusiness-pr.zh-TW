---
title: 了解集中式記錄服務組態設定
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
ms.openlocfilehash: c1be1fcb159f3ad75688e63bb61de9afef9f5a8a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="c0831-102">了解在 Lync Server 2013 中的集中式記錄服務組態設定</span><span class="sxs-lookup"><span data-stu-id="c0831-102">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0831-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="c0831-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c0831-104">The Centralized Logging Service 設定來定義記錄服務是用來收集、 及其收集的方式，它會收集，並記錄檔設定為何。</span><span class="sxs-lookup"><span data-stu-id="c0831-104">The Centralized Logging Service is configured to define what the logging service is intended to collect, how it collects, where it will collect from, and what the log settings are.</span></span> <span data-ttu-id="c0831-105">定義這些設定全域 (也就是整個部署) 或針對網站 （也就是您在部署中的具名網站）。</span><span class="sxs-lookup"><span data-stu-id="c0831-105">You define these settings globally (that is, for the entire deployment) or for a site (that is, a named site in your deployment).</span></span> <span data-ttu-id="c0831-106">任何您定義的記錄都會依據您在進行開始、停止、清除及搜尋記錄命令時所使用的身分，而使用適當的設定。</span><span class="sxs-lookup"><span data-stu-id="c0831-106">Any logging that you define will use the settings that are appropriate for the identity that you use for commands to start, stop, flush, and search logs.</span></span>

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="c0831-107">若要顯示目前的集中式記錄服務組態</span><span class="sxs-lookup"><span data-stu-id="c0831-107">To display the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="c0831-108">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="c0831-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c0831-109">在命令列提示輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="c0831-109">Type the following at a command-line prompt:</span></span>
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > <span data-ttu-id="c0831-110">您可以縮小或傳回所定義的組態設定的範圍依序展開 [<CODE>-Identity</CODE>和範圍，例如"Site: Redmond"傳回僅針對 Redmond 網站 CsClsConfiguration。</span><span class="sxs-lookup"><span data-stu-id="c0831-110">You can narrow or expand the scope of the configuration settings that are returned by defining <CODE>-Identity</CODE> and a scope, such as "Site:Redmond" to return only the CsClsConfiguration for the site Redmond.</span></span> <span data-ttu-id="c0831-111">如果您想設定的指定部分詳細，您可以將輸出內容輸送到另一個的 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c0831-111">If you want details about a given portion of the configuration, you can pipe the output into another Windows PowerShell cmdlet.</span></span> <span data-ttu-id="c0831-112">例如，若要取得有關站台"Redmond"的設定中所定義案例的詳細資訊，請輸入：<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span><span class="sxs-lookup"><span data-stu-id="c0831-112">For example, to get details about the scenarios defined in the configuration for site "Redmond", type: <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span></span>

    
    </div>
    
    <span data-ttu-id="c0831-113">![從 Get-csclsconfiguration 輸出的範例。](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "從 Get-csclsconfiguration 輸出的範例。")</span><span class="sxs-lookup"><span data-stu-id="c0831-113">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>
    
    <span data-ttu-id="c0831-114">Cmdlet 的結果會顯示目前的集中式記錄服務組態。</span><span class="sxs-lookup"><span data-stu-id="c0831-114">The result from the cmdlet displays the current configuration of the Centralized Logging Service.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="c0831-115">組態設定</span><span class="sxs-lookup"><span data-stu-id="c0831-115">Configuration Setting</span></span></th>
    <th><span data-ttu-id="c0831-116">描述</span><span class="sxs-lookup"><span data-stu-id="c0831-116">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="c0831-117"><strong>身分識別</strong></span><span class="sxs-lookup"><span data-stu-id="c0831-117"><strong>Identity</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0831-p103">識別此組態的範圍及名稱。只有一個全域組態，而每個網站有一個組態。</span><span class="sxs-lookup"><span data-stu-id="c0831-p103">Identifies the scope and name for this configuration. There is only one Global configuration, and one configuration per site.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c0831-120"><strong>Scenarios</strong></span><span class="sxs-lookup"><span data-stu-id="c0831-120"><strong>Scenarios</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0831-121">列出針對此組態定義的所有案例。</span><span class="sxs-lookup"><span data-stu-id="c0831-121">Listing of all scenarios that are defined for this configuration.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c0831-122"><strong>SearchTerms</strong></span><span class="sxs-lookup"><span data-stu-id="c0831-122"><strong>SearchTerms</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0831-123">定義組態的搜尋字詞。</span><span class="sxs-lookup"><span data-stu-id="c0831-123">Defined search terms for the configuration.</span></span> <span data-ttu-id="c0831-124">Office 365、 不在內部部署。</span><span class="sxs-lookup"><span data-stu-id="c0831-124">Office 365, not on-premises deployments.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c0831-125"><strong>SecurityGroups</strong></span><span class="sxs-lookup"><span data-stu-id="c0831-125"><strong>SecurityGroups</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0831-126">定義安全性群組，根據其所在的網站，控制誰 (亦即安全性群組的成員) 可以看到電腦。</span><span class="sxs-lookup"><span data-stu-id="c0831-126">Defined security groups that control who (that is, members of the security groups) can see computers based on the site they are located in.</span></span> <span data-ttu-id="c0831-127">網站，在此上下文中，是站台拓撲產生器中所定義。</span><span class="sxs-lookup"><span data-stu-id="c0831-127">Site, in this context, is the site as defined in Topology Builder.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c0831-128"><strong>區域</strong></span><span class="sxs-lookup"><span data-stu-id="c0831-128"><strong>Regions</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0831-129">定義地區，用於將 SecurityGroups 集合至地區，例如 EMEA。</span><span class="sxs-lookup"><span data-stu-id="c0831-129">Defined regions are used to collect SecurityGroups into a region, for example EMEA.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c0831-130"><strong>EtlFileFolder</strong></span><span class="sxs-lookup"><span data-stu-id="c0831-130"><strong>EtlFileFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0831-p106">定義將記錄檔寫入電腦所在位置的路徑。CLSAgent 寫入記錄檔並在網路服務環境下執行。在此情況下，%TEMP% 會展開為 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span><span class="sxs-lookup"><span data-stu-id="c0831-p106">Defined path to the location where log files are written on computers. CLSAgent writes the log files and runs under the context of the Network Service. In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c0831-134"><strong>EtlFileRolloverSizeMB</strong></span><span class="sxs-lookup"><span data-stu-id="c0831-134"><strong>EtlFileRolloverSizeMB</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0831-p107">此參數指示在建立新的事件追蹤記錄 (.etl) 檔之前，記錄檔的大小上限。達到定義的大小時，即使還未達到 EtlFileRolloverMinutes 中設定的時間上限，還是會建立新的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="c0831-p107">The parameter indicates the maximum size of the log file before a new event trace log (.etl) file is created. A new log file is created when the defined size is reached even if the maximum time set in EtlFileRolloverMinutes has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c0831-137"><strong>EtlFileRolloverMinutes</strong></span><span class="sxs-lookup"><span data-stu-id="c0831-137"><strong>EtlFileRolloverMinutes</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0831-p108">定義在建立新的 .etl 檔之前，記錄檔可以存在的時間上限 (分)。計時器逾期時，即使還未達到 EtlFileRolloverSizeMB 中設定的大小上限，還是會建立新的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="c0831-p108">Defined maximum amount of time, in minutes, that a log can elapse before a new .etl file is created. A new log file is created when the timer expires even if the maximum size set in EtlFileRolloverSizeMB has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c0831-140"><strong>TmfFileSearchPath</strong></span><span class="sxs-lookup"><span data-stu-id="c0831-140"><strong>TmfFileSearchPath</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0831-p109">搜尋追蹤訊息格式檔的位置。追蹤訊息格式檔是用於將二進位檔案轉換為人類看得懂的格式。</span><span class="sxs-lookup"><span data-stu-id="c0831-p109">Location to search for the trace message format files. The trace message format files are used to convert the binary files into a human readable format.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c0831-143"><strong>CacheFileLocalFolders</strong></span><span class="sxs-lookup"><span data-stu-id="c0831-143"><strong>CacheFileLocalFolders</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0831-p110">定義將快取檔案寫入電腦所在位置的路徑。CLSAgent 寫入快取檔案並在網路服務環境下執行。在此情況下，%TEMP% 會展開為 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local。依據預設，快取檔案及記錄檔會寫入相同的目錄。</span><span class="sxs-lookup"><span data-stu-id="c0831-p110">Defined path to the location where cache files are written on computers. CLSAgent writes the cache files and runs under the context of the Network Service. In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. By default, cache files and log files are written to the same directory.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c0831-148"><strong>CacheFileNetworkFolder</strong></span><span class="sxs-lookup"><span data-stu-id="c0831-148"><strong>CacheFileNetworkFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0831-149">您可以定義通用命名慣例 (UNC) 路徑，以在記錄作業時接收快取檔案。</span><span class="sxs-lookup"><span data-stu-id="c0831-149">You can define a universal naming convention (UNC) path to receive the cache files during logging operations.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c0831-150"><strong>CacheFileLocalRetentionPeriod</strong></span><span class="sxs-lookup"><span data-stu-id="c0831-150"><strong>CacheFileLocalRetentionPeriod</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0831-151">定義快取檔案保留的時間上限 (天)。</span><span class="sxs-lookup"><span data-stu-id="c0831-151">Defined as the maximum time, in days, that cache files are retained.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c0831-152"><strong>CacheFileMaxDiskUsage</strong></span><span class="sxs-lookup"><span data-stu-id="c0831-152"><strong>CacheFileMaxDiskUsage</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0831-153">定義快取檔案可使用的磁碟空間百分比。</span><span class="sxs-lookup"><span data-stu-id="c0831-153">Defined as the percentage of disk space that can be used by the cache files.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c0831-154"><strong>ComponentThrottleLimit</strong></span><span class="sxs-lookup"><span data-stu-id="c0831-154"><strong>ComponentThrottleLimit</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0831-155">定義在觸發自動節流限制器之前，元件每秒可以產生的追蹤上限。</span><span class="sxs-lookup"><span data-stu-id="c0831-155">Defined as the maximum number of traces per second that a component can produce before the automatic throttle limiter is triggered.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c0831-156"><strong>ComponentThrottleSample</strong></span><span class="sxs-lookup"><span data-stu-id="c0831-156"><strong>ComponentThrottleSample</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0831-157">60 秒內可超過 ComponentThrottleLimit 的次數。</span><span class="sxs-lookup"><span data-stu-id="c0831-157">Number of times in 60 seconds that the ComponentThrottleLimit can be exceeded.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c0831-158"><strong>MinimumClsAgentServiceVersion</strong></span><span class="sxs-lookup"><span data-stu-id="c0831-158"><strong>MinimumClsAgentServiceVersion</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0831-159">允許執行的 CLSAgent 最小版本。</span><span class="sxs-lookup"><span data-stu-id="c0831-159">The minimum version of the CLSAgent allowed to run.</span></span> <span data-ttu-id="c0831-160">這個項目適用於 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c0831-160">This element is intended for Office 365.</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c0831-161">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c0831-161">See Also</span></span>


[<span data-ttu-id="c0831-162">Lync Server 2013 中的集中式的記錄服務概觀</span><span class="sxs-lookup"><span data-stu-id="c0831-162">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


<span data-ttu-id="c0831-163">[Set-csclsconfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c0831-163">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="c0831-164">[Remove-csclsconfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c0831-164">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>  
<span data-ttu-id="c0831-165">[New-csclsconfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c0831-165">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="c0831-166">[Get-csclsconfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c0831-166">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


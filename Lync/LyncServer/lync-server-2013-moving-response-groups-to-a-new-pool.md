---
title: Lync Server 2013：將回應群組移至新的池中
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96740d8937f1548952d41d5674ef3e66cd29e2b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a><span data-ttu-id="d897a-102">在 Lync Server 2013 中將回應群組移至新的文件庫</span><span class="sxs-lookup"><span data-stu-id="d897a-102">Moving response groups to a new pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d897a-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d897a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d897a-104">Lync Server 2013 引入了新的 Cmdlet 支援，可將回應群組從一個池移到另一個池中，即使完全符合的功能變數名稱（FQDN）不同也一樣。</span><span class="sxs-lookup"><span data-stu-id="d897a-104">Lync Server 2013 introduces new cmdlet support for moving response groups from one pool to another pool, even when the fully qualified domain name (FQDN) is different.</span></span>

<span data-ttu-id="d897a-105">使用下列程式中的步驟，將回應群組從一個前端池移到另一個具有不同 FQDN 的 [前端] 池。</span><span class="sxs-lookup"><span data-stu-id="d897a-105">Use the steps in the following procedure to move response groups from one Front End pool to another Front End pool with a different FQDN.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d897a-106">在共存環境中，您只能在 Lync Server 2013&nbsp;前端池之間移動回應群組。</span><span class="sxs-lookup"><span data-stu-id="d897a-106">In a coexistence environment, you can move response groups only between Lync Server 2013&nbsp;Front End pools.</span></span>



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a><span data-ttu-id="d897a-107">若要將回應群組移到具有不同 FQDN 的池</span><span class="sxs-lookup"><span data-stu-id="d897a-107">To move response groups to a pool with a different FQDN</span></span>

1.  <span data-ttu-id="d897a-108">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d897a-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d897a-109">匯出來源池中的回應群組。</span><span class="sxs-lookup"><span data-stu-id="d897a-109">Export the response groups in the source pool.</span></span> <span data-ttu-id="d897a-110">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="d897a-110">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    <span data-ttu-id="d897a-111">例如：</span><span class="sxs-lookup"><span data-stu-id="d897a-111">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    <span data-ttu-id="d897a-112">若要在匯出期間從來源池中移除回應群組，請包括-RemoveExportedConfiguration 參數。</span><span class="sxs-lookup"><span data-stu-id="d897a-112">To remove the response groups from the source pool during the export, include the –RemoveExportedConfiguration parameter.</span></span> <span data-ttu-id="d897a-113">例如：</span><span class="sxs-lookup"><span data-stu-id="d897a-113">For example:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  <span data-ttu-id="d897a-114">匯入回應群組至目的地池中，並將目的地池指派為新的擁有者。</span><span class="sxs-lookup"><span data-stu-id="d897a-114">Import the response groups to the destination pool and assign the destination pool as the new owner.</span></span> <span data-ttu-id="d897a-115">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="d897a-115">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    <span data-ttu-id="d897a-116">如果您也想要將 [回應] 群組的應用層級設定從來源池複製到目的地池，請包含– ReplaceExistingRgsSettings 參數。</span><span class="sxs-lookup"><span data-stu-id="d897a-116">If you also want to copy the Response Group application-level settings from the source pool to the destination pool, include the –ReplaceExistingRgsSettings parameter.</span></span> <span data-ttu-id="d897a-117">每個 pool 只能定義一組應用層級設定。</span><span class="sxs-lookup"><span data-stu-id="d897a-117">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="d897a-118">如果您將應用程式層級設定從來源池複製到目的地池，來源池中的設定會取代目的地池的設定。</span><span class="sxs-lookup"><span data-stu-id="d897a-118">If you copy the application-level settings from the source pool to the destination pool, the settings from the source pool replace the settings for the destination pool.</span></span> <span data-ttu-id="d897a-119">如果您沒有從來源池中複製應用程式層級設定，目的地池中的現有設定就會套用至匯入的回應群組。</span><span class="sxs-lookup"><span data-stu-id="d897a-119">If you do not copy the application-level settings from the source pool, the existing settings from the destination pool apply to the imported response groups.</span></span>
    
    <span data-ttu-id="d897a-120">例如：</span><span class="sxs-lookup"><span data-stu-id="d897a-120">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d897a-121">應用程式層級設定包括預設的 [隨用音樂保留] 設定、預設的 [音樂保留] 音訊檔案、[代理程式 ringback 寬限期]，以及 [通話內容] 配置。</span><span class="sxs-lookup"><span data-stu-id="d897a-121">Application-level settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="d897a-122">若要查看這些設定，請執行<STRONG>CsRgsConfiguration</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d897a-122">To view these configuration settings, run the <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="d897a-123">如需此 Cmdlet 的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">CsRgsConfiguration</A>。</span><span class="sxs-lookup"><span data-stu-id="d897a-123">For details about this cmdlet, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="d897a-124">您可以執行下列動作，透過顯示匯入的回應群組設定來確認匯入成功：</span><span class="sxs-lookup"><span data-stu-id="d897a-124">Verify that the import was successful by displaying the imported response group configuration by doing the following:</span></span>
    
      - <span data-ttu-id="d897a-125">確認所有工作流程都已匯入。</span><span class="sxs-lookup"><span data-stu-id="d897a-125">Verify that all the workflows were imported.</span></span> <span data-ttu-id="d897a-126">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="d897a-126">At the command line, type the following:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="d897a-127">確認已匯入所有佇列。</span><span class="sxs-lookup"><span data-stu-id="d897a-127">Verify that all the queues were imported.</span></span> <span data-ttu-id="d897a-128">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="d897a-128">At the command line, type the following:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="d897a-129">確認已匯入所有的代理程式群組。</span><span class="sxs-lookup"><span data-stu-id="d897a-129">Verify that all the agent groups were imported.</span></span> <span data-ttu-id="d897a-130">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="d897a-130">At the command line, type the following:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="d897a-131">確認已匯入所有上班時間。</span><span class="sxs-lookup"><span data-stu-id="d897a-131">Verify that all the hours of business were imported.</span></span> <span data-ttu-id="d897a-132">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="d897a-132">At the command line, type the following:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - <span data-ttu-id="d897a-133">確認所有假日集都已匯入。</span><span class="sxs-lookup"><span data-stu-id="d897a-133">Verify that all the holiday sets were imported.</span></span> <span data-ttu-id="d897a-134">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="d897a-134">At the command line, type the following:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  <span data-ttu-id="d897a-135">將呼叫撥到其中一個回應群組，並確認正確處理通話，以確認匯入成功。</span><span class="sxs-lookup"><span data-stu-id="d897a-135">Verify that the import was successful by placing a call to one of the response groups and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="d897a-136">要求是正式代理群組成員的代理，在目的地池中登入其代理群組。</span><span class="sxs-lookup"><span data-stu-id="d897a-136">Request agents who are members of formal agent groups to sign in to their agent groups in the destination pool.</span></span>

7.  <span data-ttu-id="d897a-137">如果您之前從未從來源池中移除回應群組，請從來源池中移除回應群組。</span><span class="sxs-lookup"><span data-stu-id="d897a-137">If you did not previously remove response groups from the source pool, remove the response groups from the source pool.</span></span> <span data-ttu-id="d897a-138">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="d897a-138">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    <span data-ttu-id="d897a-139">例如：</span><span class="sxs-lookup"><span data-stu-id="d897a-139">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>


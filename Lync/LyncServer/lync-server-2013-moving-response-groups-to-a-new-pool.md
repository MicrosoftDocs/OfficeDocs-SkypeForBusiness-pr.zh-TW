---
title: Lync Server 2013：移動回應群組至新集區
description: Lync Server 2013：將回應群組移至新集區。
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
ms.openlocfilehash: b696963a28abbcd258f53fae12c3e281efa6ae4d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541980"
---
# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a><span data-ttu-id="c61e4-103">將回應群組移至 Lync Server 2013 中的新集區</span><span class="sxs-lookup"><span data-stu-id="c61e4-103">Moving response groups to a new pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c61e4-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c61e4-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c61e4-105">Lync Server 2013 引進新的指令程式支援，可將回應群組從一個集區移至另一個集區，即使 (FQDN) 的完整功能變數名稱不同也是一樣。</span><span class="sxs-lookup"><span data-stu-id="c61e4-105">Lync Server 2013 introduces new cmdlet support for moving response groups from one pool to another pool, even when the fully qualified domain name (FQDN) is different.</span></span>

<span data-ttu-id="c61e4-106">使用下列程式中的步驟，將回應群組從一個前端集區移至另一個具有不同 FQDN 的前端集區。</span><span class="sxs-lookup"><span data-stu-id="c61e4-106">Use the steps in the following procedure to move response groups from one Front End pool to another Front End pool with a different FQDN.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c61e4-107">在共存環境中，您只能移動 Lync Server 2013 前端集區之間的回應群組 &nbsp; 。</span><span class="sxs-lookup"><span data-stu-id="c61e4-107">In a coexistence environment, you can move response groups only between Lync Server 2013&nbsp;Front End pools.</span></span>



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a><span data-ttu-id="c61e4-108">將回應群組移至具有不同 FQDN 的集區</span><span class="sxs-lookup"><span data-stu-id="c61e4-108">To move response groups to a pool with a different FQDN</span></span>

1.  <span data-ttu-id="c61e4-109">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="c61e4-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c61e4-110">匯出來源集區中的回應群組。</span><span class="sxs-lookup"><span data-stu-id="c61e4-110">Export the response groups in the source pool.</span></span> <span data-ttu-id="c61e4-111">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="c61e4-111">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    <span data-ttu-id="c61e4-112">例如：</span><span class="sxs-lookup"><span data-stu-id="c61e4-112">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    <span data-ttu-id="c61e4-113">若要在匯出期間從來源集區中移除回應群組，請包括–RemoveExportedConfiguration 參數。</span><span class="sxs-lookup"><span data-stu-id="c61e4-113">To remove the response groups from the source pool during the export, include the –RemoveExportedConfiguration parameter.</span></span> <span data-ttu-id="c61e4-114">例如：</span><span class="sxs-lookup"><span data-stu-id="c61e4-114">For example:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  <span data-ttu-id="c61e4-115">將回應群組匯入目的地集區，並將目的地集區指派為新的擁有者。</span><span class="sxs-lookup"><span data-stu-id="c61e4-115">Import the response groups to the destination pool and assign the destination pool as the new owner.</span></span> <span data-ttu-id="c61e4-116">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="c61e4-116">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    <span data-ttu-id="c61e4-117">如果您也想要將來源集區的回應群組應用層級設定複製到目的地集區，請加入– ReplaceExistingRgsSettings 參數。</span><span class="sxs-lookup"><span data-stu-id="c61e4-117">If you also want to copy the Response Group application-level settings from the source pool to the destination pool, include the –ReplaceExistingRgsSettings parameter.</span></span> <span data-ttu-id="c61e4-118">您只能為每個集區定義一組應用層級的設定。</span><span class="sxs-lookup"><span data-stu-id="c61e4-118">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="c61e4-119">如果您將應用層級設定從來源集區複製到目的地集區，來源集區的設定會取代目的地集區的設定。</span><span class="sxs-lookup"><span data-stu-id="c61e4-119">If you copy the application-level settings from the source pool to the destination pool, the settings from the source pool replace the settings for the destination pool.</span></span> <span data-ttu-id="c61e4-120">如果您未從來源集區複製應用層級設定，則目的地集區中的現有設定會套用至匯入的回應群組。</span><span class="sxs-lookup"><span data-stu-id="c61e4-120">If you do not copy the application-level settings from the source pool, the existing settings from the destination pool apply to the imported response groups.</span></span>
    
    <span data-ttu-id="c61e4-121">例如：</span><span class="sxs-lookup"><span data-stu-id="c61e4-121">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c61e4-122">應用層級設定包括預設的等候音樂設定、預設的等候音樂音訊檔、代理程式回電寬限時間，以及通話內容設定。</span><span class="sxs-lookup"><span data-stu-id="c61e4-122">Application-level settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="c61e4-123">若要檢視這些組態設定，請執行 <STRONG>Get-CsRgsConfiguration</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c61e4-123">To view these configuration settings, run the <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="c61e4-124">如需此 Cmdlet 的詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>。</span><span class="sxs-lookup"><span data-stu-id="c61e4-124">For details about this cmdlet, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="c61e4-125">執行下列動作來顯示匯入的回應群組設定，以確認匯入是否成功：</span><span class="sxs-lookup"><span data-stu-id="c61e4-125">Verify that the import was successful by displaying the imported response group configuration by doing the following:</span></span>
    
      - <span data-ttu-id="c61e4-126">確認已匯入所有工作流程。</span><span class="sxs-lookup"><span data-stu-id="c61e4-126">Verify that all the workflows were imported.</span></span> <span data-ttu-id="c61e4-127">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="c61e4-127">At the command line, type the following:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="c61e4-128">確認已匯入所有佇列。</span><span class="sxs-lookup"><span data-stu-id="c61e4-128">Verify that all the queues were imported.</span></span> <span data-ttu-id="c61e4-129">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="c61e4-129">At the command line, type the following:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="c61e4-130">確認已匯入所有代理程式群組。</span><span class="sxs-lookup"><span data-stu-id="c61e4-130">Verify that all the agent groups were imported.</span></span> <span data-ttu-id="c61e4-131">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="c61e4-131">At the command line, type the following:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="c61e4-132">確認已匯入商務用時數。</span><span class="sxs-lookup"><span data-stu-id="c61e4-132">Verify that all the hours of business were imported.</span></span> <span data-ttu-id="c61e4-133">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="c61e4-133">At the command line, type the following:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - <span data-ttu-id="c61e4-134">確認已匯入所有假日集。</span><span class="sxs-lookup"><span data-stu-id="c61e4-134">Verify that all the holiday sets were imported.</span></span> <span data-ttu-id="c61e4-135">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="c61e4-135">At the command line, type the following:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  <span data-ttu-id="c61e4-136">撥打電話給其中一個回應群組，確認是否已正確處理該呼叫，以確認匯入是否成功。</span><span class="sxs-lookup"><span data-stu-id="c61e4-136">Verify that the import was successful by placing a call to one of the response groups and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="c61e4-137">要求是正式代理群組成員的代理人，以登入目的地集區中的其代理群組。</span><span class="sxs-lookup"><span data-stu-id="c61e4-137">Request agents who are members of formal agent groups to sign in to their agent groups in the destination pool.</span></span>

7.  <span data-ttu-id="c61e4-138">如果您先前沒有從來源集區移除回應群組，請從來源集區中移除回應群組。</span><span class="sxs-lookup"><span data-stu-id="c61e4-138">If you did not previously remove response groups from the source pool, remove the response groups from the source pool.</span></span> <span data-ttu-id="c61e4-139">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="c61e4-139">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    <span data-ttu-id="c61e4-140">例如：</span><span class="sxs-lookup"><span data-stu-id="c61e4-140">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：設定影片頻寬
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8995f47ff1059921c324d71cbaca26fa47c50ca0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a><span data-ttu-id="22e72-102">在 Lync Server 2013 中設定影片頻寬</span><span class="sxs-lookup"><span data-stu-id="22e72-102">Configuring video bandwidth in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22e72-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="22e72-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="22e72-104">Lync Server 2013 包含數個設定，用來管理兩方通話和多方會議的影片。</span><span class="sxs-lookup"><span data-stu-id="22e72-104">Lync Server 2013 includes several settings for managing video for two-party calls and multiparty conferences.</span></span> <span data-ttu-id="22e72-105">當您部署 Lync Server 2013 時，應評估預設設定是否適合您的組織，並視需要加以修改。</span><span class="sxs-lookup"><span data-stu-id="22e72-105">When you deploy Lync Server 2013, you should evaluate whether the default settings are appropriate for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="22e72-p102">本節所述的參數適用於雙方通話和多方會議。請使用下列其中一個 Cmdlet 來檢視或修改這些設定：</span><span class="sxs-lookup"><span data-stu-id="22e72-p102">The parameters described in this section apply to both two-party calls and multiparty conferencing. View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="22e72-108">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="22e72-108">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="22e72-109">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="22e72-109">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="22e72-110">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="22e72-110">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="22e72-111">在您的會議原則中確認下列設定：</span><span class="sxs-lookup"><span data-stu-id="22e72-111">Verify the following settings in your conferencing policy:</span></span>

  - <span data-ttu-id="22e72-112">**VideoBitRateKb**    此設定指定由使用者所傳送之影片的最高每秒 (kbps) 的影片位元速率。</span><span class="sxs-lookup"><span data-stu-id="22e72-112">**VideoBitRateKb**   This setting specifies the maximum video bit rate in kilobits per second (kbps) used for video sent by a user.</span></span> <span data-ttu-id="22e72-113">預設值為 50000 kbps。</span><span class="sxs-lookup"><span data-stu-id="22e72-113">The default value is 50000 kbps.</span></span> <span data-ttu-id="22e72-114">有效的值為0到50000。</span><span class="sxs-lookup"><span data-stu-id="22e72-114">Valid values are 0 to 50000.</span></span>
    
    <span data-ttu-id="22e72-115">這個設定分別套用至主要視訊和全景視訊。</span><span class="sxs-lookup"><span data-stu-id="22e72-115">This setting applies separately to main video and panoramic video.</span></span>
    
    <span data-ttu-id="22e72-116">範例：如果您指定 2000 kbps，Lync Server 可以傳送 2000 kbps 的主要影片資料流程，以及全景影片資料流程的 2000 kbps。</span><span class="sxs-lookup"><span data-stu-id="22e72-116">Example: if you specify 2000 kbps, then Lync Server can send 2000 kbps for the main video stream and 2000 kbps for the panoramic video stream.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22e72-117">Lync 2013 端點的最大視頻網路頻寬是 8000 kbps 的主要影片及全景影片的 2500 kbps。</span><span class="sxs-lookup"><span data-stu-id="22e72-117">The maximum video network bandwidth for a Lync 2013 endpoint is 8000 kbps for the main video and 2500 kbps for panoramic video.</span></span> <span data-ttu-id="22e72-118">只有當接收或傳送多個視訊時，才會達到上述最大值。</span><span class="sxs-lookup"><span data-stu-id="22e72-118">These maximum values are reached only if multiple videos are received or sent.</span></span> <span data-ttu-id="22e72-119">如需詳細資訊，請參閱<A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Lync Server 2013 中媒體流量的網路頻寬需求</A>中的「媒體流量網路使用量」一節。</span><span class="sxs-lookup"><span data-stu-id="22e72-119">For details, see the "Media Traffic Network Usage" section in <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Network bandwidth requirements for media traffic in Lync Server 2013</A>.</span></span> <span data-ttu-id="22e72-120">這一節列出所有支援的解析度的最大及一般視訊資料流頻寬。</span><span class="sxs-lookup"><span data-stu-id="22e72-120">This section lists the maximum and typical video stream bandwidth for all supported resolutions.</span></span>

    
    </div>

  - <span data-ttu-id="22e72-121">**TotalReceiveVideoBitRateKb**    此設定是 Lync Server 2013 中的新功能，指定用戶端所收到之所有影片的最大位元速率 (，單位為每秒千位) 。</span><span class="sxs-lookup"><span data-stu-id="22e72-121">**TotalReceiveVideoBitRateKb**   This setting, which is new in Lync Server 2013, specifies the maximum allowed bitrate (in kilobits per second) for all the video streams received by a client.</span></span> <span data-ttu-id="22e72-122">也就是說，它會指定用戶端可以接收的所有影片資料流程（除了全景影片資料流程以外）的合併總計。</span><span class="sxs-lookup"><span data-stu-id="22e72-122">That is, it specifies the combined total for all the video streams, except for panoramic video streams, that a client can receive.</span></span> <span data-ttu-id="22e72-123">例如，如果您指定 1500 kbps，則用戶端最多可以接收 1500 kbps 的影片，其可能是由多個影片資料流程或單一的視頻資料流程所組成。</span><span class="sxs-lookup"><span data-stu-id="22e72-123">For example, if you specify 1500 kbps, then a client can receive up to 1500 kbps of video, which may consist of multiple video streams or a single video stream.</span></span> <span data-ttu-id="22e72-124">此設定僅適用于 Lync Server 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="22e72-124">This setting applies only to Lync Server 2013 clients.</span></span>
    
    <span data-ttu-id="22e72-p106">**TotalReceiveVideoBitRateKb** 的預設值為 50000 kbps。如果「圖庫檢視」的 **EnableMultiviewJoin** 設定為 True，**TotalReceiveVideoBitRateKb** 的設定就不得低於 420 kbps。如果「圖庫檢視」的 **EnableMultiviewJoin** 設定為 False，**TotalReceiveVideoBitRateKb** 的設定就不得低於 100 kbps。如果 **EnableMultiviewJoin** 設定為 True，但您將值設定為低於 420 kbps，該值將會預設為臨界值。這個臨界值有助於防止意外的錯誤設定，避免造成不佳的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="22e72-p106">The default value for **TotalReceiveVideoBitRateKb** is 50000 kbps. If the **EnableMultiviewJoin** setting for Gallery View is set to True, **TotalReceiveVideoBitRateKb** must not be set below 420 kbps. If the **EnableMultiviewJoin** setting for Gallery View is set to False, **TotalReceiveVideoBitRateKb** must not be set below 100 kbps. If **EnableMultiviewJoin** is set to True and you set the value below 420 kbps, the values will default to the threshold value. This threshold helps prevent accidental misconfiguration that might result in poor user experience.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22e72-130">如需<STRONG>EnableMultiviewJoin</STRONG>設定的詳細資訊，請參閱<A href="lync-server-2013-configuring-gallery-view.md">在 Lync Server 2013 中設定圖庫 View</A>。</span><span class="sxs-lookup"><span data-stu-id="22e72-130">For details about the <STRONG>EnableMultiviewJoin</STRONG> setting, see <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="22e72-131">**MaxVideoConferencingResolution**    此參數不再用於 Lync Server 2013 會議中的 Lync Server 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="22e72-131">**MaxVideoConferencingResolution**   This parameter is no longer used for Lync Server 2013 clients in Lync Server 2013 conferences.</span></span> <span data-ttu-id="22e72-132">Lync Server 2013 會議使用本節先前所述的位元速率控制。</span><span class="sxs-lookup"><span data-stu-id="22e72-132">Lync Server 2013 conferences use the bit rate controls described earlier in this section.</span></span> <span data-ttu-id="22e72-133">此設定仍用於加入 Lync Server 2013 會議的舊版用戶端。</span><span class="sxs-lookup"><span data-stu-id="22e72-133">This setting is still used for legacy clients joining a Lync Server 2013 conference.</span></span> <span data-ttu-id="22e72-134">此參數會決定舊版用戶端對於以 Lync Server 2013 為宿主之使用者所組織的會議中所允許的最大解決方法。</span><span class="sxs-lookup"><span data-stu-id="22e72-134">This parameter determines the maximum resolution allowed for legacy clients in conferences organized by users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="22e72-135">也就是說，舊版用戶端的處理方式與舊版本的 Lync Server 或 Office 通訊伺服器相同。</span><span class="sxs-lookup"><span data-stu-id="22e72-135">That is, legacy clients are treated the same as they were in previous versions of Lync Server or Office Communications Server.</span></span>

<span data-ttu-id="22e72-p108">除了套用至使用者的會議原則設定，也要評估媒體組態設定。請使用下列其中一個 Cmdlet 來檢視或修改這些設定：</span><span class="sxs-lookup"><span data-stu-id="22e72-p108">In addition to conferencing policy settings that apply to users, evaluate media configuration settings. View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="22e72-138">**Get-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="22e72-138">**Get-CsMediaConfiguration**</span></span>

  - <span data-ttu-id="22e72-139">**CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="22e72-139">**Set- CsMediaConfiguration**</span></span>

  - <span data-ttu-id="22e72-140">**新 CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="22e72-140">**New- CsMediaConfiguration**</span></span>

<span data-ttu-id="22e72-141">確認下列設定：</span><span class="sxs-lookup"><span data-stu-id="22e72-141">Verify the following setting:</span></span>

  - <span data-ttu-id="22e72-142">**MaxVideoRateAllowed**    這個每個集區設定會指定在用戶端端點傳輸的視訊訊號的最大速率。</span><span class="sxs-lookup"><span data-stu-id="22e72-142">**MaxVideoRateAllowed**   This per-pool setting specifies the maximum rate at which video signals will be transferred at the client endpoints.</span></span> <span data-ttu-id="22e72-143">它只適用于舊版的 Lync Server 用戶端。</span><span class="sxs-lookup"><span data-stu-id="22e72-143">It applies only to previous versions of Lync Server clients.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22e72-144">Lync Server 2013 用戶端忽略此設定，而改用會議原則中的 [TotalReceiveVideoBitRateKb] 設定。</span><span class="sxs-lookup"><span data-stu-id="22e72-144">Lync Server 2013 clients ignore this setting and use the TotalReceiveVideoBitRateKb setting in conferencing policy instead.</span></span>

    
    </div>
    
    <span data-ttu-id="22e72-p110">預設值為 HD720P。有效值為 HD720p15M、VGA600K 和 CIF250K。</span><span class="sxs-lookup"><span data-stu-id="22e72-p110">The default value is HD720P. Valid values are HD720p15M, VGA600K, and CIF250K.</span></span>
    
    <span data-ttu-id="22e72-147">範例：如果您指定 1500 kbps，則集區中所有舊版用戶端在雙方或多方會議中都可以接收高達 1500 kbps 的視訊。</span><span class="sxs-lookup"><span data-stu-id="22e72-147">Example: If you specify 1500 kbps, then all the legacy clients in the pool can receive up to 1500 kbps of video in two-party or multiparty conferences.</span></span>

<span data-ttu-id="22e72-148">下列程式是使用 Lync Server 管理命令介面來修改本節所述設定的範例。</span><span class="sxs-lookup"><span data-stu-id="22e72-148">The following procedures are examples of using Lync Server Management Shell to modify the settings described in this section.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a><span data-ttu-id="22e72-149">修改視訊設定的會議原則</span><span class="sxs-lookup"><span data-stu-id="22e72-149">To modify conferencing policy for video settings</span></span>

1.  <span data-ttu-id="22e72-150">啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="22e72-150">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="22e72-151">在命令列上執行下列 Cmdlet 以編輯會議原則：</span><span class="sxs-lookup"><span data-stu-id="22e72-151">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a><span data-ttu-id="22e72-152">修改舊版用戶端的媒體組態</span><span class="sxs-lookup"><span data-stu-id="22e72-152">To modify media configuration for legacy clients</span></span>

1.  <span data-ttu-id="22e72-153">啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="22e72-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="22e72-154">在命令列上執行下列 Cmdlet 以編輯媒體組態：</span><span class="sxs-lookup"><span data-stu-id="22e72-154">At the command line, run the following cmdlet to edit the media configuration:</span></span>
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：設定影片頻寬
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ee374be85bc9427135ff89f3eb75acefd1cf5a8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a><span data-ttu-id="d5226-102">在 Lync Server 2013 中設定影片頻寬</span><span class="sxs-lookup"><span data-stu-id="d5226-102">Configuring video bandwidth in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5226-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d5226-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d5226-104">Lync Server 2013 包含數個設定，可用於管理雙方通話和多方會議的影片。</span><span class="sxs-lookup"><span data-stu-id="d5226-104">Lync Server 2013 includes several settings for managing video for two-party calls and multiparty conferences.</span></span> <span data-ttu-id="d5226-105">當您部署 Lync Server 2013 時，您應該評估預設設定是否適合您的組織，並視需要加以修改。</span><span class="sxs-lookup"><span data-stu-id="d5226-105">When you deploy Lync Server 2013, you should evaluate whether the default settings are appropriate for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="d5226-106">本節所述的參數同時適用于雙方通話和多方會議。</span><span class="sxs-lookup"><span data-stu-id="d5226-106">The parameters described in this section apply to both two-party calls and multiparty conferencing.</span></span> <span data-ttu-id="d5226-107">使用下列其中一個 Cmdlet 來查看或修改這些設定：</span><span class="sxs-lookup"><span data-stu-id="d5226-107">View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="d5226-108">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="d5226-108">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="d5226-109">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="d5226-109">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="d5226-110">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="d5226-110">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="d5226-111">驗證會議原則中的下列設定：</span><span class="sxs-lookup"><span data-stu-id="d5226-111">Verify the following settings in your conferencing policy:</span></span>

  - <span data-ttu-id="d5226-112">**VideoBitRateKb**   此設定會指定使用者所傳送之影片的最大視頻位元速率，以千位數/秒（kbps）為單位。</span><span class="sxs-lookup"><span data-stu-id="d5226-112">**VideoBitRateKb**   This setting specifies the maximum video bit rate in kilobits per second (kbps) used for video sent by a user.</span></span> <span data-ttu-id="d5226-113">預設值為 50000 kbps。</span><span class="sxs-lookup"><span data-stu-id="d5226-113">The default value is 50000 kbps.</span></span> <span data-ttu-id="d5226-114">有效值為0至50000。</span><span class="sxs-lookup"><span data-stu-id="d5226-114">Valid values are 0 to 50000.</span></span>
    
    <span data-ttu-id="d5226-115">此設定會分別適用于主要影片和全景影片。</span><span class="sxs-lookup"><span data-stu-id="d5226-115">This setting applies separately to main video and panoramic video.</span></span>
    
    <span data-ttu-id="d5226-116">範例：如果您指定 2000 kbps，Lync Server 可以傳送 2000 kbps 的主要影片資料流程，以及全景視頻資料流程的 2000 kbps。</span><span class="sxs-lookup"><span data-stu-id="d5226-116">Example: if you specify 2000 kbps, then Lync Server can send 2000 kbps for the main video stream and 2000 kbps for the panoramic video stream.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5226-117">Lync 2013 端點的 [最大視頻網路頻寬] 是 8000 kbps 的，用於全景影片的主要影片和 2500 kbps。</span><span class="sxs-lookup"><span data-stu-id="d5226-117">The maximum video network bandwidth for a Lync 2013 endpoint is 8000 kbps for the main video and 2500 kbps for panoramic video.</span></span> <span data-ttu-id="d5226-118">只有在收到或傳送多個視頻時，才會達到這些最大值。</span><span class="sxs-lookup"><span data-stu-id="d5226-118">These maximum values are reached only if multiple videos are received or sent.</span></span> <span data-ttu-id="d5226-119">如需詳細資訊，請參閱<A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Lync Server 2013 中的媒體流量需求網路頻寬需求</A>中的「媒體流量網路使用量」一節。</span><span class="sxs-lookup"><span data-stu-id="d5226-119">For details, see the "Media Traffic Network Usage" section in <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Network bandwidth requirements for media traffic in Lync Server 2013</A>.</span></span> <span data-ttu-id="d5226-120">本節列出所有受支援之解析度的最大及典型視頻資料流程頻寬。</span><span class="sxs-lookup"><span data-stu-id="d5226-120">This section lists the maximum and typical video stream bandwidth for all supported resolutions.</span></span>

    
    </div>

  - <span data-ttu-id="d5226-121">**TotalReceiveVideoBitRateKb**   [Lync Server 2013] 中的 [新增] 這項設定，指定用戶端收到的所有影片串流的最大使用率（以千位/秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="d5226-121">**TotalReceiveVideoBitRateKb**   This setting, which is new in Lync Server 2013, specifies the maximum allowed bitrate (in kilobits per second) for all the video streams received by a client.</span></span> <span data-ttu-id="d5226-122">也就是說，它會為用戶端可以接收的所有視頻資料流程（除了全景視頻資料流程）指定合併總計。</span><span class="sxs-lookup"><span data-stu-id="d5226-122">That is, it specifies the combined total for all the video streams, except for panoramic video streams, that a client can receive.</span></span> <span data-ttu-id="d5226-123">例如，如果您指定 1500 kbps，用戶端最多可以接收 1500 kbps 的視頻，可能由多個視頻資料流程或單一的視頻資料流程所組成。</span><span class="sxs-lookup"><span data-stu-id="d5226-123">For example, if you specify 1500 kbps, then a client can receive up to 1500 kbps of video, which may consist of multiple video streams or a single video stream.</span></span> <span data-ttu-id="d5226-124">此設定僅適用于 Lync Server 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="d5226-124">This setting applies only to Lync Server 2013 clients.</span></span>
    
    <span data-ttu-id="d5226-125">**TotalReceiveVideoBitRateKb**的預設值為 50000 kbps。</span><span class="sxs-lookup"><span data-stu-id="d5226-125">The default value for **TotalReceiveVideoBitRateKb** is 50000 kbps.</span></span> <span data-ttu-id="d5226-126">如果圖庫視圖的 [ **EnableMultiviewJoin** ] 設定設為 True，則**TotalReceiveVideoBitRateKb**不得將低於 420 kbps。</span><span class="sxs-lookup"><span data-stu-id="d5226-126">If the **EnableMultiviewJoin** setting for Gallery View is set to True, **TotalReceiveVideoBitRateKb** must not be set below 420 kbps.</span></span> <span data-ttu-id="d5226-127">如果圖庫視圖的**EnableMultiviewJoin**設定設為 False， **TotalReceiveVideoBitRateKb**不得將低於 100 kbps。</span><span class="sxs-lookup"><span data-stu-id="d5226-127">If the **EnableMultiviewJoin** setting for Gallery View is set to False, **TotalReceiveVideoBitRateKb** must not be set below 100 kbps.</span></span> <span data-ttu-id="d5226-128">如果**EnableMultiviewJoin**設定為 True，且您設定的值低於 420 kbps，則這些值將會預設為 [閾值] 值。</span><span class="sxs-lookup"><span data-stu-id="d5226-128">If **EnableMultiviewJoin** is set to True and you set the value below 420 kbps, the values will default to the threshold value.</span></span> <span data-ttu-id="d5226-129">這個閾值可協助防止意外的錯誤配置，可能會導致不佳的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="d5226-129">This threshold helps prevent accidental misconfiguration that might result in poor user experience.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5226-130">如需<STRONG>EnableMultiviewJoin</STRONG>設定的詳細資訊，請參閱<A href="lync-server-2013-configuring-gallery-view.md">在 Lync Server 2013 中設定圖庫視圖</A>。</span><span class="sxs-lookup"><span data-stu-id="d5226-130">For details about the <STRONG>EnableMultiviewJoin</STRONG> setting, see <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="d5226-131">**MaxVideoConferencingResolution**   此參數已不再用於 lync server 2013 會議中的 lync server 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="d5226-131">**MaxVideoConferencingResolution**   This parameter is no longer used for Lync Server 2013 clients in Lync Server 2013 conferences.</span></span> <span data-ttu-id="d5226-132">Lync Server 2013 會議使用本節前面所述的位元速率控制。</span><span class="sxs-lookup"><span data-stu-id="d5226-132">Lync Server 2013 conferences use the bit rate controls described earlier in this section.</span></span> <span data-ttu-id="d5226-133">此設定仍用於加入 Lync Server 2013 會議的舊版用戶端。</span><span class="sxs-lookup"><span data-stu-id="d5226-133">This setting is still used for legacy clients joining a Lync Server 2013 conference.</span></span> <span data-ttu-id="d5226-134">這個參數決定由駐留在 Lync Server 2013 的使用者所組織之會議中的舊版用戶端所允許的最大解析度。</span><span class="sxs-lookup"><span data-stu-id="d5226-134">This parameter determines the maximum resolution allowed for legacy clients in conferences organized by users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="d5226-135">也就是說，舊用戶端的處理方式與舊版 Lync Server 或 Office 通訊伺服器相同。</span><span class="sxs-lookup"><span data-stu-id="d5226-135">That is, legacy clients are treated the same as they were in previous versions of Lync Server or Office Communications Server.</span></span>

<span data-ttu-id="d5226-136">除了適用于使用者的會議原則設定之外，評估媒體設定。</span><span class="sxs-lookup"><span data-stu-id="d5226-136">In addition to conferencing policy settings that apply to users, evaluate media configuration settings.</span></span> <span data-ttu-id="d5226-137">使用下列其中一個 Cmdlet 來查看或修改這些設定：</span><span class="sxs-lookup"><span data-stu-id="d5226-137">View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="d5226-138">**CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="d5226-138">**Get-CsMediaConfiguration**</span></span>

  - <span data-ttu-id="d5226-139">**Set-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="d5226-139">**Set- CsMediaConfiguration**</span></span>

  - <span data-ttu-id="d5226-140">**新-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="d5226-140">**New- CsMediaConfiguration**</span></span>

<span data-ttu-id="d5226-141">確認下列設定：</span><span class="sxs-lookup"><span data-stu-id="d5226-141">Verify the following setting:</span></span>

  - <span data-ttu-id="d5226-142">**MaxVideoRateAllowed**   [此每個池] 設定會指定要在用戶端端點傳送視訊訊號的最大速度。</span><span class="sxs-lookup"><span data-stu-id="d5226-142">**MaxVideoRateAllowed**   This per-pool setting specifies the maximum rate at which video signals will be transferred at the client endpoints.</span></span> <span data-ttu-id="d5226-143">它只適用于舊版的 Lync Server 用戶端。</span><span class="sxs-lookup"><span data-stu-id="d5226-143">It applies only to previous versions of Lync Server clients.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5226-144">Lync Server 2013 用戶端會忽略此設定，而改為使用會議原則中的 [TotalReceiveVideoBitRateKb] 設定。</span><span class="sxs-lookup"><span data-stu-id="d5226-144">Lync Server 2013 clients ignore this setting and use the TotalReceiveVideoBitRateKb setting in conferencing policy instead.</span></span>

    
    </div>
    
    <span data-ttu-id="d5226-145">預設值為 HD720P。</span><span class="sxs-lookup"><span data-stu-id="d5226-145">The default value is HD720P.</span></span> <span data-ttu-id="d5226-146">有效值為 HD720p15M、VGA600K 和 CIF250K。</span><span class="sxs-lookup"><span data-stu-id="d5226-146">Valid values are HD720p15M, VGA600K, and CIF250K.</span></span>
    
    <span data-ttu-id="d5226-147">範例：如果您指定 1500 kbps，則所有舊版用戶端都可以在兩方或多方會議中接收最多 1500 kbps 的影片。</span><span class="sxs-lookup"><span data-stu-id="d5226-147">Example: If you specify 1500 kbps, then all the legacy clients in the pool can receive up to 1500 kbps of video in two-party or multiparty conferences.</span></span>

<span data-ttu-id="d5226-148">下列程式是使用 Lync Server 管理命令介面來修改本節所述設定的範例。</span><span class="sxs-lookup"><span data-stu-id="d5226-148">The following procedures are examples of using Lync Server Management Shell to modify the settings described in this section.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a><span data-ttu-id="d5226-149">修改影片設定的會議原則</span><span class="sxs-lookup"><span data-stu-id="d5226-149">To modify conferencing policy for video settings</span></span>

1.  <span data-ttu-id="d5226-150">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d5226-150">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d5226-151">在命令列上，執行下列 Cmdlet 來編輯會議原則：</span><span class="sxs-lookup"><span data-stu-id="d5226-151">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a><span data-ttu-id="d5226-152">若要修改舊版用戶端的媒體配置</span><span class="sxs-lookup"><span data-stu-id="d5226-152">To modify media configuration for legacy clients</span></span>

1.  <span data-ttu-id="d5226-153">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d5226-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d5226-154">在命令列上，執行下列 Cmdlet 來編輯媒體設定：</span><span class="sxs-lookup"><span data-stu-id="d5226-154">At the command line, run the following cmdlet to edit the media configuration:</span></span>
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>


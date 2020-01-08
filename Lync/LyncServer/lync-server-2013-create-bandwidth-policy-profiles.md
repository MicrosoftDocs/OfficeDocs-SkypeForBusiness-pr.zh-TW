---
title: Lync Server 2013：建立頻寬原則設定檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create bandwidth policy profiles
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48185086
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69aa99d94843c6daa1483911325d45ede0a39f4a
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40976348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="153e0-102">在 Lync Server 2013 中建立頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="153e0-102">Create bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="153e0-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="153e0-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="153e0-104">*頻寬原則*定義即時音訊與視頻形式的頻寬使用量限制。</span><span class="sxs-lookup"><span data-stu-id="153e0-104">*Bandwidth policies* define limitations on bandwidth usage for real-time audio and video modalities.</span></span> <span data-ttu-id="153e0-105">頻寬原則會套用到*頻寬策略設定檔*，這可以套用到多個網路網站以進行呼叫許可控制。</span><span class="sxs-lookup"><span data-stu-id="153e0-105">Bandwidth policies are applied to *bandwidth policy profiles*, which can be applied to multiple network sites for call admission control.</span></span>

<span data-ttu-id="153e0-106">如需在您的 CAC 部署中應該設定哪些頻寬限制的指導方針，請參閱在規劃檔中，在[Lync Server 2013 中定義您的通話許可控制需求](lync-server-2013-defining-your-requirements-for-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="153e0-106">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Defining your requirements for call admission control in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="153e0-107">如需使用頻寬原則與原則設定檔的詳細資訊，請參閱 Lync Server 管理命令介面檔，瞭解下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="153e0-107">For details about working with bandwidth policies and policy profiles, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="153e0-108">新-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="153e0-108">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="153e0-109">CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="153e0-109">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="153e0-110">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="153e0-110">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="153e0-111">移除-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="153e0-111">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

<span data-ttu-id="153e0-112">下列程式中建立的範例原則設定了整體音訊流量、個別音訊會話、整體影片流量，以及個別的視頻會話限制。</span><span class="sxs-lookup"><span data-stu-id="153e0-112">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions.</span></span> <span data-ttu-id="153e0-113">例如，5Mb\_連結頻寬原則設定檔會設定下列限制：</span><span class="sxs-lookup"><span data-stu-id="153e0-113">For example, the 5Mb\_Link bandwidth policy profile sets the following limits:</span></span>

  - <span data-ttu-id="153e0-114">音訊限制： 2000 kbps</span><span class="sxs-lookup"><span data-stu-id="153e0-114">Audio Limit: 2,000 kbps</span></span>

  - <span data-ttu-id="153e0-115">音訊會話限制： 200 kbps</span><span class="sxs-lookup"><span data-stu-id="153e0-115">Audio Session Limit: 200 kbps</span></span>

  - <span data-ttu-id="153e0-116">影片限制： 1400 kbps</span><span class="sxs-lookup"><span data-stu-id="153e0-116">Video Limit: 1,400 kbps</span></span>

  - <span data-ttu-id="153e0-117">影片會話限制： 700 kbps</span><span class="sxs-lookup"><span data-stu-id="153e0-117">Video Session Limit: 700 kbps</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="153e0-118">最小音訊會話限制值為 40 kbps。</span><span class="sxs-lookup"><span data-stu-id="153e0-118">The minimum Audio Session Limit value is 40 kbps.</span></span> <span data-ttu-id="153e0-119">最小的視頻會話限制值為 100 kbps。</span><span class="sxs-lookup"><span data-stu-id="153e0-119">The minimum Video Session Limit value is 100 kbps.</span></span>



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a><span data-ttu-id="153e0-120">使用管理命令介面建立頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="153e0-120">To create bandwidth policy profiles by using Management Shell</span></span>

1.  <span data-ttu-id="153e0-121">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="153e0-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="153e0-122">針對您想要建立的每一個頻寬原則設定檔，執行新的 CsNetworkBandwidthPolicyProfile Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="153e0-122">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="153e0-123">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="153e0-123">For example, run:</span></span>
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
       ```

</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a><span data-ttu-id="153e0-124">使用 Lync Server [控制台] 建立頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="153e0-124">To create bandwidth policy profiles by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="153e0-125">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="153e0-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="153e0-126">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="153e0-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="153e0-127">在左側導覽列中，按一下 [**網路**設定]。</span><span class="sxs-lookup"><span data-stu-id="153e0-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="153e0-128">按一下 [**原則設定檔**] 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="153e0-128">Click the **Policy Profile** navigation button.</span></span>

4.  <span data-ttu-id="153e0-129">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="153e0-129">Click **New**.</span></span>

5.  <span data-ttu-id="153e0-130">在 [**新增原則設定檔**] 頁面上，按一下 [**名稱**]，然後輸入頻寬原則設定檔的名稱。</span><span class="sxs-lookup"><span data-stu-id="153e0-130">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>

6.  <span data-ttu-id="153e0-131">按一下 [**音訊限制**]，然後輸入允許所有音訊會話合併的最大 kbps 數。</span><span class="sxs-lookup"><span data-stu-id="153e0-131">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>

7.  <span data-ttu-id="153e0-132">按一下 [**音訊會話限制**]，然後輸入每個個別音訊會話允許的最大 kbps 數。</span><span class="sxs-lookup"><span data-stu-id="153e0-132">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>

8.  <span data-ttu-id="153e0-133">按一下 [**影片限制**]，然後輸入允許所有視頻會話合併的最大 kbps 數。</span><span class="sxs-lookup"><span data-stu-id="153e0-133">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>

9.  <span data-ttu-id="153e0-134">按一下 [**視頻會話限制**]，然後輸入每個個別影片會話允許的最大 kbps 數。</span><span class="sxs-lookup"><span data-stu-id="153e0-134">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>

10. <span data-ttu-id="153e0-135">或者，按一下 [**描述**]，然後輸入其他資訊來描述此頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="153e0-135">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>

11. <span data-ttu-id="153e0-136">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="153e0-136">Click **Commit**.</span></span>

12. <span data-ttu-id="153e0-137">若要完成建立拓撲的頻寬原則設定檔，請重複步驟4到11，以及其他頻寬策略設定檔的設定。</span><span class="sxs-lookup"><span data-stu-id="153e0-137">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


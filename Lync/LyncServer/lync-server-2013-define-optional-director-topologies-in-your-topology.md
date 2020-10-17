---
title: Lync Server 2013：在拓撲中定義選用的 Director 拓撲
description: Lync Server 2013：在拓撲中定義選用的 Director 拓撲。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bc82108d4277969489739fc81db07ec6f96bb96
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542649"
---
# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a><span data-ttu-id="d4066-103">在您的拓撲中為 Lync Server 2013 定義選用的 Director 拓撲</span><span class="sxs-lookup"><span data-stu-id="d4066-103">Define optional Director topologies in your topology for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4066-104">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="d4066-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="d4066-105">Lync Server 2013 Director 可以是單一實例伺服器，也可以以多個 Director 的負載平衡集區形式進行安裝，以獲得較高的可用性和容量。</span><span class="sxs-lookup"><span data-stu-id="d4066-105">Lync Server 2013 Directors can be single-instance servers or they can be installed as a load-balanced pool of multiple Directors for higher availability and capacity.</span></span> <span data-ttu-id="d4066-106">支援硬體負載平衡和網域名稱系統 (DNS) 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="d4066-106">Both hardware load balancing and Domain Name System (DNS) load balancing are supported.</span></span> <span data-ttu-id="d4066-107">本主題說明如何設定 Director 集區的 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="d4066-107">This topic explains how to configure DNS load balancing for Director pools.</span></span>

<span data-ttu-id="d4066-108">若要在您新增或移除伺服器角色時順利發行、啟用或停用拓撲，您應該以 **RTCUniversalServerAdmins** 和 **Domain Admins** 群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="d4066-108">To successfully publish, enable, or disable a topology when you add or remove a server role, you should be logged on as a user who is a member of the **RTCUniversalServerAdmins** and **Domain Admins** groups.</span></span> <span data-ttu-id="d4066-109">您也可以委派適當的系統管理員權力，以加入伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="d4066-109">You can also delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="d4066-110">如需詳細資訊，請參閱 Standard Edition server 或 Enterprise Edition server 部署檔中的 [Lync server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md) 。</span><span class="sxs-lookup"><span data-stu-id="d4066-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="d4066-111">針對其他設定變更，只需要 **RTCUniversalServerAdmins** 群組中的成員資格。</span><span class="sxs-lookup"><span data-stu-id="d4066-111">For other configuration changes, only membership in the **RTCUniversalServerAdmins** group is required.</span></span>

<span data-ttu-id="d4066-112">本主題說明為兩個 Director 拓撲定義及發行拓撲的步驟：</span><span class="sxs-lookup"><span data-stu-id="d4066-112">This topic describes the steps to define and publish the topology for the two Director topologies:</span></span>

  - <span data-ttu-id="d4066-113">若要定義 Director (單一實例) </span><span class="sxs-lookup"><span data-stu-id="d4066-113">To define the Director (single instance)</span></span>

  - <span data-ttu-id="d4066-114">若要定義 Director (多個 Director 集區) </span><span class="sxs-lookup"><span data-stu-id="d4066-114">To define the Director (multiple Director pool)</span></span>

<div>

## <a name="to-define-the-director-single-instance"></a><span data-ttu-id="d4066-115">若要定義 Director (單一實例) </span><span class="sxs-lookup"><span data-stu-id="d4066-115">To define the Director (single instance)</span></span>

1.  <span data-ttu-id="d4066-116">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="d4066-116">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="d4066-117">在 [歡迎] 頁面上，按一下 [ **從現有的部署下載拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="d4066-117">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="d4066-118">在 [ **另存拓撲** ] 對話方塊中，輸入現有拓撲的本機複本名稱和位置，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d4066-118">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="d4066-119">展開您計畫加入 Director 的網站，以滑鼠右鍵按一下 [ **Director**集區]，然後按一下 [ **新增 director 集**區]。</span><span class="sxs-lookup"><span data-stu-id="d4066-119">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="d4066-120">在 [ **定義 Director 集區 FQDN** ] 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d4066-120">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="d4066-121">在 [ **集區 FQDN**] 中，輸入 Director 集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d4066-121">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="d4066-122">按一下 **[單一電腦集區]**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d4066-122">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="d4066-123">在 [ **定義檔案共用** ] 對話方塊中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="d4066-123">In the **Define the file share** dialog box, do one of the following:</span></span>
    
    1.  <span data-ttu-id="d4066-124">若要使用現有的檔案共用，請按一下 [ **使用先前定義的檔案共用**]，然後從清單中選取檔案共用，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d4066-124">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
    2.  <span data-ttu-id="d4066-125">若要建立新的檔案共用，請按一下 [ **定義新的檔案共用**]，並在 [ **檔案伺服器 FQDN**] 中輸入檔案共用位置的 FQDN，在 [檔案 **共用**] 中輸入共用的名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d4066-125">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d4066-126">您在此步驟中所指定或建立的檔案共用，必須存在或在發佈拓撲之前建立。</span><span class="sxs-lookup"><span data-stu-id="d4066-126">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="d4066-127">指派給 Director 的檔案共用實際上並未使用，因此您可以指派組織中任何集區的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="d4066-127">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

7.  <span data-ttu-id="d4066-128">在 [ **指定 Web 服務 URL** ] 對話方塊的 [ **外部基礎 URL**] 中，指定 director 的 FQDN，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="d4066-128">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d4066-129">此名稱必須可從網際網路 DNS 伺服器解析，並指向反向 proxy 的公用 IP 位址，該位址會偵聽該 URL 的 HTTP/HTTPS 要求，並將其代理至該 Director 上的外部 Web 服務虛擬目錄。</span><span class="sxs-lookup"><span data-stu-id="d4066-129">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests to that URL and proxies them to the external Web Services virtual directory on that Director.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d4066-130">如果您有一個以上的前端集區或前端伺服器，則外部 Web 服務 FQDN 必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="d4066-130">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="d4066-131">例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為 <STRONG>pool01.contoso.com</STRONG>，則無法將 <STRONG>pool01.contoso.com</STRONG> 用於另一個前端集區或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="d4066-131">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="d4066-132">如果您也要部署 Director，則為任何 Director 或 Director 集區定義的外部 Web 服務 FQDN，都必須與任何其他 Director 或 Director 集區以及任何前端集區或前端伺服器都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="d4066-132">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="d4066-133">如果決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 必須與其他任何前端集區、Director 或 Director 集區是唯一的。</span><span class="sxs-lookup"><span data-stu-id="d4066-133">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

8.  <span data-ttu-id="d4066-134">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="d4066-134">Publish the topology.</span></span>

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a><span data-ttu-id="d4066-135">若要定義 Director (多個 Director 集區) </span><span class="sxs-lookup"><span data-stu-id="d4066-135">To define the Director (multiple Director pool)</span></span>

1.  <span data-ttu-id="d4066-136">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="d4066-136">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="d4066-137">在 [歡迎] 頁面上，按一下 [ **從現有的部署下載拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="d4066-137">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="d4066-138">在 [ **另存拓撲** ] 對話方塊中，輸入現有拓撲的本機複本名稱和位置，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d4066-138">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="d4066-139">展開您計畫加入 Director 的網站，以滑鼠右鍵按一下 [ **Director**集區]，然後按一下 [ **新增 director 集**區]。</span><span class="sxs-lookup"><span data-stu-id="d4066-139">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="d4066-140">在 [ **定義 Director 集區 FQDN** ] 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d4066-140">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="d4066-141">在 [ **集區 FQDN**] 中，輸入 Director 集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d4066-141">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="d4066-142">按一下 [多部電腦集區]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d4066-142">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="d4066-143">在 [ **定義此集區中的電腦** ] 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d4066-143">In the **Define the computers in this pool** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="d4066-144">指定第一個集區成員的電腦 FQDN，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="d4066-144">Specify the computer FQDN of the first pool member, and then click **Add**.</span></span>
    
      - <span data-ttu-id="d4066-145">針對您要新增的每一部電腦重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="d4066-145">Repeat the previous step for each computer that you want to add.</span></span> <span data-ttu-id="d4066-146">完成後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d4066-146">When you are finished, click **Next**.</span></span>

7.  <span data-ttu-id="d4066-147">在 [ **定義檔案共用** ] 對話方塊中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="d4066-147">In the **Define the file share** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="d4066-148">若要使用現有的檔案共用，請按一下 [ **使用先前定義的檔案共用**]，然後從清單中選取檔案共用，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d4066-148">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
      - <span data-ttu-id="d4066-149">若要建立新的檔案共用，請按一下 [ **定義新的檔案共用**]，並在 [ **檔案伺服器 FQDN**] 中輸入檔案共用位置的 FQDN，在 [檔案 **共用**] 中輸入共用的名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d4066-149">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d4066-150">您在此步驟中所指定或建立的檔案共用，必須存在或在發佈拓撲之前建立。</span><span class="sxs-lookup"><span data-stu-id="d4066-150">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="d4066-151">指派給 Director 的檔案共用實際上並未使用，因此您可以指派組織中任何集區的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="d4066-151">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

8.  <span data-ttu-id="d4066-152">在 [ **指定 Web 服務 URL** ] 對話方塊的 [ **外部基礎 URL**] 中，指定 director 的 FQDN，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="d4066-152">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d4066-153">此名稱必須可從網際網路 DNS 伺服器解析，並指向反向 proxy 的公用 IP 位址，該位址會偵聽傳送至該 URL 的 HTTP/HTTPS 要求，並將其代理至該 Director 集區上的外部 Web 服務虛擬目錄。</span><span class="sxs-lookup"><span data-stu-id="d4066-153">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests sent to that URL and proxies them to the external Web Services virtual directory on that Director pool.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d4066-154">如果您有一個以上的前端集區或前端伺服器，則外部 Web 服務 FQDN 必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="d4066-154">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="d4066-155">例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為 <STRONG>pool01.contoso.com</STRONG>，則無法將 <STRONG>pool01.contoso.com</STRONG> 用於另一個前端集區或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="d4066-155">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="d4066-156">如果您也要部署 Director，則為任何 Director 或 Director 集區定義的外部 Web 服務 FQDN，都必須與任何其他 Director 或 Director 集區以及任何前端集區或前端伺服器都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="d4066-156">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="d4066-157">如果決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 必須與其他任何前端集區、Director 或 Director 集區是唯一的。</span><span class="sxs-lookup"><span data-stu-id="d4066-157">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

9.  <span data-ttu-id="d4066-158">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="d4066-158">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


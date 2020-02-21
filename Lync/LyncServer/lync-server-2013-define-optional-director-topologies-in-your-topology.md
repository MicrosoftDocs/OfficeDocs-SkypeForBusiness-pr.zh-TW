---
title: Lync Server 2013： 在您的拓撲中定義選用的 Director 拓撲
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
ms.openlocfilehash: 0448ddfdb9988b791ff14dff89ab4c122df1d38f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a><span data-ttu-id="e5f26-102">Lync Server 2013 的拓撲中定義選用的 Director 拓撲</span><span class="sxs-lookup"><span data-stu-id="e5f26-102">Define optional Director topologies in your topology for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5f26-103">_**主題上次修改日期：** 2012年-09-08_</span><span class="sxs-lookup"><span data-stu-id="e5f26-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="e5f26-104">Lync Server 2013 Director 可以為單一執行個體的伺服器，或將它們安裝為高可用性和容量的多個 Director 負載平衡集區。</span><span class="sxs-lookup"><span data-stu-id="e5f26-104">Lync Server 2013 Directors can be single-instance servers or they can be installed as a load-balanced pool of multiple Directors for higher availability and capacity.</span></span> <span data-ttu-id="e5f26-105">支援的硬體負載平衡和網域名稱系統 (DNS) 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="e5f26-105">Both hardware load balancing and Domain Name System (DNS) load balancing are supported.</span></span> <span data-ttu-id="e5f26-106">本主題說明如何設定 DNS 負載平衡的 Director 集區。</span><span class="sxs-lookup"><span data-stu-id="e5f26-106">This topic explains how to configure DNS load balancing for Director pools.</span></span>

<span data-ttu-id="e5f26-107">若要成功發佈、 啟用或停用拓樸，當您新增或移除伺服器角色，您應該是 [ **RTCUniversalServerAdmins** ] 和 [ **Domain Admins**群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="e5f26-107">To successfully publish, enable, or disable a topology when you add or remove a server role, you should be logged on as a user who is a member of the **RTCUniversalServerAdmins** and **Domain Admins** groups.</span></span> <span data-ttu-id="e5f26-108">您也可以委派適當的系統管理員權限和權限新增伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="e5f26-108">You can also delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="e5f26-109">如需詳細資訊，請參閱 Standard Edition server 或 Enterprise Edition server 部署文件中的[Lync Server 2013 中的委派設定權限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="e5f26-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="e5f26-110">變更其他設定，只能**以 RTCUniversalServerAdmins**群組的成員資格的必要。</span><span class="sxs-lookup"><span data-stu-id="e5f26-110">For other configuration changes, only membership in the **RTCUniversalServerAdmins** group is required.</span></span>

<span data-ttu-id="e5f26-111">本主題說明的步驟來定義並發行兩個 Director 拓撲的拓撲：</span><span class="sxs-lookup"><span data-stu-id="e5f26-111">This topic describes the steps to define and publish the topology for the two Director topologies:</span></span>

  - <span data-ttu-id="e5f26-112">若要定義 Director （單一執行個體）</span><span class="sxs-lookup"><span data-stu-id="e5f26-112">To define the Director (single instance)</span></span>

  - <span data-ttu-id="e5f26-113">若要定義 Director （多個 Director 集區）</span><span class="sxs-lookup"><span data-stu-id="e5f26-113">To define the Director (multiple Director pool)</span></span>

<div>

## <a name="to-define-the-director-single-instance"></a><span data-ttu-id="e5f26-114">若要定義 Director （單一執行個體）</span><span class="sxs-lookup"><span data-stu-id="e5f26-114">To define the Director (single instance)</span></span>

1.  <span data-ttu-id="e5f26-115">啟動拓撲產生器： 按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 拓撲產生器]**。</span><span class="sxs-lookup"><span data-stu-id="e5f26-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="e5f26-116">在 [歡迎] 頁面上，按一下 [**從現有部署下載拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="e5f26-116">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="e5f26-117">在 [**另存拓撲**] 對話方塊中，輸入的名稱和位置的現有拓撲中的本機複本，然後按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="e5f26-117">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="e5f26-118">展開您要新增 Director，以滑鼠右鍵按一下 [ **Director 集區**，然後按一下 [**新增 Director 集區**的網站。</span><span class="sxs-lookup"><span data-stu-id="e5f26-118">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="e5f26-119">在 [**定義 Director 集區 FQDN** ] 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e5f26-119">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="e5f26-120">在 [**集區 FQDN**] 中，輸入 Director 集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e5f26-120">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="e5f26-121">按一下 **[單一電腦集區]**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e5f26-121">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="e5f26-122">在 [**定義檔案共用**] 對話方塊中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="e5f26-122">In the **Define the file share** dialog box, do one of the following:</span></span>
    
    1.  <span data-ttu-id="e5f26-123">若要使用現有的檔案共用，請按一下 [**使用先前定義的檔案共用**，從清單中選取檔案共用，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e5f26-123">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
    2.  <span data-ttu-id="e5f26-124">若要建立新的檔案共用，按一下 [**定義新的檔案共用**中**檔案伺服器 FQDN**] 中，輸入檔案共用之位置的 FQDN 中**檔案共用**，請輸入共用的名稱，然後按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e5f26-124">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e5f26-125">您指定，或在此步驟中建立的檔案共用必須存在於或建立之前發行的拓撲。</span><span class="sxs-lookup"><span data-stu-id="e5f26-125">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="e5f26-126">指派給 Director 的檔案共用實際上不會使用，因此您可以指派組織中任何集區的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="e5f26-126">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

7.  <span data-ttu-id="e5f26-127">在 [**指定 Web 服務 URL** ] 對話方塊，在 [**外部基底 URL**] 中，指定 Director 的 FQDN，然後按一下 [**完成]**。</span><span class="sxs-lookup"><span data-stu-id="e5f26-127">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e5f26-128">名稱必須可以解析為反向 proxy 會接聽該 URL 和 proxy 的 HTTP/HTTPS 要求他們至 Director 上的外部 Web 服務虛擬目錄的公用 IP 位址從網際網路 DNS 伺服器和點。</span><span class="sxs-lookup"><span data-stu-id="e5f26-128">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests to that URL and proxies them to the external Web Services virtual directory on that Director.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e5f26-129">如果您有一個以上的前端集區或前端伺服器的外部 Web 服務 FQDN 必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e5f26-129">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="e5f26-130">例如，如果您定義的外部 Web 服務的前端伺服器 FQDN 為<STRONG>pool01.contoso.com</STRONG>，您無法使用<STRONG>pool01.contoso.com</STRONG>另一個前端集區或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="e5f26-130">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="e5f26-131">如果您也要部署 Director、 外部 Web 服務 FQDN 定義任何 director 或 Director 集區必須是唯一的任何其他 Director 集區也為任何前端集區或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="e5f26-131">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="e5f26-132">如果決定要覆寫內部 web 服務以自我定義的 FQDN、 每個 FQDN 都必須是唯一因任何其他的前端集區、 Director 或 Director 集區。</span><span class="sxs-lookup"><span data-stu-id="e5f26-132">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

8.  <span data-ttu-id="e5f26-133">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="e5f26-133">Publish the topology.</span></span>

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a><span data-ttu-id="e5f26-134">若要定義 Director （多個 Director 集區）</span><span class="sxs-lookup"><span data-stu-id="e5f26-134">To define the Director (multiple Director pool)</span></span>

1.  <span data-ttu-id="e5f26-135">啟動拓撲產生器： 按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 拓撲產生器]**。</span><span class="sxs-lookup"><span data-stu-id="e5f26-135">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="e5f26-136">在 [歡迎] 頁面上，按一下 [**從現有部署下載拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="e5f26-136">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="e5f26-137">在 [**另存拓撲**] 對話方塊中，輸入的名稱和位置的現有拓撲中的本機複本，然後按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="e5f26-137">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="e5f26-138">展開您要新增 Director，以滑鼠右鍵按一下 [ **Director 集區**，然後按一下 [**新增 Director 集區**的網站。</span><span class="sxs-lookup"><span data-stu-id="e5f26-138">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="e5f26-139">在 [**定義 Director 集區 FQDN** ] 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e5f26-139">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="e5f26-140">在 [**集區 FQDN**] 中，輸入 Director 集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e5f26-140">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="e5f26-141">按一下 [多部電腦集區]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e5f26-141">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="e5f26-142">在 [**定義此集區中的電腦**] 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e5f26-142">In the **Define the computers in this pool** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="e5f26-143">指定第一個集區成員的電腦 FQDN，然後按一下 [**新增]**。</span><span class="sxs-lookup"><span data-stu-id="e5f26-143">Specify the computer FQDN of the first pool member, and then click **Add**.</span></span>
    
      - <span data-ttu-id="e5f26-144">重複上述步驟，為每個您想要新增的電腦。</span><span class="sxs-lookup"><span data-stu-id="e5f26-144">Repeat the previous step for each computer that you want to add.</span></span> <span data-ttu-id="e5f26-145">完成後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e5f26-145">When you are finished, click **Next**.</span></span>

7.  <span data-ttu-id="e5f26-146">在 [**定義檔案共用**] 對話方塊中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="e5f26-146">In the **Define the file share** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="e5f26-147">若要使用現有的檔案共用，請按一下 [**使用先前定義的檔案共用**，從清單中選取檔案共用，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e5f26-147">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
      - <span data-ttu-id="e5f26-148">若要建立新的檔案共用，按一下 [**定義新的檔案共用**中**檔案伺服器 FQDN**] 中，輸入檔案共用之位置的 FQDN 中**檔案共用**，請輸入共用的名稱，然後按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e5f26-148">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e5f26-149">您指定，或在此步驟中建立的檔案共用必須存在於或建立之前發行的拓撲。</span><span class="sxs-lookup"><span data-stu-id="e5f26-149">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="e5f26-150">指派給 Director 的檔案共用實際上不會使用，因此您可以指派組織中任何集區的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="e5f26-150">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

8.  <span data-ttu-id="e5f26-151">在 [**指定 Web 服務 URL** ] 對話方塊，在 [**外部基底 URL**] 中，指定 Director 的 FQDN，然後按一下 [**完成]**。</span><span class="sxs-lookup"><span data-stu-id="e5f26-151">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e5f26-152">名稱必須可以解析為反向 proxy 會接聽傳送至該 URL 及 proxy 它們以該 Director 集區上的外部 Web 服務虛擬目錄的 HTTP/HTTPS 要求的公用 IP 位址從網際網路 DNS 伺服器和點。</span><span class="sxs-lookup"><span data-stu-id="e5f26-152">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests sent to that URL and proxies them to the external Web Services virtual directory on that Director pool.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e5f26-153">如果您有一個以上的前端集區或前端伺服器的外部 Web 服務 FQDN 必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e5f26-153">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="e5f26-154">例如，如果您定義的外部 Web 服務的前端伺服器 FQDN 為<STRONG>pool01.contoso.com</STRONG>，您無法使用<STRONG>pool01.contoso.com</STRONG>另一個前端集區或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="e5f26-154">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="e5f26-155">如果您也要部署 Director、 外部 Web 服務 FQDN 定義任何 director 或 Director 集區必須是唯一的任何其他 Director 集區也為任何前端集區或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="e5f26-155">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="e5f26-156">如果決定要覆寫內部 web 服務以自我定義的 FQDN、 每個 FQDN 都必須是唯一因任何其他的前端集區、 Director 或 Director 集區。</span><span class="sxs-lookup"><span data-stu-id="e5f26-156">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

9.  <span data-ttu-id="e5f26-157">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="e5f26-157">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


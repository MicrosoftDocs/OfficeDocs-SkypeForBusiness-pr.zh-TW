---
title: 定義和設定前端集區或 Standard Edition Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ac840cb40da71f81a24501f3d9caa53fb316e86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="184f9-102">在 Lync Server 2013 中定義和設定前端集區或 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="184f9-102">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="184f9-103">_**主題上次修改日期：** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="184f9-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="184f9-104">此程式不需要本機系統管理員或許可權網域群組的成員資格。</span><span class="sxs-lookup"><span data-stu-id="184f9-104">This procedure does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="184f9-105">您應該以標準使用者的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="184f9-105">You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="184f9-106">如果您要部署企業伺服器，則池中的最小前端伺服器數必須在任何時間執行。</span><span class="sxs-lookup"><span data-stu-id="184f9-106">If you are deploying an Enterprise server, a minimum number of Front End Servers in a pool must be running at all times.</span></span> <span data-ttu-id="184f9-107">下表摘要說明這些需求。</span><span class="sxs-lookup"><span data-stu-id="184f9-107">The following table summarizes these requirements.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="184f9-108">池中的前端伺服器總數</span><span class="sxs-lookup"><span data-stu-id="184f9-108">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="184f9-109">必須執行才能供擁有池中運作的伺服器數量</span><span class="sxs-lookup"><span data-stu-id="184f9-109">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="184f9-110">1-2</span><span class="sxs-lookup"><span data-stu-id="184f9-110">1-2</span></span></p></td>
<td><p><span data-ttu-id="184f9-111">1</span><span class="sxs-lookup"><span data-stu-id="184f9-111">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="184f9-112">3-4</span><span class="sxs-lookup"><span data-stu-id="184f9-112">3-4</span></span></p></td>
<td><p><span data-ttu-id="184f9-113">pplx-2</span><span class="sxs-lookup"><span data-stu-id="184f9-113">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="184f9-114">5-6</span><span class="sxs-lookup"><span data-stu-id="184f9-114">5-6</span></span></p></td>
<td><p><span data-ttu-id="184f9-115">3</span><span class="sxs-lookup"><span data-stu-id="184f9-115">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="184f9-116">7-8</span><span class="sxs-lookup"><span data-stu-id="184f9-116">7-8</span></span></p></td>
<td><p><span data-ttu-id="184f9-117">4</span><span class="sxs-lookup"><span data-stu-id="184f9-117">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="184f9-118">9-10</span><span class="sxs-lookup"><span data-stu-id="184f9-118">9-10</span></span></p></td>
<td><p><span data-ttu-id="184f9-119">500</span><span class="sxs-lookup"><span data-stu-id="184f9-119">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="184f9-120">11-12</span><span class="sxs-lookup"><span data-stu-id="184f9-120">11-12</span></span></p></td>
<td><p><span data-ttu-id="184f9-121">6</span><span class="sxs-lookup"><span data-stu-id="184f9-121">6</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="184f9-122">在 Lync Server 2013 中，您可以隨時從池中新增或移除前端伺服器，您必須重新開機服務。</span><span class="sxs-lookup"><span data-stu-id="184f9-122">For Lync Server 2013, any time you add or remove a Front End Server from the pool, you must restart services.</span></span> <span data-ttu-id="184f9-123">移除及新增伺服器應做為個別的作業。</span><span class="sxs-lookup"><span data-stu-id="184f9-123">Removing and adding servers should be done as separate operations.</span></span> <span data-ttu-id="184f9-124">例如，如果您要新增兩個前端伺服器並移除兩個前端伺服器，請使用下列程式：</span><span class="sxs-lookup"><span data-stu-id="184f9-124">For example, if you are going to add two Front End Servers and remove two Front End Servers, use the following process:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="184f9-125">移除兩個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="184f9-125">Remove the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="184f9-126">發佈並重新啟用拓撲。</span><span class="sxs-lookup"><span data-stu-id="184f9-126">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="184f9-127">重新開機服務</span><span class="sxs-lookup"><span data-stu-id="184f9-127">Restart the services</span></span></P>
> <LI>
> <P><span data-ttu-id="184f9-128">新增兩個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="184f9-128">Add the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="184f9-129">發佈並重新啟用拓撲。</span><span class="sxs-lookup"><span data-stu-id="184f9-129">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="184f9-130">重新開機服務。</span><span class="sxs-lookup"><span data-stu-id="184f9-130">Restart the services.</span></span></P></LI></OL>



</div>

<span data-ttu-id="184f9-131">定義拓朴之後，請使用下列程式為您的網站定義前端池。</span><span class="sxs-lookup"><span data-stu-id="184f9-131">After you have defined your topology, use the following procedure to define a Front End pool for your site.</span></span> <span data-ttu-id="184f9-132">如需定義拓朴的詳細資料，請參閱[在 Lync Server 2013 的拓撲產生器中定義及設定拓撲](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)。</span><span class="sxs-lookup"><span data-stu-id="184f9-132">For details about defining the topology, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span></span>

<div>

## <a name="to-define-a-front-end-pool"></a><span data-ttu-id="184f9-133">定義前端池</span><span class="sxs-lookup"><span data-stu-id="184f9-133">To define a Front End pool</span></span>

1.  <span data-ttu-id="184f9-134">在 [定義新的前臺端池] 嚮導的 [**定義新的前端池**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="184f9-134">In the Define New Front End Pool Wizard, on the **Define the New Front End pool** page, click **Next**.</span></span>

2.  <span data-ttu-id="184f9-135">在 [**定義前端端池 FQDN** ] 頁面上，輸入您要建立之池的完整功能變數名稱（FQDN），按一下 [**企業版頂層端池**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="184f9-135">On the **Define the Front End pool FQDN** page, enter a fully qualified domain name (FQDN) for the pool you are creating, click **Enterprise Edition Front End pool**, and then click **Next**.</span></span>

3.  <span data-ttu-id="184f9-136">在 [**定義此池中的電腦**] 頁面上，輸入池中第一個前端伺服器的電腦 FQDN，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="184f9-136">On the **Define the computers in this pool** page, enter a computer FQDN for the first Front End Server in the pool, and then click **Add**.</span></span> <span data-ttu-id="184f9-137">針對您想要新增至池中的任何其他電腦（最多十二個）重複此步驟，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="184f9-137">Repeat this step for any additional computers (up to twelve) that you want to add to the pool, and then click **Next**.</span></span>

4.  <span data-ttu-id="184f9-138">在 [**選取功能**] 頁面上，選取您要用於此前端池之功能的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="184f9-138">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="184f9-139">例如，如果您只部署立即訊息（IM）與目前狀態的功能，您可以選取 [**會議**] 核取方塊來允許多方 IM，但不會選取 [**撥入（PSTN）會議**]、[**企業語音**] 或 [**通話許可控制**] 核取方塊，因為它們代表語音、影片和共同作業會議功能。</span><span class="sxs-lookup"><span data-stu-id="184f9-139">For example, if you are deploying only instant messaging (IM) and presence features, you would select the **Conferencing** check box to allow multiparty IM but would not select the **Dial-in (PSTN) conferencing**, **Enterprise Voice**, or **Call Admission Control** check boxes, because they represent voice, video, and collaborative conferencing features.</span></span>
    
      - <span data-ttu-id="184f9-140">**會議**   此選項可啟用一組豐富的功能，包括：</span><span class="sxs-lookup"><span data-stu-id="184f9-140">**Conferencing**   This selection enables a rich set of features including:</span></span>
        
          - <span data-ttu-id="184f9-141">Im 會話中有超過兩個雙方的 IM。</span><span class="sxs-lookup"><span data-stu-id="184f9-141">IM with more than two parties in an IM session.</span></span>
        
          - <span data-ttu-id="184f9-142">會議，包括檔共同作業、應用程式共用和桌面共用。</span><span class="sxs-lookup"><span data-stu-id="184f9-142">Conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span>
        
          - <span data-ttu-id="184f9-143">A/V 會議，可讓使用者擁有即時音訊/視頻（A/V）會議，而不需要外部服務（例如 Live Meeting 服務或協力廠商音訊橋接器）。</span><span class="sxs-lookup"><span data-stu-id="184f9-143">A/V conferencing, which enables users to have real-time audio/video (A/V) conferences without the need for external services such as the Live Meeting service or a third-party audio bridge.</span></span>
    
      - <span data-ttu-id="184f9-144">**使用 [撥入（PSTN）會議**   ]，使用者可以在不需要音訊會議提供者的情況下，使用公開交換的電話網絡（pstn）電話來加入 Lync Server 2013 會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="184f9-144">**Dial-in (PSTN) conferencing**   Allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring an audio conferencing provider.</span></span>
    
      - <span data-ttu-id="184f9-145">**企業語音**   企業語音是 Lync Server 2013 的語音語音（VoIP）方案，可讓使用者撥打及接聽電話。</span><span class="sxs-lookup"><span data-stu-id="184f9-145">**Enterprise Voice**   Enterprise Voice is the Voice over IP (VoIP) solution in Lync Server 2013 that allows users to make and receive phone calls.</span></span> <span data-ttu-id="184f9-146">如果您打算使用 Lync Server 2013 進行語音通話、語音信箱，以及使用硬體裝置或軟體用戶端的其他功能，就可以部署此功能。</span><span class="sxs-lookup"><span data-stu-id="184f9-146">You would deploy this feature if you plan to use Lync Server 2013 for voice calls, voice mail, and other functions that use a hardware device or a software client.</span></span>
    
      - <span data-ttu-id="184f9-147">**呼叫許可控制（CAC）**   CAC 會根據可用的網路頻寬判斷是否允許建立即時通訊會話，例如語音或視頻通話。</span><span class="sxs-lookup"><span data-stu-id="184f9-147">**Call admission control (CAC)**   CAC determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="184f9-148">如果您只部署 IM 和目前狀態，則不需要 CAC，因為這兩個功能都不會使用 CAC。</span><span class="sxs-lookup"><span data-stu-id="184f9-148">If you have deployed only IM and presence, CAC is not needed because neither of these two features uses CAC.</span></span>
    
      - <span data-ttu-id="184f9-149">\*\*\*\*[封存封存] 提供一種方式，讓您能夠透過 Lync Server 2013 來封存 IM 內容、會議（會議）內容，或同時傳送這兩者。   </span><span class="sxs-lookup"><span data-stu-id="184f9-149">**Archiving**   Archiving provides a way for you to archive IM content, conferencing (meeting) content, or both that is sent through Lync Server 2013.</span></span>
    
      - <span data-ttu-id="184f9-150">**[監視**   監視伺服器] 可讓您收集數位資料來描述您的網路和端點的媒體質量、與 VoIP 通話相關的使用資訊、IM 訊息、A/V 交談、會議、應用程式共用及檔案傳輸，以及呼叫錯誤與失敗呼叫的疑難排解資訊。</span><span class="sxs-lookup"><span data-stu-id="184f9-150">**Monitoring**   Monitoring Server enables you to collect numerical data that describes the media quality on your network and endpoints, usage information related to VoIP calls, IM messages, A/V conversations, meetings, application sharing, and file transfers, and call error and troubleshooting information for failed calls.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="184f9-151">如果您想要在您的部署中啟用 CAC，必須在每個中央網站只啟用一個池中的 CAC。</span><span class="sxs-lookup"><span data-stu-id="184f9-151">If you would like to enable CAC in your deployment, it is required that you enable CAC in exactly one pool per central site.</span></span> <span data-ttu-id="184f9-152">如果您要部署語音功能或 A/V 會議，建議使用 CAC。</span><span class="sxs-lookup"><span data-stu-id="184f9-152">CAC is recommended if you are deploying voice features or A/V conferencing.</span></span>

    
    </div>
    
    <span data-ttu-id="184f9-153">下表顯示可用的功能（top），以及提供給使用者的功能（左圖）。</span><span class="sxs-lookup"><span data-stu-id="184f9-153">The following table shows the available features (top) and the functions offered to users (left).</span></span> <span data-ttu-id="184f9-154">表格中的選取範圍是您應該選取哪些專案，才能為您的組織啟用這些功能。</span><span class="sxs-lookup"><span data-stu-id="184f9-154">The selections in the table are what you should select to enable those features for your organization.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th></th>
    <th><span data-ttu-id="184f9-155">會議</span><span class="sxs-lookup"><span data-stu-id="184f9-155">Conferencing</span></span></th>
    <th><span data-ttu-id="184f9-156">電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="184f9-156">Dial-In Conferencing</span></span></th>
    <th><span data-ttu-id="184f9-157">企業語音</span><span class="sxs-lookup"><span data-stu-id="184f9-157">Enterprise Voice</span></span></th>
    <th><span data-ttu-id="184f9-158">通話許可控制</span><span class="sxs-lookup"><span data-stu-id="184f9-158">Call Admission Control</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="184f9-159">立即訊息與顯示狀態</span><span class="sxs-lookup"><span data-stu-id="184f9-159">Instant messaging and presence</span></span></p></td>
    <td><p><span data-ttu-id="184f9-160">X</span><span class="sxs-lookup"><span data-stu-id="184f9-160">X</span></span></p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="184f9-161">會議</span><span class="sxs-lookup"><span data-stu-id="184f9-161">Conferencing</span></span></p></td>
    <td><p><span data-ttu-id="184f9-162">X</span><span class="sxs-lookup"><span data-stu-id="184f9-162">X</span></span></p></td>
    <td><p><span data-ttu-id="184f9-163">X</span><span class="sxs-lookup"><span data-stu-id="184f9-163">X</span></span></p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="184f9-164">A/V 會議</span><span class="sxs-lookup"><span data-stu-id="184f9-164">A/V conferencing</span></span></p></td>
    <td><p><span data-ttu-id="184f9-165">X</span><span class="sxs-lookup"><span data-stu-id="184f9-165">X</span></span></p></td>
    <td><p><span data-ttu-id="184f9-166">X</span><span class="sxs-lookup"><span data-stu-id="184f9-166">X</span></span></p></td>
    <td></td>
    <td><p><span data-ttu-id="184f9-167">X</span><span class="sxs-lookup"><span data-stu-id="184f9-167">X</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="184f9-168">企業語音</span><span class="sxs-lookup"><span data-stu-id="184f9-168">Enterprise Voice</span></span></p></td>
    <td></td>
    <td></td>
    <td><p><span data-ttu-id="184f9-169">X</span><span class="sxs-lookup"><span data-stu-id="184f9-169">X</span></span></p></td>
    <td><p><span data-ttu-id="184f9-170">X</span><span class="sxs-lookup"><span data-stu-id="184f9-170">X</span></span></p></td>
    </tr>
    </tbody>
    </table>


5.  <span data-ttu-id="184f9-171">在 [**選取 collocated 伺服器角色**] 頁面上，您可以 Collocate 前端伺服器上的中繼伺服器，或將它部署為獨立伺服器。</span><span class="sxs-lookup"><span data-stu-id="184f9-171">On the **Select collocated server roles** page, you can to collocate the Mediation Server on the Front End Server or to deploy it as a stand-alone server.</span></span>
    
    <span data-ttu-id="184f9-172">您可以 collocate 前端池的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="184f9-172">You can collocate the Mediation Server on the Front End pool.</span></span>
    
      - <span data-ttu-id="184f9-173">如果您想要在企業版前端池中 collocate 轉送伺服器，請確認已選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="184f9-173">If you intend to collocate the Mediation Server on the Enterprise Edition Front End pool, ensure the check box is selected.</span></span> <span data-ttu-id="184f9-174">伺服器角色將會部署在池伺服器上。</span><span class="sxs-lookup"><span data-stu-id="184f9-174">The server role will be deployed on the pool servers.</span></span>
    
      - <span data-ttu-id="184f9-175">如果您想要將中繼伺服器部署為獨立伺服器，請清除適當的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="184f9-175">If you intend to deploy the Mediation Server as a stand-alone server, clear the appropriate check box.</span></span> <span data-ttu-id="184f9-176">在您完全部署前端伺服器之後，您將會在個別的部署步驟中部署轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="184f9-176">You will deploy Mediation Server in a separate deployment step after you completely deploy the Front End Server.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="184f9-177">我們建議您盡可能 collocate 中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="184f9-177">We recommend that you collocate the Mediation Server if possible.</span></span> <span data-ttu-id="184f9-178">如需 collocated 或獨立中繼伺服器支援的詳細資料，請參閱規劃檔中的<A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Lync server 2013 中的中繼伺服器元件與拓撲</A>。</span><span class="sxs-lookup"><span data-stu-id="184f9-178">For details about support for collocated or stand-alone Mediation Servers, see <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and topologies for Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

6.  <span data-ttu-id="184f9-179">[**關聯伺服器角色與此前端池**] 頁面可讓您定義伺服器角色，並將其與前端池建立關聯。</span><span class="sxs-lookup"><span data-stu-id="184f9-179">The **Associate server roles with this Front End pool** page lets you define and associate server roles with the Front End pool.</span></span> <span data-ttu-id="184f9-180">下列角色可供使用：</span><span class="sxs-lookup"><span data-stu-id="184f9-180">The following role is available:</span></span>
    
    <span data-ttu-id="184f9-181">**啟用邊緣池**   定義並關聯單一邊緣伺服器或邊緣伺服器池。</span><span class="sxs-lookup"><span data-stu-id="184f9-181">**Enable an Edge pool**   Defines and associates a single Edge Server or a pool of Edge Servers.</span></span> <span data-ttu-id="184f9-182">Edge 伺服器可協助組織內部使用者與組織外部人員之間的通訊與共同作業，包括聯盟使用者。</span><span class="sxs-lookup"><span data-stu-id="184f9-182">An Edge Server facilitates communication and collaboration between users inside the organization and people outside the organization, including federated users.</span></span>
    
    <span data-ttu-id="184f9-183">您可以使用兩種可能的案例來部署及關聯伺服器角色：</span><span class="sxs-lookup"><span data-stu-id="184f9-183">There are two possible scenarios that you can use to deploy and associate the server roles:</span></span>
    
    <span data-ttu-id="184f9-184">針對案例1，您正在定義新安裝的新拓撲。</span><span class="sxs-lookup"><span data-stu-id="184f9-184">For scenario one, you are defining a new topology for a new installation.</span></span> <span data-ttu-id="184f9-185">您可以採用下列兩種方式的其中一個方法來進行安裝：</span><span class="sxs-lookup"><span data-stu-id="184f9-185">You can approach the installation in one of two ways:</span></span>
    
      - <span data-ttu-id="184f9-186">讓核取方塊保持不動，然後繼續定義拓撲。</span><span class="sxs-lookup"><span data-stu-id="184f9-186">Leave the check box clear and proceed with defining the topology.</span></span> <span data-ttu-id="184f9-187">在您已發佈、設定及測試前端與後端伺服器角色之後，您可以再次執行拓撲建立程式，以將角色服務器新增到拓撲結構中。</span><span class="sxs-lookup"><span data-stu-id="184f9-187">After you have published, configured, and tested the Front End and Back End Server roles, you can run Topology Builder again to add the role servers to the topology.</span></span> <span data-ttu-id="184f9-188">此策略可讓您測試前端池和執行 SQL Server 的伺服器，而不需要額外的角色進一步複雜。</span><span class="sxs-lookup"><span data-stu-id="184f9-188">This strategy will enable you to test the Front End pool and the server running SQL Server without additional complications from additional roles.</span></span> <span data-ttu-id="184f9-189">完成初始測試之後，您可以再次執行拓撲建立器，以選取您需要部署的角色。</span><span class="sxs-lookup"><span data-stu-id="184f9-189">After you have completed your initial testing, you can run Topology Builder again to select the roles you need to deploy.</span></span>
    
      - <span data-ttu-id="184f9-190">選取您要安裝的角色，然後設定硬體以適應選取的角色。</span><span class="sxs-lookup"><span data-stu-id="184f9-190">Select roles that you need to install, and then set up the hardware to accommodate the selected roles.</span></span>
    
    <span data-ttu-id="184f9-191">若是案例二，您已有部署，且您的基礎結構已準備好使用新角色，或者您需要將現有角色與新的前端伺服器建立關聯：</span><span class="sxs-lookup"><span data-stu-id="184f9-191">For scenario two, you have an existing deployment and your infrastructure is ready for new roles or you need to associate existing roles with a new Front End Server:</span></span>
    
      - <span data-ttu-id="184f9-192">在這種情況下，您將會選取您想要部署或與新的前端伺服器建立關聯的角色。</span><span class="sxs-lookup"><span data-stu-id="184f9-192">In this case, you will select the roles that you intend to deploy or associate with the new Front End Server.</span></span> <span data-ttu-id="184f9-193">不論是哪一種情況，您都會繼續定義角色、設定任何所需的硬體，以及繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="184f9-193">In either case, you will proceed with the definition of the roles, set up any needed hardware, and proceed with the installation.</span></span>

7.  <span data-ttu-id="184f9-194">在 [**定義 SQL store** ] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="184f9-194">On the **Define the SQL store** page, do one of the following:</span></span>
    
      - <span data-ttu-id="184f9-195">若要使用已在拓撲中定義的現有 SQL Server store，請選取 **[SQL store**] 中的實例。</span><span class="sxs-lookup"><span data-stu-id="184f9-195">To use an existing SQL Server store that has already been defined in your topology, select an instance from **SQL store**.</span></span>
    
      - <span data-ttu-id="184f9-196">若要定義新的 SQL Server 實例來儲存 [池資訊]，請按一下 [**新增**]，然後在 [**定義新的 sql store** ] 對話方塊中指定**SQL Server FQDN**。</span><span class="sxs-lookup"><span data-stu-id="184f9-196">To define a new SQL Server instance to store pool information, click **New** and then specify the **SQL Server FQDN**in the **Define New SQL Store** dialog box.</span></span>
    
      - <span data-ttu-id="184f9-197">若要指定 SQL Server 實例的名稱，請選取 [**命名實例**]，然後指定實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="184f9-197">To specify the name of a SQL Server instance, select **Named Instance**, and then specify the name of the instance.</span></span>
    
      - <span data-ttu-id="184f9-198">若要使用預設實例，請按一下 [**預設實例**]。</span><span class="sxs-lookup"><span data-stu-id="184f9-198">To use the default instance, click **Default instance**.</span></span>
    
      - <span data-ttu-id="184f9-199">若要使用 SQL 鏡像，請選取 **[啟用 sql 鏡像**]，然後選取現有的實例或建立新的實例。</span><span class="sxs-lookup"><span data-stu-id="184f9-199">To use SQL Mirroring, select **Enable SQL mirroring** and select an existing instance or create a new instance.</span></span>

8.  <span data-ttu-id="184f9-200">在 [**定義檔案共用**] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="184f9-200">On the **Define the file share** page, do one of the following:</span></span>
    
      - <span data-ttu-id="184f9-201">若要使用已在您的拓撲中定義的檔案共用，請選取 [**使用先前定義**的檔案共用]。</span><span class="sxs-lookup"><span data-stu-id="184f9-201">To use a file share that has already been defined in your topology, select **Use a previously defined file share**.</span></span>
    
      - <span data-ttu-id="184f9-202">若要定義新的檔案共用，請選取 [**定義新的檔案共用**]，在 [檔案**伺服器 FQDN** ] 方塊中，輸入檔案共用所在之現有檔案伺服器的 FQDN，然後在 [檔案**共用**] 方塊中輸入檔案共用的名稱。</span><span class="sxs-lookup"><span data-stu-id="184f9-202">To define a new file share, select **Define a new file share**, in the **File Server FQDN** box, enter the FQDN of the existing file server where the file share is to reside, and then enter a name for the file share in the **File Share** box.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="184f9-203">Lync Server 2013 的檔案共用無法位於前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="184f9-203">The file share for Lync Server 2013 cannot be located on the Front End Server.</span></span> <span data-ttu-id="184f9-204">請注意，在這個範例中，檔案共用已位於 SQL Server 的後端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="184f9-204">Note that in this example, the file share has been located on the SQL Server-based Back End Server.</span></span> <span data-ttu-id="184f9-205">這可能不是貴組織需求的最佳位置，而是檔案伺服器可能是較佳的選擇。</span><span class="sxs-lookup"><span data-stu-id="184f9-205">This might not be an optimal location for your organization’s requirements, and a file server might be a better choice.</span></span> <span data-ttu-id="184f9-206">您可以定義檔案共用，但不需要建立檔案共用。</span><span class="sxs-lookup"><span data-stu-id="184f9-206">You can define the file share without the file share having been created.</span></span> <span data-ttu-id="184f9-207">您必須先在您定義的位置中建立檔案共用，然後才能發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="184f9-207">You will need to create the file share in the location you define before you publish the topology.</span></span>

    
    </div>

9.  <span data-ttu-id="184f9-208">在 [**指定 Web 服務 URL** ] 頁面上，執行下列其中一項或兩項操作：</span><span class="sxs-lookup"><span data-stu-id="184f9-208">On the **Specify the Web Services URL** page, do one or both of the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="184f9-209">基底 URL 是 URL 的 Web 服務身分識別，而不是 HTTPs://。</span><span class="sxs-lookup"><span data-stu-id="184f9-209">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="184f9-210">例如，如果該池的 Web 服務的完整 URL 是https://pool01.contoso.net，則基底 url 是 pool01.contoso.net。</span><span class="sxs-lookup"><span data-stu-id="184f9-210">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="184f9-211">如果您有多個前端池或前端伺服器，則外部 Web 服務 FQDN 必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="184f9-211">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="184f9-212">例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為<STRONG>pool01.contoso.com</STRONG>，則無法將<STRONG>pool01.contoso.com</STRONG>用於另一個前端池或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="184f9-212">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span>

    
    </div>
    
    1.  <span data-ttu-id="184f9-213">如果您要設定 DNS 負載平衡，請選取 [覆**寫內部 Web 服務池 FQDN** ] 核取方塊，輸入內部基底 url （其必須與 [池 fqdn] 不同，例如，在**內部基 url**中則\>可以是內部\<基礎 url）。</span><span class="sxs-lookup"><span data-stu-id="184f9-213">If you are configuring DNS load balancing, select the **Override internal Web Services pool FQDN** check box, enter the internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>) in **Internal Base URL**.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="184f9-214">如果您決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 都必須是與任何其他的前端池、控制器或主管池都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="184f9-214">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span> <span data-ttu-id="184f9-215">在定義 Url 或完整功能變數名稱時，<STRONG>只使用標準字元</STRONG>（包括 a-z、A 至 z、0–9和連字號）。</span><span class="sxs-lookup"><span data-stu-id="184f9-215"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when defining URLs or fully qualified domain names.</span></span> <span data-ttu-id="184f9-216">請勿使用 Unicode 字元或底線。</span><span class="sxs-lookup"><span data-stu-id="184f9-216">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="184f9-217">外部 DNS 和公用 Ca 通常不支援 URL 或 FQDN 中的非標準字元（也就是，當 URL 或 FQDN 必須指派給憑證中的消費者名稱或消費者替換名稱時）。</span><span class="sxs-lookup"><span data-stu-id="184f9-217">Nonstandard characters in a URL or FQDN are often not supported by external DNS and public CAs (that is, when the URL or FQDN must be assigned to the subject name or subject alternative name in the certificate).</span></span>

        
        </div>
    
    2.  <span data-ttu-id="184f9-218">您也可以選擇在**外部基底 url**中輸入外部基底 url。</span><span class="sxs-lookup"><span data-stu-id="184f9-218">Optionally enter the external base URL in **External Base URL**.</span></span> <span data-ttu-id="184f9-219">您可以輸入外部基底 URL，讓它有別于您的內部網域命名。</span><span class="sxs-lookup"><span data-stu-id="184f9-219">You would enter the external base URL to differentiate it from your internal domain naming.</span></span> <span data-ttu-id="184f9-220">例如，您的內部網域是 contoso.net，但是您的外部功能變數名稱是 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="184f9-220">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="184f9-221">您可以使用 contoso.com 功能變數名稱定義 URL。</span><span class="sxs-lookup"><span data-stu-id="184f9-221">You would define the URL using the contoso.com domain name.</span></span> <span data-ttu-id="184f9-222">在反向 proxy 的情況下，這也很重要。</span><span class="sxs-lookup"><span data-stu-id="184f9-222">This is also important in the case of a reverse proxy.</span></span> <span data-ttu-id="184f9-223">外部基底 URL 功能變數名稱會與反向 proxy 的 FQDN 功能變數名稱相同。</span><span class="sxs-lookup"><span data-stu-id="184f9-223">The external base URL domain name would be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="184f9-224">立即訊息和目前狀態會要求對前端池進行 HTTP 存取。</span><span class="sxs-lookup"><span data-stu-id="184f9-224">Instant messaging and presence does require HTTP access to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="184f9-225">若要使用 DNS 負載平衡，您必須建立適當的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="184f9-225">To use DNS load balancing, you must create the appropriate DNS records.</span></span> <span data-ttu-id="184f9-226">如需詳細資訊，請參閱<A href="lync-server-2013-configure-dns-for-load-balancing.md">在 Lync Server 2013 中設定負載平衡的 DNS</A>。</span><span class="sxs-lookup"><span data-stu-id="184f9-226">For details, see <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configure DNS for load balancing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="184f9-227">如果您在 [**選取功能**] 頁面上選取 [**會議**]，請在 [**選取 office web apps 伺服器**] 頁面上選取 [**與 office web** Apps 伺服器關聯]，然後按一下 [**新增**] （或從下拉式清單中選取現有的 Office Web apps 伺服器）。</span><span class="sxs-lookup"><span data-stu-id="184f9-227">If you selected **Conferencing** on the **Select Features** page, on the **Select an Office Web Apps Server** page select **Associate pool with an Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

11. <span data-ttu-id="184f9-228">在 [**定義新的 Office Web Apps 伺服器**] 對話方塊的 [ **Office WEB apps server FQDN** ] 方塊中，輸入您 office web apps server 電腦的完整功能變數名稱（FQDN）;當您這樣做時，您的 Office Web Apps 伺服器探索 URL 應該會自動輸入至 [ **Office Web Apps server 探索 url** ] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="184f9-228">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="184f9-229">如果 Office Web Apps 伺服器安裝于內部部署，且位於與 Lync Server 2013 相同的網路區域中，則不應選取 [ **Office Web Apps 伺服器] 部署在外部網路（也就是 [週邊/網際網路]）** 。</span><span class="sxs-lookup"><span data-stu-id="184f9-229">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="184f9-230">如果 Office Web Apps 伺服器是在您的內部防火牆外部署，請選取 [ **Office Web Apps 伺服器] 部署在外部網路（也就是 [週邊/網際網路]）**。</span><span class="sxs-lookup"><span data-stu-id="184f9-230">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="184f9-231">如需詳細資訊，請參閱設定<A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">與 Office Web Apps server 和 Lync server 2013 的整合</A>。</span><span class="sxs-lookup"><span data-stu-id="184f9-231">For details, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="184f9-232">在 [**定義存檔 SQL store** ] 頁面上，選取現有的實例或 SQL Server，或定義新的實例來儲存與封存資料相關的資料。</span><span class="sxs-lookup"><span data-stu-id="184f9-232">On the **Define the Archiving SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with archiving data.</span></span>

13. <span data-ttu-id="184f9-233">在 [**定義監視 SQL 存放區**] 頁面上，選取現有的實例或 SQL Server，或定義新的實例來儲存與監視資料相關聯的資料。</span><span class="sxs-lookup"><span data-stu-id="184f9-233">On the **Define the Monitoring SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with monitoring data.</span></span>

14. <span data-ttu-id="184f9-234">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="184f9-234">Click **Next**.</span></span> <span data-ttu-id="184f9-235">如果您在 [**關聯伺服器角色與此前端池**] 頁面上定義其他角色服務器，則會開啟 [個別角色配置] 嚮導頁面，讓您設定伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="184f9-235">If you defined other role servers on the **Associate server roles with this Front End pool** page, separate role configuration wizard pages will open to let you configure the server roles.</span></span> <span data-ttu-id="184f9-236">如需詳細資訊，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="184f9-236">For details, see the following:</span></span>
    
    [<span data-ttu-id="184f9-237">在 Lync Server 2013 中部署外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="184f9-237">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

15. <span data-ttu-id="184f9-238">如果您沒有選取要設定和部署的其他伺服器角色，或者當您已完成其他角色服務器的設定，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="184f9-238">If you did not select additional server roles to configure and deploy, or when you have finished the configuration of the additional role servers, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


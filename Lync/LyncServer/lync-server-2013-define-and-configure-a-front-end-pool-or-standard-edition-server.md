---
title: 定義及設定前端集區或 Standard Edition server
description: 定義及設定前端集區或 Standard Edition server。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd632564f0a5afd1f899ee8487f633c4685d12a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569979"
---
# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="21b87-103">在 Lync Server 2013 中定義及設定前端集區或 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="21b87-103">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21b87-104">_**主題上次修改日期：** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="21b87-104">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="21b87-p101">此程序不需要本機系統管理員或已授權網域群組中的成員資格。您應該以標準使用者身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="21b87-p101">This procedure does not require membership in a local administrator or privileged domain group. You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="21b87-107">如果您要部署企業伺服器，集區中的前端伺服器數目下限必須在任何時間執行。</span><span class="sxs-lookup"><span data-stu-id="21b87-107">If you are deploying an Enterprise server, a minimum number of Front End Servers in a pool must be running at all times.</span></span> <span data-ttu-id="21b87-108">下表摘要說明這些需求。</span><span class="sxs-lookup"><span data-stu-id="21b87-108">The following table summarizes these requirements.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21b87-109">集區中的前端伺服器總數</span><span class="sxs-lookup"><span data-stu-id="21b87-109">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="21b87-110">集區執行運作所需的伺服器數目</span><span class="sxs-lookup"><span data-stu-id="21b87-110">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21b87-111">1-2</span><span class="sxs-lookup"><span data-stu-id="21b87-111">1-2</span></span></p></td>
<td><p><span data-ttu-id="21b87-112">1 </span><span class="sxs-lookup"><span data-stu-id="21b87-112">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21b87-113">3-4</span><span class="sxs-lookup"><span data-stu-id="21b87-113">3-4</span></span></p></td>
<td><p><span data-ttu-id="21b87-114">第</span><span class="sxs-lookup"><span data-stu-id="21b87-114">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21b87-115">5-6</span><span class="sxs-lookup"><span data-stu-id="21b87-115">5-6</span></span></p></td>
<td><p><span data-ttu-id="21b87-116">個</span><span class="sxs-lookup"><span data-stu-id="21b87-116">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21b87-117">7-8</span><span class="sxs-lookup"><span data-stu-id="21b87-117">7-8</span></span></p></td>
<td><p><span data-ttu-id="21b87-118">4 </span><span class="sxs-lookup"><span data-stu-id="21b87-118">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21b87-119">9-10</span><span class="sxs-lookup"><span data-stu-id="21b87-119">9-10</span></span></p></td>
<td><p><span data-ttu-id="21b87-120">5 </span><span class="sxs-lookup"><span data-stu-id="21b87-120">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21b87-121">11-12</span><span class="sxs-lookup"><span data-stu-id="21b87-121">11-12</span></span></p></td>
<td><p><span data-ttu-id="21b87-122">6 </span><span class="sxs-lookup"><span data-stu-id="21b87-122">6</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="21b87-123">對於 Lync Server 2013，每當您在集區中新增或移除前端伺服器時，您必須重新開機服務。</span><span class="sxs-lookup"><span data-stu-id="21b87-123">For Lync Server 2013, any time you add or remove a Front End Server from the pool, you must restart services.</span></span> <span data-ttu-id="21b87-124">移除及新增伺服器應該做為個別的作業。</span><span class="sxs-lookup"><span data-stu-id="21b87-124">Removing and adding servers should be done as separate operations.</span></span> <span data-ttu-id="21b87-125">例如，如果您要新增兩部前端伺服器並移除兩部前端伺服器，請使用下列程式：</span><span class="sxs-lookup"><span data-stu-id="21b87-125">For example, if you are going to add two Front End Servers and remove two Front End Servers, use the following process:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="21b87-126">移除兩部前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="21b87-126">Remove the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="21b87-127">發佈並重新啟動拓撲。</span><span class="sxs-lookup"><span data-stu-id="21b87-127">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="21b87-128">重新開機服務</span><span class="sxs-lookup"><span data-stu-id="21b87-128">Restart the services</span></span></P>
> <LI>
> <P><span data-ttu-id="21b87-129">新增兩部前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="21b87-129">Add the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="21b87-130">發佈並重新啟動拓撲。</span><span class="sxs-lookup"><span data-stu-id="21b87-130">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="21b87-131">重新啟動服務。</span><span class="sxs-lookup"><span data-stu-id="21b87-131">Restart the services.</span></span></P></LI></OL>



</div>

<span data-ttu-id="21b87-132">定義好拓撲之後，請使用下列程式定義網站的前端集區。</span><span class="sxs-lookup"><span data-stu-id="21b87-132">After you have defined your topology, use the following procedure to define a Front End pool for your site.</span></span> <span data-ttu-id="21b87-133">如需定義拓撲的詳細資訊，請參閱 [在 Lync Server 2013 的拓撲產生器中定義及設定拓撲](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)。</span><span class="sxs-lookup"><span data-stu-id="21b87-133">For details about defining the topology, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span></span>

<div>

## <a name="to-define-a-front-end-pool"></a><span data-ttu-id="21b87-134">定義前端集區</span><span class="sxs-lookup"><span data-stu-id="21b87-134">To define a Front End pool</span></span>

1.  <span data-ttu-id="21b87-135">在 [定義新前端集區] 精靈的 **[定義新前端集區]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="21b87-135">In the Define New Front End Pool Wizard, on the **Define the New Front End pool** page, click **Next**.</span></span>

2.  <span data-ttu-id="21b87-136">在 [ **定義前端集區 FQDN** ] 頁面上，輸入您要建立之集區的完整功能變數名稱 (FQDN) ，按一下 [ **Enterprise Edition 前端集**區]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="21b87-136">On the **Define the Front End pool FQDN** page, enter a fully qualified domain name (FQDN) for the pool you are creating, click **Enterprise Edition Front End pool**, and then click **Next**.</span></span>

3.  <span data-ttu-id="21b87-137">在 [ **定義此集區中的電腦** ] 頁面上，輸入集區中第一部前端伺服器的電腦 FQDN，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="21b87-137">On the **Define the computers in this pool** page, enter a computer FQDN for the first Front End Server in the pool, and then click **Add**.</span></span> <span data-ttu-id="21b87-138">針對您要新增至集區的十二) ，對任何其他 (電腦重複此步驟，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="21b87-138">Repeat this step for any additional computers (up to twelve) that you want to add to the pool, and then click **Next**.</span></span>

4.  <span data-ttu-id="21b87-139">在「選取功能」\*\*\*\* 頁面上，選取您希望此前端集區擁有的功能之對應核取方塊。</span><span class="sxs-lookup"><span data-stu-id="21b87-139">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="21b87-140">例如，如果您只部署立即訊息 (IM) 和目前狀態功能，您可以選取 [ **會議** ] 核取方塊以允許多方 IM，但不會選取 **撥入 (PSTN) 會議**、 **Enterprise Voice**或 **通話許可控制** 核取方塊，因為它們代表語音、影片及共同作業會議功能。</span><span class="sxs-lookup"><span data-stu-id="21b87-140">For example, if you are deploying only instant messaging (IM) and presence features, you would select the **Conferencing** check box to allow multiparty IM but would not select the **Dial-in (PSTN) conferencing**, **Enterprise Voice**, or **Call Admission Control** check boxes, because they represent voice, video, and collaborative conferencing features.</span></span>
    
      - <span data-ttu-id="21b87-141">**會議**    這種選取範圍可啟用一組豐富的功能，包括：</span><span class="sxs-lookup"><span data-stu-id="21b87-141">**Conferencing**   This selection enables a rich set of features including:</span></span>
        
          - <span data-ttu-id="21b87-142">Im 會話中有兩個以上的多方的 IM。</span><span class="sxs-lookup"><span data-stu-id="21b87-142">IM with more than two parties in an IM session.</span></span>
        
          - <span data-ttu-id="21b87-143">會議，包含檔共同作業、應用程式共用和桌面共用。</span><span class="sxs-lookup"><span data-stu-id="21b87-143">Conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span>
        
          - <span data-ttu-id="21b87-144">A/V 會議，可讓使用者 (A/V) 會議，而不需要使用外部服務（例如 Live Meeting 服務或協力廠商音訊橋）進行即時音訊/視頻。</span><span class="sxs-lookup"><span data-stu-id="21b87-144">A/V conferencing, which enables users to have real-time audio/video (A/V) conferences without the need for external services such as the Live Meeting service or a third-party audio bridge.</span></span>
    
      - <span data-ttu-id="21b87-145">**電話撥入 (PSTN) 會議**    使用公用交換電話網路 (PSTN) 電話，而不需要音訊會議提供者，允許使用者加入 Lync Server 2013 會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="21b87-145">**Dial-in (PSTN) conferencing**   Allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring an audio conferencing provider.</span></span>
    
      - <span data-ttu-id="21b87-146">**Enterprise Voice**    Enterprise Voice 是 Lync Server 2013 中的 Voice over IP (VoIP) 方案，可讓使用者撥打和接聽電話。</span><span class="sxs-lookup"><span data-stu-id="21b87-146">**Enterprise Voice**   Enterprise Voice is the Voice over IP (VoIP) solution in Lync Server 2013 that allows users to make and receive phone calls.</span></span> <span data-ttu-id="21b87-147">如果您打算使用 Lync Server 2013 進行語音通話、語音信箱，以及使用硬體裝置或軟體用戶端的其他功能，則會部署此功能。</span><span class="sxs-lookup"><span data-stu-id="21b87-147">You would deploy this feature if you plan to use Lync Server 2013 for voice calls, voice mail, and other functions that use a hardware device or a software client.</span></span>
    
      - <span data-ttu-id="21b87-148">\*\* (CAC) \*\*     的通話許可控制CAC 會根據可用的網路頻寬，判斷是否允許建立即時通訊會話（例如語音或視頻通話）。</span><span class="sxs-lookup"><span data-stu-id="21b87-148">**Call admission control (CAC)**   CAC determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="21b87-149">如果您只有部署 IM 與顯示狀態功能，那就不需要部署 CAC，因為兩者都不會用到 CAC 功能。</span><span class="sxs-lookup"><span data-stu-id="21b87-149">If you have deployed only IM and presence, CAC is not needed because neither of these two features uses CAC.</span></span>
    
      - <span data-ttu-id="21b87-150">**Archiving**封存    封存為您提供一種方式，可讓您封存透過 Lync Server 2013 傳送的 IM 內容、會議 (會議) 內容或兩者。</span><span class="sxs-lookup"><span data-stu-id="21b87-150">**Archiving**   Archiving provides a way for you to archive IM content, conferencing (meeting) content, or both that is sent through Lync Server 2013.</span></span>
    
      - <span data-ttu-id="21b87-151">**監控**    監控伺服器可讓您收集描述網路和端點上媒體質量的數值資料、與 VoIP 通話相關的使用資訊、IM 訊息、A/V 交談、會議、應用程式共用和檔案傳輸，以及呼叫錯誤和失敗通話的疑難排解資訊。</span><span class="sxs-lookup"><span data-stu-id="21b87-151">**Monitoring**   Monitoring Server enables you to collect numerical data that describes the media quality on your network and endpoints, usage information related to VoIP calls, IM messages, A/V conversations, meetings, application sharing, and file transfers, and call error and troubleshooting information for failed calls.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="21b87-152">如果您想要在部署中啟用 CAC，必須在每個中央網站的恰好一個集區中啟用 CAC。</span><span class="sxs-lookup"><span data-stu-id="21b87-152">If you would like to enable CAC in your deployment, it is required that you enable CAC in exactly one pool per central site.</span></span> <span data-ttu-id="21b87-153">如果您要部署語音功能或 A/V 會議，則建議使用 CAC。</span><span class="sxs-lookup"><span data-stu-id="21b87-153">CAC is recommended if you are deploying voice features or A/V conferencing.</span></span>

    
    </div>
    
    <span data-ttu-id="21b87-p110">下表說明可用的功能 (上方) 以及提供給使用者使用的功能 (左側)。表中的選項代表您應該為組織選取並啟用的功能。</span><span class="sxs-lookup"><span data-stu-id="21b87-p110">The following table shows the available features (top) and the functions offered to users (left). The selections in the table are what you should select to enable those features for your organization.</span></span>
    
    
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
    <th><span data-ttu-id="21b87-156">會議</span><span class="sxs-lookup"><span data-stu-id="21b87-156">Conferencing</span></span></th>
    <th><span data-ttu-id="21b87-157">電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="21b87-157">Dial-In Conferencing</span></span></th>
    <th><span data-ttu-id="21b87-158">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="21b87-158">Enterprise Voice</span></span></th>
    <th><span data-ttu-id="21b87-159">通話許可控制</span><span class="sxs-lookup"><span data-stu-id="21b87-159">Call Admission Control</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="21b87-160">立即訊息和顯示狀態</span><span class="sxs-lookup"><span data-stu-id="21b87-160">Instant messaging and presence</span></span></p></td>
    <td><p><span data-ttu-id="21b87-161">X</span><span class="sxs-lookup"><span data-stu-id="21b87-161">X</span></span></p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="21b87-162">會議</span><span class="sxs-lookup"><span data-stu-id="21b87-162">Conferencing</span></span></p></td>
    <td><p><span data-ttu-id="21b87-163">X</span><span class="sxs-lookup"><span data-stu-id="21b87-163">X</span></span></p></td>
    <td><p><span data-ttu-id="21b87-164">X</span><span class="sxs-lookup"><span data-stu-id="21b87-164">X</span></span></p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="21b87-165">A/V 會議</span><span class="sxs-lookup"><span data-stu-id="21b87-165">A/V conferencing</span></span></p></td>
    <td><p><span data-ttu-id="21b87-166">X</span><span class="sxs-lookup"><span data-stu-id="21b87-166">X</span></span></p></td>
    <td><p><span data-ttu-id="21b87-167">X</span><span class="sxs-lookup"><span data-stu-id="21b87-167">X</span></span></p></td>
    <td></td>
    <td><p><span data-ttu-id="21b87-168">X</span><span class="sxs-lookup"><span data-stu-id="21b87-168">X</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="21b87-169">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="21b87-169">Enterprise Voice</span></span></p></td>
    <td></td>
    <td></td>
    <td><p><span data-ttu-id="21b87-170">X</span><span class="sxs-lookup"><span data-stu-id="21b87-170">X</span></span></p></td>
    <td><p><span data-ttu-id="21b87-171">X</span><span class="sxs-lookup"><span data-stu-id="21b87-171">X</span></span></p></td>
    </tr>
    </tbody>
    </table>


5.  <span data-ttu-id="21b87-172">在 [ **選取組合的伺服器角色** ] 頁面上，您可以在前端伺服器上組合轉送伺服器，或將其部署為獨立伺服器。</span><span class="sxs-lookup"><span data-stu-id="21b87-172">On the **Select collocated server roles** page, you can to collocate the Mediation Server on the Front End Server or to deploy it as a stand-alone server.</span></span>
    
    <span data-ttu-id="21b87-173">您可以組合前端集區上的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="21b87-173">You can collocate the Mediation Server on the Front End pool.</span></span>
    
      - <span data-ttu-id="21b87-174">如果您想要在 Enterprise Edition 前端集區上組合轉送伺服器，請確定已選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="21b87-174">If you intend to collocate the Mediation Server on the Enterprise Edition Front End pool, ensure the check box is selected.</span></span> <span data-ttu-id="21b87-175">伺服器角色將會部署在集區伺服器上。</span><span class="sxs-lookup"><span data-stu-id="21b87-175">The server role will be deployed on the pool servers.</span></span>
    
      - <span data-ttu-id="21b87-176">如果您想要將轉送伺服器部署為獨立伺服器，請清除適當的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="21b87-176">If you intend to deploy the Mediation Server as a stand-alone server, clear the appropriate check box.</span></span> <span data-ttu-id="21b87-177">在您完全部署前端伺服器後，您會在個別的部署步驟中部署轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="21b87-177">You will deploy Mediation Server in a separate deployment step after you completely deploy the Front End Server.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="21b87-178">建議您盡可能組合轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="21b87-178">We recommend that you collocate the Mediation Server if possible.</span></span> <span data-ttu-id="21b87-179">如需有關組合或獨立轉送伺服器支援的詳細資訊，請參閱規劃檔中的 Lync Server 2013 中的「中繼」 <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">伺服器元件和拓撲</A> 。</span><span class="sxs-lookup"><span data-stu-id="21b87-179">For details about support for collocated or stand-alone Mediation Servers, see <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and topologies for Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

6.  <span data-ttu-id="21b87-180">[ **關聯伺服器角色與此前端集** 區] 頁面可讓您定義伺服器角色與前端集區的關聯。</span><span class="sxs-lookup"><span data-stu-id="21b87-180">The **Associate server roles with this Front End pool** page lets you define and associate server roles with the Front End pool.</span></span> <span data-ttu-id="21b87-181">下列為可用的角色：</span><span class="sxs-lookup"><span data-stu-id="21b87-181">The following role is available:</span></span>
    
    <span data-ttu-id="21b87-182">**啟用 Edge 集**     區定義及關聯單一 Edge Server 或 Edge Server 集區。</span><span class="sxs-lookup"><span data-stu-id="21b87-182">**Enable an Edge pool**   Defines and associates a single Edge Server or a pool of Edge Servers.</span></span> <span data-ttu-id="21b87-183">Edge Server 會協助組織內的使用者與組織外部的人員之間的通訊和共同作業，包括同盟使用者。</span><span class="sxs-lookup"><span data-stu-id="21b87-183">An Edge Server facilitates communication and collaboration between users inside the organization and people outside the organization, including federated users.</span></span>
    
    <span data-ttu-id="21b87-184">您可透過以下兩種案例，部署及關聯伺服器角色：</span><span class="sxs-lookup"><span data-stu-id="21b87-184">There are two possible scenarios that you can use to deploy and associate the server roles:</span></span>
    
    <span data-ttu-id="21b87-p116">在案例一當中，您可以為全新安裝定義新的拓撲。您可透過下列兩種方式之一進行安裝後續動作：</span><span class="sxs-lookup"><span data-stu-id="21b87-p116">For scenario one, you are defining a new topology for a new installation. You can approach the installation in one of two ways:</span></span>
    
      - <span data-ttu-id="21b87-187">保持核取方塊為清除，並繼續定義拓撲。</span><span class="sxs-lookup"><span data-stu-id="21b87-187">Leave the check box clear and proceed with defining the topology.</span></span> <span data-ttu-id="21b87-188">在發佈、設定及測試前端及後端伺服器角色之後，您可以再次執行拓撲產生器，將角色服務器新增至拓撲。</span><span class="sxs-lookup"><span data-stu-id="21b87-188">After you have published, configured, and tested the Front End and Back End Server roles, you can run Topology Builder again to add the role servers to the topology.</span></span> <span data-ttu-id="21b87-189">此策略可讓您測試前端集區和執行 SQL Server 的伺服器，而不需要其他角色的其他複雜工作。</span><span class="sxs-lookup"><span data-stu-id="21b87-189">This strategy will enable you to test the Front End pool and the server running SQL Server without additional complications from additional roles.</span></span> <span data-ttu-id="21b87-190">完成初始測試之後，您可以再次執行拓撲產生器，以選取需要部署的角色。</span><span class="sxs-lookup"><span data-stu-id="21b87-190">After you have completed your initial testing, you can run Topology Builder again to select the roles you need to deploy.</span></span>
    
      - <span data-ttu-id="21b87-191">選取您需要安裝的角色，然後設定硬體以容納選取的角色。</span><span class="sxs-lookup"><span data-stu-id="21b87-191">Select roles that you need to install, and then set up the hardware to accommodate the selected roles.</span></span>
    
    <span data-ttu-id="21b87-192">在案例二中，您有現有的部署，且您的基礎結構已準備好使用新角色，或您必須將現有的角色與新的前端伺服器關聯：</span><span class="sxs-lookup"><span data-stu-id="21b87-192">For scenario two, you have an existing deployment and your infrastructure is ready for new roles or you need to associate existing roles with a new Front End Server:</span></span>
    
      - <span data-ttu-id="21b87-193">在此情況下，您會選取要部署或與新前端伺服器產生關聯的角色。</span><span class="sxs-lookup"><span data-stu-id="21b87-193">In this case, you will select the roles that you intend to deploy or associate with the new Front End Server.</span></span> <span data-ttu-id="21b87-194">不管是哪一種情況，您都需要先定義角色並設定需要的硬體後，才開始安裝。</span><span class="sxs-lookup"><span data-stu-id="21b87-194">In either case, you will proceed with the definition of the roles, set up any needed hardware, and proceed with the installation.</span></span>

7.  <span data-ttu-id="21b87-195">在 [ **定義 SQL 存放區** ] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="21b87-195">On the **Define the SQL store** page, do one of the following:</span></span>
    
      - <span data-ttu-id="21b87-196">若要使用拓撲中已定義的現有 SQL Server 儲存區，請從 **[sql 存放區**] 中選取實例。</span><span class="sxs-lookup"><span data-stu-id="21b87-196">To use an existing SQL Server store that has already been defined in your topology, select an instance from **SQL store**.</span></span>
    
      - <span data-ttu-id="21b87-197">若要定義新的 SQL Server 實例以儲存集區資訊，請按一下 [**新增**]，然後在 [**定義新的 sql 存放區**] 對話方塊中指定**SQL Server FQDN**。</span><span class="sxs-lookup"><span data-stu-id="21b87-197">To define a new SQL Server instance to store pool information, click **New** and then specify the **SQL Server FQDN**in the **Define New SQL Store** dialog box.</span></span>
    
      - <span data-ttu-id="21b87-198">若要指定 SQL Server 實例的名稱，請選取 [ **命名實例**]，然後指定實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="21b87-198">To specify the name of a SQL Server instance, select **Named Instance**, and then specify the name of the instance.</span></span>
    
      - <span data-ttu-id="21b87-199">若要使用預設實例，請按一下 [ **預設實例**]。</span><span class="sxs-lookup"><span data-stu-id="21b87-199">To use the default instance, click **Default instance**.</span></span>
    
      - <span data-ttu-id="21b87-200">若要使用 SQL 鏡像，請選取 **[啟用 sql 鏡像** ]，然後選取現有的實例或建立新的實例。</span><span class="sxs-lookup"><span data-stu-id="21b87-200">To use SQL Mirroring, select **Enable SQL mirroring** and select an existing instance or create a new instance.</span></span>

8.  <span data-ttu-id="21b87-201">在 **[定義檔案共用]** 頁面上，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="21b87-201">On the **Define the file share** page, do one of the following:</span></span>
    
      - <span data-ttu-id="21b87-202">若要使用拓撲中已經定義的檔案共用，選取 **[使用先前定義的檔案共用]**。</span><span class="sxs-lookup"><span data-stu-id="21b87-202">To use a file share that has already been defined in your topology, select **Use a previously defined file share**.</span></span>
    
      - <span data-ttu-id="21b87-203">若要定義新的檔案共用，請選取 [ **定義新的檔案共用**]，然後在 [檔案 **伺服器 FQDN** ] 方塊中，輸入檔案共用所在的現有檔案伺服器的 FQDN，然後在 [檔案 **共用** ] 方塊中輸入檔案共用的名稱。</span><span class="sxs-lookup"><span data-stu-id="21b87-203">To define a new file share, select **Define a new file share**, in the **File Server FQDN** box, enter the FQDN of the existing file server where the file share is to reside, and then enter a name for the file share in the **File Share** box.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="21b87-204">Lync Server 2013 的檔案共用不能位於前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="21b87-204">The file share for Lync Server 2013 cannot be located on the Front End Server.</span></span> <span data-ttu-id="21b87-205">請注意，在此範例中，檔案共用位於以 SQL Server 為基礎的後端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="21b87-205">Note that in this example, the file share has been located on the SQL Server-based Back End Server.</span></span> <span data-ttu-id="21b87-206">這個位置可能不符合貴組織的最佳需求，使用檔案伺服器可能會更適合。</span><span class="sxs-lookup"><span data-stu-id="21b87-206">This might not be an optimal location for your organization’s requirements, and a file server might be a better choice.</span></span> <span data-ttu-id="21b87-207">您不需要先建立檔案共用，就能定義檔案共用。</span><span class="sxs-lookup"><span data-stu-id="21b87-207">You can define the file share without the file share having been created.</span></span> <span data-ttu-id="21b87-208">在您發行拓撲之前，必須先在定義檔案共用的位置上加以建立。</span><span class="sxs-lookup"><span data-stu-id="21b87-208">You will need to create the file share in the location you define before you publish the topology.</span></span>

    
    </div>

9.  <span data-ttu-id="21b87-209">在 [ **指定 Web 服務 URL** ] 頁面上，執行下列其中一項或兩項操作：</span><span class="sxs-lookup"><span data-stu-id="21b87-209">On the **Specify the Web Services URL** page, do one or both of the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="21b87-210">基底 URL 是 URL 的 Web 服務識別身分，去除 https://。</span><span class="sxs-lookup"><span data-stu-id="21b87-210">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="21b87-211">例如，如果集區的 Web 服務完整 URL 為 https://pool01.contoso.net ，則基本 url 為 pool01.contoso.net。</span><span class="sxs-lookup"><span data-stu-id="21b87-211">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="21b87-212">如果您有一個以上的前端集區或前端伺服器，則外部 Web 服務 FQDN 必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="21b87-212">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="21b87-213">例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為 <STRONG>pool01.contoso.com</STRONG>，則無法將 <STRONG>pool01.contoso.com</STRONG> 用於另一個前端集區或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="21b87-213">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span>

    
    </div>
    
    1.  <span data-ttu-id="21b87-214">若要設定 DNS 負載平衡，請選取 [覆 **寫內部 Web 服務集區 fqdn** ] 核取方塊，並輸入內部基本 url (，其必須與集區 FQDN 不同，例如內部的內部 \<your base URL\>) 內部 **基底 url**。</span><span class="sxs-lookup"><span data-stu-id="21b87-214">If you are configuring DNS load balancing, select the **Override internal Web Services pool FQDN** check box, enter the internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>) in **Internal Base URL**.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="21b87-215">如果您決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 必須與其他任何前端集區、Director 或 Director 集區是唯一的。</span><span class="sxs-lookup"><span data-stu-id="21b87-215">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span> <span data-ttu-id="21b87-216">在定義 URLs 或完全限定功能變數名稱時，<STRONG>只能使用標準字元</STRONG> (包括 A–Z、-Z、0–9和連字號) 。</span><span class="sxs-lookup"><span data-stu-id="21b87-216"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when defining URLs or fully qualified domain names.</span></span> <span data-ttu-id="21b87-217">請勿使用 Unicode 字元或底線。</span><span class="sxs-lookup"><span data-stu-id="21b87-217">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="21b87-218">在 URL 或 FQDN 中，通常不支援 URL 或 FQDN 中的非標準字元，也就是當 URL 或 FQDN 必須指派給憑證) 中的主體名稱或主體替代名稱時 (。</span><span class="sxs-lookup"><span data-stu-id="21b87-218">Nonstandard characters in a URL or FQDN are often not supported by external DNS and public CAs (that is, when the URL or FQDN must be assigned to the subject name or subject alternative name in the certificate).</span></span>

        
        </div>
    
    2.  <span data-ttu-id="21b87-219">（選用）在 [ **外部基礎 url**] 中輸入外部基底 url。</span><span class="sxs-lookup"><span data-stu-id="21b87-219">Optionally enter the external base URL in **External Base URL**.</span></span> <span data-ttu-id="21b87-220">您可以輸入外部基底 URL，使其有別于您的內部網域命名。</span><span class="sxs-lookup"><span data-stu-id="21b87-220">You would enter the external base URL to differentiate it from your internal domain naming.</span></span> <span data-ttu-id="21b87-221">例如，您的內部網域為 contoso.net，而外部網域名稱為 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="21b87-221">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="21b87-222">這時您可以使用 contoso.com 網域名稱來定義 URL。</span><span class="sxs-lookup"><span data-stu-id="21b87-222">You would define the URL using the contoso.com domain name.</span></span> <span data-ttu-id="21b87-223">在反向 Proxy 的情況中，這種作法也很重要。</span><span class="sxs-lookup"><span data-stu-id="21b87-223">This is also important in the case of a reverse proxy.</span></span> <span data-ttu-id="21b87-224">外部基底 URL 功能變數名稱會與反向 proxy 的 FQDN 功能變數名稱相同。</span><span class="sxs-lookup"><span data-stu-id="21b87-224">The external base URL domain name would be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="21b87-225">立即訊息和目前狀態確實需要存取前端集區的 HTTP。</span><span class="sxs-lookup"><span data-stu-id="21b87-225">Instant messaging and presence does require HTTP access to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="21b87-226">若要使用 DNS 負載平衡，您必須建立適當的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="21b87-226">To use DNS load balancing, you must create the appropriate DNS records.</span></span> <span data-ttu-id="21b87-227">如需詳細資訊，請參閱 <A href="lync-server-2013-configure-dns-for-load-balancing.md">在 Lync Server 2013 中設定 DNS 以進行負載平衡</A>。</span><span class="sxs-lookup"><span data-stu-id="21b87-227">For details, see <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configure DNS for load balancing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="21b87-228">如果您在 [**選取功能**] 頁面上選取 [**會議**]，請在 [**選取 office web apps server** ] 頁面上，選取 [**將集區與 office web apps server 建立關聯**]，然後按一下 [**新增** (] 或從下拉式清單中選取現有的 Office Web Apps server) 。</span><span class="sxs-lookup"><span data-stu-id="21b87-228">If you selected **Conferencing** on the **Select Features** page, on the **Select an Office Web Apps Server** page select **Associate pool with an Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

11. <span data-ttu-id="21b87-229">在 **[定義新的 Office Web Apps Server]** 對話方塊的 **[Office Web Apps Server FQDN]** 方塊中，鍵入 Office Web Apps Server 電腦的完整網域名稱 (FQDN)；執行此動作時，您的 Office Web Apps Server 探索 URL 應自動輸入至 **[Office Web Apps Server 探索 URL]** 方塊。</span><span class="sxs-lookup"><span data-stu-id="21b87-229">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="21b87-230">如果 Office Web Apps Server 安裝于內部部署，且與 Lync Server 2013 位於相同的網路區域中，則選項 \*\*Office Web Apps server 部署在外部網路中 (也就是說，不應該選取周邊/網際網路) \*\* 。</span><span class="sxs-lookup"><span data-stu-id="21b87-230">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="21b87-231">如果 Office Web Apps Server 部署在內部防火牆外，則選取 **[Office Web Apps Server 部署在外部網路 (亦即周邊/網際網路]** 選項。</span><span class="sxs-lookup"><span data-stu-id="21b87-231">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="21b87-232">如需詳細資訊，請參閱設定 <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Office Web Apps Server 和 Lync Server 2013 的整合</A>。</span><span class="sxs-lookup"><span data-stu-id="21b87-232">For details, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="21b87-233">在 [ **定義封存 SQL 存放區** ] 頁面上，選取現有的實例或 SQL Server，或定義新的實例以儲存與封存資料相關聯的資料。</span><span class="sxs-lookup"><span data-stu-id="21b87-233">On the **Define the Archiving SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with archiving data.</span></span>

13. <span data-ttu-id="21b87-234">在 [ **定義監控 SQL 存放區** ] 頁面上，選取現有的實例或 SQL Server，或定義新的實例以儲存與監控資料相關聯的資料。</span><span class="sxs-lookup"><span data-stu-id="21b87-234">On the **Define the Monitoring SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with monitoring data.</span></span>

14. <span data-ttu-id="21b87-235">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="21b87-235">Click **Next**.</span></span> <span data-ttu-id="21b87-236">如果您在 [ **關聯伺服器角色與此前端集** 區] 頁面上定義其他角色服務器，則會開啟 [不同角色設定] 頁面，讓您設定伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="21b87-236">If you defined other role servers on the **Associate server roles with this Front End pool** page, separate role configuration wizard pages will open to let you configure the server roles.</span></span> <span data-ttu-id="21b87-237">如需詳細資訊，請參閱下列各項：</span><span class="sxs-lookup"><span data-stu-id="21b87-237">For details, see the following:</span></span>
    
    [<span data-ttu-id="21b87-238">在 Lync Server 2013 中部署外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="21b87-238">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

15. <span data-ttu-id="21b87-239">如果您沒有選取要設定及部署的其他伺服器角色，或是當您已完成其他角色伺服器的組態時，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="21b87-239">If you did not select additional server roles to configure and deploy, or when you have finished the configuration of the additional role servers, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


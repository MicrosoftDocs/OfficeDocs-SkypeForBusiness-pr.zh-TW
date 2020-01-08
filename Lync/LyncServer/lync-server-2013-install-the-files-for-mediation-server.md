---
title: Lync Server 2013：安裝用於轉送作業伺服器的檔案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60274ced1bf72a17b4c05b4908f60bde32323f12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="c7861-102">在 Lync Server 2013 中安裝轉送服務伺服器的檔案</span><span class="sxs-lookup"><span data-stu-id="c7861-102">Install the files for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7861-103">_**主題上次修改日期：** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="c7861-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="c7861-104">若要成功完成這個程式，您應該至少以本機系統管理員和至少擁有 RTCUniversalReadOnlyAdmins 群組成員資格的網域使用者的身分登入伺服器。</span><span class="sxs-lookup"><span data-stu-id="c7861-104">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>

<span data-ttu-id="c7861-105">使用本主題中的步驟執行 Lync Server 2013 部署嚮導，在您使用拓撲建立器定義及發佈池時，在您新增到轉送伺服器池中的電腦上安裝中繼伺服器的檔案。</span><span class="sxs-lookup"><span data-stu-id="c7861-105">Use the steps in this topic to run Lync Server 2013 Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool when you used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="c7861-106">在安裝檔轉送伺服器時，您也會安裝並指派中繼伺服器池中每個電腦所需的憑證。</span><span class="sxs-lookup"><span data-stu-id="c7861-106">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span>

<span data-ttu-id="c7861-107">在此網站，如果您已在前端池或標準版伺服器上部署了轉送伺服器 collocated，您可以略過這個主題，而改為繼續[在 Lync server 2013 中設定 trunks](lync-server-2013-configuring-trunks.md)。</span><span class="sxs-lookup"><span data-stu-id="c7861-107">At this site, if you have already deployed Mediation Servers collocated on the Front End pools or Standard Edition server, you can skip this topic and, instead, continue to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7861-108">本主題假設您已定義併發布獨立的中繼伺服器池，如在 lync Server 2013 中的 [拓撲建立器] 中<A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">定義轉送伺服器</A>，並在部署檔中<A href="lync-server-2013-publish-the-topology.md">發佈 lync server 2013 中的拓朴</A>，且您已驗證轉送伺服器池中的電腦符合在企業版的 Lync server <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">2013</A>與<A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">安全性與設定必備元件中所述的先決條件Lync Server 2013 中的 [語音</A>]。</span><span class="sxs-lookup"><span data-stu-id="c7861-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool as described in <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Define a Mediation Server in Topology Builder in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation, and that you have verified that the computers in the Mediation Server pool meet the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="c7861-109">若要為獨立的中繼伺服器池安裝檔案</span><span class="sxs-lookup"><span data-stu-id="c7861-109">To install the files for a stand-alone Mediation Server pool</span></span>

1.  <span data-ttu-id="c7861-110">在安裝媒體中，以滑鼠右鍵\<按一下 [\>安裝媒體**\\安裝\\程式 amd64\\**setup.exe]，然後按一下 [**以系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="c7861-110">From the installation media, right-click \<installation media\>**\\Setup\\amd64\\Setup.exe**, and then click **Run as Administrator**.</span></span>

2.  <span data-ttu-id="c7861-111">在 [**安裝位置**] 頁面上，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c7861-111">On the **Installation Location** page, click **OK**.</span></span>

3.  <span data-ttu-id="c7861-112">在 [**使用者授權合約**] 頁面上，按一下 [**我接受**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c7861-112">On the **End User License Agreement** page, click **I accept**, and then click **OK**.</span></span> <span data-ttu-id="c7861-113">（需要才能繼續）。</span><span class="sxs-lookup"><span data-stu-id="c7861-113">(Required to continue.)</span></span>

4.  <span data-ttu-id="c7861-114">在 [ **Lync server 2010 部署嚮導]** 頁面上，按一下 [**安裝或更新 Lync Server 系統**]。</span><span class="sxs-lookup"><span data-stu-id="c7861-114">On the **Lync Server 2010 Deployment Wizard** page, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="c7861-115">在 [**步驟1：安裝本機設定儲存區**] 旁，按一下 [**執行**]，然後依照畫面上的指示進行。</span><span class="sxs-lookup"><span data-stu-id="c7861-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>

6.  <span data-ttu-id="c7861-116">在 [**設定中央管理儲存的本機複本**] 頁面上，接受 **[直接從中央管理存儲**的預設檢索]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c7861-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>

7.  <span data-ttu-id="c7861-117">在 [**執行命令**] 頁面上，當任務狀態顯示為 [**完成**] 時，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c7861-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

8.  <span data-ttu-id="c7861-118">在 [**步驟2：設定] 或 [移除 Lync Server 元件**] 旁，按一下 [**執行**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c7861-118">Next to **Step 2: Setup or Remove Lync Server Components**, click **Run**, and then click **Next**.</span></span>

9.  <span data-ttu-id="c7861-119">在 [**執行命令**] 頁面上，當任務狀態顯示為 [**完成**] 時，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c7861-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

10. <span data-ttu-id="c7861-120">在**步驟3：要求、安裝或指派憑證**，按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="c7861-120">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span> <span data-ttu-id="c7861-121">依照畫面上的指示進行，接受預設設定。</span><span class="sxs-lookup"><span data-stu-id="c7861-121">Follow the instructions on the screen, accepting the default settings.</span></span> <span data-ttu-id="c7861-122">中繼伺服器需要一個憑證，因此您執行的**步驟 3**兩次：一次是頒發所需的憑證，然後再將它指派給您。</span><span class="sxs-lookup"><span data-stu-id="c7861-122">The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>

11. <span data-ttu-id="c7861-123">在證書已頒發並指派正確之後，在**步驟4：啟動服務**，按一下 [**執行**]，然後依照畫面上的指示進行。</span><span class="sxs-lookup"><span data-stu-id="c7861-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>

12. <span data-ttu-id="c7861-124">當**步驟 4**成功完成時，請重新開機伺服器，並以 DomainAdmins 群組成員的身分登入伺服器。</span><span class="sxs-lookup"><span data-stu-id="c7861-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>

13. <span data-ttu-id="c7861-125">在執行 Lync Server [控制台] 的電腦上，確認 [Lync server 控制台] 的 [**拓撲**] 頁面上的 [中繼伺服器] 的服務狀態顯示為綠色核取記號。</span><span class="sxs-lookup"><span data-stu-id="c7861-125">On the computer where you are running Lync Server Control Panel, verify on the **Topology** page of Lync Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="c7861-126">如果改為顯示紅色 X，請選取中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="c7861-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="c7861-127">在 [**動作**] 功能表上，按一下 [**啟動所有服務**]。</span><span class="sxs-lookup"><span data-stu-id="c7861-127">On the **Action** menu, click **Start All Services**.</span></span>

<span data-ttu-id="c7861-128">如果您在中繼伺服器池中新增多個電腦，請在轉送伺服器池中的所有其他電腦上執行此程式中的步驟。</span><span class="sxs-lookup"><span data-stu-id="c7861-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="c7861-129">如果您不需要為任何其他電腦安裝轉送伺服器的檔案，請依照在[Lync server 2013 中設定 trunks 中](lync-server-2013-configuring-trunks.md)的程式，來設定此中繼伺服器池（或網站上的所有中繼伺服器）與對等機之間的中繼連線設定。</span><span class="sxs-lookup"><span data-stu-id="c7861-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c7861-130">請參閱</span><span class="sxs-lookup"><span data-stu-id="c7861-130">See Also</span></span>


[<span data-ttu-id="c7861-131">Lync Server 2013 中內部伺服器的憑證需求</span><span class="sxs-lookup"><span data-stu-id="c7861-131">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


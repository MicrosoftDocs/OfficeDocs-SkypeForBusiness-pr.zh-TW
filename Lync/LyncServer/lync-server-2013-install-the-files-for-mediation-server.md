---
title: Lync Server 2013：安裝轉送伺服器的檔案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc7fd5613b39fd17724c9b62152f9d9401fbc072
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498590"
---
# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="c7527-102">在 Lync Server 2013 中安裝轉送伺服器的檔案</span><span class="sxs-lookup"><span data-stu-id="c7527-102">Install the files for Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7527-103">_**主題上次修改日期：** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="c7527-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="c7527-104">若要順利完成此程式，您應該至少以本機系統管理員身分登入伺服器，以及至少擁有 RTCUniversalReadOnlyAdmins 群組成員資格的網域使用者。</span><span class="sxs-lookup"><span data-stu-id="c7527-104">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>

<span data-ttu-id="c7527-105">使用本主題中的步驟執行 Lync Server 2013 部署嚮導，在您使用拓撲產生器來定義及發行集區時，在您新增至轉送伺服器集區的電腦上，安裝轉送伺服器的檔案。</span><span class="sxs-lookup"><span data-stu-id="c7527-105">Use the steps in this topic to run Lync Server 2013 Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool when you used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="c7527-106">在安裝檔轉送伺服器時，您也會安裝並指派轉送伺服器集區中每一部電腦所需的憑證。</span><span class="sxs-lookup"><span data-stu-id="c7527-106">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span>

<span data-ttu-id="c7527-107">在此網站上，如果您已在前端集區或 Standard Edition server 上部署轉送伺服器組合，您可以略過本主題，而 [在 Lync server 2013 中](lync-server-2013-configuring-trunks.md)繼續設定主幹。</span><span class="sxs-lookup"><span data-stu-id="c7527-107">At this site, if you have already deployed Mediation Servers collocated on the Front End pools or Standard Edition server, you can skip this topic and, instead, continue to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7527-108">本主題假設您已定義及發佈獨立轉送伺服器集區，如在 <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Lync server 2013</A> 中的拓撲產生器中定義轉送伺服器和在部署檔 <A href="lync-server-2013-publish-the-topology.md">中發佈 lync server 2013 中的拓撲</A> 一節所述。而且，您已確認轉送伺服器集區中的電腦符合 lync Server 2013 中的 <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">enterprise voice server 先決條件</A> 中所述的必要條件，以及 <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Lync server 2013 中 enterprise voice 的安全性和設定必要條件</A>。</span><span class="sxs-lookup"><span data-stu-id="c7527-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool as described in <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Define a Mediation Server in Topology Builder in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation, and that you have verified that the computers in the Mediation Server pool meet the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="c7527-109">若要為獨立的轉送伺服器集區安裝檔案</span><span class="sxs-lookup"><span data-stu-id="c7527-109">To install the files for a stand-alone Mediation Server pool</span></span>

1.  <span data-ttu-id="c7527-110">在安裝媒體中，以滑鼠右鍵按一下 [ \<installation media\> \*\* \\ 安裝 \\ amd64 \\Setup.exe**]，然後按一下 [以**系統管理員身分執行\*\*]。</span><span class="sxs-lookup"><span data-stu-id="c7527-110">From the installation media, right-click \<installation media\>**\\Setup\\amd64\\Setup.exe**, and then click **Run as Administrator**.</span></span>

2.  <span data-ttu-id="c7527-111">在 [ **安裝位置** ] 頁面上，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c7527-111">On the **Installation Location** page, click **OK**.</span></span>

3.  <span data-ttu-id="c7527-112">在 [ **使用者授權合約** ] 頁面上，按一下 [ **我接受**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c7527-112">On the **End User License Agreement** page, click **I accept**, and then click **OK**.</span></span> <span data-ttu-id="c7527-113">需要 (才能繼續。 ) </span><span class="sxs-lookup"><span data-stu-id="c7527-113">(Required to continue.)</span></span>

4.  <span data-ttu-id="c7527-114">在 [ **Lync server 2010 部署嚮導]** 頁面上，按一下 [ **安裝或更新 Lync Server 系統**]。</span><span class="sxs-lookup"><span data-stu-id="c7527-114">On the **Lync Server 2010 Deployment Wizard** page, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="c7527-115">在 [ **步驟1：安裝本機設定存放區**] 旁邊，按一下 [ **執行**]，然後依照畫面上的指示進行。</span><span class="sxs-lookup"><span data-stu-id="c7527-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>

6.  <span data-ttu-id="c7527-116">在 [ **設定中央管理存放區的本機複本** ] 頁面上，接受 **直接從中央管理存放區進行**的預設檢索，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c7527-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>

7.  <span data-ttu-id="c7527-117">在 [ **執行命令** ] 頁面上，當工作狀態顯示為 [ **已完成**] 時，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c7527-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

8.  <span data-ttu-id="c7527-118">在 [ **步驟2：安裝或移除 Lync Server 元件**] 旁邊，按一下 [ **執行**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c7527-118">Next to **Step 2: Setup or Remove Lync Server Components**, click **Run**, and then click **Next**.</span></span>

9.  <span data-ttu-id="c7527-119">在 [ **執行命令** ] 頁面上，當工作狀態顯示為 [ **已完成**] 時，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c7527-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

10. <span data-ttu-id="c7527-120">在 [ **步驟3：要求、安裝或指派憑證**] 旁邊，按一下 [ **執行**]。</span><span class="sxs-lookup"><span data-stu-id="c7527-120">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span> <span data-ttu-id="c7527-121">依照畫面上的指示，接受預設設定。</span><span class="sxs-lookup"><span data-stu-id="c7527-121">Follow the instructions on the screen, accepting the default settings.</span></span> <span data-ttu-id="c7527-122">轉送伺服器需要一個憑證，因此您將執行 **步驟 3** 兩次：一次發出必要的憑證，再進行指派。</span><span class="sxs-lookup"><span data-stu-id="c7527-122">The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>

11. <span data-ttu-id="c7527-123">當憑證已正確發行並指派正確時，在 [ **步驟4：啟動服務**] 旁邊，按一下 [ **執行**]，然後依照畫面上的指示進行。</span><span class="sxs-lookup"><span data-stu-id="c7527-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>

12. <span data-ttu-id="c7527-124">當 **步驟 4** 成功完成後，請重新開機伺服器，並以 DomainAdmins 群組成員的身分登入伺服器。</span><span class="sxs-lookup"><span data-stu-id="c7527-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>

13. <span data-ttu-id="c7527-125">在執行 Lync Server 控制台的電腦上，確認 [Lync Server 控制台] 的 [ **拓撲** ] 頁面上，轉送伺服器的服務狀態會顯示為綠色核取記號。</span><span class="sxs-lookup"><span data-stu-id="c7527-125">On the computer where you are running Lync Server Control Panel, verify on the **Topology** page of Lync Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="c7527-126">若改為顯示紅色 X，請選取轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="c7527-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="c7527-127">在 [ **動作** ] 功能表上，按一下 [ **啟動所有服務**]。</span><span class="sxs-lookup"><span data-stu-id="c7527-127">On the **Action** menu, click **Start All Services**.</span></span>

<span data-ttu-id="c7527-128">如果您已將一部以上的電腦新增至轉送伺服器集區，請在轉送伺服器集區中的所有其他電腦上，執行此程式中的步驟。</span><span class="sxs-lookup"><span data-stu-id="c7527-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="c7527-129">如果您不需要為其他任何電腦安裝轉送伺服器的檔案，請依照在 [Lync server 2013 中設定主幹中](lync-server-2013-configuring-trunks.md) 的程式來設定此轉送伺服器集區 (或所有轉送伺服器（位於網站) 及其對等）之間的主幹連接設定。</span><span class="sxs-lookup"><span data-stu-id="c7527-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c7527-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c7527-130">See Also</span></span>


[<span data-ttu-id="c7527-131">Lync Server 2013 中內部伺服器的憑證需求</span><span class="sxs-lookup"><span data-stu-id="c7527-131">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


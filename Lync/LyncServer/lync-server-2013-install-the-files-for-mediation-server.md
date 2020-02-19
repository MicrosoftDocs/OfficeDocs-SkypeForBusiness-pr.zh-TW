---
title: Lync Server 2013： 中繼伺服器的安裝檔案
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
ms.openlocfilehash: 39d2072b32f386e182ea51f6bf88e8d67028a0d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="1b2d7-102">Lync Server 2013 中的中繼伺服器的安裝檔案</span><span class="sxs-lookup"><span data-stu-id="1b2d7-102">Install the files for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b2d7-103">_**主題上次修改日期：** 2012年-08-06_</span><span class="sxs-lookup"><span data-stu-id="1b2d7-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="1b2d7-104">若要順利完成此程序，您應該登入伺服器，在最低限度下，為本機系統管理員或網域使用者誰成員資格至少具有 RTCUniversalReadOnlyAdmins 群組。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-104">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>

<span data-ttu-id="1b2d7-105">使用本主題中的步驟執行 Lync Server 2013 部署精靈來安裝中繼伺服器時您用來定義並發行之集區的拓撲產生器新增至中繼伺服器集區的電腦上的檔案。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-105">Use the steps in this topic to run Lync Server 2013 Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool when you used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="1b2d7-106">當安裝檔案的中繼伺服器，您也安裝，並指派憑證所需的中繼伺服器集區中每一部電腦。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-106">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span>

<span data-ttu-id="1b2d7-107">在此網站中，如果您已部署中繼伺服器上的前端集區或 Standard Edition server 組合，您可以略過此主題，而繼續[設定 Lync Server 2013 中的主幹](lync-server-2013-configuring-trunks.md)。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-107">At this site, if you have already deployed Mediation Servers collocated on the Front End pools or Standard Edition server, you can skip this topic and, instead, continue to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1b2d7-108">本主題假設您有已定義和發佈獨立中繼伺服器集區中所述<A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">定義 Lync Server 2013 中的拓撲產生器中的中繼伺服器</A>和<A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A>中部署文件，且您已確認中繼伺服器集區中的電腦符合必要條件中所述<A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">的 Lync Server 2013 中的 Enterprise Voice 的軟體先決條件</A>和<A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">安全性和企業版的組態先決條件Lync Server 2013 中的語音</A>。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool as described in <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Define a Mediation Server in Topology Builder in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation, and that you have verified that the computers in the Mediation Server pool meet the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="1b2d7-109">若要安裝獨立中繼伺服器集區的檔案</span><span class="sxs-lookup"><span data-stu-id="1b2d7-109">To install the files for a stand-alone Mediation Server pool</span></span>

1.  <span data-ttu-id="1b2d7-110">從安裝媒體，以滑鼠右鍵按一下\<安裝媒體\>**\\安裝\\amd64\\Setup.exe**，然後按一下 [**以管理員身分執行**。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-110">From the installation media, right-click \<installation media\>**\\Setup\\amd64\\Setup.exe**, and then click **Run as Administrator**.</span></span>

2.  <span data-ttu-id="1b2d7-111">在 [**安裝位置**] 頁面上，按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-111">On the **Installation Location** page, click **OK**.</span></span>

3.  <span data-ttu-id="1b2d7-112">在**使用者授權合約**] 頁面上，按一下 [**我接受**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-112">On the **End User License Agreement** page, click **I accept**, and then click **OK**.</span></span> <span data-ttu-id="1b2d7-113">（必要繼續）。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-113">(Required to continue.)</span></span>

4.  <span data-ttu-id="1b2d7-114">在**Lync Server 2010 部署精靈**] 頁面上，按一下 [**安裝或更新 Lync Server 系統**]。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-114">On the **Lync Server 2010 Deployment Wizard** page, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="1b2d7-115">接下來為**步驟 1： 安裝本機設定存放區**，按一下 [**執行**]，然後依照畫面上的指示。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>

6.  <span data-ttu-id="1b2d7-116">在**設定本機複本的中央管理存放區**] 頁面上，接受預設值 [**直接從中央管理存放區擷取**，然後再按 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>

7.  <span data-ttu-id="1b2d7-117">在**執行命令**] 頁面上，當工作狀態顯示為 [**已完成**，按一下 [**完成]**。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

8.  <span data-ttu-id="1b2d7-118">接下來為**步驟 2： 安裝或移除 Lync Server 元件**，按一下 [**執行**]，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-118">Next to **Step 2: Setup or Remove Lync Server Components**, click **Run**, and then click **Next**.</span></span>

9.  <span data-ttu-id="1b2d7-119">在**執行命令**] 頁面上，當工作狀態顯示為 [**已完成**，按一下 [**完成]**。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

10. <span data-ttu-id="1b2d7-120">接下來為**步驟 3： 要求、 安裝或指派憑證**，按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-120">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span> <span data-ttu-id="1b2d7-121">在畫面上，接受預設設定，請遵循指示。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-121">Follow the instructions on the screen, accepting the default settings.</span></span> <span data-ttu-id="1b2d7-122">中繼伺服器需要一個憑證，並讓您將兩次執行**步驟 3** ： 發出所需的憑證，以及一次更將其指派一次。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-122">The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>

11. <span data-ttu-id="1b2d7-123">時發出並正確，指派憑證] 旁邊**步驟 4： 啟動服務**，按一下 [**執行**]，然後依照畫面上的指示。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>

12. <span data-ttu-id="1b2d7-124">當已順利完成**步驟 4**時，重新啟動伺服器，並以 DomainAdmins 群組成員身分登入伺服器。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>

13. <span data-ttu-id="1b2d7-125">在執行 Lync Server Control Panel 所在的電腦，確認中繼伺服器的服務狀態顯示為一個綠色核取記號的 Lync Server Control Panel 的 [**拓撲**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-125">On the computer where you are running Lync Server Control Panel, verify on the **Topology** page of Lync Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="1b2d7-126">如果出現的紅色的 X 相反地，選取 [中繼伺服器]。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="1b2d7-127">在 [**動作**] 功能表中，按一下 [**啟動所有服務**。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-127">On the **Action** menu, click **Start All Services**.</span></span>

<span data-ttu-id="1b2d7-128">如果您將多部電腦加入中繼伺服器集區時，請在此程序中的中繼伺服器集區中的所有其他電腦上執行步驟。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="1b2d7-129">如果您不需要安裝中繼伺服器的任何其他電腦的檔案，然後遵循程序來設定此中繼伺服器集區 （或在網站上的所有中繼伺服器） 之間的主幹連線的[Lync Server 2013 中的設定主幹](lync-server-2013-configuring-trunks.md)和其對等。</span><span class="sxs-lookup"><span data-stu-id="1b2d7-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1b2d7-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1b2d7-130">See Also</span></span>


[<span data-ttu-id="1b2d7-131">適用於 Lync Server 2013 中的內部伺服器的憑證需求</span><span class="sxs-lookup"><span data-stu-id="1b2d7-131">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


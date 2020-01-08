---
title: Lync Server 2013：安裝 Edge Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 211baa13f80e89fa081b6bf65d4bd7e90d50d000
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a><span data-ttu-id="2dd51-102">安裝 Lync Server 2013 的 Edge Server</span><span class="sxs-lookup"><span data-stu-id="2dd51-102">Install Edge Servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2dd51-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="2dd51-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="2dd51-104">您可以使用 Lync Server 部署嚮導，在 Edge 伺服器上安裝 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="2dd51-104">You install Lync Server 2013 on Edge Servers by using Lync Server Deployment Wizard.</span></span> <span data-ttu-id="2dd51-105">在每個邊緣伺服器上執行部署嚮導，您就可以完成設定 Edge 伺服器所需的大部分工作。</span><span class="sxs-lookup"><span data-stu-id="2dd51-105">By running the Deployment Wizard on each Edge Server, you can complete most of the tasks required to set up the Edge Server.</span></span> <span data-ttu-id="2dd51-106">若要在 Edge 伺服器上部署 Lync Server 2013，您必須已執行拓撲建立器，才能定義及發佈 Edge 伺服器拓撲，並將它匯出到從 Edge 伺服器提供的媒體中。</span><span class="sxs-lookup"><span data-stu-id="2dd51-106">In order to deploy Lync Server 2013 on an Edge Server, you must have already run Topology Builder to define and publish your Edge Server topology, and exported it to media that is available from the Edge Server.</span></span> <span data-ttu-id="2dd51-107">如需詳細資訊，請參閱[Lync server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)，並[匯出 lync server 2013 拓朴，並將其複製到外部媒體以進行 edge 安裝](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)。</span><span class="sxs-lookup"><span data-stu-id="2dd51-107">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<span data-ttu-id="2dd51-108">使用 [部署嚮導] 安裝每個 Edge 伺服器、安裝並指派所需的憑證，然後啟動所需的服務之後，您就可以使用在[Lync server 2013 中設定外部使用者存取支援](lync-server-2013-configuring-support-for-external-user-access.md)中的資訊來完成設定，以啟用及設定外部使用者存取，以及[驗證 lync server 2013 中的 Edge 部署中](lync-server-2013-verifying-your-edge-deployment.md)的資訊，包括伺服器與用戶端連線。</span><span class="sxs-lookup"><span data-stu-id="2dd51-108">After using the Deployment Wizard to install each Edge Server, install and assign the required certificates, and start the required services, you can complete the setup by using the information in [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) to enable and configure external user access and the information in [Verifying your edge deployment in Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) to validate the setup, including server and client connectivity.</span></span>

<div>

## <a name="to-install-an-edge-server"></a><span data-ttu-id="2dd51-109">若要安裝邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="2dd51-109">To install an Edge Server</span></span>

1.  <span data-ttu-id="2dd51-110">登入您想要將 Edge 伺服器安裝為本機管理員群組成員的電腦，或是具有同等使用者權利和許可權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="2dd51-110">Log on to the computer on which you want to install your Edge Server as a member of the local Administrators group or an account with equivalent user rights and permissions.</span></span>

2.  <span data-ttu-id="2dd51-111">請確定您使用拓撲結構建立器所建立的拓撲設定檔案，然後匯出並複製到外部媒體，這是在 Edge 伺服器上提供的（例如，存取您複寫拓撲設定檔的 USB 磁片磁碟機），或驗證存取您複製檔案的網路共用位置。</span><span class="sxs-lookup"><span data-stu-id="2dd51-111">Ensure that the topology configuration file you created using Topology Builder, and then exported and copied to external media, is available on the Edge Server (for example, access to the USB drive onto which you copied the topology configuration file, or verify access to the network share where you copied the file).</span></span>

3.  <span data-ttu-id="2dd51-112">啟動 [部署] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="2dd51-112">Start the Deployment Wizard.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2dd51-113">如果您收到一則訊息，指出您需要安裝 Microsoft Visual c + + 可再發行的資訊，請按一下<STRONG>[是]</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="2dd51-113">If you get a message saying that you need to install Microsoft Visual C++ Redistributable, click <STRONG>Yes</STRONG>.</span></span> <span data-ttu-id="2dd51-114">在下一個對話方塊中，您可以接受預設的<STRONG>安裝位置</STRONG>，或按一下<STRONG>[流覽]</STRONG>以選取替換位置，然後按一下 [<STRONG>安裝</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="2dd51-114">In the next dialog box, you can accept the default <STRONG>Installation Location</STRONG> or click the <STRONG>Browse</STRONG> to select an alternate location, and then click <STRONG>Install</STRONG>.</span></span> <span data-ttu-id="2dd51-115">在下一個對話方塊中，選取 [<STRONG>我接受授權合約中的條款</STRONG>] 核取方塊，然後按一下<STRONG>[確定]</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="2dd51-115">In the next dialog box, select the <STRONG>I accept the terms in the license agreement</STRONG> check box, and then click <STRONG>OK</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="2dd51-116">在 [部署嚮導] 中，按一下 [**安裝或更新 Lync Server 系統**]。</span><span class="sxs-lookup"><span data-stu-id="2dd51-116">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="2dd51-117">嚮導決定部署狀態之後，請執行**步驟1。安裝本機配置存放區**，按一下 [**執行**]，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="2dd51-117">After the wizard determines the deployment state, for **Step 1. Install Local Configuration Store**, click **Run** and then do the following:</span></span>
    
      - <span data-ttu-id="2dd51-118">在 [**設定中央管理儲存的本機複本**] 對話方塊中，按一下 [從檔案匯**入] （適用于 Edge 伺服器）**，移至匯出拓撲設定檔案的位置，選取 .Zip 檔案，按一下 [**開啟**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="2dd51-118">In the **Configure Local Replica of Central Management Store** dialog box, click **Import from a file (Recommended for Edge Servers)**, go to the location of the exported topology configuration file, select the .zip file, click **Open**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="2dd51-119">[部署] 嚮導會從配置檔案中讀取配置資訊，並將 XML 設定檔寫入本機電腦。</span><span class="sxs-lookup"><span data-stu-id="2dd51-119">The Deployment Wizard reads the configuration information from the configuration file and writes the XML configuration file to the local computer.</span></span>
    
      - <span data-ttu-id="2dd51-120">完成**執行命令**程式後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="2dd51-120">After the **Executing Commands** process is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="2dd51-121">在 [部署嚮導] 中，按一下 [**步驟2：設定] 或 [移除 Lync Server 元件**] 來安裝 lync server 2013 edge 元件（儲存在本機電腦上的 XML 設定檔中指定）。</span><span class="sxs-lookup"><span data-stu-id="2dd51-121">In the Deployment Wizard, click **Step 2: SetUp or Remove Lync Server Components** to install the Lync Server 2013 edge components specified in the XML configuration file that is stored on the local computer.</span></span>

7.  <span data-ttu-id="2dd51-122">完成安裝後，請使用[設定 Lync Server 2013 的邊緣憑證](lync-server-2013-set-up-edge-certificates.md)中的資訊來安裝並指派所需的憑證，然後再啟動服務。</span><span class="sxs-lookup"><span data-stu-id="2dd51-122">After completing the installation, use the information in [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) to install and assign the required certificates before you start services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


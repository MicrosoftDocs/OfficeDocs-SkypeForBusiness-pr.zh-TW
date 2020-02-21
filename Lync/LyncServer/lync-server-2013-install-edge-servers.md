---
title: Lync Server 2013： 安裝 Edge 伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af95403b8a1fc383d8d6065f26a55242e735a51b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a><span data-ttu-id="3ec6e-102">安裝 Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="3ec6e-102">Install Edge Servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ec6e-103">_**主題上次修改日期：** 2012年-09-08_</span><span class="sxs-lookup"><span data-stu-id="3ec6e-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="3ec6e-104">您安裝 Lync Server 2013 Edge Server 上使用 Lync Server 部署精靈。</span><span class="sxs-lookup"><span data-stu-id="3ec6e-104">You install Lync Server 2013 on Edge Servers by using Lync Server Deployment Wizard.</span></span> <span data-ttu-id="3ec6e-105">在每部 Edge Server 上執行 [部署精靈]，可以完成設定 Edge Server 所需的大部分工作。</span><span class="sxs-lookup"><span data-stu-id="3ec6e-105">By running the Deployment Wizard on each Edge Server, you can complete most of the tasks required to set up the Edge Server.</span></span> <span data-ttu-id="3ec6e-106">若要部署 Edge Server 上的 Lync Server 2013，您必須已執行拓撲產生器來定義並發行您的 Edge Server 拓撲，並匯出至可從 Edge Server 的媒體。</span><span class="sxs-lookup"><span data-stu-id="3ec6e-106">In order to deploy Lync Server 2013 on an Edge Server, you must have already run Topology Builder to define and publish your Edge Server topology, and exported it to media that is available from the Edge Server.</span></span> <span data-ttu-id="3ec6e-107">如需詳細資訊，請參閱[Lync Server 2013 中的外部使用者存取的案例](lync-server-2013-scenarios-for-external-user-access.md)和[匯出您的 Lync Server 2013 拓撲，並複製到邊緣安裝的外部媒體](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)。</span><span class="sxs-lookup"><span data-stu-id="3ec6e-107">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<span data-ttu-id="3ec6e-108">之後使用部署精靈來安裝在每部 Edge Server、 安裝及指派必要的憑證，以及啟動必要的服務，您可以使用[Lync Server 2013 中的外部使用者存取的設定支援](lync-server-2013-configuring-support-for-external-user-access.md)的資訊，來啟用及設定外部使用者存取及資訊中[驗證 edge 部署 Lync Server 2013 中的](lync-server-2013-verifying-your-edge-deployment.md)驗證安裝程式，包括伺服器和用戶端連線，以完成安裝程式。</span><span class="sxs-lookup"><span data-stu-id="3ec6e-108">After using the Deployment Wizard to install each Edge Server, install and assign the required certificates, and start the required services, you can complete the setup by using the information in [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) to enable and configure external user access and the information in [Verifying your edge deployment in Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) to validate the setup, including server and client connectivity.</span></span>

<div>

## <a name="to-install-an-edge-server"></a><span data-ttu-id="3ec6e-109">安裝 Edge Server</span><span class="sxs-lookup"><span data-stu-id="3ec6e-109">To install an Edge Server</span></span>

1.  <span data-ttu-id="3ec6e-110">以本機 Administrators 群組成員的身分或具有相同使用者權限的帳戶，登入您想要安裝 Edge Server 的電腦。</span><span class="sxs-lookup"><span data-stu-id="3ec6e-110">Log on to the computer on which you want to install your Edge Server as a member of the local Administrators group or an account with equivalent user rights and permissions.</span></span>

2.  <span data-ttu-id="3ec6e-111">請確定您使用拓撲產生器中，建立然後匯出並複製到外部媒體的拓撲組態檔是可在 Edge Server （例如，存取內含複製拓撲組態檔，或確認的 USB 磁碟機上存取複製檔案的網路共用）。</span><span class="sxs-lookup"><span data-stu-id="3ec6e-111">Ensure that the topology configuration file you created using Topology Builder, and then exported and copied to external media, is available on the Edge Server (for example, access to the USB drive onto which you copied the topology configuration file, or verify access to the network share where you copied the file).</span></span>

3.  <span data-ttu-id="3ec6e-112">啟動部署精靈。</span><span class="sxs-lookup"><span data-stu-id="3ec6e-112">Start the Deployment Wizard.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3ec6e-p102">如果出現訊息告知必須安裝 Microsoft Visual C++ 可轉散發套件，請按一下 <STRONG>[是]</STRONG>。在下一個對話方塊中，您可以接受預設的 <STRONG>[安裝位置]</STRONG>，也可以按一下 <STRONG>[瀏覽]</STRONG> 選取其他位置，然後按一下 <STRONG>[安裝]</STRONG>。在下一個對話方塊中，選取 <STRONG>[我接受授權合約中的條款]</STRONG> 核取方塊，然後按一下 <STRONG>[確定]</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="3ec6e-p102">If you get a message saying that you need to install Microsoft Visual C++ Redistributable, click <STRONG>Yes</STRONG>. In the next dialog box, you can accept the default <STRONG>Installation Location</STRONG> or click the <STRONG>Browse</STRONG> to select an alternate location, and then click <STRONG>Install</STRONG>. In the next dialog box, select the <STRONG>I accept the terms in the license agreement</STRONG> check box, and then click <STRONG>OK</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="3ec6e-116">在部署精靈中按一下 **[安裝或更新 Lync Server 系統]**。</span><span class="sxs-lookup"><span data-stu-id="3ec6e-116">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="3ec6e-117">等精靈決定部署狀態後，在 **[步驟 1：安裝本機設定存放區]** 中按一下 **[執行]**，然後執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="3ec6e-117">After the wizard determines the deployment state, for **Step 1. Install Local Configuration Store**, click **Run** and then do the following:</span></span>
    
      - <span data-ttu-id="3ec6e-118">在 **[設定中央管理存放區的本機複本]** 對話方塊中，按一下 **[從檔案匯入 (建議 Edge Server 使用)]**，前往匯出拓撲設定檔的位置、選取 .zip 檔案、按一下 **[開啟]**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3ec6e-118">In the **Configure Local Replica of Central Management Store** dialog box, click **Import from a file (Recommended for Edge Servers)**, go to the location of the exported topology configuration file, select the .zip file, click **Open**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="3ec6e-119">部署精靈會從設定檔讀取設定資訊，並將 XML 設定檔寫入本機電腦。</span><span class="sxs-lookup"><span data-stu-id="3ec6e-119">The Deployment Wizard reads the configuration information from the configuration file and writes the XML configuration file to the local computer.</span></span>
    
      - <span data-ttu-id="3ec6e-120">**[執行命令]** 程序完成後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="3ec6e-120">After the **Executing Commands** process is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="3ec6e-121">在 [部署精靈] 中按一下 [**步驟 2： 安裝或移除 Lync Server 元件**安裝指定的 XML 設定檔儲存在本機電腦上的 Lync Server 2013 edge 元件。</span><span class="sxs-lookup"><span data-stu-id="3ec6e-121">In the Deployment Wizard, click **Step 2: SetUp or Remove Lync Server Components** to install the Lync Server 2013 edge components specified in the XML configuration file that is stored on the local computer.</span></span>

7.  <span data-ttu-id="3ec6e-122">完成安裝之後，使用中[設定 Lync Server 2013 的邊緣憑證](lync-server-2013-set-up-edge-certificates.md)安裝並指派必要的憑證，再開始服務的資訊。</span><span class="sxs-lookup"><span data-stu-id="3ec6e-122">After completing the installation, use the information in [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) to install and assign the required certificates before you start services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


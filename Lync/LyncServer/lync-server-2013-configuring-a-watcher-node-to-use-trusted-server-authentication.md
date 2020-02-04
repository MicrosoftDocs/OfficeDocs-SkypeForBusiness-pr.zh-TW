---
title: 將觀察程式節點設定為使用信任的伺服器驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7279e18c73ecca9340f57d40794a3e9eb2dd160b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a><span data-ttu-id="4d67f-102">在 Lync Server 2013 中設定 [觀察程式] 節點，以使用信任的伺服器驗證</span><span class="sxs-lookup"><span data-stu-id="4d67f-102">Configuring a watcher node in Lync Server 2013 to use Trusted Server authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d67f-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="4d67f-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="4d67f-104">如果您的觀察程式節點電腦位於周邊網路內，使用受信任的伺服器驗證可大大減少管理稅款，以維護單一憑證，而不是多個使用者帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="4d67f-104">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration taxes to maintaining a single certificate rather than numerous user account passwords.</span></span>

<span data-ttu-id="4d67f-105">設定信任伺服器驗證的第一個步驟是建立信任的應用程式池來託管觀察程式節點電腦。</span><span class="sxs-lookup"><span data-stu-id="4d67f-105">The first step in configuring Trusted Server authentication is to create a trusted application pool to host the watcher node computer.</span></span> <span data-ttu-id="4d67f-106">在已建立受信任的應用程式池之後，您必須接著在該觀察程式節點上設定綜合交易，以作為受信任的應用程式執行。</span><span class="sxs-lookup"><span data-stu-id="4d67f-106">After the trusted application pool has been created, you must then configure synthetic transactions on that watcher node to run as a trusted application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="4d67f-107">受信任的應用程式是一種受信任的狀態，可作為 Lync Server 2013 的一部分執行的應用程式，但這不是產品內建的元件。</span><span class="sxs-lookup"><span data-stu-id="4d67f-107">A trusted application is an application that is given trusted status to run as part of Lync Server 2013, but that is not a built-in part of the product.</span></span> <span data-ttu-id="4d67f-108">[受信任的狀態] 表示應用程式在每次執行時不會受到驗證的挑戰。</span><span class="sxs-lookup"><span data-stu-id="4d67f-108">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>



</div>

<span data-ttu-id="4d67f-109">若要建立信任的應用程式池，請開啟 Lync Server 2013 管理命令介面，並執行如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="4d67f-109">To create a trusted application pool, open the Lync Server 2013 Management Shell and run a command similar to this:</span></span>

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> <span data-ttu-id="4d67f-110">如需有關上述命令中所使用之參數的詳細資訊，請在 Lync Server 管理命令介面提示字元輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="4d67f-110">For details about the parameters used in the preceding command, type the following at the Lync Server Management Shell prompt:</span></span><BR><span data-ttu-id="4d67f-111">取得-說明新-CsTrustedApplicationPool-全 |等</span><span class="sxs-lookup"><span data-stu-id="4d67f-111">Get-Help New-CsTrustedApplicationPool -Full | more</span></span>



</div>

<span data-ttu-id="4d67f-112">建立受信任的應用程式池之後，請將觀察程式節點電腦設定為將綜合交易作為受信任的應用程式執行。</span><span class="sxs-lookup"><span data-stu-id="4d67f-112">After creating the trusted application pool, configure the watcher node computer to run synthetic transactions as a trusted application.</span></span> <span data-ttu-id="4d67f-113">這是使用**新的 CsTrustedApplication** Cmdlet 和類似以下的命令來完成：</span><span class="sxs-lookup"><span data-stu-id="4d67f-113">This is done by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

<span data-ttu-id="4d67f-114">當上述命令完成且已建立受信任的應用程式時，請執行 Enable-CsTopology，以確保變更生效：</span><span class="sxs-lookup"><span data-stu-id="4d67f-114">When the preceding command completes and the trusted application has been created, run Enable-CsTopology to make sure that the changes take effect:</span></span>

    Enable-CsTopology

<span data-ttu-id="4d67f-115">執行 Enable-CsTopology 之後，建議您重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="4d67f-115">After running Enable-CsTopology, we recommend that you restart the computer.</span></span>

<span data-ttu-id="4d67f-116">若要確認已建立新的受信任應用程式，請在 Lync Server 管理命令介面提示字元輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="4d67f-116">To verify that the new trusted application has been created, type the following at the Lync Server Management Shell prompt:</span></span>

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="4d67f-117">在 [觀察程式] 節點上設定預設憑證</span><span class="sxs-lookup"><span data-stu-id="4d67f-117">Configuring a Default Certificate on the Watcher Node</span></span>

<span data-ttu-id="4d67f-118">每個觀察程式節點必須有使用 Lync Server 部署嚮導指派的預設憑證。</span><span class="sxs-lookup"><span data-stu-id="4d67f-118">Each watcher node must have a Default certificate assigned by using the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="4d67f-119">**指派預設憑證**</span><span class="sxs-lookup"><span data-stu-id="4d67f-119">**To assign a Default certificate**</span></span>

1.  <span data-ttu-id="4d67f-120">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **lync server**]，然後按一下 [ **lync server 部署嚮導]**。</span><span class="sxs-lookup"><span data-stu-id="4d67f-120">Click **Start**, click **All Programs**, click **Lync Server**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="4d67f-121">在 Lync Server 部署嚮導中，按一下 [**安裝或更新 Lync Server System** ]，然後按一下標題**要求、安裝或指派憑證**底下的 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="4d67f-121">In the Lync Server Deployment Wizard, click **Install or Update Lync Server System** and then click **Run** under the heading **Request, Install, or Assign Certificate**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="4d67f-122">如果停用 [<STRONG>執行</STRONG>] 按鈕，您可能需要先按一下 [<STRONG>安裝本機設定儲存區</STRONG>] 下的 [<STRONG>執行</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="4d67f-122">If the <STRONG>Run</STRONG> button is disabled, you may need to first click <STRONG>Run</STRONG> under <STRONG>Install Local Configuration Store</STRONG>.</span></span>

    
    </div>

3.  <span data-ttu-id="4d67f-123">請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="4d67f-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="4d67f-124">如果您已有可用作預設憑證的憑證，請按一下 [憑證] 嚮導中的 [**預設**]，然後按一下 [**指派**]。</span><span class="sxs-lookup"><span data-stu-id="4d67f-124">If you already have a certificate that can be used as the Default certificate, click **Default** in the Certificate wizard and then click **Assign**.</span></span> <span data-ttu-id="4d67f-125">遵循 [證書指派] 嚮導中的步驟，將該憑證指派給您。</span><span class="sxs-lookup"><span data-stu-id="4d67f-125">Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
      - <span data-ttu-id="4d67f-126">如果您需要要求使用預設憑證的憑證，請按一下 [**要求**]，然後依照 [證書申請] 嚮導中的步驟要求認證。</span><span class="sxs-lookup"><span data-stu-id="4d67f-126">If you need to request a certificate for use the Default certificate, click **Request** and then follow the steps in the Certificate Request wizard to request that certificate.</span></span> <span data-ttu-id="4d67f-127">如果您使用的是 Web 服務器憑證的預設值，您會取得可指派為預設憑證的憑證。</span><span class="sxs-lookup"><span data-stu-id="4d67f-127">If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a><span data-ttu-id="4d67f-128">安裝和設定觀察程式節點</span><span class="sxs-lookup"><span data-stu-id="4d67f-128">Installing and Configuring a Watcher Node</span></span>

<span data-ttu-id="4d67f-129">重新開機觀察程式節點電腦並設定憑證之後，您必須執行檔案 Watchernode。</span><span class="sxs-lookup"><span data-stu-id="4d67f-129">After you have restarted the watcher node computer and configured a certificate, you need to run the file Watchernode.msi.</span></span> <span data-ttu-id="4d67f-130">（您必須在同時安裝 Operations Manager 代理程式檔案和 Lync Server 2013 核心元件的電腦上執行 Watchernode）。</span><span class="sxs-lookup"><span data-stu-id="4d67f-130">(You must run Watchernode.msi on a computer where both the Operations Manager agent files and the Lync Server 2013 core components are installed.)</span></span>

<span data-ttu-id="4d67f-131">**安裝和設定觀察程式節點**</span><span class="sxs-lookup"><span data-stu-id="4d67f-131">**To install and configure a watcher node**</span></span>

1.  <span data-ttu-id="4d67f-132">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **lync server**]，然後按一下 [ **lync Server Management Shell**]，以開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="4d67f-132">Open the Lync Server Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server**, and then clicking **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4d67f-133">在 Lync Server 管理命令介面中，輸入下列命令，然後按 ENTER 鍵（指定您 Watchernode 複本的實際路徑）：</span><span class="sxs-lookup"><span data-stu-id="4d67f-133">In the Lync Server Management Shell, type the following command and then press ENTER (specify the actual path to your copy of Watchernode.msi):</span></span>
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="4d67f-134">您也可以從命令視窗執行 Watchernode。</span><span class="sxs-lookup"><span data-stu-id="4d67f-134">You can also run Watchernode.msi from a command window.</span></span> <span data-ttu-id="4d67f-135">若要開啟命令視窗，請按一下 [<STRONG>開始</STRONG>]，以滑鼠右鍵按一下 [<STRONG>命令提示</STRONG>字元]，然後按一下 [<STRONG>以系統管理員身分執行</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="4d67f-135">To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>.</span></span> <span data-ttu-id="4d67f-136">當命令視窗開啟時，請輸入相同的前述命令。</span><span class="sxs-lookup"><span data-stu-id="4d67f-136">When the command window opens, type the same preceding command.</span></span>

    
    </div>

<span data-ttu-id="4d67f-137">請注意，前面命令驗證 = TrustedServer 中的名稱/值對是區分大小寫的。</span><span class="sxs-lookup"><span data-stu-id="4d67f-137">Note that the name/value pair in the preceding command Authentication=TrustedServer is case-sensitive.</span></span> <span data-ttu-id="4d67f-138">您必須完全按照所示輸入。</span><span class="sxs-lookup"><span data-stu-id="4d67f-138">You must type it exactly as shown.</span></span> <span data-ttu-id="4d67f-139">下列命令無法使用正確的字母大小寫：</span><span class="sxs-lookup"><span data-stu-id="4d67f-139">The following command fails because it does not use the correct letter casing:</span></span>

<span data-ttu-id="4d67f-140">C：\\Tools\\Watchernode （msi）驗證 = trustedserver</span><span class="sxs-lookup"><span data-stu-id="4d67f-140">C:\\Tools\\Watchernode.msi authentication=trustedserver</span></span>

<span data-ttu-id="4d67f-141">您只能在位於周邊網路中的電腦上使用 TrustedServer 模式。</span><span class="sxs-lookup"><span data-stu-id="4d67f-141">You can use TrustedServer mode only with computers that are located within the perimeter network.</span></span> <span data-ttu-id="4d67f-142">當觀察程式節點在 TrustedServer 模式中執行時，系統管理員不需要維護電腦上的測試使用者密碼。</span><span class="sxs-lookup"><span data-stu-id="4d67f-142">When a watcher node is running in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


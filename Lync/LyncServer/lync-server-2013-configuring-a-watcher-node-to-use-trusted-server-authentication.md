---
title: 設定監看員節點以使用信任的伺服器驗證
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
ms.openlocfilehash: a50f095fef5e99a02b464babd30af69a94bbd660
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a><span data-ttu-id="3dbed-102">若要使用信任的伺服器驗證的 Lync Server 2013 中設定監看員節點</span><span class="sxs-lookup"><span data-stu-id="3dbed-102">Configuring a watcher node in Lync Server 2013 to use Trusted Server authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3dbed-103">_**主題上次修改日期：** 2012年-10-22_</span><span class="sxs-lookup"><span data-stu-id="3dbed-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="3dbed-104">如果您的監看員節點電腦位於周邊網路內，使用受信任的伺服器驗證可大幅減少管理負擔，僅需維護單一憑證即可，不必再維護許多使用者帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="3dbed-104">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration taxes to maintaining a single certificate rather than numerous user account passwords.</span></span>

<span data-ttu-id="3dbed-p101">若要設定受信任的伺服器驗證，首先必須建立信任的應用程式集區，以便管理監看員節點電腦。建立信任的應用程式集區後，必須在該監看員節點上設定綜合交易，當作是信任的應用程式來執行。</span><span class="sxs-lookup"><span data-stu-id="3dbed-p101">The first step in configuring Trusted Server authentication is to create a trusted application pool to host the watcher node computer. After the trusted application pool has been created, you must then configure synthetic transactions on that watcher node to run as a trusted application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="3dbed-107">信任的應用程式是應用程式的指定受信任的狀態] 以執行 Lync Server 2013 的一部分，但不是可以是內建的組件的產品。</span><span class="sxs-lookup"><span data-stu-id="3dbed-107">A trusted application is an application that is given trusted status to run as part of Lync Server 2013, but that is not a built-in part of the product.</span></span> <span data-ttu-id="3dbed-108">信任狀態表示每次執行應用程式時，其驗證不會受到質疑。</span><span class="sxs-lookup"><span data-stu-id="3dbed-108">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>



</div>

<span data-ttu-id="3dbed-109">若要建立受信任的應用程式集區，請開啟 Lync Server 2013 管理命令介面並執行如下的命令：</span><span class="sxs-lookup"><span data-stu-id="3dbed-109">To create a trusted application pool, open the Lync Server 2013 Management Shell and run a command similar to this:</span></span>

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> <span data-ttu-id="3dbed-110">如需在上述命令中使用的參數的詳細資訊，在 Lync Server 管理命令介面提示字元處輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="3dbed-110">For details about the parameters used in the preceding command, type the following at the Lync Server Management Shell prompt:</span></span><BR><span data-ttu-id="3dbed-111">Get-Help New-CsTrustedApplicationPool -Full | more</span><span class="sxs-lookup"><span data-stu-id="3dbed-111">Get-Help New-CsTrustedApplicationPool -Full | more</span></span>



</div>

<span data-ttu-id="3dbed-112">建立信任的應用程式集區後，請將監看員節點電腦設為以信任的應用程式執行綜合交易。</span><span class="sxs-lookup"><span data-stu-id="3dbed-112">After creating the trusted application pool, configure the watcher node computer to run synthetic transactions as a trusted application.</span></span> <span data-ttu-id="3dbed-113">若要設定，可使用 **New-CsTrustedApplication** Cmdlet 以及與下列類似的命令進行：</span><span class="sxs-lookup"><span data-stu-id="3dbed-113">This is done by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

<span data-ttu-id="3dbed-114">完成以上命令並建立信任的應用程式後請執行 Enable-CsTopology，確保變更生效：</span><span class="sxs-lookup"><span data-stu-id="3dbed-114">When the preceding command completes and the trusted application has been created, run Enable-CsTopology to make sure that the changes take effect:</span></span>

    Enable-CsTopology

<span data-ttu-id="3dbed-115">執行 Enable-CsTopology 後，建議重新啟動電腦。</span><span class="sxs-lookup"><span data-stu-id="3dbed-115">After running Enable-CsTopology, we recommend that you restart the computer.</span></span>

<span data-ttu-id="3dbed-116">若要確認已建立新的受信任應用程式，在 Lync Server 管理命令介面提示字元處輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="3dbed-116">To verify that the new trusted application has been created, type the following at the Lync Server Management Shell prompt:</span></span>

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="3dbed-117">在監看員節點上設定預設憑證</span><span class="sxs-lookup"><span data-stu-id="3dbed-117">Configuring a Default Certificate on the Watcher Node</span></span>

<span data-ttu-id="3dbed-118">每個監看員節點必須使用 Lync Server 部署精靈指派預設憑證。</span><span class="sxs-lookup"><span data-stu-id="3dbed-118">Each watcher node must have a Default certificate assigned by using the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="3dbed-119">**指派預設憑證**</span><span class="sxs-lookup"><span data-stu-id="3dbed-119">**To assign a Default certificate**</span></span>

1.  <span data-ttu-id="3dbed-120">按一下 [**開始]**、 [**所有程式]**、 [ **Lync Server**]，然後按一下**Lync Server 部署精靈**。</span><span class="sxs-lookup"><span data-stu-id="3dbed-120">Click **Start**, click **All Programs**, click **Lync Server**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="3dbed-121">在 Lync Server 部署精靈中，按一下 [**安裝或更新 Lync Server 系統**，然後按一下 [**要求、 安裝或指派憑證**] 標題下的 [**執行**。</span><span class="sxs-lookup"><span data-stu-id="3dbed-121">In the Lync Server Deployment Wizard, click **Install or Update Lync Server System** and then click **Run** under the heading **Request, Install, or Assign Certificate**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="3dbed-122">如果 <STRONG>[執行]</STRONG> 按鈕停用，需先按一下 <STRONG>[安裝本機組態存放區]</STRONG> 下方的 <STRONG>[執行]</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="3dbed-122">If the <STRONG>Run</STRONG> button is disabled, you may need to first click <STRONG>Run</STRONG> under <STRONG>Install Local Configuration Store</STRONG>.</span></span>

    
    </div>

3.  <span data-ttu-id="3dbed-123">執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="3dbed-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="3dbed-p104">如果您擁有的憑證可作為預設憑證，請按一下驗證精靈中的 **[預設]**，然後再按一下 **[指派]**，並遵照驗證指派精靈中的步驟指派該憑證。</span><span class="sxs-lookup"><span data-stu-id="3dbed-p104">If you already have a certificate that can be used as the Default certificate, click **Default** in the Certificate wizard and then click **Assign**. Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
      - <span data-ttu-id="3dbed-p105">如果想要求提供憑證作為預設憑證，請按一下 **[要求]** 並遵照憑證要求精靈中的步驟要求提供憑證。如果使用網頁伺服器憑證的預設值，則可獲得一個憑證並將其指派為預設憑證。</span><span class="sxs-lookup"><span data-stu-id="3dbed-p105">If you need to request a certificate for use the Default certificate, click **Request** and then follow the steps in the Certificate Request wizard to request that certificate. If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a><span data-ttu-id="3dbed-128">安裝與設定監看員節點</span><span class="sxs-lookup"><span data-stu-id="3dbed-128">Installing and Configuring a Watcher Node</span></span>

<span data-ttu-id="3dbed-129">您必須重新啟動監看員節點電腦，並設定憑證之後，您需要執行 Watchernode.msi 的檔案。</span><span class="sxs-lookup"><span data-stu-id="3dbed-129">After you have restarted the watcher node computer and configured a certificate, you need to run the file Watchernode.msi.</span></span> <span data-ttu-id="3dbed-130">（您必須執行 Watchernode.msi 的電腦上安裝 Operations Manager 代理程式檔案和 Lync Server 2013 核心元件的位置）。</span><span class="sxs-lookup"><span data-stu-id="3dbed-130">(You must run Watchernode.msi on a computer where both the Operations Manager agent files and the Lync Server 2013 core components are installed.)</span></span>

<span data-ttu-id="3dbed-131">**安裝與設定監看員節點**</span><span class="sxs-lookup"><span data-stu-id="3dbed-131">**To install and configure a watcher node**</span></span>

1.  <span data-ttu-id="3dbed-132">按一下 [**開始**，按一下 [**所有程式]**、 [ **Lync Server**，，然後按一下 [ **Lync Server 管理命令介面**來開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="3dbed-132">Open the Lync Server Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server**, and then clicking **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3dbed-133">在 Lync Server 管理命令介面中，輸入下列命令，然後按 ENTER 鍵 （指定 Watchernode.msi 副本的實際路徑）：</span><span class="sxs-lookup"><span data-stu-id="3dbed-133">In the Lync Server Management Shell, type the following command and then press ENTER (specify the actual path to your copy of Watchernode.msi):</span></span>
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="3dbed-p107">您可以從命令視窗執行 Watchernode.msi。若要開啟命令視窗，請按一下 <STRONG>[開始]</STRONG>、在 <STRONG>[命令提示字元]</STRONG> 上按滑鼠右鍵，然後按一下 <STRONG>[以系統管理員身分執行]</STRONG>。待命令視窗開啟後，鍵入以上同一個命令。</span><span class="sxs-lookup"><span data-stu-id="3dbed-p107">You can also run Watchernode.msi from a command window. To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>. When the command window opens, type the same preceding command.</span></span>

    
    </div>

<span data-ttu-id="3dbed-p108">請注意，以上命令 Authentication=TrustedServer 的名稱/值對區分大小寫。必須確實鍵入顯示的內容。下列命令因未使用正確的大小寫字母而導致失敗：</span><span class="sxs-lookup"><span data-stu-id="3dbed-p108">Note that the name/value pair in the preceding command Authentication=TrustedServer is case-sensitive. You must type it exactly as shown. The following command fails because it does not use the correct letter casing:</span></span>

<span data-ttu-id="3dbed-140">C:\\工具\\Watchernode.msi 驗證 = trustedserver</span><span class="sxs-lookup"><span data-stu-id="3dbed-140">C:\\Tools\\Watchernode.msi authentication=trustedserver</span></span>

<span data-ttu-id="3dbed-p109">只有在周邊網路內的電腦上才能使用 TrustedServer 模式。在 TrustedServer 模式下執行監看員節點時，系統管理員便無須維護電腦的測試使用者密碼。</span><span class="sxs-lookup"><span data-stu-id="3dbed-p109">You can use TrustedServer mode only with computers that are located within the perimeter network. When a watcher node is running in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


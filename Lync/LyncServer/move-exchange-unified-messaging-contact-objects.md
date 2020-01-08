---
title: 移動 Exchange 整合訊息連絡人物件
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 946bf7221ab9f4c5a7111839bca25dabaad31d82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a><span data-ttu-id="78b5f-102">移動 Exchange 整合訊息連絡人物件</span><span class="sxs-lookup"><span data-stu-id="78b5f-102">Move Exchange Unified Messaging Contact objects</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78b5f-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="78b5f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="78b5f-104">若要將自動語音應答（AA）及訂閱者存取（SA）連絡人物件遷移至新的 Lync Server 2013 部署，您必須先使用**CsExUmContact**和**CsExUmContact** Cmdlet，將舊版 Office 通訊伺服器 2007 R2 部署中的物件移至新的 lync server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="78b5f-104">To migrate Auto Attendant (AA) and Subscriber Access (SA) contact objects to the new Lync Server 2013 deployment, you first move the objects from the legacy Office Communications Server 2007 R2 deployment to the new the Lync Server 2013 deployment using the **Get-CsExUmContact** and **Move-CsExUmContact** cmdlets.</span></span> <span data-ttu-id="78b5f-105">在 Exchange 伺服器上，您可以執行**ExchUCUtil** Windows PowerShell 腳本來針對新部署的 Lync pool 執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="78b5f-105">On the Exchange Server, you then run the **ExchUCUtil** Windows PowerShell script to do the following for the newly deployed Lync pool:</span></span>

  - <span data-ttu-id="78b5f-106">將它新增到 [統一訊息 IP 閘道]。</span><span class="sxs-lookup"><span data-stu-id="78b5f-106">Add it to the Unified Messaging IP gateways.</span></span>

  - <span data-ttu-id="78b5f-107">將它新增到 [整合訊息查尋] 群組。</span><span class="sxs-lookup"><span data-stu-id="78b5f-107">Add it to the Unified Messaging hunt groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="78b5f-108">若要使用<STRONG>CsExUmContact</STRONG>和<STRONG>CsExUmContact</STRONG> Cmdlet，您必須是 [RTCUniversalUserAdmins] 群組的成員，並對儲存連絡人物件的 OU 擁有組織單位（OU）許可權。</span><span class="sxs-lookup"><span data-stu-id="78b5f-108">In order to use the <STRONG>Get-CsExUmContact</STRONG> and <STRONG>Move-CsExUmContact</STRONG> cmdlets, you must be a member of the RTCUniversalUserAdmins group and have organizational unit (OU) permission to the OU where the contacts objects are stored.</span></span> <span data-ttu-id="78b5f-109">您可以使用<STRONG>Grant OUPermission</STRONG> Cmdlet 來授與 OU 許可權。</span><span class="sxs-lookup"><span data-stu-id="78b5f-109">OU permission can be granted using the <STRONG>Grant-OUPermission</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a><span data-ttu-id="78b5f-110">使用 Lync Server 管理命令介面移動連絡人物件</span><span class="sxs-lookup"><span data-stu-id="78b5f-110">To move contact objects by using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="78b5f-111">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="78b5f-111">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="78b5f-112">針對使用 Exchange UM 註冊的每個池（其中 pool1.contoso.net 是 Office 通訊伺服器 2007 R2 部署，pool2.contoso.net 是來自 Lync Server 2013 部署的 pool），請輸入以下命令：</span><span class="sxs-lookup"><span data-stu-id="78b5f-112">For each pool registered with Exchange UM (where pool1.contoso.net is a pool from the Office Communications Server 2007 R2 deployment and pool2.contoso.net is the pool from the Lync Server 2013 deployment) at the command line, type the following:</span></span>
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    <span data-ttu-id="78b5f-113">若要驗證連絡人物件是否已移動，請執行**CsExumContact** Cmdlet，並確認**RegistrarPool**現在是指向新的池中。</span><span class="sxs-lookup"><span data-stu-id="78b5f-113">To verify that the contact objects are moved, run the **Get-CsExumContact** cmdlet and confirm that **RegistrarPool** is now pointing to the new pool.</span></span>

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a><span data-ttu-id="78b5f-114">若要執行 ExchUCUtil Windows PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="78b5f-114">To run the ExchUCUtil Windows PowerShell script</span></span>

1.  <span data-ttu-id="78b5f-115">以 Exchange 組織管理員許可權的使用者身分登入 Exchange UM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="78b5f-115">Log on to the Exchange UM Server as a user with Exchange Organization Administrator privileges.</span></span>

2.  <span data-ttu-id="78b5f-116">流覽至 ExchUCUtil Windows PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="78b5f-116">Navigate to the ExchUCUtil Windows PowerShell script.</span></span>
    
    <span data-ttu-id="78b5f-117">在 Exchange 2007 中，ExchUCUtil 是位於： **%\\Program Files%\\Microsoft Exchange Server\\腳本\\ExchUCUtil. ps1**</span><span class="sxs-lookup"><span data-stu-id="78b5f-117">In Exchange 2007, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\Scripts\\ExchUCUtil.ps1**</span></span>
    
    <span data-ttu-id="78b5f-118">在 Exchange 2010 中，ExchUCUtil 是位於： **%\\Program Files% Microsoft\\Exchange Server\\V14\\腳本\\ExchUCUtil. ps1**</span><span class="sxs-lookup"><span data-stu-id="78b5f-118">In Exchange 2010, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\V14\\Scripts\\ExchUCUtil.ps1**</span></span>

3.  <span data-ttu-id="78b5f-119">如果 Exchange 是在單一目錄林中部署，請輸入：</span><span class="sxs-lookup"><span data-stu-id="78b5f-119">If Exchange is deployed in a single forest, type:</span></span>
    
        exchucutil.ps1
    
    <span data-ttu-id="78b5f-120">或者，如果 Exchange 是部署在多個目錄林中，請輸入：</span><span class="sxs-lookup"><span data-stu-id="78b5f-120">Or, if Exchange is deployed in multiple forests, type:</span></span>
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    <span data-ttu-id="78b5f-121">其中，目錄林 FQDN 會指定部署 Lync Server 2013 的林。</span><span class="sxs-lookup"><span data-stu-id="78b5f-121">where forest FQDN specifies the forest in which Lync Server 2013 is deployed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="78b5f-122">執行 exchucutil<EM>後</EM>，請務必重新開機<STRONG>Lync Server 前端</STRONG>服務（rtcsrv）。</span><span class="sxs-lookup"><span data-stu-id="78b5f-122">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="78b5f-123">否則，Lync Server 2013 在拓撲中不會偵測到統一訊息。</span><span class="sxs-lookup"><span data-stu-id="78b5f-123">Otherwise, Lync Server 2013 will not detect Unified Messaging in the topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


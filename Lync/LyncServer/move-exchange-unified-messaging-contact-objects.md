---
title: 移動 Exchange 整合通訊連絡人物件
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3b3091a342b46b5c1aad1d456aa9159d951a4ba
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a><span data-ttu-id="c041e-102">移動 Exchange 整合通訊連絡人物件</span><span class="sxs-lookup"><span data-stu-id="c041e-102">Move Exchange Unified Messaging Contact objects</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c041e-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="c041e-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="c041e-104">若要將自動語音應答（AA）和訂閱者存取（SA）連絡人物件遷移至新的 Lync Server 2013 部署，您必須先使用**Get-CsExUmContact**和**Move-CsExUmContact** Cmdlet，將物件從舊版 Office 通訊伺服器 2007 R2 部署移至新的 lync server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="c041e-104">To migrate Auto Attendant (AA) and Subscriber Access (SA) contact objects to the new Lync Server 2013 deployment, you first move the objects from the legacy Office Communications Server 2007 R2 deployment to the new the Lync Server 2013 deployment using the **Get-CsExUmContact** and **Move-CsExUmContact** cmdlets.</span></span> <span data-ttu-id="c041e-105">在 Exchange 伺服器上，您可以執行**ExchUCUtil** Windows PowerShell 腳本，針對新部署的 Lync 集區執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="c041e-105">On the Exchange Server, you then run the **ExchUCUtil** Windows PowerShell script to do the following for the newly deployed Lync pool:</span></span>

  - <span data-ttu-id="c041e-106">將其新增至整合通訊 IP 閘道。</span><span class="sxs-lookup"><span data-stu-id="c041e-106">Add it to the Unified Messaging IP gateways.</span></span>

  - <span data-ttu-id="c041e-107">將其新增至整合通訊群組搜尋。</span><span class="sxs-lookup"><span data-stu-id="c041e-107">Add it to the Unified Messaging hunt groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c041e-108">In order to use the <STRONG>Get-CsExUmContact</STRONG> and <STRONG>Move-CsExUmContact</STRONG> cmdlets, you must be a member of the RTCUniversalUserAdmins group and have organizational unit (OU) permission to the OU where the contacts objects are stored.</span><span class="sxs-lookup"><span data-stu-id="c041e-108">In order to use the <STRONG>Get-CsExUmContact</STRONG> and <STRONG>Move-CsExUmContact</STRONG> cmdlets, you must be a member of the RTCUniversalUserAdmins group and have organizational unit (OU) permission to the OU where the contacts objects are stored.</span></span> <span data-ttu-id="c041e-109">OU permission can be granted using the <STRONG>Grant-OUPermission</STRONG> cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c041e-109">OU permission can be granted using the <STRONG>Grant-OUPermission</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a><span data-ttu-id="c041e-110">使用 Lync Server 管理命令介面移動連絡人物件</span><span class="sxs-lookup"><span data-stu-id="c041e-110">To move contact objects by using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="c041e-111">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="c041e-111">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="c041e-112">針對每個使用 Exchange UM 註冊的集區（其中 pool1.contoso.net 是 Office 通訊伺服器 2007 R2 部署的集區，而 pool2.contoso.net 是 Lync Server 2013 部署的集區），請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="c041e-112">For each pool registered with Exchange UM (where pool1.contoso.net is a pool from the Office Communications Server 2007 R2 deployment and pool2.contoso.net is the pool from the Lync Server 2013 deployment) at the command line, type the following:</span></span>
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    <span data-ttu-id="c041e-113">若要確認連絡人物件是否移動，請執行 **Get-CsExumContact** Cmdlet 並確認 **[RegistrarPool]** 現在已指向新集區。</span><span class="sxs-lookup"><span data-stu-id="c041e-113">To verify that the contact objects are moved, run the **Get-CsExumContact** cmdlet and confirm that **RegistrarPool** is now pointing to the new pool.</span></span>

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a><span data-ttu-id="c041e-114">執行 ExchUCUtil Windows PowerShell 指令碼</span><span class="sxs-lookup"><span data-stu-id="c041e-114">To run the ExchUCUtil Windows PowerShell script</span></span>

1.  <span data-ttu-id="c041e-115">以具備 Exchange 組織系統管理員權限的使用者登入 Exchange UM Server。</span><span class="sxs-lookup"><span data-stu-id="c041e-115">Log on to the Exchange UM Server as a user with Exchange Organization Administrator privileges.</span></span>

2.  <span data-ttu-id="c041e-116">流覽至 ExchUCUtil Windows PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="c041e-116">Navigate to the ExchUCUtil Windows PowerShell script.</span></span>
    
    <span data-ttu-id="c041e-117">在 Exchange 2007 中，ExchUCUtil.ps1 位於： **% Program Files% \\ Microsoft \\ Exchange Server \\ 腳本 \\ExchUCUtil.ps1**</span><span class="sxs-lookup"><span data-stu-id="c041e-117">In Exchange 2007, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\Scripts\\ExchUCUtil.ps1**</span></span>
    
    <span data-ttu-id="c041e-118">在 Exchange 2010 中，ExchUCUtil.ps1 位於： **% Program Files% \\ Microsoft \\ Exchange Server \\ V14 \\ 腳本 \\ExchUCUtil.ps1**</span><span class="sxs-lookup"><span data-stu-id="c041e-118">In Exchange 2010, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\V14\\Scripts\\ExchUCUtil.ps1**</span></span>

3.  <span data-ttu-id="c041e-119">如果 Exchange 部署在單一樹系中，請輸入：</span><span class="sxs-lookup"><span data-stu-id="c041e-119">If Exchange is deployed in a single forest, type:</span></span>
    
        exchucutil.ps1
    
    <span data-ttu-id="c041e-120">或者，如果 Exchange 部署在多個樹系中，請輸入：</span><span class="sxs-lookup"><span data-stu-id="c041e-120">Or, if Exchange is deployed in multiple forests, type:</span></span>
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    <span data-ttu-id="c041e-121">其中，樹系 FQDN 會指定要在其中部署 Lync Server 2013 的樹系。</span><span class="sxs-lookup"><span data-stu-id="c041e-121">where forest FQDN specifies the forest in which Lync Server 2013 is deployed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c041e-122">請務必在執行 exchucutil.ps1 之後<EM></EM>，重新啟動 <STRONG>[Lync Server 前端]</STRONG> 服務 (rtcsrv.exe)。</span><span class="sxs-lookup"><span data-stu-id="c041e-122">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="c041e-123">否則，Lync Server 2013 將不會在拓撲中偵測到整合通訊。</span><span class="sxs-lookup"><span data-stu-id="c041e-123">Otherwise, Lync Server 2013 will not detect Unified Messaging in the topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


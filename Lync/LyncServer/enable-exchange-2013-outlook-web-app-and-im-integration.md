---
title: 啟用 Exchange 2013 Outlook Web App 與 IM 整合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69df3f33f0671d3014e90859fd39cc2b85f9558b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a><span data-ttu-id="7939e-102">啟用 Exchange 2013 Outlook Web App 與 IM 整合</span><span class="sxs-lookup"><span data-stu-id="7939e-102">Enable Exchange 2013 Outlook Web App and IM integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7939e-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="7939e-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="7939e-104">若要啟用 Exchange 2013 Outlook Web Access （OWA）與立即訊息（IM）與 Lync Server 2013 整合，您必須將 Exchange 2013 用戶端存取伺服器（CAS）伺服器新增到 Lync Server 2013 拓撲，成為受信任的應用程式伺服器。</span><span class="sxs-lookup"><span data-stu-id="7939e-104">To enable Exchange 2013 Outlook Web Access (OWA) and instant messaging (IM) integration with Lync Server 2013, you must add the Exchange 2013 Client Access Server (CAS) server to the Lync Server 2013 topology as a trusted application server.</span></span>

<div>

## <a name="to-create-a-trusted-application-pool"></a><span data-ttu-id="7939e-105">建立信任的應用程式池</span><span class="sxs-lookup"><span data-stu-id="7939e-105">To create a trusted application pool</span></span>

1.  <span data-ttu-id="7939e-106">啟動 Lync Server 2013 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="7939e-106">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="7939e-107">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7939e-107">Run the following cmdlet:</span></span>
    
        Get-CsSite
    
    <span data-ttu-id="7939e-108">這會傳回您在其中建立池的 siteName 的 siteID。</span><span class="sxs-lookup"><span data-stu-id="7939e-108">This returns the siteID for the siteName in which you are creating the pool.</span></span> <span data-ttu-id="7939e-109">如需詳細資訊，請參閱 Lync Server 2013 管理命令介面檔中的[CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) 。</span><span class="sxs-lookup"><span data-stu-id="7939e-109">For details, see [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="7939e-110">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7939e-110">Run the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    <span data-ttu-id="7939e-111">如需詳細資訊，請參閱 Lync Server 2013 管理命令介面檔中的[新 CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) 。</span><span class="sxs-lookup"><span data-stu-id="7939e-111">For details, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in the Lync Server 2013 Management Shell documentation.</span></span>
    
    <span data-ttu-id="7939e-112">Exchange 伺服器 FQDN 應該設定為 Exchange OWA 證書受領人名稱（SN.EXE），或 Subject 替代名稱（SAN）。</span><span class="sxs-lookup"><span data-stu-id="7939e-112">The Exchange Server FQDN should be configured as the Exchange OWA certificate Subject Name (SN), or the Subject Alternate Name (SAN).</span></span>
    
    <span data-ttu-id="7939e-113">在 [Exchange OWA] 中，確認該池的 FQDN 也是受信任的。</span><span class="sxs-lookup"><span data-stu-id="7939e-113">In Exchange OWA, verify that the pool’s FQDN is trusted as well.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7939e-114">如果您的 CAS 伺服器<EM>無法</EM>在執行 Exchange 2013 整合通訊（UM）的同一台伺服器上 collocated，請跳過此程式中的其餘步驟，然後執行本主題稍後的「建立 EXCHANGE 2013 CAS 伺服器的信任的應用程式」程式。</span><span class="sxs-lookup"><span data-stu-id="7939e-114">If your CAS server is <EM>not</EM> collocated on the same server that is running Exchange 2013 Unified Messaging (UM), skip the remaining steps in this procedure and perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span> <span data-ttu-id="7939e-115">如果您的 CAS 伺服器是在執行 Exchange 2013 整合通訊（UM）的同一台伺服器上 collocated，請完成此程式中的步驟，並不要執行本主題稍後的「為 Exchange 2013 CAS 伺服器建立信任的應用程式」程式。</span><span class="sxs-lookup"><span data-stu-id="7939e-115">If your CAS server is collocated on the same server that is running Exchange 2013 Unified Messaging (UM), complete the steps in this procedure and do not perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span>

    
    </div>

4.  <span data-ttu-id="7939e-116">執行 [ **Enable-CsTopology**]。</span><span class="sxs-lookup"><span data-stu-id="7939e-116">Run **Enable-CsTopology**.</span></span>

5.  <span data-ttu-id="7939e-117">開啟拓撲建立器並下載現有的拓撲。</span><span class="sxs-lookup"><span data-stu-id="7939e-117">Open Topology Builder and download the existing topology.</span></span>

6.  <span data-ttu-id="7939e-118">在左窗格中，展開樹狀結構，直到您到達**受信任的應用程式伺服器**為止。</span><span class="sxs-lookup"><span data-stu-id="7939e-118">In the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

7.  <span data-ttu-id="7939e-119">展開 [**受信任的應用程式伺服器**] 節點。</span><span class="sxs-lookup"><span data-stu-id="7939e-119">Expand the **Trusted application servers** node.</span></span>

8.  <span data-ttu-id="7939e-120">您現在應該會看到 [Exchange 2013 CAS 伺服器] 列為受信任的應用程式伺服器。</span><span class="sxs-lookup"><span data-stu-id="7939e-120">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a><span data-ttu-id="7939e-121">若要為 Exchange 2013 CAS 伺服器建立信任的應用程式</span><span class="sxs-lookup"><span data-stu-id="7939e-121">To create a trusted application for the Exchange 2013 CAS server</span></span>

1.  <span data-ttu-id="7939e-122">啟動 Lync Server 2013 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="7939e-122">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="7939e-123">如果您的 CAS 伺服器*無法*在執行 Exchange 2013 整合通訊（UM）的同一台伺服器上 collocated，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7939e-123">If your CAS server is *not* collocated on the same server that is running Exchange 2013 Unified Messaging (UM), run the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    <span data-ttu-id="7939e-124">如需詳細資訊，請參閱 Lync Server 2013 管理命令介面檔中的 [[新-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) ] 主題。</span><span class="sxs-lookup"><span data-stu-id="7939e-124">For details, see the topic [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="7939e-125">執行 [ **Enable-CsTopology**]。</span><span class="sxs-lookup"><span data-stu-id="7939e-125">Run **Enable-CsTopology**.</span></span>

4.  <span data-ttu-id="7939e-126">從 [拓撲建立器] 的左窗格中，展開樹狀結構，直到您到達**受信任的應用程式伺服器**為止。</span><span class="sxs-lookup"><span data-stu-id="7939e-126">From Topology Builder, in the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

5.  <span data-ttu-id="7939e-127">展開 [**受信任的應用程式伺服器**] 節點。</span><span class="sxs-lookup"><span data-stu-id="7939e-127">Expand the **Trusted application servers** node.</span></span>

6.  <span data-ttu-id="7939e-128">您現在應該會看到 [Exchange 2013 CAS 伺服器] 列為受信任的應用程式伺服器。</span><span class="sxs-lookup"><span data-stu-id="7939e-128">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


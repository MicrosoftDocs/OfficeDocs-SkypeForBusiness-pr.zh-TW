---
title: 啟用 Exchange 2013 Outlook Web App 與 IM 整合
description: 啟用 Exchange 2013 Outlook Web App 和 IM 整合。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7fd6e8600f255d6ac4dde52487776cdb5fe1a51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551119"
---
# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a><span data-ttu-id="11a4a-103">啟用 Exchange 2013 Outlook Web App 與 IM 整合</span><span class="sxs-lookup"><span data-stu-id="11a4a-103">Enable Exchange 2013 Outlook Web App and IM integration</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11a4a-104">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="11a4a-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="11a4a-105">若要啟用 Exchange 2013 Outlook Web Access (OWA) 和立即訊息 (IM) 與 Lync Server 2013 整合，您必須將 Exchange 2013 Client Access Server (CAS) Server 新增至 Lync Server 2013 拓撲，做為信任的應用程式伺服器。</span><span class="sxs-lookup"><span data-stu-id="11a4a-105">To enable Exchange 2013 Outlook Web Access (OWA) and instant messaging (IM) integration with Lync Server 2013, you must add the Exchange 2013 Client Access Server (CAS) server to the Lync Server 2013 topology as a trusted application server.</span></span>

<div>

## <a name="to-create-a-trusted-application-pool"></a><span data-ttu-id="11a4a-106">建立信任的應用程式集區</span><span class="sxs-lookup"><span data-stu-id="11a4a-106">To create a trusted application pool</span></span>

1.  <span data-ttu-id="11a4a-107">啟動 Lync Server 2013 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="11a4a-107">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="11a4a-108">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="11a4a-108">Run the following cmdlet:</span></span>
    
        Get-CsSite
    
    <span data-ttu-id="11a4a-109">其會傳回建立集區所在之 siteName 的 siteID。</span><span class="sxs-lookup"><span data-stu-id="11a4a-109">This returns the siteID for the siteName in which you are creating the pool.</span></span> <span data-ttu-id="11a4a-110">如需詳細資訊，請參閱 Lync Server 2013 管理命令介面檔中的 [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) 。</span><span class="sxs-lookup"><span data-stu-id="11a4a-110">For details, see [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="11a4a-111">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="11a4a-111">Run the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    <span data-ttu-id="11a4a-112">如需詳細資訊，請參閱 Lync Server 2013 管理命令介面檔中的 [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) 。</span><span class="sxs-lookup"><span data-stu-id="11a4a-112">For details, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in the Lync Server 2013 Management Shell documentation.</span></span>
    
    <span data-ttu-id="11a4a-113">Exchange Server FQDN 應設定為 Exchange OWA 憑證主體名稱 (SN)，或主體別名 (SAN)。</span><span class="sxs-lookup"><span data-stu-id="11a4a-113">The Exchange Server FQDN should be configured as the Exchange OWA certificate Subject Name (SN), or the Subject Alternate Name (SAN).</span></span>
    
    <span data-ttu-id="11a4a-114">在 Exchange OWA 中，確認集區的 FQDN 也是可信任的。</span><span class="sxs-lookup"><span data-stu-id="11a4a-114">In Exchange OWA, verify that the pool’s FQDN is trusted as well.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="11a4a-115">如果您的 CAS 伺服器 <EM>不</EM> 是在執行 Exchange 2013 整合通訊 (UM) 的同一部伺服器上組合，請略過此程式中的其餘步驟，並執行本主題稍後的「為 EXCHANGE 2013 CAS 伺服器建立信任的應用程式」過程。</span><span class="sxs-lookup"><span data-stu-id="11a4a-115">If your CAS server is <EM>not</EM> collocated on the same server that is running Exchange 2013 Unified Messaging (UM), skip the remaining steps in this procedure and perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span> <span data-ttu-id="11a4a-116">如果您的 CAS 伺服器組合位於執行 Exchange 2013 整合通訊 (UM) 的相同伺服器上，請完成此程式中的步驟，並不要執行本主題稍後的「為 Exchange 2013 CAS 伺服器建立信任的應用程式」過程。</span><span class="sxs-lookup"><span data-stu-id="11a4a-116">If your CAS server is collocated on the same server that is running Exchange 2013 Unified Messaging (UM), complete the steps in this procedure and do not perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span>

    
    </div>

4.  <span data-ttu-id="11a4a-117">執行 **[Enable-CsTopology]**。</span><span class="sxs-lookup"><span data-stu-id="11a4a-117">Run **Enable-CsTopology**.</span></span>

5.  <span data-ttu-id="11a4a-118">開啟 Topology Builder，然後下載現有的拓樸。</span><span class="sxs-lookup"><span data-stu-id="11a4a-118">Open Topology Builder and download the existing topology.</span></span>

6.  <span data-ttu-id="11a4a-119">在左邊的窗格中，展開樹狀目錄，直到找到 **[信任的應用程式伺服器]**。</span><span class="sxs-lookup"><span data-stu-id="11a4a-119">In the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

7.  <span data-ttu-id="11a4a-120">展開 **[信任的應用程式伺服器]** 節點。</span><span class="sxs-lookup"><span data-stu-id="11a4a-120">Expand the **Trusted application servers** node.</span></span>

8.  <span data-ttu-id="11a4a-121">您現在應該會看到列出為信任的應用程式伺服器的 Exchange 2013 CAS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="11a4a-121">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a><span data-ttu-id="11a4a-122">若要為 Exchange 2013 CAS 伺服器建立信任的應用程式</span><span class="sxs-lookup"><span data-stu-id="11a4a-122">To create a trusted application for the Exchange 2013 CAS server</span></span>

1.  <span data-ttu-id="11a4a-123">啟動 Lync Server 2013 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="11a4a-123">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="11a4a-124">如果您的 CAS 伺服器 *沒有* 組合在執行 Exchange 2013 整合通訊 (UM) 的同一部伺服器上，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="11a4a-124">If your CAS server is *not* collocated on the same server that is running Exchange 2013 Unified Messaging (UM), run the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    <span data-ttu-id="11a4a-125">如需詳細資訊，請參閱 Lync Server 2013 管理命令介面檔中的主題 [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) 。</span><span class="sxs-lookup"><span data-stu-id="11a4a-125">For details, see the topic [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="11a4a-126">執行 **[Enable-CsTopology]**。</span><span class="sxs-lookup"><span data-stu-id="11a4a-126">Run **Enable-CsTopology**.</span></span>

4.  <span data-ttu-id="11a4a-127">從拓撲產生器，在左邊的窗格中，展開樹狀目錄，直到找到 **[信任的應用程式伺服器]**。</span><span class="sxs-lookup"><span data-stu-id="11a4a-127">From Topology Builder, in the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

5.  <span data-ttu-id="11a4a-128">展開 **[信任的應用程式伺服器]** 節點。</span><span class="sxs-lookup"><span data-stu-id="11a4a-128">Expand the **Trusted application servers** node.</span></span>

6.  <span data-ttu-id="11a4a-129">您現在應該會看到列出為信任的應用程式伺服器的 Exchange 2013 CAS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="11a4a-129">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


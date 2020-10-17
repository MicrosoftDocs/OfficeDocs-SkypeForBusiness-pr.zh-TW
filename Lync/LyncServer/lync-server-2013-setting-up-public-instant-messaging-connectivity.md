---
title: Lync Server 2013：設定公用立即訊息連線能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab2c3cfec8a685251a3a1627392d6d4eb9691748
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521830"
---
# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="3149e-102">在 Lync Server 2013 中設定公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="3149e-102">Setting up public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3149e-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="3149e-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="3149e-p101">如果您的組織想要支援與 AOL 的公用立即訊息 (IM) 連線能力，您將無法使用 Lync Server 部署精靈要求憑證。請改為執行下列程序的步驟。</span><span class="sxs-lookup"><span data-stu-id="3149e-p101">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate. Instead, perform the steps in the following procedure.</span></span>

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a><span data-ttu-id="3149e-106">設定 Public Instant Messaging Connectivity</span><span class="sxs-lookup"><span data-stu-id="3149e-106">Setting Up Public Instant Messaging Connectivity</span></span>

1.  <span data-ttu-id="3149e-p102">在前端伺服器上，開啟拓撲建置器。展開 Edge 集區，然後以滑鼠右鍵按一下 Edge Server 或 Edge Server 集區。選取 [編輯內容]。</span><span class="sxs-lookup"><span data-stu-id="3149e-p102">On a Front End server, open Topology Builder. Expand Edge pools, then right click your Edge server or Edge server pool. Select Edit properties.</span></span>

2.  <span data-ttu-id="3149e-p103">在 [編輯內容] 的 [一般] 下方，選取 [啟用此 Edge 集區的同盟 (連接埠 5061)]。按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="3149e-p103">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061). Click OK.</span></span>

3.  <span data-ttu-id="3149e-p104">按一下 [動作]，然後依序選取 [拓撲] 和 [發行]。出現發行拓撲的提示時，按 [下一步]。完成發行時，按一下 [完成]。</span><span class="sxs-lookup"><span data-stu-id="3149e-p104">Click Action, select Topology, select Publish. When prompted on Publish the topology, click Next. When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="3149e-p105">在 Edge Server 上，開啟 [Lync Server 部署精靈]。按一下 [安裝或更新 Lync Server 系統]，然後按一下 [安裝或移除 Lync Server 元件]。按一下 [再執行一次]。</span><span class="sxs-lookup"><span data-stu-id="3149e-p105">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="3149e-p106">在 [安裝 Lync Server 元件] 中按 [下一步]。摘要畫面將顯示所執行的動作。一旦部署完成，按一下 [檢視記錄檔]，檢視出現的記錄檔。按一下 [完成] 即可完成部署。</span><span class="sxs-lookup"><span data-stu-id="3149e-p106">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="3149e-122">若要為 Edge Server 的外部介面建立憑證要求以支援對 AOL 的公用 IM 連線能力</span><span class="sxs-lookup"><span data-stu-id="3149e-122">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="3149e-123">若有必要的範本可提供給 CA，請在 Edge Server 中使用下列 Windows PowerShell Cmdlet 以要求憑證：</span><span class="sxs-lookup"><span data-stu-id="3149e-123">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="3149e-124">Lync Server 使用的範本預設憑證名稱是網頁伺服器。</span><span class="sxs-lookup"><span data-stu-id="3149e-124">The default certificate name of the template used for Lync Server is Web Server.</span></span> <span data-ttu-id="3149e-125">只有在 \<template name\> 您需要使用不同于預設範本的範本時，才指定。</span><span class="sxs-lookup"><span data-stu-id="3149e-125">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3149e-126">如果您的組織想要支援與 AOL 的公用 IM 連線，您必須使用 Windows PowerShell，而不是使用憑證嚮導要求將憑證指派給 Access Edge service 的外部 edge。</span><span class="sxs-lookup"><span data-stu-id="3149e-126">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="3149e-127">這是因為憑證精靈用來要求憑證的 Certificate Authority (CA) 伺服器範本不支援用戶端 EKU 組態。</span><span class="sxs-lookup"><span data-stu-id="3149e-127">This is because the Certificate Authority (CA) Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="3149e-128">在使用 Windows PowerShell 建立憑證之前，CA 管理員必須建立及部署支援用戶端 EKU 的新範本。</span><span class="sxs-lookup"><span data-stu-id="3149e-128">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


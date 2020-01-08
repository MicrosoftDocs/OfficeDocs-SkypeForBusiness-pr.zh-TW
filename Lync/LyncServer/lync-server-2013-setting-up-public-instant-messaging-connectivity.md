---
title: Lync Server 2013：設定 Public Instant Messaging Connectivity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e77d8914a1f55ac10544591913a7347e271e9de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="cf8b8-102">在 Lync Server 2013 中設定 Public Instant Messaging Connectivity</span><span class="sxs-lookup"><span data-stu-id="cf8b8-102">Setting up public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf8b8-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="cf8b8-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="cf8b8-104">如果您的組織想要支援與 AOL 的公用立即訊息（IM）連線，您就無法使用 Lync Server 部署嚮導來要求認證。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-104">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="cf8b8-105">請改為執行下列程式中的步驟。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-105">Instead, perform the steps in the following procedure.</span></span>

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a><span data-ttu-id="cf8b8-106">設定公用立即訊息連線能力</span><span class="sxs-lookup"><span data-stu-id="cf8b8-106">Setting Up Public Instant Messaging Connectivity</span></span>

1.  <span data-ttu-id="cf8b8-107">在前端伺服器上，開啟 [拓撲建立器]。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-107">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="cf8b8-108">展開 [邊緣池]，然後以滑鼠右鍵按一下 Edge 伺服器或 Edge 伺服器池。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-108">Expand Edge pools, then right click your Edge server or Edge server pool.</span></span> <span data-ttu-id="cf8b8-109">選取 [編輯屬性]。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-109">Select Edit properties.</span></span>

2.  <span data-ttu-id="cf8b8-110">在 [編輯屬性] 底下的 [一般] 底下，選取 [針對此 Edge 池啟用同盟（埠5061）]。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-110">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061).</span></span> <span data-ttu-id="cf8b8-111">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-111">Click OK.</span></span>

3.  <span data-ttu-id="cf8b8-112">按一下 [動作]，選取 [拓撲]，選取 [發佈]。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-112">Click Action, select Topology, select Publish.</span></span> <span data-ttu-id="cf8b8-113">發佈拓撲時出現提示時，請按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-113">When prompted on Publish the topology, click Next.</span></span> <span data-ttu-id="cf8b8-114">發佈完成後，請按一下 [完成]。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-114">When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="cf8b8-115">在邊緣伺服器上，開啟 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-115">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="cf8b8-116">按一下 [安裝或更新 Lync Server 系統]，然後按一下 [設定] 或 [移除 Lync Server 元件]。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-116">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="cf8b8-117">再次按一下 [執行]。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-117">Click Run Again.</span></span>

5.  <span data-ttu-id="cf8b8-118">在安裝程式 Lync Server 元件上，按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-118">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="cf8b8-119">[摘要] 畫面會在執行時顯示動作。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-119">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="cf8b8-120">完成部署之後，按一下 [查看記錄] 以查看可用的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-120">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="cf8b8-121">按一下 [完成] 以完成部署。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-121">Click Finish to complete the deployment.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="cf8b8-122">建立邊緣伺服器外部介面的憑證要求，以支援與 AOL 的公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="cf8b8-122">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="cf8b8-123">當 CA 提供所需的範本時，請從 Edge 伺服器使用下列 Windows PowerShell Cmdlet，以要求憑證</span><span class="sxs-lookup"><span data-stu-id="cf8b8-123">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="cf8b8-124">Lync Server 所用之範本的預設憑證名是 Web 服務器。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-124">The default certificate name of the template used for Lync Server is Web Server.</span></span> <span data-ttu-id="cf8b8-125">如果您需要\<使用不同\>于預設範本的範本，請只指定範本名稱。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-125">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cf8b8-126">如果您的組織想要支援與 AOL 的公用 IM 連線，您必須使用 Windows PowerShell，而不是憑證嚮導，以要求將憑證指派給存取邊緣服務的外部邊緣。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-126">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="cf8b8-127">這是因為證書嚮導用來要求憑證的憑證授權單位（CA） Web 服務器範本不支援用戶端 EKU 配置。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-127">This is because the Certificate Authority (CA) Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="cf8b8-128">在使用 Windows PowerShell 建立憑證前，CA 管理員必須建立並部署支援用戶端 EKU 的新範本。</span><span class="sxs-lookup"><span data-stu-id="cf8b8-128">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 匯出拓撲並將拓撲複製到 edge 安裝的外部媒體
description: 匯出拓撲並將拓撲複製到 edge 安裝的外部媒體。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47fcee032b4c0e667455ae7f35afe8b99c2d12cc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564759"
---
# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a><span data-ttu-id="e2b22-103">匯出 Lync Server 2013 拓撲，並將其複製到 edge 安裝的外部媒體</span><span class="sxs-lookup"><span data-stu-id="e2b22-103">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2b22-104">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="e2b22-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="e2b22-105">發行拓撲之後，Lync Server 部署嚮導必須存取中央管理存放區資料，以便在伺服器上啟動部署程式。</span><span class="sxs-lookup"><span data-stu-id="e2b22-105">After you publish your topology, the Lync Server Deployment Wizard needs access to the Central Management store data in order to start the deployment process on the server.</span></span> <span data-ttu-id="e2b22-106">在內部網路中，可直接從伺服器存取資料，但不在內部網域中的 Edge Server 無法存取資料。</span><span class="sxs-lookup"><span data-stu-id="e2b22-106">In the internal network, the data is available directly from the servers, but Edge Servers that are not in the internal domain cannot access the data.</span></span> <span data-ttu-id="e2b22-107">若要讓拓撲設定資料可用於 Edge Server 部署，您必須將拓撲資料匯出至檔案，並將它複製到外部媒體 (例如，在 Edge server 上執行 Lync Server 部署嚮導之前，可從 Edge Server 取得的 USB 磁片磁碟機或網路共用) 。</span><span class="sxs-lookup"><span data-stu-id="e2b22-107">To make the topology configuration data available for an Edge Server deployment, you must export the topology data to a file and copy it to external media (for example, a USB drive or a network share that is available from the Edge Server) before you run the Lync Server Deployment Wizard on the Edge Server.</span></span> <span data-ttu-id="e2b22-108">使用下列程式可讓您的拓撲設定資料可用於您要部署的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="e2b22-108">Use the following procedure to make your topology configuration data available on the Edge Server that you are deploying.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="e2b22-109">在 Edge Server 上安裝 Lync Server 2013 之後，您可以使用內部網路中的管理工具來管理 Edge Server，這會自動將設定複寫至部署中的任何 Edge server。</span><span class="sxs-lookup"><span data-stu-id="e2b22-109">After you install Lync Server 2013 on an Edge Server, you manage the Edge Server using the administrative tools in the internal network, which automatically replicate configuration to any Edge Servers in your deployment.</span></span> <span data-ttu-id="e2b22-110">唯一例外是指派及安裝憑證，以及停止和啟動服務，這兩者都必須在 Edge Server 上執行。</span><span class="sxs-lookup"><span data-stu-id="e2b22-110">The only exception is assigning and installing certificates and stopping and starting services, both of which must be done on the Edge Server.</span></span>



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a><span data-ttu-id="e2b22-111">使用 Lync Server 管理命令介面使拓撲資料可用於 Edge Server</span><span class="sxs-lookup"><span data-stu-id="e2b22-111">To make your topology data available on an Edge Server by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="e2b22-112">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="e2b22-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e2b22-113">在 Lync Server 管理命令介面中，執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e2b22-113">In the Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  <span data-ttu-id="e2b22-114">將匯出的檔案複製到外部媒體 (例如，在部署) 時，可從 Edge Server 取得的 USB 磁片磁碟機或網路共用。</span><span class="sxs-lookup"><span data-stu-id="e2b22-114">Copy the exported file to external media (for example, a USB drive or a network share that is available from the Edge Server during deployment).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


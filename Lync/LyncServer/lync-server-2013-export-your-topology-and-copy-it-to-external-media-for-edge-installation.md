---
title: 匯出拓撲並將它複製到邊緣安裝的外部媒體
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
ms.openlocfilehash: 52903a2e7ae1b9a3a994a1199e32d8d7c4bd1e03
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a><span data-ttu-id="4b389-102">匯出您的 Lync Server 2013 拓撲，並將它複製到邊緣安裝的外部媒體</span><span class="sxs-lookup"><span data-stu-id="4b389-102">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b389-103">_**主題上次修改日期：** 2012年-09-08_</span><span class="sxs-lookup"><span data-stu-id="4b389-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="4b389-104">發行拓撲之後，[Lync Server 部署精靈會需要存取中央管理存放區資料才能在伺服器上啟動部署程序。</span><span class="sxs-lookup"><span data-stu-id="4b389-104">After you publish your topology, the Lync Server Deployment Wizard needs access to the Central Management store data in order to start the deployment process on the server.</span></span> <span data-ttu-id="4b389-105">在內部網路中，資料無法直接從伺服器，但不在內部網域中的 Edge Server 無法存取的資料。</span><span class="sxs-lookup"><span data-stu-id="4b389-105">In the internal network, the data is available directly from the servers, but Edge Servers that are not in the internal domain cannot access the data.</span></span> <span data-ttu-id="4b389-106">您必須要使用 Edge Server 部署的拓撲組態資料，請將拓撲資料匯出至檔案，並將它複製到外部媒體 （例如 USB 磁碟機或可從 Edge Server 的網路共用） 在執行 Lync Server Dep 之前loyment Edge Server 上的精靈。</span><span class="sxs-lookup"><span data-stu-id="4b389-106">To make the topology configuration data available for an Edge Server deployment, you must export the topology data to a file and copy it to external media (for example, a USB drive or a network share that is available from the Edge Server) before you run the Lync Server Deployment Wizard on the Edge Server.</span></span> <span data-ttu-id="4b389-107">使用下列程序以在您要部署 Edge Server 上提供您的拓撲組態資料。</span><span class="sxs-lookup"><span data-stu-id="4b389-107">Use the following procedure to make your topology configuration data available on the Edge Server that you are deploying.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="4b389-108">Edge Server 上安裝 Lync Server 2013 之後，您會管理 Edge Server 使用的系統管理工具在內部網路中，這會自動將設定複寫到您在部署中任何 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="4b389-108">After you install Lync Server 2013 on an Edge Server, you manage the Edge Server using the administrative tools in the internal network, which automatically replicate configuration to any Edge Servers in your deployment.</span></span> <span data-ttu-id="4b389-109">唯一的例外是指派安裝憑證並停止及啟動服務，這兩種都必須完成 Edge Server 上。</span><span class="sxs-lookup"><span data-stu-id="4b389-109">The only exception is assigning and installing certificates and stopping and starting services, both of which must be done on the Edge Server.</span></span>



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a><span data-ttu-id="4b389-110">若要使用您的拓撲資料 Edge Server 上使用 Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="4b389-110">To make your topology data available on an Edge Server by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="4b389-111">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="4b389-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4b389-112">在 Lync Server 管理命令介面中，執行下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4b389-112">In the Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  <span data-ttu-id="4b389-113">將匯出的檔案複製到外部媒體 （例如 USB 磁碟機或在部署期間可從 Edge Server 的網路共用）。</span><span class="sxs-lookup"><span data-stu-id="4b389-113">Copy the exported file to external media (for example, a USB drive or a network share that is available from the Edge Server during deployment).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


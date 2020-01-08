---
title: Lync Server 2013：設定次要位置資訊服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a secondary Location Information service
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48183334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8219aa234330120e6462a600b9c2c27b4b11c100
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a><span data-ttu-id="67b47-102">在 Lync Server 2013 中設定次要位置資訊服務</span><span class="sxs-lookup"><span data-stu-id="67b47-102">Configure a secondary Location Information service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67b47-103">_**主題上次修改日期：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="67b47-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="67b47-104">Lync Server 2013 提供 web 服務介面，您可以用來將位置資訊服務指向次要位置來源（SLS）資料庫。</span><span class="sxs-lookup"><span data-stu-id="67b47-104">Lync Server 2013 provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="67b47-105">連接到 SLS 資料庫的 web 服務介面必須符合位置資訊服務 WSDL。</span><span class="sxs-lookup"><span data-stu-id="67b47-105">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="67b47-106">如果已設定位置資料庫和次要位置資料庫，位置資訊服務會先查詢位置資料庫，如果沒有找到相符的專案，則會將位置要求從用戶端傳送到 SLS 資料庫。</span><span class="sxs-lookup"><span data-stu-id="67b47-106">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="67b47-107">如果該位置存在於 SLS 中，則位置資訊服務接著會將該位置傳送回用戶端。</span><span class="sxs-lookup"><span data-stu-id="67b47-107">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span>

<span data-ttu-id="67b47-108">如需詳細資訊，請參閱適用于下列 Cmdlet 的 Lync Server 管理命令介面檔：</span><span class="sxs-lookup"><span data-stu-id="67b47-108">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="67b47-109">**Set-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="67b47-109">**Set-CsWebServiceConfiguration**</span></span>

<div>

## <a name="to-configure-secondary-location-database"></a><span data-ttu-id="67b47-110">若要設定次要位置資料庫</span><span class="sxs-lookup"><span data-stu-id="67b47-110">To configure Secondary Location database</span></span>

1.  <span data-ttu-id="67b47-111">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="67b47-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="67b47-112">執行下列 Cmdlet 來設定次要位置資料庫位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="67b47-112">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span>
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>


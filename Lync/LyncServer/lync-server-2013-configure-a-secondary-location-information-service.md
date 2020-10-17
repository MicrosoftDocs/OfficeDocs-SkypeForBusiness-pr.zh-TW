---
title: Lync Server 2013：設定次要位置資訊服務
description: Lync Server 2013：設定次要位置資訊服務。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a secondary Location Information service
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48183334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1721299a0c70535dff8dd05e31712ee6a8d93691
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551709"
---
# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a><span data-ttu-id="b4567-103">在 Lync Server 2013 中設定次要位置資訊服務</span><span class="sxs-lookup"><span data-stu-id="b4567-103">Configure a secondary Location Information service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4567-104">_**主題上次修改日期：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="b4567-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="b4567-105">Lync Server 2013 提供 web 服務介面，您可以用來將位置資訊服務指向次要位置來源 (SLS) 資料庫。</span><span class="sxs-lookup"><span data-stu-id="b4567-105">Lync Server 2013 provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="b4567-106">連接至 SLS 資料庫的 web 服務介面必須符合位置資訊服務 WSDL。</span><span class="sxs-lookup"><span data-stu-id="b4567-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="b4567-107">如果已設定位置資料庫和次要位置資料庫，則位置資訊服務會先查詢位置資料庫，如果找不到相符的位置，就會將位置要求從用戶端傳送至 SLS 資料庫。</span><span class="sxs-lookup"><span data-stu-id="b4567-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="b4567-108">如果該位置存在於 SLS 中，則位置資訊服務會將該位置傳回用戶端。</span><span class="sxs-lookup"><span data-stu-id="b4567-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span>

<span data-ttu-id="b4567-109">如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b4567-109">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="b4567-110">**Set-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="b4567-110">**Set-CsWebServiceConfiguration**</span></span>

<div>

## <a name="to-configure-secondary-location-database"></a><span data-ttu-id="b4567-111">若要設定次要位置資料庫</span><span class="sxs-lookup"><span data-stu-id="b4567-111">To configure Secondary Location database</span></span>

1.  <span data-ttu-id="b4567-112">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="b4567-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b4567-113">執行下列 Cmdlet 以設定次要位置資料庫的位置 URL。</span><span class="sxs-lookup"><span data-stu-id="b4567-113">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span>
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>


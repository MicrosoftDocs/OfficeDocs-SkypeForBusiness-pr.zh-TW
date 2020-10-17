---
title: Lync Server 2013：設定 SNMP 應用程式
description: Lync Server 2013：設定 SNMP 應用程式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an SNMP application
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48185346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7374b61ad85d7ddcb40ef1db535e17f86dea58f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546699"
---
# <a name="configure-an-snmp-application-in-lync-server-2013"></a><span data-ttu-id="2fb6a-103">在 Lync Server 2013 中設定 SNMP 應用程式</span><span class="sxs-lookup"><span data-stu-id="2fb6a-103">Configure an SNMP application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fb6a-104">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="2fb6a-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="2fb6a-105">Lync Server 2013 包含標準的 web 服務介面，可讓您用來將位置資訊服務連線至簡易網路管理通訊協定 (SNMP) 應用程式，該應用程式會與埠及切換資訊相符的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="2fb6a-105">Lync Server 2013 includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span>

<span data-ttu-id="2fb6a-106">如果已安裝 SNMP 應用程式，且 Location 資訊服務無法在位置資料庫中找到相符的位置，則位置資訊服務會自動使用用戶端所提供的 MAC 位址來查詢應用程式。</span><span class="sxs-lookup"><span data-stu-id="2fb6a-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="2fb6a-107">然後，位置資訊服務會使用 SNMP 應用程式傳回的埠及切換資訊，以重新查詢位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="2fb6a-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>

<span data-ttu-id="2fb6a-108">如需詳細資訊，請參閱 [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="2fb6a-108">For details, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2fb6a-109">MAC 位址無法在執行 Windows 8 的電腦上使用。</span><span class="sxs-lookup"><span data-stu-id="2fb6a-109">MAC addresses are not available on computers running Windows 8.</span></span>



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="2fb6a-110">設定 SNMP 應用程式 URL</span><span class="sxs-lookup"><span data-stu-id="2fb6a-110">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="2fb6a-111">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="2fb6a-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2fb6a-112">執行下列 Cmdlet 來設定 SNMP 應用程式的 URL。</span><span class="sxs-lookup"><span data-stu-id="2fb6a-112">Run the following cmdlet to configure the URL for the SNMP application.</span></span>
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013： 設定 SNMP 應用程式
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
ms.openlocfilehash: 31f220ca823d739fa95ad6edb3aec97b13d6242b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-an-snmp-application-in-lync-server-2013"></a><span data-ttu-id="14cda-102">在 Lync Server 2013 中設定 SNMP 應用程式</span><span class="sxs-lookup"><span data-stu-id="14cda-102">Configure an SNMP application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14cda-103">_**主題上次修改日期：** 2012年-10-03_</span><span class="sxs-lookup"><span data-stu-id="14cda-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="14cda-104">Lync Server 2013 包含可用來以比對 MAC 位址與連接埠和交換器資訊的簡易網路管理通訊協定 (SNMP) 應用程式連線的位置資訊服務的標準 web 服務介面。</span><span class="sxs-lookup"><span data-stu-id="14cda-104">Lync Server 2013 includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span>

<span data-ttu-id="14cda-105">如果安裝 SNMP 應用程式和位置資訊服務無法在位置資料庫中尋找相符項目，將位置資訊服務自動查詢應用程式使用用戶端所提供的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="14cda-105">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="14cda-106">位置資訊服務然後使用 SNMP 應用程式所傳回的連接埠和交換器資訊來重新查詢位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="14cda-106">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>

<span data-ttu-id="14cda-107">如需詳細資訊，請參閱[Set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="14cda-107">For details, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="14cda-108">MAC 位址不提供在執行 Windows 8 的電腦上。</span><span class="sxs-lookup"><span data-stu-id="14cda-108">MAC addresses are not available on computers running Windows 8.</span></span>



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="14cda-109">若要設定 SNMP 應用程式 URL</span><span class="sxs-lookup"><span data-stu-id="14cda-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="14cda-110">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="14cda-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="14cda-111">執行下列 cmdlet 以設定 SNMP 應用程式的 URL。</span><span class="sxs-lookup"><span data-stu-id="14cda-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span>
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013： Edge 伺服器 Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Edge Server cmdlets
ms:assetid: 1a5427f4-a0d1-4652-8135-91333158ffc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415635(v=OCS.15)
ms:contentKeyID: 48183534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5c743cb229adb6f1ed8298d51713da181750cea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975072"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的 Edge 伺服器 Cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

Edge 伺服器提供一種將 Microsoft Lync Server 2013 延伸至未登入內部網路的使用者的方式。 例如，如果您的遠端使用者是透過網際網路（而非透過內部網路）登入 Lync Server 2013 的經過驗證的使用者，您將需要設定執行 Lync Server Access Edge 服務的邊緣伺服器。 此外，如果您想要建立與其他組織的聯盟，或如果您想要讓您的使用者與擁有公用立即訊息服務（例如 Yahoo\!、AOL 或 MSN）之帳戶的人員進行通訊，則需要 Edge 伺服器。

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P>從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。 擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟 信使，直到服務關閉日期為止。 AOL 和 Yahoo！的存留期結束日期為2014年6月 已公佈。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權 名單. Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</P>
> <LI>
> <P>Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。 與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。 您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</P></LI></UL>



</div>

<div>

## <a name="edge-server-cmdlets"></a>Edge 伺服器 Cmdlet

以下是直接與管理邊緣伺服器相關的 Cmdlet 清單：

**Edge 伺服器**

  - <span></span>  
    [CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398574(v=OCS.15))

  - <span></span>  
    [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413008(v=OCS.15))

  - <span></span>  
    [新-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))

  - <span></span>  
    [移除-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))

  - <span></span>  
    [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAVEdgeConnectivity](https://technet.microsoft.com/en-us/library/JJ205138(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsEdgeServer](https://technet.microsoft.com/en-us/library/Gg398859(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server PowerShell 博客](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


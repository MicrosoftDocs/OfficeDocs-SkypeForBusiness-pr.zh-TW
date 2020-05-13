---
title: 管理集中式記錄服務設定設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c6e156fbae7147b650c7360394cbd0d277b937b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中管理集中式記錄服務設定設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

集中式記錄服務由集中式記錄服務控制器（CLSController）所建立及使用的設定和參數所控制及設定，以將命令傳送至個別電腦的集中式記錄服務代理程式（CLSAgent）。 代理程式會處理傳送給它的命令，而且（在 Start 命令的情況下）會使用案例的設定、提供者、記錄大小、追蹤持續時間及旗標，根據提供的設定資訊開始收集追蹤記錄檔。

<div>


> [!IMPORTANT]
> 並未針對集中式記錄服務列出的所有 Windows PowerShell Cmdlet，都適用于 Lync Server 2013 內部部署。 雖然似乎可以運作，但下列 Cmdlet 並非設計為在 Lync Server 2013 內部部署中運作： 
> <UL>
> <LI>
> <P><STRONG>CsClsRegion Cmdlet：</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>、 <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>、 <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>及<A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>。</P>
> <LI>
> <P><STRONG>CsClsSearchTerm Cmdlet：</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A>和<A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>。</P>
> <LI>
> <P><STRONG>CsClsSecurityGroup Cmdlet：</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>、 <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>、 <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>及<A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>。</P></LI></UL>在這些 Cmdlet 中定義的設定將不會妨礙或導致任何不良行為，但其設計目的是用於 Microsoft 365，而且不會在內部部署部署中產生預期的結果。 這並不是說，在內部部署中不會使用這些 Cmdlet，但是其使用是本檔中未涵蓋的更高級主題。


</div>

<div>

## <a name="in-this-section"></a>本章節內容

本節中的主題會定義集中式記錄服務的配置選項、參數和設定。 下列主題中包含如何設定集中式記錄服務、如何取回設定設定、建立案例、安全性群組管理以進行集中式記錄服務、搜尋等相關資訊。

  - [在 Lync Server 2013 中管理電腦、網站和全域集中式記錄服務設定](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [在 Lync Server 2013 中設定集中式記錄服務的提供者](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [在 Lync Server 2013 中設定集中式記錄服務的案例](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的集中式記錄服務概述](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[Lync Server 2013 中的集中式記錄 Cmdlet](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 管理集中式記錄服務設定設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cb3b16210b3fac64c0c5bd7886849da7dd0d065
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中管理集中式記錄服務設定設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

集中式記錄服務由集中式記錄服務控制器（CLSController）所建立和使用的設定和參數加以控制和設定，以便將命令傳送到個別電腦的集中式記錄服務代理程式（CLSAgent). Agent 會處理傳送給它的命令，以及（在 [開始] 命令中）使用案例、提供者、記錄大小、追蹤持續時間及旗標的設定，根據所提供的設定資訊來開始收集追蹤記錄。

<div>


> [!IMPORTANT]
> 並非所有針對集中式記錄服務列出的 Windows PowerShell Cmdlet 都要用於 Lync Server 2013 內部部署。 雖然可能看起來很正常，但下列 Cmdlet 不是針對 Lync Server 2013 內部部署部署而設計的： 
> <UL>
> <LI>
> <P><STRONG>CsClsRegion Cmdlet：</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15)">CsClsRegion</A>、 <A href="https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>、 <A href="https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>及<A href="https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>。</P>
> <LI>
> <P><STRONG>CsClsSearchTerm Cmdlet：</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15)">CsClsSearchTerm</A>和<A href="https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15)">Set CsClsSearchTerm</A>。</P>
> <LI>
> <P><STRONG>CsClsSecurityGroup Cmdlet：</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15)">CsClsSecurityGroup</A>、 <A href="https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>、 <A href="https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>及<A href="https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>。</P></LI></UL>在這些 Cmdlet 中定義的設定將不會受到影響或導致任何不利的行為，但它們的設計目的是與 Microsoft Office 365 搭配使用，且不會在內部部署部署中產生預期的結果。 這不表示這些 Cmdlet 在內部部署部署中無法使用，但其使用方式是本檔中未涵蓋的更高級主題。



</div>

<div>

## <a name="in-this-section"></a>本節內容

本節中的主題定義集中式記錄服務的配置選項、參數及設定。 有關如何設定集中式記錄服務、如何取得配置設定、案例的建立、集中式記錄服務、搜尋及其他內容的相關資訊，請參閱下列主題。

  - [在 Lync Server 2013 中管理電腦、網站和全域集中式記錄服務設定](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [在 Lync Server 2013 中組態集中式記錄服務的提供者](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [在 Lync Server 2013 中組態集中式記錄服務的案例](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的集中式記錄服務概覽](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[Lync Server 2013 中的集中式記錄 Cmdlet](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


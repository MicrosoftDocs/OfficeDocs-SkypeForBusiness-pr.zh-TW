---
title: 管理的集中式記錄服務組態設定
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
ms.openlocfilehash: 7811c8c55a7c759076382ecf102868cc6c7abf09
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>管理 Lync Server 2013 中的集中式記錄服務組態設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

The Centralized Logging Service 控制，且設定來設定和參數，是由建立及使用集中式記錄服務控制站 (CLSController) 傳送命令到個別電腦的集中式記錄服務代理程式 （Clsagent 的通訊）。 代理程式所處理的命令，傳送給它，並 （若是啟動命令） 使用的案例，提供者、 記錄檔的大小、 追蹤持續時間和旗標設定來開始收集根據所提供的組態資訊的追蹤記錄檔。

<div>


> [!IMPORTANT]
> 並非所有列出 the Centralized Logging Service 的 Windows PowerShell cmdlet 是針對 Lync Server 2013 內部部署搭配使用。 雖然他們可能會出現運作，下列指令程式會並非設計用來與 Lync Server 2013 內部部署的運作： 
> <UL>
> <LI>
> <P><STRONG>CsClsRegion cmdlet:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-csclsregion</A>、 <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-csclsregion</A>、 <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-csclsregion</A>及<A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-csclsregion</A>。</P>
> <LI>
> <P><STRONG>CsClsSearchTerm cmdlet:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-csclssearchterm</A>與<A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-csclssearchterm</A>。</P>
> <LI>
> <P><STRONG>CsClsSecurityGroup cmdlet:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-csclssecuritygroup</A>、 <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-csclssecuritygroup</A>、 <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-csclssecuritygroup</A>及<A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-csclssecuritygroup</A>。</P></LI></UL>這些 cmdlet 中所定義的設定將不會妨礙或造成任何負面的行為，但專為與 Microsoft Office 365 搭配使用，且不會產生預期的結果，在內部部署中。 這並不是說未使用這些指令程式在內部部署中，但其使用是更進階的主題，未涵蓋此文件中。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

本節中的主題定義組態選項、 參數及 the Centralized Logging Service 的設定。 有關如何設定 the Centralized Logging Service，資訊來擷取組態設定、 建立案例、 管理安全性群組的集中式記錄服務，請搜尋，以及多個包含下列主題。

  - [管理電腦、 網站及 Lync Server 2013 中全域的集中式記錄服務組態](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [在 Lync Server 2013 中設定集中式記錄服務提供的者](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [集中式記錄服務的 Lync Server 2013 中設定案例](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的集中式的記錄服務概觀](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[Lync Server 2013 中的集中式的記錄 cmdlet](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


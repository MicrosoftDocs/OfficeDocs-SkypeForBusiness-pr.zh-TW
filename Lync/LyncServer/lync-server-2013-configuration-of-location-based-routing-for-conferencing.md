---
title: Lync Server 2013： 設定的電話撥入會議的位置型路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a959addbcd98e04d336ba380676399dbff2f586b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的會議位置型路由的組態

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-09-11_

位置型路由會議應用程式依賴 Lync Server 2013 Location-Based 路由的組態。 主要的設定如下所示：

  - 參與者加入會議的位置取決於其網站。 網站和其相關聯的網路子網路必須定義在 Lync Server 以強制執行位置型的路由。

  - 若要強制的會議位置型路由，Lync 參與者必須啟用位置型的路由。

  - 若要強制位置型路由的加入會議的 PSTN 端點，用來連線的 PSTN 端點 SIP 主幹必須針對位置型的路由。

如需有關部署和設定 Lync Server 2013 Location-Based 路由的詳細資訊，請參閱設定[位置型的路由](lync-server-2013-configuring-location-based-routing.md)。

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>啟用位置型路由的會議應用程式

預設會停用位置型路由會議應用程式。 之前啟用此應用程式，您必須決定要指派給應用程式的正確優先順序。 若要判斷此優先順序，請在 Lync Server 管理命令介面中執行下列 cmdlet:

Get-csserverapplication-Identity Service: Registrar:\<集區 FQDN\>

此指令程式，\<集區 FQDN\>是啟用位置型路由會議應用程式集區。

此 cmdlet 會傳回由 Lync Server 和優先順序值給個別使用者主控應用程式的清單。 位置型路由會議應用程式需要被指派大於 「 UdcAgent 」 應用程式且小於 「 DefaultRouting 」、 「 ExumRouting 」 及 「 OutboundRouting 」 應用程式的優先順序值。 我們建議您指派的位置型路由會議應用程式是一個點的優先順序值高於 「 UdcAgent 」 應用程式的優先順序值。

例如，如果 「 UdcAgent 」 應用程式都有優先順序值為"2"，「 DefaultRouting 」 應用程式都有優先順序值為"8"、 「 ExumRouting 」 應用程式都有優先順序值為"9"且 「 OutboundRouting 」 應用程式優先順序值為"10"然後您應該將位置型路由會議應用程式指派優先順序值為"3"。 這樣會將應用程式的優先順序，依下列順序： 其他應用程式 (優先順序： 0 到 1)，「 UdcAgent 」 (優先順序： 2)、 位置型路由會議應用程式 (優先順序： 3)，其他應用程式 (優先順序： 4 到 8)，」DefaultRouting 」 (Priority: 9)，「 ExumRouting 」 (優先順序： 10) 和 「 OutboundRouting 」 (優先順序： 11)。

您尋找正確的優先順序值的位置型路由會議應用程式後，請輸入每個前端集區或 Standard Edition Server 主控的使用者啟用位置型路由的下列 cmdlet:

New-csserverapplication-Identity Service: Registrar:\<集區 FQDN\>/LBRouting-優先順序\<應用程式的優先順序\>-啟用 $true-重要 $true Urihttp://www.microsoft.com/LCS/LBRouting

例如：

New-csserverapplication-Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting-優先順序 3-啟用的 $true-重要 $true Urihttp://www.microsoft.com/LCS/LBRouting

使用此 cmdlet 之後, 重新啟動集區或 Standard Edition 伺服器已啟用位置型路由會議應用程式中的所有前端伺服器。

<div>


> [!IMPORTANT]  
> 會議或諮詢轉接位置型路由 enforcements 不會強制執行直到所有前端伺服器中適用的集區或 Standard Edition 伺服器重新啟動。



</div>

一旦成功啟用位置型路由會議應用程式及所有適用的 Lync 伺服器重新啟動後，可防止 PSTN 通話費略過監視啟用位置型路由的 Lync 使用者所召集的所有會議

</div>

</div>

<span> </span>

</div>

</div>

</div>


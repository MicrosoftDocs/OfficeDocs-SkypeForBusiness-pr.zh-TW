---
title: Lync Server 2013：設定會議 Location-Based 路由
description: Lync Server 2013：設定會議 Location-Based 路由。
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
ms.openlocfilehash: 6a87f9c799e565f64b0dd30ce025a4e7a3174625
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552159"
---
# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中設定會議的 Location-Based 路由

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-09-11_

Location-Based 路由會議應用程式取決於 Lync Server 2013 的設定 Location-Based 路由。 主要設定如下：

  - 加入會議的參與者位置是根據其網路網站來決定。 您必須在 Lync Server 中定義網路網站及其相關聯的網路子網，才能強制執行 Location-Based 路由傳送。

  - 若要強制進行會議 Location-Based，必須啟用 Lync 參與者才能進行 Location-Based 路由傳送。

  - 若要強制執行 Location-Based 路由加入會議，必須針對 Location-Based 路由設定用來連接 PSTN 端點的 SIP 主幹。

如需部署及設定 Lync Server 2013 Location-Based 路由的詳細資訊，請參閱設定 [位置基礎路由](lync-server-2013-configuring-location-based-routing.md)。

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>啟用 Location-Based 路由會議應用程式

預設會停用 Location-Based 路由會議應用程式。 在啟用此應用程式之前，您必須決定指派給應用程式的正確優先順序。 若要決定此優先順序，請在 Lync Server 管理命令介面中執行下列 Cmdlet：

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

在此 Cmdlet 中， \<Pool FQDN\> 是要在其中啟用 Location-Based 路由會議應用程式的集區。

此 Cmdlet 會傳回 Lync Server 所主控之應用程式的清單，以及每個應用程式的優先順序值。 Location-Based 路由會議應用程式需要指派優先順序值大於 "UdcAgent" 應用程式，且小於 "DefaultRouting"、"ExumRouting" 和 "OutboundRouting" 應用程式。 建議您指派「Location-Based 路由會議」應用程式的優先順序值，其比 "UdcAgent" 應用程式的優先順序值高一個點。

例如，如果 "UdcAgent" 應用程式的優先順序值為 "2"，"DefaultRouting" 應用程式的優先順序值為 "8"，"ExumRouting" 應用程式的優先順序值為 "9"，而 "OutboundRouting" 應用程式的優先順序值為 "10"，您應該將「Location-Based 路由會議應用程式」指派為 "3" 的優先順序值。 這樣做會依照下列順序進行應用程式的優先順序：其他應用程式 (優先順序：0到 1) ，"UdcAgent" (優先順序： 2) ，Location-Based 路由會議應用程式 (優先順序： 3) ，其他應用程式 (優先順序：4到 8) ，"DefaultRouting" (優先順序： 9) ，"ExumRouting" (優先順序： 10) ，OutboundRouting " (Priority： 11) 。

找到 Location-Based 路由會議應用程式的正確優先順序值後，請為每個 Front-End 集區或 Standard Edition Server 輸入下列 Cmdlet，以供住宅使用者啟用 Location-Based 路由：

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

例如：

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

使用此 Cmdlet 後，請重新開機集區中的所有前端伺服器或已啟用 Location-Based 路由會議應用程式的 Standard Edition 伺服器。

<div>


> [!IMPORTANT]  
> 在重新開機適用的集區或 Standard Edition Server 中的所有前端伺服器之前，不會強制執行 enforcements 到會議或諮詢傳遞的路由傳送。 Location-Based



</div>

當成功啟用 Location-Based 路由會議應用程式，且已重新開機所有可用的 Lync 伺服器後，系統就會監控所有啟用 Location-Based 路由的 Lync 使用者所組織的會議，以避免 PSTN 免付費旁路

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：設定位置基礎路由以進行會議
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
ms.openlocfilehash: 6f982f6e484412234c75eadaea925b65ee11bcbb
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中為會議設定位置基礎路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-09-11_

以位置為基礎的路由會議應用程式取決於 Lync Server 2013 位置基礎路由的設定。 主要設定如下：

  - 加入會議的參與者位置是根據其網路網站來決定。 您必須在 Lync Server 中定義網路網站及其相關聯的網路子網，才能強制進行位置基礎路由。

  - 若要強制進行會議的位置基礎路由，必須啟用 Lync 參與者以進行位置基礎路由傳送。

  - 若要強制執行 PSTN 端點的位置基礎路由加入會議，必須針對位置基礎路由設定用來連接 PSTN 端點的 SIP 主幹。

如需部署及設定 Lync Server 2013 位置型路由的詳細資訊，請參閱設定[位置基礎路由](lync-server-2013-configuring-location-based-routing.md)。

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>啟用以位置為基礎的路由會議應用程式

以位置為基礎的路由會議應用程式預設為停用。 在啟用此應用程式之前，您必須決定指派給應用程式的正確優先順序。 若要決定此優先順序，請在 Lync Server 管理命令介面中執行下列 Cmdlet：

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

在此 Cmdlet 中， \<Pool FQDN\> 是要在其中啟用位置基礎路由會議應用程式的集區。

此 Cmdlet 會傳回 Lync Server 所主控之應用程式的清單，以及每個應用程式的優先順序值。 以位置為基礎的路由會議應用程式需要指派優先順序值大於 "UdcAgent" 應用程式，並小於 "DefaultRouting"、"ExumRouting" 和 "OutboundRouting" 應用程式。 建議您指派位置為基礎的路由會議應用程式，其優先順序值為比 "UdcAgent" 應用程式的優先順序值高一個點。

例如，如果 "UdcAgent" 應用程式的優先順序值為 "2"，"DefaultRouting" 應用程式的優先順序值為 "8"，"ExumRouting" 應用程式的優先順序值為 "9"，而 "OutboundRouting" 應用程式的優先順序值為 "10"，您應該指派優先順序值為 "3" 的「以位置為基礎的路由會議應用程式」。 這樣做會依照下列順序進行應用程式的優先順序：其他應用程式（優先順序：0到1）、"UdcAgent" （Priority：2）、位置基礎路由會議應用程式（優先順序：3）、其他應用程式（優先順序：4到8）、"DefaultRouting" （優先順序：9）、"ExumRouting" （Priority：10）和 "OutboundRouting" （Priority：11）。

找到位置基礎路由會議應用程式的正確優先順序值後，請為每一個前端集區或 Standard Edition Server 輸入下列 Cmdlet，以供住宅使用者進行位置基礎的路由：

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

例如：

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

使用此 Cmdlet 後，請重新開機集區中的所有前端伺服器或啟用位置型路由會議應用程式的 Standard Edition Server。

<div>


> [!IMPORTANT]  
> 在重新開機適用的集區或 Standard Edition Server 中的所有前端伺服器之前，不會強制執行以位置為基礎的路由 enforcements 至會議或諮詢轉移。



</div>

一旦已成功啟用位置式路由會議應用程式，且已重新開機所有適用的 Lync 伺服器，則會監控透過啟用位置路由之 Lync 使用者所組織的所有會議，以避免 PSTN 免付費旁路

</div>

</div>

<span> </span>

</div>

</div>

</div>


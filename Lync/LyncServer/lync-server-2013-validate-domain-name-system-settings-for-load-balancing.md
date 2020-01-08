---
title: Lync Server 2013：驗證用於負載平衡的網域名稱系統設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d56219dc36859eb37a766a94f827fb0c28a9909
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a>驗證 Lync Server 2013 中的負載平衡的網域名稱系統設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-02_

若要支援 DNS 負載平衡所使用的 FQDN，您必須提供 DNS，以將池 FQDN （例如 pool01.contoso.com）解析為池中所有伺服器的 IP 位址（例如，192.168.1.1、192.168.1.2 等等）。 您應該只包含目前已部署之伺服器的 IP 位址。

此外，如果您使用的是適用于 Edge 池的 DNS 負載平衡，則需要下列 DNS 專案：

  - 對於 Lync Server Access Edge 服務，池中的每個伺服器都必須有一個專案。 每個專案都必須將 Lync Server 存取邊緣服務（例如，sip.contoso.com）的 FQDN 解析成池中某個邊緣伺服器上的 Lync Server Access Edge 服務的 IP 位址。

  - 針對 Lync Server Web 會議 Edge 服務，您必須為池中的每個伺服器都有一個專案。 每個專案都必須將 Lync Server Web 會議 Edge 服務（例如 webconf.contoso.com）的 FQDN 解析成池中某個邊緣伺服器上的 Lync Server Web 會議 Edge 服務的 IP 位址。

  - 針對 Lync Server 音訊/視頻邊緣服務，您必須為池中的每個伺服器都有一個專案。 每個專案都必須將 Lync Server 音訊/視頻邊緣服務（例如，av.contoso.com）的 FQDN 解析成池中某個邊緣伺服器上的 Lync Server 音訊/視頻邊緣服務的 IP 位址。

  - 如果您想要在 Edge 池的內部介面上使用 DNS 負載平衡，您必須加入一個 DNS 記錄，該記錄會將 Edge 池的內部 FQDN 解析成池中每個伺服器的 IP 位址。

若要驗證 DNS 是否傳回 DNS 負載平衡的正確值，您應該使用 nslookup 工具。 若要以 nslookup 傳回 DNS 記錄的所有值，您應該執行命令：

`nslookup <FQDN >`

您可以針對 DNS 負載平衡設定中使用的每個 FQDN 執行這個命令，以驗證 DNS 負載平衡的每個記錄集傳回了所有正確的專案。

</div>

<span> </span>

</div>

</div>

</div>


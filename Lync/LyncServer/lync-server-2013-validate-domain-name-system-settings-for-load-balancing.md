---
title: Lync Server 2013： 驗證網域名稱系統設定負載平衡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc91b9f3c4ce28946830f6d91bd8cb90dd0544ce
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42116706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a>驗證 Lync Server 2013 中的負載平衡的網域名稱系統設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-05-02_

若要支援 DNS 負載平衡所使用的 FQDN，您必須佈建 DNS，以將集區 FQDN (如 pool01.contoso.com) 解析為集區中所有伺服器的 IP 位址 (例如，192.168.1.1、192.168.1.2 等)。您應該只包含目前部署之伺服器的 IP 位址。

此外使用 DNS 負載平衡 Edge 集區的下列 DNS 項目需要：

  - 為 Lync Server Access Edge 服務] 中，您必須為每個伺服器的一個項目集區中。 每個項目必須解決的 FQDN，Lync Server Access Edge 服務 (例如 sip.contoso.com) 上下列其中一個 Edge Server 集區中的 Lync Server Access Edge 服務的 IP 位址。

  - Lync Server Web Conferencing Edge service，您必須為每個伺服器的一個項目集區中。 每個項目必須解決的 FQDN，Lync Server Web Conferencing Edge service (例如，webconf.contoso.com) 上下列其中一個 Edge Server 集區中的 Lync Server Web 會議 Edge 服務的 IP 位址。

  - Lync Server Audio/Video Edge service，您必須為每個伺服器的一個項目集區中。 每個項目必須為下列其中一個 Edge Server 集區中的 Lync Server Audio/Video Edge 服務 IP 位址解析 Lync Server Audio/Video Edge service (例如，av.contoso.com) 的 FQDN。

  - 如果您想要使用 DNS 負載平衡 Edge 集區的內部介面上，您必須新增一個內部 Edge 集區 FQDN 解析為集區中每部伺服器的 IP 位址的 DNS 記錄。

若要確認 DNS 會傳回正確的值為 DNS 負載平衡您應該使用 nslookup 工具。 若要傳回所有具有 nslookup 的 DNS 記錄的值，您應該執行命令：

`nslookup <FQDN >`

您可以執行此命令來確認每一筆記錄設定 DNS 負載平衡傳回所有的正確的項目使用 DNS 負載平衡組態中每個 fqdn。

</div>

<span> </span>

</div>

</div>

</div>


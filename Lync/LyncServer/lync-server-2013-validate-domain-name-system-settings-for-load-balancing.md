---
title: Lync Server 2013：驗證負載平衡的網域名稱系統設定
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
ms.openlocfilehash: bc346dba48de1914f9aa5684d114e2f3466396f9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508610"
---
# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a>在 Lync Server 2013 中驗證負載平衡的網域名稱系統設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-02_

若要支援 DNS 負載平衡所使用的 FQDN，您必須佈建 DNS，以將集區 FQDN (如 pool01.contoso.com) 解析為集區中所有伺服器的 IP 位址 (例如，192.168.1.1、192.168.1.2 等)。您應該只包含目前部署之伺服器的 IP 位址。

此外，如果您要對 Edge 集區使用 DNS 負載平衡，則需要下列 DNS 專案：

  - 對於 Lync Server Access Edge service，集區中的每一部伺服器都必須有一個專案。 每個專案都必須解析 Lync Server Access Edge service (的 FQDN，例如，sip.contoso.com) 到集區中某一部 Edge Server 上的 Lync Server Access Edge service 的 IP 位址。

  - 對於 Lync Server Web 會議 Edge service，集區中的每一部伺服器都必須有一個專案。 每個專案都必須解析 Lync Server Web 會議 Edge service (的 FQDN，例如，webconf.contoso.com) 到集區中某一部 Edge Server 上的 Lync Server Web 會議 Edge service 的 IP 位址。

  - 對於 Lync Server Audio/Video Edge service，集區中的每一部伺服器都必須有一個專案。 每個專案都必須解析 Lync Server Audio/Video Edge service 的 FQDN (例如，av.contoso.com) 至集區中某一部 Edge Server 上的 Lync Server Audio/Video Edge service 的 IP 位址。

  - 如果您想要在 Edge 集區的內部介面上使用 DNS 負載平衡，您必須新增一個 DNS 記錄，以將 Edge 集區的內部 FQDN 解析為集區中每一部伺服器的 IP 位址。

若要確認 DNS 是否傳回 DNS 負載平衡的正確值，您應該使用 nslookup 工具。 若要傳回具有 nslookup 之 DNS 記錄的所有值，您應該執行下列命令：

`nslookup <FQDN >`

您可以針對 DNS 負載平衡設定中所用的每個 FQDN，執行此命令，以確認 DNS 負載平衡的每一筆記錄都傳回所有正確的專案。

</div>

<span> </span>

</div>

</div>

</div>


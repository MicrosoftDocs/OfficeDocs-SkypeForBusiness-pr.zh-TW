---
title: Lync Server 2013：反向 proxy 的設定需求
description: Lync Server 2013：反向 proxy 的設定需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75f3f5b9437ba4518e3feffc193853b446b702d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552139"
---
# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 中反向 proxy 的設定需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-05_

Lync Server 2013 對從外部用戶端進行通訊的需求，對傳送到 Director、Director 集區、前端伺服器或前端集區上的外部 Web 服務很有一定的需求。 反向 proxy 也負責發佈 Office Web Apps Server （如果您為使用者提供會議）。

<div>


> [!NOTE]  
> Lync Server 2013 未指定您必須使用的特定反向 proxy。 Lync Server 2013 僅定義反向 proxy 必須能夠執行的運作需求。 一般來說，您已部署在基礎結構中的反向 proxy 可能能夠符合需求。



</div>

<div>

## <a name="reverse-proxy-requirements"></a>反向 Proxy 需求

Lync Server 2013 預期反向 proxy 執行的功能作業如下：

  - 使用安全通訊端層 (SSL) 和傳輸層安全性 (TLS) ，其使用從公用憑證授權單位取得的憑證來連線至 Director、Director 集區、前端伺服器或前端集區的已發佈外部 Web 服務。 Director 和前端伺服器可以使用硬體負載平衡器在負載平衡集區中。

  - 可以使用憑證來發佈內部網站，也可以在必要時以未加密的方式發佈。

  - 可以使用完整功能變數名稱 (FQDN) ，從外部發佈內部主控的網站。

  - 能夠發佈主控網站的所有內容。 根據預設，您可以使用 **/\*** 大多數網頁伺服器所識別的指令，以表示「在網頁伺服器上發行所有內容」。 您也可以修改此指令，例如， **/Uwca/ \* **，這表示「發行虛擬目錄 Ucwa 下的所有內容」。

  - 必須可設定為需要安全通訊端層 (SSL) 和/或傳輸層安全性 (TLS) 與要求來自已發佈網站之內容的用戶端的連線。

  - 必須接受主體替代名稱 (SAN) 專案的憑證。

  - 必須能夠將憑證系結至攔截器或介面，以供外部 web 服務 FQDN 解析。 監聽器設定優於介面。 在單一介面上可以設定許多監聽器。

  - 必須允許設定主機標頭處理。 通常會以透明的方式傳遞要求用戶端所傳送的原始主機標頭，而不是反向 proxy 進行修改。

  - 橋接從外部定義埠 (的 SSL 和 TLS 流量，例如，TCP 443) 至另一個已定義的埠 (例如，TCP 4443) 。 反向 proxy 可能會解密資料包上的封包，然後在傳送時重新加密此封包。

  - 橋接單一端口 (的未加密 TCP 流量例如，TCP 80) 到另一個 (例如，TCP 8080) 。

  - 允許設定或接受 NTLM 驗證，不具驗證及透過驗證。

</div>

</div>

<span> </span>

</div>

</div>

</div>


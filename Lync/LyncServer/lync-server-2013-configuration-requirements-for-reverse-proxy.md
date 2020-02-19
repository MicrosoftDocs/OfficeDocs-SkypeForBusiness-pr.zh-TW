---
title: Lync Server 2013： 設定反向 proxy 需求
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
ms.openlocfilehash: b19684913f147eed353ff9f69400e9993de40c12
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 中的反向 proxy 的設定需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-03-05_

Lync Server 2013 施加在從外部用戶端的通訊，然後傳遞至 Director 集區、 前端伺服器或前端集區裝載在 Director 上的外部 Web 服務上的一些需求。 如果您為使用者提供了會議，也是負責發佈 Office Web Apps Server，反向 proxy。

<div>


> [!NOTE]  
> Lync Server 2013 不指定特定的反向 proxy，您必須使用。 Lync Server 2013 只定義反向 proxy 必須能夠執行的作業需求。 一般而言，您已部署在您的基礎結構中的反向 proxy 可能無法符合需求。



</div>

<div>

## <a name="reverse-proxy-requirements"></a>反向 Proxy 需求

Lync Server 2013 預期的反向 proxy，以執行的功能作業包括：

  - 使用安全通訊端層 (SSL) 和傳輸層安全性 (TLS) 連線至已發行外部 Web 服務 Director 的 Director 集區、 前端伺服器或前端集區使用公用憑證授權單位取得憑證來實作。 Director 與前端伺服器可以使用硬體負載平衡器是負載平衡集區中。

  - 能夠發佈內部網路網站使用的憑證進行加密，或將它們發行透過未加密的方法，如有需要。

  - 用以發佈內部代管的網站外部使用的完整的網域名稱 (FQDN)。

  - 用以發佈主控網站的所有內容。 根據預設，您可以使用**/** 指示詞，大部分的網頁伺服器辨識表示 「 發佈網頁伺服器上的所有內容 」。 您也可以修改指示詞 — 例如， **/Uwca/\***，這表示 「 發佈虛擬目錄 Ucwa 下的所有內容。 」

  - 必須是可設定為需要與用戶端要求內容從發佈網站的 Secure Sockets Layer (SSL) 和/或傳輸層安全性 (TLS) 連線。

  - 必須接受憑證主體替代名稱 (SAN) 項目。

  - 必須能夠允許的接聽程式或外部 web 服務 FQDN 會解析透過的介面的憑證繫結。 接聽程式的設定會優先於介面。 許多接聽程式可以在單一介面上設定。

  - 必須允許主機標頭處理的設定。 通常，必須無障礙，傳遞要求的用戶端所傳送的原始主機標頭而非要修改的反向 proxy。

  - 從一個的 SSL 和 TLS 流量的外部橋接至另一個定義的連接埠 (例如，TCP 4443) 定義連接埠 (例如，TCP 443)。 反向 proxy 可能解密在收到封包，然後重新加密上傳送的封包。

  - 從一個連接埠 (例如，TCP 80) 未加密的 TCP 流量，（例如，TCP 8080） 之間的橋接。

  - 允許組態，或接受，NTLM 驗證不驗證並通過驗證。

</div>

</div>

<span> </span>

</div>

</div>

</div>


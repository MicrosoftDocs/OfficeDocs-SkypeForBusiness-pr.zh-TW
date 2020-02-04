---
title: Lync Server 2013：反向 proxy 的配置需求
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
ms.openlocfilehash: 37a2a535ddaa90efa2f4140236b52788fa58e41a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 中的反向 proxy 設定需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-05_

Lync Server 2013 對來自外部用戶端的通訊有一些需求，就是傳送到主管、主管池、前端伺服器或頂層端池所託管的外部 Web 服務。 如果您是向使用者提供會議，則反向 proxy 也負責發佈 Office Web Apps 伺服器。

<div>


> [!NOTE]  
> Lync Server 2013 不會指定您必須使用的特定反向 proxy。 Lync Server 2013 只定義反向 proxy 必須能夠執行的操作需求。 通常，您已在您的基礎結構中部署的反向 proxy 可能能夠滿足需求。



</div>

<div>

## <a name="reverse-proxy-requirements"></a>反向 Proxy 需求

Lync Server 2013 預期要執行反向 proxy 的功能作業如下：

  - 使用安全通訊端層（SSL）和傳輸層安全性（TLS），方法是使用從公用憑證授權單位取得的憑證連線至主管、主管池、前端伺服器或頂層端池的已發佈外部 Web 服務。 控制器和前端伺服器可以在負載平衡的池中使用硬體負載平衡器。

  - 如果需要，您可以使用憑證來發佈內部網站，或以未加密的方式發佈它們。

  - 您可以使用完整的功能變數名稱（FQDN），在外部發佈內部託管的網站。

  - 能夠發佈託管網站的所有內容。 根據預設，您可以使用** / **此指令，大多數的 web 伺服器都會辨識此指示，表示「在 web 伺服器上發佈所有內容」。 您也可以修改指令（例如 **/Uwca/\***），這表示「在虛擬目錄 Ucwa 中發佈所有內容」。

  - 必須可設定為需要安全通訊端層（SSL）與/或傳輸層安全性（TLS）連線至從已發佈網站要求內容的用戶端。

  - 必須接受使用 [消費者備用名稱（SAN）] 專案的憑證。

  - 必須能夠將憑證系結到偵聽程式或介面，才能透過外部 web 服務 FQDN 解析。 偵聽程式設定優於介面。 許多監聽器可以在單一介面上設定。

  - 必須允許主機標頭處理的設定。 通常，由要求用戶端傳送的原始主機標頭必須透明地傳遞，而不是由反向 proxy 進行修改。

  - 將 SSL 和 TLS 流量從一個外部定義的埠（例如，TCP 443）橋接到另一個已定義的埠（例如，TCP 4443）。 反向 proxy 可能會在接收時解密資料包，然後在傳送時 reencrypt 該資料包。

  - 從一個埠（例如 tcp 80）到另一個埠（例如，TCP 8080）橋接未加密的 TCP 流量。

  - 允許設定或接受 NTLM 驗證，無驗證與傳遞驗證。

</div>

</div>

<span> </span>

</div>

</div>

</div>


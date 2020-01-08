---
title: Lync Server 2013：驗證外部使用者的連線能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 577ba970e272e2306aae3a587d9ae014ba75ba17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a>在 Lync Server 2013 中驗證外部使用者的連線能力

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

驗證外部使用者的連線性需要確保使用者能連線到伺服器和埠，以存取邊緣服務。

一種重要資源，可確認您的設定，以及能夠連線、傳送及接收外部使用者存取所需之案例的正確訊息，就是遠端連線分析<http://www.testocsconnectivity.com>程式網站（）。 網站由 Microsoft 支援服務管理和維護。 若要到達遠端連線分析程式，請在瀏覽器中開啟網站，然後依照指示來選取案例。

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>測試外部使用者與外部存取的連通性

外部使用者存取的測試應該包括貴組織支援的每一種外部使用者類型，包括下列任何一項或所有專案：

  - 至少一個聯盟網域中的使用者，並測試 IM、目前狀態、A/V 與桌面共用。

  - 貴組織支援的每個公用 IM 服務提供者（以及已完成哪些預配）的使用者。

  - 匿名使用者。

  - 貴組織內已登入 Lync 但無法使用 VPN 的使用者。

這些測試會判斷您的邊緣伺服器是否為：

  - 從您的網路外部使用 telnet 用戶端來偵聽必要的埠。
    
      - 範例： telnet sip.contoso.com 443
    
      - 根據您的部署，在 Edge 伺服器或 Edge 伺服器池中所使用的埠上執行上述測試。

  - 執行正確的外部 DNS 解析。
    
      - 從您的網路外部 ping 您的邊緣或邊緣池的每個外部 FQDN。 即使 ping 失敗，您也會看到 IP 位址，您可以將它們與您指派的 IP 位址進行比較。

</div>

</div>

<span> </span>

</div>

</div>

</div>


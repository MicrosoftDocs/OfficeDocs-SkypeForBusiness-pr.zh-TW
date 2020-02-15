---
title: 'Lync Server 2013: DNS 基礎結構支援'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 190e0160532ca0ac26ce4f818f260848ea68f0a1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034805"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 基礎結構支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-03-08_

Lync Server 2013 需要網域名稱系統 (DNS) 和使用方式如下：

  - 探索內部伺服器或集區以進行伺服器對伺服器的通訊。

  - 讓用戶端可探索用於各種 SIP 交易的前端集區或 Standard Edition Server。

  - 將會議的簡單 URL 與裝載這些會議的伺服器產生關聯。

  - 讓外部伺服器與用戶端可連線至 Edge Server 或 HTTP 反向 Proxy 以進行立即訊息 (IM) 或會議。

  - 讓未登入的整合通訊 (UC) 裝置可探索執行裝置更新 Web 服務的前端集區或 Standard Edition Server 以取得更新以及傳送記錄檔。

  - 讓行動用戶端能自動探索 Web 服務資源，而不需使用者手動在裝置設定中輸入 URL。

  - 進行 DNS 負載平衡。

<div>


> [!NOTE]  
> Lync Server 2013 不支援國際化的網域名稱 (Idn)。



</div>

<div>


> [!IMPORTANT]  
> 您指定的名稱必須與伺服器上設定的電腦名稱一模一樣。 根據預設，未加入網域的電腦，其電腦名稱是簡短名稱，而不是完整網域名稱 (FQDN)。 拓撲產生器會使用 Fqdn，不短檔名。 因此，在未加入網域但要部署為 Edge Server 電腦的電腦名稱中，您必須設定 DNS 尾碼。 當您為 Lync Server、Edge Server 以及集區指派 FQDN 時，只能使用標準字元<STRONG></STRONG> (包括 A–Z、a–z、0–9 與連字號)。 請勿使用 Unicode 字元或底線。 也就是當 FQDN 必須指派給憑證的 SN 時，外部 DNS 與公用 CA 通常不支援在 FQDN 中使用非標準字元。



</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：DNS 基礎結構支援
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
ms.openlocfilehash: 6d192388d03bb96a5d630a230ab4bd35e22c3217
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 基礎結構支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-08_

Lync Server 2013 需要網域名稱系統（DNS），並以下列方式使用：

  - 探索內部伺服器或池以進行伺服器間的通訊。

  - 使用戶端能夠探索用於各種 SIP 事務的前端池或標準版伺服器。

  - 若要將會議的簡單 Url 與主持這些會議的伺服器產生關聯。

  - 若要讓外部伺服器和用戶端連線到 Edge 伺服器或 HTTP 反向 proxy 以進行立即訊息（IM）或會議。

  - 若要啟用未登入的整合通訊（UC）裝置，以探索執行裝置更新 Web 服務的前端池或標準版伺服器，請取得更新並傳送記錄。

  - 若要讓行動用戶端能夠自動探索 Web 服務資源，而不需要使用者在裝置設定中手動輸入 Url。

  - 針對 DNS 負載平衡。

<div>


> [!NOTE]  
> Lync Server 2013 不支援國際化功能變數名稱（IDNs）。



</div>

<div>


> [!IMPORTANT]  
> 您指定的名稱必須與伺服器上設定的電腦名稱相同。 根據預設，未加入網域之電腦的電腦名稱稱就是簡稱，不是完全合格的功能變數名稱（FQDN）。 拓撲產生器會使用 FQDN，而非簡稱。 因此，您必須在要部署為邊緣伺服器且未加入網域的電腦名稱稱上設定 DNS 尾碼。 在指派 Lync Server、Edge 伺服器和池的 Fqdn 時，<STRONG>只使用標準字元</STRONG>（包括 a-z、A 至 z、0–9和連字號）。 請勿使用 Unicode 字元或底線。 外部 DNS 和公用 Ca 通常不支援 FQDN 中的非標準字元（也就是當 FQDN 必須指派給憑證中的 SN）時。



</div>

</div>

<span> </span>

</div>

</div>

</div>


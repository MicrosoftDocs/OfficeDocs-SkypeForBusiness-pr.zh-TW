---
title: Lync Server 2013：加密
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01c989213b050bdb536e95a8a42e8f7b35292eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a>Lync Server 2013 的加密

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-09-14_

Microsoft Lync Server 2013 使用 TLS 和 MTLS 來加密立即訊息。 不論流量是限制在內部網路或交叉對內部網路周邊，所有伺服器對伺服器的流量都必須是 MTLS。 TLS 是選擇性的，但強烈建議在中繼伺服器與媒體閘道之間使用。 如果在此連結上設定 TLS，則需要 MTLS。 因此，閘道必須使用來自中繼伺服器信任的 CA 的憑證進行設定。

<div>


> [!NOTE]  
> 已在2014中發佈有關 SSL 3.0 的安全性通知。 在 Lync Server 2013 中停用 SSL 3.0 是受支援的選項。 若要深入瞭解安全性建議，請參閱<A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>。



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全性" alt="security" />安全性注意事項：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>為了確保使用最強的加密通訊協定，Lync Server 2013 將以下列順序為用戶端提供 TLS 加密通訊協定： <strong>tls 1.2</strong> 、 <strong>tls 1.1</strong>、 <strong>tls 1.0</strong>。 TLS 是 Lync Server 2013 的一個重要層面，因此需要維持支援的環境。</td>
</tr>
</tbody>
</table>


</div>

用戶端對用戶端流量的需求取決於通信量是否與內部公司防火牆交叉。 嚴格的內部流量可以使用 TLS，在這種情況下，立即訊息是經過加密，或 TCP，在這種情況下不會。

下表摘要列出每種通信量類型的通訊協定需求。

### <a name="traffic-protection"></a>交通防護

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>流量類型</th>
<th>受</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>伺服器與伺服器</p></td>
<td><p>MTLS</p></td>
</tr>
<tr class="even">
<td><p>用戶端到伺服器</p></td>
<td><p>EAP-TLS</p></td>
</tr>
<tr class="odd">
<td><p>立即訊息與顯示狀態</p></td>
<td><p>TLS （如果針對 TLS 進行設定）</p></td>
</tr>
<tr class="even">
<td><p>媒體的音訊和影片與桌面共用</p></td>
<td><p>SRTP</p></td>
</tr>
<tr class="odd">
<td><p>桌面共用（信號）</p></td>
<td><p>EAP-TLS</p></td>
</tr>
<tr class="even">
<td><p>網路會議</p></td>
<td><p>EAP-TLS</p></td>
</tr>
<tr class="odd">
<td><p>會議內容下載、通訊錄下載、通訊群組延伸</p></td>
<td><p>IP-HTTPS</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a>媒體加密

媒體流量是使用安全的 RTP （SRTP）來加密，這是一種即時傳輸通訊協定（RTP）設定檔，可為 RTP 流量提供保密性、驗證及重放攻擊保護。 此外，在中繼伺服器與其內部下一個躍點之間的兩個方向上，媒體也會使用 SRTP 來加密。 在中繼伺服器與媒體閘道之間的兩個方向上的媒體都會流動，預設不會加密。 中繼伺服器可以支援對媒體閘道進行加密，但閘道必須支援 MTLS 和儲存憑證。

<div>


> [!NOTE]  
> 新版本的 Windows Live Messenger 支援音訊/視頻（A/V）。 如果您是使用 Windows Live Messenger 來實現 A/V 同盟，您也必須修改 Lync 伺服器加密層級。 根據預設，加密層級是必要的。 您必須使用 Lync Server 管理命令介面將此設定變更為 [支援]。 如需詳細資訊，請參閱部署檔中的<A href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013 中的 [部署外部使用者存取</A>]。



</div>

在 Microsoft Lync 2013 和 Windows Live 用戶端之間，音訊及視頻媒體流量沒有加密。

</div>

<div>

## <a name="fips"></a>FIPS

如果 Windows 伺服器作業系統已設定為使用 FIPS 140-2 演算法進行系統加密，則 Lync Server 2013 和 Microsoft Exchange Server 2013 會使用聯邦資訊處理標準（FIPS）140-2 演算法的支援運作。 若要實現 FIPS 支援，您必須設定執行 Lync Server 2013 的每個伺服器以支援它。 如需有關使用 FIPS 相容的演算法及如何實現 FIPS 支援的詳細資料，請參閱 Microsoft 知識庫文章811833：啟用「系統加密：使用 FIPS 相容的演算法來加密、雜湊及簽署」安全設定（在 Windows XP 中）及更新版本的 Windows 中[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)。 如需有關 FIPS 140-2 支援的詳細資訊，以及 Exchange 2010 中的限制，請參閱 Exchange 2010 SP1， [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)以及支援 fips 相容的演算法。

</div>

</div>

<span> </span>

</div>

</div>

</div>


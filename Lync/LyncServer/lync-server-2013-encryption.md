---
title: Lync Server 2013：加密
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4fca7065c18ab67fce1940adccce6b9071f3373
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533330"
---
# <a name="encryption-for-lync-server-2013"></a>Lync Server 2013 的加密

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-09-14_

Microsoft Lync Server 2013 使用 TLS 和 MTLS 來加密立即訊息。 不論流量是限制在內部網路或越過內部網路周邊，所有伺服器對伺服器的流量都需要 MTLS。 TLS 是選擇性的，但在轉送伺服器和媒體閘道之間強烈建議使用。 如果在此連結上設定 TLS，則需要 MTLS。 因此，閘道必須使用來自轉送伺服器所信任之 CA 的憑證加以設定。

<div>


> [!NOTE]  
> 有關 SSL 3.0 的安全性通報已在2014中發佈。 在 Lync Server 2013 中停用 SSL 3.0 是支援的選項。 若要深入瞭解安全性通報，請參閱 <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A> 。



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全" alt="security" />安全性附注：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>為了確保使用最強的加密通訊協定，Lync Server 2013 會以下列順序為用戶端提供 TLS 加密通訊協定： <strong>tls 1.2</strong> ， <strong>tls 1.1</strong>， <strong>tls 1.0</strong>。 TLS 是 Lync Server 2013 的重要層面，因此必須使用此功能才能維護支援的環境。</td>
</tr>
</tbody>
</table>


</div>

用戶端對用戶端流量的需求是根據流量是否通過內部企業防火牆而定。嚴格內部流量可以使用 TLS (此時即時訊息會經過加密)，或者使用 TCP (此時就不會加密)。

下表摘要說明每一種流量類型的通訊協定需求。

### <a name="traffic-protection"></a>流量保護

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>流量類型</th>
<th>提供保護的通訊協定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>伺服器對伺服器</p></td>
<td><p>MTLS</p></td>
</tr>
<tr class="even">
<td><p>用戶端對伺服器</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>立即訊息和目前狀態</p></td>
<td><p>TLS (若設定為 TLS)</p></td>
</tr>
<tr class="even">
<td><p>音訊和視訊及媒體的桌面共用</p></td>
<td><p>SRTP</p></td>
</tr>
<tr class="odd">
<td><p>桌面共用 (訊號)</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="even">
<td><p>Web 會議</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>會議內容下載、通訊錄下載、通訊群組擴充</p></td>
<td><p>HTTPS:</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a>媒體加密

媒體流量都是使用安全 RTP (SRTP) 加密，它是即時傳輸通訊協定 (RTP) 的設定檔，為 RTP 流量提供機密性、驗證功能和重播攻擊防護。 此外，中繼伺服器與其下一個內部躍點之間的雙向媒體流量也是使用 SRTP 來加密。 轉送伺服器和媒體閘道之間的兩種方向的媒體會預設不加密。 中繼伺服器可支援媒體閘道加密，但是閘道必須支援 MTLS 和憑證存放。

<div>


> [!NOTE]  
> Windows Live Messenger 的新版本支援 Audio/Video (A/V) 。 如果您要實作 Windows Live Messenger 的 A/V 同盟，則必須修改 Lync Server 加密層級。 根據預設，加密層級為 [必要]。 您必須使用 Lync Server 管理命令介面將此設定變更為 [支援]。 如需詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013 中部署外部使用者存取</A> 。



</div>

在 Microsoft Lync 2013 和 Windows Live 用戶端之間未加密音訊和影片媒體流量。

</div>

<div>

## <a name="fips"></a>Fips

Lync Server 2013 和 Microsoft Exchange Server 2013 的運作方式是使用聯邦資訊處理標準 (FIPS) 140-2 演算法如果 Windows Server 作業系統設定為使用 FIPS 140-2 演算法進行系統加密。 若要實施 FIPS 支援，您必須設定每台執行 Lync Server 2013 的伺服器以支援它。 如需使用 FIPS 相容的演算法及如何實施 FIPS 支援的詳細資訊，請參閱 Microsoft 知識庫文章811833：在 Windows XP 和更新版本的 Windows 中，啟用「系統加密：使用 FIPS 相容的演算法進行加密、雜湊和簽署」安全性設定的影響 [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833) 。 如需 Exchange 2010 中的 FIPS 140-2 支援和限制的詳細資訊，請參閱 Exchange 2010 SP1 及支援 FIPS 相容的演算法 [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>


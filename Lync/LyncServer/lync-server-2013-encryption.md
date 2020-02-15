---
title: Lync Server 2013： 加密
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
ms.openlocfilehash: 5cc25c66ce807e796cf7e510d89a5a623f98eb49
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a>Lync Server 2013 的加密

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017年-09-14_

Microsoft Lync Server 2013 使用 TLS 和 MTLS 加密立即訊息。 伺服器對伺服器的所有流量都需要 MTLS，不論是否流量局限於內部網路或跨越內部網路周邊網路。 TLS 是選擇性的但強烈建議在中繼伺服器和媒體閘道之間。 如果在此連結上設定 TLS，則 MTLS 是必要的。 因此，必須設定閘道，以從中繼伺服器所信任的 CA 憑證。

<div>


> [!NOTE]  
> 安全性公告有關 SSL 3.0 發佈在 2014年。 停用 Lync Server 2013 中的 SSL 3.0 是支援的選項。 若要深入了解安全性摘要報告，請參閱<A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>。



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全性" alt="security" />安全性附註：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>若要確保會使用最強的密碼編譯通訊協定，Lync Server 2013 將用戶端提供 TLS 加密通訊協定，依下列順序： <strong>TLS 1.2</strong> 、 <strong>TLS 1.1</strong>、 <strong>TLS 1.0</strong>。 TLS 是不可或缺的 Lync Server 2013，因此它必須要有維持支援的環境。</td>
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
<td><p>HTTPS</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a>媒體加密

媒體流量都是使用安全 RTP (SRTP) 加密，它是即時傳輸通訊協定 (RTP) 的設定檔，為 RTP 流量提供機密性、驗證功能和重播攻擊防護。 此外，在中繼伺服器及其內部下一個躍點之間往返流動的媒體也是使用 SRTP 加密。 依預設不會加密雙向中繼伺服器和媒體閘道之間流動的媒體。 中繼伺服器可支援媒體閘道加密，但是閘道必須支援 MTLS 和憑證存放。

<div>


> [!NOTE]  
> 音訊/視訊 (A / V) 支援與 Windows Live Messenger 的新版本。 如果您要實作 Windows Live Messenger 的 A/V 同盟，則必須修改 Lync Server 加密層級。 根據預設，加密層級為 [必要]。 您必須使用 Lync Server 管理命令介面，將此設定變更為支援。 如需詳細資訊，請參閱部署文件中的<A href="lync-server-2013-deploying-external-user-access.md">Deploying Lync Server 2013 中的外部使用者存取</A>。



</div>

音訊和視訊媒體流量並未加密 Microsoft Lync 2013 與 Windows Live 用戶端之間。

</div>

<div>

## <a name="fips"></a>FIPS

Lync Server 2013 和 Microsoft Exchange Server 2013 操作與支援的聯邦資訊處理標準 (FIPS) 140-2 演算法如果 Windows Server 作業系統設定為使用 FIPS 140-2 演算法系統密碼編譯。 若要實作 FIPS 支援，您必須設定執行 Lync Server 2013 到支援它的每部伺服器。 如需使用 FIPS 相容演算法以及如何實作 FIPS 支援的詳細資訊，請參閱 Microsoft 知識庫文章 811833，啟用效果 」 系統密碼編譯： 使用 FIPS 相容演算法進行加密，雜湊，以及簽章 」 安全性設定和更新版本的 Windows，Windows XP 中[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)。 如需 FIPS 140-2 支援和限制在 Exchange 2010 中，請參閱 Exchange 2010 SP1 和支援的 FIPS 相容演算法在[https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)。

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013 支援公用立即信使連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ad9f5083d336fdf90e415d627fe448d02e4db29
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519420"
---
# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a>Lync Server 2013 中的公用立即信使連線支援

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a>支援公用立即信使連線

本文提供 (PIC) 之公用 IM 連線支援的相關資訊。 PIC 是 Microsoft Lync 的一項功能，可讓組織讓其 Lync 使用者能夠透過其 Lync 用戶端和身分識別，透過某些公用立即訊息 (IM) 服務的使用者進行連線。

使用者可在其條款中與客戶、合作夥伴及廠商聯繫，以享受相關條款。 其好處是支援單一即時通訊用戶端，同時維持 Lync 的控制、法規遵從性及封存功能。 Lync-Skype 連線，可于 [2013 年5月公開](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx)取得，依賴舊版的 Lync/Office 通訊伺服器 (OCS) /Live 通訊伺服器 (LCS) ，可在連線至 MSN/Windows LIVE、AOL 和 Yahoo 時，先建立與 PIC 的連接。如需 Lync-Skype 連線的詳細資訊，請參閱 [Lync-Skype 連通性](https://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx)。 與 Windows Live、AOL 和 Yahoo 的同盟都是在生命週期結束的路徑上。此頁面會記錄每個服務的狀態。

若要使用 PIC，客戶必須啟用每個公用 IM 服務提供者的服務。 如何做到這一點的需求和詳細資料，取決於 IM 服務提供者和客戶的基礎授權計畫。

<div>

## <a name="windows-live-messenger"></a>Windows Live Messenger

Microsoft 會讓 Windows Live Messenger 和 Skype 一起運作。 在4月2013，Messenger 使用者已遷移到登入的 Skype。 依靠同盟與 Messenger 的 Lync 客戶將繼續與其 Messenger 連絡人進行通訊，即使這些連絡人更新至 Skype，也是如此。 Lync 系統管理員或 Lync 使用者不需要執行任何動作來維護服務的連續性，而且 Lync 中此功能的管理仍保持與使用信使進行通訊的方式相同。 

當 Messenger 使用者使用其 Microsoft 帳戶登入 Skype 時 (亦即，Messenger 所用的相同認證) 所有的信使連絡人-包括同盟 Lync 連絡人-遵循 Skype。 您可以使用 Skype 和 Lync 之間的顯示狀態共用和立即訊息。 

Lync-Skype 連線-連絡人的新增、目前狀態共用、立即訊息，以及 Lync 與 Skype 使用者之間的語音通話-現在，所有的 Lync 客戶皆可使用此功能。

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a>雅虎\! 和 AOL 立即信使

使用 Yahoo 的同盟\! 和 AOL 都是在 Lync (和 Office 通訊伺服器) 客戶的使用週期中的路徑。 Microsoft 提供每項服務的能力都是由 Yahoo 的支援所決定\! 和 AOL，以及這些條款的底層合約會向下纏繞。 這兩個 Yahoo\! 和 AOL，服務會在2014年6月繼續。

  - **Yahoo** -服務會在2014年6月繼續進行，並且客戶會繼續使用 Microsoft LYNC Public IM 連線使用者訂閱授權 ( "PIC USL" ) 獲得授權。從2012年9月1日起，USL 已無法再購買新的或更新的協定。在此日期之前購買授權的客戶，將可以繼續與 Yahoo 進行同盟\! 直到之前的服務關閉日期或其授權到期為止。閱讀 Lync 小組博客上 [的宣告](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) 。若客戶在已超過6月30日的合約上使用 PIC 授權，將會以支付于2014年6月 30 2014 日的時段的付款金額為比例，取得學分。

  - **AOL** -在2014年6月30日，LYNC 的 IM 連線 ( "PIC" ) 服務將無法再使用。為了在服務結束時限制客戶的中斷，我們已停止提供額外的客戶網域。 在2014年6月30日之前，客戶不需要執行任何動作，就能繼續支援與 AIM 的同盟通訊。 除了這一日期 (或客戶若要在此同時布建其他網域) ，可直接從 AOL 取得替代服務。 如需 AOL 新服務的詳細資訊，請參閱[建立與 AIM 的直接同盟](http://aimenterprise.aol.com/pic.php)    (開啟 AOL.com) 上的新頁面。  

</div>

<div>

## <a name="public-im-provider-summary"></a>公用 IM 提供者摘要

下表提供公用 IM 服務提供者、具有 Lync 的同盟功能及授權需求的摘要。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>公用 IM 服務提供者</th>
<th>同盟功能</th>
<th>授權需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype</p></td>
<td><p>IM、顯示狀態、音訊</p></td>
<td><p>Lync Server 用戶端存取授權，Lync Online 方案1/2/3</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>IM、目前狀態、Audio/Video</p></td>
<td><p> (支援 Lync Server 用戶端存取授權，只要 WLM 位於市場) </p></td>
</tr>
<tr class="odd">
<td><p>Aol</p></td>
<td><p>IM、目前狀態</p></td>
<td><p>Lync Server 用戶端存取授權;支援現有客戶2014年6月。</p></td>
</tr>
<tr class="even">
<td><p>雅虎！</p></td>
<td><p>IM、目前狀態</p></td>
<td><p>除了 Lync Server 用戶端存取授權之外，還需要額外的 Microsoft Lync Public IM 連線使用者訂閱授權 ( "PIC USL" ) 。 從2012年9月的標價，PIC USL 已無法再供購買。 具有有效授權的客戶可以繼續與 Yahoo！進行同盟 在2014年6月30日，直到服務關閉日期為止。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


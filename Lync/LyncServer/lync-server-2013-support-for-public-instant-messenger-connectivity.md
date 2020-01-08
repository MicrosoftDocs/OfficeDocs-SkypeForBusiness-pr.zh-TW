---
title: Lync Server 2013 支援公用立即信使連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c89cc911411095034385f7b8ebbe01edddcd20c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a>支援 Lync Server 2013 中的公用立即信使連線

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a>支援公用立即信使連線

本文提供有關公用 IM 連線（PIC）支援的資訊。 PIC 是 Microsoft Lync 的一項功能，可讓組織透過其 Lync 用戶端和身分識別，讓其 Lync 使用者能夠與特定公用立即訊息（IM）服務的使用者連線。

當使用者與客戶、合作夥伴及廠商的相關產品時，使用者就能獲益。 它的優點在於支援單一即時通訊用戶端，同時維持 Lync 的控制、合規性和歸檔功能。 Lync-Skype 連線（[在2013年5月公開提供](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx)）依賴舊版的 Lync/Office 通訊伺服器（OCS）/Live 通訊伺服器（LCS），首先在連線至 MSN/Windows LIVE、AOL 和 Yahoo 時建立與 PIC 的連接。如需 Lync Skype 連線的詳細資訊，請參閱[lync-skype 連線能力](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx)。 與 Windows Live、AOL 和 Yahoo 的同盟，都是以路徑結束的方式進行。此頁面會記錄每個服務的狀態。

若要使用 PIC，必須有客戶為每個公用 IM 服務提供者啟用服務。 此做法的需求及詳細資料取決於 IM 服務提供者和客戶的基礎授權計畫。

<div>

## <a name="windows-live-messenger"></a>Windows Live Messenger

Microsoft 會將 Windows 即時信使和 Skype 集中在一起。 在2013年4月，Messenger 使用者已在登入時遷移至 Skype。 依賴同盟與 Messenger 的 Lync 客戶將會繼續與其 Messenger 連絡人通訊，即使在這些連絡人更新到 Skype 之後也一樣。 Lync 系統管理員或 Lync 使用者不需要執行此動作，就能維持服務的連續性，而且在 Lync 中管理這項功能的方式與 Messenger 的通訊是一樣的。 

當 Messenger 使用者使用其 Microsoft 帳戶登入 Skype 時（亦即用於 Messenger 的相同認證）所有的 Messenger 連絡人（包括同盟 Lync 連絡人），請依照 Skype 進行。 您可以使用 Skype 和 Lync 之間的目前狀態共用與立即訊息。 

Lync-Skype 連線-連絡人在 Lync 與 Skype 使用者之間的新增、目前狀態共用、立即訊息及語音通話，現在也可供所有 Lync 客戶使用。

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a>Yahoo\! 以及 AOL 立即 Messenger

使用 Yahoo 的同盟\! 而且 AOL 都是在 Lync （以及 Office 通訊伺服器）用戶端的路線中使用。 Microsoft 提供每一項服務的能力都是從 Yahoo 支援。\! 而且 AOL 以及這些專案的基礎協定會向下纏繞。 兩個 Yahoo\! 而且 AOL、服務將在2014年6月後繼續進行。

  - **Yahoo** -服務將在2014年6月後繼續，而且客戶繼續需要使用 Microsoft LYNC 公用 IM 連線使用者訂閱授權（"PIC USL"）。從2012年9月1日起，PIC USL 已不再提供購買新的或續約協定的功能。擁有此日期之前購買之授權的客戶，將能夠繼續與 Yahoo 進行聯盟\! 直到較舊的服務關閉日期或其授權到期日為止。閱讀 Lync 團隊博客上[的公告](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx)。如果客戶在2014年6月30日延長的合約上擁有 PIC 授權，將會以比例支付與2014年6月30日之後的付款金額的點數。

  - **AOL** -在2014年6月30日，LYNC 的 IM 連線（"PIC"）服務將不再提供使用。為了在服務結束時限制客戶的中斷，我們已停止提供額外的客戶網域。 除非2014年6月30日，否則客戶就不需要執行任何動作，就能繼續支援與 AIM 進行聯盟通訊。 在此日期之後（或針對想要同時提供其他網域的客戶），可以直接從 AOL 取得替代服務。 如需 AOL 新服務的詳細資訊，請參閱[建立直接同盟與 AIM](http://aimenterprise.aol.com/pic.php)  （在 AOL.com 上開啟新頁面）。  

</div>

<div>

## <a name="public-im-provider-summary"></a>公用 IM 提供者摘要

下表提供公用 IM 服務提供者的摘要、與 Lync 的同盟功能以及授權需求。


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
<td><p>IM、目前狀態、音訊</p></td>
<td><p>Lync Server 用戶端存取授權，Lync Online 方案1/2/3</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>IM、目前狀態、音訊/視頻</p></td>
<td><p>Lync Server 用戶端存取授權（只要 WLM 為市場，即支援此功能）</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>IM、目前狀態</p></td>
<td><p>Lync Server 用戶端存取授權;支援于現有客戶的2014年6月。</p></td>
</tr>
<tr class="even">
<td><p>Yahoo</p></td>
<td><p>IM、目前狀態</p></td>
<td><p>除了 Lync Server 用戶端存取授權之外，還需要額外的 Microsoft Lync 公用 IM 連線使用者訂閱授權（"PIC USL"）。 從2012年9月的價目表，PIC USL 已不再提供購買。 擁有有效授權的客戶可以繼續與 Yahoo！進行聯盟 Messenger，直到服務在2014年6月30日為止關閉。</p></td>
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


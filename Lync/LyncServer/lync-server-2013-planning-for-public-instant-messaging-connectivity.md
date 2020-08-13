---
title: Lync Server 2013：規劃公用立即訊息連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52bc8a563a45e75b01932ee716df90f1cf2ca7da
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a>在 Lync Server 2013 中規劃公用立即訊息連線

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

公用立即訊息連線是同盟的類別，設定為允許您的內部及外部 Lync Server 2013 使用者從下列任何專案新增連絡人：

  - 信使連絡人

  - 雅虎\! 接觸

  - 北美線上 (AOL) 連絡人

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 (PIC USL) 已不再提供購買新的或更新的協定。 具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟 信使直到服務關閉日期。 AOL 和 Yahoo！的循環結束日期為2014年6月 已宣告。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的每一使用者、每月訂閱授權。 信使。 Microsoft 提供此服務的能力已因 Yahoo！的支援而產生，不會更新的基準合約。</P>
> <LI>
> <P>Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。 與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。 隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以透過 IM 和語音來抵達數百個人的人員。</P></LI></UL>



</div>

這個同盟類別需要下列規劃考慮：

  - Windows Live Messenger 使用者除了立即訊息之外，還可以與 Lync Server 2013 使用者進行對等音訊/視覺通訊。 您的 Edge Server 必須符合特定埠和通訊協定的需求。 如需詳細資訊，請參閱[決定 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。

  - 在規劃及部署提供同盟之典型 Edge Server 的情況下，Yahoo 立即訊息沒有獨特的需求。

  - 北美洲線上要求指派給 Access Edge service 的 Edge Server 憑證具有用戶端增強型金鑰使用方式 (EKU) 。

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中的憑證摘要-公用立即訊息連線](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [Lync Server 2013 中的埠摘要-公用立即訊息連線](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [Lync Server 2013 中的 DNS 摘要-公用立即訊息連線](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))

</div>

</div>

<span> </span>

</div>

</div>

</div>


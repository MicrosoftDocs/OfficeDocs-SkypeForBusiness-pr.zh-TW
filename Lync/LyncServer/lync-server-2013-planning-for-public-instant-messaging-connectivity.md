---
title: Lync Server 2013：規劃公用立即訊息連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4432484fbd6056d51a38090a18dbe106851d7c0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a>規劃 Lync Server 2013 中的公用立即訊息連線能力

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

公用立即訊息連線是一種聯盟類別，並設定為允許您的內部和外部 Lync Server 2013 使用者從下列任何專案新增連絡人：

  - 信使連絡人

  - Yahoo\! 聯絡

  - 美洲線上（AOL）連絡人

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（PIC USL）已不再提供購買新或續約協定的功能。 擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟 信使，直到服務關閉日期為止。 AOL 和 Yahoo！的存留期結束日期為2014年6月 已公佈。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟所需的每個使用者、每月訂閱授權 名單. Microsoft 提供此服務的能力已因 Yahoo！的支援而定，不會更新的底層合約。</P>
> <LI>
> <P>Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。 與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。 Skype 同盟將會新增到此清單，讓 Lync 使用者能夠透過 IM 和語音來取得成百上千的人員。</P></LI></UL>



</div>

此同盟類別需要下列規劃考慮：

  - 除了立即訊息之外，Windows Live Messenger 使用者也可以與 Lync Server 2013 使用者進行對等音訊/視覺通訊。 您的邊緣伺服器必須符合特定的埠和通訊協定需求。 如需詳細資訊，請參閱[判斷 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。

  - Yahoo [立即訊息] 沒有任何獨特的需求，除了在提供同盟的一般邊緣伺服器規劃和部署中通常所使用的情況。

  - 美洲線上要求指派給存取邊緣服務的 Edge 伺服器憑證具有用戶端增強型金鑰用法（EKU）。

<div>

## <a name="in-this-section"></a>本節內容

  - [證書摘要-Lync Server 2013 中的公用立即訊息連線](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [埠摘要-Lync Server 2013 中的公用立即訊息連線能力](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [DNS 摘要-Lync Server 2013 中的公用立即訊息連線](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))

</div>

</div>

<span> </span>

</div>

</div>

</div>


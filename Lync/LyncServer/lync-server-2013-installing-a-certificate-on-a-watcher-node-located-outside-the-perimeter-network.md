---
title: Lync Server 2013：在周邊網路以外的監視節點上安裝憑證
description: Lync Server 2013：在周邊網路以外的監視節點上安裝憑證。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66f40886e9784b5bd4182a60b955745b5daf2034
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574029"
---
# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a>在 Lync Server 2013 周邊網路以外的監看員節點上安裝憑證

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

在周邊網路中執行的 System Center Operations Manager 代理 (例如 Lync Server Edge Server) （如外部綜合交易觀察器節點) 或跨 Active Directory 網域服務信任界限） (以外，可能需要設定 System Center Operations Manager 閘道伺服器。 這個伺服器角色可讓與 Root Management Server 沒有任何信任關係的代理程式發出通知。 如需詳細資訊，請參閱 System Center Operations Manager 中的「管理 Operations Manager 中的閘道伺服器2007」。 TechNet 程式庫位置 [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703) 。

如果您在這些位置中的其中一個位置部署代理程式，您也需要要求及設定憑證，以啟用監看員節點，將提醒傳送至 System Center Operations Manager。 為了簡化這個程序，Operations Manager 團隊已建立一套公用程式，讓您要求正確類型的憑證，並安裝於監控程式節點電腦上。 如需詳細資訊，以及若要下載這些公用程式，請參閱「使用憑證產生嚮導輕鬆取得非網域加入的代理程式的憑證」博客文章 [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421) 。

</div>

<span> </span>

</div>

</div>

</div>


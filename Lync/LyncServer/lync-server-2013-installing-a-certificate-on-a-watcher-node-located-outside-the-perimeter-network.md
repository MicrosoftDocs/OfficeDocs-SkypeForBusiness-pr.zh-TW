---
title: Lync Server 2013：在周邊網路以外的觀察程式節點上安裝憑證
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
ms.openlocfilehash: 10cd31639445fab6138ea77cb40a03d727ecce12
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a>在 Lync Server 2013 周邊網路以外的監視者節點上安裝憑證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

在周邊網路（例如在 Lync Server Edge 伺服器）之外，企業外部（例如外部綜合交易觀察程式節點）或跨 Active Directory 網域服務信任邊界的 System Center Operations Manager 代理程式可能需要系統中心作業管理員閘道伺服器的設定。 這個伺服器角色允許沒有與根管理伺服器有信任關係的代理程式，以引發通知。 如需詳細資訊，請參閱 System Center Operations Manager TechNet 文件庫中的「管理 Operations Manager 2007 中[http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703)的閘道伺服器」。

如果您在其中一個位置部署代理程式，您也必須要求並設定可讓監視者節點傳送警示給 System Center Operations Manager 的憑證。 為了簡化此程式，Operations Manager 小組已建立一組實用程式，讓您在監視者節點電腦上要求並安裝正確類型的憑證。 如需詳細資訊，以及若要下載這些實用程式，請參閱「透過證書產生嚮導輕鬆地取得非網域加入的代理程式」 [http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421)中的 [博客文章]。

</div>

<span> </span>

</div>

</div>

</div>


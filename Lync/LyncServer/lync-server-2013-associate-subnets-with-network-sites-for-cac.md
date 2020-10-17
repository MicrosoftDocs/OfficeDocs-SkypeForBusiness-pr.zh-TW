---
title: Lync Server 2013：將子網與 CAC 的網路網站產生關聯
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for CAC
ms:assetid: a749c9b3-15f3-4e74-9f43-1507d3c2c940
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412786(v=OCS.15)
ms:contentKeyID: 48185017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fde0eb443a643371072c4c0018c05e2cd4538d0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531600"
---
# <a name="associate-subnets-with-network-sites-for-cac-in-lync-server-2013"></a>在 Lync Server 2013 中將子網與 CAC 的網路網站產生關聯

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-20_

網路中的每個子網路都必須與特定網路網站關聯。 這是因為我們需要子網路資訊來判斷端點所在的網路網站。 當會話中雙方雙方的位置都已知時，通話許可控制 (CAC) 可以判斷是否有足夠的頻寬可以建立通話。

通話許可控制沒有任何將子網與網站相關聯的特殊需求。 若要在拓撲中建立子網與網站之間的關聯性，請遵循在 [Lync Server 2013 中將子網與網路網站關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)的程式。 若要在通話許可控制的範例網路拓撲中查看網路網站 (及其各自的子網) ，請參閱規劃檔中的 [範例：在 Lync Server 2013 中收集通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 。

</div>

<span> </span>

</div>

</div>

</div>


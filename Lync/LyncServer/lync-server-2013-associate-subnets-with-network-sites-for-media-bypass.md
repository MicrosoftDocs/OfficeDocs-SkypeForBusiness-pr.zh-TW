---
title: Lync Server 2013：將子網與媒體旁路的網路網站產生關聯
description: Lync Server 2013：將子網與媒體旁路的網路網站產生關聯。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee03b51d29a88ff634cb87385c5889c35acd8884
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563579"
---
# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a>在 Lync Server 2013 中將子網與媒體旁路的網站建立關聯

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

<div>


> [!NOTE]  
> 本主題假定您已經設定好媒體旁路全域設定，以及媒體旁路的網路區域與網路網站。



</div>

網路中的每個子網路都必須與特定網路網站關聯。這是因為我們需要子網路資訊來判斷端點所在的網路網站。一旦知道工作階段中的雙方位置，媒體旁路就能判斷出要將媒體傳送到何處以便處理。

媒體旁路不需要任何特殊需求，就能將子網路與網路網站進行關聯。 若要在拓撲中建立子網與網站之間的關聯性，請遵循在 [Lync Server 2013 中將子網與網路網站關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)的程式。

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a>後續步驟：建立頻寬原則設定檔

當您為媒體旁路需要將子網路與網站關聯之後，必須建立一個或多個頻寬原則設定檔，以將子網路分割為具有良好連線能力與不具備良好連線能力的子網路，以因應媒體旁路所需。當網路地區內的所有子網路與沒有頻寬限制的網站關聯時，將提供良好的連線能力，因此這些子網路可以使用媒體旁路。

如需設定頻寬原則設定檔的程式，請參閱 [在 Lync Server 2013 中建立頻寬原則設定檔](lync-server-2013-create-bandwidth-policy-profiles.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>


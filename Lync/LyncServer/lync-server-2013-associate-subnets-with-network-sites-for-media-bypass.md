---
title: Lync Server 2013：將子網與網路網站建立關聯，以進行媒體旁路
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
ms.openlocfilehash: dd45daa964b51639c7fe1db3ff10e334e21641f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a>在 Lync Server 2013 中將子網與網路網站進行媒體旁路

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

<div>


> [!NOTE]  
> 本主題假設您已設定媒體旁路全域設定，且已設定媒體旁路的網路區域和網路網站。



</div>

您網路中的每個子網都必須與特定的網路網站相關聯。 這是因為子網資訊是用來判斷端點所在的網路網站。 當會話中雙方的位置都已知時，媒體旁路可以決定傳送媒體以進行處理的位置。

媒體旁路不需要將子網與網路網站建立關聯的任何特殊需求。 若要在您的拓撲中的子網和網路網站之間建立關聯，請遵循在[Lync Server 2013 中將子網與網路網站建立](lync-server-2013-associate-a-subnet-with-a-network-site.md)關聯的程式。

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a>後續步驟：建立頻寬原則設定檔

當您將子網與網路網站進行媒體旁路的關聯之後，您必須建立一個或多個頻寬原則設定檔，將子網分割成具有良好連線性的子網，而不需要使用，就是為了媒體略過。 網路區域中的所有子網都有一個沒有頻寬限制的網路網站具有良好的連線性，因此，這些子網可以使用媒體旁路。

如需設定頻寬原則設定檔的程式，請參閱[在 Lync Server 2013 中建立頻寬原則設定檔](lync-server-2013-create-bandwidth-policy-profiles.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>


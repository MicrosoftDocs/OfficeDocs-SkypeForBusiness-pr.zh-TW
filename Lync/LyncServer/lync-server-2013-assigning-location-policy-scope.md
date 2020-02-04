---
title: Lync Server 2013：指派位置原則範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning location policy scope
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205360(v=OCS.15)
ms:contentKeyID: 48185734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 395b8a4271338231b4c2c1927f7e40fb21a1cb14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-location-policy-scope-in-lync-server-2013"></a>在 Lync Server 2013 中指派位置原則範圍

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-06_

與其他 Lync 伺服器原則一樣，位置原則可以在多個範圍層級指派：全域、網站和使用者。 不過，使用者層級位置原則的運作方式比其他 Lync 伺服器原則稍有不同。 您不僅可以將每個使用者的位置原則套用到端點物件（例如使用者和常見的區域電話連絡人物件），也可以將它們套用至 Lync Server network 網站。 網路網站是與地理位置相關聯的用戶端子網群組（但不一定是整個中央網站或分支網站中的所有子網）。 連接至網路網站中子網的任何用戶端，都會自動挑選指派給該網路網站的位置原則。 在使用者層級位置原則指派給使用者和網路網站的情況下，網路網站的位置原則會覆寫任何每個使用者的原則設定。

每個網路網站都有一個指派的位置原則，而每個原則都有不同的 PSTN 用法、通知 Uri 以及指派給它的會議 Uri 值。

<div>


> [!NOTE]  
> 這個特殊原則範圍行為的原因是，當使用者位於某個 office 網站上的某個召集人造訪另一個網站，而且必須撥打電話時，無論該網路網站是哪個池或網站，都不需要使用 E9-1-1 呼叫路由設定ser 指派給您。



</div>

</div>

<span> </span>

</div>

</div>

</div>


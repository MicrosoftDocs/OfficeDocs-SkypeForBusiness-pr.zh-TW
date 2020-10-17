---
title: Lync Server 2013：指派位置原則範圍
description: Lync Server 2013：指派位置原則範圍。
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
ms.openlocfilehash: 9f6c46150241b0b224e8005556c0f2f594d8bce5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563379"
---
# <a name="assigning-location-policy-scope-in-lync-server-2013"></a>在 Lync Server 2013 中指派位置原則範圍

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-06_

與其他 Lync Server 原則一樣，位置原則可以指派于多個範圍層級：全域、網站和使用者。 不過，使用者層級位置原則的範圍會與其他 Lync Server 原則的行為稍有不同。 每位使用者的位置原則不僅可以套用至端點物件 (例如使用者和公共區域電話連絡人物件) ，也可以套用至 Lync Server 網路網站。 網路網站是與地理位置相關聯之用戶端子網的群組 (但不一定是整個中央網站或分支網站) 中的所有子網。 任何連接至網路網站之子網的用戶端，都會自動挑選指派給該網路網站的位置原則。 在將使用者層級位置原則指派給使用者和網路網站時，網路網站型位置原則會覆寫任何個別使用者原則設定。

每個網站都有指派的位置原則，且每個原則都具有指派給它的不同 PSTN 使用方式、通知 URIs 和會議 URIs 值。

<div>


> [!NOTE]  
> 這種特殊原則範圍行為的原因在於，當位於一個 office 網站上的集區的使用者要訪問另一個網站並必須撥打緊急電話時，就會套用適當于該網路網站的 E9-1-1 通話路由設定，不論使用者指派的集區或網站為何。



</div>

</div>

<span> </span>

</div>

</div>

</div>


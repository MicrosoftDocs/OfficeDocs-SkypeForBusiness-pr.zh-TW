---
title: Lync Server 2013： 指派位置原則範圍
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
ms.openlocfilehash: 69218c3f5399b62fc67fe0d538a98f1bdadd3cf4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-location-policy-scope-in-lync-server-2013"></a>指派 Lync Server 2013 中的位置原則範圍

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-06-06_

為以其他 Lync Server 的原則，可以位置原則指派多個範圍層級： 全域、 網站及使用者。 不過，使用者層級位置原則範圍行為與其他 Lync Server 原則元方式不同。 不僅可以個別使用者位置原則套用至端點物件 （例如使用者和一般區域電話連絡人物件），它們也可以套用至 Lync Server 的網路網站。 網路網站相關聯的地理位置的子網路會分組的用戶端 （但不是一定是在整個中央站台或分支網站中的所有子網路）。 自動連線至網路網站中的子網路的任何用戶端中挑選指派給該網路站台的位置原則。 在使用者層級位置原則指派給使用者與網路網站的情況下，網路網站為基礎的位置原則會覆寫任何個別使用者原則設定。

各網站皆位置原則指派給它，而每個原則會有不同的 PSTN 使用方式、 通知 Uri、 以及會議 Uri 值指派給它。

<div>


> [!NOTE]  
> 此特殊原則範圍行為是，這樣當使用者某一集區在某辦公室網站瀏覽其他網站且需撥打緊急電話，E9-1-1 通話路由設定適用於該網路站台的原因會套用不論何種集區或網站 user 為指派給。



</div>

</div>

<span> </span>

</div>

</div>

</div>


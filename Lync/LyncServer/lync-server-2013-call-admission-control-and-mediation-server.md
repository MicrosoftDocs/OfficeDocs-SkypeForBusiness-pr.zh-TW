---
title: Lync Server 2013：通話許可控制和轉送伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6c0cf06ccf9acde86e3ab344058803218eaf0cf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537260"
---
# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a>Lync Server 2013 中的通話許可控制和轉送伺服器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

通話許可控制 (CAC) ，第一次引進于 Lync Server 2010，它會根據可用的頻寬來管理即時會話建立，以協助避免使用者在擁擠的網路上 (QoE) 的品質欠佳。 為了支援此功能，在企業語音基礎結構與閘道或 SIP 主幹提供者之間提供信號和媒體翻譯的轉送伺服器，負責其在 Lync Server 端和閘道端的兩個互動的頻寬管理。 在通話許可控制服務中，通話的終端實體負責處理頻寬保留。 轉送伺服器與閘道端互動的「閘道對等」 (PSTN 閘道、IP-PBX、SBC) ，都不支援 Lync Server 2013 通話許可控制。 因此，轉送伺服器必須代表其閘道對等處理頻寬互動。 轉送伺服器會在任何可能的情況下，預先保留頻寬。 如果情況不允許 (例如，撥出至閘道對等時，如果閘道端上最終媒體端點的位置不明)，則會在撥打電話時保留頻寬。 此行為可能會導致頻寬超額的情況，但這是防止撥號錯誤的唯一方式。

媒體旁路與頻寬保留是互斥的。 如果對某通電話使用了媒體旁路，即無法再對其執行通話許可控制服務。 此處是假設與電話有關的連結都沒有頻寬受限的情形。 如果通話許可控制用於涉及轉送伺服器的特定通話，則該呼叫無法使用媒體旁路。

如需媒體旁路或通話許可控制的詳細資訊，請參閱規劃檔中的在 lync server [2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md) 或 [在 lync Server 2013 中規劃通話許可控制](lync-server-2013-planning-for-call-admission-control.md) 。

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013： 通話許可控制和中繼伺服器
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
ms.openlocfilehash: 0c93bdfc1133bea7d6e6c39358663c18016e0622
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a>通話許可控制和 Lync Server 2013 中的中繼伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-21_

通話許可控制 (CAC)、 第一次導入在 Lync Server 2010 中，管理即時工作階段建立，根據可用頻寬，以協助防止不佳的經驗品質 (QoE) 擁塞網路上的使用者。 若要支援此功能，中繼伺服器，可提供企業語音基礎結構和閘道或 SIP 主幹提供者之間的訊號和媒體轉譯，負責在 Lync 其兩個互動的頻寬管理左側與閘道端伺服器。 在通話許可控制服務中，通話的終端實體負責處理頻寬保留。 中繼伺服器與閘道端互動閘道對等 （PSTN 閘道、 IP PBX、 SBC） 不支援 Lync Server 2013 通話許可控制。 因此，中繼伺服器已處理代表其閘道對等網路頻寬互動。 請盡可能中繼伺服器將會事先預約頻寬。 如果情況不允許 (例如，撥出至閘道對等時，如果閘道端上最終媒體端點的位置不明)，則會在撥打電話時保留頻寬。 此行為可能會導致頻寬超額的情況，但這是防止撥號錯誤的唯一方式。

媒體旁路與頻寬保留是互斥的。 如果對某通電話使用了媒體旁路，即無法再對其執行通話許可控制服務。 此處是假設與電話有關的連結都沒有頻寬受限的情形。 如果使用牽涉到中繼伺服器的特定呼叫的通話許可控制，則該通話無法使用媒體旁路。

如需詳細資訊的媒體旁路或通話許可控制，請參閱[規劃媒體旁路 Lync Server 2013 中](lync-server-2013-planning-for-media-bypass.md)or [Planning for Lync Server 2013 中的通話許可控制](lync-server-2013-planning-for-call-admission-control.md)中規劃文件。

</div>

<span> </span>

</div>

</div>

</div>


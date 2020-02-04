---
title: Lync Server 2013：通話許可控制和中繼伺服器
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
ms.openlocfilehash: 8aa12bd22f27cbe25946c14ad04977b98025d557
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a>Lync Server 2013 中的通話許可控制和中繼伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

呼叫許可控制（CAC），第一次在 Lync Server 2010 中引入，可根據可用的頻寬來管理即時會話建立，以協助避免使用者在擁擠的網路上出現品質欠佳（QoE）。 若要支援這項功能，您可以在企業語音結構和閘道或 SIP 中繼提供者之間提供信號與媒體翻譯的中繼伺服器，負責在 Lync 上的兩個互動進行頻寬管理伺服器端和閘道端。 在 [呼叫許可控制] 中，通話的終止實體會處理頻寬保留。 在閘道端與中繼伺服器互動的閘道對等（PSTN 閘道、IP PBX、SBC）不支援 Lync Server 2013 通話許可控制。 因此，中繼伺服器必須代表其閘道對等來處理頻寬互動。 只要有可能，中繼伺服器就會提前保留頻寬。 如果無法這樣做（例如，如果閘道端的最終媒體端點的位置不適供撥出電話到閘道對等），則會在撥打電話時保留頻寬。 這種行為可能會導致過度訂閱頻寬，但這是避免誤報的唯一方法。

[媒體旁路] 和 [頻寬保留] 是相互排斥的。 如果使用媒體旁路進行通話，就不會針對該通話執行呼叫許可控制。 這裡的假設是通話中沒有受限制頻寬的連結。 如果呼叫許可控制是用於涉及轉送伺服器的特定通話，該呼叫無法使用媒體旁路。

如需媒體旁路或呼叫許可控制的詳細資料，請參閱規劃檔中的[lync server 2013 規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)或在[lync Server 2013 中規劃通話許可控制](lync-server-2013-planning-for-call-admission-control.md)。

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：媒體旁路簡介
description: Lync Server 2013：媒體旁路的簡介。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3859c41a01ae5e7f1100a6872fd4e6747f45dbd8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577329"
---
# <a name="overview-of-media-bypass-in-lync-server-2013"></a>Lync Server 2013 中的媒體旁路概述

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

當您想要將已部署的轉送伺服器數目降至最低時，媒體旁路很有用。 一般來說，轉送伺服器集區會部署在中央網站，它會控制分支網站上的閘道。 啟用媒體旁路允許公用交換電話網路的媒體 (PSTN) 來自分支網站用戶端的呼叫，以直接透過這些網站上的閘道來流向。 Lync Server 2013 輸出呼叫路由和 Enterprise Voice 原則必須正確設定，才能讓來自分支網站之用戶端的 PSTN 呼叫路由傳送至適當的閘道。

Wi-Fi 網路通常會比有線網路體驗更大的封包遺失。 從這封包中復原的情況通常不是閘道可容納的內容。 因此，建議您先評估 Wi-Fi 網路的品質，再決定是否應該為無線子網啟用旁路。 延遲延遲與從封包遺失的復原也有折衷。 RTAudio，可供未略過轉送伺服器之呼叫使用的編解碼器，會更適合處理封包遺失。

在您的企業語音結構就緒後，規劃媒體旁路是直接的。

  - 如果您有集中式拓撲，但沒有分支網站的 WAN 連結，您可以啟用全域媒體旁路，因為不需要微調控制項。

  - 如果您有分散式拓撲，且該拓撲是由一或多個網路地區和其附屬分支網站組成，請決定下列各項：
    
      - 您的轉送伺服器對等是否可以支援媒體旁路所需的功能。
    
      - 每個網路地區的哪些網站已正確連接。
    
      - 媒體旁路和通話許可控制的組合適用于您的網路。

當您啟用媒體旁路時，系統會自動為網路地區產生唯一的旁路識別碼，以及該地區內沒有頻寬限制的所有網路網站。 在地區內具有頻寬限制的網站，以及透過頻寬限制透過 WAN 連結連線至區域的網站，會為每個使用者指派各自的唯一旁路 IDs。

當使用者呼叫 PSTN 時，轉送伺服器會將用戶端子網上的旁路識別碼與閘道子網的旁路識別碼進行比較。 如果兩個旁路 IDs 相符，媒體旁路會用於通話。 如果旁路 IDs 不符，則通話的媒體必須透過轉送伺服器流動。

當使用者從 PSTN 接收來電時，使用者的用戶端會將其旁路識別碼與 PSTN 閘道的要求進行比較。 如果兩個略過的 IDs 相符，媒體就會直接從閘道流向用戶端，以略過轉送伺服器。

只有 Lync 2010 或以上的用戶端和裝置才支援與轉送伺服器的媒體旁路互動。

<div>


> [!IMPORTANT]  
> 除了啟用全域旁路之外，您還必須在每個 PSTN 主幹上個別啟用媒體旁路。 如果以全域方式啟用旁路，但未針對特定 PSTN 主幹啟用旁路，則任何涉及該 PSTN 主幹的呼叫都不會叫用媒體旁路。 此外，當媒體旁路設定為 <STRONG>使用網站與地區資訊</STRONG>時，您必須將所有可路由的子網與所在的網站產生關聯。 如果不想要略過的網站內有可路由的子網，這些子網應該會在新的網站中群組，再啟用媒體旁路。 這樣做會保證會為 unroutable 子網指派不同的回避識別碼。



</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的媒體旁路模式](lync-server-2013-media-bypass-modes.md)  
[Lync Server 2013 中的媒體旁路和通話許可控制](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Lync Server 2013 中媒體旁路的技術需求](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


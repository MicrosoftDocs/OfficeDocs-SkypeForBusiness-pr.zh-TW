---
title: Lync Server 2013：媒體旁路簡介
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
ms.openlocfilehash: 84c70cae521deebecf30e7c8ec6505b18e9842fa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a>Lync Server 2013 中的媒體旁路概覽

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

如果您想要將部署的中繼伺服器數量減至最少，則可以使用 [媒體旁路]。 通常，會將中繼伺服器池部署在中央網站，它會控制分支網站上的閘道。 啟用「媒體旁路」可讓您從分支網站上的用戶端直接透過閘道從分支網站傳送公用交換電話網絡（PSTN）通話的媒體。 Lync Server 2013 出站通話路由及企業語音原則必須正確設定，才能將分支網站用戶端的 PSTN 呼叫路由至適當的閘道。

Wi-fi 網路通常會比有線網路遇到更多的資料包遺失情況。 從這個資料包遺失中進行的復原並非通常是由閘道所能容納的。 因此，建議您先評估 Wi-fi 網路的品質，然後再決定是否應該針對無線子網啟用旁路。 在延遲減少與從資料包遺失到恢復的情況下，也有一個折衷考慮。 RTAudio （可供不略過中繼伺服器的呼叫使用的編解碼器）更適合處理資料包遺失。

在您的企業語音結構就緒之後，規劃媒體略過簡單。

  - 如果您的中央拓撲沒有 WAN 連結至分支網站，您可以啟用全域媒體旁路，因為不需要微調控制措施。

  - 如果您有包含一或多個網路區域及其附屬分支網站的分散式拓朴，請判斷下列事項：
    
      - 您的中繼伺服器對等是否能夠支援媒體旁路所需的功能。
    
      - 每個網路區域中的哪些網站有良好的連接。
    
      - [媒體旁路] 與 [呼叫許可控制] 的組合適合您的網路。

當您啟用媒體旁路時，系統會自動為網路區域建立唯一的旁路 ID，以及該區域內不含頻寬限制的所有網路網站。 在區域內具有頻寬限制的網站，以及使用頻寬限制連接到區域的網站，會分別指派自己獨特的旁路 Id。

當使用者撥打電話給 PSTN 時，中繼伺服器會將用戶端子網上的旁路 ID 與閘道子網的旁路 ID 進行比較。 如果兩個旁路識別碼相符，就會使用媒體旁路進行通話。 如果旁路識別碼不相符，通話的媒體必須透過中繼伺服器進行流動。

當使用者從 PSTN 接收來電時，使用者的用戶端會將它的旁路 ID 與 PSTN 閘道的旁路識別碼進行比較。 如果兩個旁路識別碼相符，媒體就會直接從閘道流向用戶端，而不需要轉送伺服器。

只有 Lync 2010 或以上的用戶端與裝置支援與中繼伺服器的媒體旁路互動。

<div>


> [!IMPORTANT]  
> 除了在全域啟用旁路媒體之外，您還必須在每個 PSTN 主幹上個別啟用媒體旁路。 如果旁路是全域啟用，但未針對特定 PSTN 幹線啟用，則任何涉及 PSTN 幹線的呼叫都不會呼叫媒體旁路。 此外，當 [媒體旁路] 設定為<STRONG>使用網站和區域資訊</STRONG>時，您必須將所有可路由的子網與它們所在的網站建立關聯。 如果在不想要略過的網站內有可路由的子網，在您啟用媒體旁路之前，必須將這些子網群組放在新的網站中。 如此一來，就能保證 unroutable 子網已獲指派不同的旁路 ID。



</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的媒體旁路模式](lync-server-2013-media-bypass-modes.md)  
[Lync Server 2013 中的媒體旁路和通話許可控制](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Lync Server 2013 中媒體旁路的技術需求](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 媒體旁路的 Lync Server 2013： 概觀
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
ms.openlocfilehash: 66c2484b656cce15a6f7d013060c1fc95047f49d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a>Lync Server 2013 中的媒體旁路概觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-21_

當您想要部署的中繼伺服器的數目降至最低，媒體旁路特別有用。 一般而言，或中繼伺服器集區將會部署在中央網站，而且它會控制在分支站台的閘道。 啟用媒體旁路允許來自在分支站台的用戶端至流程直接通過這些網站閘道的公用交換的電話網路 (PSTN) 通話的媒體。 Lync Server 2013 撥出電話路由和企業語音原則必須正確設定，讓來自用戶端在分支網站的 PSTN 通話路由傳送至適當的閘道。

Wi-fi 網路通常會遇到更多比有線網路封包遺失。 從這個封包遺失復原不是通常可以容納的閘道。 因此，建議您先決定是否應啟用無線子網路的旁路評估的 Wi-fi 網路品質。 與封包遺失考量，以及從復原延遲減少沒有取捨。 RTAudio，這是適用於不會略過中繼伺服器的呼叫轉碼器是更適合處理封包遺失。

您的企業語音結構就緒後，規劃媒體旁路便相當簡單。

  - 如果您有集中式的拓撲，而 WAN 連結至分支網站，您可以啟用通用媒體旁路，因為不需要精細的控制。

  - 如果您有分散式的拓撲，其中包含一或多個網路地區及其附屬的分支網站的決定下列項目：
    
      - 中繼伺服器對等是否可以支援媒體旁路所需的功能。
    
      - 每個網路地區中的哪些網站已妥善連接。
    
      - 哪一種媒體組合旁路和通話許可控制適合您的網路。

當您啟用媒體旁路時，唯一的旁路 ID 會自動產生的網路地區，並沒有該區域內的頻寬限制的所有網路網站。 使用的區域內的頻寬限制的網站和網站透過與頻寬限制的 WAN 連結來連線至區域是每個指派給其專屬唯一旁路 Id。

當使用者進行 pstn 通話時，中繼伺服器比較旁路 ID 之用戶端子網路與閘道子網路的旁路識別碼。 如果這兩個略過識別碼比對，媒體旁路用於通話。 略過不相符識別碼，如果通話的媒體必須經過中繼伺服器。

當使用者收到 PSTN 呼叫時，使用者的用戶端會比較的 PSTN 閘道其旁路識別碼。 如果這兩個略過識別碼比對，媒體流向直接從用戶端，略過中繼伺服器閘道。

只有 Lync 2010 或以上的用戶端和裝置支援媒體旁路與中繼伺服器之間的互動。

<div>


> [!IMPORTANT]  
> 除了啟用媒體旁路全域，您必須啟用媒體旁路，分別在每個 PSTN 主幹。 如果旁路全域，已啟用，但未啟用特定的 PSTN 主幹，媒體旁路將不會叫用任何涉及該 PSTN 主幹的通話。 此外，當媒體旁路設為<STRONG>使用網站與地區資訊</STRONG>，您必須關聯可路由傳送的所有子網路所屬的所在的網站。 如果不想略過站台內的路由傳送子網路，則這些子網路應進行分組，新的站台內啟用媒體旁路之前。 這樣可確保無法路由的子網路會指派不同的旁路 id。



</div>

<div>

## <a name="see-also"></a>另請參閱


[媒體旁路模式的 Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[媒體旁路和 Lync Server 2013 中的通話許可控制](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Lync Server 2013 中略過媒體的技術需求](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


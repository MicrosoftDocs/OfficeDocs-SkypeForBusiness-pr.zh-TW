---
title: 設定媒體旁路全域設定以使用網站和區域資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac820c444f894aabf060c06d6f034f7d92b696c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a>在 Lync Server 2013 中設定媒體旁路全域設定以使用網站和區域資訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

<div>


> [!NOTE]
> 本主題假設您已將來自中繼伺服器的任何干線連線的媒體旁路設定設為對等（公用交換電話網絡（PSTN）閘道、IP PBX，或網際網路電話語音的會話邊界控制器（SBC）您想要媒體略過轉送伺服器的特定網站或服務的提供者（ITSP）。<BR>本主題也假設您已定義拓撲建立器中的所有中心網站和分支網站，符合在<A href="lync-server-2013-create-or-modify-a-network-region.md">Lync server 2013 中建立或修改網路區域</A>、在 lync server <A href="lync-server-2013-create-or-modify-a-network-site.md">2013 中建立或修改網路網站</A>中的步驟，以及在<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">lync server 2013 中將子網與網路網站建立關聯</A>的方式。 如果不相符，則媒體略過將無法成功。



</div>

除了為與對等相關聯的個別幹線連線啟用媒體旁路之外，您還必須設定全域設定。 如果您使用本主題中的步驟來設定媒體旁路的全域設定，假設下列其中一個或兩個情況會影響您的設定：

  - 您在 Lync 伺服器端點與您在中繼連線中設定媒體旁路的任何對等的使用者之間，*都沒有良好的連線*性。

  - 已啟用 [頻寬管理] 的通話許可控制（CAC）。
    
    <div>
    

    > [!NOTE]
    > 如需有關呼叫許可控制和媒體旁路考慮的詳細資料，請參閱規劃檔中的<A href="lync-server-2013-media-bypass-and-mediation-server.md">Lync server 2013 的媒體旁路和轉送伺服器</A>中的 [呼叫 PSTN 連線的接入控制] 區段。

    
    </div>

網路區域和網路網站資訊都是在 [呼叫許可控制] 中共用，當兩個專案都啟用時，媒體就會繞過高級企業語音功能。 因此，如果您已設定 [通話許可控制]，則不需要您使用下列程式來編輯專門針對媒體旁路的網站和區域資訊。 如果您尚未設定 [通話許可控制] 的網路區域和網站，且您想要變更媒體旁路設定，請遵循此程式中的步驟。

或者，如果您想要在進行回避決定時使用網站和區域資訊，但不想要啟用呼叫許可控制，請遵循下列步驟。 在這種情況下，頻寬限制連結仍需要透過網路網站間原則來表示，如在[Lync Server 2013 中建立網路站間原則](lync-server-2013-create-network-intersite-policies.md)中所述。 在這種情況下，實際的頻寬限制並不重要，因為尚未啟用 [通話許可控制]。 相反地，這些連結是用來將子網劃分成分區，以指定那些沒有頻寬限制且可以使用媒體略過的專案。 請注意，當您同時啟用 [通話許可控制] 和 [媒體旁路] 時，也是如此。

此外，若要讓 [旁路] 正常運作，在拓撲建立器中定義的網站與在您設定網路區域和網路網站時所定義的網站而言，都必須是一致性。 例如，如果您在拓撲建立器中定義了一個已部署 PSTN 閘道的分支網站，則必須使用企業語音原則來設定分支網站，讓分支網站使用者能夠透過 PSTN 路由其 PSTN 通話分支網站上的閘道。

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a>若要設定媒體旁路的網站和區域資訊

1.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左側導覽列中，按一下 [**網路**設定]。

3.  在資料表中按兩下**全域**配置。

4.  在 [**編輯全域設定**] 頁面上，選取 [**啟用旁路媒體**] 核取方塊。

5.  按一下 [**使用網站和地區**設定]。

6.  如有需要，請選取 [為**未對應的網站啟用旁路**] 核取方塊。
    
    <div>
    

    > [!NOTE]
    > 只有當您有一個或多個大型網站與不含頻寬限制（例如大型中央網站）的同一個區域相關聯時，才選取此核取方塊，但您還有一些與有頻寬的相同區域相關聯的分支網站限制. 當您針對未對應的網站啟用 [旁路] 時，系統會簡化配置，讓您只指定與分支網站相關聯的子網，而不需要指定與所有網站相關聯的所有子網。 如果已啟用 [通話許可控制]，建議您不要選取此核取方塊。

    
    </div>

7.  按一下 [認可]****。

接著，將子網新增至網路網站，如在[Lync Server 2013 中將子網與媒體旁路的網路網站相關聯](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)的說明。 （在[Lync Server 2013 中，將子網與網路網站相關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)的實際程式將在 [與網路網站建立關聯] 中描述。）將所有子網與網路網站建立關聯之後，就會完成媒體略過部署。

<div>


> [!IMPORTANT]
> 如果您還沒有建立網路區域和網路網站，您必須先建立這些區域，才能繼續進行媒體旁路部署。 如需詳細資訊，請參閱<A href="lync-server-2013-create-or-modify-a-network-region.md">在 Lync server 2013 中建立或修改網路區域</A>，以及<A href="lync-server-2013-create-or-modify-a-network-site.md">在 lync Server 2013 中建立或修改網路網站</A>。



</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中將子網與網路網站進行媒體旁路](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


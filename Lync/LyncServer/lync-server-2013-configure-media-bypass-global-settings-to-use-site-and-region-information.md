---
title: 設定媒體旁路通用設定以使用網站與地區資訊
description: 設定媒體旁路全域設定以使用網站與地區資訊。
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
ms.openlocfilehash: a65dcec966030262d6d0fb5530b94f2411003c7a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559799"
---
# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a>在 Lync Server 2013 中設定媒體旁路全域設定，以使用網站與地區資訊

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

<div>


> [!NOTE]
> 本主題假設您已經針對您希望媒體略過中繼伺服器的特定網站或服務，對於從中繼伺服器至對等 (網際網路電話語音服務提供者 (ITSP) 的公用交換電話網路 (PSTN) 閘道、IP-PBX 或工作階段界限控制器 (SBC)) 的任何主幹連線設定媒體旁路。<BR>本主題也假設您已在拓撲產生器中定義所有的中央網站和分支網站，使其符合您依照在 <A href="lync-server-2013-create-or-modify-a-network-region.md">Lync server 2013 中建立或修改網路地區</A>的步驟，在 lync server <A href="lync-server-2013-create-or-modify-a-network-site.md">2013 中建立或修改網路網站</A>，以及 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 lync server 2013 中建立子網與網路網站的關聯</A>，都符合您執行的網路地區、網路網站及子網設定。 如果不符合，則媒體旁路會失敗。



</div>

除了針對與對等關聯的個別主幹連線啟用媒體旁路以外，您也必須設定全域設定。如果您使用本主題中的步驟來設定媒體旁路的全域設定，則假設下列其中一種或兩種情況會影響您的設定：

  - 您沒有在 Lync Server 端點和您在主幹連線上設定媒體旁路的任何對等專案之間取得 *良好的連線* 能力。

  - 已啟用頻寬管理的通話許可控制 (CAC)。
    
    <div>
    

    > [!NOTE]
    > 如需通話許可控制和媒體旁路考慮的詳細資訊，請參閱規劃檔中的「 <A href="lync-server-2013-media-bypass-and-mediation-server.md">Lync server 2013 中的媒體旁路和轉送伺服器</A> 」一節中的「呼叫許可控制 PSTN 連線」一節。

    
    </div>

若已啟用通話許可控制與媒體旁路進階 Enterprise Voice 功能，則網路地區和網路網站資訊會由這兩項功能共用。因此，如果您已經設定通話許可控制，則不需要使用下列程序特別針對媒體旁路來編輯網站與地區資訊。如果您尚未設定通話許可控制的網路地區和網站，而想要變更媒體旁路設定，請遵循此程序中的步驟。

或者，如果您想要使用網站與地區資訊進行旁路決策，但無意啟用通話許可控制，請遵循下列步驟。 在這種情況下，頻寬限制連結仍必須透過網路網站間原則來表示，如在 [Lync Server 2013 中建立網路站策略中](lync-server-2013-create-network-intersite-policies.md)所述。 因為尚未啟用通話許可控制，所以在此情況下實際頻寬限制沒那麼重要。 這些連結會用來分割子網路，以指定沒有頻寬限制，因而可運用媒體旁路的子網路。 請注意，若已同時啟用通話許可控制和媒體旁路，情形也是如此。

此外，為了讓旁路能夠正常運作，在拓撲產生器中所定義的網站與設定網路地區和網站時所定義的網站之間，必須是一致的一致性。 例如，如果您已在拓撲產生器中定義的分支網站，只部署了 PSTN 閘道，則該分支網站必須設定企業語音原則，讓分支網站使用者能夠透過分支網站的 PSTN 閘道路由傳送 PSTN 通話。

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a>設定媒體旁路的網站與地區資訊

1.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左導覽列中，按一下 **[網路組態]**。

3.  連按兩下表格中的 **[全域]** 組態。

4.  在 **[編輯通用設定]** 頁面上，選取 **[啟用媒體旁路]** 核取方塊。

5.  按一下 **[使用網站和地區設定]**。

6.  如有必要，請選取 **[啟用非對應網站的旁路]** 核取方塊。
    
    <div>
    

    > [!NOTE]
    > 如果您有一或多個與相同區域關聯的大型網站沒有頻寬限制 (例如，大型中央網站)，但也有一些與相同區域關聯的分支網站具有頻寬限制，請選取此核取方塊。當您啟用非對應網站的旁路時，設定作業比較精簡，因為您只需指定與分支網站關聯的子網路，而不需指定與所有網站關聯的所有子網路。如果已啟用通話許可控制，則建議您不要選取此核取方塊。

    
    </div>

7.  按一下 **[認可]**。

接下來，將子網新增至網站，如在 [Lync Server 2013 中關聯子網與媒體旁路的網路網站](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)所述。  (將子網與網路網站相關聯的實際程式，會在 [ [將子網與 Lync Server 2013 中的網路網站關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)] 中說明。 ) 將所有子網與網站關聯之後，媒體旁路部署即完成。

<div>


> [!IMPORTANT]
> 如果您尚未建立網路地區和網路網站，您必須先予以建立，才能繼續進行媒體旁路部署。 如需詳細資訊，請參閱在 lync server <A href="lync-server-2013-create-or-modify-a-network-region.md">2013 中建立或修改網路地區</A> ，以及 <A href="lync-server-2013-create-or-modify-a-network-site.md">在 lync Server 2013 中建立或修改網路網站</A>。



</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中將子網與媒體旁路的網站建立關聯](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


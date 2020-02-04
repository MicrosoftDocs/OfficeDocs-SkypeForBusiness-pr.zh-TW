---
title: Lync Server 2013：為 E9 設計 SIP 幹線-1-1
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the SIP trunk for E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48184096
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0ca42092b33632dbc7aed84808499b13ab0843c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a>在 Lync Server 2013 中針對 E9-1-1 設計 SIP 主幹

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

Lync Server 會使用 SIP trunks，將緊急呼叫連線至 E9-1-1 服務提供者。 您可以在一個中央網站、多個中央網站或每個分支網站上設定 E9-1-1 的緊急服務 SIP trunks。 不過，如果呼叫者的網站與託管緊急服務 SIP 主幹的網站之間的 WAN 連結無法使用，則在斷開連接的網站上由使用者所撥的通話將需要使用者語音原則中的特殊電話使用記錄，將呼叫路由至ECRC 透過本機的公用交換電話網絡（PSTN）閘道。 如果通話許可控制併發通話限制生效，就是如此。

<div>


> [!NOTE]  
> 在 Lync Server 環境中，有兩種方式可以實施 SIP 主幹： 
> <UL>
> <LI>
> <P>使用多宿主的出局轉送伺服器，使用其向外公開路由介面與 SIP 中繼提供者通訊。</P>
> <LI>
> <P>使用內部部署會話邊界控制器（SBC），在中繼伺服器與 SIP 中繼提供者的服務之間提供安全的 demarcation 點。</P></LI></UL>如果您選擇後一個方法，請確定您所選擇的 SBC 與模型已獲認證，並且支援將目前狀態資訊資料格式位置物件（PIDF-LO）位置資料傳送成其 SIP 邀請的一部分。 否則，來電將會在緊急服務服務提供者去除其位置資訊時收到。 如需有關驗證的 SBCs 的詳細資料，請參閱「Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</A>的基礎結構合格」。<BR>E9-1-1 服務提供者會提供一組半形的存取權，以實現冗余。 您需要針對中繼伺服器拓撲和呼叫路由設定進行數個決策。 您會將 SBCs 視為同等對等，並使用迴圈式路由來進行呼叫，或是將一個 SBC 指派為主要的，另一個是副？



</div>

如需在 Lync Server 中部署 SIP 主幹的詳細資料，請參閱[如何在 Lync server 2013 中實現 sip 中繼？](lync-server-2013-how-do-i-implement-sip-trunking.md)。 下列問題將協助您決定如何部署 E9 的 SIP trunks-1-1。

  - **您是否應該透過專用租使用者或共用的網際網路連線來部署 SIP 幹線？**  
    緊急通話永遠都是重要的。 專用線路提供的連線功能不會被網路上的其他流量搶佔，並可讓您實現服務品質（QoS）。 請記住，如果您是透過公用網際網路連線到緊急服務服務提供者，而且您需要保證緊急通話的機密性，則需要進行 IPSec 加密。

<!-- end list -->

  - **您的 E9-1-1 部署是否專為災難耐受性而設計？**  
    因為這是緊急解決方案，所以復原非常重要。 在災難容錯位置部署主要和次要轉送伺服器和 SIP trunks。 建議您部署最接近支援的使用者的主要轉送伺服器，並透過次要轉送伺服器（位於不同的地理位置）路由容錯移轉呼叫。

<!-- end list -->

  - **您是否應該針對每個分支機搆部署個別的 SIP 幹線？**  
    Lync Server 提供幾項策略，可處理分支辦公室中的語音復原，包括：具備彈性資料網路、在每個分支部署 SIP 幹線，或在中斷期間將呼叫推送到本機閘道。 如需詳細資訊，請參閱[Lync Server 2013 中的分支網站 SIP 中繼](lync-server-2013-branch-site-sip-trunking.md)。

<!-- end list -->

  - **已啟用呼叫許可控制（CAC）嗎？**  
    Lync Server 不會以任何不同于一般呼叫的方式來處理緊急通話。 基於這個原因，頻寬管理或呼叫許可控制（CAC）會對 E9-1-1 設定造成負面影響。 如果啟用了 CAC，緊急通話會遭到封鎖，或路由到本機 PSTN 閘道，且在路由緊急通話的連結上超過設定的限制。 如本主題前面所示，此類呼叫將沒有位置資料，必須手動路由至 ECRC。

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：設計 E9-1-1 的 SIP 主幹
description: Lync Server 2013：設計 E9-1-1 的 SIP 主幹。
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
ms.openlocfilehash: ced3c92cb14739367c4e54da933a536cb66deb08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542599"
---
# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a>在 Lync Server 2013 中設計 E9-1-1 的 SIP 主幹

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

Lync Server 使用 SIP 主幹將緊急通話連接至 E9-1-1 服務提供者。 您可以在一個中央網台、多個中央網台或每個分支網站上設定 E9-1-1 的緊急服務 SIP 主幹。 不過，如果來電者網站與主控緊急服務 SIP 主幹的網站之間的 WAN 連結無法使用，由中斷連線網站上的使用者所撥打的電話在使用者語音原則中，需要有特殊的電話使用方式記錄來指定透過本機公用交換電話網路 (PSTN) 閘道，將電話路由至 ECRC。 如果通話許可控制並行通話限制有效，則有同樣的需求。

<div>


> [!NOTE]  
> 在 Lync Server 環境中執行 SIP 主幹的方式有兩種： 
> <UL>
> <LI>
> <P>使用多宿主的轉送伺服器，利用其向外公開路由的介面與 SIP 主幹提供者通訊。</P>
> <LI>
> <P>使用內部部署會話邊界控制器 (SBC) ，以在轉送伺服器和 SIP 主幹提供者的服務之間提供安全的分割點。</P></LI></UL>如果您選擇後者，請確定您所選擇的 SBC 品牌與型號已取得認證，並且支援傳遞「目前狀態資訊資料格式位置物件」(PIDF-LO) 位置資料做為其 SIP INVITE 的一部分。 否則電話將會送達去除其位置資訊的緊急服務服務提供者。 如需認證 SBCs 的詳細資訊，請參閱「Microsoft Lync 的基礎結構合格」 <A href="https://go.microsoft.com/fwlink/p/?linkid=248425">https://go.microsoft.com/fwlink/p/?LinkId=248425</A> 。<BR>E9-1-1 服務提供者為您提供一組 SBC 的存取做為後備之用。 您需要對轉送伺服器拓撲及通話路由設定進行幾項決策。 您是要將兩台 SBC 視為對等，並對它們之間的通話使用循環配置資源路由；或是要將一個 SBC 指派為主要，而另一個指派為次要呢？



</div>

如需在 Lync Server 中部署 SIP 主幹的詳細資訊，請參閱 [如何在 Lync server 2013？中執行 sip 中繼](lync-server-2013-how-do-i-implement-sip-trunking.md)。 為了協助決定如何部署 E9-1-1 的 SIP 主幹，您應該先回答下列問題。

  - **您應該在專用的租用網際網路連線上還是共用的網際網路連線上部署 SIP 主幹？**  
    重點是一定要能夠接通緊急通話。專用線路可提供不被網路上其他流量佔用的連線，並讓您能夠實作服務品質 (QoS)。請記住，如果您透過公用網際網路連線至緊急服務服務提供者，而且需要保證緊急電話的機密性，則需要 IPSec 加密。

<!-- end list -->

  - **您的 E9-1-1 部署是針對嚴重損壞而設計嗎？**  
    因為這是緊急解決方案，所以恢復能力很重要。 在災難容錯位置部署主要和次要轉送伺服器和 SIP 主幹。 最好是部署最接近其支援之使用者的主要轉送伺服器，並將容錯移轉呼叫路由傳送至位於不同地理位置) 中的次要轉送伺服器 (。

<!-- end list -->

  - **您是否應該為每個分公司部署個別的 SIP 主幹？**  
    Lync Server 提供數個策略，可處理分支辦公室中的語音恢復作業，包括：具有可恢復的資料網路、在每個分支部署 SIP 主幹，或在中斷期間將呼叫推出至本機閘道。 如需詳細資訊，請參閱 [Lync Server 2013 中的分支網站 SIP trunk](lync-server-2013-branch-site-sip-trunking.md)。

<!-- end list -->

  - **是否啟用通話許可控制 (CAC)?**  
    Lync Server 不會處理與一般通話不同的緊急通話。 因此，頻寬管理或通話許可控制 (CAC) 可能對 E9-1-1 組態有負面影響。 如果啟用 CAC，且在路由緊急通話的連結上的流量超出設定的限制，則緊急通話可能會被封鎖或路由至本機 PSTN 閘道。 如同本主題稍早所述，這類通話將會沒有位置資料，並且必須以手動方式路由至 ECRC。

</div>

<span> </span>

</div>

</div>

</div>


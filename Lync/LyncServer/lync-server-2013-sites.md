---
title: Lync Server 2013 網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37843e85f5da250b3cb3d8e0fa4cdccdf506176d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a>Lync Server 2013 的 lync Server 網站

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-16_

在 Lync Server 中，您可以在網路上定義包含 Lync Server 元件的*網站*。 網站是以高速、低延遲網路來妥善連線的一組電腦，例如單一區域網路 (LAN) 或以高速光纖網路連接的兩個網路。 請注意，Lync Server 網站是來自 Active Directory 網域服務網站和 Microsoft Exchange Server 網站的不同概念。 您的 Lync 伺服器網站不需要對應至您的 Active Directory 網站。

<div>

## <a name="site-types"></a>網站類型

每個網站都是*中央網站*（包含至少一個前端集區或 Standard Edition server），或是一個*分支網站*。 每個分支網站都會與剛好一個中央網站產生關聯，而且分支網站的使用者可以從關聯的中央網站的伺服器取得大多數的 Lync Server 功能。

每一個分支網站都包含下列其中一項：

  - *Survivable Branch 裝置 (SBA) *，也就是具有 Lync Server 註冊機構的工業標準刀片式伺服器，以及在 Windows server 上執行的轉送伺服器。 Survivable Branch 裝置也包含公用交換電話網路 (PSTN) 閘道。 Survivable 分支裝置專為25到1000使用者之間的分支網站而設計。

  - *Survivable Branch Server (SBS) *，也就是執行 Windows Server 符合指定硬體需求，且已安裝 Lync Server 註冊機構和轉送伺服器軟體的伺服器。 該伺服器必須將 PSTN 閘道或 SIP 主幹連線至電話服務提供者。 Survivable Branch 伺服器特別針對具有 1000 至 5000 位用者的分支網站所設計。

  - PSTN 閘道和「中繼伺服器」**(選用)。 如需此伺服器及其他伺服器角色的詳細資訊，請參閱[Lync server 2013 中的伺服器角色](lync-server-2013-server-roles.md)。

具有中央網站的可恢復廣域網路 (WAN) 連結的分公司可以使用第三個選項，也就是 PSTN 閘道和中繼伺服器 (選用)。 具有較低彈性連結的分支 office 網站應該使用 Survivable 分支裝置或 Survivable 分支伺服器，這會在廣域網路絡失敗時提供恢復功能。 例如，在已部署 Survivable Branch 裝置或 Survivable Branch 伺服器的網站中，如果將分支網站連接至中央網站的 WAN，使用者仍可撥打及接收企業語音通話。 如需 Survivable 分支裝置、Survivable 分支伺服器及恢復功能的詳細資訊，請參閱規劃檔中的[規劃 Lync server 2013 中的 Enterprise Voice 韌性](lync-server-2013-planning-for-enterprise-voice-resiliency.md)。

</div>

<div>

## <a name="site-topologies"></a>網站拓撲

您的部署必須包含至少一個中央網站，並可以包含零到多個分支網站。 每一個分支網站均隸屬於一個中央網站。 中央網站向分支網站提供 Lync Server 服務，該網站不會在分支網站上的本機主控，例如目前狀態和會議。

如果您有多個網站，您可以將不同網站的前端集區配對在一起，以啟用嚴重損壞修復功能。 如需詳細資訊，請參閱[Lync Server 2013 中的高可用性和嚴重損壞修復支援](lync-server-2013-high-availability-and-disaster-recovery-support.md)。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的伺服器角色](lync-server-2013-server-roles.md)  
[Lync Server 2013 的高可用性和嚴重損壞修復支援](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[在 Lync Server 2013 中規劃 Enterprise Voice 韌性](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


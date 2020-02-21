---
title: Lync Server 2013： 通用媒體旁路選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96c97301221e50873ab53dc06452721c74ed6627
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a>通用媒體旁路 Lync Server 2013 中的選項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-04_

<div>


> [!NOTE]  
> 本主題會假設您已設定好主幹對等端 （公用交換的電話網路 (PSTN) 閘道、 IP PBX 或在網際網路電話語音服務提供者的工作階段邊界控制器 (SBC)） 的媒體旁路的特定網站或服務您想要媒體略過此中繼伺服器。



</div>

除了啟用對等端相關之個別主幹連線的媒體旁路，您也必須通用啟用媒體旁路。 通用媒體旁路設定可以指定媒體旁路永遠嘗試 pstn 通話或媒體旁路所使用的子網路以網路網站與網路地區對應採用 — 類似所執行之動作的通話許可控制，另一個進階的語音功能。 媒體旁路和通話許可控制會同時啟用，然後網路地區、 網路網站，並針對指定的子網路資訊時決定是否要使用媒體旁路時，都會自動會使用通話許可控制。 啟用通話許可控制時，這表示，您不能指定媒體旁路會永遠會嘗試至 PSTN 通話。

本主題說明如何使用 Lync Server 控制台] 及 [Lync Server 管理命令介面在一起進行通用媒體旁路設定。

<div>


> [!NOTE]  
> 使用下列步驟設定媒體旁路時，假設前提是用戶端和中繼伺服器對等端 (例如 PSTN 閘道、IP-PBX 或 SIP 主幹提供者上的 SBC) 之間的連線良好。 如果連結上有頻寬限制，就無法將媒體旁路套用至通話。 媒體旁路不會與每個 PSTN 閘道、IP-PBX 以及 SBC 相互溝通。 Microsoft 已測試一組的 PSTN 閘道與 Sbc 與認證合作夥伴，並已執行一些測試與 Cisco Ip-pbx。 媒體旁路只支援的產品和版本列在 Unified Communications Open Interoperability Program – 在 Lync Server <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>。



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a>後續步驟：選擇通用媒體旁路設定

在針對特定網站或服務對等端的主幹連線啟用媒體旁路後，使用下列內容可執行下列其中一項：

  - [設定媒體旁路以始終略過中繼伺服器的 Lync Server 2013 中](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)所述，一律，啟用媒體旁路。

  - 或者，設定媒體旁路使用網站與地區資訊，[設定媒體旁路使用網站與地區資訊的 Lync Server 2013 中的全域設定](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)中所述。

</div>

<div>

## <a name="see-also"></a>另請參閱


[設定與 Lync Server 2013 中的媒體旁路的主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[關聯子網路與 Lync Server 2013 中的網路網站](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[在 Lync Server 2013 中設定媒體旁路](lync-server-2013-configure-media-bypass.md)  
[媒體旁路和 Lync Server 2013 中的中繼伺服器](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


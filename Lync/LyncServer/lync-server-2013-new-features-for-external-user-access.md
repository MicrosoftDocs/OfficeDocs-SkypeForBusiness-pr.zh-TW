---
title: Lync Server 2013：外部使用者存取的新功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d365c4e32c5eaebbd0368cd85b41be7886a59df
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中外部使用者存取的新功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-17_

Lync Server 2013 引入了新功能，可延伸您使用者的功能與通訊方法。 此外，Lync Server 2013 也會為現有的服務引入變更，以更好地整合及延伸貴組織所提供的服務。 以下是可能會影響您規劃和部署 Lync Server 2013 Edge Server 服務的變更摘要。

  - **支援 ipv6 位址**   Lync server 2013 支援所有 Edge 伺服器服務的 ipv6 位址。 如果您已透過 Windows Server 中的設定提供介面的 IPv6 位址，您可以透過拓撲建立器中的 IP 位址設定，在 Edge 伺服器配置中使用 IPv6 位址。
    
    <div>
    

    > [!IMPORTANT]  
    > 在 Lync Server 2013 中使用 IPv6 位址，取決於貴組織部署的路由器和防火牆中的 IPv6 支援，以及透過網際網路服務提供者提供的支援。

    
    </div>

  - **可擴展訊息和目前狀態通訊協定（XMPP）**   Lync Server 2013 引進了完全整合的 XMPP proxy （部署在 Edge 伺服器上），以及部署在您的前端伺服器上的 XMPP 閘道。 您可以將 XMPP 同盟部署為選用的元件。 新增並設定 XMPP proxy 和 XMPP 閘道，您的 Microsoft Lync 2013 使用者就能將來自 XMPP 合作夥伴的連絡人新增至 [立即訊息（IM）] 和 [目前狀態]。
    
    <div>
    

    > [!NOTE]  
    > 目前，Lync Server 2013 中的 XMPP 服務只會在 Lync 用戶端和 XMPP 的連絡人之間提供立即訊息和目前狀態。

    
    </div>

  - ****    在 lync server 2010 的客戶更新中引入行動用戶端的行動裝置服務在 lync server 2013 中的行動服務可讓您在手機和平板電腦上使用支援 Apple iOS、Android、Windows Phone 或 Nokia 行動裝置的 Microsoft Lync Mobile 用戶端執行此類活動，以傳送和接收立即訊息、查看連絡人及查看目前狀態。 此外，行動裝置支援一些企業語音功能，例如按一下以加入會議、透過工作撥打電話、單一號碼達到、語音信箱及未接來電通知。
    
    <div>
    

    > [!NOTE]  
    > 行動服務會使用部署在您前端伺服器上的反向 proxy 與已發佈的服務。 Edge 伺服器不需要任何變更。

    
    </div>

  - **控制器是一個選用的角色**   ，即在 Lync server 2013 拓撲中，控制器伺服器的角色沒有變更。 它仍會寄存 web 服務、預驗證傳入的使用者要求，並將外部使用者導向其主池中。 將 Director 從建議的角色變更為選用的角色並不會降低主管的價值，但強調減少伺服器數量及其他硬體需求（例如，控制器的硬體負載平衡器）需求，而不需要影響功能和功能。 因為前端伺服器可以執行與主管所提供服務不受影響的相同作業，您也可以選擇性地部署控制器（如果您選擇的話）。 您可以放心地排除主管，讓前端伺服器能夠在其位置提供相同的服務。

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中規劃和設定 IPv6](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[在 Lync Server 2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)  
[在 Lync Server 2013 中規劃可擴展訊息和目前狀態通訊協定（XMPP）同盟](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


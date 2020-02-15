---
title: 外部使用者存取的 Lync Server 2013： 新功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e85c9e83a6dde06c7c091241bea903a3ddd1d813
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中的外部使用者存取的新功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-17_

Lync Server 2013 引進擴充功能與通訊的方法，為您的使用者的新功能。 此外，Lync Server 2013 引進變更至現有的服務，以更妥善地整合，並擴充可供貴組織的服務。 以下是可能會影響規劃的變更摘要。 與部署的 Lync Server 2013 Edge Server 服務。

  - **支援 IPv6 定址**   Lync Server 2013 支援 IPv6 定址的所有 Edge Server 服務。 如果您已透過 Windows Server 中設定介面提供 IPv6 位址，您可以透過在拓撲產生器的 IP 位址設定 Edge Server 設定中使用 IPv6 位址。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 中的 IPv6 位址的使用取決於路由器和防火牆，貴組織部署，以及透過網際網路服務提供者支援的 IPv6 支援。

    
    </div>

  - **可延伸訊息和顯示狀態通訊協定 (XMPP)**   Lync Server 2013 引進 （在 Edge Server 上已部署） 完全整合的 XMPP proxy 及 XMPP 閘道部署在前端伺服器上。 您可部署 XMPP 同盟作為選用元件。 新增及設定 XMPP proxy 及 XMPP 閘道將允許 Microsoft Lync 2013 使用者從 XMPP 為基礎的協力廠商的立即訊息 (IM) 和目前狀態新增連絡人。
    
    <div>
    

    > [!NOTE]  
    > 目前，Lync Server 2013 中的 XMPP 服務僅提供立即訊息和 Lync 用戶端與 XMPP 型連絡人之間的目前狀態。

    
    </div>

  - **行動用戶端行動性服務**   Lync Server 2013 中的行動服務客戶更新 Lync Server 2010 中引進，可讓行動電話上的 Microsoft Lync 行動用戶端和平板電腦裝置使用支援的 Apple iOS、 Android、 Windows Phone 或 Nokia 行動裝置，以執行這類活動傳送和接收立即訊息、 檢視連絡人，以及檢視目前狀態。 此外，行動裝置支援某些 Enterprise Voice 功能，例如按一下以加入會議，從公司撥號，單一數字到達，語音信箱和未接來電通知。
    
    <div>
    

    > [!NOTE]  
    > 行動性服務使用前端伺服器中部署的反向 Proxy 和發佈的服務。 Edge Server 不需要進行任何變更。

    
    </div>

  - **Director 是選用角色**   後未變更的 Lync Server 2013 拓撲中的 Director 伺服器角色。 它仍主控 web 服務、 預先驗證傳入的使用者要求，並指示其主集區的外部使用者。 變更為選用角色從建議角色 Director 不減損 Director 的值，但強調降低伺服器計數，並沒有其他硬體需求 （例如，硬體負載平衡器的 Director） 需求危害特色與功能。 因為前端伺服器可以做為不會影響所提供的服務與 Director 的相同工作，您可以選擇性地部署 Director，如果您選擇。 安全地可以排除 Director 與前端伺服器將會提供相同的服務，在其位置的信賴度。

<div>

## <a name="see-also"></a>另請參閱


[規劃和設定 Lync Server 2013 中的 IPv6](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[規劃 Lync Server 2013 中的外部使用者存取](lync-server-2013-planning-for-external-user-access.md)  
[可延伸訊息與顯示狀態通訊協定 (XMPP) 同盟 Lync Server 2013 中規劃](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


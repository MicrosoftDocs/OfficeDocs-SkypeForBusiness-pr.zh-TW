---
title: Lync Server 2013：外部使用者存取的概覽
description: Lync Server 2013：外部使用者存取的概述。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of external user access
ms:assetid: 97aded6c-5fa3-4225-95a6-9ad094d61654
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398775(v=OCS.15)
ms:contentKeyID: 48184934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2900dde457da34c4438892878ae7ddb4f74723a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562889"
---
# <a name="overview-of-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中的外部使用者存取的概覽

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

在本檔中，我們使用「 *外部使用者* 」來定義與您的 Lync Server 2013 和 lync 2013 使用者從防火牆外通訊的大型使用者類別。 您可以授權以與內部使用者通訊 Lync Server 2013 的外部使用者 (也就是說，從) 防火牆內登入 Lync Server 的使用者可以包含下列專案：

  - **遠端使用者**    從防火牆外登入 Lync Server 之組織的使用者。

  - 同盟**使用者**    具有信任之客戶或夥伴組織之帳戶的使用者，例如 Lync Server 2010、Lync Server 2013 或 Office 通訊伺服器 2007 R2。 同盟使用者也可以是使用可延伸訊息和顯示狀態通訊協定 (XMPP) 透過前端伺服器或集區上的 Edge Server 和 XMPP 閘道上的 XMPP proxy 的方式來定義之夥伴組織的成員。 已定義的信任關係（稱為「同盟」）與 Active Directory 網域服務信任關聯或相互依存。
    
    <div>
    

    > [!NOTE]  
    > AOL 和 Yahoo！的循環結束日期為2014年6月 已宣告。 如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。

    
    </div>

  - **公用立即訊息連線使用者**    您的使用者透過公用立即訊息聯機服務建立的連絡人 (Windows Live、Yahoo\! 和 AOL) 。

  - 行動**使用者**    使用智慧型電話或 tablet 執行 Lync 行動用戶端之組織成員的使用者，會登入您的內部部署，而且可以與其他類別的使用者通訊。 行動使用者使用透過反向 proxy 發佈的行動服務來存取內部部署。 如需 Lync Mobile 可用功能的詳細資訊，請參閱中的行動用戶端比較表 [https://go.microsoft.com/fwlink/p/?LinkID=234777](https://go.microsoft.com/fwlink/p/?linkid=234777) 。

  - **匿名使用者**    在您組織的 Active Directory 網域服務或支援的同盟網域中沒有使用者帳戶的使用者，但已接收到在內部部署會議中遠端加入邀請的使用者。

您的 edge 部署提供下列通訊類型的外部存取：

  - **IM 和目前狀態**    授權的外部使用者可以參與 IM 交談和會議，也可以取得彼此的狀態資訊。 公用 IM 服務提供者的使用者可以與組織中的個別 Lync Server 使用者參與 IM 交談，存取顯示狀態資訊，但不能使用 Lync Server 參與 IM 多方會議。 完全對等通訊。 公用 IM 服務提供者的使用者不支援檔案傳輸，而且對等通訊中的音訊/影片支援 Windows Messenger 2011 使用者，但不適用於公用 IM 服務提供者的其他使用者。
    
    支援 SIP 和 XMPP 通訊協定。 若要提供服務以供 XMPP，請參閱 [在 Lync Server 2013 中規劃 SIP、XMPP 同盟及公用立即訊息](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)。

  - **Web 會議**    授權的外部使用者可以加入您的 Lync Server 部署上的會議。 遠端使用者、同盟使用者和匿名使用者可以啟用網路會議，但公用 IM 使用者無法參與會議。 視您選取的選項而定，啟用 web 會議的使用者可以參與桌面和應用程式共用，也可以充當會議召集人或簡報者。

  - **會議 A/V**    已授權的外部使用者可以參與您的 Lync Server 部署主控的音訊和影片會議。 對等通訊中的音訊/影片支援 Windows Messenger 2011 使用者，但不適用於公用 IM 服務提供者的其他使用者。

若要控制通訊，您可以設定一或多個原則，以定義組織內部和外部使用者之間的通訊方式。 您也可以為個別內部使用者或特定類型的外部使用者設定設定並套用原則，以控制與外部使用者的通訊。

Lync Server 2013 用來提供外部存取的角色：

**Edge Server**    Edge Server 是伺服器或伺服器集區，可執行服務，以允許外部存取 IM 及目前狀態、會議、音訊/影片及其他媒體 (例如，檔案傳輸) 服務。 您也可以將 Edge Server 設定為與其他 Lync Server 或 Office 通訊伺服器 2007 R2 部署及其他 XMPP 部署的同盟。 透過 Edge Server 啟用並設定選用的公用 IM 連線功能。

**Director**    Director 是執行 Lync Server 2013 Director 角色的選用伺服器或伺服器集區，可對使用者的首頁前端伺服器或前端集區執行預先驗證使用者要求和路由要求，但不會家用任何使用者帳戶。

**反向 Proxy**    反向 proxy 是特殊伺服器的一般術語，可用來發佈內部網路上的資源，並從已發佈的資源中取得用戶端的資訊。 Lync Server 2013 使用反向 proxy 來發佈許多功能，例如會議會議、會議加入位置、通訊錄、通訊群組清單展開、下載會議內容、裝置更新、行動服務等等。 可以使用任何可符合發佈必要資源位置之需求的反向 proxy。 Microsoft Forefront 威脅管理閘道 (TMG) 2010 是一個範例，用來示範必要的發行規則，但不需要 Forefront TMG 2010。

<div>


> [!IMPORTANT]  
> Lync Server 2013 同時支援 IPv4 和 IPv6。 Windows Server &nbsp; 2008 &nbsp; R2、windows server 2012 及 Windows Server 2012 R2 使用雙重堆疊，可以同時使用 IPv4 和 IPv6。 這一點很重要，因為部署的過渡性質從 IPv4 移至 IPv6。 在某些情況下可以支援 IPv4，在某些情況下，您可以在部署的其他區域中使用 IPv6。 這對網際網路和內部部署的考慮尤為重要。 外部用戶端必須透過反向 proxy 進行通訊，才能使用行動、會議、通訊錄下載等服務。 目前，Forefront 威脅管理閘道2010和 Internet Security 和加速度 Server 2006 不支援 IPv6 定址，不論其部署所在的作業系統版本為何。 您必須相對於使用 IPv6 和 IPv4 （與外部用戶端有關）進行對應計畫。



</div>

</div>

<span> </span>

</div>

</div>

</div>


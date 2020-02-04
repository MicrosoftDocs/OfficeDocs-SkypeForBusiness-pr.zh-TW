---
title: Lync Server 2013：外部使用者存取概觀
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
ms.openlocfilehash: 1007dfb330aaa21dbac269f606102c51712c9bf7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中的外部使用者存取概觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

在本檔中，我們使用「*外部使用者*」來定義與您的 Lync Server 2013 和 lync 2013 使用者在防火牆外通訊的大型使用者類別。 您可以授權用來與內部使用者（也就是從防火牆內登入 Lync Server 的使用者）傳達 Lync Server 2013 的外部使用者可能包含下列各項：

  - **** 從防火牆外部登入 Lync Server 的組織使用者。   

  - ****    將帳戶與信任的客戶或合作夥伴組織（例如 lync server 2010、lync server 2013 或 Office 通訊伺服器 2007 R2）共同擁有的同盟使用者。 同盟使用者也可以使用可擴展訊息和目前狀態通訊協定（XMPP），透過 Edge 伺服器上的 XMPP proxy 以及前端伺服器或池中的 XMPP 閘道，來成為已定義合作夥伴組織的成員。 已定義信任關係（稱為同盟）不與 Active Directory 網域服務信任關係相關。
    
    <div>
    

    > [!NOTE]  
    > AOL 和 Yahoo！的存留期結束日期為2014年6月 已公佈。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。

    
    </div>

  - ****    您的使用者透過公用立即訊息聯機服務（Windows Live、Yahoo）建立的公用立即訊息連線使用者連絡人\! 和 AOL）。

  - ****    您組織成員的行動使用者使用者是使用智慧手機或平板電腦來執行 Lync 行動用戶端，且能夠與其他使用者類別進行通訊。 行動使用者使用由反向 proxy 發佈的行動服務來存取內部部署。 如需 Lync Mobile 可用功能和功能的詳細資訊，請參閱的行動用戶端[http://go.microsoft.com/fwlink/p/?LinkID=234777](http://go.microsoft.com/fwlink/p/?linkid=234777)比較表。

  - ****    在您組織的 Active Directory 網域服務或支援的聯盟網域中沒有使用者帳戶的匿名使用者使用者，但在內部部署會議中收到遠端參與邀請的使用者。

您的 edge 部署提供下列通訊類型的外部存取：

  - **Im 和目前狀態**   授權的外部使用者可以參與 im 交談和會議，而且他們可以取得其他人目前狀態的相關資訊。 公用 IM 服務提供者的使用者可以與組織中的個別 Lync Server 使用者進行 IM 交談，並存取目前狀態資訊，但他們無法使用 Lync Server 參與 IM 多方會議。 它是完全對等通訊。 公用 IM 服務提供者的使用者不支援檔案傳輸，而且對等通訊中的音訊/影片支援 Windows Messenger 2011 使用者，但不適用於公用 IM 服務提供者的其他使用者。
    
    支援 SIP 與 XMPP 通訊協定。 若要提供 XMPP 的服務，請參閱[在 Lync Server 2013 中規劃 SIP、XMPP 同盟及公用立即訊息](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)。

  - ****    已授權外部使用者的網路會議可參與您的 Lync Server 部署所託管的會議。 您可以在遠端使用者、同盟使用者和匿名使用者參與網路會議，但公用 IM 使用者無法參與會議。 根據您選取的選項，網路會議的使用者可以參與桌面與應用程式共用，也可以充當會議召集人或簡報者。

  - **A/V 會議**   授權的外部使用者可以參與 Lync Server 部署主機的音訊和視訊會議。 Windows Messenger 2011 使用者支援對等通訊中的音訊/視頻，但不適用於公用 IM 服務提供者的其他使用者。

若要控制通訊，您可以設定一或多個原則，以定義組織內部和外部的使用者彼此通訊的方式。 您也可以針對個別內部使用者或特定類型的外部使用者設定設定並套用原則，以控制與外部使用者的通訊。

Lync Server 2013 用來提供外部存取的角色：

**Edge 伺服器**   ： edge 伺服器是一種伺服器或伺服器池，可執行允許外部存取 IM 和目前狀態、會議、音訊/影片，以及其他媒體（例如，檔案傳輸）服務的服務。 您也可以將 Edge 伺服器設定為與其他 Lync Server 或 Office 通訊伺服器 2007 R2 部署以及其他 XMPP 部署進行聯盟。 您可以透過 Edge 伺服器啟用並設定選用的公用 IM 連線功能。

**主管**   ：控制器是執行 Lync server 2013 主管角色的選用伺服器或伺服器池，該角色會預先驗證使用者要求，並將要求傳送給使用者的家用前端伺服器或頂層端池，但不會家用任何使用者帳戶。

**反向**proxy 是特殊伺服器的一般期限，可發佈內部網路上可用的資源，並從已發佈的資源取得用戶端的資訊。    Lync Server 2013 使用反向 proxy 來發佈許多功能，例如會議會議、會議加入位置、通訊錄、通訊群組清單展開、下載會議內容、裝置更新、行動服務等等。 任何可符合發佈必要資源位置需求的反向 proxy 都可以使用。 Microsoft Forefront 威脅管理閘道（TMG）2010是用來示範必要發佈規則的範例，但不需要 Forefront TMG 2010。

<div>


> [!IMPORTANT]  
> Lync Server 2013 支援 IPv4 與 IPv6。 Windows Server&nbsp;2008&nbsp;r2、Windows Server 2012 和 Windows server 2012 R2 使用可同時使用 IPv4 與 IPv6 的雙堆疊。 這很重要，因為部署從 IPv4 轉移到 IPv6 的過渡性質。 在某些情況下，可能會支援 IPv4，在部署的其他區域中，您可以使用 IPv6。 這在網際網路和內部部署的考慮尤為重要。 外部用戶端必須透過反向 proxy 進行通訊，才能使用行動、會議、通訊錄下載及其他服務。 目前，Forefront 威脅管理閘道2010和 Internet 安全性和加速伺服器2006不支援 IPv6 定址，無論它們的版本為何都要部署。 您必須規劃與與外部用戶端相關的 IPv6 和 IPv4 使用方式。



</div>

</div>

<span> </span>

</div>

</div>

</div>


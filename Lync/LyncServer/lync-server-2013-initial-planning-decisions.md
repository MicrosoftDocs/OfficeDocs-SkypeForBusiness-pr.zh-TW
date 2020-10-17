---
title: Lync Server 2013 初始規劃決策
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Initial planning decisions
ms:assetid: cbaa5cb3-2b00-4b9f-952d-986a0c9f160b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398855(v=OCS.15)
ms:contentKeyID: 48185651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fdc9b9e2494078a8db4b524e9ffb6b2794c545d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512570"
---
# <a name="initial-planning-decisions-for-lync-server-2013"></a>Lync Server 2013 的初始規劃決策

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

規劃程式的第一個階段是決定您的組織所需的 Lync Server 工作負載和主要功能。

1.  **您需要內部部署或線上部署嗎？**    Lync Server 支援這兩種部署案例。 如需作出這項決策的詳細資訊，請參閱本節前面的 [決定如何部署 Lync Server 2013](lync-server-2013-deciding-how-to-deploy-microsoft-lync.md)。

2.  **您需要實體或虛擬化拓撲嗎？**    Lync Server 支援實體和虛擬化拓撲中的所有工作負載和伺服器角色。 實體和虛擬拓朴的使用者容量與擴充性可能不同。 如需詳細資訊，請參閱 [在虛擬伺服器上執行 Lync Server 2013](lync-server-2013-running-lync-server-on-virtual-servers.md)。

3.  **立即訊息* (IM) *和目前*狀態*，都一定會啟用。**    在任何 Lync Server 部署中，預設會安裝立即訊息 (IM) 和目前狀態工作負載。 IM 可讓您的使用者與即時文字郵件進行通訊，而顯示狀態可讓他們查看網路上其他使用者的狀態。 使用者的目前狀態會提供資訊，以協助其他人決定是否應嘗試聯繫使用者，以及其含義。 如需詳細資訊，請參閱規劃檔中的 [規劃 Lync Server 2013 中的前端伺服器、立即訊息及顯示狀態](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md) 。

4.  **您是否要部署任何會議模式？**    會議是 Lync Server 的另一項核心功能。 支援多種會議模式。 您可以選擇部署所有支援的會議類型，或是只部署部分會議。 *Web 會議* 可讓使用者看到檔案，例如所呈現的 Microsoft PowerPoint 簡報圖形程式所建立的投影片。 *應用程式共用* 可讓使用者即時共用全部或部分的桌面。 透過 *A/V 會議*，使用者可以在會議和對等通訊) 中新增音訊 (及可能的影片。 *電話撥入式會議* 可讓使用者使用標準 PSTN 電話，加入組織中所主控之會議的音訊部分。 如需詳細資訊，請參閱規劃檔中的在 [Lync Server 2013 中規劃會議](lync-server-2013-planning-for-conferencing.md) 。
    
    在 Lync Server 2013 中，如果您要部署 Web 會議，也必須規劃與 Office Web Apps Server 整合，以在會議中啟用 Powerpoint 共用和查看。 如需詳細資訊，請參閱設定 [Office Web Apps Server 和 Lync server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

5.  **如果您部署 A/V 會議，也應監視這些會議的音訊品質。**    許多因素會影響 Lync Server A/V 會議的音訊和視頻品質。 透過使用監控，您可以監視 A/V 的通話和會議品質。 您可以偵測影響媒體質量的問題，並確定您的使用者可以獲得最佳的媒體體驗。 如需詳細資訊，請參閱 [在 Lync Server 2013 中規劃監控](lync-server-2013-planning-for-monitoring.md)。

6.  **您的 IM、目前狀態及會議服務器是否需要高可用性？**    如果您在提供 IM、目前狀態和會議功能的網站上只有一部伺服器，當該伺服器停機時，使用者的生產力會大大地影響。 透過為這些功能部署至少三台伺服器的 Enterprise Edition *集* 區，即使無法使用伺服器，也可讓 Lync Server 繼續正常運作所有這些功能。
    
    其他有5000或更少使用者需要高可用性的組織的另一個選項是部署兩部執行 Lync Server Standard Edition 的伺服器，並將這些伺服器結合在一起。 如需詳細資訊，請參閱 [在 Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

7.  **您是否想要執行嚴重損壞修復選項？**    如果您有兩個資料中心，且想要讓您的使用者能夠繼續運作，而如果一個資料中心的所有伺服器或多部伺服器都在停機，您可以在部署伺服器時考慮使用災害復原。 針對此部署，您可以將一個資料中心的伺服器集區與另一個資料中心的對應集區配對。 如果有一個資料中心停機，該配對中的另一個集區就可以服務于兩個集區中的使用者，最少中斷服務。 如需詳細資訊，請參閱 [在 Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

8.  **您是否要讓您的使用者能夠與外部使用者通訊及共同作業？**    啟用與外部使用者的通訊及共同作業，可增加您在 Lync Server 中的投資回報率。 這可讓貴組織的使用者在 Lync Server 功能上受益，甚至是在組織的防火牆外工作時。 您也可以與您的合作夥伴或執行 Lync Server 之客戶組織同盟。 如此一來，您的使用者和同盟合作夥伴使用者可以輕鬆地傳送和接收 IM 訊息、邀請對方參加會議，以及彼此查看對方的狀態。 此外，您的使用者也可以使用電子郵件訊息，將特定外部使用者邀請他們組織的會議。 如需詳細資訊，請參閱 [在 Lync Server 2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)。

9.  **您要部署 Enterprise Voice？**    *Enterprise voice* 是 Lync Server 所提供) 方案 VoIP 的 VOICE over IP (。 它為傳統 PBX 型電話語音提供了極具吸引力的替代方案。 Enterprise Voice 可讓使用者透過按一下 Outlook 或 Lync Server 中的連絡人，撥打其電腦或 VoIP 電話。 它們可以透過 IP 網路將電話從電腦移至電腦、電腦到電話，或從電話移至電腦。 使用者可在其電腦上享受所有的通訊選項-語音、電子郵件、IM 和會議，並加以整合。 如需詳細資訊，請參閱規劃檔中的 [規劃 Lync Server 2013 中的 Enterprise Voice](lync-server-2013-planning-for-enterprise-voice.md) 。

10. **如果您部署企業語音，您也應該監視這些通話的音訊品質。**    建議您使用監控功能，以確保企業語音通話的音訊品質（如果您部署企業語音）。 如需詳細資訊，請參閱 [在 Lync Server 2013 中規劃監控](lync-server-2013-planning-for-monitoring.md)。

11. **出於相容性目的，您是否需要封存 IM 內容或會議內容？**    如果您的組織出於相容性目的而必須封存 IM 內容或會議內容，您可以部署封存。 如需詳細資訊，請參閱 [在 Lync Server 2013 中規劃](lync-server-2013-planning-for-archiving.md)封存。

12. **您想要部署持續性聊天嗎？**    如果您想要讓您的使用者有可在一段時間後持續的即時交談，您可以部署持續聊天。 如需詳細資訊，請參閱 [在 Lync server 2013 中規劃 Persistent Chat Server](lync-server-2013-planning-for-persistent-chat-server.md)。

13. **是否已部署 Microsoft Exchange？**    如果您的組織使用 Microsoft Exchange Server 進行電子郵件服務，您可以啟用多種功能，以加強 Lync Server 和 Microsoft Exchange Server 的有用性。 這些功能（稱為 Exchange 整合通訊 (UM) ）包括讓使用者能夠接收語音信箱通知，以及收聽 Outlook 或 Outlook Web Access 中的語音信箱、使用電話存取其 Microsoft Exchange 信箱，以及在其 Microsoft Exchange 信箱中接收傳真。 此外，如果您已部署 Exchange 2013，您可以整合兩個系統之間使用者的連絡人存放區，並使用 Exchange 來儲存較高解析度的連絡人相片，以及整合電子郵件和立即訊息的封存。 如需詳細資訊，請參閱 [規劃 Exchange Server 與 Lync server 的整合 2013](lync-server-2013-planning-for-exchange-server-integration.md)。

14. **您的組織中有分支辦公室嗎？**    如果您的組織有分支辦事處，Lync Server 支援各種方式來支援它們，並確保其語音功能和其他功能的復原能力。 特別是，在分公司沒有資料中心的彈性 WAN 連結時，您可以安裝 Survivable Branch 裝置或 Survivable Branch 伺服器以維護 Enterprise Voice 支援。廣域網路) 連結 (會中斷。 如需詳細資訊，請參閱 [在 Lync Server 2013 中規劃分支網站語音恢復功能](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013 初始規劃決策
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Initial planning decisions
ms:assetid: cbaa5cb3-2b00-4b9f-952d-986a0c9f160b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398855(v=OCS.15)
ms:contentKeyID: 48185651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dd1359e27f6869dab1ead38da3716135a2468ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="initial-planning-decisions-for-lync-server-2013"></a>Lync Server 2013 的初始規劃決策

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

規劃程式的第一個部分是決定您要用於貴組織的 Lync 伺服器工作負載和主要功能。

1.  **您想要內部部署或線上部署嗎？**   Lync Server 支援這兩種部署案例。 如需作出此決定的詳細資訊，請參閱此區段前面的[決定如何部署 Lync Server 2013](lync-server-2013-deciding-how-to-deploy-microsoft-lync.md)

2.  **您想要使用實體或虛擬化拓撲嗎？**   Lync Server 支援物理與虛擬化拓撲中的所有工作負載和伺服器角色。 使用者的容量和可伸縮性在物理與虛擬拓朴之間可能有所不同。 如需詳細資訊，請參閱[在虛擬伺服器上執行 Lync Server 2013](lync-server-2013-running-lync-server-on-virtual-servers.md)。

3.  **[立即訊息 *（IM）* ] 和 [目前*狀態*] 都是啟用的。**   在任何 Lync Server 部署中，立即訊息（IM）與目前狀態的工作負荷預設都會安裝並啟用。 IM 可讓您的使用者與即時文字訊息通訊，並讓他們能夠查看網路上其他使用者的狀態。 使用者的目前狀態會提供資訊，協助其他人決定是否應該嘗試與使用者聯繫，以及有何意義。 如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的 [規劃前端伺服器]、[立即訊息] 和](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)[目前狀態]。

4.  **您想要部署任何會議模式嗎？**   [會議] 是 Lync Server 的另一個核心功能。 支援數種會議模式。 您可以選擇部署所有受支援的會議類型，或只是其中一部分。 *網路會議*可讓使用者查看檔案，例如使用 Microsoft PowerPoint 簡報圖形程式建立的投影片組。 [*應用程式共用*] 可讓使用者即時共用全部或部分的桌面。 使用*A/V 會議*，使用者可以在會議和對等通訊中新增音訊（也可能是影片）。 *電話撥入式會議*可讓使用者使用標準的 PSTN 電話來加入您組織內所託管之會議的音訊部分。 如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 規劃會議](lync-server-2013-planning-for-conferencing.md)。
    
    在 Lync Server 2013 中，如果您要部署 Web 會議，您也必須規劃與 Office Web Apps Server 整合，以便在會議中啟用 Powerpoint 共用及查看。 如需詳細資訊，請參閱設定[與 Office Web Apps server 和 Lync server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

5.  **如果您要部署 A/V 會議，您也應該監視這些會議的音訊品質。**   許多因素都會影響 Lync Server A/V 會議的音訊和視頻品質。 透過使用監視，您可以監控通話和會議的 A/V 品質。 您可以偵測到影響媒體質量的問題，並確保您的使用者具備最佳的媒體體驗。 如需詳細資訊，請參閱[在 Lync Server 2013 中進行監視規劃](lync-server-2013-planning-for-monitoring.md)。

6.  **您是否想要為 IM、目前狀態及會議服務器提供高可用性？**   如果您在提供 IM、目前狀態與會議功能的網站上只有一個伺服器，則如果該伺服器已停機，您的使用者的生產力將會受到極大的影響。 透過為這些函數部署至少三台伺服器的企業版文檔*庫*，即使伺服器無法使用，也可以讓 Lync Server 繼續正常運作。
    
    如果組織使用的是5000或更少的使用者，而想要高可用性，請將兩個伺服器部署在運行 Lync Server 標準版，並將這些伺服器搭配在一起。 如需詳細資訊，請參閱[在 Lync Server 2013 中規劃高可用性和災害復原](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

7.  **您是否需要災害復原選項？**   如果您有兩個資料中心，且想要讓您的使用者能夠在單一資料中心的所有伺服器或多個伺服器都在使用時繼續運作，您可以使用災害復原來部署伺服器。 針對此部署，您可以將一個資料中心的伺服器池與另一個資料中心的對應池進行配對。 如果一個資料中心出現停機，該配對中的另一個池就可以使用最小的服務中斷來服務于兩個池中的使用者。 如需詳細資訊，請參閱[在 Lync Server 2013 中規劃高可用性和災害復原](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

8.  **您想要讓您的使用者與外部使用者進行通訊及共同作業嗎？**   啟用與外部使用者的通訊與共同作業，可增加您在 Lync Server 中的投資回報。 這可讓貴組織的使用者能從 Lync Server 功能獲益，即使他們在組織的防火牆以外的工作。 您也可以與您的合作夥伴或執行 Lync Server 的客戶組織聯盟。 如此一來，您的使用者與同盟合作夥伴使用者就能輕鬆地傳送及接收 IM 訊息、邀請對方加入會議，以及相互查看彼此的目前狀態。 此外，您的使用者也可以使用電子郵件訊息，邀請特定外部使用者加入他們組織的會議。 如需詳細資訊，請參閱[在 Lync Server 2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)。

9.  **您想要部署企業語音嗎？**    *企業語音*是 Lync Server 所提供的 [語音 over IP （VoIP）] 解決方案。 它為傳統的以 PBX 為基礎的電話提供了極具吸引力的替代方案。 企業語音可讓使用者透過按一下 Outlook 或 Lync Server 中的連絡人，將呼叫從他們的電腦或 VoIP 撥打電話。 它們可將來自電腦的電話撥打電話給電腦、電腦到電話，或撥打電話給電腦。 使用者從其電腦上的所有通訊選項（語音、電子郵件、IM 及會議）都有好處。 如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的企業語音規劃](lync-server-2013-planning-for-enterprise-voice.md)。

10. **如果您要部署企業語音，您也應該監視這些通話的音訊品質。**   如果您部署企業語音，我們建議您使用 [監視] 來確保企業語音通話的音訊品質。 如需詳細資訊，請參閱[在 Lync Server 2013 中進行監視規劃](lync-server-2013-planning-for-monitoring.md)。

11. **您是否需要封存 IM 內容或會議內容以進行合規性用途？**   如果您的組織必須封存 IM 內容或會議內容以進行合規性用途，您可以部署封存。 如需詳細資訊，請參閱[在 Lync Server 2013 中進行存檔規劃](lync-server-2013-planning-for-archiving.md)。

12. **您想要部署持續聊天嗎？**   如果您想要讓您的使用者擁有可在一段時間內保留的即時交談，您可以部署持續聊天。 如需詳細資訊，請參閱[在 Lync server 2013 中規劃持久聊天伺服器](lync-server-2013-planning-for-persistent-chat-server.md)。

13. **您是否已部署 Microsoft Exchange？**   如果您的組織使用 Microsoft Exchange Server 進行其電子郵件服務，您可以啟用多種功能，加強 Lync Server 和 Microsoft exchange Server 的有用性。 這些功能（稱為 Exchange 整合通訊（UM））包括讓使用者接收語音信箱通知，以及聆聽來自 Outlook 或 Outlook Web Access 的語音信箱、使用電話存取其 Microsoft Exchange 信箱，以及接收傳真其 Microsoft Exchange 信箱。 此外，如果您已部署 Exchange 2013，您可以在兩個系統之間整合使用者的連絡人存放區，使用 Exchange 來儲存較高解析度的連絡人相片，以及整合電子郵件和立即訊息的存檔。 如需詳細資訊，請參閱[規劃與 Lync server 2013 整合 Exchange Server](lync-server-2013-planning-for-exchange-server-integration.md)的功能。

14. **您的組織中是否有分支機搆？**   如果您的組織有分支辦公室，Lync Server 支援多種不同的方式來支援它們，並確保其可復原語音及其他功能。 特別是在沒有資料中心彈性 WAN 連結的分支辦公室中，您可以安裝 Survivable 分支裝置或 Survivable 分支伺服器，以維持 [廣域網路（WAN）] 連結的功能。 如需詳細資訊，請參閱[Lync Server 2013 中的分支網站語音復原規劃](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。

</div>

<span> </span>

</div>

</div>

</div>


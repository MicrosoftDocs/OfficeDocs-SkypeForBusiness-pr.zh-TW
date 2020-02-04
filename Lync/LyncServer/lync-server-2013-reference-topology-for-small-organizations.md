---
title: 適用于小型組織的 Lync Server 2013 參考拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e0171d9678d5d890cf4ecb81f6de25f9b558b05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a>小型組織中 Lync Server 2013 的參照拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

小型組織的參考拓朴顯示如何只部署三台伺服器來執行 Lync Server，以部署強健、高可用性的解決方案。

**小型組織的參照拓撲**

![部署三個伺服器圖表的參考拓撲](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "部署三個伺服器圖表的參考拓撲")

  - **部署這個組織的一組標準版伺服器**   在其中央網站上有4000使用者。 組織已部署兩個標準版伺服器並成對搭配，以啟用高可用性和災害復原。 每個伺服器住房2000使用者，但所有使用者的相關資訊都會在兩個伺服器之間同步處理。 如果其中一個是關閉的，系統管理員可以將這些使用者的服務容錯移轉到其他伺服器，並將使用者的中斷降至最低。 如需有關 Lync Server 2013 中高可用性與災害復原功能的詳細資訊，請參閱[在 Lync server 2013 中規劃高可用性和災難](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)復原。

  - **建議使用 Edge 伺服器部署。**   雖然內部 IM、目前狀態與會議不需要部署邊緣伺服器，但我們建議您即使小型部署也一樣。 您可以部署 Edge 伺服器來將您的 Lync 伺服器投資最大化，為目前組織防火牆以外的使用者提供服務。 其優點包括下列各項：
    
      - 貴組織的使用者可以使用 Lync Server 的功能（如果他們在家中或在路上）。
    
      - 您的使用者可以邀請外部使用者參與會議。
    
      - 如果您有合作夥伴、廠商或客戶組織，且使用 Lync Server，您可以建立與該組織的*聯盟關聯*。 接著，您的 Lync Server 部署會辨識來自該同盟組織的使用者，以更好的方式共同作業。
    
      - 您的使用者可以與公用 IM 服務的使用者交換立即訊息，包括下列任一或所有專案： Windows Live、AOL、Yahoo\!和 Google 交談。 您可能需要使用這些服務的公用 IM 連線的個別授權。
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。 擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟 信使，直到服務關閉日期為止。 AOL 和 Yahoo！的存留期結束日期為2014年6月 已公佈。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</P>
        > <LI>
        > <P>PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權 名單. Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</P>
        > <LI>
        > <P>Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。 與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。 您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</P></LI></UL>

        
        </div>

  - **分支網站的留存能力。**   這個組織正在執行 Lync Server 企業語音功能的試驗程式。 有些使用者使用 Lync Server 作為其唯一的語音方案。 有些語音試驗使用者位於分支網站上。 分支網站沒有可靠的廣域網路（WAN）連結到中央網站，所以會在該處部署 Survivable 分支裝置。 在已部署的情況下，如果 WAN 連結關閉，分支網站上的使用者仍可撥打及接聽電話（在組織和 PSTN 通話中的呼叫）、擁有語音信箱功能，以及與雙方的立即訊息（IM）進行通訊。 使用者也可以在 WAN 連結無法使用時進行驗證。

  - **Exchange UM 部署。** 這個參照拓撲包含 Exchange 整合通訊（UM）伺服器，該伺服器會執行 Microsoft Exchange Server，而不是 Lync Server。
    
    如需有關 Exchange UM 的詳細資訊，請參閱規劃檔中的 lync server [2013 中的 Exchange 整合訊息整合規劃](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)（ [lync server 2013 中的託管 exchange](lync-server-2013-hosted-exchange-unified-messaging-integration.md)整合訊息整合）。

  - **Office Web Apps 伺服器。** 我們建議您在使用 Web 會議的每一個組織中部署 Office Web Apps Server 或 Office Web Apps 伺服器群。 Office Web Apps 伺服器可讓 PowerPoint 投影片呈現在網路會議中。 如需詳細資訊，請參閱設定[與 Office Web Apps server 和 Lync server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

</div>

<span> </span>

</div>

</div>

</div>


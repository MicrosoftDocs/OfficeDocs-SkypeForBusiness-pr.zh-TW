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
ms.openlocfilehash: 68163756f2c2153d1e164999532bc6265400ac5b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536730"
---
# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a>小型組織中 Lync Server 2013 的參考拓撲

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

「小型組織」的參考拓撲顯示如何只部署三台執行 Lync Server 的伺服器，來部署強大且高可用性的解決方案。

**小型組織的參考拓撲**

![部署三個伺服器圖表的參考拓撲](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "部署三個伺服器圖表的參考拓撲")

  - 已**部署**     的 Standard Edition 伺服器對此組織在其中央網站有4000使用者。 組織已部署兩個 Standard Edition 伺服器，並將其配對，以啟用高可用性和嚴重損壞修復。 每個伺服器的住宅2000使用者，但在兩部伺服器之間會同步處理所有使用者的相關資訊。 如果有一項關機，系統管理員可以將其他伺服器的使用者容錯移轉到其他伺服器，並將使用者中斷降至最低。 如需 Lync Server 2013 中高可用性和嚴重損壞修復功能的相關資訊，請參閱 [在 Lync server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

  - **建議使用 Edge Server 部署。**    雖然內部 IM、目前狀態和會議不需要部署 Edge Server，但我們建議您即使小型部署也是一樣。 您可以部署 Edge Server，將服務提供給目前組織防火牆以外的使用者，以達到最大的 Lync 伺服器投資。 優點包括下列各項：
    
      - 您組織的使用者可以使用 Lync Server 功能（如果他們在家中運作或是在旅途中外出）。
    
      - 您的使用者可以邀請外部使用者參與會議。
    
      - 如果您有也使用 Lync Server 的合作夥伴、廠商或客戶組織，您可以建立與該組織的同盟 *關聯* 。 然後，您的 Lync 伺服器部署會辨識來自該同盟組織的使用者，以改善合作。
    
      - 您的使用者可以與公用 IM 服務的使用者交換立即訊息，包括下列任何或所有專案： Windows Live、AOL、Yahoo \! 和 Google 交談。 使用這些服務的公用 IM 連線可能需要個別授權。
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 ( 「PIC USL」 ) 不再提供購買新的或更新的協定。 具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟 信使直到服務關閉日期。 AOL 和 Yahoo！的循環結束日期為2014年6月 已宣告。 如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</P>
        > <LI>
        > <P>PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權 信使。 Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</P>
        > <LI>
        > <P>Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。 與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。 隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</P></LI></UL>

        
        </div>

  - **分支網站留存能力。**    此組織正在執行 Lync Server Enterprise Voice 功能的試驗程式。 有些使用者使用 Lync Server 作為其唯一的語音方案。 有些語音試驗使用者位於分支網站。 分支網站沒有可靠的廣域網路絡 (WAN) 連結至中央網站，因此會在該處部署 Survivable 分支裝置。 在部署此功能的情況下，如果 WAN 連結停機，分支網站上的使用者仍可撥打和接聽通話 (組織中的呼叫和 PSTN 通話) 、具有語音信箱功能，以及透過兩方立即訊息 (IM) 進行通訊。 無法使用 WAN 連結時，也可以驗證使用者。

  - **Exchange UM 部署。** 此參考拓撲包含 Exchange 整合通訊 (UM) Server，它會執行 Microsoft Exchange Server，而不是 Lync Server。
    
    如需 Exchange UM 的詳細資訊，請參閱規劃檔中的在 lync server [2013 中規劃 Exchange 整合通訊整合](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 和 [主控 Exchange 整合通訊2013整合](lync-server-2013-hosted-exchange-unified-messaging-integration.md) 。

  - **Office Web Apps Server。** 建議您在使用 Web 會議的每家組織中部署 Office Web Apps Server 或 Office Web Apps Server 伺服器陣列。 Office Web Apps Server 可以在 Web 會議中呈現 PowerPoint 的投影片。 如需詳細資訊，請參閱設定 [Office Web Apps Server 和 Lync server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

</div>

<span> </span>

</div>

</div>

</div>


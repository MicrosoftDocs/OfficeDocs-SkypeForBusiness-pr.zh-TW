---
title: Lync Server 2013：行動性的拓撲和元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ccce5823e997cafc5e8c8e7555df18bc67d1fe6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a>Lync Server 2013 中行動性的拓撲和元件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

為了支援行動裝置上的 Lync 行動應用程式，Lync Server 2013 提供三種服務： Lync Server 2013 Mcx 行動服務、Lync Server 2013 自動探索服務，以及 Lync Server 2013 推播通知服務。 Lync Server 2013 的累計更新：2月2013新增「Lync 2013 行動用戶端」（透過使用整合通訊網頁 API 或 UCWA）的免費服務。 本節簡短說明這些元件，並識別支援行動性的 Lync Server 2013 拓撲。

<div>


> [!NOTE]  
> 在混合式部署中也提供行動服務。 若您的使用者在線上，您就不需要部署支援行動性的服務。 您必須定義自動探索服務的設定，讓行動使用者能夠尋找其線上身分識別。



</div>

<div>


> [!IMPORTANT]  
> 若要規劃任何外部使用者連線 (例如，同盟、外部使用者存取或行動功能) ，您必須使用具有 Standard Edition server 和前端伺服器或前端集區的 Edge server。 Standard Edition server 和前端伺服器或前端集區沒有必要的元件可讓外部使用者存取您的內部部署，或內部部署與外部使用者通訊。 針對包含與內部使用者共同作業或通訊之外部使用者的所有案例（包括行動性），您必須至少部署一個 Edge Server 與一個反向 proxy。<BR><EM>推播通知</EM>使用 Lync Online 服務的同盟類型，它會主控推播通知的 (PNCH) 。 推播通知指的是在行動裝置非使用中時，會由應用程式推入 Apple iPhone、iPad 和 Windows Phone 之聲音警示、螢幕上警示 (文字) 和徽章。 PNCH 接收來自 Lync Server 的推播通知。 當 PNCH 收到郵件的通知時，PNCH 會根據郵件適用的行動用戶端，將通知傳送給行動用戶端（透過 Apple Push Notification Services 或 Lync Server 2013 推播通知服務）。 PNCH 是這些行動用戶端所需的服務。 為了同盟至 Lync Online，PNCH 會使用 Edge Server 和憑證，以確保機密性和驗證、原則，以及正確設定的網域名稱系統 (DNS) 記錄。 Nokia Symbian 和 Android 型 Lync Mobile 用戶端不使用 PNCH。 如需規劃及部署 Edge server 的詳細資訊，請參閱在 lync server <A href="lync-server-2013-planning-for-external-user-access.md">2013 中規劃外部使用者存取</A>和<A href="lync-server-2013-deploying-external-user-access.md">部署 lync server 2013 中的外部使用者存取</A>。<BR>2013 Lync Server 的 Lync Server 行動用戶端（適用于 Lync Server 2013 的累計更新引進）：2月2013不再使用推播通知或推播通知 PNCH () 。 在 Windows Phone 上的 Lync 2013 行動用戶端仍會使用推播通知和 (PNCH) 。



</div>

<div>

## <a name="mobility-components"></a>行動元件

支援行動性的服務如下：

  - **Lync Server 2013 整合通訊網頁 API (UCWA) **    提供 Lync Server 2013 中即時通訊與行動裝置和 web 用戶端之間的服務。 當您將 Lync Server 2013 2013 的累計更新部署至前端伺服器及 Director 時，安裝會在內部和外部 web 服務 (Ucwa) 中建立虛擬目錄。 屬於 Ucwa 虛擬目錄的網頁元件接受來自啟用 UCWA 之用戶端的呼叫。 用戶端應用程式會透過 REST 介面進行通訊，以進行目前狀態、連絡人、立即訊息、VoIP、視訊會議及共同作業。 UCWA 使用 P-GET 通道，將事件（例如來電、內送立即訊息或郵件）傳送至用戶端應用程式。
    
    <div>
    

    > [!NOTE]  
    > <EM>REST</EM>或代表性狀態轉移是一種軟體架構樣式，適用于已廣泛採用多種表單的分散式系統，而且一般都很適合 Web 服務的需求。

    
    </div>

  - **Lync Server 2013 行動性服務 (Mcx) **    此服務支援在行動裝置上進行 Lync 功能，例如立即訊息 (IM) 、目前狀態和連絡人。 行動服務安裝在每個集區中的每一部前端伺服器上，以支援行動裝置上的 Lync 功能。 當您安裝 Lync Server 2013 時，會在內部網站和前端伺服器上的外部網站上建立新的虛擬目錄 (Mcx) 。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 （含 Lync Server 2013 的累計更新）：二月份2013同時支援 Lync Server 2010： 11 2011 月的累計更新所引進的行動服務，也就是 Mcx 和 UCWA 網頁元件。 這兩種行動裝置的組合可提供 Lync Server 2013 上的 Lync 2010 行動裝置和 Lync 2013 行動用戶端的互通性和使用方式。

    
    </div>

  - **Lync Server 2013 自動探索服務**    這項服務會識別使用者的位置，並可讓行動裝置和其他 Lync 用戶端尋找資源，例如 Lync Server 2013 Web 服務的內部和外部 URLs，以及 Mcx 或 UCWA 的 URL （不論網路位置為何）。 自動探索針對網路內部使用者 (lyncdiscoverinternal，使用硬式編碼主機名稱。lyncdiscover 在網路外的使用者) 和使用者的 SIP 網域。 它支援使用 HTTP 或 HTTPS 的用戶端連線。
    
    自動探索服務會安裝在每個前端伺服器及每個集區中的每個 Director 上，以支援行動裝置上的 Lync 功能。 當您安裝自動探索服務時，會在內部網站和外部網站（兩部前端伺服器及 Director）下建立新的虛擬目錄 (自動探索) 。
    
    <div>
    

    > [!NOTE]  
    > 自動探索服務是在提供行動用戶端服務時維持重要元件，所以會列在這裡。 Lync Server 2013 中的自動探索角色已經過擴充，可提供所有用戶端的服務。 如需規劃自動探索服務的詳細資訊，請參閱<A href="lync-server-2013-planning-for-autodiscover.md">在 Lync Server 2013 中規劃自動</A>探索。

    
    </div>

  - **推播通知服務**    此項服務是位於 Lync Online 資料中心的雲端式服務。 當支援的 Apple iOS 裝置或 Windows Phone 上的 Lync 行動應用程式處於非使用中狀態時，它無法回應新的事件，例如新的立即訊息 (IM) 邀請、錯過的立即訊息、未接來電或語音信箱，因為這些裝置不支援在後臺執行的行動應用程式。 在這些情況下，會將新事件（稱為推播*通知*）的通知傳送至行動裝置。 行動服務會將通知傳送至雲端式推播通知服務，然後將通知傳送至 Apple Push Notification Service (APNS)  (以取得支援的 Apple iOS 裝置) 或 Microsoft 推播通知服務 (MPNS)  (，然後再將其傳送至行動裝置。 然後，使用者可以在行動裝置上回應通知，以啟動應用程式。
    
    Apple 和 Windows Phone 裝置上的 Lync 2010 Mobile 使用推播通知。 2013 Lync Server 的 Lync Server 行動用戶端（適用于 Lync Server 2013 的累計更新引進）：2月2013不再使用推播通知或推播通知 PNCH () 。

下圖說明推播通知服務如何在使用 UCWA 和 Lync 2013 行動用戶端的 Lync Server 2013 拓撲中容納。

![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")

在 Lync Server 2010 的累計更新中引進：11月2011，Mcx service 會為 Lync 2010 行動用戶端提供服務。 下圖說明使用 Mcx 和 Lync 2010 行動用戶端套用至拓撲時的推播通知服務。

![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")

</div>

<div>

## <a name="supported-topologies"></a>支援的拓撲

對 Lync Server 2013 套用累計更新：二月份2013新增 UCWA 網頁元件，以支援下列拓撲中的 Lync 2013 行動用戶端功能：

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

Edge Server 可以是 Lync Server 2010 Edge Server。

不含 Lync Server 2013 累計更新的 Lync Server 2013 部署：2月2013將使用 Mcx 行動性服務，而且只能為 Lync 2010 Mobile 提供服務。

<div>


> [!IMPORTANT]  
> 在使用具有兩個網路介面的轉送伺服器角色組合的前端伺服器上支援行動服務，但您必須採取適當的步驟來設定介面。 您必須將 IP 位址指派給將會以轉送伺服器通訊的特定介面，以及會以前端伺服器進行通訊的網路介面 IP。 您可以在拓撲產生器中，為每個服務選取正確的 IP 位址，而不是使用預設值<STRONG>使用所有設定的 ip 位址</STRONG>。



</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)  
[在 Lync Server 2013 中部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)  
[在 Lync Server 2013 中規劃自動探索](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


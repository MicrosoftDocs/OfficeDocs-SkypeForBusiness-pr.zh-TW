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
ms.openlocfilehash: 739deecf47e25e57ca0175c29a2721e509f8dbe2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a>Lync Server 2013 中的行動性的拓撲和元件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

為了支援行動裝置上的 Lync mobile 應用程式，Lync Server 2013 提供三種服務： Lync Server 2013 Mcx 行動服務、Lync Server 2013 自動探索服務，以及 Lync Server 2013 推播通知服務。 Lync Server 2013 的累積更新：2月2013新增免費的、高級的 Lync 2013 行動用戶端服務-透過使用整合通訊網頁 API 或 UCWA 的行動支援。 本節簡要說明這些元件，並識別支援行動性的 Lync Server 2013 拓撲。

<div>


> [!NOTE]  
> 您也可以在混合式部署中使用行動服務。 如果您的使用者在線上，您就不需要部署支援行動性的服務。 您必須定義自動探索服務的設定，才能讓行動使用者尋找其線上身分識別。



</div>

<div>


> [!IMPORTANT]  
> 如果您打算規劃任何外部使用者連線（例如，同盟、外部使用者存取或行動功能），您必須使用 Edge 伺服器搭配標準版 server 和前端伺服器或前端池。 標準版伺服器和 [前端伺服器] 或 [前端] 池沒有必要的元件可讓外部使用者存取您的內部部署，或用於內部部署與外部使用者通訊。 針對所有案例，包括與內部使用者共同作業或溝通的外部使用者（包括行動性），您必須部署至少一個 Edge 伺服器和一個反向 proxy。<BR><EM>推播通知</EM>使用 Lync Online 服務的同盟類型，該類型會託管推播通知交換房屋（PNCH）。 推播通知指的是當行動裝置處於非使用中時，由應用程式推送給 Apple iPhone、iPad 和 Windows Phone 的音效通知、螢幕警示（文字）和徽章。 PNCH 從 Lync Server 接收推播通知。 當 PNCH 收到訊息的通知時，PNCH 會根據訊息所針對的行動用戶端，透過 Apple 推播通知服務或 Lync Server 2013 推播通知服務，將通知轉寄給行動用戶端。 PNCH 是這些行動用戶端所需的服務。 若要與 Lync Online 聯盟，PNCH 會使用 Edge 伺服器與憑證來確保機密性與驗證、原則，以及正確設定的網域名稱系統（DNS）記錄。 Nokia Symbian 及 Android 版 Lync Mobile 用戶端不使用 PNCH。 如需規劃及部署邊緣伺服器的詳細資料，請參閱在 lync server <A href="lync-server-2013-planning-for-external-user-access.md">2013 中規劃外部使用者存取</A>，以及<A href="lync-server-2013-deploying-external-user-access.md">在 lync Server 2013 中部署外部使用者存取</A>。<BR>適用于 Apple 裝置的 Lync 2013 行動用戶端，其中包含 Lync Server 2013 的累積更新：年2月2013不再使用推播通知或推播通知內部（PNCH）。 Windows Phone 上的 Lync 2013 行動用戶端仍在使用推播通知和（PNCH）。



</div>

<div>

## <a name="mobility-components"></a>行動元件

支援行動性的服務如下所示：

  - **Lync server 2013 整合通訊 Web API （UCWA）**   可在 Lync Server 2013 中提供即時通訊與行動裝置和 Web 用戶端的服務。 當您部署 Lync Server 2013 的累積更新時：2月2013到前端伺服器和控制器，安裝會在內部和外部 web 服務（Ucwa）中建立一個虛擬目錄。 屬於 Ucwa 虛擬目錄的網頁元件接受來自 UCWA 的用戶端的呼叫。 用戶端應用程式會在 REST 介面進行通訊，以取得目前狀態、連絡人、立即訊息、VoIP、視訊會議及共同作業。 UCWA 使用 P-取得的通道來傳送事件，例如撥入通話、內送立即訊息，或是傳送給用戶端應用程式的訊息。
    
    <div>
    

    > [!NOTE]  
    > [ <EM>REST</EM> ] 或 [representational 狀態傳輸] 是一種軟體結構樣式，適用于廣泛採用許多形式的分散式系統，且很適合一般的 Web 服務需求。

    
    </div>

  - **Lync Server 2013 行動服務（Mcx）**   此服務支援在行動裝置上進行 Lync 功能，例如立即訊息（IM）、目前狀態和連絡人。 行動服務是在每個要支援行動裝置上的 Lync 功能的每個池中，都安裝在每個前端伺服器上。 當您安裝 Lync Server 2013 時，會在內部網站和前端伺服器上的外部網站下建立新的虛擬目錄（Mcx）。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync server 2013 使用 Lync Server 2013 的累積更新：2月2013支援 Lync Server 2010 的累積更新中所引入的行動服務：2011年11月的，以及 UCWA 網頁元件。 這兩種行動服務的組合提供在 Lync Server 2013 上使用 Lync 2010 行動裝置和 Lync 2013 行動用戶端的使用者互通性與使用。

    
    </div>

  - **Lync server 2013 自動探索服務**   ：此服務會識別使用者的位置，並讓行動裝置和其他 lync 用戶端找出資源，例如 Lync Server 2013 Web 服務的內部和外部 url，以及 Mcx 或 UCWA 的 URL （無論網路位置為何）。 自動搜尋使用硬式編碼主機名稱（lyncdiscoverinternal 網路中的使用者，lyncdiscover 網路外部使用者）和使用者的 SIP 網域。 它支援使用 HTTP 或 HTTPS 的用戶端連線。
    
    自動探索服務會安裝在每個前端伺服器上，以及每個要支援行動裝置上的 Lync 功能的每個池中的每個控制器上。 當您安裝自動探索服務時，會在內部網站和外部網站（在前端伺服器與控制器）底下建立新的虛擬目錄（自動探索）。
    
    <div>
    

    > [!NOTE]  
    > [自動探索服務] 會在這裡列出，因為它在提供行動用戶端服務時會一直是一個重要的元件。 已展開 Lync Server 2013 中的自動探索角色，以便為所有用戶端提供服務。 如需規劃自動探索服務的詳細資料，請參閱<A href="lync-server-2013-planning-for-autodiscover.md">在 Lync Server 2013 中規劃自動</A>探索。

    
    </div>

  - **推播通知服務**   ：此服務是位於 Lync Online 資料中心的雲端服務。 當支援的 Apple iOS 裝置或 Windows Phone 上的 Lync 行動裝置應用程式在非使用中時，它無法回應新的事件，例如新的立即訊息（IM）邀請、未接的立即訊息、未接來電或語音信箱，因為這些裝置不支援在背景中執行的行動應用程式。 在這些情況下，會將新事件（稱為推播*通知*）通知傳送到行動裝置。 行動服務會傳送通知給雲端型推播通知服務，然後將通知傳送至 Apple 推播通知服務（APNS）（針對支援的 Apple iOS 裝置）或 Microsoft 推播通知服務（MPNS）。）（適用于 Windows Phone），然後將它傳送到行動裝置。 然後，使用者就可以在行動裝置上回應通知，以啟動應用程式。
    
    Apple 和 Windows Phone 裝置上的 Lync 2010 Mobile 使用推播通知。 適用于 Apple 裝置的 Lync 2013 行動用戶端，其中包含 Lync Server 2013 的累積更新：年2月2013不再使用推播通知或推播清除房屋（PNCH）。

下圖說明推播通知服務在使用 UCWA 和 Lync 2013 行動用戶端的 Lync Server 2013 拓撲中的相符程度。

![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")

在 Lync Server 2010 的累加更新中引入2011： Mcx 服務提供給 Lync 2010 行動用戶端的服務。 下圖說明使用 Mcx 和 Lync 2010 行動用戶端的拓撲結構時，推播通知服務。

![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")

</div>

<div>

## <a name="supported-topologies"></a>支援的拓撲

套用 Lync Server 2013 的累積更新：2013年2月新增 UCWA 網頁元件，以支援 Lync 2013 行動用戶端功能在下列拓撲中的行動：

  - Lync Server 2013 標準版

  - Lync Server 2013 企業版

Edge 伺服器可以是 Lync Server 2010 Edge 伺服器。

不含 Lync Server 2013 累計更新的 Lync Server 2013 部署：2月2013將使用 Mcx 行動服務，且只能為 Lync 2010 Mobile 提供服務。

<div>


> [!IMPORTANT]  
> Collocated 前端伺服器支援行動服務，而該伺服器擁有兩個網路介面的中繼伺服器角色，但您必須採取適當的步驟來設定介面。 您必須將 IP 位址指派給將作為中繼伺服器通訊的特定介面，以及將通訊為前端伺服器的網路介面 IP。 您可以在拓撲建立器中，為每個服務選取正確的 IP 位址，而不是使用預設的 [<STRONG>使用所有已設定的 ip 位址</STRONG>]。



</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)  
[在 Lync Server 2013 中部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)  
[規劃 Lync Server 2013 中的自動探索](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013 Enterprise Voice
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 924e15aae9590b6148864084aa68924e4c080f7c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 中的 Enterprise Voice

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015年-04-08_

與 Enterprise Voice、 Lync Server 會傳遞至增強或取代傳統的專用交換機 (pbx) 系統提供獨立 Voice over Internet Protocol (VoIP)。 Enterprise Voice 使用者可以在您的組織在 VoIP 網路或 PBX 上呼叫同事，他們可以撥組織外部的傳統的電話號碼。 企業語音解決方案包含常見的通話功能，例如 answer、 轉寄、 轉接、 保留、 轉向、 發行及駐留，和增強型 9-1-1 (E9-1-1) 通話 （E9-1-1 是只適用於美國）。Enterprise Voice 也支援廣泛的目前和較舊的 IP 和 USB 裝置。

<div>

## <a name="placing-and-receiving-calls"></a>撥打和接聽電話

使用 Lync，使用者可以撥打電話，在其鍵盤上，輸入名稱或電話號碼，或使用其螢幕上顯示的撥號鍵台。 使用者也可以啟動直接從其連絡人清單的通話。 您也可以部署 Lync Phone Edition 裝置，也就是由 Microsoft 協力廠商所提供的獨立 IP 電話裝置。

使用者可以有多個登錄與 Lync Server 的電話裝置，且可以輕鬆地切換這些。

使用者會發出警示，其所有裝置上的傳入呼叫同時，IP 電話裝置上可自訂的鈴聲與類似於其電腦上的立即訊息通知。

使用者也可以設定連接至其電話機、 電腦和行動電話，讓他們可以達到不論它們的位置的單一電話號碼。

</div>

<div>

## <a name="basic-call-features"></a>基本通話功能

在呼叫，使用者可以接聽其他來電或其中初始化的撥出電話，以及現有的作用中呼叫自動置於時保留。 到另一個，可以呼叫轉接從一位使用者，直接或之後的第一個使用者私下說出與第二個使用者。 使用者可以也將來電轉接給另一個裝置;例如，他們無法 active 來電轉接到行動電話為他們引導出其 office 門。

</div>

<div>

## <a name="richer-communications"></a>更豐富的通訊

當與另一位使用者使用 Lync 交談，使用者可以輕鬆地新增文字、 視訊或桌面共用的通話。 Do Not 打擾功能是與整合 Lync 中的目前狀態設定。

Exchange 整合通訊 (UM)、 Lync 與 Lync Server 整合與 Microsoft Exchange Server 2013 和 Microsoft Outlook 2013。 使用者可以查看是否有新語音郵件在其 Lync 視窗和電子郵件中。 在 [電子郵件，他們可以按一下來播放語音信箱音訊中電子郵件訊息，或檢視語音信箱訊息的文稿 while。

</div>

<div>

## <a name="advanced-calling-features"></a>進階通話功能

Enterprise Voice 包含數項進階通話功能，例如 Lync 通話委派、 小組通話、 群組來電接聽和回應群組。

Lync 通話委派可讓使用者委派通話處理到一或多個助理員移至 [**工具** \> **選項** \> **呼叫轉寄設定**。 代理人可以多個呼叫代表執行工作的使用者，包括檢測通話、 進行呼叫，並啟動會議。

<div>


> [!IMPORTANT]  
> 您可能會尋找另一個類似命名功能，Lync 行事曆委派。 它不需要的企業語音功能，可讓使用者從 Outlook 的線上 Lync 會議排程。 如果您已在這裡尋找的資訊，建議您取出<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-csclientpolicy</A>上啟用 Exchange 委派同步處理的資訊。



</div>

小組通話可讓使用者使來電同時在組員的小組成員的電話，讓小組成員的任何人都可以接聽來電。

群組呼叫收取，Cumulative Updates for Lync Server 2013 中的新功能： 2 月 2013年可讓使用者接聽來電從他們自己的電話其同事。 群組來電接聽與小組通話中，主要的傳入呼叫只會在預定收件者的電話鈴響但任何其他使用者可以選擇接聽撥出通話收取群組號碼。

回應群組可以設定對指定的代理程式的佇列和聰明地路由呼叫。 一般用途包括 IT 人員、 人力資源 hotlines 及其他內部的連絡人中心。

</div>

<div>

## <a name="enterprise-voice-administration"></a>Enterprise Voice 管理

Lync Server 使用標準和發行的介面與現有基礎結構交互操作。 它支援閘道和 IP PBX 系統與 PSTN 網路，互相連線 （例如 SIP 主幹） SIP 選項，讓您可以將使用者移轉到 Enterprise Voice 一段時間，干擾降到最低。 Lync Server 與 VoIP 的傳統解決方案的互通性支援傳統 G.711、 G.722 等 G.723.1 轉碼器。

通話許可控制 (CAC)，與系統管理員可以設定 Lync Server 語音和視訊流量限制的網路連結上執行的數量的限制，並指定要將新的來電會超出限制要採取的動作。 動作無法包含路由替代路徑，或拒絕來電。

Lync Server 的運作方式與協力廠商 Survivable Branch Appliance pstn 分公司，在中央網站的 WAN 故障時提供本地撥號服務和連線。

</div>

</div>

<span> </span>

</div>

</div>

</div>


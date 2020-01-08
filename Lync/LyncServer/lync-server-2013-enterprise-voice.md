---
title: Lync Server 2013 企業語音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7c8131c2f52dfc7ab061d8dec46ee34b62f89e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 中的企業語音

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-04-08_

透過企業語音，Lync Server 會提供獨立的網際網路通訊協定（VoIP）產品，以增強或取代傳統的專用分支 exchange （PBX）系統。 企業語音使用者可以呼叫貴組織的 VoIP 網路或 PBX 上的同事，而且可以呼叫貴組織外部的傳統電話號碼。 企業語音方案包含常見的呼叫功能，例如 [應答]、[轉寄]、[轉接]、[保留]、[轉移]、[發行及寄存]，以及 [增強9-1-1 （E9-1）] 呼叫（僅適用于美國的 E9-1-1）。企業語音也支援各種目前及較舊的 IP 和 USB 裝置。

<div>

## <a name="placing-and-receiving-calls"></a>撥打電話和接聽通話

使用者可以使用 Lync 在鍵盤上輸入名稱或電話號碼，或使用螢幕上顯示的撥號鍵台來撥打通話。 使用者也可以直接從連絡人清單中啟動通話。 您也可以部署 Lync Phone Edition 裝置，這些裝置是由 Microsoft 合作夥伴提供的獨立 IP 電話裝置。

使用者可以有多個註冊到 Lync Server 的電話裝置，而且可以輕鬆地在這些裝置之間切換。

使用者會在其所有裝置上同時收到來電通知，且在 IP 電話裝置上有可自訂的鈴聲，以及電腦上的立即訊息等類似通知。

使用者也可以設定連線到其手機、電腦和手機的單一電話號碼，讓他們無論身在何處都能到達。

</div>

<div>

## <a name="basic-call-features"></a>基本通話功能

在通話時，使用者可以接聽其他來電或發起撥出電話，而現有的使用中通話則會自動停留在保留狀態。 您可以直接或在第一位使用者使用第二個使用者進行私下演講之後，將通話從一個使用者轉接到另一個使用者。 使用者也可以將來電轉接到另一個裝置;例如，他們可以將使用中的來電轉接到他們的行動電話，因為他們會離開其辦公室的大門。

</div>

<div>

## <a name="richer-communications"></a>更豐富的通訊

當您使用 Lync 與其他使用者交談時，使用者可以輕鬆地在通話中新增文字、影片或桌面共用。 [請勿打擾] 功能已與 Lync 中的目前狀態設定整合。

使用 Exchange 整合通訊（UM），Lync 和 Lync Server 整合至 Microsoft Exchange Server 2013 與 Microsoft Outlook 2013。 使用者可以查看他們在 Lync 視窗和電子郵件中是否有新的語音信箱。 在電子郵件中，他們可以按一下以在電子郵件訊息中播放語音信箱音訊，或查看語音信箱訊息的記錄。

</div>

<div>

## <a name="advanced-calling-features"></a>高級通話功能

企業語音還包含數種高級通話功能，例如 Lync 通話委派、小組通話、群組通話挑選，以及回應群組。

Lync 通話委派可讓使用者將呼叫處理委派給一或多個助手，方法是移至 [**工具** \> **] 選項** \>的 [**來電轉接設定**]。 代理人可以代表使用者執行多個通話工作，包括遮罩通話、撥打電話及開始會議。

<div>


> [!IMPORTANT]  
> 您可能會尋找另一個名稱相似的功能，即 Lync 行事曆委派。 它不需要企業語音功能，且允許使用者從 Outlook 排程線上 Lync 會議。 如果您在這裡找到該資訊，我們建議您檢查<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">CsClientPolicy</A> ，瞭解啟用 Exchange 委派同步處理的相關資訊。



</div>

團隊通話可讓使用者同時撥打小組電話，讓小組中的任何人都能接聽通話。

[群組通話]： Lync Server 2013 的累積更新中的新功能：2013年2月，讓使用者從自己的手機向其同事接聽來電。 [群組呼叫挑選] 與小組通話的不同之處，主要是在預期收件者的手機上，僅限來電響鈴，但任何其他使用者都可以撥打電話挑選群組號碼，選擇接聽電話。

您可以設定回應群組，將呼叫路由及智慧地路由到指定的 agent。 常見用途包括 IT 提供人員、人力資源 hotlines，以及其他內部連絡人中心。

</div>

<div>

## <a name="enterprise-voice-administration"></a>企業語音管理

Lync Server 使用標準與已發佈介面，與現有的基礎結構互動。 它支援閘道和 SIP 選項（例如 SIP 中繼），以便與 IP PBX 系統和 PSTN 網路進行互連，因此您可以在一段時間內將使用者遷移至企業語音，同時將中斷降至最低。 Lync Server 支援傳統的編解碼器，例如711、722和723.1，以實現與傳統 VoIP 解決方案的互通性。

系統管理員可以使用 [呼叫許可控制] （CAC）來設定受限制網路連結上的 Lync Server 語音及影片流量限制，並指定新呼叫超過限制時所採取的動作。 這些動作可能包括依備用路徑進行路由，或拒絕通話。

Lync Server 與協力廠商 Survivable 分支裝置搭配使用，以提供本機呼叫服務，以及分支辦公室的 PSTN 連線（在中央網站發生 WAN 故障時）。

</div>

</div>

<span> </span>

</div>

</div>

</div>


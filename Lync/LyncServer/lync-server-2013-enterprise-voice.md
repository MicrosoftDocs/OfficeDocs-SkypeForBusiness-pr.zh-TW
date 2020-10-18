---
title: Lync Server 2013 Enterprise Voice
description: Lync Server 2013 Enterprise Voice。
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
ms.openlocfilehash: e11f2497cf99319317a75b81f02ed0d8ca797fbf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574229"
---
# <a name="enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 中的 Enterprise Voice

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-04-08_

透過 Enterprise Voice，Lync Server 會提供獨立的語音 over 網際網路通訊協定 (VoIP) 可強化或更換傳統專用交換機 (PBX) 系統的產品。 Enterprise Voice 使用者可以撥打組織 VoIP 網路或 PBX 上的同事，也可以撥打組織外部的傳統電話號碼。 Enterprise Voice 方案包含常見通話功能（例如，答案、轉寄、轉移、保留、轉移、發行和寄存）及增強型 9-1-1 (E9-1-1) 呼叫 (E9-1-1 只適用于美國。 ) Enterprise Voice 也支援廣泛的現有和 USB 裝置。

<div>

## <a name="placing-and-receiving-calls"></a>撥打和接聽電話

使用 Lync 時，使用者可以在鍵盤上輸入名稱或電話號碼，或使用螢幕上顯示的撥號鍵，以撥打通話。 使用者也可以直接從連絡人清單中初始化通話。 您也可以部署 Lync Phone Edition 裝置，這是 Microsoft 合作夥伴提供的獨立 IP 電話裝置。

使用者可以讓多個電話裝置向 Lync Server 註冊，而且可以輕鬆地進行切換。

使用者可在其所有裝置上同時收到來電，並可自訂的鈴聲于 IP 電話裝置上，以及類似于電腦上的立即訊息的通知。

使用者也可以設定一部電話號碼，以連線至其所在的電話、電腦和行動電話，所以不論身處何地，都可以到達。

</div>

<div>

## <a name="basic-call-features"></a>基本通話功能

在通話時，使用者可以接聽其他來電或發起撥出電話，而且現有的使用中通話會自動保留。 呼叫可以從某位使用者轉移到另一個使用者，不論是在第一位使用者私下使用第二位使用者的演講中。 使用者也可以將來電轉接至另一個裝置;例如，他們可以將使用中的來電轉接到行動電話，因為他們會向外移動他們的辦公室。

</div>

<div>

## <a name="richer-communications"></a>更豐富的通訊

當您使用 Lync 與其他使用者交談時，使用者可以輕鬆地將文字、影片或桌面共用新增至通話。 [請勿打擾] 功能會與 Lync 中的目前狀態設定整合。

使用 Exchange 整合通訊 (UM) ，Lync 和 Lync Server 會與 Microsoft Exchange Server 2013 和 Microsoft Outlook 2013 整合。 使用者可以查看他們的 Lync 視窗和電子郵件中是否有新的語音信箱。 在電子郵件中，他們可以按一下以在電子郵件訊息中播放語音信箱音訊，或是查看語音信箱訊息的成績單。

</div>

<div>

## <a name="advanced-calling-features"></a>高級通話功能

Enterprise Voice 也包含數種高級通話功能，例如 Lync 呼叫委派、小組通話、群組通話收取及回應群組。

Lync 呼叫委派可讓使用者將通話處理委派給一或多個助理，方法是移至 [ **工具**] \> **選項**「 \> **來電轉接設定**」。 代理人可代表使用者執行多個呼叫工作，包括篩選通話、撥出通話，以及發起會議。

<div>


> [!IMPORTANT]  
> 您可能正在尋找其他具有類似名稱的功能，例如 Lync 行事曆委派。 不需要企業語音功能，也不允許使用者從 Outlook 排程線上 Lync 會議。 如果您已在這裡尋找該資訊，建議您取出 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> ，以取得啟用 Exchange 委派同步處理的資訊。



</div>

小組通話可讓使用者同時撥打小組電話，讓小組中的任何人都可以接聽通話。

群組呼叫收取（Lync Server 2013 的累計更新中的新功能：2月2013）可讓使用者從自己的電話接聽來電給其同事。 群組呼叫收取的不同之處在于，小組來電主要是在預期的收件者的電話上進行來電振鈴，但任何其他使用者可以撥打通話收取群組號碼來選擇回復。

回應群組可以設定為進行佇列，並智慧地將通話路由傳送至指定的代理人。 常見的使用包括 IT 人員服務中心、人力資源 hotlines 及其他內部連絡人中心。

</div>

<div>

## <a name="enterprise-voice-administration"></a>Enterprise Voice Administration

Lync Server 會使用標準及發行的介面與現有基礎結構互動。 它支援閘道和 SIP 選項 (例如 SIP 主幹) ，以與 IP PBX 系統和 PSTN 網路進行互連，因此您可以將使用者遷移至 Enterprise Voice，但會使中斷降到最低。 Lync Server 支援傳統的編碼解碼器，例如 g.711、g.722 和 g.723.1，以與傳統的 VoIP 解決方案交互操作。

透過「通話許可控制」 (CAC) ，管理員可以設定受限制網路連結上的 Lync Server 語音和影片流量的數量限制，以及指定當新呼叫超出限制時所採取的動作。 動作可能包括透過替代路徑來路由傳送，或拒絕通話。

Lync Server 與協力廠商 Survivable 分支裝置搭配使用，以提供本機呼叫服務，並在分支辦公室連接至 PSTN，以在中央網站發生 WAN 失敗。

</div>

</div>

<span> </span>

</div>

</div>

</div>


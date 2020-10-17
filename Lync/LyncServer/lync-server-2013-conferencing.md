---
title: Lync Server 2013 會議
description: Lync Server 2013 會議。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417161(v=OCS.15)
ms:contentKeyID: 48184274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d4a5f1ca1edc6246aace56c8a4bfa5b5215c4bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555949"
---
# <a name="conferencing-in-lync-server-2013"></a>Lync Server 2013 中的會議

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-11_

透過 Lync Server 2013 的整合式會議，使用者可以共同作業、共用資訊，以及即時協調其工作。 所有使用者都可以完整使用自發性共同作業、排程會議及會議工具。 從任何具有網際網路連線的位置都可以使用語音及視訊會議功能，而離開電腦的使用者使用公用電話交換網路 (PSTN) 電話撥入，就可以參與音訊會議。

已整合至 Outlook 的會議工具可讓召集人以單一按一下方式排程會議或啟動即時會議，也使出席者輕鬆加入。 網頁用戶端將豐富的會議功能延伸至未執行桌上出版本 Lync 的參與者。

<div>

## <a name="audio-and-video-conferencing"></a>音訊與視訊會議

Lync Server 針對傳統音訊橋接服務使用者（包括 PSTN 電話語音電話控制命令）提供熟悉的使用者經驗。 同時，包含只有整合式整合通訊平台才提供的強大排程、加入及管理功能。

只按一下一次，使用者就可以從 Outlook 排程會議。 詳細資料，例如會議時間、地點和出席者，請遵循熟悉的 Outlook 範本。 此外，會自動填入特定電話會議的資訊 (如撥入號碼、會議 ID 及個人識別碼 (PIN) 提醒)。

為了協助確保只有授權的人員參與通話，Lync Server 會為參與者提供多種驗證層級。 使用 Lync 加入的使用者已透過 Active Directory 網域服務進行驗證，而且不需要輸入 PIN、傳遞代碼或會議識別碼。

Lync 透過將影片整合至統一用戶端，使會議能夠簡化會議使用者體驗，這樣就能順暢且輕鬆地使用影片排程會議或升級至影片。

Lync Server 可讓您輕鬆地只按一下一次，即可將影片加入至標準通話。 視訊通話或會議有多位參與者時，每位使用者最多可以同時看到其他五位使用者的視訊，或者簡報者可以選擇讓所有人只能看到同一個視訊。

高清晰度影片 (解析度 1270 x 720;方位比率 16:9) 和 VGA 影片 (解析度 640 x 480;在高端電腦上執行 Lync 的使用者之間，對等通話支援的長寬比 4:3) 。 單一交談中每位參與者所看到的解析度可能會不同，這取決於每位使用者各自硬體的視訊功能。

IT 系統管理員可以設定原則來限制或停用用戶端上的高畫質或 VGA 視訊，而這取決於電腦功能、網路頻寬，以及是否有可提供必要解析度的相機。這些原則會透過頻內佈建執行。

</div>

<div>

## <a name="web-conferencing"></a>Web 會議

Lync Server 會將會議共用功能（例如，桌面、應用程式、附件、白板、投票和 PowerPoint）整合到簡化的 Lync 中。 與音訊或視訊會議結合後，會產生十分逼真及容易使用的共同作業工作階段。

為了改善使用者呈現或查看 PowerPoint 簡報的整體體驗，Lync Server 2013 使用 Office Web Apps 來處理 PowerPoint 簡報。 使用者可以使用 Lync 會議中的白板，共用圖片或複製及貼上文字。 簡報者可以在 Lync 會議中執行投票，以徵求出席者的意見反應。

桌面共用可讓簡報者即時將其桌面的任何視覺效果、應用程式、網頁、檔、軟體或部分廣播至遠端參與者，直接從 Lync。 會議成員可以看到滑鼠的移動及鍵盤輸入情形。 簡報者可以選擇共用整個螢幕或只共用部分螢幕。 透過共用桌面，簡報者可以讓會議成員從任何位置參與互動式產品或軟體示範。

應用程式共用可讓簡報者共用其桌面上的軟體控制，而不會漏失參與者的反應或文字問題。簡報者也可以將應用程式的控制委派給會議參與者。

</div>

<div>

## <a name="dial-in-conferencing"></a>電話撥入式會議

對於未使用個人電腦的使用者，有數種方法可以加入 Lync Server 會議呼叫。 PSTN 使用者可以撥打存取號碼，並存取會議橋接器，然後輸入會議 ID。 若要進行更安全的會議，使用者也可能需要輸入 PIN，以根據 Active Directory 進行驗證。 Lync Server 也支援 Lync Phone Edition 裝置，也就是 Microsoft 合作夥伴提供的獨立 IP 電話裝置。

</div>

</div>

<span> </span>

</div>

</div>

</div>


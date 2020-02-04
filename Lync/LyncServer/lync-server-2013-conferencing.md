---
title: Lync Server 2013 會議
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
ms.openlocfilehash: e92f14a9f23617c55f1c09abc4daf29b5849b3bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a>Lync Server 2013 中的會議

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-11_

透過 Lync Server 2013 中的整合式會議，使用者可以共同作業、共用資訊，以及即時協調他們的工作。 您所有的使用者都可以使用全面的自發共同作業、排程的會議及會議工具。 語音及視訊會議功能可從任何網際網路連線的位置使用，而離開電腦的使用者可以使用公用的交換電話網絡（PSTN）電話撥入來參與音訊會議。

[會議工具] 集成在 Outlook 中，您可以透過按一下滑鼠來排程會議或啟動臨時會議，也可讓出席者輕鬆加入會議。 Web 用戶端將豐富的會議功能延伸到不執行桌上出版 Lync 的參與者。

<div>

## <a name="audio-and-video-conferencing"></a>音訊與視訊會議

Lync Server 提供傳統音訊橋接服務使用者所熟悉的使用者經驗，包括 PSTN 撥入服務與按鍵式通話控制命令。 同時，它會整合功能強大的排程、加入與管理功能，只適用于整合式整合通訊平臺。

只要按一下滑鼠，使用者就可以從 Outlook 排程會議。 詳細資料（例如會議時間、地點和出席者），請遵循熟悉的 Outlook 範本。 此外，會議通話的特定資訊，例如撥入號碼、會議 Id，以及個人識別碼（PIN）提醒，都會自動填入。

為了協助確保只有獲授權的人參與通話，Lync Server 提供多位參與者驗證等級。 使用 Lync 加入的使用者已經由 Active Directory 網域服務驗證，且不需要輸入 PIN、傳遞代碼或會議 ID。

Lync 簡化了視訊會議的使用者體驗，只要將影片併入整合的用戶端，就能順暢且輕鬆地排程會議，或透過影片進行升級。

Lync Server 可讓您只需一次按一下，就能輕鬆地將影片新增到標準通話中。 當在視頻通話或會議中有多個參與者時，每個使用者都可以同時查看最多五個其他使用者的影片，或者簡報者可以選擇只透過每個人看到的一個影片來源。

在高端電腦上執行 Lync 之使用者之間的對等呼叫支援高清晰度影片（解析度 1270 x 720; 長寬比16:9）和 VGA 影片（解析度 640 x 480; 長寬比4:3）。 由單一交談中的每個參與者所查看的解析度可能會有所不同，視每個使用者各自硬體的影片功能而定。

IT 管理員可以設定原則，以限制或停用用戶端上的高清或 VGA 影片，這要視電腦的功能、網路頻寬，以及相機是否能夠提供所需的解析度而定。 這些原則是透過頻帶內配來強制執行。

</div>

<div>

## <a name="web-conferencing"></a>網路會議

Lync Server 將會議共用功能（例如桌面、應用程式、附件、白板、投票和 PowerPoint）整合到精簡的 Lync 中。 在音訊或視訊會議中結合，結果就是一種非常輕鬆且易於進行的共同作業會話。

為了改善演示或查看 PowerPoint 簡報的使用者的整體體驗，Lync Server 2013 使用 Office Web Apps 來處理 PowerPoint 簡報。 使用者可以在 Lync 會議中使用白板共用圖片或複製及貼上文字。 簡報者可以在 Lync 會議中進行投票，徵求出席者的意見反應。

桌面共用可讓簡報者即時將任何視覺效果、應用程式、網頁、檔、軟體或部分桌面廣播至遠端參與者，直接從 Lync。 觀眾可以跟隨滑鼠移動與鍵盤輸入。 簡報者可以選擇共用整個畫面或只共用部分。 透過共用桌上型電腦，簡報者就能從任何位置在互動式產品或軟體示範中與他們的觀眾進行互動。

[應用程式共用] 可讓簡報者共用電腦上的軟體控制，而不會看到參與者意見反應或文字問題。 簡報者也可以將應用程式的控制權委派給會議參與者。

</div>

<div>

## <a name="dial-in-conferencing"></a>電話撥入式會議

對於不是使用個人電腦的使用者，有數種方法可加入 Lync Server 電話會議。 PSTN 使用者可以撥號存取號碼、存取會議橋接器，然後輸入會議 ID。 若要進行更安全的會議，您也可以要求使用者輸入其 PIN 來針對 Active Directory 進行驗證。 Lync Server 也支援 Lync Phone Edition 裝置，這些裝置是由 Microsoft 合作夥伴提供的獨立 IP 電話裝置。

</div>

</div>

<span> </span>

</div>

</div>

</div>


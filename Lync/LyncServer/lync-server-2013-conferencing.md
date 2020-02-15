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
ms.openlocfilehash: dafb39a741ac26fc6edad6362ad10f2a6c244c64
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a>Lync Server 2013 中的會議

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-11_

與整合 Lync Server 2013 中的會議，使用者可以進行共同作業、 共用的詳細資訊，及協調他們即時的努力。 所有使用者都可以完整使用自發性共同作業、排程會議及會議工具。 從任何具有網際網路連線的位置都可以使用語音及視訊會議功能，而離開電腦的使用者使用公用電話交換網路 (PSTN) 電話撥入，就可以參與音訊會議。

會議工具整合到 Outlook 啟用召集人可以排程會議或啟動即席會議，只要按一下，並也讓一樣簡單的出席者加入。 網頁用戶端會延伸至未執行 Lync 的桌上型版本的參與者的豐富的會議功能。

<div>

## <a name="audio-and-video-conferencing"></a>音訊與視訊會議

Lync Server 提供的傳統音訊橋接器服務包括 PSTN 電話撥入式服務使用按鍵式通話控制命令的使用者熟悉的使用者經驗。 同時，包含只有整合式整合通訊平台才提供的強大排程、加入及管理功能。

只要按一下，使用者可以排程從 Outlook 會議。 詳細資料，例如會議時間、 位置和出席者，請遵循熟悉 Outlook 範本。 此外，會自動填入特定電話會議的資訊 (如撥入號碼、會議 ID 及個人識別碼 (PIN) 提醒)。

為了協助確保只有授權的使用者參與的通話，Lync Server 提供多個層級的驗證的參與者。 使用 Lync 加入的使用者已經通過驗證的 Active Directory 網域服務，且不需要輸入 pin 碼，通過程式碼，或會議 id。

Lync 藉由將影片納入整合用戶端，使排程含有視訊的會議或自發性地擴大為視訊主動順暢及簡單簡化視訊會議使用者經驗。

Lync Server 可以輕鬆中只要按一下標準電話呼叫期間新增視訊。 視訊通話或會議有多位參與者時，每位使用者最多可以同時看到其他五位使用者的視訊，或者簡報者可以選擇讓所有人只能看到同一個視訊。

在高階電腦執行 Lync 使用者之間的對等通話支援高畫質視訊 （解析度 1270 x 720，長寬比 16:9） 及 VGA 視訊 （解析度為 640 x 480，長寬比為 4:3）。 單一交談中每位參與者所看到的解析度可能會不同，這取決於每位使用者各自硬體的視訊功能。

IT 系統管理員可以設定原則來限制或停用用戶端上的高畫質或 VGA 視訊，而這取決於電腦功能、網路頻寬，以及是否有可提供必要解析度的相機。這些原則會透過頻內佈建執行。

</div>

<div>

## <a name="web-conferencing"></a>Web 會議

Lync Server 整合到簡化的 Lync 會議的共用功能，例如桌面、 應用程式、 附件、 白板、 投票與 PowerPoint。 與音訊或視訊會議結合後，會產生十分逼真及容易使用的共同作業工作階段。

若要改善整體呈現或檢視 PowerPoint 簡報的使用者經驗，Lync Server 2013 會採用 Office Web Apps 才能處理的 PowerPoint 簡報。 使用者可以共用的圖片或複製並貼上文字 Lync 會議中使用白板。 簡報者可以進行投票 Lync 會議請求出席者的意見反應。

桌面共用，可讓簡報者將可直接從 Lync 即時，遠端參與者廣播任何視覺效果、 應用程式、 網頁、 文件、 軟體或其桌面的一部分。 會議成員可以看到滑鼠的移動及鍵盤輸入情形。 簡報者可以選擇共用整個螢幕或只共用部分螢幕。 透過共用桌面，簡報者可以讓會議成員從任何位置參與互動式產品或軟體示範。

應用程式共用可讓簡報者共用其桌面上的軟體控制，而不會漏失參與者的反應或文字問題。簡報者也可以將應用程式的控制委派給會議參與者。

</div>

<div>

## <a name="dial-in-conferencing"></a>電話撥入式會議

不使用個人電腦的使用者，有幾種方法可用於加入 Lync Server 電話會議。 PSTN 使用者可以撥打存取號碼，並存取會議橋接器，然後輸入會議 ID。 若要進行更安全的會議，使用者也可能需要輸入 PIN，以根據 Active Directory 進行驗證。 Lync Server 也支援 Lync Phone Edition 裝置，也就是由 Microsoft 協力廠商所提供的獨立 IP 電話裝置。

</div>

</div>

<span> </span>

</div>

</div>

</div>


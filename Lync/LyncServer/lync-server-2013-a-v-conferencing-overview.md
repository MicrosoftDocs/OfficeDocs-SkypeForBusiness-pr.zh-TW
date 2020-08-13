---
title: Lync Server 2013 A/V 會議概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2499b7cae2a6833612c34b877ca872f1a504fac9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的 A/V 會議綜述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-13_

A/V 會議可讓您的使用者之間進行即時音訊和視頻通訊。 部署會議時，您可以選擇同時啟用及使用 Web 會議和 A/V 會議，或僅啟用及使用 Web 會議。

若要規劃 A/V 會議，您需要了解組織需要的會議媒體類型及其所需的網路頻寬。 這可能包括音訊、影片及全景影片。

在您為使用者啟用 A/V 會議之前，請先確定您的網路可以處理所產生的負載。 若沒有足夠的網路頻寬，使用者體驗可能會嚴重降低。 您可以使用 [通話許可控制] (CAC) 管理 A/V 會議所使用的網路頻寬。 這對限制網路很重要，例如中央和分支網站之間有限的頻寬連結。 如需詳細資訊，請參閱 [Lync Server 2013 中的 [通話許可控制](lync-server-2013-overview-of-call-admission-control.md)]。 如需媒體頻寬需求的詳細資訊，請參閱 [Lync Server 2013 中媒體流量的網路頻寬需求](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)。

如果您在網路中部署音訊會議，您的使用者將需要諸如耳機等音訊裝置參加音訊會議。 如果您部署了影片會議，您必須部署影片裝置，例如使用者的網路攝像機。 我們建議您針對所有的裝置類型，針對由 Microsoft 認證的 UC) 裝置，使用整合通訊 (，以確保最佳的使用者體驗。 如需 UC 驗證裝置的詳細資訊，請參閱的「電話和裝置（Lync）」 [https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861) 。 針對音訊或視頻裝置、裝置部署和使用者訓練，都是您考慮和規劃的重要步驟。

下列各節說明音訊和視訊會議的功能，包括有關管理頻寬及選擇適當用戶端的資訊。

<div>

## <a name="audio-conferencing-features"></a>音訊會議功能

Lync Server 2013 提供數種功能，可讓您用來為使用者設定語音會議體驗，包括下列專案：

  - **物件靜音**    簡報者可以使用此設定來靜音會議中所有的音訊參與者，並將會議置於非簡報者無法自行取消靜音的狀態。

  - **會議進入/出口宣告**    如果您已啟用電話撥入式會議，簡報者可以使用此設定開啟或關閉進入和關閉宣告，以在會議進行中時，將干擾減至最小。

  - **以撥出**     方式新增使用者簡報者和授與出席者的許可權，可將 PSTN 號碼新增至會議，並讓會議撥出至這些號碼。

</div>

<div>

## <a name="video-conferencing-features"></a>影片會議功能

Lync Server 2013 提供數種功能，可讓您用來為使用者設定影片會議體驗，包括下列專案：

  - **圖庫視圖**    在包含超過兩個人的影片會議中，使用者會自動查看會議中的所有人。 如果會議的參與者超過五位，則最活躍的參與者影片會出現在頂端列，而只有照片顯示給其他參與者。 預設會開啟多方影片。 如需設定或關閉多方影片的詳細資訊，請參閱 [在 Lync Server 2013 中設定影片頻寬](lync-server-2013-configuring-video-bandwidth.md)。

  - **全景影片**    如果在會議室中安裝 RoundTable 的視訊會議裝置，這項功能會提供會議室的完整360度視圖。 只有 RoundTable 裝置可以使用全景影片帶。

  - **僅限簡報者影片模式**    簡報者可以設定會議，只顯示簡報者的影片。 這會在多個視頻資料流程可供使用，並且鎖定于不同來源時，防止大型會議中的干擾。 這種模式也適用于 RoundTable 裝置所捕捉及提供的影片。

  - **HD 影片**    使用者可在雙方通話和多方會議中體驗高達 HD 1080P 的解析度。

  - **影片聚光燈**    簡報者可以設定會議，使會議中的其他參與者只會看到來自選取之參加影片來源之參與者的影片。 這種模式也適用于透過顯示全景影片 RoundTable 裝置所捕獲並提供的影片。

</div>

</div>

<span> </span>

</div>

</div>

</div>


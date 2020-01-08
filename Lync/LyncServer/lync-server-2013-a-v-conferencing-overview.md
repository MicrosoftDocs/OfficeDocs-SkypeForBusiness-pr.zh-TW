---
title: Lync Server 2013 A/V 會議概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d477a8423e7e5ee57e54d0bde584edeb02db4608
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981798"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的 A/V 會議概覽

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-13_

A/V 會議可在使用者之間即時進行音訊與視頻通訊。 部署會議時，您可以選擇啟用和使用網路會議與 A/V 會議，或直接使用網路會議。

若要規劃 A/V 會議，您必須瞭解貴組織所需的會議媒體類型所需的網路頻寬。 這可能包含音訊、影片和全景影片。

在您啟用 A/V 會議的使用者之前，請確認您的網路能夠處理所產生的負載。 如果沒有足夠的網路頻寬，使用者體驗可能會嚴重下降。 您可以使用 [呼叫許可控制] （CAC）來管理由 A/V 會議使用的網路頻寬。 這對受限制的網路非常重要，例如中央與分支網站之間的頻寬連結有限。 如需詳細資訊，請參閱[Lync Server 2013 中的通話許可控制概覽](lync-server-2013-overview-of-call-admission-control.md)。 如需媒體頻寬需求的詳細資料，請參閱[Lync Server 2013 中媒體流量的網路頻寬需求](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)。

如果您在網路上部署音訊會議，您的使用者將需要音訊裝置（例如耳機）參與音訊會議。 如果您要部署視訊會議，您必須部署影片裝置，例如使用者的網路攝影機。 我們建議您使用 Microsoft 針對所有裝置類型認證的整合通訊（UC）裝置，以確保最佳的使用者體驗。 如需 UC 認證裝置的詳細資料，請參閱「Lync 與 Lync 的電話[http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861)和裝置」。 針對音訊或視頻裝置、裝置部署和使用者訓練，都是您考慮並規劃的重要步驟。

下列各節說明音訊與視訊會議的功能，包括管理頻寬及選取適當用戶端的相關資訊。

<div>

## <a name="audio-conferencing-features"></a>音訊會議功能

Lync Server 2013 提供幾項功能，可讓您用來設定使用者的語音會議體驗，包括下列專案：

  - **觀眾**   將簡報者靜音：您可以使用此設定將會議中的所有音訊參與者設為靜音，並將會議放在非簡報者無法取消靜音的狀態中。

  - **會議進入/結束宣告**   如果您已啟用電話撥入式會議，簡報者可以使用此設定來開啟或關閉 [進入] 和 [結束通知]，以在會議進行中時最小化干擾。

  - ****    若要透過撥出簡報者與已獲許可權的出席者來新增使用者，可以在會議中加入 PSTN 號碼，並讓會議撥出給那些號碼。

</div>

<div>

## <a name="video-conferencing-features"></a>視訊會議功能

Lync Server 2013 提供幾項功能，可讓您用來設定使用者的視訊會議體驗，包括下列專案：

  - ****    在視訊會議中有超過兩個人的 [庫] 視圖，使用者會自動查看會議中的每個人。 如果會議的參與者超過五個，則最活躍的參與者的影片會出現在頂端列中，而且只有相片會顯示給其他參與者。 多方影片預設為開啟狀態。 如需設定或關閉多方影片的詳細資料，請參閱[在 Lync Server 2013 中設定影片頻寬](lync-server-2013-configuring-video-bandwidth.md)。

  - **全景影片**   如果您在會議室中安裝了圓桌會議視訊會議裝置，這項功能可提供完整的360度來查看會議室。 全景視頻條只能與圓桌會議裝置一起使用。

  - **簡報者只有視訊模式**   簡報者可以設定會議，以便只顯示簡報者的影片。 這可防止在有多個視頻資料流程時，在大型會議中干擾，並鎖定不同來源。 此模式也適用于透過圓桌裝置捕獲並提供的影片。

  - **HD video**   使用者可以在雙方通話和多方會議中體驗最多 hd 1080p 的解析度。

  - **影片焦點**   簡報者可以設定會議，讓會議中的其他參與者只能看到來自所選參與者的影片。 此模式也適用于透過圓桌會議裝置捕獲並提供的影片，以取得全景影片。

</div>

</div>

<span> </span>

</div>

</div>

</div>


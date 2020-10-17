---
title: Lync Server 2013：規劃會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bf1bf0ce10281bf4d31fc8fdb1be9251b72caf6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507020"
---
# <a name="planning-for-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中規劃會議

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-29_

Lync Server 2013 提供一組豐富的會議功能：

  - Web 會議，包含檔共同作業、應用程式共用和桌面共用。 Lync Server 2013 使用 Office Web Apps 與 Office Web apps Server 來處理 PowerPoint 簡報的共用及呈現。 如需安裝及設定 Office Web Apps Server 的詳細資訊，請參閱設定 [Office Web Apps server 與 Lync server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

  - 音訊/視頻 (A/V) 會議，可讓使用者進行即時音訊或視訊會議，而不需要使用 Microsoft Live Meeting 服務或協力廠商音訊橋的外部服務。

  - 電話撥入式會議，可讓使用者使用公用交換電話網路 (PSTN) 電話加入 Lync Server 2013 會議的音訊部分，而不需要協力廠商音訊會議提供者。

  - 立即訊息 (IM) 會議，其中有兩部以上的參與方在單一 IM 會話中進行通訊。 如需 IM 會議的詳細資訊，請參閱 [在 Lync Server 2013 中規劃前端伺服器、立即訊息及顯示狀態](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)。

Lync Server 2013 支援排程會議和即時會議。

當您部署 Lync Server 2013 （前端伺服器）時，您可以選擇是否也部署 web 會議、A/V 會議和電話撥入式會議功能。 IM 會議功能一定會在 Lync Server 2013 前端伺服器上自動與 IM 交談功能一起部署。

<div>


> [!NOTE]  
> 如果您的部署包含使用 Office Communicator 2007 R2 用戶端組織的會議 (包括 Live Meeting 主控台或 Microsoft Office Outlook 的會議增益集) ，當會議遷移至 Lync Server 2013 後，就會有下列限制： 
> <UL>
> <LI>
> <P>會議中的使用者將無法使用資料共同作業功能，包括檔共同作業、應用程式共用和桌面共用。</P>
> <LI>
> <P>由於 Lync Server 2013 不支援 Office Communicator 2007 R2 用戶端，因此可能會發生穩定性問題。</P></LI></UL>若要避免這些問題，請使用 Lync 2013 的「Lync 2010」或「線上會議增益集」的線上會議增益集，以 Outlook 2010 或 Outlook 2013，重排任何組織使用 Office Communicator 2007 R2 用戶端組織的會議。



</div>

下列各節說明部署各種類型的會議功能（包括規劃程式、元件、硬體和軟體需求，以及部署程式）所需的專案。

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中的會議綜述](lync-server-2013-overview-of-conferencing.md)

  - [在 Lync Server 2013 中定義會議需求](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [Lync Server 2013 中的會議元件與拓撲](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [Lync Server 2013 中的會議技術需求](lync-server-2013-technical-requirements-for-conferencing.md)

  - [Lync Server 2013 中會議的部署檢查清單](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [Lync Server 2013 中的大型會議支援](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


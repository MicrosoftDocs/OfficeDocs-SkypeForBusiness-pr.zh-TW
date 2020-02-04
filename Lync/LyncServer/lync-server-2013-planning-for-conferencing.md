---
title: Lync Server 2013：會議規劃
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
ms.openlocfilehash: 53b7813a197dd7cc3116540c605d7efbdb22a04b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的會議規劃

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-29_

Lync Server 2013 提供了一組豐富的會議功能：

  - 網路會議，包括檔共同作業、應用程式共用和桌面共用。 Lync Server 2013 使用 Office Web Apps 和 Office Web Apps 伺服器來處理 PowerPoint 簡報的共用和轉譯。 如需安裝及設定 Office Web Apps 伺服器的詳細資料，請參閱設定[與 Office Web Apps server 和 Lync Server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

  - 音訊/視頻（A/V）會議，可讓使用者在不需要外部服務（例如 Microsoft Live Meeting 服務或協力廠商音訊橋接器）的情況下進行即時音訊或視訊會議。

  - [電話撥入式會議] 可讓使用者使用公開的交換電話網絡（PSTN）電話（不需要協力廠商音訊會議提供者）加入 Lync Server 2013 會議的音訊部分。

  - [立即訊息（IM）會議]，其中，有兩個以上雙方在單一 IM 會話中進行通訊。 如需 IM 會議的詳細資訊，請參閱[在 Lync Server 2013 中規劃前端伺服器、立即訊息和目前狀態](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)。

Lync Server 2013 支援排程的會議與臨時會議。

當您部署 Lync Server 2013 （前端伺服器）時，您可以選擇是否還要部署網路會議、A/V 會議和電話撥入式會議功能。 IM 會議功能在 Lync Server 2013 前端伺服器上會自動部署，以及 IM 交談功能。

<div>


> [!NOTE]  
> 如果您的部署包含使用 Office Communicator 2007 R2 用戶端（包括 Live Meeting 主控台或 Microsoft Office Outlook 的會議增益集）組織的會議，則在將會議遷移至 Lync 之後，就會有下列限制：Server 2013： 
> <UL>
> <LI>
> <P>會議中的使用者將無法使用資料共同作業功能，包括檔共同作業、應用程式共用和桌面共用。</P>
> <LI>
> <P>在 Lync Server 2013 不支援 Office Communicator 2007 R2 用戶端後，可能會發生穩定性問題。</P></LI></UL>若要避免這些問題，請使用適用于 lync 2013 的線上會議增益集（Lync 2010 或線上會議增益集），重新安排使用 Office Communicator 2007 R2 用戶端與 Outlook 2010 或 Outlook 2013 組織的任何會議。



</div>

下列各節說明部署各種類型的會議功能所需的專案，包括規劃程式、元件、硬體和軟體需求，以及部署程式。

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中的會議概觀](lync-server-2013-overview-of-conferencing.md)

  - [在 Lync Server 2013 中定義會議需求](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [Lync Server 2013 中的會議元件與拓撲](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [Lync Server 2013 中會議的技術需求](lync-server-2013-technical-requirements-for-conferencing.md)

  - [Lync Server 2013 中的會議部署檢查清單](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [Lync Server 2013 中的大型會議支援](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


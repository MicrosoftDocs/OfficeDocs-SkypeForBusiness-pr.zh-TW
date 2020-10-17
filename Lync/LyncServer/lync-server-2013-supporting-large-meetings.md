---
title: Lync Server 2013：支援大型會議
description: Lync Server 2013：支援大型會議。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e116f4668c37fd26eea5cec322a8c6483385e7d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554779"
---
# <a name="supporting-large-meetings-using-lync-server-2013"></a>使用 Lync Server 2013 支援大型會議

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

大型會議因為具有下列特性，所以不適用上一節中所述的測試模型：

  - 會議格式是一對多簡報。

  - 只有一位或少數使用者是簡報者，其他人都是以出席者的身分參加會議。

  - PowerPoint 簡報共用是主要的資料共同作業活動。

  - 音訊是必要的，也可以使用視訊。

  - 代理通常是由會囈召集人或召集人的助理擔任，要在會前做好準備工作。

  - 代理 (非簡報者) 負責會議進行，包括與線上會議連線、確認音訊、視訊和投影片共用的運作、管理大廳與使用者角色、設定或取消設定參與者的靜音功能、記錄問題以及管理錄音。

支援最多 1000 位使用者的大型會議需要同時解決共用硬體模型和非保留模型的相關問題。

為了讓最多1000使用者的會議具有足夠的 CPU 和記憶體資源，主控前端伺服器不應主控任何其他立即訊息 (IM) 和目前狀態或企業語音工作負載。 不論其他的會議大小為何，它也不會主控任何其他會議。 這表示將最多1000使用者的主控會議，需要設定個別的 Lync 伺服器集區，專門主控最多1000使用者的大型會議。

專用於主控大型會議的 Lync 伺服器集區，一次只能裝載一或1000多個會議，所以必須透過帶外排程過程預先保留會議時間，以確保前端伺服器的專屬支援。 如果要同時支援多場大型會議，建議您設定多個專屬的大型會議集區。

我們建議請一位代理來進行及監控大型會議的線上部分。這位代理可能是召集人、召集人或簡報者的代理人或是專屬的大型會議支援團隊的成員，視組織的喜好而定。

在下列各節中，我們將說明如何針對大型會議實施專屬集區，包括使用 Lync Server 2013 以支援大型會議案例的最佳作法。

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中設定大型會議的支援](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [在 Lync Server 2013 中管理大型會議](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


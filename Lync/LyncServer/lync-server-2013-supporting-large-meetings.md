---
title: Lync Server 2013：支援大型會議
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
ms.openlocfilehash: 6d2c36d99bc5af62771aabb643df1223db3a291c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a>使用 Lync Server 2013 支援大型會議

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

大型會議不遵循上一節所述的測試模型，因為它們具有下列特性：

  - 會議格式是一對多份簡報。

  - 一或幾個使用者是簡報者，而其他人則只參與為出席者。

  - PowerPoint 簡報共用是主要的資料共同作業活動。

  - 音訊是必要的，也可能會使用影片。

  - 專屬人員，通常是會議召集人或召集人的助手會提前設定會議。

  - 專用員工（而不是簡報者）會執行會議，包括連線至線上會議、驗證音訊、影片及投影片共用工作、管理大廳及使用者角色、靜音及 unmuting 參與者、提出問題，以及管理錄製（例如適宜.

支援最多1000使用者的大型會議，需要解決與共享硬體模型和無保留模型相關的問題。

若要在最多1000使用者的會議中擁有充足的 CPU 和記憶體資源，託管前端伺服器不應該託管任何其他的立即訊息（IM）與目前狀態或企業語音工作負載。 不論其他會議的規模為何，它也不會主持任何其他會議。 這代表將最多1000個使用者的主機託管會議，需要設定一個專用的 Lync 伺服器池，專門用來託管大型會議，最多1000個使用者。

專用來主持大型會議的 Lync Server pool 應該同時主持一或多達1000的使用者，因此必須透過不限頻帶的排程程式來預先預留會議時間，以確保從前端 Serv 的專屬支援ers. 若要同時支援多個大型會議，建議您設定多個專用大型會議池。

我們建議將一個專門的人員執行並監視大型會議的線上部分。 根據組織的喜好設定，此人可能是召集人、召集人或簡報者的代理人，或是專屬大型會議支援小組的成員。

在下列各節中，我們將說明如何針對大型會議實施專用的 pool，包括使用 Lync Server 2013 支援大型會議案例的最佳做法。

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中設定大型會議的支援](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [在 Lync Server 2013 中管理大型會議](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


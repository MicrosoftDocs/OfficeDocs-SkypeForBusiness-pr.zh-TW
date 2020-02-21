---
title: Lync Server 2013： 支援大型會議
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
ms.openlocfilehash: 949e5fb209722d8a0d8476d017bba1b7144561a4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a>支援使用 Lync Server 2013 的大型會議

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-03_

大型會議因為具有下列特性，所以不適用上一節中所述的測試模型：

  - 會議格式是一對多簡報。

  - 只有一位或少數使用者是簡報者，其他人都是以出席者的身分參加會議。

  - PowerPoint 簡報共用是主要的資料共同作業活動。

  - 音訊是必要的，也可以使用視訊。

  - 代理通常是由會囈召集人或召集人的助理擔任，要在會前做好準備工作。

  - 代理 (非簡報者) 負責會議進行，包括與線上會議連線、確認音訊、視訊和投影片共用的運作、管理大廳與使用者角色、設定或取消設定參與者的靜音功能、記錄問題以及管理錄音。

支援最多 1000 位使用者的大型會議需要同時解決共用硬體模型和非保留模型的相關問題。

有足夠的 CPU 和記憶體資源的最多 1000年會議的使用者，裝載前端伺服器不應該裝載任何其他立即訊息 (IM) 和目前狀態或 Enterprise Voice 工作負載。 它也應未裝載任何其他會議，無論其他會議的大小。 這表示，主控最多 1000 位使用者的會議需要個別的 Lync Server 集區專門用來主控最多 1000 位使用者的大型會議的設定。

專門用來主控大型會議的 Lync 伺服器集區應該裝載一個和只有一個會議最多 1000 位使用者的同時，因此會議時間一定要事先透過排程程序，以確保來自 Front End 服務的專用的支援分隔寬線的出保留電腦。 如果要同時支援多場大型會議，建議您設定多個專屬的大型會議集區。

我們建議請一位代理來進行及監控大型會議的線上部分。這位代理可能是召集人、召集人或簡報者的代理人或是專屬的大型會議支援團隊的成員，視組織的喜好而定。

下列各節中，我們將說明如何實作大型會議，包括使用 Lync Server 2013 以支援大型會議案例的最佳作法的專屬集區。

<div>

## <a name="in-this-section"></a>本章節內容

  - [設定 Lync Server 2013 中的大型會議的支援](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [管理 Lync Server 2013 中的大型會議](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：設定與 Office Web Apps Server 搭配使用的用戶端
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb4b9b881d0f7d469c924a0ba032071092bddbbc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a>針對 Office Web Apps Server 所用的 Lync Server 2013 設定用戶端

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-25_

如果您想讓使用者體驗 Office Web App 伺服器的完整功能，您應該將這些使用者升級至 Microsoft Lync 2013;只有 Lync 2013 的使用者才能在獨立于實際 PowerPoint 簡報的情況下，透過滾動流覽 PowerPoint 投影片。 （也就是說，這些使用者隨時都可以查看簡報中的任何投影片，而不會以任何方式與實際的簡報產生干涉）。未使用 Lync 2013 的使用者仍能加入線上會議並觀看 PowerPoint 簡報;不過，他們將無法獨立滾動投影片，也無法查看投影片的轉場效果或觀賞內嵌的影片。

請注意，Lync 2013 的使用者永遠都能使用這些功能;即使 PowerPoint 簡報者正在執行 Microsoft Lync 2010，也是如此。 如果 PowerPoint 簡報是由執行 Lync 2010 的使用者所託管，Lync Server 2013 將與 Office Web Apps 伺服器協調，以確保 Lync 2013 使用者將會看到該簡報的 Office Web Apps 伺服器版本。 Office Web Apps 伺服器不會針對執行 Lync 2013 以外的用戶端的使用者提供 PowerPoint 服務。 相反地，這些使用者會連接到會議服務器服務，並以與在 Microsoft Lync Server 2010 中相同的方式來查看 PowerPoint 簡報。 這也表示這些使用者將只能存取 Lync Server 2010 提供的更有限的功能。

雖然沒有必要的用戶端設定適用于 Office Web Apps 伺服器（將使用者升級至 Lync 2013），但建議會議出席者升級至 Internet Explorer 9。 雖然您可以使用 Internet Explorer 8 存取會議，但使用該網頁瀏覽器有一些限制。 例如，Internet Explorer 8 的使用者無法將 PowerPoint 階段大小調整為自訂大小;相反地，它們將限制為使用三個預先定義階段大小的其中一個。 同樣地，Internet Explorer 8 使用者將無法播放媒體檔案。

</div>

<span> </span>

</div>

</div>

</div>


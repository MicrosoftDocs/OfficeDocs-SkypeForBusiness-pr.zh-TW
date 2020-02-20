---
title: Lync Server 2013： 使用 Office Web Apps Server 的設定用戶端
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
ms.openlocfilehash: 10ec5ddaca5a8409a18504cb73912d107c9a6455
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a>設定用戶端的 Lync Server 2013 與 Office Web Apps Server 搭配使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-25_

如果您想要體驗 Office Web 應用程式伺服器的完整功能的使用者接著您應該這些使用者升級至 Microsoft Lync 2013;只有 Lync 2013 的使用者將能夠變得獨立的實際的 PowerPoint 簡報的 PowerPoint 投影片的捲軸。 （亦即，這些使用者可以查看在任何時候，簡報中的任何投影片不會以任何方式干擾實際的簡報。）不使用 Lync 2013 的使用者仍然能夠加入線上會議，並檢視 PowerPoint 簡報;不過，他們將無法單獨捲動投影片，也將它們能夠看到投影片切換效果，或檢視內嵌的影片。

請注意，這些功能將會一律可供使用者使用 Lync 2013;即使 PowerPoint 簡報者正在執行 Microsoft Lync 2010，這是，則為 true。 如果正在執行 Lync 2010 使用者所裝載的 PowerPoint 簡報，Lync Server 2013 將居中協調，以確定 Lync 2013 的使用者，將檢視該簡報的 Office Web Apps Server 版本的 Office Web Apps Server。 Office Web Apps Server 不提供 PowerPoint 服務執行 Lync 2013 之外的用戶端的使用者。 相反地，這些使用者連線至會議伺服器服務，以及他們沒有 Microsoft Lync Server 2010 中的相同方式來檢視 PowerPoint 簡報。 這也表示這些使用者只能夠存取 Lync Server 2010 所提供的更有限功能。

雖然用戶端就不需要設定 Office Web Apps server （不是將使用者升級到 Lync 2013），但建議會議出席者是升級為 Internet Explorer 9。 雖然可以使用 Internet Explorer 8 來存取會議，但有一些限制使用該網頁瀏覽器。 例如，使用者的 Internet Explorer 8 無法調整大小以自訂的大小; PowerPoint 階段相反地，他們會使用下列其中一個三個預先定義的階段大小限制。 同樣地，Internet Explorer 8 使用者將無法播放媒體檔案。

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013 web 會議概述
description: Lync Server 2013 web 會議概述。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing overview
ms:assetid: 40616dc4-f705-4890-85bf-79f76a033a9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425913(v=OCS.15)
ms:contentKeyID: 48183949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57efeb9f12321cc28ea87f8672bbcf62aa49c6c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573579"
---
# <a name="overview-of-web-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的 web 會議概述

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-30_

透過 Web 會議，使用者可以在會議期間共用文件 (例如 PowerPoint 簡報) 並以文件進行共同作業。此外，使用者也能與其他人即時共用自己整個或部分桌面，看起來就像所有會議參與者都聚集在同一張會議桌前。

<div>

## <a name="whiteboard-and-annotations"></a>白板和註釋

白板是空白的畫布，可以藉由文字、手寫、繪圖和影像來進行共同作業。在白板上所做的註釋，所有會議參與者都看得到。白板功能可讓會議參與者討論想法、腦力激盪、做註記等，而提升共同作業的效能。

</div>

<div>

## <a name="polling"></a>輪詢

投票功能可讓簡報者快速確認參與者的偏好，進而提高共同作業的效能。在線上會議與交談期間，簡報者可使用投票功能收集參與者的匿名意見。所有簡報者皆可檢視結果，並可選擇隱藏結果或對所有出席者顯示結果。

</div>

<div>

## <a name="application-sharing-and-desktop-sharing"></a>應用程式共用和桌面共用

在會議期間，您可以在多部監視器環境中共用整個桌面、個別應用程式或個別監視器。 除了單純檢視內容之外，其他會議參與者也可要求控制您的螢幕，並且在取得許可的情況下，與內容互動 (包括捲動及編輯)。

<div>


> [!NOTE]  
> 檢視會議的參與者也可取得控制，並在會議期間開始共用內容



</div>

</div>

<div>

## <a name="powerpoint-sharing"></a>PowerPoint 共用

在 Lync 2010 中，以兩種方式中的其中一種方式來查看 PowerPoint 簡報。 針對執行 Lync 2010 的使用者，使用 PowerPoint 97-2003 格式顯示 PowerPoint 簡報，並使用 PowerPoint 檢視器的內嵌副本來查看。 針對執行 Lync Web App 的使用者，PowerPoint 簡報轉換成動態 HTML 檔案，然後使用這些自訂的 DHTML 檔和 Silverlight 的組合來查看。 雖然一般而言效果不錯，此方法確實有些限制：

  -  (提供最佳觀賞體驗) 的內嵌 PowerPoint 檢視器，只適用于 Windows 平臺。

  - 許多行動裝置 (包含某些較流行的行動電話) 不支援 Silverlight。

  - PowerPoint 檢視器和 DHTML/Silverlight 方法並不支援在 PowerPoint 的最新版本中找到的所有功能 (這類幻燈片切換效果和內嵌的影片) 。

為了協助解決這些問題，以及改善使用者呈現或查看 PowerPoint 簡報的整體體驗，Lync Server 2013 使用 Office Web Apps 與 Office Web Apps Server 來處理 PowerPoint 簡報。 此新方法的主要優勢如下：

  - 更高的顯示解析度，更佳的 PowerPoint 功能支援，例如動畫、投影片切換及內嵌影片。

  - 更多行動裝置可存取這些簡報。 這是因為 Lync Server 2013 使用 standard DHTML 和 JavaScript 來廣播 PowerPoint 簡報，而不是自訂的 DHTML 和 Silverlight。

  - 擁有適當權限的使用者可以不影響簡報本身，自行捲動 PowerPoint 簡報。例如，當 Ken Myer 在進行投影片放映時，Pilar Ackerman 可以檢視任何想看的投影片，而不會影響 Ken 的簡報。

</div>

</div>

<span> </span>

</div>

</div>

</div>


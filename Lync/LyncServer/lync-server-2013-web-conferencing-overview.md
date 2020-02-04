---
title: Lync Server 2013 web 會議概述
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
ms.openlocfilehash: de63cb5bf2578359d012cda72b07b8fc7f62880d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-web-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的 web 會議概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-30_

透過網路會議，使用者可以在會議期間，在檔（例如 PowerPoint 簡報）上共用及共同作業。 此外，使用者也可以即時共用全部或部分的桌面，看起來好像會議中的人員是在會議中的同一個表格周圍收集。

<div>

## <a name="whiteboard-and-annotations"></a>白板和批註

白板是可用於共同作業的空白畫布，包括文字、筆跡、繪圖和影像。 所有會議參與者都能看到在白板上所做的批註。 「白板」功能可讓會議參與者討論想法、集體討論、記錄筆記等，以增強共同作業。

</div>

<div>

## <a name="polling"></a>投票

[輪詢] 功能可讓簡報者快速判斷參與者的喜好，以增強共同作業。 在線上會議與交談期間，簡報者可以使用 [輪詢] 來收集來自參與者的匿名回應。 所有簡報者都可以看到結果，並可以隱藏結果或將結果顯示給所有出席者。

</div>

<div>

## <a name="application-sharing-and-desktop-sharing"></a>應用程式共用和桌面共用

在會議期間，您可以在多部監視器的環境中共用整個桌面、個別的應用程式或個別的監視器。 除了直接查看內容之外，會議中的其他參與者也可以要求您的螢幕進行控制，並在許可權中與內容互動（包括滾動和編輯）。

<div>


> [!NOTE]  
> 正在觀看會議的參與者也可以在會議期間接管並開始共用內容



</div>

</div>

<div>

## <a name="powerpoint-sharing"></a>PowerPoint 共用

在 Lync 2010 中，PowerPoint 簡報是以兩種方式之一來查看。 針對執行 Lync 2010 的使用者，PowerPoint 簡報是使用 PowerPoint 97-2003 格式顯示，並使用 PowerPoint 檢視器的內嵌複本來查看。 針對執行 Lync Web App 的使用者，PowerPoint 簡報已轉換成動態 HTML 檔案，然後使用這些自訂 DHTML 檔案和 Silverlight 的組合來查看。 雖然這個方法通常有效，但有一些限制：

  - 內嵌的 PowerPoint 檢視器（提供最佳的流覽體驗）只適用于 Windows 平臺。

  - 許多行動裝置（包括一些較流行的行動電話）不支援 Silverlight。

  - PowerPoint 檢視器和 DHTML/Silverlight 方法不支援在新版 PowerPoint 中找到的所有功能（例如投影片轉場及內嵌影片）。

為了協助解決這些問題，以及改善顯示或查看 PowerPoint 簡報之使用者的整體體驗，Lync Server 2013 使用 Office Web Apps 和 Office Web Apps 伺服器來處理 PowerPoint 簡報。 在其他優點中，此新方法可讓您：

  - 更高解析度顯示及更佳的 PowerPoint 功能支援（例如動畫、投影片轉場及內嵌的影片）。

  - 其他行動裝置可存取這些簡報。 這是因為 Lync Server 2013 使用標準 DHTML 和 JavaScript 來廣播 PowerPoint 簡報，而不是自訂的 DHTML 和 Silverlight。

  - 具有適當許可權的使用者，可在獨立于簡報本身的情況下滾動流覽 PowerPoint 簡報。 例如，當 Ken Myer 正在呈現其投影片放映時，Pilar 方可以查看任何您想要的投影片，而不會影響 Ken 的簡報。

</div>

</div>

<span> </span>

</div>

</div>

</div>


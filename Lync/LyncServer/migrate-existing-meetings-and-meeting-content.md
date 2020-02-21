---
title: 移轉現有的會議與會議內容
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51f690d492d685c162d7de1e76f474b609662244
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a>移轉現有的會議與會議內容

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-22_

當使用者帳戶從 Lync Server 2010 移至 Lync Server 2013 的伺服器時，與該使用者帳戶移下列資訊：

  - **使用者已排定的會議**。包含移動會議目錄及會議資料。

  - **使用者的個人識別碼 (PIN)**。直到過期或使用者要求新 PIN 前，使用者目前的 PIN 都持續有效。

下列使用者帳戶資訊不會移到新的伺服器。

  - **會議內容**。若要移動會議期間分享的內容。例如 PowerPoint、白板、附件或投票資料，請在 **Move-CsUser** Cmdlet 中使用 **-MoveConferenceData** 參數。

</div>

<span> </span>

</div>

</div>

</div>


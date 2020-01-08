---
title: 移轉現有的會議與會議內容
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38b4f374aef66fa95d49b2330a07f9def4135328
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a>移轉現有的會議與會議內容

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

當使用者帳戶從 Lync Server 2010 移至 Lync Server 2013 伺服器時，下列資訊會與該使用者帳戶一起移動：

  - **已由使用者排程的會議**。 這包括移動會議目錄及會議資料。

  - **使用者的個人身分識別號碼（PIN）**。 使用者目前的 PIN 會持續起作用，直到過期為止，或使用者要求新的 PIN。

下列使用者帳戶資訊不會移至新的伺服器。

  - **會議內容**。 若要移動在會議期間共用的內容（例如 PowerPoint、白板、附件或投票資料），請使用 **-MoveConferenceData**參數做為**move-csuser** Cmdlet 的一部分。

</div>

<span> </span>

</div>

</div>

</div>


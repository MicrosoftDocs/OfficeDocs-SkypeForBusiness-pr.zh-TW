---
title: 移轉現有的會議與會議內容
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d811a9e66f368752107020de48e5e09dd641115
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a>移轉現有的會議與會議內容

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

當使用者帳戶從 Lync Server 2010 移至 Lync Server 2013 伺服器時，下列資訊會隨該使用者帳戶一起移動：

  - **Meetings already scheduled by the user**. This includes moving the conferencing directories and conferencing data.

  - **User’s personal identification number (PIN)**. The user’s current PIN continues to work until it expires or the user requests a new PIN.

下列使用者帳戶資訊不會移到新的伺服器。

  - **Meeting content**. In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.

</div>

<span> </span>

</div>

</div>

</div>


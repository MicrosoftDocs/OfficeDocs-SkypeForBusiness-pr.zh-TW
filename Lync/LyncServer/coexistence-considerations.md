---
title: 共存考量
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e53c57b90a85024ed5375129ce23c6ff0060edc4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a>共存考量

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

遷移之後，只有 Lync Server 2013、持續聊天伺服器池會存在，而且您可以停止舊版部署。

在遷移完成之前，如果您已完全解除目前的群組聊天伺服器部署，您可能會有下列任何一種部署：

  - Lync Server 2013，持續聊天伺服器池，必須駐留在 Lync Server 2013 池。

  - Lync Server 2010，群組聊天池，必須駐留在 Lync Server 2010 池。

  - Office 通訊伺服器 2007 R2 群組聊天池，必須駐留在 Office 通訊伺服器 2007 R2 pool。

這些部署可以並排存在。 不過，在一個部署中的類別、會議室和增益集並不與隨附部署中的專案互動。

使用手動設定，舊版用戶端（群組聊天用戶端）可以一次連線到一個池，以進行 Office 通訊伺服器 2007 R2、Lync Server 2010、群組聊天或 Lync Server 2013。

Lync 2013 （用戶端）只能與 Lync Server 2013、持續聊天伺服器池進行互動，而不能與舊版群組聊天伺服器池互動。 若要在 Lync 2013 （用戶端）中使用持續聊天，使用者必須駐留在 Lync 2013，且由原則啟用。

</div>

<span> </span>

</div>

</div>

</div>


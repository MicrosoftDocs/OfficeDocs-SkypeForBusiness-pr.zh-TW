---
title: 共存考慮
description: 共存考慮。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: fd1f9525b37bdee3249e0e47352fdea1bc7f012f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547029"
---
# <a name="coexistence-considerations"></a>共存考慮

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

遷移後，只會存在 Lync Server 2013、Persistent Chat Server 集區，您也可解除委任舊版部署。

在遷移完成之前以及完全解除委任目前的群組聊天伺服器部署之前，您可能會有下列任何部署：

  - Lync Server 2013，Persistent Chat Server 集區，必須裝載在 Lync Server 2013 集區上。

  - Lync Server 2010，群組聊天集區，必須裝載在 Lync Server 2010 集區上。

  - Office 通訊伺服器 2007 R2 群組聊天集區，必須位於 Office 通訊伺服器 2007 R2 集區。

這些部署可能並排存在。 不過，一個部署中的類別、聊天室及增益集不會與伴隨之部署中的增益集進行互動。

使用手動設定時，舊版用戶端 (群組聊天用戶端) 可以一次連線至一個集區，以進行 Office 通訊伺服器 2007 R2、Lync Server 2010、群組聊天或 Lync Server 2013。

Lync 2013 (用戶端) 只能與 Lync Server 2013、Persistent Chat Server 集區互動，而不能與舊版群組聊天伺服器集區互動。 若要在 Lync 2013 (用戶端) 中使用持續性聊天，使用者必須在 Lync 2013 上，並由原則啟用。

</div>

<span> </span>

</div>

</div>

</div>


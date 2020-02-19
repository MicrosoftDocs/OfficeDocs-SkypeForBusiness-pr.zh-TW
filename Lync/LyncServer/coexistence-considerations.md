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
ms.openlocfilehash: 7502e74eb1bb4c2a5e7889fc46cb4419101bf4a3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a>共存考量

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-06_

在移轉之後，只有在 Lync Server 2013，Persistent Chat Server 集區會存在，而且您可以解除委任舊版部署。

移轉完成之前及完全解除委任目前 Group Chat 伺服器部署之前，您可能會有任何下列的部署：

  - Lync Server 2013，Persistent Chat Server 集區，必須裝載於 Lync Server 2013 集區。

  - Lync Server 2010，Group Chat 集區，必須裝載於 Lync Server 2010 集區。

  - Office Communications Server 2007 R2 群組聊天集區，必須裝載於 Office Communications Server 2007 R2 集區。

這些部署可以並排存在。 不過類別、 聊天室及增益集一個部署中不互動中隨附的部署。

使用手動組態時，舊版用戶端 （Group Chat 用戶端） 可以連線至一個集區，一次 Office Communications Server 2007 R2、 Lync Server 2010，Group Chat，或 Lync Server 2013。

Lync 2013 （用戶端） 可以只與 Lync Server 2013，Persistent Chat Server 集區，不與舊版的 Group Chat Server 集區互動。 若要使用常設聊天室 Lync 2013 （用戶端） 中，使用者必須位於 Lync 2013 並啟用原則。

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：IPv6 的移轉與共存考量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8adf81df14d5c87eb2b54b63d9a58fc1b6f5b97e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a>Lync Server 2013 中 IPv6 的移轉與共存考量

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-14_

Lync Server 2010 或 Office 通訊伺服器不支援 IP 版本6（IPv6）。 針對試驗目的，您可以測試 Lync Server 2010 和 Lync Server 2013 雙堆疊共存。 我們建議您先將指定中央網站的所有池升級至 Lync Server 2013，然後再針對任何一個池啟用 IPv6 （雙堆疊網路）。 如果您只需要設定適用于 IPv6 的 pool，我們建議您在實驗室環境中設定 IPv6 專用池以進行測試。

在遷移和共存期間支援下列案例：

  - Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器2007在 IPv4 模式中與 Lync Server 2013 共存的 R2 池（在雙堆疊模式中共存）。

  - 如果僅限 IPv6 池是各自為政的，則 Lync Server 2013 池處於僅限 IPv6 模式。

</div>

<span> </span>

</div>

</div>

</div>


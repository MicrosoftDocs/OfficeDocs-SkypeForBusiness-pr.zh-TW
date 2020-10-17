---
title: Lync Server 2013： IPv6 的遷移和共存考慮
description: Lync Server 2013： IPv6 的遷移和共存考慮。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8618cc14ff3c2467ea41df34e39f5094d1206dc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560989"
---
# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a>Lync Server 2013 中 IPv6 的遷移和共存考慮

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-14_

Lync Server 2010 或 Office 通訊伺服器不支援 IP 版本 6 (IPv6) 。 出於試驗目的，您可以測試 Lync Server 2010 和 Lync Server 2013 雙堆疊共存。 建議您將指定中央網站的所有集區升級至 Lync Server 2013，然後再為任何集區啟用 IPv6 (雙堆疊網路) 。 [！附注] 如果您只需要為 IPv6 設定集區，建議您在實驗室環境中設定 IPv6 專用集區以進行測試。

在遷移和共存期間支援下列案例：

  - Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器 2007 R2 集區中 IPv4 模式，與 Lync Server 2013 在雙堆疊模式中共存。

  - 在僅限 IPv6 模式中的 Lync Server 2013 集區，如果僅限 IPv6 集區為孤立的集區。

</div>

<span> </span>

</div>

</div>

</div>


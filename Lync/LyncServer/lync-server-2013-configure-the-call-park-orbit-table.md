---
title: Lync Server 2013：設定通話駐留軌道表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 417fb90feb9f12f8c2776518fa8fefffae7ff003
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a>在 Lync Server 2013 中設定通話駐留軌道表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-10_

通話寄存使用 [軌道式] 進行停車通話。 您必須先設定 [通話公園軌道] 表格，才能停止並取回通話。 您必須指定貴組織將針對停車通話保留的延伸數位（軌道式）範圍，並指定哪個呼叫駐留器池處理每個範圍，以定義這些範圍的路線。 當您定義軌道範圍時，目標是有足夠的 [軌道式]，所以任何一個軌道都不會過快地重複使用，但卻不是您要限制使用者或其他服務可用的延伸數目。 您可以為部署通話駐留應用程式的每個 Lync 伺服器池建立多個通話駐留軌道範圍。 每個呼叫公園的軌道範圍都必須有全域唯一的名稱，以及一組唯一的延伸。

<div>


> [!IMPORTANT]  
> 軌道範圍通常會包含100或更少的軌道式。 每個範圍都可以大許多，只要它小於每個範圍的10000軌道式，且每個池子的每個泳池不超過50000的 [軌道式]。 如果範圍太小，則會更快速地重複使用 [軌道式]。



</div>

針對您的軌道範圍，使用虛擬延伸組塊（沒有指派使用者或電話的延伸）。

<div>


> [!NOTE]  
> 在 [通話駐留軌道] 表格中，將直向內撥（所做的）號碼指派為軌道編號，不受支援。



</div>

<div>

## <a name="in-this-section"></a>本節內容

[在 Lync Server 2013 中建立或修改通話駐留軌道的範圍](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


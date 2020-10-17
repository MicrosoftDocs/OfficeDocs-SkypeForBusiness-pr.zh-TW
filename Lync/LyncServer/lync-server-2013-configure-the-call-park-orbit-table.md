---
title: Lync Server 2013：設定通話駐留軌道表格
description: Lync Server 2013：設定通話駐留軌道表格。
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
ms.openlocfilehash: ce9fb35c2958a426888d83d075064c88ddae4bfa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544979"
---
# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a>在 Lync Server 2013 中設定通話駐留軌道表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-10_

通話駐留使用軌道進行停車通話。 您必須先設定通話駐留軌道表格，使用者才能駐留及取回通話。 您必須指定您的組織將保留用於停車通話的分機號碼範圍 (的軌道式) ，並指定處理每個範圍的通話駐留集區，以定義這些範圍的路由。 當您定義軌道範圍時，目標是具有足夠的軌道，因此，任何一個軌道都不會很快地重複使用，但卻不是這麼多的軌道來限制使用者或其他服務可使用的延伸數目。 您可以針對部署通話駐留應用程式的每個 Lync 伺服器集區，建立多個通話駐留軌道範圍。 每個通話駐留軌道範圍必須具有全域唯一名稱和一組唯一的延伸。

<div>


> [!IMPORTANT]  
> 軌道範圍通常會包含100或更少的軌道。 每個範圍都可以大量增加，只要小於每個範圍的10000軌道的最大值，且每個集區的每個集數目小於50000的軌道。 如果範圍太小，則軌道的重複使用速度變快。



</div>

使用虛擬分機區塊 (未獲指派使用者或電話的分機) 用於軌道範圍。

<div>


> [!NOTE]  
> 指派直接向內撥號 (，不支援通話駐留軌道表格中的軌道編號) 數位。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

[在 Lync Server 2013 中建立或修改通話駐留軌道範圍](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


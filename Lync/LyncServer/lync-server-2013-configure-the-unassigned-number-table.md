---
title: Lync Server 2013： 設定未指派號碼表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the unassigned number table
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48185908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef82a5976769543f83dc4656cf09eb64b94d7571
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a>在 Lync Server 2013 中設定未指派號碼表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-30_

在 Lync Server 2013 中，您可以指定至適用於您的組織，但不是會指派給使用者或電話的電話號碼的傳入呼叫會發生什麼事。 來電者可以聽到訊息，或可以路由傳送到其他目的地，或兩者。

設定未指派號碼表的方式取決於其使用方式。 您可以設定包含組織所有有效分機號碼、只包含未指派的分機號碼，或包含結合這兩種類型之號碼的表格。 未指派號碼表可以同時包含已指派和未指派的號碼，但是只有在來電者撥打目前未指派的號碼時才會叫用。 如果您在未指派號碼表中納入所有有效的分機號碼，可以指定每次某人離開組織時要執行的動作，而不必重新設定表格。 如果您在表格中包含未指派的擴充功能，您可以修改的週期定期發生特定的數字的巨集指令。 例如，如果您變更分機的客戶服務台人員時，您可以在表格中包含舊的客戶健保號碼，並再將其指派給提供新的數字的宣告。

<div>


> [!IMPORTANT]  
> 設定未指派號碼表之前，您的系統必須已定義宣告或設定 Exchange 整合通訊 (UM) 自動語音應答。



</div>

<div>


> [!TIP]  
> 如果某人撥打未指派的號碼，Lync Server 會搜尋從上到下未指派號碼表，並使用第一個比對範圍。 因此，應為表格中的最後一個範圍指定您想要做為最後的手段執行巨集指令。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

[建立或修改 Lync Server 2013 中的未指派號碼範圍](lync-server-2013-create-or-modify-an-unassigned-number-range.md)[建立 Lync Server 2013 中的宣告](lync-server-2013-create-an-announcement.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


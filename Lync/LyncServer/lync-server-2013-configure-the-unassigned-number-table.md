---
title: Lync Server 2013：設定未指派號碼表
description: Lync Server 2013：設定未指派號碼表。
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
ms.openlocfilehash: 8ed8ba6c709311dab791b711d6ba69aaff72a630
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544889"
---
# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a>在 Lync Server 2013 中設定未指派號碼表

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-30_

在 [Lync Server 2013] 中，您可以指定對組織有效的電話號碼撥入電話號碼，但不會將其指派給使用者或電話。 來電者可能會聽到訊息，或可路由傳送至其他目的地，或兩者皆有。

設定未指派號碼表的方式取決於其使用方式。 您可以設定包含組織所有有效分機號碼、只包含未指派的分機號碼，或包含結合這兩種類型之號碼的表格。 未指派號碼表可以同時包含已指派和未指派的號碼，但是只有在來電者撥打目前未指派的號碼時才會叫用。 如果您在未指派號碼表中納入所有有效的分機號碼，可以指定每次某人離開組織時要執行的動作，而不必重新設定表格。 如果您在表格中包含未指派的副檔名，您可以修改針對特定數位所發生的動作。 例如，如果您變更客戶服務服務台的分機號碼，您可以在資料表中包含舊的客戶服務號碼，然後將其指派給提供新號碼的宣告。

<div>


> [!IMPORTANT]  
> 在您設定未指派的號碼表之前，您的系統必須已定義宣告，或是已設定 Exchange 整合通訊 (UM) 自動語音應答。



</div>

<div>


> [!TIP]  
> 當某人呼叫未指派的號碼時，Lync Server 會從上到下搜尋未指派號碼表格，並使用第一個相符的範圍。 因此，應為表格中的最後一個範圍指定您想要執行做為最後一個手段的動作。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

[在 lync server 2013 中建立或修改未指派號碼範圍在](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [lync server 中建立宣告 2013](lync-server-2013-create-an-announcement.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：設定未指派號碼表
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
ms.openlocfilehash: b99679d439257b54b6bb40d8e724bb63da4a1ea5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a>在 Lync Server 2013 中設定未指派號碼表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-30_

在 Lync Server 2013 中，您可以指定撥入電話號碼對貴組織有效，但不會指派給使用者或電話的電話號碼。 來電者可以聽到訊息，或者可以傳送到另一個目的地，或同時路由到其他目的地。

設定未指派號碼表的方式取決於其使用方式。 您可以設定包含組織所有有效分機號碼、只包含未指派的分機號碼，或包含結合這兩種類型之號碼的表格。 未指派號碼表可以同時包含已指派和未指派的號碼，但是只有在來電者撥打目前未指派的號碼時才會叫用。 如果您在未指派號碼表中納入所有有效的分機號碼，可以指定每次某人離開組織時要執行的動作，而不必重新設定表格。 如果您在表格中包含未指定的延伸，您可以修改針對特定數位所發生的動作。 例如，如果您變更客戶服務台的延伸，您可以在表格中包含舊的客戶服務編號，然後將它指派給提供新號碼的宣告。

<div>


> [!IMPORTANT]  
> 在您設定 [未指派的號碼] 資料表之前，您的系統必須已定義宣告，或已設定 Exchange 整合通訊（UM）自動語音應答。



</div>

<div>


> [!TIP]  
> 當某人呼叫未指派的號碼時，Lync Server 會從上到下搜尋 [未指定的號碼] 資料表，並使用第一個相符的範圍。 因此，您想要執行的動作必須針對表格中的最後一個範圍指定，才能做為最後一個手段。



</div>

<div>

## <a name="in-this-section"></a>本節內容

[在 Lync server 2013 中建立或修改未指定的數位範圍在](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [lync server 2013 中建立宣告](lync-server-2013-create-an-announcement.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


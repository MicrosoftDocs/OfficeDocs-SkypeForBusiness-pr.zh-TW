---
title: Lync Server 2013：音訊/視頻（A/V）邊緣伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce9738dbb11ce731ac832a5529d2013f3f9b2907
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a>Lync Server 2013 中的音訊/視頻（A/V）邊緣伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

A/V Edge 服務為內部使用者（登入組織網路的使用者）提供一種方式，與外部使用者（沒有登入組織網路的使用者）共用音訊和影片。 除了音訊和影片，A/V 邊緣服務也會提供對此類內容的支援。

A/V 邊緣服務的主要管理方式是使用 A/V 邊緣設定;這些設定可讓您管理每個埠與每個使用者所分配的頻寬上限，以及指定必須在該權杖更新之前，使用驗證權杖的時間長度。 A/V 邊緣設定可套用至網站或個別的 A/V 邊緣伺服器。 確定哪個設定的優先順序會優先時，請使用下列指南：

  - 在服務作用中設定的設定（也就是在個別伺服器上）會優先處理所有專案。

  - 在網站範圍設定的設定，會優先于在全域範圍內設定的設定。 不過，服務範圍設定也會取代網站範圍設定。

  - 只有在個別伺服器上沒有設定任何服務設定，而且該伺服器所在之網站沒有網站設定的情況下，全域作用中的設定才會使用。

只有使用 Lync Server PowerShell 和 CsAVEdgeConfiguration Cmdlet，才能管理 A/V 邊緣服務。

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中傳回 A/V 邊緣伺服器配置資訊](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [在 Lync Server 2013 中建立或修改 A/V 邊緣伺服器設定的集合](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [刪除 Lync Server 2013 中現有的 A/V 邊緣伺服器設定集合](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


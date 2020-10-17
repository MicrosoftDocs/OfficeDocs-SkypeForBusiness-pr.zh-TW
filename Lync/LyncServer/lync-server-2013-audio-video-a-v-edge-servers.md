---
title: Lync Server 2013： Audio/Video (A/V) Edge Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a83aa6c21be0a1055be091ab7195f3c03c4c6e2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508270"
---
# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a>在 Lync Server 2013 中 Audio/Video (A/V) Edge Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

A/V Edge 服務可讓內部使用者 (即已登入您組織網路的使用者) 將音訊和視訊共用給外部使用者 (即未登入您組織網路的使用者)。 除了音訊和影片之外，A/V Edge service 也會提供對此類內容的支援，以進行桌面共用和檔案傳輸。

A/V Edge service 主要使用 A/V Edge 設定進行管理;這些設定可讓您管理每個埠或每位使用者所要分配的最大頻寬量，並指定在必須更新權杖之前，可使用的驗證權杖的時間長度。 A/V Edge 設定設定可以套用到網站或個別 A/V Edge server。 決定哪個設定集合優先時，請使用下列指南：

  - 服務範圍 (亦即在個別伺服器) 中的設定優先使用。

  - 在網站範圍設定的設定優先于在全域範圍設定的設定。 不過，服務範圍設定也會取代網站範圍設定。

  - 若個別伺服器裡未進行任何服務設定，且該伺服器所處的網站無任何網站設定，才會使用全域範圍的設定。

您只能使用 Lync Server PowerShell 和 CsAVEdgeConfiguration Cmdlet 來管理 A/V Edge service。

<div>

## <a name="in-this-section"></a>本章節內容

  - [傳回 Lync Server 2013 中 A/V Edge Server 設定資訊](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [在 Lync Server 2013 中建立或修改 A/V Edge Server 設定的集合](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [在 Lync Server 2013 中刪除現有的 A/V Edge Server 設定集合集合](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013： 音訊/視訊 (A / V) Edge Server
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
ms.openlocfilehash: 1262ee1a2db12569538f499731de53a9da133c98
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a>音訊/視訊 (A / V) Lync Server 2013 中的 Edge Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

A/V Edge 服務可讓內部使用者 (即已登入您組織網路的使用者) 將音訊和視訊共用給外部使用者 (即未登入您組織網路的使用者)。 除了音訊與視訊、 A / V Edge service 還能支援這類事項桌面共用與檔案傳輸時必須使用。

A / V Edge service 主要是由使用 A / V Edge 組態;這些設定可讓您管理的每個連接埠要配置的頻寬量上限和每位使用者，以及指定可以先使用的驗證權杖的時間長度必須更新權杖。 A / V Edge 組態設定可以套用至網站或個別的 A / V Edge server。 在決定哪一個設定集合會優先時，使用下列快顯功能表：

  - 服務範圍 (亦即在個別伺服器) 中的設定優先使用。

  - 在網站範圍設定的設定優先於全域範圍設定的設定。 不過，服務範圍設定也會取代網站範圍設定。

  - 若個別伺服器裡未進行任何服務設定，且該伺服器所處的網站無任何網站設定，才會使用全域範圍的設定。

A / V Edge service 只能由使用 Lync Server PowerShell 與 CsAVEdgeConfiguration cmdlet 進行管理。

<div>

## <a name="in-this-section"></a>本章節內容

  - [傳回 A / V Edge Server 在 Lync Server 2013 中的組態資訊](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [建立或修改一群 A / V Edge Server 組態設定 Lync Server 2013 中](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [刪除現有集合的 A / V Edge Server 組態設定 Lync Server 2013 中](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


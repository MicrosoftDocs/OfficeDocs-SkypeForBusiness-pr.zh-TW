---
title: Lync Server 2013：為分支使用者建立 VoIP 路由原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f53e69069bc1f39f84c057f1e90882d5ae0d65d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a>在 Lync Server 2013 中為分支使用者建立 VoIP 路由原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-23_

我們建議針對分支網站上的使用者建立個別的 [語音 over IP] （VoIP）原則。 此原則應該包含來自 Survivable 分支裝置閘道的出口，或 Survivable 分支伺服器外部閘道，以及從中央網站上的閘道傳出的備份路由。 不論使用者的登錄位置為何，無論是在 Survivable 分支裝置或 Survivable 分支伺服器上的註冊機構或中央網站的備份註冊機構群集上，使用者的 VoIP 原則都將會生效。

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a>為分支使用者設定 VoIP 路由策略

1.  建立使用者層級撥號方案並將其指派給分支使用者。 （請參閱在 [操作] 檔的[Lync Server 2013 中建立撥號方案](lync-server-2013-create-a-dial-plan.md)）。

2.  指派與使用者在該網站上的撥號習慣相對應的正常化規則。 如果 Survivable 分支裝置或 Survivable 分支伺服器使用者無法容錯移轉到中央網站上的 [備份註冊機] 池，則相同的撥號方案將會生效。 （請參閱在 [操作] 檔的[Lync Server 2013 中建立撥號方案](lync-server-2013-create-a-dial-plan.md)）。

3.  設定從 Survivable 分支裝置閘道或 Survivable 分支伺服器外部閘道 egresses 的語音路由。 （請參閱在 Operations 檔中在[Lync Server 2013 中建立語音信箱](lync-server-2013-create-a-voice-route.md)。）

4.  在 Survivable 分支裝置上設定備份呼叫路由，或 Survivable 分支伺服器閘道，以指向中央網站上的 [備份註冊器] 池（collocated 與中繼伺服器）。 （請參閱您的 Survivable 分支裝置或 Survivable 分支伺服器廠商檔。）
    
    <div>
    

    > [!NOTE]  
    > 此備份呼叫路線設定可協助確保當 Survivable 分支機搆或 Survivable 分支伺服器無法使用時，分支使用者的撥入呼叫可以正常運作（例如，如果是為了進行維護）。 如果 Survivable 分支裝置或 Survivable 分支伺服器上的註冊機構和轉送器伺服器無法使用，而且使用者已在中央網站上的 [備份註冊機構] 池中註冊，則輸入通話仍會傳送給使用者。

    
    </div>

**後續步驟**：[在 Lync Server 2013 中設定語音信箱重新路由設定](lync-server-2013-configure-voice-mail-rerouting-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：為分支使用者建立 VoIP 路由原則
description: Lync Server 2013：為分支使用者建立 VoIP 路由原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c39cff86d9ede957fa99e7955d8a87172380f963
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551079"
---
# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a>在 Lync Server 2013 中建立分支使用者的 VoIP 路由原則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-23_

我們建議您為分支網站的使用者建立個別的 VoIP 原則。 此原則應包含從中央網站之 Survivable Branch 裝置閘道或 Survivable Branch 伺服器外部閘道的傳出的路由，以及從閘道傳出的備份路由。 不論使用者登錄的位置為何，不論是在 Survivable Branch 裝置或 Survivable Branch Server 上的註冊機上，或是在中央網站的備份註冊機構叢集上，使用者的 VoIP 原則都是有效的。

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a>若要為分支使用者設定 VoIP 路由原則

1.  建立使用者層級撥號對應表，並將其指派給分支使用者。  (請參閱 Operations 檔中的在 [Lync Server 2013 中建立撥號](lync-server-2013-create-a-dial-plan.md) 對應表。 ) 

2.  指派與該網站上使用者撥號習慣對應的正規化規則。 如果 Survivable 分支裝置或 Survivable Branch 伺服器使用者容錯移轉至中央網站的備份註冊機構集區，則相同的撥號對應表會生效。  (請參閱 Operations 檔中的在 [Lync Server 2013 中建立撥號](lync-server-2013-create-a-dial-plan.md) 對應表。 ) 

3.  設定從 Survivable Branch 裝置閘道或 Survivable Branch Server 外部閘道 egresses 的語音路由。  (請參閱 Operations 檔中的在 [Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md) 。 ) 

4.  設定 Survivable Branch 裝置或 Survivable Branch Server 閘道上的備份呼叫路由，以指向中央網站上的轉送伺服器)  (組合的備份註冊機集區。  (請參閱 Survivable Branch 裝置或 Survivable Branch Server 廠商檔。 ) 
    
    <div>
    

    > [!NOTE]  
    > 此備份呼叫路由設定可協助確保當 Survivable Branch 裝置或 Survivable Branch 伺服器無法使用時，分支使用者的輸入呼叫可以運作 (例如，如果已關機以進行維護) 。 如果無法使用 Survivable Branch 裝置或 Survivable Branch Server 上的註冊機構和轉送伺服器，且使用者已向中央網站的備份註冊機構集區註冊，則輸入呼叫仍可路由傳送給使用者。

    
    </div>

**後續步驟**： [在 Lync Server 2013 中設定語音信箱重新路由設定](lync-server-2013-configure-voice-mail-rerouting-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


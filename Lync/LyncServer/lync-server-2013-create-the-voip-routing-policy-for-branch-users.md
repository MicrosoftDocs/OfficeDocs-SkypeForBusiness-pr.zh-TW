---
title: Lync Server 2013： 建立 VoIP 路由原則為分支使用者
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
ms.openlocfilehash: c55f52c104c4a9e49abb8b4989cfa4901dfe02dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a>在 Lync Server 2013 中建立分支使用者 VoIP 路由原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-23_

我們建議您為分支網站的使用者建立個別的 VoIP 原則。 此原則應該包含從 Survivable Branch Appliance 閘道或 Survivable Branch 伺服器外部閘道的輸出路由和備份來自閘道在中央網站的輸出路由。 不論其中使用者註冊，不論是在備份登錄器叢集在中央網站，或 Survivable Branch Appliance 或 Survivable Branch 伺服器上之登錄器上使用者的 VoIP 原則一律是作用中。

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a>若要為分支使用者設定 VoIP 路由原則

1.  建立使用者層級撥號對應表，並將其指派給分公司使用者。 （請參閱[建立撥號對應表 Lync Server 2013 中](lync-server-2013-create-a-dial-plan.md)的作業文件中。）

2.  指派與該網站上使用者撥號習慣對應的正規化規則。 如果 Survivable Branch Appliance 或 Survivable Branch 伺服器的使用者容錯移轉至中央網站的備份登錄器集區，相同的撥號對應表中會生效。 （請參閱[建立撥號對應表 Lync Server 2013 中](lync-server-2013-create-a-dial-plan.md)的作業文件中。）

3.  設定從 Survivable Branch Appliance 閘道或 Survivable Branch 伺服器的外部閘道 egresses 語音路由。 （請參閱[建立 Lync Server 2013 中的語音路由](lync-server-2013-create-a-voice-route.md)作業 > 文件中）。

4.  Survivable Branch Appliance 或 Survivable Branch 伺服器閘道指向備份登錄器集區 （與中繼伺服器組合） 在中央網站上設定的備份呼叫路由。 （請參閱 Survivable Branch Appliance 或 Survivable Branch 伺服器廠商文件）。
    
    <div>
    

    > [!NOTE]  
    > 此備份通話路由設定有助於確保與分支網站使用者的輸入的呼叫正常的 Survivable Branch Appliance 或 Survivable Branch 伺服器無法使用時 （例如，如果它是向下維護）。 如果登錄器和中繼伺服器上的 Survivable Branch Appliance 或 Survivable Branch 伺服器都無法使用，而且使用者註冊在中央網站的備份登錄器集區，撥入的通話可以仍然會路由傳送給使用者。

    
    </div>

**下一步**：[設定語音信箱重新路由設定 Lync Server 2013 中](lync-server-2013-configure-voice-mail-rerouting-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


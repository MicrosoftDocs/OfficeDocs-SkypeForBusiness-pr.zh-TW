---
title: Lync Server 2013：將位置原則新增至網路網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add a location policy to a network site
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425936(v=OCS.15)
ms:contentKeyID: 48183980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9ee6b5ba89cef592e137104df9e80d9373b5f02
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a>在 Lync Server 2013 的網路網站中新增位置原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

下列範例示範如何將在[Lync Server 2013 的建立位置](lync-server-2013-create-location-policies.md)原則中定義的**雷德蒙**位置原則新增到現有的網路網站，以及如何建立使用**雷蒙德**位置原則的新網路網站。

如需使用網路網站的詳細資訊，請參閱適用于下列 Cmdlet 的 Lync Server 管理命令介面檔：

  - **新-CsNetworkSite**

  - **CsNetworkSite**

  - **Set-CsNetworkSite**

  - **移除-CsNetworkSite**

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>將位置原則指派給現有的網路網站

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行下列 Cmdlet 來修改現有的網路網站。
    
    將**雷德蒙**標記的位置原則指派給名為 [**雷蒙德**] 的現有網路網站。
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a>將位置原則指派給新的網路網站

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行下列 Cmdlet 以建立新的網路網站。
    
    在網路區域中建立新的網路網站，並指派**雷德蒙**標記的位置原則。
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013： 新增網路網站的位置原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a location policy to a network site
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425936(v=OCS.15)
ms:contentKeyID: 48183980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a817a1a94b6e02167d488212dd532537cec0146
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a>將位置原則新增至 Lync Server 2013 中的網路網站

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-24_

下列範例顯示如何新增至現有的網路網站在[Lync Server 2013 中的建立位置原則](lync-server-2013-create-location-policies.md)中定義的**Redmond**位置原則，以及如何建立使用**Redmond**位置原則的新網路網站。

如需使用網路站台的詳細資訊，請參閱 Lync Server 管理命令介面文件的下列 cmdlet:

  - **新 CsNetworkSite**

  - **Get-csnetworksite**

  - **Set-csnetworksite**

  - **移除 CsNetworkSite**

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>若要指派位置原則給現有網路網站

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  執行下列 Cmdlet 來修改現有的網路網站。
    
    指派標記**Redmond**位置原則給現有網路網站名為**Redmond**。
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a>若要指派位置原則給新的網路網站

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  執行下列 Cmdlet 來建立新的網路網站。
    
    在網路地區中建立新的網路網站，並指派具有 **Redmond** 標記的位置原則。
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>


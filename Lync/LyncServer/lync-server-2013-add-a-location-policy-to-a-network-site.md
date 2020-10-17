---
title: Lync Server 2013：將位置原則新增至網路網站
description: Lync Server 2013：將位置原則新增至網路網站。
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
ms.openlocfilehash: 20f71d3144e2ef730de5dae46be16138b5d36c42
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567919"
---
# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a>在 Lync Server 2013 中將位置原則新增至網路網站

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

下列範例顯示如何將在[Lync Server 2013 中建立位置](lync-server-2013-create-location-policies.md)原則中定義的**Redmond**位置原則新增至現有的網路網站，以及如何建立使用**Redmond**位置原則的新網路網站。

如需使用網路網站的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：

  - **New-CsNetworkSite**

  - **Get-CsNetworkSite**

  - **Set-CsNetworkSite**

  - **Remove-CsNetworkSite**

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>若要指派位置原則給現有網路網站

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行下列 Cmdlet 來修改現有的網路網站。
    
    將 **雷德蒙** 標位置原則指派給名為 **redmond**的現有網路網站。
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a>若要指派位置原則給新的網路網站

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行下列 Cmdlet 來建立新的網路網站。
    
    在網路地區中建立新的網路網站，並指派具有 **Redmond** 標記的位置原則。
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>


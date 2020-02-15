---
title: Lync Server 2013： 設定位置資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f79587526172c7ccade1b74574b20657d1a82300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a>在 Lync Server 2013 中設定位置資料庫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-17_

若要啟用用戶端能夠自動偵測其網路內的位置，必須先設定位置資料庫。 如果您不需設定位置資料庫，且 [位置原則中的 [**位置所需**設為 [**是**] 或 [**免責聲明**，將會提示使用者手動輸入位置。

若要設定位置資料庫，您將會執行下列工作：

1.  填入網路元素與位置的對應資料庫。 如果您使用緊急位置識別號碼 (ELIN) 閘道，您必須包含在 ELIN \<CompanyName\> ] 欄位。

2.  驗證 E9-1-1 服務提供者所維護的主要街道地址指南 (MSAG) 地址。

3.  發佈更新過的資料庫。

<div>


> [!NOTE]  
> 或者，您可以定義可使用於放置位置資料庫的次要位置來源資料庫。 如需詳細資訊，請參閱<A href="lync-server-2013-configure-a-secondary-location-information-service.md">設定 Lync Server 2013 中的次要位置資訊服務</A>。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [填入位置資料庫在 Lync Server 2013](lync-server-2013-populate-the-location-database.md)

  - [驗證 Lync Server 2013 中的地址](lync-server-2013-validate-addresses.md)

  - [發佈位置資料庫從 Lync Server 2013](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


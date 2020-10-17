---
title: Lync Server 2013：設定位置資料庫
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
ms.openlocfilehash: 9495bc0c52e8e9af4af0daa3d29304d5b25d4b7e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520260"
---
# <a name="configure-the-location-database-in-lync-server-2013"></a>在 Lync Server 2013 中設定位置資料庫

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-17_

若要讓用戶端自動偵測網路內部的位置，您必須先設定位置資料庫。 如果您未設定位置資料庫，且位置原則中 **所需的位置** 已設定為 **[是] 或 [** **免責聲明**]，則系統會提示使用者手動輸入位置。

若要設定位置資料庫，您需要執行下列工作：

1.  以網元對應至位置，填入資料庫。 如果您使用緊急位置識別號碼 (ELIN) 閘道，您必須在欄位中包含 ELIN \<CompanyName\> 。

2.  對照主要街道通訊指南 (MSAG) 來驗證 E9-1-1 服務提供者所維護的位址。

3.  發佈更新的資料庫。

<div>


> [!NOTE]  
> 或者，您也可以定義可用於放置位置資料庫的次要位置來源資料庫。 如需詳細資訊，請參閱 <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a 次要位置資訊服務中的 Lync Server 2013</A>。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中填入位置資料庫](lync-server-2013-populate-the-location-database.md)

  - [在 Lync Server 2013 中驗證位址](lync-server-2013-validate-addresses.md)

  - [從 Lync Server 2013 發佈位置資料庫](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


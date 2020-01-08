---
title: Lync Server 2013：設定位置資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15a9456cc79e02735fe94c24748674944722b49c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a>在 Lync Server 2013 中設定位置資料庫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-17_

若要讓用戶端能在網路中自動偵測其位置，您必須先設定位置資料庫。 如果您沒有設定位置資料庫，且位置原則中**所需的位置**設定為 **[是] 或 [** **免責聲明**]，系統會提示使用者手動輸入位置。

若要設定位置資料庫，您可以執行下列工作：

1.  使用網路元素對應至位置來填入資料庫。 如果您使用緊急位置身分識別號碼（ELIN）閘道，您必須在 [ \<公司名稱\> ] 欄位中包含該 ELIN。

2.  根據 E9-1-1 服務提供者所維護的主要街道位址指南（MSAG）驗證位址。

3.  發佈更新後的資料庫。

<div>


> [!NOTE]  
> 或者，您也可以定義可在位置資料庫中使用的次要位置源資料庫。 如需詳細資訊，請參閱<A href="lync-server-2013-configure-a-secondary-location-information-service.md">在 Lync Server 2013 中設定次要位置資訊服務</A>。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中填入位置資料庫](lync-server-2013-populate-the-location-database.md)

  - [驗證 Lync Server 2013 中的位址](lync-server-2013-validate-addresses.md)

  - [從 Lync Server 2013 發佈位置資料庫](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


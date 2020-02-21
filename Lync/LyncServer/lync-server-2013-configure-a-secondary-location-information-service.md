---
title: Lync Server 2013： 設定次要位置資訊服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a secondary Location Information service
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48183334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a13e99aa7f9e3da9ddd04f5c8e7763c7de1481a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a>在 Lync Server 2013 中設定次要位置資訊服務

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-30_

Lync Server 2013 提供您可以使用位置資訊服務指向次要位置來源 (SLS) 資料庫的 web 服務介面。 連線至 SLS 資料庫的 web 服務介面必須符合位置資訊服務 WSDL。 如果設定位置資料庫和次要位置資料庫，將位置資訊服務第一次查詢位置資料庫，並如果找到不相符，就會傳送位置要求從用戶端 SLS 資料庫。 如果位置存在於 SLS，位置資訊服務會傳回給用戶端然後傳送位置。

如需詳細資訊，請參閱 < Lync Server 管理命令介面文件的下列 cmdlet:

  - **Set-cswebserviceconfiguration**

<div>

## <a name="to-configure-secondary-location-database"></a>若要設定次要位置資料庫

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  執行下列 Cmdlet 以設定次要位置資料庫的位置 URL。
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>


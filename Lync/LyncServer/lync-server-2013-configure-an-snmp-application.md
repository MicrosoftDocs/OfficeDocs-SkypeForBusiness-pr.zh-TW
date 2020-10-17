---
title: Lync Server 2013：設定 SNMP 應用程式
description: Lync Server 2013：設定 SNMP 應用程式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an SNMP application
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48185346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7374b61ad85d7ddcb40ef1db535e17f86dea58f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546699"
---
# <a name="configure-an-snmp-application-in-lync-server-2013"></a>在 Lync Server 2013 中設定 SNMP 應用程式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

Lync Server 2013 包含標準的 web 服務介面，可讓您用來將位置資訊服務連線至簡易網路管理通訊協定 (SNMP) 應用程式，該應用程式會與埠及切換資訊相符的 MAC 位址。

如果已安裝 SNMP 應用程式，且 Location 資訊服務無法在位置資料庫中找到相符的位置，則位置資訊服務會自動使用用戶端所提供的 MAC 位址來查詢應用程式。 然後，位置資訊服務會使用 SNMP 應用程式傳回的埠及切換資訊，以重新查詢位置資料庫。

如需詳細資訊，請參閱 [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)。

<div>


> [!NOTE]  
> MAC 位址無法在執行 Windows 8 的電腦上使用。



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a>設定 SNMP 應用程式 URL

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行下列 Cmdlet 來設定 SNMP 應用程式的 URL。
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>


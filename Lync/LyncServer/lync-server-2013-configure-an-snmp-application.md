---
title: Lync Server 2013： 設定 SNMP 應用程式
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
ms.openlocfilehash: 3e7dafe07796f6d93e6357a5bff9aa058fe29b85
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-snmp-application-in-lync-server-2013"></a>在 Lync Server 2013 中設定 SNMP 應用程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-03_

Lync Server 2013 包含可用來以比對 MAC 位址與連接埠和交換器資訊的簡易網路管理通訊協定 (SNMP) 應用程式連線的位置資訊服務的標準 web 服務介面。

如果安裝 SNMP 應用程式和位置資訊服務無法在位置資料庫中尋找相符項目，將位置資訊服務自動查詢應用程式使用用戶端所提供的 MAC 位址。 位置資訊服務然後使用 SNMP 應用程式所傳回的連接埠和交換器資訊來重新查詢位置資料庫。

如需詳細資訊，請參閱[Set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)。

<div>


> [!NOTE]  
> MAC 位址不提供在執行 Windows 8 的電腦上。



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a>若要設定 SNMP 應用程式 URL

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  執行下列 cmdlet 以設定 SNMP 應用程式的 URL。
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>


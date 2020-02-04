---
title: Lync Server 2013：設定 SNMP 應用程式
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
ms.openlocfilehash: 9e11d79278318c99e1c6a1db3c4609e19553ba4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-snmp-application-in-lync-server-2013"></a>在 Lync Server 2013 中設定 SNMP 應用程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

Lync Server 2013 包含標準的 web 服務介面，您可以用來將位置資訊服務連線到與含埠和切換資訊的 MAC 位址相符的簡單網路管理通訊協定（SNMP）應用程式。

如果已安裝 SNMP 應用程式，且位置資訊服務無法在位置資料庫中找到相符的專案，位置資訊服務會使用用戶端提供的 MAC 位址來自動查詢應用程式。 然後，位置資訊服務會使用 SNMP 應用程式傳回的埠和切換資訊來重新查詢位置資料庫。

如需詳細資訊，請參閱[設定 CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)。

<div>


> [!NOTE]  
> MAC 位址無法在執行 Windows 8 的電腦上使用。



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a>若要設定 SNMP 應用程式 URL

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行下列 Cmdlet 來設定 SNMP 應用程式的 URL。
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>


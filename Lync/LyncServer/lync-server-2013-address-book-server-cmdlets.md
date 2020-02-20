---
title: 'Lync Server 2013: Address Book Server cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Address Book Server cmdlets
ms:assetid: 33da45da-3c57-4d04-9679-f0e5a0cfd37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415643(v=OCS.15)
ms:contentKeyID: 48183793
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe9a7462edb8df2741a8c783cff17e62bfe848eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="address-book-server-cmdlets-in-lync-server-2013"></a>處理 Lync Server 2013 中的活頁簿 Server cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-06-26_

Address Book server 是 Active Directory 網域服務和 Microsoft Lync Server 2013 之間的媒介。 Address Book server 可確保儲存在 Lync Server 2013 中的使用者資訊的同步處理儲存在 Active Directory 中的使用者資訊。 其作法是定期將 Address Book 檔案與使用者資料庫中儲存的資訊同步化。 接著，Lync Server 包含許多管理 Address Book server cmdlet。

<div>

## <a name="address-book-server-cmdlets"></a>Address Book Server Cmdlet

您無法 Address Book Server 中設定 Lync Server Control Panel。 Windows PowerShell 為主要工具，以管理這些設定。 下表列出的 Cmdlet 與管理 Address Book Server 直接相關：

**Address Book Server**

  - <span></span>  
    [Get-csaddressbookconfiguration cmdlet](https://technet.microsoft.com/library/Gg398132(v=OCS.15))

  - <span></span>  
    [New-csaddressbookconfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))

  - <span></span>  
    [Remove-csaddressbookconfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))

  - <span></span>  
    [Set-csaddressbookconfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Update-csaddressbook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Debug-csaddressbookreplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-csaddressbookservice](https://technet.microsoft.com/library/Gg398661(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-csaddressbookwebquery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server PowerShell 部落格](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


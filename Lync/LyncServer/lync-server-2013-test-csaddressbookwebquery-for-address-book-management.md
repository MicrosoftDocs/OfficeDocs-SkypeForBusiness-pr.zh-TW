---
title: Lync Server 2013：用於通訊錄管理的 Test-CsAddressBookWebQuery
description: Lync Server 2013：用於通訊錄管理的 Test-CsAddressBookWebQuery。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test-CsAddressBookWebQuery for Address Book management
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429716(v=OCS.15)
ms:contentKeyID: 48184865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7448733ed1477d36b887648154d66c96f9e6d0b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547439"
---
# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013 中用於通訊錄管理的 Test-CsAddressBookWebQuery

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

誰可以執行這個 Cmdlet：根據預設，會授權下列群組的成員執行 Test-CsAddressBookWebQuery Cmdlet： RTCUniversalServerAdmins。 若要傳回所有獲指派此 Cmdlet 的角色型存取控制 (RBAC) 角色清單 (包括您自行建立的自訂 RBAC 角色)，請在 Windows PowerShell 命令提示中執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

與 Test-CsAddressBookService 綜合交易類似，Test-CsAddressBookWebQuery 會針對通訊錄 Web 查詢執行查詢，以確保其運作正常。 Cmdlet 會連線至 Web 票證驗證，並顯示– UserCredential 中指定的認證。 若驗證，Cmdlet 會呈現– TargetSipAddress 資訊。 如果能夠取得連絡人的相關資訊，指令程式就應報告成功。

例如：

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a>請參閱


[Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


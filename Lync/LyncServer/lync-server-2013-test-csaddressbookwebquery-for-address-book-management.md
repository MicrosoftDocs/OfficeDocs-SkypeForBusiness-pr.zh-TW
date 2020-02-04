---
title: Lync Server 2013：針對通訊錄管理進行測試 CsAddressBookWebQuery
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
ms.openlocfilehash: c50497979e8439a60799864376d1f93d36646cec
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a>在 Lync Server 2013 中 CsAddressBookWebQuery 通訊錄管理的測試

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

誰可以執行這個 Cmdlet：根據預設，下列群組的成員有權執行測試 CsAddressBookWebQuery Cmdlet： RTCUniversalServerAdmins。 若要傳回已指派這個 Cmdlet 的所有角色式存取控制（RBAC）角色的清單（包括您自行建立的任何自訂 RBAC 角色），請在 Windows PowerShell 提示中執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

與 Test CsAddressBookService 綜合交易類似，Test CsAddressBookWebQuery 會針對通訊錄網頁查詢執行查詢，以確保其正常運作。 這個 Cmdlet 會連線至 Web 票證驗證，並呈現在-UserCredential 中指定的認證。 如果經過驗證，則 Cmdlet 會呈現-TargetSipAddress 資訊。 如果該 Cmdlet 能夠取得連絡人的相關資訊，就應該報告成功。

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


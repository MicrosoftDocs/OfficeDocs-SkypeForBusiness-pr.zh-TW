---
title: Lync Server 2013：用於通訊錄管理的 Get-CsAddressBookConfiguration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsAddressBookConfiguration for Address Book management
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429721(v=OCS.15)
ms:contentKeyID: 48185264
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03a13705381c127a6c2c04e7c4ffa70214c49cb6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512640"
---
# <a name="get-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013 中用於通訊錄管理的 Get-CsAddressBookConfiguration

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

誰可以執行此 Cmdlet：根據預設，會授權下列群組的成員在本機執行 Get-CsAddressBookConfiguration Cmdlet： RTCUniversalServerAdmins。 若要傳回所有獲指派此 Cmdlet 的角色型存取控制 (RBAC) 角色清單 (包括您自行建立的自訂 RBAC 角色)，請在 Windows PowerShell 命令提示中執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

Cmdlet Get-CsAddressBookConfiguration 會傳回已存在之設定的相關資訊。

例如：

    Get-CsAddressBookConfiguration -Identity site:Redmond

結合 Get-CsAddressBookConfiguration 和 Set-CsAddressBookConfiguration 的功能可讓系統管理員定義要修改的設定，然後套用修改。 例如，這會結合下列專案：

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

會傳回所有網站中的所有設定，並將23:00 小時的 RunTimeOfDay 套用至設定。

<div>

## <a name="see-also"></a>另請參閱


[Get-CsAddressBookConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


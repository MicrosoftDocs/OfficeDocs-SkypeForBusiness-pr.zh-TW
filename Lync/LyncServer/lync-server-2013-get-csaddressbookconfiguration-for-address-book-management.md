---
title: 'Lync Server 2013: Get-CsAddressBookConfiguration cmdlet 適用於通訊錄管理'
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
ms.openlocfilehash: 36d6811dc410a37ac885bd569e0a1474bb9a4dd0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="get-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a>Get-csaddressbookconfiguration cmdlet 適用於 Lync Server 2013 中的 Address Book 管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

誰可以執行此 cmdlet： 根據預設，下列群組的成員會獲授權在本機上執行 Get-csaddressbookconfiguration cmdlet: RTCUniversalServerAdmins。 若要傳回所有獲指派此 Cmdlet 的角色型存取控制 (RBAC) 角色清單 (包括您自行建立的自訂 RBAC 角色)，請在 Windows PowerShell 命令提示中執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

Get-csaddressbookconfiguration cmdlet 會傳回已存在的組態資訊。

例如：

    Get-CsAddressBookConfiguration -Identity site:Redmond

合併的 Get-csaddressbookconfiguration cmdlet 與 Set-csaddressbookconfiguration 功能可讓系統管理員定義要修改，然後套用修改的組態。 例如，此組合：

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

會傳回所有組態中的所有網站，並將 23:00 小時的 RunTimeOfDay 套用設定。

<div>

## <a name="see-also"></a>另請參閱


[Get-csaddressbookconfiguration cmdlet](https://docs.microsoft.com/powershell/module/skype/Get-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


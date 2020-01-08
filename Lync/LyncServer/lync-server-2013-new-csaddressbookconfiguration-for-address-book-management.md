---
title: Lync Server 2013：針對通訊錄管理的新 CsAddressBookConfiguration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New-CsAddressBookConfiguration for Address Book management
ms:assetid: a58ddc8c-ae04-4141-b69e-e45374a67d72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429718(v=OCS.15)
ms:contentKeyID: 48184985
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10a11829a6c0dd4e53f5684e5b950e3adf755811
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013 中的通訊錄管理的新 CsAddressBookConfiguration

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

誰可以執行這個 Cmdlet：根據預設，下列群組的成員有權在本機執行新的 CsAddressBookConfiguration Cmdlet： RTCUniversalServerAdmins。 若要傳回已指派這個 Cmdlet 的所有角色式存取控制（RBAC）角色的清單（包括您自行建立的任何自訂 RBAC 角色），請在 Windows PowerShell 提示中執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsAddressBookConfiguration"}

新的-CsAddressBookConfiguration Cmdlet 會建立新的設定，以管理通訊錄的行為。 這個 Cmdlet 的功能是定義通訊錄服務是否會建立用戶端下載檔案，以及是否使用正常化規則，在併入新的完整檔案之前，要保留增量和精簡的增量檔案、增量檔案大小，才能包含新的完整檔案建立、一天中建立完整檔案通訊錄的時間，以及內部應該如何同步處理使用者資料庫中的資訊。

例如：

    New-CsAddressBookConfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

<div>

## <a name="see-also"></a>請參閱


[New-CsAddressBookConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


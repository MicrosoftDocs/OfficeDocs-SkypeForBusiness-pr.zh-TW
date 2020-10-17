---
title: Lync Server 2013：用於通訊錄管理的 Update-CsAddressBook
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fdbef7a3826a734262a77aa39fb2ce32e547463
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527700"
---
# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013 中用於通訊錄管理的 Update-CsAddressBook

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

誰可以執行這個 Cmdlet：根據預設，下列群組成員已獲得授權，可在本機執行 Update-CsAddressBook Cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。若要傳回指派給該 Cmdlet 的所有角色型存取控制 (RBAC) 角色清單 (包括您自己建立的任何自訂 RBAC 角色)，請在 Windows PowerShell 提示中輸入下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

Update-CsAddressBook Cmdlet 會取代 Office Communications Server 中的 **abserver.exe –syncNow** 命令。此 Cmdlet 的目的在於立即啟動同步處理，而非等待排程的時間。第一個範例命令會更新組織中的所有通訊錄。第二個範例命令只會更新與所定義伺服器關聯的通訊錄。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中，Lync Server 使用者複寫器會從 Active Directory 中挑選變更，並根據設定的間隔來更新 Lync Server 使用者資料庫。 Lync Server 使用者複寫器也會快速傳播變更至 RTCab 資料庫，而不需管理員必須執行 Update-csaddressbook 的更新。 只有在啟用通訊錄檔案下載時，系統管理員才需要執行 Update-csaddressbook 更新。



</div>

例如：

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a>請參閱


[Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


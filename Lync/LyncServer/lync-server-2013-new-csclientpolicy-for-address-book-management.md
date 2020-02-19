---
title: 'Lync Server 2013: New-CsClientPolicy 適用於通訊錄管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsClientPolicy for Address Book management
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48185771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78d63b29ea1198bfee91437a1e6dcd70c1be0a45
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42124856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a>適用於通訊錄管理 Lync Server 2013 中的新 CsClientPolicy

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

誰可以執行這個 Cmdlet：根據預設，下列群組成員已獲得授權，可執行 New-CsClientPolicy Cmdlet：RTCUniversalServerAdmins。 若要傳回所有獲指派此 Cmdlet 的角色型存取控制 (RBAC) 角色清單 (包括您自行建立的自訂 RBAC 角色)，請在 Windows PowerShell 命令提示中執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

此 cmdlet New-csclientpolicy 定義大量設定如佈建 Lync Server 2013 中可用的功能的用戶端。 若為通訊錄服務，參數 AddressBookAvailability 是感興趣。 此參數，直接影響用戶端可用的選項，有三個可能的選項：

  - WebSearchAndFileDownload

  - WebSearchOnly

  - FileDownloadOnly

定義時，它會決定用戶端存取通訊錄的方式。 如果您定義此參數，您必須定義其中一個選項。 如果您不要修改此設定，預設 WebSearchAndFileDownload 仍然有效。

例如：

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a>請參閱


[New-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：針對通訊錄管理的新 CsClientPolicy
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New-CsClientPolicy for Address Book management
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48185771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77cf1f7ebe085fc11d23381db9d1c474c79403d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013 中的通訊錄管理的新 CsClientPolicy

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

誰可以執行這個 Cmdlet：根據預設，下列群組的成員有權執行新的 CsClientPolicy Cmdlet： RTCUniversalServerAdmins。 若要傳回已指派這個 Cmdlet 的所有角色式存取控制（RBAC）角色的清單（包括您自行建立的任何自訂 RBAC 角色），請在 Windows PowerShell 提示中執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

Cmdlet New-CsClientPolicy 會定義大量設定，以便為 Lync Server 2013 中提供的功能提供客戶。 針對通訊錄服務，參數 AddressBookAvailability 是有意義的。 這個參數會直接影響用戶端可用的選項，有三種可能的選項：

  - WebSearchAndFileDownload

  - WebSearchOnly

  - FileDownloadOnly

定義後，會決定用戶端存取通訊錄的方式。 如果您定義此參數，您必須定義其中一個選項。 如果您不修改此設定，預設 WebSearchAndFileDownload 會保持生效。

例如：

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a>請參閱


[New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


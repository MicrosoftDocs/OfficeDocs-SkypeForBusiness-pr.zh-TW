---
title: Lync Server 2013：設定通訊錄管理的 CsWebServiceConfiguration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set-CsWebServiceConfiguration for Address Book management
ms:assetid: 79d0edf5-23f3-4845-a7b7-e11b5a928bab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429709(v=OCS.15)
ms:contentKeyID: 48184572
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cb1fa5d6474a792442510181a5c13b17e074c61
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a>在 Lync Server 2013 中設定通訊錄管理 CsWebServiceConfiguration

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

誰可以執行這個 Cmdlet：根據預設，下列群組的成員有權在本機執行 CsWebServiceConfiguration Cmdlet： RTCUniversalServerAdmins。 若要傳回已指派這個 Cmdlet 的所有角色式存取控制（RBAC）角色的清單（包括您自行建立的任何自訂 RBAC 角色），請在 Windows PowerShell 提示中執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsWebServiceConfiguration"}

CsWebServiceConfiguration Cmdlet 可讓系統管理員在 Web 服務的設定中重新定義現有的屬性。

例如：

    Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True

<div>

## <a name="see-also"></a>請參閱


[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


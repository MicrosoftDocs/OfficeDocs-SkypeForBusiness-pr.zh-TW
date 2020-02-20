---
title: 'Lync Server 2013: Set-CsWebServiceConfiguration 適用於通訊錄管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set-CsWebServiceConfiguration for Address Book management
ms:assetid: 79d0edf5-23f3-4845-a7b7-e11b5a928bab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429709(v=OCS.15)
ms:contentKeyID: 48184572
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4df313529dc1c217319d9116ca8d7d806175987d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a>設定 CsWebServiceConfiguration 適用於 Lync Server 2013 中的 Address Book 管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

誰可以執行這個 Cmdlet：根據預設，下列群組的成員已獲得授權，可在本機執行 Set-CsWebServiceConfiguration Cmdlet：RTCUniversalServerAdmins。若要傳回指派給該 Cmdlet 的所有角色型存取控制 (RBAC) 角色清單 (包括您自己建立的任何自訂 RBAC 角色)，請在 Windows PowerShell 提示中輸入下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsWebServiceConfiguration"}

Set-CsWebServiceConfiguration Cmdlet 可讓系統管理員重新定義 Web 服務設定中的現有屬性。

例如：

    Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True

<div>

## <a name="see-also"></a>請參閱


[Set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


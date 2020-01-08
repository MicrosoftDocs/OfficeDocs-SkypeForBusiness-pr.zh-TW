---
title: Lync Server 2013：執行及監視備份
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fffc6a8355305e11d87513ffc37626f3e386c749
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a>在 Lync Server 2013 中執行及監視備份

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-15_

您的業務優先順序應該會推動貴組織的備份與還原需求的規範。 執行伺服器與資料的備份是規劃災難中的第一項防線。

執行 Lync Server 2013 服務或伺服器角色的電腦必須擁有目前拓撲的複本、目前的設定設定，以及目前原則，才能在其已設定的角色中起作用。 Lync Server 負責確保將此資訊傳遞給需要它的每個電腦。

**Export CsConfiguration**和匯**入-CsConfiguration** Cmdlet 是用來在中央管理存儲升級期間備份及還原 Lync Server 拓撲、配置設定及原則。 **Export CsConfiguration** Cmdlet 可讓您將資料匯出至。ZIP 檔案。 然後，您可以使用**CsConfiguration** Cmdlet 來讀取該指令。ZIP 檔案並將拓撲、配置設定及原則還原到中央管理儲存體。 之後，Lync Server 的複製服務會將還原的資訊複製到其他執行 Lync Server services 的電腦。

在您的周邊網路（例如，Edge 伺服器）的初始設定電腦中，也會使用匯出及匯入設定資料的功能。 在周邊網路中設定電腦時，您必須先使用 CsConfiguration Cmdlet 來執行手動複製：您必須使用**export-CsConfiguration**匯出設定資料，然後再複製。ZIP 檔案到周邊網路的電腦。 之後，您可以使用匯**入-CsConfiguration**和 LocalStore 參數匯入資料。 您只需要進行一次。 之後，就會自動進行複製。

誰可以執行這個 Cmdlet：根據預設，下列群組的成員有權在本機執行**Export CsConfiguration** Cmdlet： RTCUniversalServerAdmins。 若要傳回所有 RBAC 角色的清單，請將此 Cmdlet 指派給（包括您自行建立的任何自訂 RBAC 角色），並在 Windows PowerShell 提示中執行下列命令：

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

所有的 SQL 2012 後端資料庫，都應該按照[SQL 最佳做法](http://go.microsoft.com/fwlink/p/?linkid=290716)進行備份。

針對 Lync Server 2013 基礎結構的災害復原方案進行定期測試，應該在模仿生產環境的實驗環境中執行。 如需有關災害復原測試的詳細資訊，請參閱每月工作。

請注意，備份頻率可以根據您的還原點和復原點目標來調整。 最佳做法是在一天內定期進行定期快照。 一般來說，您應該每24小時執行一次完整備份。

<div>

## <a name="see-also"></a>請參閱


[匯入-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Export-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[SQL 最佳做法](http://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


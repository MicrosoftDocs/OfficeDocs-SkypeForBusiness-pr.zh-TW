---
title: Lync Server 2013： 執行與監控備份
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d44fe94ab8e02551f8d33d95248c6cede63a6974
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a>執行與監控備份 Lync Server 2013 中

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-05-15_

您的業務優先順序應磁碟機規格的備份和還原您的組織需求。 執行備份的伺服器和資料是國防版的第一行中規劃嚴重損壞。

執行 Lync Server 2013 服務或伺服器角色的電腦必須具備一份目前的拓撲、 目前的組態設定，與目前的原則，才能他們可以在其指定角色中的運作。 Lync Server 負責確保此資訊會傳遞至需要它每一部電腦。

**Export-csconfiguration**和**Import-csconfiguration**指令程式可用來備份及還原 Lync Server 拓撲、 組態設定和原則期間中央管理存放區升級。 **Export-csconfiguration** cmdlet 可讓您匯出的資料。ZIP 檔案。 您可以再使用**Import-csconfiguration** cmdlet 可讀取的。ZIP 檔案，並還原中央管理存放區的拓撲、 組態設定和原則。 之後，Lync Server 複寫服務會將已還原的資訊複寫至其他執行 Lync Server 服務的電腦。

匯出及匯入組態資料的能力也會在位於周邊網路 (例如 Edge Server) 的電腦的初始設定期間使用。 當在周邊網路中設定的電腦，您必須先執行使用 CsConfiguration cmdlet 手動複寫： 您必須使用**Export-csconfiguration**匯出組態資料，然後複製。ZIP 檔案，以在周邊網路的電腦。 在那之後，您可以使用**Import-csconfiguration**和 LocalStore 參數匯入資料。 您只需要進行此一次。 在那之後，將會自動進行複寫。

誰可以執行此 cmdlet： 根據預設，下列群組的成員會獲授權在本機上執行**Export-csconfiguration** cmdlet: RTCUniversalServerAdmins。 若要傳回的所有 RBAC 角色清單，此 cmdlet 會指派給 （包括任何自訂 RBAC 角色，您自行建立），請在 Windows PowerShell 提示字元中執行下列命令：

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

所有的 SQL 2012 後端資料庫是應該備份根據[SQL 最佳作法](https://go.microsoft.com/fwlink/p/?linkid=290716)。

應執行的災害復原規劃 Lync Server 2013 基礎結構的一般測試，盡可能模擬實際執行環境在實驗室環境中。 如需有關嚴重損壞修復測試每月的工作，請參閱。

請注意的備份頻率可以都調整，根據您的還原點和復原點目標。 最佳作法是，快照一般、 定期一天之內。 一般而言，您應該執行完整備份，每隔 24 小時。

<div>

## <a name="see-also"></a>另請參閱


[Import-csconfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Export-csconfiguration](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[SQL 最佳作法](https://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：執行及監視備份
description: Lync Server 2013：執行及監視備份。
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
ms.openlocfilehash: 2fb8ce99e850f0918974be08eb10796ef1397225
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557229"
---
# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a>在 Lync Server 2013 中執行及監視備份

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-15_

您的業務優先順序應該會推動組織的備份與還原需求規格。 在規劃災難時，執行伺服器和資料的備份是第一項防禦工作。

執行 Lync Server 2013 服務或伺服器角色的電腦必須具有目前拓撲的複本、目前的設定，以及目前的原則，才能在其所指的角色中運作。 Lync Server 負責確保將此資訊傳送給每個需要的電腦。

**Export-CsConfiguration**和**Import-CsConfiguration** Cmdlet 是用來備份及還原您的 Lync Server 拓撲、設定設定，以及在中央管理存放區升級期間的原則。 **Export-CsConfiguration** Cmdlet 可讓您將資料匯出至。ZIP 檔案。 然後，您可以使用 **Import-CsConfiguration** Cmdlet 來讀取該。ZIP 檔案，並將拓撲、設定設定和原則還原至中央管理存放區。 之後，Lync Server 的複寫服務會將還原的資訊複製到其他執行 Lync Server 服務的電腦。

在周邊網路中的電腦初始設定時，也會使用匯出及匯入設定資料的功能 (例如，Edge Servers) 。 當您設定周邊網路中的電腦時，您必須先使用 CsConfiguration Cmdlet 執行手動複寫：您必須使用 **Export-CsConfiguration** 匯出設定資料，然後再複製。在周邊網路中的電腦的 ZIP 檔案。 之後，您可以使用 **Import-CsConfiguration** 和 LocalStore 參數匯入資料。 您只需執行一次。 之後，就會自動進行複寫。

誰可以執行此 Cmdlet：根據預設，會授權下列群組的成員在本機執行 **Export-CsConfiguration** Cmdlet： RTCUniversalServerAdmins。 若要傳回所有 RBAC 角色的清單，此 Cmdlet 會指派給 (包含您自行建立的任何自訂 RBAC 角色) ，請從 Windows PowerShell 提示執行下列命令：

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

所有的 SQL 2012 後端資料庫應該依照每個 [sql 的最佳作法](https://go.microsoft.com/fwlink/p/?linkid=290716)來備份。

定期測試 Lync Server 2013 基礎結構的嚴重損壞修復計畫時，應該會在盡可能模仿實際執行環境的實驗室環境中執行。 如需有關嚴重損壞修復測試的詳細資訊，請參閱每月任務。

請注意，根據您的還原點和復原點目標，可以調整備份頻率。 最佳作法是在一天內定期進行定期快照。 一般來說，您應該每24小時執行一次完整備份。

<div>

## <a name="see-also"></a>另請參閱


[Import-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Export-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[SQL 最佳作法](https://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


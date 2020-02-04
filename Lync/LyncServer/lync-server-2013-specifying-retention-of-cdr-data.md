---
title: Lync Server 2013：指定保留 CDR 資料的功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Specifying retention of CDR data
ms:assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182581(v=OCS.15)
ms:contentKeyID: 48185299
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32eee413b25da3231d5633e89571bbc08deb1f38
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="specifying-retention-of-cdr-data-in-lync-server-2013"></a>在 Lync Server 2013 中指定 CDR 資料的保留

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

根據預設，通話詳細資料錄製（CDR）資料會在60天之後清除。 您可以使用 [**通話詳細資料記錄**] 頁面上的設定，將資料保留較長或較短的時間週期。 如果您停用 CDR，在啟用 CDR 之前捕獲的資料，也會受到清除。

<div>


> [!NOTE]  
> 您應該設定 CDR 和體驗品質（QoE），以保留相同天數的資料。 [監視伺服器報告] 頁面提供的呼叫詳細資料包告（CDRs）中的每個通話，包括 CDR 和 QoE 資訊。 如果 CDR 與 QoE 的清除持續時間不一樣，有些通話可能只會包含 CDR 資料，而其他可能只包含 QoE 資料。



</div>

使用下列程式來設定 CDR 資料的清除設定。

<div>

## <a name="to-specify-retention-of-cdr-data"></a>指定保留 CDR 資料

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [**呼叫詳細資料錄製**]。

4.  在 [**通話詳細資料記錄**] 頁面上，按一下表格中的適當網站，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  若要開啟清除，請選取 [**啟用清除 CDRs**]。

6.  在 **[保留 CDRs 的最大持續時間（天數）** ] 中：選取應保留通話詳細資料錄製的最大天數。

7.  若要在**最大持續時間（天）內保留錯誤報表資料：** 請選取要保留錯誤報表的最大天數。

8.  按一下 [認可]****。

</div>

<div>

## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指定 CDR 保留

您可以使用 Windows PowerShell 和 CsCdrConfiguration Cmdlet 來建立 CDR 保留設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-specify-cdr-retention-for-a-specific-location"></a>針對特定位置指定 CDR 保留

  - 這個命令可讓您清除雷德蒙網站的 CDR 資料，並將網站設定為維持 CDR 資料，以及20天的錯誤報表資料。
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<div>

## <a name="to-specify-cdr-retention-for-multiple-locations"></a>若要為多個位置指定 CDR 保留

  - 這個命令會針對組織中使用的所有 CDR 配置設定，設定 CDR 保留。
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

如需詳細資訊，請參閱[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中呼叫詳細資料錄製（CDR）](lync-server-2013-call-detail-recording-cdr.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


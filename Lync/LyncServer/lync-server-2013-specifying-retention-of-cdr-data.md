---
title: Lync Server 2013：指定保留 CDR 資料
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
ms.openlocfilehash: 942ccccb5a7a9224c33e3d5bdeafc10600585128
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="specifying-retention-of-cdr-data-in-lync-server-2013"></a>在 Lync Server 2013 中指定保留 CDR 資料

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

根據預設，[詳細通話記錄] (CDR) 資料會在60天之後清除。 您可以使用 [ **詳細通話記錄** ] 頁面上的設定，將資料保留較長或更短的時間週期。 如果您停用 CDR，啟用 CDR 之前所捕獲的資料也會受到清除。

<div>


> [!NOTE]  
> 您應設定 CDR 和經驗品質 (QoE) 保留相同天數的資料。 「監控伺服器報告」頁面提供的 [通話詳細資料包告] 中的每個通話 (Cdr) ，包含 CDR 和 QoE 資訊。 如果 CDR 和 QoE 的清除持續時間不同，有些呼叫可能只會包含 CDR 資料，另有可能只包含 QoE 資料。



</div>

使用下列程式可設定 CDR 資料的清除設定。

<div>

## <a name="to-specify-retention-of-cdr-data"></a>指定保留 CDR 資料

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[詳細通話記錄]**。

4.  在 [ **詳細通話記錄** ] 頁面上，按一下表格中的適當網站，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細**資料]。

5.  若要開啟清除，請選取 [ **啟用清除 cdr**]。

6.  在 [ **保持 cdr 的最大持續期間 (天數) ：** 選取應該保留詳細通話記錄的最大天數。

7.  在 [ **將錯誤報表的最大持續時間 (天數]) 中：** 選取應該保留錯誤報表的最大天數。

8.  按一下 **[認可]**。

</div>

<div>

## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指定 CDR 保留

您可以使用 Windows PowerShell 和 Set-CsCdrConfiguration Cmdlet 來建立 CDR 保留設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-specify-cdr-retention-for-a-specific-location"></a>指定特定位置的 CDR 保留

  - 此命令可讓您清除 Redmond 網站的 CDR 資料，並將網站設定為維護 CDR 資料和錯誤報表資料的20天。
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<div>

## <a name="to-specify-cdr-retention-for-multiple-locations"></a>指定多個位置的 CDR 保留

  - 此命令會針對組織中使用的所有 CDR 設定設定，設定 CDR 保留。
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

如需詳細資訊，請參閱 [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) Cmdlet 的 [說明] 主題。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的詳細通話記錄 (CDR) ](lync-server-2013-call-detail-recording-cdr.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：修改經驗品質設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify Quality of Experience settings
ms:assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182563(v=OCS.15)
ms:contentKeyID: 48184996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e5af1f53cc35bd22fcc09058a0aecb1b499897f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-quality-of-experience-settings-in-lync-server-2013"></a>修改 Lync Server 2013 中的經驗品質設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

根據預設，在60天后會清除 (QoE) 資料的經驗品質。 您可以使用 [**經驗品質資料**] 頁面上的設定，將資料保留較長或更短的時間週期。 如果您停用 QoE，啟用 QoE 之前所捕獲的資料也會加以清除。

<div>


> [!NOTE]  
> 您應設定詳細通話記錄 (CDR) 和 QoE 保留相同天數的資料。 [通話詳細資料包告] 中的每個通話 (Cdr) ，可從監控報告首頁取得，包含 CDR 和 QoE 資訊。 如果 CDR 和 QoE 的清除持續時間不同，有些呼叫可能只會包含 CDR 資料，另有可能只包含 QoE 資料。



</div>

下列程式說明如何設定 QoE 資料的清除設定。

<div>

## <a name="to-specify-retention-of-qoe-data-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台指定 QoE 資料的保留

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱[在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[經驗品質資料]**。

4.  在 [**經驗品質資料**] 頁面上，按一下表格中的適當網站，然後按一下 [**編輯**]，再按一下 [**顯示詳細**資料]。

5.  若要開啟清除，請選取 [**啟用 QoE 的清除**]。

6.  在 [**保持 QoE 的最大持續時間 (天數]) **選取應該保留 QoE 資料的最大天數。

7.  按一下 **[認可]**。

</div>

<div>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指定 QoE 保留

您可以使用 Windows PowerShell 及**Set CsQoEConfiguration** Cmdlet 來建立 QoE 保留設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-specify-qoe-retention-for-a-specific-location"></a>指定特定位置的 QoE 保留

  - 這個命令可讓 Redmond 網站的 QoE 資料得以清除，並設定網站以維護20天的 QoE 資料。
    
        Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20

</div>

<div>

## <a name="to-specify-qoe-retention-for-multiple-locations"></a>若要指定多個位置的 QoE 保留

  - 這個命令會針對組織中使用的所有 QoE 設定設定，設定 QoE 保留。
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 

</div>

如需詳細資訊，請參閱[Set CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) Cmdlet 的 [說明] 主題。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中部署監控](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


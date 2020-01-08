---
title: Lync Server 2013：修改體驗品質設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify Quality of Experience settings
ms:assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182563(v=OCS.15)
ms:contentKeyID: 48184996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ce6041e6512714f10785cf2976727788e105f70
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-quality-of-experience-settings-in-lync-server-2013"></a>在 Lync Server 2013 中修改體驗品質設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

根據預設，經驗品質（QoE）資料會在60天之後清除。 您可以使用 [**體驗資料品質**] 頁面上的設定，將資料保留較長或較短的時間週期。 如果您停用 QoE，則在啟用 QoE 之前捕獲的資料也會受到清除。

<div>


> [!NOTE]  
> 您應該設定 [通話詳細資料錄製（CDR）] 和 [QoE]，以保留相同天數的資料。 [監視報告] 首頁提供的呼叫詳細資料包告（CDRs）中的每個通話都包含 CDR 和 QoE 資訊。 如果 [CDR] 和 [QoE] 的清除持續時間不一樣，有些通話可能只會包含 CDR 資料，而其他可能只包含 QoE 的資料。



</div>

下列程式說明如何設定 QoE 資料的清除設定。

<div>

## <a name="to-specify-retention-of-qoe-data-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 來指定 QoE 資料的保留

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [**體驗資料品質**]。

4.  在 [**體驗品質資料**] 頁面上，從表格中按一下適當的網站，按一下 [**編輯**]，然後按一下 [**顯示詳細**資料]。

5.  若要開啟清除，請選取 [**啟用清除 QoE**]。

6.  在 **[保留 QoE 的最大持續時間（天數）** ] 中，選取 QoE 資料應保留的最大天數。

7.  按一下 [認可]****。

</div>

<div>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指定 QoE 保留

您可以使用 Windows PowerShell 和**CsQoEConfiguration** Cmdlet 來建立 QoE 保留設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-specify-qoe-retention-for-a-specific-location"></a>若要指定特定位置的 QoE 保留

  - 這個命令可讓您清除雷德蒙網站的 QoE 資料，並將該網站設定為維護20天的 QoE 資料。
    
        Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20

</div>

<div>

## <a name="to-specify-qoe-retention-for-multiple-locations"></a>若要指定多個位置的 QoE 保留

  - 這個命令會針對組織中使用的所有 QoE 設定設定，設定 QoE 保留。
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 

</div>

如需詳細資訊，請參閱[CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中部署監視](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


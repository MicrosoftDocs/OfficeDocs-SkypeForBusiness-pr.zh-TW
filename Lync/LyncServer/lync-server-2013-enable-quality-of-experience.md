---
title: Lync Server 2013：啟用經驗品質
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Quality of Experience
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182583(v=OCS.15)
ms:contentKeyID: 48185385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 539408bfaa32565ef76312e1b0d96767edecc169
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-quality-of-experience-in-lync-server-2013"></a>在 Lync Server 2013 中啟用經驗品質

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

經驗品質 (QoE) 會記錄數字資料，指出有關通話與工作階段中所包含參與者、裝置名稱、驅動程式、IP 位址和端點類型的媒體品質和資訊。 如需詳細資訊，請參閱規劃檔中的 [規劃在 Lync Server 2013 中的監視](lync-server-2013-planning-for-monitoring.md) 。

請使用下列程式，為您的整個組織或組織中的每個網站啟用 QoE。

<div>


> [!NOTE]  
> 若要啟用 QoE，您必須先設定監控和監控後端資料庫。 如需詳細資訊，請參閱 <A href="lync-server-2013-deploying-monitoring.md">在 Lync Server 2013 中部署監控</A>。



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台啟用 QoE

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[經驗品質資料]**。

4.  在 [ **經驗品質資料** ] 頁面上，按一下表格中的適當集合，按一下 [ **動作**]，然後按一下 [ **啟用 QoE**]。

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 啟用 QoE

您可以使用 Windows PowerShell 及 **Set CsQoEConfiguration** Cmdlet 來啟用 QoE。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-enable-qoe-for-a-single-location"></a>針對單一位置啟用 QoE

  - 若要啟用 QoE，請將 EnableQoE 參數設定為 True ($True) 。
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a>停用單一位置的 QoE

  - 若要停用 QoE，請將 EnableQoE 參數設定為 False ($False) 。 這不會卸載監控。 它會暫停 QoE 資料的收集和儲存。
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>使用單一命令啟用多個位置的 QoE

  - 此命令會為組織中目前使用的所有 QoE 設定設定啟用 QoE。
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

如需詳細資訊，請參閱 [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration)。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中規劃監控](lync-server-2013-planning-for-monitoring.md)  
[在 Lync Server 2013 中部署監控](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


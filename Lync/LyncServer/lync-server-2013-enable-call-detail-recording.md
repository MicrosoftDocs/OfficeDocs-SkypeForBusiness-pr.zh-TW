---
title: Lync Server 2013：啟用通話詳細資料錄製
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable call detail recording
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520980(v=OCS.15)
ms:contentKeyID: 48183865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b12359e331e9abd2767285a5ef8c32d56433731e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-detail-recording-in-lync-server-2013"></a>啟用 Lync Server 2013 的通話詳細資料錄製

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

通話詳細資料錄製（CDR）記錄對等活動的用法與診斷資訊，包括實例訊息、透過網際網路通訊協定（VoIP）通話、應用程式共用、檔案傳輸及會議。 使用資料可用來計算投資回報率（ROI），而診斷資料可用來針對對等活動和會議進行疑難排解。

使用下列程式可為您的整個組織或貴組織中的每個網站啟用 CDR。

<div>


> [!NOTE]  
> 若要啟用 CDR，您必須設定監視及監視資料庫。 如需詳細資訊，請參閱<A href="lync-server-2013-deploying-monitoring.md">在 Lync Server 2013 中部署監視</A>。



</div>

<div>

## <a name="to-enable-cdr-with-lync-server-control-panel"></a>若要使用 Lync Server [控制台] 啟用 CDR

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [**呼叫詳細資料錄製**]。

4.  在 [**通話詳細資料記錄**] 頁面上，從表格中按一下適當的網站，按一下 [**動作**]，然後按一下 [**啟用 CDR**]。
    
    <div>
    

    > [!NOTE]  
    > 預設會啟用 CDR。

    
    </div>

</div>

<div>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 啟用 CDR

您可以使用 Windows PowerShell 和**CsCdrConfiguration** Cmdlet 來啟用 CDR。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-enable-cdr-for-a-single-location"></a>若要針對單一位置啟用 CDR

  - 若要停用 CDR，請將 EnableCDR 參數設定為 True （$True）。
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

</div>

<div>

## <a name="to-disable-cdr-for-a-single-location"></a>若要針對單一位置停用 CDR

  - 若要停用 CDR，請將 EnableCDR 參數設定為 False （$False）。 停用 CDR 不會卸載監視。 它會暫停 CDR 資料的收集和儲存。
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>若要使用單一命令在多個位置啟用 CDR

  - 這個命令會針對貴組織中目前使用的所有 CDR 配置設定啟用 CDR。
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

</div>

如需詳細資訊，請參閱[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的規劃監控](lync-server-2013-planning-for-monitoring.md)  
[在 Lync Server 2013 中部署監視](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


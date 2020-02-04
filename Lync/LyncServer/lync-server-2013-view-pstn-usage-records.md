---
title: Lync Server 2013：查看 PSTN 使用記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PSTN usage records
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48184361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2551c8bbc40429d7e5bc4af45cae862991381a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-pstn-usage-records-in-lync-server-2013"></a>在 Lync Server 2013 中查看 PSTN 使用狀況記錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

公用交換電話網絡（PSTN）使用記錄會指定呼叫類別（例如內部、當地或長途），這些使用者可以由不同的使用者或組織中的使用者群組進行。 如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的 PSTN 使用記錄](lync-server-2013-pstn-usage-records.md)。

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 來查看 PSTN 使用記錄

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**語音路由**]，然後按一下 [ **PSTN 使用狀況**]。

4.  在 [ **Pstn 使用狀況**] 頁面上，醒目提示您要查看的 PSTN 使用記錄，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。
    
    <div>
    

    > [!NOTE]  
    > 所選 PSTN 使用記錄的唯讀頁面會顯示關聯的路線及相關的語音原則。

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看 PSTN 使用狀況資訊

您也可以使用 Windows PowerShell 和**CsPstnUsage** Cmdlet 來查看 PSTN 使用方式。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看 PSTN 使用狀況資訊

  - 若要查看所有 PSTN 用法的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER：
    
        Get-CsPstnUsage
    
    這個命令會傳回如下所示的資訊：
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

</div>

如需詳細資訊，請參閱[CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage)。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中建立語音原則和設定 PSTN 使用記錄](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[在 Lync Server 2013 中修改語音原則和設定 PSTN 使用狀況記錄](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


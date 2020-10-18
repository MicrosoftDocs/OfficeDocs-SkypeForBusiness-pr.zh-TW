---
title: Lync Server 2013：重設裝置更新規則
description: Lync Server 2013：重設裝置更新規則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a4d42b6aee8f4cb3fd93839b4a8575059ba71cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577839"
---
# <a name="reset-a-device-update-rule-in-lync-server-2013"></a>在 Lync Server 2013 中重設裝置更新規則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

如果您不喜歡更新在測試裝置上的運作方式，您可以重設裝置更新規則，此規則會移除規則的擱置狀態，並且從測試裝置卸載更新。

您可以使用 Lync Server 控制台或 Windows PowerShell 移除裝置更新規則。

<div>


> [!NOTE]  
> 若要卸載您已核准的規則 (也就是) ，請將它還原。 如需詳細資訊，請參閱 <A href="lync-server-2013-restore-a-device-update-rule.md">Restore a Device Update rule In Lync Server 2013</A>。



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台重設裝置更新規則

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **用戶端**]，然後按一下 [ **裝置更新** ] 導覽按鈕。

4.  在 [ **裝置更新** ] 頁面上，執行下列其中一項操作：
    
      - 若要重設一個規則，請選取您要重設的規則。
    
      - 若要重設所有規則，請在 [ **編輯** ] 功能表上，按一下 [ **全選**]。
    
      - 若要重設某個品牌的所有規則，請使用 [ **品牌** ] 欄功能表。

5.  按一下 [ **動作**]，然後按一下 [ **解除擱置的更新**]。
    
    <div>
    

    > [!TIP]  
    > 如果您確定永遠不想要向您取消的裝置更新規則 (s) ，您可能想要將其刪除。 如需詳細資訊，請參閱 <A href="lync-server-2013-remove-a-device-update-rule.md">Remove a Device Update rule In Lync Server 2013</A>。

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 重設裝置更新規則

裝置更新規則也可以使用 Windows PowerShell 和 **Reset CsDeviceUpdateRule** Cmdlet 進行重設。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。

<div>


> [!NOTE]  
> 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a>在伺服器上重設特定裝置更新規則

  - 下列命令會在網頁伺服器上上重設裝置更新規則 d5ce3c10-2588-420a-82ac-dc2d9b1222ff9-82ac-atl-cs-001.litwareinc.com：
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a>重設伺服器上的所有裝置更新規則

  - 此命令會重設網頁伺服器 atl-cs-001.litwareinc.com 上的所有裝置更新規則：
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a>若要重設所有具有特定品牌的裝置更新規則

  - 在此範例中，會重設整個組織中與 Microsoft 品牌相同的所有裝置更新：
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

如需詳細資訊，請參閱 [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>另請參閱


[核准 Lync Server 2013 中的裝置更新規則](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Survivable Branch Appliance 或 Server 上的 Lync Server 2013： 首頁使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6efd5991260ffeec3c6279857625eadfe34eca4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>使用者隸屬於 Survivable Branch Appliance 或 Lync Server 2013 中的伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-12-10_

首頁的程序 Survivable Branch Appliance 或 Survivable Branch 伺服器上的使用者是類似隸屬使用者的程序上的前端集區。 執行 Survivable Branch Appliance 或 Survivable Branch 伺服器的程序在中央網站。

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a>將使用者隸屬於 Survivable Branch Appliance 或 Survivable Branch 伺服器

1.  之前將使用者移至 Survivable Branch 伺服器或 Survivable Branch 伺服器，開啟 [Lync Server 管理命令介面中，，然後執行下列各項：
    
      - 執行指令程式**Test-cspstnoutboundcall**若要確認 Survivable Branch 伺服器正在執行，而且已公用交換電話網路 (PSTN) 連線能力。 如果您要修改 PSTN 閘道內容，使用**Set-cspstngateway**cmdlet。
    
      - 執行指令程式**Get-csvoicepolicy**驗證將會位於 Survivable Branch 伺服器的使用者具備適當的 VoIP 路由原則。 如果您要修改的 VoIP 原則，使用 cmdlet **Set-csvoicepolicy**。
    
      - 執行指令程式**Get-csvoicemailreroutingconfiguration**若要確認已設定語音信箱重新設定。 如果您要修改語音信箱重新路由設定，使用 cmdlet**設定 CsVoicemailReroutingConfiguration**。

2.  在 Lync Server 管理命令介面中，執行 cmdlet **Move-csuser**以移動隸屬使用者。

<div>


> [!NOTE]  
> 您也可以使用 Lync Server 控制台來確認先決條件並隸屬使用者。



</div>

<div>


> [!NOTE]  
> 位於 Lync Server Survivable Branch Appliance 的使用者將無法建立新聊天室或檢視現有的會議室的會議室卡片。



</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[Test-cspstnoutboundcall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[Get-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-csvoicemailreroutingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[Move-csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


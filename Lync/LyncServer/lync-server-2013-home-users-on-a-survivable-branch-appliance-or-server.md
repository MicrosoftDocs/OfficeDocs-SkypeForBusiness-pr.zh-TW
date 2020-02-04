---
title: Lync Server 2013：將使用者隸屬於 Survivable Branch Appliance 或 Survivable Branch Server
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
ms.openlocfilehash: 0c6cca9528e884807f6180d8c99b143eb0041211
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>在 Lync Server 2013 中將使用者隸屬於 Survivable Branch Appliance 或 Survivable Branch Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-12-10_

將使用者放在 Survivable 分支裝置或 Survivable 分支伺服器的程式，與將使用者放在前端池中的程式類似。 在中央網站執行 Survivable 分支裝置或 Survivable 分支伺服器程式。

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a>Survivable 分支裝置或 Survivable 分支伺服器上的家用使用者

1.  在將使用者移至 Survivable 分支伺服器或 Survivable 分支伺服器之前，請先開啟 Lync Server 管理命令介面，然後執行下列所有動作：
    
      - 執行 Cmdlet**測試-CsPstnOutboundCall** ，以驗證 Survivable 分支伺服器是否正在執行，以及是否已設定公用交換電話網絡（PSTN）連線。 如果您需要修改 PSTN 閘道屬性，請使用 Cmdlet **CsPstnGateway**。
    
      - 執行 Cmdlet **CsVoicePolicy** ，確認將駐留在 Survivable 分支伺服器的使用者具有適當的 VoIP 路由原則。 如果您需要修改 VoIP 原則，請使用 Cmdlet **CsVoicePolicy**。
    
      - 執行 Cmdlet **CsVoicemailReroutingConfiguration** ，確認已設定語音信箱重新路由設定。 如果您需要修改語音信箱重新路由設定，請使用 Cmdlet **CsVoicemailReroutingConfiguration**。

2.  在 Lync Server 管理命令介面中，執行 Cmdlet**移動 move-csuser**以移動家用使用者。

<div>


> [!NOTE]  
> 您也可以使用 Lync Server [控制台] 驗證系統必備與家用使用者。



</div>

<div>


> [!NOTE]  
> 駐留在 Lync Server Survivable 分支裝置上的使用者無法建立新的聊天室，或無法查看現有聊天室的聊天室卡片。



</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[CsVoicemailReroutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[移動流覽 Move-csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


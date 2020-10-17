---
title: Lync Server 2013： Survivable 分支裝置或伺服器上的家庭使用者
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
ms.openlocfilehash: add711ca547648a6071a22fee6a0bcd0eeb0f6c0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528200"
---
# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Lync Server 2013 的 Survivable 分支裝置或伺服器上的家庭使用者

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-12-10_

在 Survivable Branch 裝置或 Survivable Branch Server 上，將使用者上指的程式，類似于在前端集區上進行使用者的引導。 在中央網站執行 Survivable Branch 裝置或 Survivable Branch Server 程式。

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a>在 Survivable Branch 裝置或 Survivable Branch Server 上的家庭使用者

1.  將使用者移至 Survivable Branch Server 或 Survivable Branch 伺服器之前，請先開啟 Lync Server 管理命令介面，然後執行下列所有動作：
    
      - 執行 Cmdlet **Test-CsPstnOutboundCall** ，確認 Survivable 分支伺服器正在執行，且已設定公用交換電話網路 (PSTN) 連線。 如果您需要修改 PSTN 閘道屬性，請使用 Cmdlet **Set-CsPstnGateway**。
    
      - 執行 Cmdlet **Get-CsVoicePolicy** ，確認將裝載在 Survivable Branch 伺服器上的使用者具有適當的 VoIP 路由原則。 如果您需要修改 VoIP 原則，請使用 Cmdlet **Set-CsVoicePolicy**。
    
      - 執行 Cmdlet **Get-CsVoicemailReroutingConfiguration** ，確認已設定語音信箱重新路由設定。 如果您需要修改語音信箱重新路由設定，請使用 Cmdlet **Set-CsVoicemailReroutingConfiguration**。

2.  在 Lync Server 管理命令介面中，執行 Cmdlet **Move-CsUser** 以移動家用使用者。

<div>


> [!NOTE]  
> 您也可以使用 Lync Server 控制台來驗證必要條件和家用使用者。



</div>

<div>


> [!NOTE]  
> 在 Lync Server Survivable Branch 裝置上的使用者無法建立新聊天室或查看現有聊天室的會議室卡片。



</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[Get-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoicemailReroutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


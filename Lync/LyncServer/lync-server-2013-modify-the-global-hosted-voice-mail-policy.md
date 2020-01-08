---
title: Lync Server 2013：修改全域託管的語音信箱原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4759fd0cfe4f8a4c55905b265c2418354a6a6dae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a>在 Lync Server 2013 中修改全域託管的語音信箱原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-24_

*全域*託管的語音信箱原則是與 Lync Server 2013 一起安裝。 您可以對其進行修改以符合您的需求，但無法重新命名或刪除該檔案。 若要修改全域原則，您可以使用 CsHostedVoicemailPolicy Cmdlet，為您的特定部署將參數設定為適當的值。

如需[CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a>修改全域託管的語音信箱原則

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 CsHostedVoicemailPolicy Cmdlet，為您的環境設定全域原則參數。 例如，執行：
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    因為這個命令不會指定原則的身分識別參數，所以 Windows PowerShell 命令列介面會在全域託管的語音信箱原則上設定下列值：
    
      - **Destination**指定託管 Exchange UM 服務的完整功能變數名稱（FQDN）。 這個參數是選用的，但如果您嘗試啟用託管語音信箱的使用者，且使用者指派的原則沒有目的地值，enable 將會失敗。
    
      - [**組織**] 指定家用 Lync Server 使用者之 Exchange 承租人的逗號分隔清單。 每個租使用者都必須在託管 Exchange UM 服務上指定為該租使用者的 FQDN。
    
    <div>
    

    > [!NOTE]  
    > 在上一個範例 Cmdlet 中，值 "corp1.litwareinc.com" 會取代組織參數中可能已經存在的任何值。 例如，如果原則已包含以逗號分隔的組織清單，完整清單將會被取代。 如果您想要將組織新增至清單，而不是取代整個清單，請執行如下所示的命令。

    
    </div>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

</div>

</div>

<span> </span>

</div>

</div>

</div>


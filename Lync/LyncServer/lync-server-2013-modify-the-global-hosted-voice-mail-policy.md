---
title: Lync Server 2013：修改全域主控語音信箱原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88d0e29981df18ed883d6c33fb810d86da09d255
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a>在 Lync Server 2013 中修改全域主控語音信箱原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-24_

*通用*主控語音信箱原則是隨 Lync Server 2013 一起安裝。 您可以修改它以符合您的需求，但是您無法重新命名或刪除。 若要修改全域原則，您可以使用 CsHostedVoicemailPolicy 指令程式，將參數設定為特定部署的適當值。

如需[CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a>修改全域主控語音信箱原則

1.  啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 CsHostedVoicemailPolicy 指令程式，為您的環境設定全域原則參數。 例如，執行：
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    因為此命令不會指定原則的 Identity 參數，所以 Windows PowerShell 命令列介面會設定全域主控語音信箱原則的下列值：
    
      - **Destination** 指定主控之 Exchange UM 服務的完整網域名稱 (FQDN)。此參數是選用的，但如果您企圖啟用使用者的主控語音信箱，且指派給使用者的原則沒有 Destination 值，則啟用作業會失敗。
    
      - **組織**指定家用 Lync Server 使用者之 Exchange 承租人的逗號分隔清單。 必須以主控之 Exchange UM 服務上的租用戶之 FQDN 來指定每一個租用戶。
    
    <div>
    

    > [!NOTE]  
    > 在前面的範例 Cmdlet 中，值 "corp1.litwareinc.com" 會取代可能已存在於組織參數中的任何值。 例如，如果原則已包含以逗號分隔的組織清單，則會取代完整清單。 如果您想要將組織新增至清單，而不是取代整個清單，請執行類似下列的命令。

    
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


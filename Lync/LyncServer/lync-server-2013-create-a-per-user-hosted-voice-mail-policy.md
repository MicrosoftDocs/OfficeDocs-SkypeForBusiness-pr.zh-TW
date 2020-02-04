---
title: Lync Server 2013：建立每位使用者託管的語音信箱原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 535515fd11c0cb736b5b6fb4b70d041ea3af8a3c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>在 Lync Server 2013 中建立每使用者託管的語音信箱原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-24_

*每個使用者*的原則只會影響個別的使用者、群組和連絡人物件。 若要部署每個使用者的原則，您必須將原則明確指派給一或多個使用者、群組或連絡人物件。 如需詳細資訊，請參閱[在 Lync Server 2013 中指派每個使用者託管的語音信箱原則](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)。

如需有關使用每個使用者託管語音信箱原則的詳細資訊，請參閱 Lync Server 管理命令介面檔，瞭解下列 Cmdlet：

  - [新-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a>若要建立每位使用者託管的語音信箱原則

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行新的 CsHostedVoicemailPolicy Cmdlet 來建立原則。 例如，執行：
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    前面的範例會建立含每個使用者範圍的託管語音信箱原則，並設定下列參數：
    
      - 身分**識別**會指定原則的唯一識別碼，包括範圍。 針對具有每使用者範圍的原則，此參數值是指定為簡單字串，例如 ExRedmond。
    
      - **Destination**指定託管 Exchange UM 服務的完整功能變數名稱（FQDN）。 這個參數是選用的，但如果您嘗試啟用託管語音信箱的使用者，且使用者指派的原則沒有目的地值，enable 將會失敗。
    
      - **描述**提供原則的選用描述性資訊。
    
      - [**組織**]：指定家用 Lync Server 2013 使用者的 Exchange 租使用者清單（以逗號分隔）。 每個租使用者都必須在託管 Exchange UM 服務上指定為該租使用者的 FQDN。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中指派每個使用者託管的語音信箱原則](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


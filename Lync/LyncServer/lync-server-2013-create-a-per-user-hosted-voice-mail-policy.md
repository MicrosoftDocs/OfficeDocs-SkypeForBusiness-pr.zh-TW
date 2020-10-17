---
title: Lync Server 2013：建立每位使用者的主控語音信箱原則
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
ms.openlocfilehash: 04dc942c0cd44c6390c8a7d6627c5da4b551b94c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501890"
---
# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>在 Lync Server 2013 中建立個別使用者的主控語音信箱原則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-24_

*「個別使用者的」* 原則只會影響個別使用者、群組和連絡人物件。 若要部署個別使用者的原則，您必須明確指派原則給一個或多個使用者、群組或連絡人物件。 如需詳細資訊，請參閱 [在 Lync Server 2013 中指派每位使用者的主控語音信箱原則](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)。

如需使用個別使用者主控語音信箱原則的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：

  - [新 CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a>若要建立個別使用者的裝載語音信箱原則

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 New-CsHostedVoicemailPolicy Cmdlet，建立原則。例如，執行：
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    上述範例會建立個別使用者範圍的裝載語音信箱原則，並設定下列參數：
    
      - **Identity** 指定原則的唯一識別碼，包含範圍。若是個別使用者範圍的原則，此參數值必須以單一字串格式指定，例如 ExRedmond。
    
      - **Destination** 指定主控之 Exchange UM 服務的完整網域名稱 (FQDN)。此參數是選用的，但如果您企圖啟用使用者的主控語音信箱，且指派給使用者的原則沒有 Destination 值，則啟用作業會失敗。
    
      - **Description** 提供關於原則的選用說明資訊。
    
      - **組織** 指定家用 Lync Server 2013 使用者之 Exchange 承租人的逗號分隔清單。 必須以主控之 Exchange UM 服務上的租用戶之 FQDN 來指定每一個租用戶。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中指派每位使用者的主控語音信箱原則](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


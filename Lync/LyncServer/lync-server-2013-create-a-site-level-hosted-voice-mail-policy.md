---
title: Lync Server 2013：建立網站層級託管的語音信箱原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9df91e28eeba8bc9769e4fcbeff6ebba2b3746d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a>在 Lync Server 2013 中建立網站層級託管的語音信箱原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-24_

*網站*原則可能會影響託管在已定義策略之網站上的所有使用者。 如果使用者是針對託管 Exchange UM 存取進行設定，且尚未獲指派每個使用者的原則，則會套用網站原則。 如果您尚未部署網站原則，則會套用全域原則。

如需有關設定網站原則的詳細資訊，請參閱下列 Cmdlet 的 Lync Server 管理命令介面檔：

  - [新-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a>建立網站託管的語音信箱原則

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行新的 CsHostedVoicemailPolicy Cmdlet 來建立原則。 例如，執行：
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    這個範例會建立含網站範圍的託管語音信箱原則，並設定下列參數：
    
      - 身分**識別**會指定原則的唯一識別碼，包括範圍。 針對具有網站範圍的原則，必須在格式`site:` * \<名稱\>* 中指定身分識別參數值，例如。 `site:Redmond`
    
      - **Destination**指定託管 Exchange UM 服務的完整功能變數名稱（FQDN）。 這個參數是選用的，但如果您嘗試啟用託管語音信箱的使用者，且使用者指派的原則沒有目的地值，enable 將會失敗。
    
      - **描述**提供原則的選用描述性資訊。
    
      - [**組織**]：指定家用 Lync Server 2013 使用者的 Exchange 租使用者清單（以逗號分隔）。 每個租使用者都必須在託管 Exchange UM 服務上指定為該租使用者的 FQDN。

</div>

</div>

<span> </span>

</div>

</div>

</div>


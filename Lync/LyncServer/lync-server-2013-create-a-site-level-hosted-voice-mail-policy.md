---
title: Lync Server 2013： 建立網站層級裝載的語音信箱原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b103369591846cc49b2c676a90103675fe09baec
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a>在 Lync Server 2013 中建立的網站層級的主控的語音信箱原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-24_

「網站」** 原則會影響定義該原則之網站上所屬的全部使用者。如果使用者已針對主控 Exchange UM 存取進行設定，且未獲指派個別使用者原則，便會套用網站原則。如果您尚未部署網站原則，則會套用全域原則。

如需設定網站原則的詳細資訊，請參閱 Lync Server 管理命令介面文件的下列 cmdlet:

  - [新 CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-cshostedvoicemailpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-cshostedvoicemailpolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a>建立網站主控的語音信箱原則

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  執行 New-CsHostedVoicemailPolicy Cmdlet，建立原則。例如，執行：
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    此範例會建立網站範圍的主控語音信箱原則，並設定下列參數：
    
      - **Identity** 指定原則的唯一識別碼，包含範圍。 對於網站範圍的原則，Identity 參數值必須指定格式`site:`*\<名稱\>*，例如`site:Redmond`。
    
      - **Destination** 指定主控之 Exchange UM 服務的完整網域名稱 (FQDN)。此參數是選用的，但如果您企圖啟用使用者的主控語音信箱，且指派給使用者的原則沒有 Destination 值，則啟用作業會失敗。
    
      - **Description** 提供關於原則的選用說明資訊。
    
      - **Organization**指定以逗號分隔清單中的 Exchange 承租人該隸屬的 Lync Server 2013 使用者。 必須以主控之 Exchange UM 服務上的租用戶之 FQDN 來指定每一個租用戶。

</div>

</div>

<span> </span>

</div>

</div>

</div>


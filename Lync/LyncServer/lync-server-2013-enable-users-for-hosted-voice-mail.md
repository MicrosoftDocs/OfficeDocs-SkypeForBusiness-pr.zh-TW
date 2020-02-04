---
title: Lync Server 2013：為使用者啟用主控語音信箱
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e0ce9ee4da6ee0a36e5e5f0028371aab8af523f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a>在 Lync Server 2013 中為使用者啟用主控語音信箱

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-24_

按照程式在託管 Exchange 整合通訊（UM）服務上，為語音信箱啟用 Lync Server 2013 使用者。

如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的託管 Exchange 使用者管理](lync-server-2013-hosted-exchange-user-management.md)。

如需[move-csuser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。

<div>


> [!IMPORTANT]  
> 在 Lync Server 2013 使用者可以啟用託管語音信箱之前，必須先部署適用于其使用者帳戶的託管語音信箱原則。 如需詳細資訊，請參閱<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中託管的語音信箱原則</A>。



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a>允許使用者使用託管的語音信箱

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 Move-csuser Cmdlet 來設定託管語音信箱的使用者帳戶。 例如，執行：
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    上述範例會設定下列參數：
    
      - **HostedVoiceMail**可讓使用者的語音信箱呼叫路由至託管 Exchange UM。 它也會通知 Microsoft Lync 2013，以將「撥號語音信箱」指標發亮。
    
      - 身分**識別**指定要修改的使用者帳戶。 身分識別值可以使用下列任何一種格式加以指定：
        
          - 使用者的 SIP 位址
        
          - 使用者的 Active Directory 使用者主要名稱
        
          - 使用者的網域\\登入名稱（例如 contoso\\kenmyer）
        
          - 使用者的 Active Directory 網域服務顯示名稱（例如，Ken Myer）。 如果使用顯示名稱作為身分識別值，您可以使用星號（\*）萬用字元。 例如，恒等 "\* smith" 會傳回其顯示名稱以字串值 "smith" 結尾的所有使用者。
        
        <div>
        

        > [!NOTE]  
        > 使用者的 Active Directory SAM-帳戶名稱不能用來做為身分識別值，因為 SAM-帳戶名稱在林中不一定是唯一的。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


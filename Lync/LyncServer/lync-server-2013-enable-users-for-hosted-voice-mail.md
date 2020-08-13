---
title: Lync Server 2013：針對主控的語音信箱啟用使用者
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
ms.openlocfilehash: 836edd026e6b80404b9a85a3d5a0f53fa2ba574a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a>在 Lync Server 2013 中啟用使用者的主控語音信箱功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-24_

請遵循程式，在主控 Exchange 整合通訊 (UM) 服務上啟用語音信箱的 Lync Server 2013 使用者。

如需詳細資訊，請參閱規劃檔中的[主控 Exchange 使用者管理（Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) ）。

如需[Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。

<div>


> [!IMPORTANT]  
> 在 Lync Server 2013 使用者可以啟用裝載的語音信箱之前，必須先部署套用至使用者帳戶的主控語音信箱原則。 如需詳細資訊，請參閱<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的主控語音信箱原則</A>。



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a>啟用使用者的主控語音信箱

1.  啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 Set-CsUser Cmdlet 以設定主控語音信箱的使用者帳戶。 例如，執行：
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    上述範例會設定下列參數：
    
      - **HostedVoiceMail**可讓使用者的語音信箱呼叫路由傳送至主控 Exchange UM。 它也會向 Microsoft Lync 2013 發出語音訊息，以發光「呼叫語音信箱」指示器。
    
      - **Identity**指定要修改的使用者帳戶。 您可以使用下列任何格式指定 Identity 值：
        
          - 使用者的 SIP 位址
        
          - 使用者的 Active Directory 使用者主體名稱
        
          - 使用者的網域 \\ 登入名稱 (例如，contoso \\ kenmyer) 
        
          - 使用者的 Active Directory 網域服務顯示名稱 (例如，Ken Myer) 。 如果使用顯示名稱做為 Identity 值，您可以使用星號 (\*) 萬用字元。 例如，身分識別 " \* smith" 會傳回顯示名稱結尾為字串值 "Smith" 的所有使用者。
        
        <div>
        

        > [!NOTE]  
        > 使用者的 Active Directory SAM 帳戶名稱不能做為身分識別值，因為 SAM 帳戶名稱在樹系中不一定是唯一的。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


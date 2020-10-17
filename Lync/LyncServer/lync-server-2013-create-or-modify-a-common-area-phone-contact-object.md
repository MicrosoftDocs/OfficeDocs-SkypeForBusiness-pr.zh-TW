---
title: Lync Server 2013：建立或修改公共區域電話連絡人物件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0855db68e1f08a26070689b1699bd200a1edbfaf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504740"
---
# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改公共區域電話連絡人物件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-20_

若要為您的所有公共區域電話建立 Active Directory 網域服務連絡人物件，請使用 **New-CsCommonAreaPhone** Cmdlet。 這個指令程式可以建立新的連絡人物件，以與公共區域電話搭配使用，也可以將現有的連絡人物件與新的通用區域電話產生關聯。 若要修改與公共區域電話相關聯之連絡人物件的屬性，請使用 **CsCommonAreaPhone 指令程式** 。 **Set-CsCommonAreaPhone**的選用參數可讓您變更專案，例如連絡人的 Active Directory 顯示名稱或行統一資源識別項 (URI) 與電話相關聯，並啟用及停用與 Lync Server 搭配使用的帳戶。 如需所有可用修改的詳細資訊，請參閱 Parameters 區段 [CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone)。 如需 **New-CsCommonAreaPhone** 參數的詳細資訊，請參閱 [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone)。

您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行這兩個 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a>建立公共區域電話連絡人物件

  - 若要建立新的公共區域電話連絡人物件，請使用 **New-CsCommonAreaPhone** Cmdlet。 在建立連絡人物件時，至少必須提供下列資訊：
    
      - **LineUri**：指派給公共區域電話的電話號碼。 請注意，指定電話號碼時，必須使用 e.164 格式。
    
      - **RegistrarPool**：將主控 contact 物件之註冊集區的完整功能變數名稱 (FQDN) 。
    
      - **OU**：將建立連絡人物件的 Active Directory 容器的辨別名稱。
    
    我們也建議您提供 Active Directory 網域服務顯示名稱。 否則，您必須使用 GUID 來指定電話身分識別。 例如：
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a>修改公共區域電話連絡人物件

  - 若要修改現有的公共區域電話的屬性，contact 物件使用 **CsCommonAreaPhone 指令程式** 。 例如，此命令會使用 DisplayName 會議廳設定常見區域電話的 SIP 位址：
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

如需詳細資訊，請參閱 [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) Cmdlet 和 [CsCommonAreaPhone 指令程式](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>


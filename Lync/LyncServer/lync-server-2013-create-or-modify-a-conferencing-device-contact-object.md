---
title: Lync Server 2013：建立或修改會議裝置連絡人物件
description: Lync Server 2013：建立或修改會議裝置連絡人物件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 853ee1c7dfda2fda99431b8cc1a5210a51f39a4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578009"
---
# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改會議裝置連絡人物件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-02_

若要建立會議聊天室物件，請先建立 Active Directory 使用者帳戶來代表裝置。 然後，使用 **Enable-CsMeetingRoom** Cmdlet 以啟用該帳戶充當會議裝置。 如果您需要變更現有會議裝置的屬性，請使用 **Set-CsMeetingRoom** Cmdlet。

您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話執行這些 Cmdlet。

<div>


> [!NOTE]  
> 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a>建立會議裝置

  - 在您建立代表新會議裝置的 Active Directory 使用者帳戶之後，使用 **Enable-CsMeetingRoom** Cmdlet 來啟用它。 請務必加入) 會議裝置身分識別、b) 會議室帳戶所在的註冊機構集區，以及 c) 指派給該帳戶的 SIP 位址。 例如：
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a>修改會議裝置

  - 若要修改現有會議裝置的屬性值，請使用 **Set-CsMeetingRoom** Cmdlet。 例如，下列命令會更新與會議裝置相關聯的電話號碼 (LineUri) ：
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

如需詳細資訊，請參閱 [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) Cmdlet 及 [Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>


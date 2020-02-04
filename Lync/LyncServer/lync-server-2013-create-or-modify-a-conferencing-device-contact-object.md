---
title: Lync Server 2013：建立或修改會議裝置連絡人物件
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
ms.openlocfilehash: 56d594f0bf6e393545f4a7c29785b5f66b328bdc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改會議裝置連絡人物件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-02_

若要建立會議會議室物件，請先建立 Active Directory 使用者帳戶來代表裝置。 接著，使用**enable-CsMeetingRoom** Cmdlet 來啟用該帳戶作為會議裝置。 如果您需要變更現有會議裝置的屬性，請使用**CsMeetingRoom** Cmdlet。

這些 Cmdlet 都可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。

<div>


> [!NOTE]  
> 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a>建立會議裝置

  - 在您建立代表新會議裝置的 Active Directory 使用者帳戶之後，請使用**enable-CsMeetingRoom** Cmdlet 來啟用它。 請務必包含 a）會議裝置身分識別、b）房間帳戶所在的註冊機構池，以及 c）要指派給該帳戶的 SIP 位址。 例如：
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a>修改會議裝置

  - 若要修改現有會議裝置的屬性值，請使用**CsMeetingRoom** Cmdlet。 例如，下列命令會更新與會議裝置相關聯的電話號碼（LineUri）：
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

如需詳細資訊，請參閱[Enable CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) Cmdlet 和[CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>


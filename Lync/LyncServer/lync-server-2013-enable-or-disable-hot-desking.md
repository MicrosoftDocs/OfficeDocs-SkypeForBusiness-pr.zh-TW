---
title: Lync Server 2013：啟用或停用熱 desking
description: Lync Server 2013：啟用或停用熱 desking。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fd22c9bf51078324cfe5e215bd154503c2d9b57
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552429"
---
# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a>啟用或停用 Lync Server 2013 中的熱 desking

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-20_

您可以將公用區域電話設定為 *熱電話*。 在使用手機的情況下，使用者可以登入自己的使用者帳戶，並在登入之後，使用 Lync Server 功能及其自己的使用者設定檔設定。 使用用戶端原則來管理熱 desking：若要啟用或停用熱 desking，您需要修改您的公用區域電話所使用的用戶端原則。 如需如何判斷已指派給您一般區域電話之會議原則的詳細資訊，請參閱 [在 Lync Server 2013 中查看常見區域電話資訊](lync-server-2013-view-common-area-phone-information.md)。

您可以使用 **New-CSClientPolicy** Cmdlet 的 EnableHotdesking 參數或 **Set-CSClientPolicy** 指令，在電話上啟用或停用熱 desking，如下所示。 請從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行這些 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>


<div>

## <a name="enabling-hot-desking"></a>啟用熱 desking

  - 若要啟用常見區域電話的熱 desking，您必須修改指派給該電話 (或電話集合) 的用戶端原則。
    
    在您識別需要修改的原則之後，下一步是使用 **Set-CsClientPolicy** Cmdlet 將 EnableHotdesking 參數設定為 True。 例如：
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - 或者，您也可以使用 **New-CsClientPolicy** Cmdlet 來建立新的用戶端原則，以啟用熱 desking。 例如：
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> 建立此原則之後，您必須將其指派給適當的公共區域電話。 如需詳細資訊，請參閱 <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">將 Lync Server 2013 中的原則指派給一般區域電話</A>。



</div>

<div>

## <a name="disabling-hot-desking"></a>停用熱 desking

  - 若要停用通用區域電話的熱 desking，請將 **Set-CsClientPolicy** Cmdlet 的 EnableHotdesking 參數重設為預設值 False。 例如：
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

如需詳細資訊，請參閱 [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) Cmdlet 及 [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>


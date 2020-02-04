---
title: Lync Server 2013：啟用或停用熱 desking
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
ms.openlocfilehash: 7c56d7ae13be9afa3af7e4732242a86f4be4c458
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a>在 Lync Server 2013 中啟用或停用熱 desking

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-20_

您可以將常用的區域電話設定為「*熱手機*」。 使用 [熱手機]，使用者可以登入自己的使用者帳戶，並在登入之後，使用 Lync Server 功能及其自己的使用者設定檔設定。 熱 desking 是使用用戶端原則進行管理：若要啟用或停用熱 desking，您必須修改您的通用區域手機所使用的用戶端原則。 如需如何判斷已指派給您常見區域手機之會議原則的詳細資訊，請參閱[在 Lync Server 2013 中查看常見的區域電話資訊](lync-server-2013-view-common-area-phone-information.md)。

您可以使用**新的-CSClientPolicy** Cmdlet 的 EnableHotdesking 參數或**Set CSClientPolicy** Cmdlet 來啟用或停用手機上的熱 desking，如下所示。 從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行這些 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>


<div>

## <a name="enabling-hot-desking"></a>啟用熱 desking

  - 若要啟用常見區域手機的熱 desking，您必須修改已指派給該電話（或手機集合）的用戶端原則。
    
    在您發現需要修改的原則之後，下一步就是使用**CsClientPolicy** Cmdlet，將 EnableHotdesking 參數設定為 True。 例如：
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - 或者，您也可以使用**新的 CsClientPolicy** Cmdlet 來建立啟用熱 desking 的新用戶端原則。 例如：
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> 建立此原則之後，您必須將它指派給適當的常見區域電話。 如需詳細資訊，請參閱<A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">在 Lync Server 2013 中將原則指派給常見的區域電話</A>。



</div>

<div>

## <a name="disabling-hot-desking"></a>停用熱 desking

  - 若要停用常用區域手機的熱 desking，請將**CsClientPolicy** Cmdlet 的 EnableHotdesking 參數重設為預設值 False。 例如：
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

如需詳細資訊，請參閱[新版 CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) Cmdlet 和[CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>


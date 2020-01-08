---
title: Lync Server 2013：查看常見的區域電話資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View common area phone information
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994081(v=OCS.15)
ms:contentKeyID: 51803992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 900beb4f96fd71e0e6a4ded40d776f1e7d356529
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-common-area-phone-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看常見區域電話資訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-20_

您可以透過**CsCommonAreaPhone** Cmdlet，查看設定為在您的組織中使用之通用區域電話的相關資訊。 如果在沒有任何參數的情況下使用，這個 Cmdlet 會傳回所有您所有常見區域手機的相關資訊。 選用的參數提供不同的方式來篩選資訊。 例如，您可以傳回在指定組織單位（OU）中有連絡人物件的所有常見區域電話，或是指定建築物中的所有連絡人物件。 如需**取得 CsCommonAreaPhone**參數的詳細資訊，請參閱[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)。

從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行**CsCommonAreaPhone** 。

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a>查看所有常用區域手機的相關資訊

  - 若要查看所有常見區域手機的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 Enter 鍵：
    
        Get-CsCommonAreaPhone
    
    您會收到類似以下的資訊：
    
        Identity           : CN=Building 14 Lobby,OU=Redmond,
                             DC=litwareinc,DC=com
        RegistrarPool      : atl-cs-001.litwareinc.com
        Enabled            : True
        SipAddress         : sip:4714e34b-9781-421d-b07a-
                             52056b5b4a56@litwareinc.com
        ClientPolicy       :
        PinPolicy          :
        VoicePolicy        :
        MobilityPolicy     :
        GroupChatPolicy    :
        ConferencingPolicy :
        LineURI            : tel:+14255550712
        DisplayNumber      : 1-425-555-0712
        DisplayName        : Building 14 Lobby
        Description        :
        ExUmEnabled        : False

</div>

如需詳細資訊，請參閱[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>


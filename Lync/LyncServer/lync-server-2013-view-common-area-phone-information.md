---
title: Lync Server 2013：查看共同區域電話資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View common area phone information
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994081(v=OCS.15)
ms:contentKeyID: 51803992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b2a3bc8191b093e589d74d9783ddb6323cf3b2a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506540"
---
# <a name="view-common-area-phone-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看共同區域電話資訊

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-20_

您可以使用 **Get-CsCommonAreaPhone** Cmdlet，查看設定供組織使用之公用區域電話的相關資訊。 使用無任何參數時，此 Cmdlet 會傳回所有公用區域電話的相關資訊。 選用參數提供不同的篩選資訊的方式。 例如，您可以傳回在指定的組織單位 (OU) 或所有位於指定大樓中的連絡人物件中，都有 contact 物件的所有公共區域電話。 如需 **Get-CsCommonAreaPhone** 參數的詳細資訊，請參閱 [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)。

請從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行 **Get-CsCommonAreaPhone** 。

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a>查看您所有通用區域電話的資訊

  - 若要查看所有通用區域電話的資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 Enter：
    
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

如需詳細資訊，請參閱 [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) Cmdlet 的 [說明] 主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>


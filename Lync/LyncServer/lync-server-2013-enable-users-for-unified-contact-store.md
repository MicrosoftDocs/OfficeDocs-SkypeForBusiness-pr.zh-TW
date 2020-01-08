---
title: Lync Server 2013：為使用者啟用整合連絡人存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable users for unified contact store
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48184599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ece699d8c5b43e09323708c075687bfe81146e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a>在 Lync Server 2013 中為使用者啟用整合連絡人存放區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-07_

當您部署 Lync Server 2013 併發布拓撲時，預設會為所有使用者啟用「整合連絡人存放區」。 您在部署 Lync Server 2013 之後，不需要採取任何其他動作即可啟用 [整合連絡人存放區]。 不過，您可以使用**CsUserServicesPolicy** Cmdlet 來自訂哪些使用者可以使用 [整合的連絡人] 存放區。 您可以在全球、由網站、由租使用者，或由個人或個人群組來啟用此功能。

<div>

## <a name="to-enable-users-for-unified-contact-store"></a>若要讓使用者使用整合連絡人存放區

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  請執行下列任何一項操作：
    
      - 若要讓所有 Lync Server 使用者全域都能使用整合連絡人存放區，請在命令列輸入：
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - 若要針對特定網站的使用者啟用整合連絡人存放區，請在命令列輸入：
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        例如：
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - 若要啟用租使用者的整合連絡人存放區，請在命令列輸入：
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        例如：
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - 若要針對特定使用者啟用整合連絡人存放區，請在命令列輸入：
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > 您也可以使用使用者別名或 SIP URI，而不是使用者的顯示名稱。

        
        </div>
        
        例如：
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > 在前面的範例中，第一個命令會建立名為 [ <EM>UCS</EM> ] 的新使用者原則，並將 UcsAllowed 標誌設定為 True。 第二個命令會將原則指派給使用者，並使用顯示名稱 Ken Myer，這表示現在已為整合連絡人存放區啟用 Ken Myer。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013： 啟用整合連絡人存放區的使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for unified contact store
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48184599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b99fd96b16d19305ea5bb63ea9f84096ef6117c7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a>啟用使用者的 Lync Server 2013 中整合連絡人存放區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-07_

當您部署 Lync Server 2013，並發行拓撲時，則整合連絡人存放區預設會啟用所有使用者。 您不需要採取任何其他的動作，來啟用整合連絡人存放區之後，您將部署 Lync Server 2013。 不過，您可以使用 **Set-CsUserServicesPolicy** Cmdlet 自訂哪些連絡人有整合連絡人存放區可用。 您可以全域、依網站、依承租人或依個人或個人群組啟用此功能。

<div>

## <a name="to-enable-users-for-unified-contact-store"></a>啟用整合連絡人存放區的使用者

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  執行下列任一項作業：
    
      - 若要啟用整合連絡人存放區全域所有 Lync Server 使用者，請在命令列中輸入：
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - 若要對特定網站的使用者啟用整合連絡人存放區，請在命令列中輸入：
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        例如：
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - 若要依承租人啟用整合連絡人存放區，請在命令列中輸入：
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        例如：
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - 若要對特定使用者啟用整合連絡人存放區，請在命令列中輸入：
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > 您也可以使用使用者別名或 SIP URI，而不使用使用者顯示名稱。

        
        </div>
        
        例如：
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > 在上一個範例中，第一個命令建立名稱為「UCS 已啟用使用者」<EM></EM> 的新個別使用者原則，而且將 UcsAllowed 旗標設定為 True。第二個指令將該原則指派給顯示名稱為 Ken Myer 的使用者，這表示目前已針對 Ken Myer 啟用整合連絡人存放區。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


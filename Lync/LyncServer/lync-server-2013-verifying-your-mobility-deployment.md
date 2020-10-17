---
title: Lync Server 2013：驗證行動性部署
description: Lync Server 2013：驗證行動性部署。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying your mobility deployment
ms:assetid: 72f9b4d3-57b0-4705-9480-cfdca313a70c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690024(v=OCS.15)
ms:contentKeyID: 48184477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eadda35438961e469fdd5fa7976762141b26a385
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564439"
---
# <a name="verifying-your-mobility-deployment-in-lync-server-2013"></a>在 Lync Server 2013 中驗證行動性部署

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-12_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

在您部署 Lync Server 行動服務和 Lync Server 自動探索服務之後，請執行測試交易，以確認您的部署正確運作。 您可以執行 **Test-CsUcwaConference** ，以測試兩個使用 Lync 2013 行動用戶端的使用者在會議中建立、加入和通訊的能力。 若要使用此測試交易，您需要有兩個實際的使用者或測試使用者，以及其完整認證。

您可以使用 **Test-CsMcxP2PIM** 來測試在使用 Lync 2010 Mobile 的兩位使用者之間傳送立即訊息。 類似 **Test-CsUcwaConference**，您可以使用兩個實際的使用者或兩個預先定義的測試使用者。

<div>

## <a name="to-test-conferencing-for-lync-2013-mobile-clients"></a>若要測試 Lync 2013 行動用戶端的會議

1.  在安裝 Lync Server 管理命令介面和 Ocscore.msi 的任何電腦上以 CsAdministrator 角色成員的身分登入。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令列中輸入：
    
        Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
    
    您可以在指令碼中設定認證，並將其傳遞至測試 Cmdlet。例如：
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v

</div>

<div>

## <a name="to-test-person-to-person-instant-messaging-im-for-lync-2010-mobile"></a>測試 Lync 2010 Mobile 的「人員對人員立即訊息 (IM) 

1.  在安裝 Lync Server 管理命令介面和 Ocscore.msi 的任何電腦上以 CsAdministrator 角色成員的身分登入。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令列中輸入：
    
        Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
    
    您可以在指令碼中設定認證，並將其傳遞至測試 Cmdlet。例如：
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v

</div>

<div>

## <a name="see-also"></a>另請參閱


[Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM)  
[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


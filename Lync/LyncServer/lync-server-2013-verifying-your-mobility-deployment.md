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
# <a name="verifying-your-mobility-deployment-in-lync-server-2013"></a><span data-ttu-id="08aeb-103">在 Lync Server 2013 中驗證行動性部署</span><span class="sxs-lookup"><span data-stu-id="08aeb-103">Verifying your mobility deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08aeb-104">_**主題上次修改日期：** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="08aeb-104">_**Topic Last Modified:** 2013-02-12_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="08aeb-105">在您部署 Lync Server 行動服務和 Lync Server 自動探索服務之後，請執行測試交易，以確認您的部署正確運作。</span><span class="sxs-lookup"><span data-stu-id="08aeb-105">After you deploy the Lync Server Mobility Service and Lync Server Autodiscover Service, run a test transaction to verify that your deployment works correctly.</span></span> <span data-ttu-id="08aeb-106">您可以執行 **Test-CsUcwaConference** ，以測試兩個使用 Lync 2013 行動用戶端的使用者在會議中建立、加入和通訊的能力。</span><span class="sxs-lookup"><span data-stu-id="08aeb-106">You can run **Test-CsUcwaConference** to test the ability of two users who are using Lync 2013 Mobile clients to create, join and communicate in a conference.</span></span> <span data-ttu-id="08aeb-107">若要使用此測試交易，您需要有兩個實際的使用者或測試使用者，以及其完整認證。</span><span class="sxs-lookup"><span data-stu-id="08aeb-107">To use this test transaction, you need two actual users or test users, and their full credentials.</span></span>

<span data-ttu-id="08aeb-108">您可以使用 **Test-CsMcxP2PIM** 來測試在使用 Lync 2010 Mobile 的兩位使用者之間傳送立即訊息。</span><span class="sxs-lookup"><span data-stu-id="08aeb-108">You use **Test-CsMcxP2PIM** to test sending an instant message between two users who are using Lync 2010 Mobile.</span></span> <span data-ttu-id="08aeb-109">類似 **Test-CsUcwaConference**，您可以使用兩個實際的使用者或兩個預先定義的測試使用者。</span><span class="sxs-lookup"><span data-stu-id="08aeb-109">Similar to **Test-CsUcwaConference**, you use two actual users or two predefined test users.</span></span>

<div>

## <a name="to-test-conferencing-for-lync-2013-mobile-clients"></a><span data-ttu-id="08aeb-110">若要測試 Lync 2013 行動用戶端的會議</span><span class="sxs-lookup"><span data-stu-id="08aeb-110">To test conferencing for Lync 2013 Mobile clients</span></span>

1.  <span data-ttu-id="08aeb-111">在安裝 Lync Server 管理命令介面和 Ocscore.msi 的任何電腦上以 CsAdministrator 角色成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="08aeb-111">Log on as a member of the CsAdministrator role on any computer where Lync Server Management Shell and Ocscore are installed.</span></span>

2.  <span data-ttu-id="08aeb-112">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="08aeb-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="08aeb-113">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="08aeb-113">At the command line, type:</span></span>
    
        Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
    
    <span data-ttu-id="08aeb-p103">您可以在指令碼中設定認證，並將其傳遞至測試 Cmdlet。例如：</span><span class="sxs-lookup"><span data-stu-id="08aeb-p103">You can set credentials in a script and pass them to the test cmdlet. For example:</span></span>
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v

</div>

<div>

## <a name="to-test-person-to-person-instant-messaging-im-for-lync-2010-mobile"></a><span data-ttu-id="08aeb-116">測試 Lync 2010 Mobile 的「人員對人員立即訊息 (IM) </span><span class="sxs-lookup"><span data-stu-id="08aeb-116">To test person-to-person instant messaging (IM) for Lync 2010 Mobile</span></span>

1.  <span data-ttu-id="08aeb-117">在安裝 Lync Server 管理命令介面和 Ocscore.msi 的任何電腦上以 CsAdministrator 角色成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="08aeb-117">Log on as a member of the CsAdministrator role on any computer where Lync Server Management Shell and Ocscore are installed.</span></span>

2.  <span data-ttu-id="08aeb-118">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="08aeb-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="08aeb-119">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="08aeb-119">At the command line, type:</span></span>
    
        Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
    
    <span data-ttu-id="08aeb-p104">您可以在指令碼中設定認證，並將其傳遞至測試 Cmdlet。例如：</span><span class="sxs-lookup"><span data-stu-id="08aeb-p104">You can set credentials in a script and pass them to the test cmdlet. For example:</span></span>
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="08aeb-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="08aeb-122">See Also</span></span>


[<span data-ttu-id="08aeb-123">Test-CsMcxP2PIM</span><span class="sxs-lookup"><span data-stu-id="08aeb-123">Test-CsMcxP2PIM</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM)  
[<span data-ttu-id="08aeb-124">Test-CsUcwaConference</span><span class="sxs-lookup"><span data-stu-id="08aeb-124">Test-CsUcwaConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


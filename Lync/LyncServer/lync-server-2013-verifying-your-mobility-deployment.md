---
title: Lync Server 2013： 驗證行動部署
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
ms.openlocfilehash: f044d3e6df799f70e33994ff90f8ebfed77c2478
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verifying-your-mobility-deployment-in-lync-server-2013"></a><span data-ttu-id="932fb-102">驗證行動部署 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="932fb-102">Verifying your mobility deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="932fb-103">_**上次修改主題：** 2013年-02-12_</span><span class="sxs-lookup"><span data-stu-id="932fb-103">_**Topic Last Modified:** 2013-02-12_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="932fb-104">部署 Lync Server Mobility Service 和 Lync Server 自動探索服務之後，請執行測試交易若要驗證您的部署正常運作。</span><span class="sxs-lookup"><span data-stu-id="932fb-104">After you deploy the Lync Server Mobility Service and Lync Server Autodiscover Service, run a test transaction to verify that your deployment works correctly.</span></span> <span data-ttu-id="932fb-105">您可以執行**Test-csucwaconference**若要測試的兩個使用者建立、 加入及通訊會議中使用 Lync 2013 行動用戶端的能力。</span><span class="sxs-lookup"><span data-stu-id="932fb-105">You can run **Test-CsUcwaConference** to test the ability of two users who are using Lync 2013 Mobile clients to create, join and communicate in a conference.</span></span> <span data-ttu-id="932fb-106">若要使用此測試交易，您需要兩個實際使用者，或測試使用者，以及其完整的認證。</span><span class="sxs-lookup"><span data-stu-id="932fb-106">To use this test transaction, you need two actual users or test users, and their full credentials.</span></span>

<span data-ttu-id="932fb-107">您可以使用**Test-csmcxp2pim**來測試傳送立即訊息之間使用 Lync 2010 Mobile 的兩個使用者。</span><span class="sxs-lookup"><span data-stu-id="932fb-107">You use **Test-CsMcxP2PIM** to test sending an instant message between two users who are using Lync 2010 Mobile.</span></span> <span data-ttu-id="932fb-108">類似於**Test-csucwaconference**，您使用兩個實際使用者或兩個預先定義的測試使用者。</span><span class="sxs-lookup"><span data-stu-id="932fb-108">Similar to **Test-CsUcwaConference**, you use two actual users or two predefined test users.</span></span>

<div>

## <a name="to-test-conferencing-for-lync-2013-mobile-clients"></a><span data-ttu-id="932fb-109">若要測試 Lync 2013 行動用戶端的會議</span><span class="sxs-lookup"><span data-stu-id="932fb-109">To test conferencing for Lync 2013 Mobile clients</span></span>

1.  <span data-ttu-id="932fb-110">安裝 Lync Server 管理命令介面和 Ocscore 的任何電腦上 CsAdministrator 角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="932fb-110">Log on as a member of the CsAdministrator role on any computer where Lync Server Management Shell and Ocscore are installed.</span></span>

2.  <span data-ttu-id="932fb-111">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="932fb-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="932fb-112">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="932fb-112">At the command line, type:</span></span>
    
        Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
    
    <span data-ttu-id="932fb-p103">您可以在指令碼中設定認證，並將其傳遞至測試 Cmdlet。例如：</span><span class="sxs-lookup"><span data-stu-id="932fb-p103">You can set credentials in a script and pass them to the test cmdlet. For example:</span></span>
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v

</div>

<div>

## <a name="to-test-person-to-person-instant-messaging-im-for-lync-2010-mobile"></a><span data-ttu-id="932fb-115">若要測試個人對個人立即訊息 (IM) for Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="932fb-115">To test person-to-person instant messaging (IM) for Lync 2010 Mobile</span></span>

1.  <span data-ttu-id="932fb-116">安裝 Lync Server 管理命令介面和 Ocscore 的任何電腦上 CsAdministrator 角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="932fb-116">Log on as a member of the CsAdministrator role on any computer where Lync Server Management Shell and Ocscore are installed.</span></span>

2.  <span data-ttu-id="932fb-117">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="932fb-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="932fb-118">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="932fb-118">At the command line, type:</span></span>
    
        Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
    
    <span data-ttu-id="932fb-p104">您可以在指令碼中設定認證，並將其傳遞至測試 Cmdlet。例如：</span><span class="sxs-lookup"><span data-stu-id="932fb-p104">You can set credentials in a script and pass them to the test cmdlet. For example:</span></span>
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="932fb-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="932fb-121">See Also</span></span>


[<span data-ttu-id="932fb-122">Test-csmcxp2pim</span><span class="sxs-lookup"><span data-stu-id="932fb-122">Test-CsMcxP2PIM</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM)  
[<span data-ttu-id="932fb-123">Test-csucwaconference</span><span class="sxs-lookup"><span data-stu-id="932fb-123">Test-CsUcwaConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


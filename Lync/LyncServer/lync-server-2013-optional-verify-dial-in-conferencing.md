---
title: 'Lync Server 2013: （選用） 驗證電話撥入式會議'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425905(v=OCS.15)
ms:contentKeyID: 48183941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c5fbe9298a3a4157dfc62a31d7a429079ac1853
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="cd408-102">（選用）確認 Lync Server 2013 中的電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="cd408-102">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd408-103">_**主題上次修改日期：** 2011年-01-21_</span><span class="sxs-lookup"><span data-stu-id="cd408-103">_**Topic Last Modified:** 2011-01-21_</span></span>

<span data-ttu-id="cd408-104">若要確認電話撥入式會議設定網頁和撥入式存取號碼正確運作，您需要執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="cd408-104">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>

  - <span data-ttu-id="cd408-105">登入簡單 URL，以測試 [電話撥入式會議設定] 網頁。</span><span class="sxs-lookup"><span data-stu-id="cd408-105">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>

  - <span data-ttu-id="cd408-p101">執行本主題稍後的指令碼，以測試特定集區的存取號碼是否正常運作。此指令碼會模擬撥打存取號碼。您需要特定集區裝載控之某個整合通訊 (UC) 用戶端的 SIP 位址和認證，才能使用此指令碼。</span><span class="sxs-lookup"><span data-stu-id="cd408-p101">Test that access numbers work correctly for a specific pool by running the script later in this topic. This script simulates calls to access numbers. You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>

<span data-ttu-id="cd408-109">這是選用步驟。</span><span class="sxs-lookup"><span data-stu-id="cd408-109">This step is optional.</span></span>

<div>

## <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="cd408-110">若要測試特定集區的存取號碼</span><span class="sxs-lookup"><span data-stu-id="cd408-110">To test access numbers for a specific pool</span></span>

1.  <span data-ttu-id="cd408-111">以 RTCUniversalServerAdmins 群組成員或 **Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="cd408-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="cd408-112">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="cd408-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cd408-113">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="cd408-113">Run the following at the command prompt:</span></span>
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    <span data-ttu-id="cd408-p102">產生的報告會顯示「成功」或「失敗」，以及特定的診斷資訊。使用 -Verbose 旗標會進一步顯示找到幾個存取號碼，以及這些存取號碼的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="cd408-p102">The resulting report shows either Success or Failure, along with specific diagnostic information. The –Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


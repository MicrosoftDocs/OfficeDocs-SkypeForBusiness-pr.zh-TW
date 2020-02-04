---
title: Lync Server 2013：(選用) 驗證電話撥入式會議
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
ms.openlocfilehash: f1b5f078ccd5e95df708012b7be1527736133392
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="b58f0-102">Lync Server 2013 中的 (選用) 驗證電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="b58f0-102">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b58f0-103">_**主題上次修改日期：** 2011-01-21_</span><span class="sxs-lookup"><span data-stu-id="b58f0-103">_**Topic Last Modified:** 2011-01-21_</span></span>

<span data-ttu-id="b58f0-104">若要確認電話撥入式會議設定網頁和撥入式存取號碼都能正常運作，您必須執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b58f0-104">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>

  - <span data-ttu-id="b58f0-105">登入簡單的 URL，測試電話撥入式會議設定網頁。</span><span class="sxs-lookup"><span data-stu-id="b58f0-105">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>

  - <span data-ttu-id="b58f0-106">您可以在本主題稍後執行腳本，以測試存取號碼是否能在特定的池中正常運作。</span><span class="sxs-lookup"><span data-stu-id="b58f0-106">Test that access numbers work correctly for a specific pool by running the script later in this topic.</span></span> <span data-ttu-id="b58f0-107">此腳本會類比存取號碼的通話。</span><span class="sxs-lookup"><span data-stu-id="b58f0-107">This script simulates calls to access numbers.</span></span> <span data-ttu-id="b58f0-108">您需要在特定的池中託管的單一整合通訊（UC）用戶端的 SIP 位址和認證，才能使用此腳本。</span><span class="sxs-lookup"><span data-stu-id="b58f0-108">You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>

<span data-ttu-id="b58f0-109">此為選用步驟。</span><span class="sxs-lookup"><span data-stu-id="b58f0-109">This step is optional.</span></span>

<div>

## <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="b58f0-110">測試特定資源的存取號碼</span><span class="sxs-lookup"><span data-stu-id="b58f0-110">To test access numbers for a specific pool</span></span>

1.  <span data-ttu-id="b58f0-111">以 RTCUniversalServerAdmins 群組的成員或**Cs-ServerAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="b58f0-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="b58f0-112">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="b58f0-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b58f0-113">在命令提示字元執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b58f0-113">Run the following at the command prompt:</span></span>
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    <span data-ttu-id="b58f0-114">產生的報告會顯示成功或失敗，以及特定的診斷資訊。</span><span class="sxs-lookup"><span data-stu-id="b58f0-114">The resulting report shows either Success or Failure, along with specific diagnostic information.</span></span> <span data-ttu-id="b58f0-115">-Verbose 標誌提供有關已找到多少個存取號碼的詳細資訊，以及它們的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b58f0-115">The –Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


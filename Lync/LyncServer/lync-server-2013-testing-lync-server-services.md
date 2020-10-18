---
title: Lync Server 2013：測試 Lync Server 服務
description: Lync Server 2013：測試 Lync Server 服務。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f04cf5e0c098c671b6fb126d4607f3cdba107712
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575219"
---
# <a name="testing-lync-server-services-in-lync-server-2013"></a><span data-ttu-id="b66b6-103">在 Lync Server 2013 中測試 Lync Server 服務</span><span class="sxs-lookup"><span data-stu-id="b66b6-103">Testing Lync Server services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b66b6-104">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="b66b6-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b66b6-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="b66b6-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b66b6-106">每日</span><span class="sxs-lookup"><span data-stu-id="b66b6-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b66b6-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="b66b6-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b66b6-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b66b6-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b66b6-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="b66b6-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b66b6-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b66b6-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b66b6-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsComputer Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="b66b6-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsComputer cmdlet.</span></span> <span data-ttu-id="b66b6-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b66b6-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b66b6-113">描述</span><span class="sxs-lookup"><span data-stu-id="b66b6-113">Description</span></span>

<span data-ttu-id="b66b6-114">Test-CsComputer 驗證本機電腦上執行的所有 Lync Server 2013 服務的狀態。</span><span class="sxs-lookup"><span data-stu-id="b66b6-114">Test-CsComputer verifies the status of all the Lync Server 2013 services that are running on the local computer.</span></span> <span data-ttu-id="b66b6-115"> (Test-CsComputer 只能在本機執行，所以無法從 Windows PowerShell 的遠端實例執行。 ) 指令程式也會檢查是否已在電腦上開啟適當的防火牆埠，並決定當您安裝 Lync Server 2013 時所建立的 Active Directory 群組是否已新增至對應的本地群組。</span><span class="sxs-lookup"><span data-stu-id="b66b6-115">(Test-CsComputer can only be run locally, it cannot be run from a remote instance of Windows PowerShell.) The cmdlet also checks whether the appropriate firewall ports are opened on the computer, and determines whether the Active Directory groups that were created when you installed Lync Server 2013 were added to the corresponding local groups.</span></span> <span data-ttu-id="b66b6-116">例如，Test-CsComputer 會驗證是否已將 Active Directory 群組 RTCUniversalUserAdmins 新增至 Administrators 群組。</span><span class="sxs-lookup"><span data-stu-id="b66b6-116">For example, Test-CsComputer will verify that the Active Directory group RTCUniversalUserAdmins was added to the Administrators group.</span></span>

<span data-ttu-id="b66b6-117">如需詳細資訊，請參閱 [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="b66b6-117">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b66b6-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="b66b6-118">Running the test</span></span>

<span data-ttu-id="b66b6-119">Test-CsComputer Cmdlet 只能在本機電腦上執行，所以您無法從 Windows PowerShell 的遠端實例呼叫 Test-CsComputer。</span><span class="sxs-lookup"><span data-stu-id="b66b6-119">The Test-CsComputer cmdlet can only be run on the local computer, you can't call Test-CsComputer from a remote instance of Windows PowerShell.</span></span> <span data-ttu-id="b66b6-120">根據預設，Test-CsComputer 會在螢幕上顯示非常少的輸出，而不是將 Cmdlet 所傳回的資訊寫入 HTML 檔案。</span><span class="sxs-lookup"><span data-stu-id="b66b6-120">By default, Test-CsComputer displays very little output on-screen, instead information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="b66b6-121">因此，建議您在每次執行 Test-CsComputer 時，加入 Verbose 參數和 Report 參數。</span><span class="sxs-lookup"><span data-stu-id="b66b6-121">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsComputer.</span></span> <span data-ttu-id="b66b6-122">在執行 Cmdlet 時，Verbose 參數會在螢幕上稍有增加的輸出。</span><span class="sxs-lookup"><span data-stu-id="b66b6-122">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="b66b6-123">Report 參數可讓您指定 Test-CsComputer 所產生之 HTML 檔案的檔案路徑和檔案名。</span><span class="sxs-lookup"><span data-stu-id="b66b6-123">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsComputer.</span></span> <span data-ttu-id="b66b6-124">如果不包含報表參數，HTML 檔案將會自動儲存至您的使用者資料夾，並指定如下名稱： ce84964a-c4da-4622-ad34-c54ff3ed361f.html。</span><span class="sxs-lookup"><span data-stu-id="b66b6-124">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="b66b6-125">下列範例命令會執行 Test-CsComputer，並將輸出儲存至名為 C： Logs 的 \\ 檔案 \\ComputerTest.html：</span><span class="sxs-lookup"><span data-stu-id="b66b6-125">The following sample command runs Test-CsComputer and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="b66b6-126">如需詳細資訊，請參閱 [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="b66b6-126">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b66b6-127">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="b66b6-127">Determining success or failure</span></span>

<span data-ttu-id="b66b6-128">因為執行的驗證檢查數目，所以 Test-CsComputer 不會傳回簡單的 **是，測試成功** 或 **否，測試失敗**。</span><span class="sxs-lookup"><span data-stu-id="b66b6-128">Because of the number of verification checks that it performs, Test-CsComputer does not report back a simple **Yes, the test succeeded** or **No, the test failed**.</span></span> <span data-ttu-id="b66b6-129">相反地，您必須使用 Internet Explorer 來查看所產生的 HTML 檔案，以判斷每項測試的成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="b66b6-129">Instead, you have to view the generated HTML file by using Internet Explorer to determine the success or failure of each test.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b66b6-130">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="b66b6-130">Reasons why the test might have failed</span></span>

<span data-ttu-id="b66b6-131">以下是一些 Test-CsComputer 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="b66b6-131">Here are some common reasons why Test-CsComputer might fail:</span></span>

  - <span data-ttu-id="b66b6-132">測試電腦可能未啟用，無法搭配 Lync Server 使用。</span><span class="sxs-lookup"><span data-stu-id="b66b6-132">The test computer might not be enabled for use with Lync Server.</span></span> <span data-ttu-id="b66b6-133">如果電腦上的 Lync Server 服務或伺服器角色已變更，且未執行 Enable-CsComputer Cmdlet，便會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="b66b6-133">This can occur if the Lync Server services or server roles on the computer have changed and the Enable-CsComputer cmdlet was not run.</span></span> <span data-ttu-id="b66b6-134">若要解決此問題，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b66b6-134">To resolve this issue, run the following command:</span></span>
    
        Enable-CsComputer

  - <span data-ttu-id="b66b6-135">測試電腦上的複寫可能不是最新的。</span><span class="sxs-lookup"><span data-stu-id="b66b6-135">Replication might not be up to date on the test computer.</span></span> <span data-ttu-id="b66b6-136">您可以執行 Get-CsManagementStoreReplicationStatus Cmdlet，檢查電腦目前的複寫狀態。</span><span class="sxs-lookup"><span data-stu-id="b66b6-136">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="b66b6-137">若複寫狀態不是最新的，您可以使用類似下列的命令，手動強制進行複寫：</span><span class="sxs-lookup"><span data-stu-id="b66b6-137">If the replication status is not up to date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="b66b6-138">可能必須啟用拓撲。</span><span class="sxs-lookup"><span data-stu-id="b66b6-138">The topology might have to be enabled.</span></span> <span data-ttu-id="b66b6-139">如果您變更 Lync Server 拓撲 (可能會影響本機電腦的變更) ，則必須啟用新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="b66b6-139">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="b66b6-140">您可以隨時執行下列命令來啟用拓撲：</span><span class="sxs-lookup"><span data-stu-id="b66b6-140">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：測試 Lync Server 服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b193473ad5941c647c572fae1b7cb5e7ece7f95d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a><span data-ttu-id="11909-102">在 Lync Server 2013 中測試 Lync Server services</span><span class="sxs-lookup"><span data-stu-id="11909-102">Testing Lync Server services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11909-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="11909-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11909-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="11909-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="11909-105">日常</span><span class="sxs-lookup"><span data-stu-id="11909-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11909-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="11909-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="11909-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="11909-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11909-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="11909-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="11909-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="11909-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="11909-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsComputer Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="11909-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsComputer cmdlet.</span></span> <span data-ttu-id="11909-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="11909-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="11909-112">描述</span><span class="sxs-lookup"><span data-stu-id="11909-112">Description</span></span>

<span data-ttu-id="11909-113">測試 CsComputer 會驗證本機電腦上執行的所有 Lync Server 2013 服務狀態。</span><span class="sxs-lookup"><span data-stu-id="11909-113">Test-CsComputer verifies the status of all the Lync Server 2013 services that are running on the local computer.</span></span> <span data-ttu-id="11909-114">（測試 CsComputer 只能在本機執行，無法從 Windows PowerShell 的遠端實例執行。）這個 Cmdlet 也會檢查是否在電腦上開啟適當的防火牆埠，並判斷您安裝 Lync Server 2013 時所建立的 Active Directory 群組是否已新增到對應的本機群組中。</span><span class="sxs-lookup"><span data-stu-id="11909-114">(Test-CsComputer can only be run locally, it cannot be run from a remote instance of Windows PowerShell.) The cmdlet also checks whether the appropriate firewall ports are opened on the computer, and determines whether the Active Directory groups that were created when you installed Lync Server 2013 were added to the corresponding local groups.</span></span> <span data-ttu-id="11909-115">例如，測試 CsComputer 會確認已將 Active Directory 群組 RTCUniversalUserAdmins 新增到 [管理員] 群組。</span><span class="sxs-lookup"><span data-stu-id="11909-115">For example, Test-CsComputer will verify that the Active Directory group RTCUniversalUserAdmins was added to the Administrators group.</span></span>

<span data-ttu-id="11909-116">如需詳細資訊，請參閱[Test CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="11909-116">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="11909-117">執行測試</span><span class="sxs-lookup"><span data-stu-id="11909-117">Running the test</span></span>

<span data-ttu-id="11909-118">Test CsComputer Cmdlet 只能在本機電腦上執行，您無法從 Windows PowerShell 的遠端實例呼叫 Test CsComputer。</span><span class="sxs-lookup"><span data-stu-id="11909-118">The Test-CsComputer cmdlet can only be run on the local computer, you can't call Test-CsComputer from a remote instance of Windows PowerShell.</span></span> <span data-ttu-id="11909-119">根據預設，測試 CsComputer 會在畫面上顯示極小的輸出，而不是由 Cmdlet 傳回的資訊寫入 HTML 檔案。</span><span class="sxs-lookup"><span data-stu-id="11909-119">By default, Test-CsComputer displays very little output on-screen, instead information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="11909-120">因此，建議您在每次執行 Test CsComputer 時包含詳細參數和 Report 參數。</span><span class="sxs-lookup"><span data-stu-id="11909-120">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsComputer.</span></span> <span data-ttu-id="11909-121">此詳細參數會在執行 Cmdlet 時，在螢幕上提供稍有更詳細的輸出。</span><span class="sxs-lookup"><span data-stu-id="11909-121">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="11909-122">Report 參數可讓您指定由 Test CsComputer 所產生之 HTML 檔案的檔案路徑和檔案名。</span><span class="sxs-lookup"><span data-stu-id="11909-122">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsComputer.</span></span> <span data-ttu-id="11909-123">如果您不包含報表參數，HTML 檔案將會自動儲存到 [使用者] 資料夾，並指定如下的名稱： ce84964a-c4da-4622-ad34-c54ff3ed361f .html。</span><span class="sxs-lookup"><span data-stu-id="11909-123">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="11909-124">下列範例命令會執行 Test-CsComputer，並將輸出儲存到名為 C：\\Logs\\ComputerTest 的檔案中：</span><span class="sxs-lookup"><span data-stu-id="11909-124">The following sample command runs Test-CsComputer and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="11909-125">如需詳細資訊，請參閱[Test CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="11909-125">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="11909-126">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="11909-126">Determining success or failure</span></span>

<span data-ttu-id="11909-127">由於執行的驗證檢查數量，測試 CsComputer 不會傳回簡單的 **[是]、[測試成功]** 或 [否] **，測試失敗**。</span><span class="sxs-lookup"><span data-stu-id="11909-127">Because of the number of verification checks that it performs, Test-CsComputer does not report back a simple **Yes, the test succeeded** or **No, the test failed**.</span></span> <span data-ttu-id="11909-128">相反地，您必須使用 Internet Explorer 來查看所產生的 HTML 檔案，才能判斷每個測試的成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="11909-128">Instead, you have to view the generated HTML file by using Internet Explorer to determine the success or failure of each test.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="11909-129">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="11909-129">Reasons why the test might have failed</span></span>

<span data-ttu-id="11909-130">以下是測試 CsComputer 可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="11909-130">Here are some common reasons why Test-CsComputer might fail:</span></span>

  - <span data-ttu-id="11909-131">測試電腦可能未啟用，無法搭配 Lync Server 使用。</span><span class="sxs-lookup"><span data-stu-id="11909-131">The test computer might not be enabled for use with Lync Server.</span></span> <span data-ttu-id="11909-132">如果電腦上的 Lync Server 服務或伺服器角色已變更，且 CsComputer Cmdlet 未執行，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="11909-132">This can occur if the Lync Server services or server roles on the computer have changed and the Enable-CsComputer cmdlet was not run.</span></span> <span data-ttu-id="11909-133">若要解決此問題，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="11909-133">To resolve this issue, run the following command:</span></span>
    
        Enable-CsComputer

  - <span data-ttu-id="11909-134">測試電腦上的複製可能不是最新的。</span><span class="sxs-lookup"><span data-stu-id="11909-134">Replication might not be up to date on the test computer.</span></span> <span data-ttu-id="11909-135">您可以執行 CsManagementStoreReplicationStatus Cmdlet 來檢查電腦的目前複製狀態：</span><span class="sxs-lookup"><span data-stu-id="11909-135">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="11909-136">如果複製狀態不是最新的，您可以使用類似以下的命令，手動強制進行複製：</span><span class="sxs-lookup"><span data-stu-id="11909-136">If the replication status is not up to date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="11909-137">可能必須啟用拓撲。</span><span class="sxs-lookup"><span data-stu-id="11909-137">The topology might have to be enabled.</span></span> <span data-ttu-id="11909-138">如果您變更 Lync Server 拓撲（可能會影響本機電腦的變更），則您必須啟用新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="11909-138">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="11909-139">您可以在任何時候執行此命令來啟用拓撲：</span><span class="sxs-lookup"><span data-stu-id="11909-139">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>


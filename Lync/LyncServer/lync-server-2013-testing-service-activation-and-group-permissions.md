---
title: Lync Server 2013：測試服務啟用和群組許可權
description: Lync Server 2013：測試服務啟用和群組許可權。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 116cf939f3110616ce395eb14c7945890bdb89b7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556259"
---
# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a><span data-ttu-id="ee94c-103">在 Lync Server 2013 中測試服務啟用和群組許可權</span><span class="sxs-lookup"><span data-stu-id="ee94c-103">Testing service activation and group permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee94c-104">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="ee94c-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee94c-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="ee94c-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ee94c-106">每日</span><span class="sxs-lookup"><span data-stu-id="ee94c-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee94c-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="ee94c-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ee94c-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee94c-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee94c-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="ee94c-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ee94c-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="ee94c-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ee94c-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsTopology Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="ee94c-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTopology cmdlet.</span></span> <span data-ttu-id="ee94c-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ee94c-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ee94c-113">描述</span><span class="sxs-lookup"><span data-stu-id="ee94c-113">Description</span></span>

<span data-ttu-id="ee94c-114">Test-CsTopology Cmdlet 可讓您驗證 Lync Server 2013 在全域範圍內是否運作正常。</span><span class="sxs-lookup"><span data-stu-id="ee94c-114">The Test-CsTopology cmdlet enables you to verify that Lync Server 2013 is functioning correctly at a global scope.</span></span> <span data-ttu-id="ee94c-115">根據預設，指令程式會檢查整個 Lync 伺服器基礎結構，確認所需的服務正在執行，且已針對這些服務及在安裝 Lync Server 時所建立的通用安全性群組設定適當的許可權。</span><span class="sxs-lookup"><span data-stu-id="ee94c-115">By default, the cmdlet checks your whole Lync Server infrastructure, verifying that the required services are running and that the appropriate permissions are set for these services and for the universal security groups that are created when you install Lync Server.</span></span>

<span data-ttu-id="ee94c-116">除了驗證 Lync Server 安裝的有效性之外，Test-CsTopology 也可讓您檢查特定服務的有效性。</span><span class="sxs-lookup"><span data-stu-id="ee94c-116">In addition to verifying the validity of the Lync Server installation, Test-CsTopology also lets you check the validity of a specific service.</span></span> <span data-ttu-id="ee94c-117">例如，下列命令會檢查集區 atl-cs-001.litwareinc.com 上 A/V 會議伺服器的狀態：</span><span class="sxs-lookup"><span data-stu-id="ee94c-117">For example, this command checks the state of the A/V Conferencing Server on the pool atl-cs-001.litwareinc.com:</span></span>

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ee94c-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="ee94c-118">Running the test</span></span>

<span data-ttu-id="ee94c-119">根據預設，Test-CsTopology 會在螢幕上顯示非常少的輸出。</span><span class="sxs-lookup"><span data-stu-id="ee94c-119">By default, Test-CsTopology displays very little output on-screen.</span></span> <span data-ttu-id="ee94c-120">相反地，指令程式傳回的資訊會寫入至 HTML 檔案。</span><span class="sxs-lookup"><span data-stu-id="ee94c-120">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="ee94c-121">Report 參數可讓您指定 Test-CsTopology 所產生之 HTML 檔案的檔案路徑和檔案名。</span><span class="sxs-lookup"><span data-stu-id="ee94c-121">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsTopology.</span></span> <span data-ttu-id="ee94c-122">如果不包含報表參數，HTML 檔案將會自動儲存至您的使用者資料夾，並指定如下名稱： ce84964a-c4da-4622-ad34-c54ff3ed361f.html。</span><span class="sxs-lookup"><span data-stu-id="ee94c-122">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="ee94c-123">下列範例命令會執行 Test-CsTopology，並將輸出儲存至名為 C： Logs 的 \\ 檔案 \\ComputerTest.html：</span><span class="sxs-lookup"><span data-stu-id="ee94c-123">The following sample command runs Test-CsTopology and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="ee94c-124">如需詳細資訊，請參閱 [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="ee94c-124">For more information, see the Help documentation for the [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ee94c-125">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="ee94c-125">Determining success or failure</span></span>

<span data-ttu-id="ee94c-126">與大多數的測試 Cmdlet 不同的是，Test-CsTopology 會傳回成功或失敗報告。</span><span class="sxs-lookup"><span data-stu-id="ee94c-126">Unlike most of the test cmdlets, Test-CsTopology does report back Success or Failure.</span></span> <span data-ttu-id="ee94c-127">部分，這是因為在每次執行 Cmdlet 時，都必須執行大量驗證檢查。</span><span class="sxs-lookup"><span data-stu-id="ee94c-127">In part, that’s due to the large number of verification checks that the cmdlet must make every time that it runs.</span></span> <span data-ttu-id="ee94c-128">相反地，會將資料儲存到 HTML 報表，然後再使用 Internet Explorer 來查看。</span><span class="sxs-lookup"><span data-stu-id="ee94c-128">Instead, data is saved to an HTML report that can then be viewed by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ee94c-129">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="ee94c-129">Reasons why the test might have failed</span></span>

<span data-ttu-id="ee94c-130">以下是一些 Test-CsTopology 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="ee94c-130">Here are some common reasons why Test-CsTopology might fail:</span></span>

  - <span data-ttu-id="ee94c-131">測試電腦上的複寫可能不是最新的。</span><span class="sxs-lookup"><span data-stu-id="ee94c-131">Replication might not be up-to-date on the test computer.</span></span> <span data-ttu-id="ee94c-132">您可以執行 Get-CsManagementStoreReplicationStatus Cmdlet，檢查電腦目前的複寫狀態。</span><span class="sxs-lookup"><span data-stu-id="ee94c-132">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="ee94c-133">若複寫狀態不是最新狀態，您可以使用類似下列的命令，手動強制進行複寫：</span><span class="sxs-lookup"><span data-stu-id="ee94c-133">If the replication status is not up-to-date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="ee94c-134">可能必須啟用拓撲。</span><span class="sxs-lookup"><span data-stu-id="ee94c-134">The topology might have to be enabled.</span></span> <span data-ttu-id="ee94c-135">如果您變更 Lync Server 拓撲 (可能會影響本機電腦的變更) ，則必須啟用新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="ee94c-135">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="ee94c-136">您可以隨時執行下列命令來啟用拓撲：</span><span class="sxs-lookup"><span data-stu-id="ee94c-136">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>


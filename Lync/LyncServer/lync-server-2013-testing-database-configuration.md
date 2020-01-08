---
title: Lync Server 2013：測試資料庫配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 805b62e234f7a5469d3af3677ba81478fb3abc8f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="3c3a1-102">在 Lync Server 2013 中測試資料庫配置</span><span class="sxs-lookup"><span data-stu-id="3c3a1-102">Testing database configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c3a1-103">_**主題上次修改日期：** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="3c3a1-103">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c3a1-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="3c3a1-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3c3a1-105">日常</span><span class="sxs-lookup"><span data-stu-id="3c3a1-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c3a1-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="3c3a1-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3c3a1-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c3a1-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c3a1-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="3c3a1-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3c3a1-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員，且需要在 SQL Server 上擁有系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="3c3a1-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="3c3a1-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsDatabase</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="3c3a1-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="3c3a1-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="3c3a1-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3c3a1-112">描述</span><span class="sxs-lookup"><span data-stu-id="3c3a1-112">Description</span></span>

<span data-ttu-id="3c3a1-113">**CsDatabase** Cmdlet 會驗證一或多個 Lync Server 2013 資料庫的連線能力。</span><span class="sxs-lookup"><span data-stu-id="3c3a1-113">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="3c3a1-114">在執行時， **Test CsDatabase** Cmdlet 會讀取 Lync Server 拓撲，嘗試連線至相關資料庫，然後傳回每次嘗試的成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="3c3a1-114">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="3c3a1-115">如果可以建立連線，則 Cmdlet 也會傳回此類資訊，例如資料庫名稱、SQL Server 版本資訊，以及任何已安裝鏡像資料庫的位置。</span><span class="sxs-lookup"><span data-stu-id="3c3a1-115">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3c3a1-116">執行測試</span><span class="sxs-lookup"><span data-stu-id="3c3a1-116">Running the test</span></span>

<span data-ttu-id="3c3a1-117">範例1中所示的命令會驗證中央管理資料庫的配置。</span><span class="sxs-lookup"><span data-stu-id="3c3a1-117">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="3c3a1-118">範例2驗證所有安裝在電腦 atl-sql-001.litwareinc.com 上的 Lync Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="3c3a1-118">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="3c3a1-119">在範例3中，僅針對電腦 atl-sql-001.litwareinc.com 上安裝的封存資料庫執行驗證。</span><span class="sxs-lookup"><span data-stu-id="3c3a1-119">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="3c3a1-120">請注意，SqlInstanceName 參數包含于指定封存資料庫所在的 SQL Server 實例（Archinst）。</span><span class="sxs-lookup"><span data-stu-id="3c3a1-120">Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="3c3a1-121">範例4所示的命令會驗證本機電腦上已安裝的資料庫。</span><span class="sxs-lookup"><span data-stu-id="3c3a1-121">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3c3a1-122">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="3c3a1-122">Determining success or failure</span></span>

<span data-ttu-id="3c3a1-123">如果資料庫連線設定正確，您會收到類似以下的輸出，並將 [成功] 屬性標示為**True**：</span><span class="sxs-lookup"><span data-stu-id="3c3a1-123">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="3c3a1-124">SqlServerFqdn： atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3c3a1-124">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="3c3a1-125">SqlInstanceName： rtc</span><span class="sxs-lookup"><span data-stu-id="3c3a1-125">SqlInstanceName : rtc</span></span>

<span data-ttu-id="3c3a1-126">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="3c3a1-126">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="3c3a1-127">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="3c3a1-127">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="3c3a1-128">DatabaseName： xds</span><span class="sxs-lookup"><span data-stu-id="3c3a1-128">DatabaseName : xds</span></span>

<span data-ttu-id="3c3a1-129">資料來源</span><span class="sxs-lookup"><span data-stu-id="3c3a1-129">DataSource :</span></span>

<span data-ttu-id="3c3a1-130">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="3c3a1-130">SQLServerVersion :</span></span>

<span data-ttu-id="3c3a1-131">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="3c3a1-131">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="3c3a1-132">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="3c3a1-132">InstalledVersion :</span></span>

<span data-ttu-id="3c3a1-133">成功： True</span><span class="sxs-lookup"><span data-stu-id="3c3a1-133">Succeed : True</span></span>

<span data-ttu-id="3c3a1-134">SqlServerFqdn： atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3c3a1-134">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="3c3a1-135">SqlInstanceName： rtc</span><span class="sxs-lookup"><span data-stu-id="3c3a1-135">SqlInstanceName : rtc</span></span>

<span data-ttu-id="3c3a1-136">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="3c3a1-136">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="3c3a1-137">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="3c3a1-137">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="3c3a1-138">DatabaseName： .lis</span><span class="sxs-lookup"><span data-stu-id="3c3a1-138">DatabaseName : lis</span></span>

<span data-ttu-id="3c3a1-139">資料來源</span><span class="sxs-lookup"><span data-stu-id="3c3a1-139">DataSource :</span></span>

<span data-ttu-id="3c3a1-140">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="3c3a1-140">SQLServerVersion :</span></span>

<span data-ttu-id="3c3a1-141">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="3c3a1-141">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="3c3a1-142">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="3c3a1-142">InstalledVersion :</span></span>

<span data-ttu-id="3c3a1-143">成功： True</span><span class="sxs-lookup"><span data-stu-id="3c3a1-143">Succeed : True</span></span>

<span data-ttu-id="3c3a1-144">如果資料庫已正確設定但仍可使用，則 [成功] 欄位會顯示為**False**，並提供額外的警告和資訊：</span><span class="sxs-lookup"><span data-stu-id="3c3a1-144">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="3c3a1-145">SqlServerFqdn： atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3c3a1-145">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="3c3a1-146">SqlInstanceName： rtc</span><span class="sxs-lookup"><span data-stu-id="3c3a1-146">SqlInstanceName : rtc</span></span>

<span data-ttu-id="3c3a1-147">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="3c3a1-147">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="3c3a1-148">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="3c3a1-148">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="3c3a1-149">DatabaseName： xds</span><span class="sxs-lookup"><span data-stu-id="3c3a1-149">DatabaseName : xds</span></span>

<span data-ttu-id="3c3a1-150">資料來源</span><span class="sxs-lookup"><span data-stu-id="3c3a1-150">DataSource :</span></span>

<span data-ttu-id="3c3a1-151">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="3c3a1-151">SQLServerVersion :</span></span>

<span data-ttu-id="3c3a1-152">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="3c3a1-152">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="3c3a1-153">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="3c3a1-153">InstalledVersion :</span></span>

<span data-ttu-id="3c3a1-154">成功： False</span><span class="sxs-lookup"><span data-stu-id="3c3a1-154">Succeed : False</span></span>

<span data-ttu-id="3c3a1-155">SqlServerFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3c3a1-155">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="3c3a1-156">SqlInstanceName： rtc</span><span class="sxs-lookup"><span data-stu-id="3c3a1-156">SqlInstanceName : rtc</span></span>

<span data-ttu-id="3c3a1-157">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="3c3a1-157">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="3c3a1-158">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="3c3a1-158">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="3c3a1-159">DatabaseName： .lis</span><span class="sxs-lookup"><span data-stu-id="3c3a1-159">DatabaseName : lis</span></span>

<span data-ttu-id="3c3a1-160">資料來源</span><span class="sxs-lookup"><span data-stu-id="3c3a1-160">DataSource :</span></span>

<span data-ttu-id="3c3a1-161">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="3c3a1-161">SQLServerVersion :</span></span>

<span data-ttu-id="3c3a1-162">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="3c3a1-162">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="3c3a1-163">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="3c3a1-163">InstalledVersion :</span></span>

<span data-ttu-id="3c3a1-164">成功： False</span><span class="sxs-lookup"><span data-stu-id="3c3a1-164">Succeed : False</span></span>

<span data-ttu-id="3c3a1-165">警告：測試 CsDatabase 遇到錯誤。</span><span class="sxs-lookup"><span data-stu-id="3c3a1-165">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="3c3a1-166">請參閱記錄檔</span><span class="sxs-lookup"><span data-stu-id="3c3a1-166">Consult the log file for a</span></span>

<span data-ttu-id="3c3a1-167">詳細分析，並確保所有錯誤（2）和警告（0）都得到解決</span><span class="sxs-lookup"><span data-stu-id="3c3a1-167">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="3c3a1-168">然後再繼續進行。</span><span class="sxs-lookup"><span data-stu-id="3c3a1-168">before continuing.</span></span>

<span data-ttu-id="3c3a1-169">警告：您可以在以下網址找到詳細的結果</span><span class="sxs-lookup"><span data-stu-id="3c3a1-169">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="3c3a1-170">"C：\\使用者\\測試\\AppData\\本機\\Temp\\2\\測試-CsDatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="3c3a1-170">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="3c3a1-171">04d593cce8e6 "。</span><span class="sxs-lookup"><span data-stu-id="3c3a1-171">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3c3a1-172">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="3c3a1-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="3c3a1-173">以下是**測試 CsDatabase**可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="3c3a1-173">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="3c3a1-174">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="3c3a1-174">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="3c3a1-175">如果使用，必須正確設定選用的參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="3c3a1-175">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="3c3a1-176">重新執行不含選用參數的命令，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="3c3a1-176">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="3c3a1-177">如果資料庫的配置錯誤或尚未部署，此命令就會失敗。</span><span class="sxs-lookup"><span data-stu-id="3c3a1-177">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3c3a1-178">請參閱</span><span class="sxs-lookup"><span data-stu-id="3c3a1-178">See Also</span></span>


[<span data-ttu-id="3c3a1-179">Get-CsDatabaseMirrorState</span><span class="sxs-lookup"><span data-stu-id="3c3a1-179">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="3c3a1-180">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="3c3a1-180">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="3c3a1-181">CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="3c3a1-181">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


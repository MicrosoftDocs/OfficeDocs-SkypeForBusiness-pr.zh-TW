---
title: Lync Server 2013：測試資料庫設定
description: Lync Server 2013：測試資料庫設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b9f88eee99c4a2d523cc84df401dcc1d7b9fe59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560679"
---
# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="a3650-103">在 Lync Server 2013 中測試資料庫設定</span><span class="sxs-lookup"><span data-stu-id="a3650-103">Testing database configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3650-104">_**主題上次修改日期：** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="a3650-104">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3650-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="a3650-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a3650-106">每日</span><span class="sxs-lookup"><span data-stu-id="a3650-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3650-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="a3650-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a3650-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3650-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3650-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="a3650-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a3650-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員，而且必須具備 SQL Server 的系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="a3650-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="a3650-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsDatabase</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="a3650-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="a3650-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a3650-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a3650-113">描述</span><span class="sxs-lookup"><span data-stu-id="a3650-113">Description</span></span>

<span data-ttu-id="a3650-114">**Test-CsDatabase** Cmdlet 會驗證一或多部 Lync Server 2013 資料庫的連線能力。</span><span class="sxs-lookup"><span data-stu-id="a3650-114">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="a3650-115">執行時， **Test-CsDatabase** 指令指令會讀取 Lync Server 拓撲，嘗試連線至相關資料庫，然後傳回每次嘗試的成功或失敗報告。</span><span class="sxs-lookup"><span data-stu-id="a3650-115">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="a3650-116">若連線成功，此 Cmdlet 亦會回報資料庫名稱、SQL Server 版本資訊與所安裝之鏡像資料庫的位置等資訊。</span><span class="sxs-lookup"><span data-stu-id="a3650-116">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a3650-117">執行測試</span><span class="sxs-lookup"><span data-stu-id="a3650-117">Running the test</span></span>

<span data-ttu-id="a3650-118">範例 1 所示的命令會驗證中央管理資料庫的組態。</span><span class="sxs-lookup"><span data-stu-id="a3650-118">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="a3650-119">範例2會驗證所有安裝在電腦 atl-sql-001.litwareinc.com 上的 Lync 伺服器資料庫。</span><span class="sxs-lookup"><span data-stu-id="a3650-119">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="a3650-p103">在範例 3 中，只會驗證安裝在 atl-sql-001.litwareinc.com 電腦上的封存資料庫。請注意，會包含 SqlInstanceName 參數來指定封存資料庫所在的 SQL Server 執行個體 (Archinst)。</span><span class="sxs-lookup"><span data-stu-id="a3650-p103">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com. Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="a3650-122">範例 4 所示的命令會驗證本機電腦上所安裝的資料庫。</span><span class="sxs-lookup"><span data-stu-id="a3650-122">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a3650-123">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="a3650-123">Determining success or failure</span></span>

<span data-ttu-id="a3650-124">如果資料庫連線設定正確，您會收到類似以下的輸出，其成功的屬性會標示為 **True**：</span><span class="sxs-lookup"><span data-stu-id="a3650-124">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="a3650-125">SqlServerFqdn： atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a3650-125">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="a3650-126">SqlInstanceName： rtc</span><span class="sxs-lookup"><span data-stu-id="a3650-126">SqlInstanceName : rtc</span></span>

<span data-ttu-id="a3650-127">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="a3650-127">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="a3650-128">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="a3650-128">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="a3650-129">DatabaseName： xds</span><span class="sxs-lookup"><span data-stu-id="a3650-129">DatabaseName : xds</span></span>

<span data-ttu-id="a3650-130">DataSource：</span><span class="sxs-lookup"><span data-stu-id="a3650-130">DataSource :</span></span>

<span data-ttu-id="a3650-131">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="a3650-131">SQLServerVersion :</span></span>

<span data-ttu-id="a3650-132">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="a3650-132">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="a3650-133">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="a3650-133">InstalledVersion :</span></span>

<span data-ttu-id="a3650-134">成功： True</span><span class="sxs-lookup"><span data-stu-id="a3650-134">Succeed : True</span></span>

<span data-ttu-id="a3650-135">SqlServerFqdn： atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a3650-135">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="a3650-136">SqlInstanceName： rtc</span><span class="sxs-lookup"><span data-stu-id="a3650-136">SqlInstanceName : rtc</span></span>

<span data-ttu-id="a3650-137">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="a3650-137">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="a3650-138">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="a3650-138">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="a3650-139">DatabaseName： .lis</span><span class="sxs-lookup"><span data-stu-id="a3650-139">DatabaseName : lis</span></span>

<span data-ttu-id="a3650-140">DataSource：</span><span class="sxs-lookup"><span data-stu-id="a3650-140">DataSource :</span></span>

<span data-ttu-id="a3650-141">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="a3650-141">SQLServerVersion :</span></span>

<span data-ttu-id="a3650-142">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="a3650-142">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="a3650-143">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="a3650-143">InstalledVersion :</span></span>

<span data-ttu-id="a3650-144">成功： True</span><span class="sxs-lookup"><span data-stu-id="a3650-144">Succeed : True</span></span>

<span data-ttu-id="a3650-145">如果資料庫設定正確但仍然可用，[成功] 欄位就會顯示為 **False**，並且會提供其他警告和資訊：</span><span class="sxs-lookup"><span data-stu-id="a3650-145">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="a3650-146">SqlServerFqdn： atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a3650-146">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="a3650-147">SqlInstanceName： rtc</span><span class="sxs-lookup"><span data-stu-id="a3650-147">SqlInstanceName : rtc</span></span>

<span data-ttu-id="a3650-148">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="a3650-148">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="a3650-149">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="a3650-149">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="a3650-150">DatabaseName： xds</span><span class="sxs-lookup"><span data-stu-id="a3650-150">DatabaseName : xds</span></span>

<span data-ttu-id="a3650-151">DataSource：</span><span class="sxs-lookup"><span data-stu-id="a3650-151">DataSource :</span></span>

<span data-ttu-id="a3650-152">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="a3650-152">SQLServerVersion :</span></span>

<span data-ttu-id="a3650-153">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="a3650-153">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="a3650-154">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="a3650-154">InstalledVersion :</span></span>

<span data-ttu-id="a3650-155">成功： False</span><span class="sxs-lookup"><span data-stu-id="a3650-155">Succeed : False</span></span>

<span data-ttu-id="a3650-156">SqlServerFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a3650-156">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a3650-157">SqlInstanceName： rtc</span><span class="sxs-lookup"><span data-stu-id="a3650-157">SqlInstanceName : rtc</span></span>

<span data-ttu-id="a3650-158">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="a3650-158">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="a3650-159">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="a3650-159">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="a3650-160">DatabaseName： .lis</span><span class="sxs-lookup"><span data-stu-id="a3650-160">DatabaseName : lis</span></span>

<span data-ttu-id="a3650-161">DataSource：</span><span class="sxs-lookup"><span data-stu-id="a3650-161">DataSource :</span></span>

<span data-ttu-id="a3650-162">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="a3650-162">SQLServerVersion :</span></span>

<span data-ttu-id="a3650-163">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="a3650-163">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="a3650-164">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="a3650-164">InstalledVersion :</span></span>

<span data-ttu-id="a3650-165">成功： False</span><span class="sxs-lookup"><span data-stu-id="a3650-165">Succeed : False</span></span>

<span data-ttu-id="a3650-166">警告： Test-CsDatabase 發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="a3650-166">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="a3650-167">請參閱記錄檔中的</span><span class="sxs-lookup"><span data-stu-id="a3650-167">Consult the log file for a</span></span>

<span data-ttu-id="a3650-168">詳細分析，並確定所有的錯誤 (2) 和警告 (均已定址) </span><span class="sxs-lookup"><span data-stu-id="a3650-168">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="a3650-169">繼續之前。</span><span class="sxs-lookup"><span data-stu-id="a3650-169">before continuing.</span></span>

<span data-ttu-id="a3650-170">警告：您可以在以下位置找到詳細的結果：</span><span class="sxs-lookup"><span data-stu-id="a3650-170">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="a3650-171">"C： \\ 使用者 \\ 測試 \\ AppData \\ 本機 \\ Temp \\ 2 \\ Test-CsDatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="a3650-171">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="a3650-172">04d593cce8e6.html "。</span><span class="sxs-lookup"><span data-stu-id="a3650-172">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a3650-173">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="a3650-173">Reasons why the test might have failed</span></span>

<span data-ttu-id="a3650-174">以下是一些 **Test-CsDatabase** 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="a3650-174">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="a3650-175">提供的參數值不正確。</span><span class="sxs-lookup"><span data-stu-id="a3650-175">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="a3650-176">如果使用，必須正確設定選用參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="a3650-176">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="a3650-177">請重新執行不含選用參數的命令，然後查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="a3650-177">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="a3650-178">如果資料庫設定不當或尚未部署，此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="a3650-178">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a3650-179">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a3650-179">See Also</span></span>


[<span data-ttu-id="a3650-180">Get-CsDatabaseMirrorState</span><span class="sxs-lookup"><span data-stu-id="a3650-180">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="a3650-181">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="a3650-181">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="a3650-182">Get-CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="a3650-182">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013： 測試資料庫組態
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
ms.openlocfilehash: 45781238f7fb8aa461e050f2e8f0cbf04e45a950
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="5e161-102">Lync Server 2013 中的測試資料庫組態</span><span class="sxs-lookup"><span data-stu-id="5e161-102">Testing database configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e161-103">_**主題上次修改日期：** 2016年-07-07_</span><span class="sxs-lookup"><span data-stu-id="5e161-103">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e161-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="5e161-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5e161-105">每日</span><span class="sxs-lookup"><span data-stu-id="5e161-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e161-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="5e161-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5e161-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e161-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e161-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="5e161-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5e161-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須屬於 RTCUniversalServerAdmins 安全性] 群組中，並需要 SQL server 上有系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="5e161-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="5e161-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-csdatabase</strong> cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="5e161-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="5e161-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="5e161-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5e161-112">描述</span><span class="sxs-lookup"><span data-stu-id="5e161-112">Description</span></span>

<span data-ttu-id="5e161-113">**Test-csdatabase** cmdlet 驗證連線至一或多個 Lync Server 2013 資料庫。</span><span class="sxs-lookup"><span data-stu-id="5e161-113">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="5e161-114">當執行時， **Test-csdatabase** cmdlet 會讀取 Lync Server 拓撲、 嘗試連線至相關的資料庫，並再回復報告成功或失敗的每個嘗試。</span><span class="sxs-lookup"><span data-stu-id="5e161-114">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="5e161-115">若連線成功，此 Cmdlet 亦會回報資料庫名稱、SQL Server 版本資訊與所安裝之鏡像資料庫的位置等資訊。</span><span class="sxs-lookup"><span data-stu-id="5e161-115">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5e161-116">執行測試</span><span class="sxs-lookup"><span data-stu-id="5e161-116">Running the test</span></span>

<span data-ttu-id="5e161-117">範例 1 所示的命令會驗證中央管理資料庫的組態。</span><span class="sxs-lookup"><span data-stu-id="5e161-117">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="5e161-118">範例 2 會驗證安裝在電腦 atl-cs-001.litwareinc.com sql-001.litwareinc.com 上的所有 Lync Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="5e161-118">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="5e161-p103">在範例 3 中，只會驗證安裝在 atl-sql-001.litwareinc.com 電腦上的封存資料庫。請注意，會包含 SqlInstanceName 參數來指定封存資料庫所在的 SQL Server 執行個體 (Archinst)。</span><span class="sxs-lookup"><span data-stu-id="5e161-p103">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com. Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="5e161-121">範例 4 所示的命令會驗證本機電腦上所安裝的資料庫。</span><span class="sxs-lookup"><span data-stu-id="5e161-121">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5e161-122">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="5e161-122">Determining success or failure</span></span>

<span data-ttu-id="5e161-123">如果已正確設定資料庫連線，您會收到類似，具有標示為 **，則為 True**的成功屬性的輸出：</span><span class="sxs-lookup"><span data-stu-id="5e161-123">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="5e161-124">SqlServerFqdn: atl-cs-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5e161-124">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="5e161-125">SqlInstanceName: rtc</span><span class="sxs-lookup"><span data-stu-id="5e161-125">SqlInstanceName : rtc</span></span>

<span data-ttu-id="5e161-126">MirrorSqlServerFqdn:</span><span class="sxs-lookup"><span data-stu-id="5e161-126">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="5e161-127">MirrorSqlInstanceName:</span><span class="sxs-lookup"><span data-stu-id="5e161-127">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="5e161-128">DatabaseName: xds</span><span class="sxs-lookup"><span data-stu-id="5e161-128">DatabaseName : xds</span></span>

<span data-ttu-id="5e161-129">資料來源：</span><span class="sxs-lookup"><span data-stu-id="5e161-129">DataSource :</span></span>

<span data-ttu-id="5e161-130">SQLServerVersion:</span><span class="sxs-lookup"><span data-stu-id="5e161-130">SQLServerVersion :</span></span>

<span data-ttu-id="5e161-131">ExpectedVersion: 10.13.2</span><span class="sxs-lookup"><span data-stu-id="5e161-131">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="5e161-132">InstalledVersion:</span><span class="sxs-lookup"><span data-stu-id="5e161-132">InstalledVersion :</span></span>

<span data-ttu-id="5e161-133">成功： True</span><span class="sxs-lookup"><span data-stu-id="5e161-133">Succeed : True</span></span>

<span data-ttu-id="5e161-134">SqlServerFqdn: atl-cs-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5e161-134">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="5e161-135">SqlInstanceName: rtc</span><span class="sxs-lookup"><span data-stu-id="5e161-135">SqlInstanceName : rtc</span></span>

<span data-ttu-id="5e161-136">MirrorSqlServerFqdn:</span><span class="sxs-lookup"><span data-stu-id="5e161-136">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="5e161-137">MirrorSqlInstanceName:</span><span class="sxs-lookup"><span data-stu-id="5e161-137">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="5e161-138">DatabaseName: lis</span><span class="sxs-lookup"><span data-stu-id="5e161-138">DatabaseName : lis</span></span>

<span data-ttu-id="5e161-139">資料來源：</span><span class="sxs-lookup"><span data-stu-id="5e161-139">DataSource :</span></span>

<span data-ttu-id="5e161-140">SQLServerVersion:</span><span class="sxs-lookup"><span data-stu-id="5e161-140">SQLServerVersion :</span></span>

<span data-ttu-id="5e161-141">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="5e161-141">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="5e161-142">InstalledVersion:</span><span class="sxs-lookup"><span data-stu-id="5e161-142">InstalledVersion :</span></span>

<span data-ttu-id="5e161-143">成功： True</span><span class="sxs-lookup"><span data-stu-id="5e161-143">Succeed : True</span></span>

<span data-ttu-id="5e161-144">如果資料庫已正確設定，但仍可使用，[成功] 欄位會顯示為**False**，並會提供額外的警告和資訊：</span><span class="sxs-lookup"><span data-stu-id="5e161-144">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="5e161-145">SqlServerFqdn: atl-cs-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5e161-145">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="5e161-146">SqlInstanceName: rtc</span><span class="sxs-lookup"><span data-stu-id="5e161-146">SqlInstanceName : rtc</span></span>

<span data-ttu-id="5e161-147">MirrorSqlServerFqdn:</span><span class="sxs-lookup"><span data-stu-id="5e161-147">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="5e161-148">MirrorSqlInstanceName:</span><span class="sxs-lookup"><span data-stu-id="5e161-148">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="5e161-149">DatabaseName: xds</span><span class="sxs-lookup"><span data-stu-id="5e161-149">DatabaseName : xds</span></span>

<span data-ttu-id="5e161-150">資料來源：</span><span class="sxs-lookup"><span data-stu-id="5e161-150">DataSource :</span></span>

<span data-ttu-id="5e161-151">SQLServerVersion:</span><span class="sxs-lookup"><span data-stu-id="5e161-151">SQLServerVersion :</span></span>

<span data-ttu-id="5e161-152">ExpectedVersion: 10.13.2</span><span class="sxs-lookup"><span data-stu-id="5e161-152">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="5e161-153">InstalledVersion:</span><span class="sxs-lookup"><span data-stu-id="5e161-153">InstalledVersion :</span></span>

<span data-ttu-id="5e161-154">成功： False</span><span class="sxs-lookup"><span data-stu-id="5e161-154">Succeed : False</span></span>

<span data-ttu-id="5e161-155">SqlServerFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5e161-155">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5e161-156">SqlInstanceName: rtc</span><span class="sxs-lookup"><span data-stu-id="5e161-156">SqlInstanceName : rtc</span></span>

<span data-ttu-id="5e161-157">MirrorSqlServerFqdn:</span><span class="sxs-lookup"><span data-stu-id="5e161-157">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="5e161-158">MirrorSqlInstanceName:</span><span class="sxs-lookup"><span data-stu-id="5e161-158">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="5e161-159">DatabaseName: lis</span><span class="sxs-lookup"><span data-stu-id="5e161-159">DatabaseName : lis</span></span>

<span data-ttu-id="5e161-160">資料來源：</span><span class="sxs-lookup"><span data-stu-id="5e161-160">DataSource :</span></span>

<span data-ttu-id="5e161-161">SQLServerVersion:</span><span class="sxs-lookup"><span data-stu-id="5e161-161">SQLServerVersion :</span></span>

<span data-ttu-id="5e161-162">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="5e161-162">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="5e161-163">InstalledVersion:</span><span class="sxs-lookup"><span data-stu-id="5e161-163">InstalledVersion :</span></span>

<span data-ttu-id="5e161-164">成功： False</span><span class="sxs-lookup"><span data-stu-id="5e161-164">Succeed : False</span></span>

<span data-ttu-id="5e161-165">警告： Test-csdatabase 遇到錯誤。</span><span class="sxs-lookup"><span data-stu-id="5e161-165">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="5e161-166">請洽詢的記錄檔</span><span class="sxs-lookup"><span data-stu-id="5e161-166">Consult the log file for a</span></span>

<span data-ttu-id="5e161-167">詳細的分析，並確定已解決所有錯誤 (2) 及警告 (0)</span><span class="sxs-lookup"><span data-stu-id="5e161-167">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="5e161-168">再繼續。</span><span class="sxs-lookup"><span data-stu-id="5e161-168">before continuing.</span></span>

<span data-ttu-id="5e161-169">警告： 可以在找到詳細的結果</span><span class="sxs-lookup"><span data-stu-id="5e161-169">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="5e161-170">「 C:\\使用者\\測試\\AppData\\本機\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="5e161-170">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="5e161-171">04d593cce8e6.html 」。</span><span class="sxs-lookup"><span data-stu-id="5e161-171">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5e161-172">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="5e161-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="5e161-173">以下是一些常見的原因為何**Test-csdatabase**可能會失敗：</span><span class="sxs-lookup"><span data-stu-id="5e161-173">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="5e161-174">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="5e161-174">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="5e161-175">如果使用，必須正確設定選用的參數或測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="5e161-175">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="5e161-176">重新執行此命令不含選擇性參數，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="5e161-176">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="5e161-177">如果資料庫設定正確，或是尚未部署，此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="5e161-177">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5e161-178">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5e161-178">See Also</span></span>


[<span data-ttu-id="5e161-179">Get-csdatabasemirrorstate</span><span class="sxs-lookup"><span data-stu-id="5e161-179">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="5e161-180">Get-csservice</span><span class="sxs-lookup"><span data-stu-id="5e161-180">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="5e161-181">Get-csuserdatabasestate</span><span class="sxs-lookup"><span data-stu-id="5e161-181">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


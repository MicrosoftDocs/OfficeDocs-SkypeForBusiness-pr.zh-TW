---
title: Lync Server 2013：使用者註冊報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User Registration Report
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48183486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f56ffd05e677d5106552a9ebcf8a0718efbc100
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-registration-report-in-lync-server-2013"></a><span data-ttu-id="31fa2-102">Lync Server 2013 中的使用者註冊報告</span><span class="sxs-lookup"><span data-stu-id="31fa2-102">User Registration Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31fa2-103">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="31fa2-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="31fa2-104">[使用者註冊] 報告提供使用者登入活動的概覽，最重要的是在指定的時間期間（每小時、每天、每週、每月）登入 Microsoft Lync Server 2013 的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="31fa2-104">The User Registration Report provides an overview of user logon activity, most notably information about the number of users who logged on to Microsoft Lync Server 2013 during a specified time period (hourly, daily, weekly, monthly).</span></span> <span data-ttu-id="31fa2-105">請記住，報告只會告訴您有多少人登入。</span><span class="sxs-lookup"><span data-stu-id="31fa2-105">Keep in mind that the report only tells you how many people logged on.</span></span> <span data-ttu-id="31fa2-106">它不會告知您已登入*的*使用者。</span><span class="sxs-lookup"><span data-stu-id="31fa2-106">It does not tell you *which* people logged on.</span></span> <span data-ttu-id="31fa2-107">[監視報告] 不會提供哪些特定使用者使用的是 Lync Server 2013 （以及哪些不是）的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="31fa2-107">Monitoring Reports do not provide information about which specific users are using Lync Server 2013 (and which ones are not).</span></span> <span data-ttu-id="31fa2-108">不過，您可以使用使用者活動報告來取得使用者資訊的粗略估計。</span><span class="sxs-lookup"><span data-stu-id="31fa2-108">However, you can get a rough estimate of user information by using the User Activity Report.</span></span>

<span data-ttu-id="31fa2-109">提供使用者登錄的相關資訊時，[使用者註冊] 報告會繪製兩個重要的差異。</span><span class="sxs-lookup"><span data-stu-id="31fa2-109">When providing information about user logons, the User Registration Report draws two important distinctions.</span></span> <span data-ttu-id="31fa2-110">首先，它會將登錄中斷為兩個主要類別：內部登錄和外部登錄。</span><span class="sxs-lookup"><span data-stu-id="31fa2-110">First, it breaks logons down into two primary categories: internal logons and external logons.</span></span> <span data-ttu-id="31fa2-111">內部登入代表從貴組織的防火牆內部（也就是連線到公司網路時）的使用者。</span><span class="sxs-lookup"><span data-stu-id="31fa2-111">Internal logons represent users who logged on from inside your organization's firewall (that is, while connected to the corporate network).</span></span> <span data-ttu-id="31fa2-112">[外部登入] 代表從防火牆以外的邊緣伺服器登入的使用者（例如，從網路登入的使用者，不會算作外部登入）。</span><span class="sxs-lookup"><span data-stu-id="31fa2-112">External logons represent users who logged on from outside the firewall through an Edge Server (for example, a user who logged on from an Internet café counts as an external logon).</span></span> <span data-ttu-id="31fa2-113">如果您需要知道有多少使用者是從防火牆外登入，使用者註冊報告就能提供此資訊。</span><span class="sxs-lookup"><span data-stu-id="31fa2-113">If you need to know how many of your users are logging on from outside the firewall, the User Registration Report can provide you with this information.</span></span>

<span data-ttu-id="31fa2-114">此外，使用者註冊報告會記錄在指定時段內有多少*活動*使用者。</span><span class="sxs-lookup"><span data-stu-id="31fa2-114">In addition, the User Registration Report notes how many *active* users were present during a given time period.</span></span> <span data-ttu-id="31fa2-115">[作用中的使用者] 是在立即訊息（IM）會話中參與的使用者，在這段時間內參與 Lync 會議、撥打或接聽電話，或其他使用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="31fa2-115">An active user is a user who took part in an instant messaging (IM) session, participated in a Lync Meeting, made or received a phone call, or otherwise used Lync Server during that period of time.</span></span> <span data-ttu-id="31fa2-116">這與已登入，但實際上並未使用系統的使用者不同。</span><span class="sxs-lookup"><span data-stu-id="31fa2-116">This is different from a user who logged on, but never actually used the system.</span></span>

<div>

## <a name="accessing-the-user-registration-report"></a><span data-ttu-id="31fa2-117">存取使用者註冊報告</span><span class="sxs-lookup"><span data-stu-id="31fa2-117">Accessing the User Registration Report</span></span>

<span data-ttu-id="31fa2-118">您只能從 [監控報告] 首頁存取使用者註冊報告。</span><span class="sxs-lookup"><span data-stu-id="31fa2-118">You access the User Registration Report only from the Monitoring Reports home page.</span></span> <span data-ttu-id="31fa2-119">[使用者註冊報告] 不會連結至任何其他報告。</span><span class="sxs-lookup"><span data-stu-id="31fa2-119">The User Registration Report does not link to any other reports.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a><span data-ttu-id="31fa2-120">充分運用使用者註冊報告</span><span class="sxs-lookup"><span data-stu-id="31fa2-120">Making the Best Use of the User Registration Report</span></span>

<span data-ttu-id="31fa2-121">在您部署 Lync Server 之後，我們通常會問到這個問題：如何知道我的使用者是否真的使用這個新技術？</span><span class="sxs-lookup"><span data-stu-id="31fa2-121">After you've deployed Lync Server one commonly-asked question is this: How do I know if my users are actually using this new technology?</span></span> <span data-ttu-id="31fa2-122">雖然在這個方面有一些限制，但使用者註冊報告可以協助您回答這個問題。</span><span class="sxs-lookup"><span data-stu-id="31fa2-122">Although it has a few limitations in this regard, the User Registration Report can help you answer this question.</span></span> <span data-ttu-id="31fa2-123">若要判斷使用者是否正在使用 Lync Server，您必須執行兩項操作。</span><span class="sxs-lookup"><span data-stu-id="31fa2-123">To determine whether or not users are using Lync Server, you need to do two things.</span></span> <span data-ttu-id="31fa2-124">首先，從使用者註冊報告取得唯一的登入使用者統計值。</span><span class="sxs-lookup"><span data-stu-id="31fa2-124">First, get the value of the Unique logon users metric from the User Registration Report.</span></span> <span data-ttu-id="31fa2-125">這個值告訴您登入 Lync Server 的不同人有多少。</span><span class="sxs-lookup"><span data-stu-id="31fa2-125">This value tells you how many distinct individuals logged on to Lync Server.</span></span>

<span data-ttu-id="31fa2-126">根據比較，[總登入] 度量單位會顯示有多少人登入 Lync Server 的總時間。</span><span class="sxs-lookup"><span data-stu-id="31fa2-126">By comparison, the Total logons metric shows how many total times anyone logged on to Lync Server.</span></span> <span data-ttu-id="31fa2-127">例如，假設 Ken Myer 登入 Lync Server 五個不同時間的一天。</span><span class="sxs-lookup"><span data-stu-id="31fa2-127">For example, suppose Ken Myer logged on to Lync Server five different times in a single day.</span></span> <span data-ttu-id="31fa2-128">在這種情況下，Ken Myer 會針對總共登入統計數計算出五個獨立的登入會話，但只有一個使用者登入使用者的度量。</span><span class="sxs-lookup"><span data-stu-id="31fa2-128">In that case, Ken Myer would count as five separate logon sessions for the Total logons metric, but just one logon user for the Unique logon users metric.</span></span> <span data-ttu-id="31fa2-129">同樣地，使用者從多個裝置或多個位置登入，並不常見。</span><span class="sxs-lookup"><span data-stu-id="31fa2-129">Likewise, it's not uncommon for a user to log on from multiple devices or multiple locations.</span></span> <span data-ttu-id="31fa2-130">例如，使用者可以使用她的桌上型電腦（她的膝上型電腦）登入，而她可以有可自動登入 Lync Server 的 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="31fa2-130">For example, a user can log on using her desktop computer, her laptop computer, and she can have an IP phone that automatically logs on to Lync Server.</span></span> <span data-ttu-id="31fa2-131">在這個範例中，有一個具有三次登錄的唯一使用者。</span><span class="sxs-lookup"><span data-stu-id="31fa2-131">In this example, there is one unique user with three logons.</span></span>

<span data-ttu-id="31fa2-132">若要進一步說明總登錄與唯一的登錄之間的差異，請考慮在下表中的特定時段內登錄。</span><span class="sxs-lookup"><span data-stu-id="31fa2-132">To further explain the difference between total logons and unique logons, consider the logons for a given time period in the following table.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31fa2-133">使用者</span><span class="sxs-lookup"><span data-stu-id="31fa2-133">User</span></span></th>
<th><span data-ttu-id="31fa2-134">登入時間</span><span class="sxs-lookup"><span data-stu-id="31fa2-134">Logon time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31fa2-135">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="31fa2-135">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="31fa2-136">7/7/2012 8:45 AM</span><span class="sxs-lookup"><span data-stu-id="31fa2-136">7/7/2012 8:45 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31fa2-137">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="31fa2-137">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="31fa2-138">7/7/2012 8:46 AM</span><span class="sxs-lookup"><span data-stu-id="31fa2-138">7/7/2012 8:46 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31fa2-139">Pilar 方</span><span class="sxs-lookup"><span data-stu-id="31fa2-139">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="31fa2-140">7/7/2012 9:17 AM</span><span class="sxs-lookup"><span data-stu-id="31fa2-140">7/7/2012 9:17 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31fa2-141">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="31fa2-141">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="31fa2-142">7/7/2012 9:22 AM</span><span class="sxs-lookup"><span data-stu-id="31fa2-142">7/7/2012 9:22 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31fa2-143">Pilar 方</span><span class="sxs-lookup"><span data-stu-id="31fa2-143">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="31fa2-144">7/7/2012 9:31 AM</span><span class="sxs-lookup"><span data-stu-id="31fa2-144">7/7/2012 9:31 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="31fa2-145">請注意，總共有五次登錄;不過，只有兩個唯一的登錄使用者： Ken Myer （登入三次的人員）和 Pilar 方（登入兩次）。</span><span class="sxs-lookup"><span data-stu-id="31fa2-145">Notice that there is a total of five logons; however, there are only two unique logon users: Ken Myer (who logged on three times) and Pilar Ackerman (who logged on twice).</span></span> <span data-ttu-id="31fa2-146">這就是登入與唯一登入使用者之間的差異。</span><span class="sxs-lookup"><span data-stu-id="31fa2-146">That's the difference between logons and unique logon users.</span></span>

<span data-ttu-id="31fa2-147">除了瞭解唯一輸入的數目之外，您還需要知道已啟用 Lync Server 的使用者總數。</span><span class="sxs-lookup"><span data-stu-id="31fa2-147">In addition to knowing the number of unique logons, you need to know the total number of users who have been enabled for Lync Server.</span></span> <span data-ttu-id="31fa2-148">您可以開啟 Lync Server 2013 管理命令介面並執行下列 Windows PowerShell 命令來檢索這個值：</span><span class="sxs-lookup"><span data-stu-id="31fa2-148">That value can be retrieved by opening the Lync Server 2013 Management Shell and running the following Windows PowerShell command:</span></span>

    (Get-CsUser).Count

<span data-ttu-id="31fa2-149">如果上述命令傳回1236和唯一的登入使用者度量值，則會傳回667的平均值，這表示使用者每天都能讓 Lync 實際登入系統（也就是667除以1236）。，大約是54%。</span><span class="sxs-lookup"><span data-stu-id="31fa2-149">If the preceding command returns a value of 1,236 and Unique logon users metric returns an average value of 667, that suggests that a little over half of your users enable for Lync are actually logging on to the system each day (that is, 667 divided by 1,236, which is approximately 54%).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="31fa2-150">請記住，登入度量單位會記錄在指定時段內實際登入的使用者。</span><span class="sxs-lookup"><span data-stu-id="31fa2-150">Keep in mind that the logon metrics record users who actually logged on during the specified time period.</span></span> <span data-ttu-id="31fa2-151">它們不會追蹤已登入系統的使用者。</span><span class="sxs-lookup"><span data-stu-id="31fa2-151">They don't keep track of users who were already logged on to the system.</span></span> <span data-ttu-id="31fa2-152">例如，如果您唯一的登入使用者度量會顯示667登入，而您有1236個使用者，這表示您的使用者會登入系統的一半。</span><span class="sxs-lookup"><span data-stu-id="31fa2-152">For example, if your Unique logon users metric shows 667 logons and you have 1,236 users, that suggests that about half your users are logging on to the system.</span></span> <span data-ttu-id="31fa2-153">不過，假設您在開始檢查登入資料時，已登入系統中的300使用者。</span><span class="sxs-lookup"><span data-stu-id="31fa2-153">However, suppose 300 users were already logged on to the system at the time you began checking the logon data.</span></span> <span data-ttu-id="31fa2-154">這表示您實際已有近1000的使用者登入 Lync Server，這會代表使用者已登入80% 的使用者。</span><span class="sxs-lookup"><span data-stu-id="31fa2-154">That would mean that you actually had nearly 1,000 users logged on to Lync Server, which would mean that closer to 80% of your users were logged on.</span></span>



</div>

<span data-ttu-id="31fa2-155">您也應該將唯一的登入使用者值與唯一的作用中使用者度量值進行比較。</span><span class="sxs-lookup"><span data-stu-id="31fa2-155">You should also compare the Unique logon users value with the value of the Unique active users metric.</span></span> <span data-ttu-id="31fa2-156">[唯一作用中的使用者] 指標會告訴您實際使用 Lync Server 的使用者數目有多少（他們已撥打電話）、加入 Lync 會議，或參與 IM 會話。</span><span class="sxs-lookup"><span data-stu-id="31fa2-156">The Unique active users metric tells you how many unique users actually used Lync Server: they made a phone call, they joined a Lync Meeting, or they participated in an IM session.</span></span> <span data-ttu-id="31fa2-157">這是有用的資訊，因為 Microsoft Lync 2013 可以設定為在使用者每次啟動 Windows 時自動啟動。</span><span class="sxs-lookup"><span data-stu-id="31fa2-157">This is useful information, because Microsoft Lync 2013 can be configured to automatically start each time a user starts Windows.</span></span> <span data-ttu-id="31fa2-158">因此，您可能會有大量的使用者會在每天登入 Windows 時自動登入 Lync，但在該期間不會實際使用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="31fa2-158">Because of that, you might have a large number of users who automatically log on to Lync when they log on to Windows each day, but then never actually use Lync Server during that time period.</span></span>

<span data-ttu-id="31fa2-159">唯一的作用中使用者規格也會在組織中提供更有意義的資料，而使用者通常不會在一天結束時登入 Windows。</span><span class="sxs-lookup"><span data-stu-id="31fa2-159">The Unique active users metric also provides more meaningful data in an organization where users typically do not log off Windows at the end of the day.</span></span> <span data-ttu-id="31fa2-160">相反地，它們只是鎖定其電腦，並離開 Windows 和 Lync 執行。</span><span class="sxs-lookup"><span data-stu-id="31fa2-160">Instead, they simply lock their computers and leave Windows and Lync running.</span></span> <span data-ttu-id="31fa2-161">在這種情況下，您可能會因為您的使用者在數天前登入，且從未登核，所以每天登錄時間都會稍少。</span><span class="sxs-lookup"><span data-stu-id="31fa2-161">In a situation like that, you might end up with very few logons per day because your users logged on several days ago and never logged off.</span></span> <span data-ttu-id="31fa2-162">不過，唯一作用中的使用者會告訴您使用者是否正在使用 Lync 或其他 Lync Server 用戶端。</span><span class="sxs-lookup"><span data-stu-id="31fa2-162">However, Unique active users tells you whether users are actively using Lync or another Lync Server client.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="31fa2-163">濾鏡</span><span class="sxs-lookup"><span data-stu-id="31fa2-163">Filters</span></span>

<span data-ttu-id="31fa2-164">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同的方式來查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="31fa2-164">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="31fa2-165">例如，[使用者註冊] 報告可讓您查看所有註冊機構池及邊緣伺服器的資料，或查看個別池的資料。</span><span class="sxs-lookup"><span data-stu-id="31fa2-165">For example, the User Registration Report enables you to view data for all your Registrar pool and Edge Servers or to view data for an individual pool.</span></span> <span data-ttu-id="31fa2-166">您也可以選擇分組資料的方式。</span><span class="sxs-lookup"><span data-stu-id="31fa2-166">You can also choose how data should be grouped.</span></span> <span data-ttu-id="31fa2-167">在這種情況下，登記會依小時、日、周或月分組。</span><span class="sxs-lookup"><span data-stu-id="31fa2-167">In this case, registrations grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="31fa2-168">下表列出可與使用者註冊報告搭配使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="31fa2-168">The following table lists the filters that you can use with the User Registration Report.</span></span>

### <a name="user-registration-report-filters"></a><span data-ttu-id="31fa2-169">使用者註冊報告篩選</span><span class="sxs-lookup"><span data-stu-id="31fa2-169">User Registration Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31fa2-170">名稱</span><span class="sxs-lookup"><span data-stu-id="31fa2-170">Name</span></span></th>
<th><span data-ttu-id="31fa2-171">描述</span><span class="sxs-lookup"><span data-stu-id="31fa2-171">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31fa2-172"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="31fa2-172"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="31fa2-173">時間範圍的開始日期和時間。</span><span class="sxs-lookup"><span data-stu-id="31fa2-173">Start date and time for the time range.</span></span> <span data-ttu-id="31fa2-174">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="31fa2-174">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="31fa2-175">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="31fa2-175">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="31fa2-176">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="31fa2-176">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="31fa2-177">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="31fa2-177">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="31fa2-178">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="31fa2-178">7/7/2012</span></span></p>
<p><span data-ttu-id="31fa2-179">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="31fa2-179">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="31fa2-180">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="31fa2-180">7/3/2012</span></span></p>
<p><span data-ttu-id="31fa2-181">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="31fa2-181">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31fa2-182"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="31fa2-182"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="31fa2-183">時間範圍的結束日期和時間。</span><span class="sxs-lookup"><span data-stu-id="31fa2-183">End date and time for the time range.</span></span> <span data-ttu-id="31fa2-184">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="31fa2-184">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="31fa2-185">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="31fa2-185">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="31fa2-186">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="31fa2-186">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="31fa2-187">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="31fa2-187">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="31fa2-188">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="31fa2-188">7/7/2012</span></span></p>
<p><span data-ttu-id="31fa2-189">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="31fa2-189">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="31fa2-190">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="31fa2-190">7/3/2012</span></span></p>
<p><span data-ttu-id="31fa2-191">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="31fa2-191">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31fa2-192"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="31fa2-192"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="31fa2-193">時間間隔。</span><span class="sxs-lookup"><span data-stu-id="31fa2-193">Time interval.</span></span> <span data-ttu-id="31fa2-194">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="31fa2-194">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="31fa2-195">每小時（最多可顯示25小時）</span><span class="sxs-lookup"><span data-stu-id="31fa2-195">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="31fa2-196">每天（最多可以顯示31天）</span><span class="sxs-lookup"><span data-stu-id="31fa2-196">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="31fa2-197">每週（最多可以顯示12周）</span><span class="sxs-lookup"><span data-stu-id="31fa2-197">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="31fa2-198">每月（最多可以顯示12個月）</span><span class="sxs-lookup"><span data-stu-id="31fa2-198">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="31fa2-199">如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數目，則只會顯示最大值數（從開始日期開始）。</span><span class="sxs-lookup"><span data-stu-id="31fa2-199">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed.</span></span> <span data-ttu-id="31fa2-200">例如，如果您選取 [開始日期 7/7/2012] 和 [結束日期] 2/28/2012 的 [日間隔]，則會顯示 8/7/2012 12:00 AM 至 9/7/2012 12:00 AM （也就是31天內的資料）的資料。</span><span class="sxs-lookup"><span data-stu-id="31fa2-200">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31fa2-201"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="31fa2-201"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="31fa2-202">註冊機構池或邊緣伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="31fa2-202">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="31fa2-203">您可以選取個別的池子，或選擇<strong>[all] （[全部]）</strong>來查看所有資源庫的資料。</span><span class="sxs-lookup"><span data-stu-id="31fa2-203">You can either select an individual pool or choose <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="31fa2-204">這個下拉式清單會根據資料庫中的記錄，自動填入給您。</span><span class="sxs-lookup"><span data-stu-id="31fa2-204">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="31fa2-205">指標</span><span class="sxs-lookup"><span data-stu-id="31fa2-205">Metrics</span></span>

<span data-ttu-id="31fa2-206">下表列出 [使用者註冊] 報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="31fa2-206">The following table lists the information provided in the User Registration Report.</span></span>

### <a name="user-registration-report-metrics"></a><span data-ttu-id="31fa2-207">使用者註冊報告度量單位</span><span class="sxs-lookup"><span data-stu-id="31fa2-207">User Registration Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31fa2-208">名稱</span><span class="sxs-lookup"><span data-stu-id="31fa2-208">Name</span></span></th>
<th><span data-ttu-id="31fa2-209">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="31fa2-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="31fa2-210">描述</span><span class="sxs-lookup"><span data-stu-id="31fa2-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31fa2-211"><strong>工資</strong></span><span class="sxs-lookup"><span data-stu-id="31fa2-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="31fa2-212"><strong>日常</strong></span><span class="sxs-lookup"><span data-stu-id="31fa2-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="31fa2-213"><strong>周更新</strong></span><span class="sxs-lookup"><span data-stu-id="31fa2-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="31fa2-214"><strong>次</strong></span><span class="sxs-lookup"><span data-stu-id="31fa2-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="31fa2-215">否</span><span class="sxs-lookup"><span data-stu-id="31fa2-215">No</span></span></p></td>
<td><p><span data-ttu-id="31fa2-216">指出您在 [篩選] 工具列上選取的時間間隔。</span><span class="sxs-lookup"><span data-stu-id="31fa2-216">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="31fa2-217">在適當的地方，您可以按一下指定的時間間隔，以查看該間隔的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="31fa2-217">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="31fa2-218">例如，如果您使用的是每日間隔，而您按一下 [7/7/2012]，就會看到該日期的使用者註冊活動的每小時細目。</span><span class="sxs-lookup"><span data-stu-id="31fa2-218">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31fa2-219"><strong>登錄總計</strong></span><span class="sxs-lookup"><span data-stu-id="31fa2-219"><strong>Total logons</strong></span></span></p></td>
<td><p><span data-ttu-id="31fa2-220">否</span><span class="sxs-lookup"><span data-stu-id="31fa2-220">No</span></span></p></td>
<td><p><span data-ttu-id="31fa2-221">成功登入會話的總數。</span><span class="sxs-lookup"><span data-stu-id="31fa2-221">Total number of successful logon sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31fa2-222"><strong>內部登錄</strong></span><span class="sxs-lookup"><span data-stu-id="31fa2-222"><strong>Internal logons</strong></span></span></p></td>
<td><p><span data-ttu-id="31fa2-223">否</span><span class="sxs-lookup"><span data-stu-id="31fa2-223">No</span></span></p></td>
<td><p><span data-ttu-id="31fa2-224">內部網路中的登錄總數量。</span><span class="sxs-lookup"><span data-stu-id="31fa2-224">Total number of logons within the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31fa2-225"><strong>外部登錄</strong></span><span class="sxs-lookup"><span data-stu-id="31fa2-225"><strong>External logons</strong></span></span></p></td>
<td><p><span data-ttu-id="31fa2-226">否</span><span class="sxs-lookup"><span data-stu-id="31fa2-226">No</span></span></p></td>
<td><p><span data-ttu-id="31fa2-227">使用 Edge 伺服器從內部網路外部進行的登錄總次數。</span><span class="sxs-lookup"><span data-stu-id="31fa2-227">Total number of logons from outside the internal network, using the Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31fa2-228"><strong>唯一的登入使用者</strong></span><span class="sxs-lookup"><span data-stu-id="31fa2-228"><strong>Unique logon users</strong></span></span></p></td>
<td><p><span data-ttu-id="31fa2-229">否</span><span class="sxs-lookup"><span data-stu-id="31fa2-229">No</span></span></p></td>
<td><p><span data-ttu-id="31fa2-230">至少有一個登入會話的使用者總數。</span><span class="sxs-lookup"><span data-stu-id="31fa2-230">Total number of users who had at least one logon session.</span></span> <span data-ttu-id="31fa2-231">有多個登入會話的使用者會算作一個使用者，與只有單一登入會話的人一樣。</span><span class="sxs-lookup"><span data-stu-id="31fa2-231">A user who had multiple logon sessions counts as one user, the same as a person who had just a single logon session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31fa2-232"><strong>唯一的作用中使用者</strong></span><span class="sxs-lookup"><span data-stu-id="31fa2-232"><strong>Unique active users</strong></span></span></p></td>
<td><p><span data-ttu-id="31fa2-233">否</span><span class="sxs-lookup"><span data-stu-id="31fa2-233">No</span></span></p></td>
<td><p><span data-ttu-id="31fa2-234">參與對等或會議會話的使用者總數。</span><span class="sxs-lookup"><span data-stu-id="31fa2-234">Total number of users who were involved in a peer-to-peer or conferencing session.</span></span> <span data-ttu-id="31fa2-235">擁有多個會議的使用者，與只有單一會話的人員相同。</span><span class="sxs-lookup"><span data-stu-id="31fa2-235">A user who had multiple sessions counts as one user, the same as a person who had just a single session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013： 使用者註冊報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Registration Report
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48183486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 716d8324fba8346fa1326da2ed253dfa07bc3915
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-registration-report-in-lync-server-2013"></a><span data-ttu-id="03155-102">Lync Server 2013 中的使用者註冊報告</span><span class="sxs-lookup"><span data-stu-id="03155-102">User Registration Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03155-103">_**主題上次修改日期：** 2012年-10-21_</span><span class="sxs-lookup"><span data-stu-id="03155-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="03155-104">使用者註冊報告提供的使用者登入活動的概觀，最特別是在指定的時間期間內 （每小時、 每天、 每週、 每月） 登入 Microsoft Lync Server 2013 的使用者數目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="03155-104">The User Registration Report provides an overview of user logon activity, most notably information about the number of users who logged on to Microsoft Lync Server 2013 during a specified time period (hourly, daily, weekly, monthly).</span></span> <span data-ttu-id="03155-105">請記住，報告只會告訴您登入的人數。</span><span class="sxs-lookup"><span data-stu-id="03155-105">Keep in mind that the report only tells you how many people logged on.</span></span> <span data-ttu-id="03155-106">它不會告訴您*哪些*人的身分登入。</span><span class="sxs-lookup"><span data-stu-id="03155-106">It does not tell you *which* people logged on.</span></span> <span data-ttu-id="03155-107">使用 Lync Server 2013 相關的特定使用者 （且哪些項目不） 監控報告不會提供資訊。</span><span class="sxs-lookup"><span data-stu-id="03155-107">Monitoring Reports do not provide information about which specific users are using Lync Server 2013 (and which ones are not).</span></span> <span data-ttu-id="03155-108">不過，您可以使用使用者活動報告來取得使用者資訊大約估計。</span><span class="sxs-lookup"><span data-stu-id="03155-108">However, you can get a rough estimate of user information by using the User Activity Report.</span></span>

<span data-ttu-id="03155-109">使用者註冊報告在提供使用者登入的相關資訊時，會提出兩項重要差異。</span><span class="sxs-lookup"><span data-stu-id="03155-109">When providing information about user logons, the User Registration Report draws two important distinctions.</span></span> <span data-ttu-id="03155-110">首先，其會將登入分為兩種主要類別：內部登入及外部登入。</span><span class="sxs-lookup"><span data-stu-id="03155-110">First, it breaks logons down into two primary categories: internal logons and external logons.</span></span> <span data-ttu-id="03155-111">內部登入代表從組織防火牆內部登入的使用者 (也就是連線到公司網路時)。</span><span class="sxs-lookup"><span data-stu-id="03155-111">Internal logons represent users who logged on from inside your organization's firewall (that is, while connected to the corporate network).</span></span> <span data-ttu-id="03155-112">外部登入代表從登入透過 Edge Server （例如，從咖算作外部登入網際網路登入的使用者） 防火牆外的使用者。</span><span class="sxs-lookup"><span data-stu-id="03155-112">External logons represent users who logged on from outside the firewall through an Edge Server (for example, a user who logged on from an Internet café counts as an external logon).</span></span> <span data-ttu-id="03155-113">如果您需要知道您有多少使用者從防火牆外部登入，使用者註冊報告可以提供您此資訊。</span><span class="sxs-lookup"><span data-stu-id="03155-113">If you need to know how many of your users are logging on from outside the firewall, the User Registration Report can provide you with this information.</span></span>

<span data-ttu-id="03155-114">此外，使用者註冊報告會記錄在指定的時段內，有多少「作用中」\*\* 使用者存在。</span><span class="sxs-lookup"><span data-stu-id="03155-114">In addition, the User Registration Report notes how many *active* users were present during a given time period.</span></span> <span data-ttu-id="03155-115">作用中的使用者是時間的參與立即訊息 (IM) 工作階段的使用者參與 Lync 會議、 進行或收到的電話，或否則在該期間內使用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="03155-115">An active user is a user who took part in an instant messaging (IM) session, participated in a Lync Meeting, made or received a phone call, or otherwise used Lync Server during that period of time.</span></span> <span data-ttu-id="03155-116">這不同於登入但實際上從未使用系統的使用者。</span><span class="sxs-lookup"><span data-stu-id="03155-116">This is different from a user who logged on, but never actually used the system.</span></span>

<div>

## <a name="accessing-the-user-registration-report"></a><span data-ttu-id="03155-117">存取使用者註冊報告</span><span class="sxs-lookup"><span data-stu-id="03155-117">Accessing the User Registration Report</span></span>

<span data-ttu-id="03155-p104">您只能從監視報告首頁存取使用者註冊報告。使用者註冊報告沒有連結至任何其他報告。</span><span class="sxs-lookup"><span data-stu-id="03155-p104">You access the User Registration Report only from the Monitoring Reports home page. The User Registration Report does not link to any other reports.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a><span data-ttu-id="03155-120">善加利用使用者註冊報告</span><span class="sxs-lookup"><span data-stu-id="03155-120">Making the Best Use of the User Registration Report</span></span>

<span data-ttu-id="03155-121">部署 Lync Server 其中經常要求後的問題是： 如何知道我的使用者是否實際上使用這項新技術？</span><span class="sxs-lookup"><span data-stu-id="03155-121">After you've deployed Lync Server one commonly-asked question is this: How do I know if my users are actually using this new technology?</span></span> <span data-ttu-id="03155-122">雖然在這方面有些許限制，但是使用者註冊報告可以協助您回答這個問題。</span><span class="sxs-lookup"><span data-stu-id="03155-122">Although it has a few limitations in this regard, the User Registration Report can help you answer this question.</span></span> <span data-ttu-id="03155-123">若要決定使用者要使用 Lync Server，您需要執行下列兩件事。</span><span class="sxs-lookup"><span data-stu-id="03155-123">To determine whether or not users are using Lync Server, you need to do two things.</span></span> <span data-ttu-id="03155-124">首先，從使用者註冊報告取得唯一登入使用者計量值。</span><span class="sxs-lookup"><span data-stu-id="03155-124">First, get the value of the Unique logon users metric from the User Registration Report.</span></span> <span data-ttu-id="03155-125">此值會告訴您如何許多不同的個人登入 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="03155-125">This value tells you how many distinct individuals logged on to Lync Server.</span></span>

<span data-ttu-id="03155-126">相較之下，登入總數公制顯示多少人登入 Lync Server 的總時間。</span><span class="sxs-lookup"><span data-stu-id="03155-126">By comparison, the Total logons metric shows how many total times anyone logged on to Lync Server.</span></span> <span data-ttu-id="03155-127">例如，假設為 Ken myer 的使用者登入 Lync Server 五個不同的時間，在一天。</span><span class="sxs-lookup"><span data-stu-id="03155-127">For example, suppose Ken Myer logged on to Lync Server five different times in a single day.</span></span> <span data-ttu-id="03155-128">在此情況下，就總登入計量而言，Ken Myer 會計為五個不同的登入工作階段，但是就唯一登入使用者計量而言，只有一位登入使用者。</span><span class="sxs-lookup"><span data-stu-id="03155-128">In that case, Ken Myer would count as five separate logon sessions for the Total logons metric, but just one logon user for the Unique logon users metric.</span></span> <span data-ttu-id="03155-129">同樣地，一位使用者從多個裝置或多個位置登入並無不同。</span><span class="sxs-lookup"><span data-stu-id="03155-129">Likewise, it's not uncommon for a user to log on from multiple devices or multiple locations.</span></span> <span data-ttu-id="03155-130">例如，使用者可以使用登入其桌面的電腦，其膝上型電腦，而她可以有自動登入 Lync Server IP 電話。</span><span class="sxs-lookup"><span data-stu-id="03155-130">For example, a user can log on using her desktop computer, her laptop computer, and she can have an IP phone that automatically logs on to Lync Server.</span></span> <span data-ttu-id="03155-131">在此範例中，共有一位唯一使用者登入三次。</span><span class="sxs-lookup"><span data-stu-id="03155-131">In this example, there is one unique user with three logons.</span></span>

<span data-ttu-id="03155-132">為進一步說明總登入及唯一登入之間的差異，請想想下表中特定時段內的登入。</span><span class="sxs-lookup"><span data-stu-id="03155-132">To further explain the difference between total logons and unique logons, consider the logons for a given time period in the following table.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03155-133">使用者</span><span class="sxs-lookup"><span data-stu-id="03155-133">User</span></span></th>
<th><span data-ttu-id="03155-134">登入時間</span><span class="sxs-lookup"><span data-stu-id="03155-134">Logon time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03155-135">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="03155-135">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="03155-136">7/7/2012 8:45 AM</span><span class="sxs-lookup"><span data-stu-id="03155-136">7/7/2012 8:45 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03155-137">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="03155-137">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="03155-138">7/7/2012 8:46 AM</span><span class="sxs-lookup"><span data-stu-id="03155-138">7/7/2012 8:46 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03155-139">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="03155-139">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="03155-140">7/7/2012 9:17 AM</span><span class="sxs-lookup"><span data-stu-id="03155-140">7/7/2012 9:17 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03155-141">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="03155-141">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="03155-142">7/7/2012 9:22 AM</span><span class="sxs-lookup"><span data-stu-id="03155-142">7/7/2012 9:22 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03155-143">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="03155-143">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="03155-144">7/7/2012 9:31 AM</span><span class="sxs-lookup"><span data-stu-id="03155-144">7/7/2012 9:31 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="03155-p107">請注意，總共有五次登入；不過，只有兩位唯一登入使用者：Ken Myer (登入三次) 及 Pilar Ackerman (登入兩次)。這就是登入與唯一登入使用者之間的差異。</span><span class="sxs-lookup"><span data-stu-id="03155-p107">Notice that there is a total of five logons; however, there are only two unique logon users: Ken Myer (who logged on three times) and Pilar Ackerman (who logged on twice). That's the difference between logons and unique logon users.</span></span>

<span data-ttu-id="03155-147">除了瞭解有多少的唯一登入，您需要知道的已啟用 Lync Server 的使用者總數。</span><span class="sxs-lookup"><span data-stu-id="03155-147">In addition to knowing the number of unique logons, you need to know the total number of users who have been enabled for Lync Server.</span></span> <span data-ttu-id="03155-148">值可以被擷取的開啟 Lync Server 2013 管理命令介面，並執行下列 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="03155-148">That value can be retrieved by opening the Lync Server 2013 Management Shell and running the following Windows PowerShell command:</span></span>

    (Get-CsUser).Count

<span data-ttu-id="03155-149">如果上述命令會傳回的值為 1236，而唯一登入使用者計量傳回的平均值為 667，建議，有點超過一半的使用者啟用 Lync 實際登入系統 (也就是 667 除以 1236 每日也就是大約為 54%)。</span><span class="sxs-lookup"><span data-stu-id="03155-149">If the preceding command returns a value of 1,236 and Unique logon users metric returns an average value of 667, that suggests that a little over half of your users enable for Lync are actually logging on to the system each day (that is, 667 divided by 1,236, which is approximately 54%).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="03155-150">請記住，登入度量資訊記錄在指定的時間期間實際登入的使用者。</span><span class="sxs-lookup"><span data-stu-id="03155-150">Keep in mind that the logon metrics record users who actually logged on during the specified time period.</span></span> <span data-ttu-id="03155-151">它們不追蹤的已登入系統的使用者。</span><span class="sxs-lookup"><span data-stu-id="03155-151">They don't keep track of users who were already logged on to the system.</span></span> <span data-ttu-id="03155-152">例如，如果您唯一登入使用者計量顯示 667 登入，且您有 1,236 的使用者的建議，您大約一半的使用者登入系統。</span><span class="sxs-lookup"><span data-stu-id="03155-152">For example, if your Unique logon users metric shows 667 logons and you have 1,236 users, that suggests that about half your users are logging on to the system.</span></span> <span data-ttu-id="03155-153">不過，假設 300 位使用者已登入系統次您開始檢查登入資料。</span><span class="sxs-lookup"><span data-stu-id="03155-153">However, suppose 300 users were already logged on to the system at the time you began checking the logon data.</span></span> <span data-ttu-id="03155-154">這表示您真的開幾乎 1000 位使用者登入 Lync Server，這就是，近 80%的使用者已登入。</span><span class="sxs-lookup"><span data-stu-id="03155-154">That would mean that you actually had nearly 1,000 users logged on to Lync Server, which would mean that closer to 80% of your users were logged on.</span></span>



</div>

<span data-ttu-id="03155-155">您也應該要比較唯一登入使用者值與唯一作用中使用者計量值。</span><span class="sxs-lookup"><span data-stu-id="03155-155">You should also compare the Unique logon users value with the value of the Unique active users metric.</span></span> <span data-ttu-id="03155-156">唯一作用中使用者] 計量會告訴您單獨使用者人數實際上使用 Lync Server： 他們進行的通話、 他們加入 Lync 會議中，或他們參與的 IM 工作階段。</span><span class="sxs-lookup"><span data-stu-id="03155-156">The Unique active users metric tells you how many unique users actually used Lync Server: they made a phone call, they joined a Lync Meeting, or they participated in an IM session.</span></span> <span data-ttu-id="03155-157">這是很有用的資訊，因為 Microsoft Lync 2013 可以設定設為自動啟動 [每次使用者啟動視窗。</span><span class="sxs-lookup"><span data-stu-id="03155-157">This is useful information, because Microsoft Lync 2013 can be configured to automatically start each time a user starts Windows.</span></span> <span data-ttu-id="03155-158">因此，您可能有大量的自動登入 Lync 當他們登入 Windows 每一天，但然後從未實際在該時間期間內使用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="03155-158">Because of that, you might have a large number of users who automatically log on to Lync when they log on to Windows each day, but then never actually use Lync Server during that time period.</span></span>

<span data-ttu-id="03155-159">唯一作用中使用者] 計量也會提供更有意義的資料，其中使用者通常不需登關閉 Windows 一天結尾處的組織中。</span><span class="sxs-lookup"><span data-stu-id="03155-159">The Unique active users metric also provides more meaningful data in an organization where users typically do not log off Windows at the end of the day.</span></span> <span data-ttu-id="03155-160">相反地，他們只要鎖定他們的電腦，並保留 Windows 和執行 Lync。</span><span class="sxs-lookup"><span data-stu-id="03155-160">Instead, they simply lock their computers and leave Windows and Lync running.</span></span> <span data-ttu-id="03155-161">在這類情況下，您可能結尾很少的登入每日因為您的使用者登入數天之內及永遠不會關閉登入。</span><span class="sxs-lookup"><span data-stu-id="03155-161">In a situation like that, you might end up with very few logons per day because your users logged on several days ago and never logged off.</span></span> <span data-ttu-id="03155-162">不過，唯一作用中使用者會告訴您是否使用者目前正在使用 Lync 或其他的 Lync Server 用戶端。</span><span class="sxs-lookup"><span data-stu-id="03155-162">However, Unique active users tells you whether users are actively using Lync or another Lync Server client.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="03155-163">篩選</span><span class="sxs-lookup"><span data-stu-id="03155-163">Filters</span></span>

<span data-ttu-id="03155-164">篩選器可以讓您傳回更精確的資料集，或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="03155-164">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="03155-165">例如，使用者註冊報告可讓您檢視所有登錄器集區與 Edge Server 的資料，或檢視個別的集區的資料。</span><span class="sxs-lookup"><span data-stu-id="03155-165">For example, the User Registration Report enables you to view data for all your Registrar pool and Edge Servers or to view data for an individual pool.</span></span> <span data-ttu-id="03155-166">您也可以選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="03155-166">You can also choose how data should be grouped.</span></span> <span data-ttu-id="03155-167">在這種情況下，註冊會按照小時、日、星期或月來分組。</span><span class="sxs-lookup"><span data-stu-id="03155-167">In this case, registrations grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="03155-168">下表列出您可以搭配使用者註冊報告的篩選。</span><span class="sxs-lookup"><span data-stu-id="03155-168">The following table lists the filters that you can use with the User Registration Report.</span></span>

### <a name="user-registration-report-filters"></a><span data-ttu-id="03155-169">使用者註冊報告篩選</span><span class="sxs-lookup"><span data-stu-id="03155-169">User Registration Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03155-170">名稱</span><span class="sxs-lookup"><span data-stu-id="03155-170">Name</span></span></th>
<th><span data-ttu-id="03155-171">描述</span><span class="sxs-lookup"><span data-stu-id="03155-171">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03155-172"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="03155-172"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="03155-p113">時間範圍的開始日期和時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="03155-p113">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="03155-175">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="03155-175">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="03155-p114">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="03155-p114">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="03155-178">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="03155-178">7/7/2012</span></span></p>
<p><span data-ttu-id="03155-179">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="03155-179">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="03155-180">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="03155-180">7/3/2012</span></span></p>
<p><span data-ttu-id="03155-181">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="03155-181">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03155-182"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="03155-182"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="03155-p115">時間範圍的結束日期和時間。若要按照小時檢視資料，請輸入結束日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="03155-p115">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="03155-185">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="03155-185">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="03155-p116">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="03155-p116">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="03155-188">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="03155-188">7/7/2012</span></span></p>
<p><span data-ttu-id="03155-189">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="03155-189">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="03155-190">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="03155-190">7/3/2012</span></span></p>
<p><span data-ttu-id="03155-191">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="03155-191">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03155-192"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="03155-192"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="03155-p117">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="03155-p117">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="03155-195">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="03155-195">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="03155-196">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="03155-196">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="03155-197">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="03155-197">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="03155-198">每月 (最多可以顯示 12 個月)</span><span class="sxs-lookup"><span data-stu-id="03155-198">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="03155-p118">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 7 月 7 日及 2012 年 2 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</span><span class="sxs-lookup"><span data-stu-id="03155-p118">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03155-201"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="03155-201"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="03155-202">登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="03155-202">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="03155-203">您可以選取個別的集區，或是選擇 [全部]<strong></strong>，以檢視所有集區的資料。</span><span class="sxs-lookup"><span data-stu-id="03155-203">You can either select an individual pool or choose <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="03155-204">此下拉式清單會自動將資料庫內的資料填入。</span><span class="sxs-lookup"><span data-stu-id="03155-204">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="03155-205">計量</span><span class="sxs-lookup"><span data-stu-id="03155-205">Metrics</span></span>

<span data-ttu-id="03155-206">下表列出使用者註冊報告提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="03155-206">The following table lists the information provided in the User Registration Report.</span></span>

### <a name="user-registration-report-metrics"></a><span data-ttu-id="03155-207">使用者註冊報告計量</span><span class="sxs-lookup"><span data-stu-id="03155-207">User Registration Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03155-208">名稱</span><span class="sxs-lookup"><span data-stu-id="03155-208">Name</span></span></th>
<th><span data-ttu-id="03155-209">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="03155-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="03155-210">描述</span><span class="sxs-lookup"><span data-stu-id="03155-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03155-211"><strong>每小時</strong></span><span class="sxs-lookup"><span data-stu-id="03155-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="03155-212"><strong>每日</strong></span><span class="sxs-lookup"><span data-stu-id="03155-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="03155-213"><strong>每週</strong></span><span class="sxs-lookup"><span data-stu-id="03155-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="03155-214"><strong>每月</strong></span><span class="sxs-lookup"><span data-stu-id="03155-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="03155-215">否</span><span class="sxs-lookup"><span data-stu-id="03155-215">No</span></span></p></td>
<td><p><span data-ttu-id="03155-p120">在篩選工具列上顯示您所選取的時間間隔。在適用的情況下，只要按一下所指定的時間間隔，即可檢視該間隔的詳細資訊。例如，您若是使用 [每日] 間隔，然後按一下 7/7/2012，將會顯示該日之使用者註冊活動的每小時明細。</span><span class="sxs-lookup"><span data-stu-id="03155-p120">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03155-219"><strong>登入總數</strong></span><span class="sxs-lookup"><span data-stu-id="03155-219"><strong>Total logons</strong></span></span></p></td>
<td><p><span data-ttu-id="03155-220">否</span><span class="sxs-lookup"><span data-stu-id="03155-220">No</span></span></p></td>
<td><p><span data-ttu-id="03155-221">登入工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="03155-221">Total number of successful logon sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03155-222"><strong>內部登入</strong></span><span class="sxs-lookup"><span data-stu-id="03155-222"><strong>Internal logons</strong></span></span></p></td>
<td><p><span data-ttu-id="03155-223">否</span><span class="sxs-lookup"><span data-stu-id="03155-223">No</span></span></p></td>
<td><p><span data-ttu-id="03155-224">內部網路內的登入總數。</span><span class="sxs-lookup"><span data-stu-id="03155-224">Total number of logons within the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03155-225"><strong>外部登入</strong></span><span class="sxs-lookup"><span data-stu-id="03155-225"><strong>External logons</strong></span></span></p></td>
<td><p><span data-ttu-id="03155-226">否</span><span class="sxs-lookup"><span data-stu-id="03155-226">No</span></span></p></td>
<td><p><span data-ttu-id="03155-227">使用 Edge Server，來自內部網路以外的登入總數。</span><span class="sxs-lookup"><span data-stu-id="03155-227">Total number of logons from outside the internal network, using the Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03155-228"><strong>唯一登入使用者</strong></span><span class="sxs-lookup"><span data-stu-id="03155-228"><strong>Unique logon users</strong></span></span></p></td>
<td><p><span data-ttu-id="03155-229">否</span><span class="sxs-lookup"><span data-stu-id="03155-229">No</span></span></p></td>
<td><p><span data-ttu-id="03155-p121">至少有一次登入工作階段的使用者總數。若使用者擁有多個登入工作階段，仍會計為一個使用者；和僅有單一登入工作階段的人員相同。</span><span class="sxs-lookup"><span data-stu-id="03155-p121">Total number of users who had at least one logon session. A user who had multiple logon sessions counts as one user, the same as a person who had just a single logon session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03155-232"><strong>唯一作用中使用者</strong></span><span class="sxs-lookup"><span data-stu-id="03155-232"><strong>Unique active users</strong></span></span></p></td>
<td><p><span data-ttu-id="03155-233">否</span><span class="sxs-lookup"><span data-stu-id="03155-233">No</span></span></p></td>
<td><p><span data-ttu-id="03155-p122">參與對等或會議工作階段的使用者總數。若使用者擁有多個登入工作階段，仍會計為一個使用者；和僅有單一登入工作階段的人員相同。</span><span class="sxs-lookup"><span data-stu-id="03155-p122">Total number of users who were involved in a peer-to-peer or conferencing session. A user who had multiple sessions counts as one user, the same as a person who had just a single session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


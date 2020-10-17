---
title: Lync Server 2013：使用者註冊報告
description: Lync Server 2013：使用者註冊報告。
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
ms.openlocfilehash: 7adb8ef7e94a24f0fd088f12e009fc9d63f3be9d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569749"
---
# <a name="user-registration-report-in-lync-server-2013"></a><span data-ttu-id="da5de-103">Lync Server 2013 中的使用者註冊報告</span><span class="sxs-lookup"><span data-stu-id="da5de-103">User Registration Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da5de-104">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="da5de-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="da5de-105">使用者註冊報告提供使用者登入活動的概覽，最值得注意的是在指定期間 (每小時、每日、每週、每月) 時，登入 Microsoft Lync Server 2013 之使用者數目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="da5de-105">The User Registration Report provides an overview of user logon activity, most notably information about the number of users who logged on to Microsoft Lync Server 2013 during a specified time period (hourly, daily, weekly, monthly).</span></span> <span data-ttu-id="da5de-106">請記住，報告只會告訴您已登入的人員人數。</span><span class="sxs-lookup"><span data-stu-id="da5de-106">Keep in mind that the report only tells you how many people logged on.</span></span> <span data-ttu-id="da5de-107">它不會告訴您登入 *的* 人員。</span><span class="sxs-lookup"><span data-stu-id="da5de-107">It does not tell you *which* people logged on.</span></span> <span data-ttu-id="da5de-108">監視報告不會提供哪些特定使用者使用 Lync Server 2013 (，哪些不是) 的資訊。</span><span class="sxs-lookup"><span data-stu-id="da5de-108">Monitoring Reports do not provide information about which specific users are using Lync Server 2013 (and which ones are not).</span></span> <span data-ttu-id="da5de-109">不過，您可以使用 [使用者活動報告] 來取得使用者資訊的粗略估計。</span><span class="sxs-lookup"><span data-stu-id="da5de-109">However, you can get a rough estimate of user information by using the User Activity Report.</span></span>

<span data-ttu-id="da5de-110">使用者註冊報告在提供使用者登入的相關資訊時，會提出兩項重要差異。</span><span class="sxs-lookup"><span data-stu-id="da5de-110">When providing information about user logons, the User Registration Report draws two important distinctions.</span></span> <span data-ttu-id="da5de-111">首先，其會將登入分為兩種主要類別：內部登入及外部登入。</span><span class="sxs-lookup"><span data-stu-id="da5de-111">First, it breaks logons down into two primary categories: internal logons and external logons.</span></span> <span data-ttu-id="da5de-112">內部登入代表從組織防火牆內部登入的使用者 (也就是連線到公司網路時)。</span><span class="sxs-lookup"><span data-stu-id="da5de-112">Internal logons represent users who logged on from inside your organization's firewall (that is, while connected to the corporate network).</span></span> <span data-ttu-id="da5de-113">外部登入代表透過 Edge Server 從防火牆外部登入的使用者 (例如，從網際網路咖啡館登入的使用者會算作外部登入) 。</span><span class="sxs-lookup"><span data-stu-id="da5de-113">External logons represent users who logged on from outside the firewall through an Edge Server (for example, a user who logged on from an Internet café counts as an external logon).</span></span> <span data-ttu-id="da5de-114">如果您需要知道您有多少使用者從防火牆外部登入，使用者註冊報告可以提供您此資訊。</span><span class="sxs-lookup"><span data-stu-id="da5de-114">If you need to know how many of your users are logging on from outside the firewall, the User Registration Report can provide you with this information.</span></span>

<span data-ttu-id="da5de-115">此外，使用者註冊報告會記錄在指定的時段內，有多少「作用中」\*\* 使用者存在。</span><span class="sxs-lookup"><span data-stu-id="da5de-115">In addition, the User Registration Report notes how many *active* users were present during a given time period.</span></span> <span data-ttu-id="da5de-116">作用中的使用者是在立即訊息 (IM) 會話中參與的使用者，參與 Lync 會議，撥打或接聽電話，或在該期間內使用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="da5de-116">An active user is a user who took part in an instant messaging (IM) session, participated in a Lync Meeting, made or received a phone call, or otherwise used Lync Server during that period of time.</span></span> <span data-ttu-id="da5de-117">這不同於登入但實際上從未使用系統的使用者。</span><span class="sxs-lookup"><span data-stu-id="da5de-117">This is different from a user who logged on, but never actually used the system.</span></span>

<div>

## <a name="accessing-the-user-registration-report"></a><span data-ttu-id="da5de-118">存取使用者註冊報告</span><span class="sxs-lookup"><span data-stu-id="da5de-118">Accessing the User Registration Report</span></span>

<span data-ttu-id="da5de-p104">您只能從監視報告首頁存取使用者註冊報告。使用者註冊報告沒有連結至任何其他報告。</span><span class="sxs-lookup"><span data-stu-id="da5de-p104">You access the User Registration Report only from the Monitoring Reports home page. The User Registration Report does not link to any other reports.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a><span data-ttu-id="da5de-121">善加利用使用者註冊報告</span><span class="sxs-lookup"><span data-stu-id="da5de-121">Making the Best Use of the User Registration Report</span></span>

<span data-ttu-id="da5de-122">在您部署 Lync Server 的一個常見問題是：如何知道我的使用者是否真的使用這項新技術？</span><span class="sxs-lookup"><span data-stu-id="da5de-122">After you've deployed Lync Server one commonly-asked question is this: How do I know if my users are actually using this new technology?</span></span> <span data-ttu-id="da5de-123">雖然在這方面有些許限制，但是使用者註冊報告可以協助您回答這個問題。</span><span class="sxs-lookup"><span data-stu-id="da5de-123">Although it has a few limitations in this regard, the User Registration Report can help you answer this question.</span></span> <span data-ttu-id="da5de-124">若要判斷使用者是否正在使用 Lync Server，您需要執行兩項動作。</span><span class="sxs-lookup"><span data-stu-id="da5de-124">To determine whether or not users are using Lync Server, you need to do two things.</span></span> <span data-ttu-id="da5de-125">首先，從使用者註冊報告取得唯一登入使用者計量值。</span><span class="sxs-lookup"><span data-stu-id="da5de-125">First, get the value of the Unique logon users metric from the User Registration Report.</span></span> <span data-ttu-id="da5de-126">這個值會告訴您登入 Lync Server 的不同個人人數。</span><span class="sxs-lookup"><span data-stu-id="da5de-126">This value tells you how many distinct individuals logged on to Lync Server.</span></span>

<span data-ttu-id="da5de-127">相比之下，Total 登入度量單位會顯示登入 Lync Server 的任何人的總時間。</span><span class="sxs-lookup"><span data-stu-id="da5de-127">By comparison, the Total logons metric shows how many total times anyone logged on to Lync Server.</span></span> <span data-ttu-id="da5de-128">例如，假設 Ken Myer 在一天內登入 Lync Server 五個不同的時間。</span><span class="sxs-lookup"><span data-stu-id="da5de-128">For example, suppose Ken Myer logged on to Lync Server five different times in a single day.</span></span> <span data-ttu-id="da5de-129">在此情況下，就總登入計量而言，Ken Myer 會計為五個不同的登入工作階段，但是就唯一登入使用者計量而言，只有一位登入使用者。</span><span class="sxs-lookup"><span data-stu-id="da5de-129">In that case, Ken Myer would count as five separate logon sessions for the Total logons metric, but just one logon user for the Unique logon users metric.</span></span> <span data-ttu-id="da5de-130">同樣地，一位使用者從多個裝置或多個位置登入並無不同。</span><span class="sxs-lookup"><span data-stu-id="da5de-130">Likewise, it's not uncommon for a user to log on from multiple devices or multiple locations.</span></span> <span data-ttu-id="da5de-131">例如，使用者可以使用她的桌上型電腦（她的膝上型電腦）登入，而她可以擁有可自動登入 Lync 伺服器的 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="da5de-131">For example, a user can log on using her desktop computer, her laptop computer, and she can have an IP phone that automatically logs on to Lync Server.</span></span> <span data-ttu-id="da5de-132">在此範例中，共有一位唯一使用者登入三次。</span><span class="sxs-lookup"><span data-stu-id="da5de-132">In this example, there is one unique user with three logons.</span></span>

<span data-ttu-id="da5de-133">為進一步說明總登入及唯一登入之間的差異，請想想下表中特定時段內的登入。</span><span class="sxs-lookup"><span data-stu-id="da5de-133">To further explain the difference between total logons and unique logons, consider the logons for a given time period in the following table.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da5de-134">使用者</span><span class="sxs-lookup"><span data-stu-id="da5de-134">User</span></span></th>
<th><span data-ttu-id="da5de-135">登入時間</span><span class="sxs-lookup"><span data-stu-id="da5de-135">Logon time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da5de-136">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="da5de-136">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="da5de-137">7/7/2012 8:45 AM</span><span class="sxs-lookup"><span data-stu-id="da5de-137">7/7/2012 8:45 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da5de-138">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="da5de-138">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="da5de-139">7/7/2012 8:46 AM</span><span class="sxs-lookup"><span data-stu-id="da5de-139">7/7/2012 8:46 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da5de-140">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="da5de-140">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="da5de-141">7/7/2012 9:17 AM</span><span class="sxs-lookup"><span data-stu-id="da5de-141">7/7/2012 9:17 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da5de-142">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="da5de-142">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="da5de-143">7/7/2012 9:22 AM</span><span class="sxs-lookup"><span data-stu-id="da5de-143">7/7/2012 9:22 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da5de-144">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="da5de-144">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="da5de-145">7/7/2012 9:31 AM</span><span class="sxs-lookup"><span data-stu-id="da5de-145">7/7/2012 9:31 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="da5de-p107">請注意，總共有五次登入；不過，只有兩位唯一登入使用者：Ken Myer (登入三次) 及 Pilar Ackerman (登入兩次)。這就是登入與唯一登入使用者之間的差異。</span><span class="sxs-lookup"><span data-stu-id="da5de-p107">Notice that there is a total of five logons; however, there are only two unique logon users: Ken Myer (who logged on three times) and Pilar Ackerman (who logged on twice). That's the difference between logons and unique logon users.</span></span>

<span data-ttu-id="da5de-148">除了瞭解唯一登入的次數之外，您還需要知道已啟用 Lync Server 的使用者總數。</span><span class="sxs-lookup"><span data-stu-id="da5de-148">In addition to knowing the number of unique logons, you need to know the total number of users who have been enabled for Lync Server.</span></span> <span data-ttu-id="da5de-149">您可以開啟 Lync Server 2013 管理命令介面，並執行下列 Windows PowerShell 命令，以找回此值：</span><span class="sxs-lookup"><span data-stu-id="da5de-149">That value can be retrieved by opening the Lync Server 2013 Management Shell and running the following Windows PowerShell command:</span></span>

    (Get-CsUser).Count

<span data-ttu-id="da5de-150">如果上述命令傳回的值為1236，且唯一登入使用者度量會傳回平均值667，則表示啟用 Lync 的一半以上的使用者每日實際登入系統 (亦即667除以1236，也就是大約 54% ) 。</span><span class="sxs-lookup"><span data-stu-id="da5de-150">If the preceding command returns a value of 1,236 and Unique logon users metric returns an average value of 667, that suggests that a little over half of your users enable for Lync are actually logging on to the system each day (that is, 667 divided by 1,236, which is approximately 54%).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="da5de-151">請記住，登入度量會記錄在指定期間內實際登入的使用者。</span><span class="sxs-lookup"><span data-stu-id="da5de-151">Keep in mind that the logon metrics record users who actually logged on during the specified time period.</span></span> <span data-ttu-id="da5de-152">他們不會追蹤已經登入系統的使用者。</span><span class="sxs-lookup"><span data-stu-id="da5de-152">They don't keep track of users who were already logged on to the system.</span></span> <span data-ttu-id="da5de-153">例如，如果您的唯一登入使用者度量顯示667登入，而您有1236使用者，則表示您的使用者在登入系統時大約有一半。</span><span class="sxs-lookup"><span data-stu-id="da5de-153">For example, if your Unique logon users metric shows 667 logons and you have 1,236 users, that suggests that about half your users are logging on to the system.</span></span> <span data-ttu-id="da5de-154">不過，假設您在開始檢查登入資料時，已登入系統的300使用者。</span><span class="sxs-lookup"><span data-stu-id="da5de-154">However, suppose 300 users were already logged on to the system at the time you began checking the logon data.</span></span> <span data-ttu-id="da5de-155">這表示您實際上有近1000使用者登入 Lync Server，這表示您的使用者離80% 的使用者已登入。</span><span class="sxs-lookup"><span data-stu-id="da5de-155">That would mean that you actually had nearly 1,000 users logged on to Lync Server, which would mean that closer to 80% of your users were logged on.</span></span>



</div>

<span data-ttu-id="da5de-156">您也應該要比較唯一登入使用者值與唯一作用中使用者計量值。</span><span class="sxs-lookup"><span data-stu-id="da5de-156">You should also compare the Unique logon users value with the value of the Unique active users metric.</span></span> <span data-ttu-id="da5de-157">「作用中的作用中使用者指標」會告訴您，有多少使用者實際使用 Lync Server：他們撥打了電話、加入 Lync 會議或參加了 IM 會話。</span><span class="sxs-lookup"><span data-stu-id="da5de-157">The Unique active users metric tells you how many unique users actually used Lync Server: they made a phone call, they joined a Lync Meeting, or they participated in an IM session.</span></span> <span data-ttu-id="da5de-158">這是很有用的資訊，因為 Microsoft Lync 2013 可以設定為每次使用者啟動 Windows 時自動啟動。</span><span class="sxs-lookup"><span data-stu-id="da5de-158">This is useful information, because Microsoft Lync 2013 can be configured to automatically start each time a user starts Windows.</span></span> <span data-ttu-id="da5de-159">因此，您可能會有大量的使用者在每日登入 Windows 時自動登入 Lync，但在該時段內，則不會實際使用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="da5de-159">Because of that, you might have a large number of users who automatically log on to Lync when they log on to Windows each day, but then never actually use Lync Server during that time period.</span></span>

<span data-ttu-id="da5de-160">「作用中的「作用中使用者」度量也會在組織中提供更有意義的資料，而使用者通常不會在一天結束時登出 Windows。</span><span class="sxs-lookup"><span data-stu-id="da5de-160">The Unique active users metric also provides more meaningful data in an organization where users typically do not log off Windows at the end of the day.</span></span> <span data-ttu-id="da5de-161">相反地，它們只是鎖定其電腦，並讓 Windows 和 Lync 保持執行狀態。</span><span class="sxs-lookup"><span data-stu-id="da5de-161">Instead, they simply lock their computers and leave Windows and Lync running.</span></span> <span data-ttu-id="da5de-162">在此情況下，您可能會最後一次登入，因為您的使用者在數天前登入，而且永不登出。</span><span class="sxs-lookup"><span data-stu-id="da5de-162">In a situation like that, you might end up with very few logons per day because your users logged on several days ago and never logged off.</span></span> <span data-ttu-id="da5de-163">不過，唯一的作用中使用者會告訴您使用者目前使用 Lync 或其他 Lync Server 用戶端。</span><span class="sxs-lookup"><span data-stu-id="da5de-163">However, Unique active users tells you whether users are actively using Lync or another Lync Server client.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="da5de-164">篩選</span><span class="sxs-lookup"><span data-stu-id="da5de-164">Filters</span></span>

<span data-ttu-id="da5de-165">篩選器可以讓您傳回更精確的資料集，或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="da5de-165">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="da5de-166">例如，使用者註冊報告可讓您查看所有註冊區集區和 Edge Server 的資料，或查看個別集區的資料。</span><span class="sxs-lookup"><span data-stu-id="da5de-166">For example, the User Registration Report enables you to view data for all your Registrar pool and Edge Servers or to view data for an individual pool.</span></span> <span data-ttu-id="da5de-167">您也可以選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="da5de-167">You can also choose how data should be grouped.</span></span> <span data-ttu-id="da5de-168">在這種情況下，註冊會按照小時、日、星期或月來分組。</span><span class="sxs-lookup"><span data-stu-id="da5de-168">In this case, registrations grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="da5de-169">下表列出您可以搭配使用者註冊報告的篩選。</span><span class="sxs-lookup"><span data-stu-id="da5de-169">The following table lists the filters that you can use with the User Registration Report.</span></span>

### <a name="user-registration-report-filters"></a><span data-ttu-id="da5de-170">使用者註冊報告篩選</span><span class="sxs-lookup"><span data-stu-id="da5de-170">User Registration Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da5de-171">名稱</span><span class="sxs-lookup"><span data-stu-id="da5de-171">Name</span></span></th>
<th><span data-ttu-id="da5de-172">描述</span><span class="sxs-lookup"><span data-stu-id="da5de-172">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da5de-173"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="da5de-173"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="da5de-p113">時間範圍的開始日期和時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="da5de-p113">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="da5de-176">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="da5de-176">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="da5de-p114">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="da5de-p114">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="da5de-179">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="da5de-179">7/7/2012</span></span></p>
<p><span data-ttu-id="da5de-180">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="da5de-180">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="da5de-181">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="da5de-181">7/3/2012</span></span></p>
<p><span data-ttu-id="da5de-182">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="da5de-182">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da5de-183"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="da5de-183"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="da5de-p115">時間範圍的結束日期和時間。若要按照小時檢視資料，請輸入結束日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="da5de-p115">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="da5de-186">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="da5de-186">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="da5de-p116">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="da5de-p116">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="da5de-189">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="da5de-189">7/7/2012</span></span></p>
<p><span data-ttu-id="da5de-190">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="da5de-190">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="da5de-191">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="da5de-191">7/3/2012</span></span></p>
<p><span data-ttu-id="da5de-192">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="da5de-192">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da5de-193"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="da5de-193"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="da5de-p117">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="da5de-p117">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="da5de-196">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="da5de-196">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="da5de-197">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="da5de-197">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="da5de-198">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="da5de-198">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="da5de-199">每月 (最多可以顯示 12 個月)</span><span class="sxs-lookup"><span data-stu-id="da5de-199">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="da5de-p118">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 7 月 7 日及 2012 年 2 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</span><span class="sxs-lookup"><span data-stu-id="da5de-p118">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da5de-202"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="da5de-202"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="da5de-203">登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="da5de-203">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="da5de-204">您可以選取個別的集區，或是選擇 [全部]<strong></strong>，以檢視所有集區的資料。</span><span class="sxs-lookup"><span data-stu-id="da5de-204">You can either select an individual pool or choose <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="da5de-205">此下拉式清單會自動將資料庫內的資料填入。</span><span class="sxs-lookup"><span data-stu-id="da5de-205">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="da5de-206">指標</span><span class="sxs-lookup"><span data-stu-id="da5de-206">Metrics</span></span>

<span data-ttu-id="da5de-207">下表列出使用者註冊報告提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="da5de-207">The following table lists the information provided in the User Registration Report.</span></span>

### <a name="user-registration-report-metrics"></a><span data-ttu-id="da5de-208">使用者註冊報告計量</span><span class="sxs-lookup"><span data-stu-id="da5de-208">User Registration Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da5de-209">姓名</span><span class="sxs-lookup"><span data-stu-id="da5de-209">Name</span></span></th>
<th><span data-ttu-id="da5de-210">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="da5de-210">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="da5de-211">描述</span><span class="sxs-lookup"><span data-stu-id="da5de-211">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da5de-212"><strong>每小時</strong></span><span class="sxs-lookup"><span data-stu-id="da5de-212"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="da5de-213"><strong>每日</strong></span><span class="sxs-lookup"><span data-stu-id="da5de-213"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="da5de-214"><strong>每週</strong></span><span class="sxs-lookup"><span data-stu-id="da5de-214"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="da5de-215"><strong>每月</strong></span><span class="sxs-lookup"><span data-stu-id="da5de-215"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="da5de-216">否</span><span class="sxs-lookup"><span data-stu-id="da5de-216">No</span></span></p></td>
<td><p><span data-ttu-id="da5de-p120">在篩選工具列上顯示您所選取的時間間隔。在適用的情況下，只要按一下所指定的時間間隔，即可檢視該間隔的詳細資訊。例如，您若是使用 [每日] 間隔，然後按一下 7/7/2012，將會顯示該日之使用者註冊活動的每小時明細。</span><span class="sxs-lookup"><span data-stu-id="da5de-p120">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da5de-220"><strong>登入總數</strong></span><span class="sxs-lookup"><span data-stu-id="da5de-220"><strong>Total logons</strong></span></span></p></td>
<td><p><span data-ttu-id="da5de-221">否</span><span class="sxs-lookup"><span data-stu-id="da5de-221">No</span></span></p></td>
<td><p><span data-ttu-id="da5de-222">登入工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="da5de-222">Total number of successful logon sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da5de-223"><strong>內部登入</strong></span><span class="sxs-lookup"><span data-stu-id="da5de-223"><strong>Internal logons</strong></span></span></p></td>
<td><p><span data-ttu-id="da5de-224">否</span><span class="sxs-lookup"><span data-stu-id="da5de-224">No</span></span></p></td>
<td><p><span data-ttu-id="da5de-225">內部網路內的登入總數。</span><span class="sxs-lookup"><span data-stu-id="da5de-225">Total number of logons within the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da5de-226"><strong>外部登入</strong></span><span class="sxs-lookup"><span data-stu-id="da5de-226"><strong>External logons</strong></span></span></p></td>
<td><p><span data-ttu-id="da5de-227">否</span><span class="sxs-lookup"><span data-stu-id="da5de-227">No</span></span></p></td>
<td><p><span data-ttu-id="da5de-228">使用 Edge Server，來自內部網路以外的登入總數。</span><span class="sxs-lookup"><span data-stu-id="da5de-228">Total number of logons from outside the internal network, using the Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da5de-229"><strong>唯一登入使用者</strong></span><span class="sxs-lookup"><span data-stu-id="da5de-229"><strong>Unique logon users</strong></span></span></p></td>
<td><p><span data-ttu-id="da5de-230">否</span><span class="sxs-lookup"><span data-stu-id="da5de-230">No</span></span></p></td>
<td><p><span data-ttu-id="da5de-p121">至少有一次登入工作階段的使用者總數。若使用者擁有多個登入工作階段，仍會計為一個使用者；和僅有單一登入工作階段的人員相同。</span><span class="sxs-lookup"><span data-stu-id="da5de-p121">Total number of users who had at least one logon session. A user who had multiple logon sessions counts as one user, the same as a person who had just a single logon session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da5de-233"><strong>唯一作用中使用者</strong></span><span class="sxs-lookup"><span data-stu-id="da5de-233"><strong>Unique active users</strong></span></span></p></td>
<td><p><span data-ttu-id="da5de-234">否</span><span class="sxs-lookup"><span data-stu-id="da5de-234">No</span></span></p></td>
<td><p><span data-ttu-id="da5de-p122">參與對等或會議工作階段的使用者總數。若使用者擁有多個登入工作階段，仍會計為一個使用者；和僅有單一登入工作階段的人員相同。</span><span class="sxs-lookup"><span data-stu-id="da5de-p122">Total number of users who were involved in a peer-to-peer or conferencing session. A user who had multiple sessions counts as one user, the same as a person who had just a single session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


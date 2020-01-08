---
title: Lync Server 2013：使用者模型
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 user models
ms:assetid: c551371c-d740-4372-bada-f0d713ec0d33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398811(v=OCS.15)
ms:contentKeyID: 49733811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8185fc2fdb92f907eb013349b8a202df2b7b62bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-models-in-lync-server-2013"></a><span data-ttu-id="38376-102">Lync Server 2013 中的使用者模型</span><span class="sxs-lookup"><span data-stu-id="38376-102">User models in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38376-103">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="38376-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="38376-104">此處所述的使用者模型提供[使用使用者模型的 Lync Server 2013 容量規劃](lync-server-2013-capacity-planning-using-the-user-models.md)中所述的容量規劃測量與建議的基礎。</span><span class="sxs-lookup"><span data-stu-id="38376-104">The user models described here provide the basis for the capacity planning measurements and recommendations described in [Capacity planning for Lync Server 2013 using the user models](lync-server-2013-capacity-planning-using-the-user-models.md).</span></span>

<div>

## <a name="lync-server-2013-user-models"></a><span data-ttu-id="38376-105">Lync Server 2013 使用者模型</span><span class="sxs-lookup"><span data-stu-id="38376-105">Lync Server 2013 User Models</span></span>

<span data-ttu-id="38376-106">下表說明 Lync Server 2013 註冊、連絡人、立即訊息（IM）和目前狀態的使用者模型。</span><span class="sxs-lookup"><span data-stu-id="38376-106">The following table describes the user model for registration, contacts, instant messaging (IM), and presence for Lync Server 2013.</span></span>

### <a name="environment-and-registration-user-model"></a><span data-ttu-id="38376-107">環境與註冊使用者模型</span><span class="sxs-lookup"><span data-stu-id="38376-107">Environment and Registration User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38376-108">類別</span><span class="sxs-lookup"><span data-stu-id="38376-108">Category</span></span></th>
<th><span data-ttu-id="38376-109">描述</span><span class="sxs-lookup"><span data-stu-id="38376-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38376-110">部署大小與發佈</span><span class="sxs-lookup"><span data-stu-id="38376-110">Deployment size and distribution</span></span></p></td>
<td><p><span data-ttu-id="38376-111">我們會針對具有三個中心網站的大型部署建模，每個網站都有一個前端池。</span><span class="sxs-lookup"><span data-stu-id="38376-111">We model a large deployment with three central sites, with one Front End pool per site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38376-112">Active Directory 使用者的百分比</span><span class="sxs-lookup"><span data-stu-id="38376-112">Percentage of Active Directory users</span></span></p></td>
<td><p><span data-ttu-id="38376-113">我們假設組織中所有 Active Directory 使用者的70% 都已啟用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="38376-113">We assume that 70% of all Active Directory users in the organization are enabled for Lync Server.</span></span> <span data-ttu-id="38376-114">80% 的使用者每天都會登入 Lync Server （80% concurrency）。</span><span class="sxs-lookup"><span data-stu-id="38376-114">80% of those enabled users are logged on to Lync Server each day (80% concurrency).</span></span> <span data-ttu-id="38376-115">併發使用者是本節其餘部分中的數位的基礎。</span><span class="sxs-lookup"><span data-stu-id="38376-115">The concurrent users are the basis for the numbers in the rest of this section.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38376-116">Active Directory 變更</span><span class="sxs-lookup"><span data-stu-id="38376-116">Active Directory changes</span></span></p></td>
<td><p><span data-ttu-id="38376-117">我們假設每週為 Active Directory 中的 Lync 建立並啟用總使用者數的0.5%，而使用者每週從 Active Directory 和 Lync 停用總使用者數的0.5%。</span><span class="sxs-lookup"><span data-stu-id="38376-117">We assume that 0.5% of total users are created and enabled for Lync in Active Directory each week, and that 0.5% of total users are disabled from Active Directory and from Lync each week.</span></span> <span data-ttu-id="38376-118">5% 的使用者每週至少有一個 Active Directory 屬性已變更。</span><span class="sxs-lookup"><span data-stu-id="38376-118">5% of users have at least one Active Directory attribute changed each week.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38376-119">Active Directory 通訊群組</span><span class="sxs-lookup"><span data-stu-id="38376-119">Active Directory distribution groups</span></span></p></td>
<td><p><span data-ttu-id="38376-120">我們假設組織中的 Active Directory 通訊群組數目等於 Active Directory 中所有使用者數的三倍。</span><span class="sxs-lookup"><span data-stu-id="38376-120">We assume that the number of Active Directory distribution groups in the organization is equal to three times the number of all users in Active Directory.</span></span> <span data-ttu-id="38376-121">通訊群組具有下列大小：</span><span class="sxs-lookup"><span data-stu-id="38376-121">The distribution groups have the following sizes:</span></span></p>
<ul>
<li><p><span data-ttu-id="38376-122">64% 有2-30 使用者</span><span class="sxs-lookup"><span data-stu-id="38376-122">64% have 2-30 users</span></span></p></li>
<li><p><span data-ttu-id="38376-123">13% 有31-50 使用者</span><span class="sxs-lookup"><span data-stu-id="38376-123">13% have 31-50 users</span></span></p></li>
<li><p><span data-ttu-id="38376-124">10% 有51-100 使用者</span><span class="sxs-lookup"><span data-stu-id="38376-124">10% have 51-100 users</span></span></p></li>
<li><p><span data-ttu-id="38376-125">13% 有101-500 使用者</span><span class="sxs-lookup"><span data-stu-id="38376-125">13% have 101-500 users</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38376-126">[語音 over IP （VoIP）] 使用者</span><span class="sxs-lookup"><span data-stu-id="38376-126">Voice over IP (VoIP) users</span></span></p></td>
<td><p><span data-ttu-id="38376-127">60% 的 Lync Server 使用者已啟用整合通訊（UC）（也就是他們的電話號碼是由 Lync Server 所擁有）。</span><span class="sxs-lookup"><span data-stu-id="38376-127">60% of Lync Server users are enabled for unified communications (UC) (that is, their phone numbers are owned by Lync Server).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38376-128">已註冊的用戶端分配</span><span class="sxs-lookup"><span data-stu-id="38376-128">Registered client distribution</span></span></p></td>
<td><p><span data-ttu-id="38376-129">65% 的用戶端執行 Lync 2013 軟體，包括 Lync 和 Lync Phone Edition。</span><span class="sxs-lookup"><span data-stu-id="38376-129">65% of clients run Lync 2013 software, including Lync and Lync Phone Edition.</span></span></p>
<p><span data-ttu-id="38376-130">從舊版 Lync 執行用戶端軟體之客戶的30%。</span><span class="sxs-lookup"><span data-stu-id="38376-130">30% of clients running client software from a previous version of Lync.</span></span></p>
<p><span data-ttu-id="38376-131">5% 的用戶端使用 Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="38376-131">5% of clients using Lync Web App.</span></span></p>
<p><span data-ttu-id="38376-132">如果行動已啟用，我們會假設40% 的使用者正在與其他先前提及的註冊用戶端選項同時使用行動。</span><span class="sxs-lookup"><span data-stu-id="38376-132">If mobility is enabled, we assume that 40% of users are using mobility concurrently with the other previously cited registered client options.</span></span> <span data-ttu-id="38376-133">在這種情況下，用戶端的多重狀態點（MPOP）比率為1：1.9。</span><span class="sxs-lookup"><span data-stu-id="38376-133">In this case the client multiple point of presence (MPOP) ratio is 1:1.9.</span></span> <span data-ttu-id="38376-134">如果行動已停用，則 MPOP 比率為1：1.5。</span><span class="sxs-lookup"><span data-stu-id="38376-134">If mobility is disabled, the MPOP ratio is 1:1.5.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38376-135">遠端使用者發佈</span><span class="sxs-lookup"><span data-stu-id="38376-135">Remote user distribution</span></span></p></td>
<td><p><span data-ttu-id="38376-136">內部連接的使用者70%。</span><span class="sxs-lookup"><span data-stu-id="38376-136">70% of users connecting internally.</span></span></p>
<p><span data-ttu-id="38376-137">透過邊緣伺服器和主管連線的使用者的30%。</span><span class="sxs-lookup"><span data-stu-id="38376-137">30% of users connecting through an Edge Server and a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38376-138">連絡人分配</span><span class="sxs-lookup"><span data-stu-id="38376-138">Contact distribution</span></span></p></td>
<td><p><span data-ttu-id="38376-139">使用者擁有的連絡人數目上限為1000。</span><span class="sxs-lookup"><span data-stu-id="38376-139">The maximum number of contacts a user has is 1,000.</span></span> <span data-ttu-id="38376-140">少於1% 的使用者有1000連絡人。</span><span class="sxs-lookup"><span data-stu-id="38376-140">Less than 1% of users have 1,000 contacts.</span></span> <span data-ttu-id="38376-141">少於25% 的使用者有100或更多連絡人。</span><span class="sxs-lookup"><span data-stu-id="38376-141">Less than 25% of users have 100 or more contacts.</span></span></p>
<p><span data-ttu-id="38376-142">使用公用雲端連線的使用者的80連絡人平均值。</span><span class="sxs-lookup"><span data-stu-id="38376-142">Average of 80 contacts for users with public cloud connectivity.</span></span> <span data-ttu-id="38376-143">下列使用者：</span><span class="sxs-lookup"><span data-stu-id="38376-143">Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="38376-144">50% 的連絡人都在組織內。</span><span class="sxs-lookup"><span data-stu-id="38376-144">50% of the contacts are within the organization.</span></span> <span data-ttu-id="38376-145">這些使用者的10% 是遠端使用者，從防火牆外部連線。</span><span class="sxs-lookup"><span data-stu-id="38376-145">10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="38376-146">40% 的連絡人是公用雲端使用者（例如 AOL、Yahoo！、MSN 或 Google 交談的使用者）。</span><span class="sxs-lookup"><span data-stu-id="38376-146">40% of the contacts are public cloud users (such as users of AOL, Yahoo!, MSN, or Google Talk).</span></span></p></li>
<li><p><span data-ttu-id="38376-147">連絡人的10% 是來自聯盟合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="38376-147">10% of the contacts are from federated partners.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="38376-148">從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。</span><span class="sxs-lookup"><span data-stu-id="38376-148">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="38376-149">擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="38376-149">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="38376-150">信使，直到服務關閉日期為止。</span><span class="sxs-lookup"><span data-stu-id="38376-150">Messenger until the service shut down date.</span></span> <span data-ttu-id="38376-151">AOL 和 Yahoo！的存留期結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="38376-151">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="38376-152">已公佈。</span><span class="sxs-lookup"><span data-stu-id="38376-152">has been announced.</span></span> <span data-ttu-id="38376-153">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</span><span class="sxs-lookup"><span data-stu-id="38376-153">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="38376-154">PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="38376-154">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="38376-155">名單.</span><span class="sxs-lookup"><span data-stu-id="38376-155">Messenger.</span></span> <span data-ttu-id="38376-156">Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</span><span class="sxs-lookup"><span data-stu-id="38376-156">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="38376-157">Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。</span><span class="sxs-lookup"><span data-stu-id="38376-157">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="38376-158">與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="38376-158">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="38376-159">您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="38376-159">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
</ul>
<p><span data-ttu-id="38376-160">不含公用雲端連線的使用者的50連絡人平均值。</span><span class="sxs-lookup"><span data-stu-id="38376-160">Average of 50 contacts for users without public cloud connectivity.</span></span> <span data-ttu-id="38376-161">下列使用者：</span><span class="sxs-lookup"><span data-stu-id="38376-161">Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="38376-162">80% 的連絡人都在組織內。</span><span class="sxs-lookup"><span data-stu-id="38376-162">80% of the contacts are within the organization.</span></span> <span data-ttu-id="38376-163">這些使用者的10% 是遠端使用者，從防火牆外部連線。</span><span class="sxs-lookup"><span data-stu-id="38376-163">10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="38376-164">此連絡人的20% 是來自聯盟合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="38376-164">20% of the contacts are from federated partners.</span></span></p>
<p><span data-ttu-id="38376-165">每個使用者的連絡人清單中都有一個通訊群組。</span><span class="sxs-lookup"><span data-stu-id="38376-165">Each user has 1 distribution group in their contact list.</span></span> <span data-ttu-id="38376-166">針對效能測試，我們假設通訊群組總是展開。</span><span class="sxs-lookup"><span data-stu-id="38376-166">For performance testing, we assume that distribution groups are always expanded.</span></span></p></li>
</ul>
<p><span data-ttu-id="38376-167">使用者的連絡人的25% 使用 XMPP。</span><span class="sxs-lookup"><span data-stu-id="38376-167">25% of a user’s contacts use XMPP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38376-168">會話時間</span><span class="sxs-lookup"><span data-stu-id="38376-168">Session time</span></span></p></td>
<td><p><span data-ttu-id="38376-169">一般的使用者登入會話持續12小時。</span><span class="sxs-lookup"><span data-stu-id="38376-169">The average user logon session lasts 12 hours.</span></span> <span data-ttu-id="38376-170">所有使用者都會在會話開始的120分鐘內登入。</span><span class="sxs-lookup"><span data-stu-id="38376-170">All users log on within 120 minutes of the start of the session.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="im-and-presence-user-model"></a><span data-ttu-id="38376-171">IM 和目前狀態使用者模型</span><span class="sxs-lookup"><span data-stu-id="38376-171">IM and Presence User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38376-172">類別</span><span class="sxs-lookup"><span data-stu-id="38376-172">Category</span></span></th>
<th><span data-ttu-id="38376-173">描述</span><span class="sxs-lookup"><span data-stu-id="38376-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38376-174">對等 IM 會話</span><span class="sxs-lookup"><span data-stu-id="38376-174">Peer-to-peer IM sessions</span></span></p></td>
<td><p><span data-ttu-id="38376-175">每個使用者每天平均六個對等 IM 會話。</span><span class="sxs-lookup"><span data-stu-id="38376-175">Each user averages six peer-to-peer IM sessions per day.</span></span></p>
<p><span data-ttu-id="38376-176">每個會話10個即時消息。</span><span class="sxs-lookup"><span data-stu-id="38376-176">10 instant messages per session.</span></span></p>
<p><span data-ttu-id="38376-177">每封郵件都是由兩個 SIP 資訊訊息和2個 SIP 200 的 [確定] 訊息（例如&lt;"&gt; Name is Name" 之類的狀態指標）來相符。</span><span class="sxs-lookup"><span data-stu-id="38376-177">Each message is matched by two SIP INFO messages and 2 SIP 200 OK messages (for the status indicators such as “&lt;Name&gt; is Typing”)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38376-178">目前狀態輪詢</span><span class="sxs-lookup"><span data-stu-id="38376-178">Presence polling</span></span></p></td>
<td><p><span data-ttu-id="38376-179">總的來說，我們假設每個使用者每小時的目前狀態輪詢平均為60輪詢。</span><span class="sxs-lookup"><span data-stu-id="38376-179">Overall, we assume presence polling at an average of 60 polls per user per hour.</span></span> <span data-ttu-id="38376-180">針對每個使用者，假設平均值：</span><span class="sxs-lookup"><span data-stu-id="38376-180">For each user, assume an average of:</span></span></p>
<ul>
<li><p><span data-ttu-id="38376-181">在使用者的 [組織] 索引標籤（但不是 [連絡人] 清單）中，每一天輪詢一天。</span><span class="sxs-lookup"><span data-stu-id="38376-181">One poll per day of the presence of users in the user’s organization tab (but not Contacts list).</span></span> <span data-ttu-id="38376-182">在使用者的 [組織] 索引標籤中，第15位使用者的非連絡人平均數。</span><span class="sxs-lookup"><span data-stu-id="38376-182">Average number of non-contacts in the user’s organization tab is 15 users.</span></span> <span data-ttu-id="38376-183">每日兩個連絡人卡片查看作業。</span><span class="sxs-lookup"><span data-stu-id="38376-183">Two contact card viewing operations per day.</span></span></p></li>
<li><p><span data-ttu-id="38376-184">每次使用者按一下另一個使用者以開始交談時，每小時估計一次，即會有一個目前狀態輪詢。</span><span class="sxs-lookup"><span data-stu-id="38376-184">One presence poll every time the user clicks another user to start a conversation, estimated at once per hour.</span></span></p></li>
<li><p><span data-ttu-id="38376-185">每小時六個使用者搜尋。</span><span class="sxs-lookup"><span data-stu-id="38376-185">Six user searches per hour.</span></span> <span data-ttu-id="38376-186">每次執行搜尋時，都會針對搜尋結果清單中的每個人傳送批次投票。</span><span class="sxs-lookup"><span data-stu-id="38376-186">Every time a search is performed, a batch poll is sent for everyone in the search result list.</span></span> <span data-ttu-id="38376-187">我們假設搜尋結果的平均大小為20。</span><span class="sxs-lookup"><span data-stu-id="38376-187">We assume the average size of search results is 20.</span></span> <span data-ttu-id="38376-188">如果搜尋結果停留在螢幕上，批次輪詢會每隔5分鐘更新一次;我們假設每小時會有兩個此類更新。</span><span class="sxs-lookup"><span data-stu-id="38376-188">If the search results stay on screen, the batch poll is refreshed every 5 minutes; we assume that there will be two such refreshes per hour.</span></span></p></li>
<li><p><span data-ttu-id="38376-189">當使用者在 Outlook 中開啟或預覽電子郵件時，會在電子郵件的 [收件者：] 和 [抄送：] 欄位中的目前狀態，在每個電子郵件上估計5封電子郵件，以及每個電子郵件的四個使用者。</span><span class="sxs-lookup"><span data-stu-id="38376-189">When the user opens or previews an email in Outlook, a poll of the presence of users in the To: and CC: fields of the email, estimated at five emails per hour and four users per email.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38376-190">目前狀態訂閱</span><span class="sxs-lookup"><span data-stu-id="38376-190">Presence subscriptions</span></span></p></td>
<td><p><span data-ttu-id="38376-191">當使用者將另一個使用者新增為連絡人時，第一個使用者會<em>訂閱</em>五個有關第二個使用者的資訊類別。</span><span class="sxs-lookup"><span data-stu-id="38376-191">When one user adds another as a contact, the first user is <em>subscribing</em> to five categories of information about the second user.</span></span> <span data-ttu-id="38376-192">這些資訊類別的更新會自動傳送給第一個使用者。</span><span class="sxs-lookup"><span data-stu-id="38376-192">Updates of these categories of information are automatically sent to the first user.</span></span></p>
<p><span data-ttu-id="38376-193">針對每個用戶端，會傳送單一批次訂閱要求，以取得平均40連絡人的目前狀態，還有額外的40對話方塊來取得同盟連絡人的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="38376-193">For each client, a single batch subscription request is sent to obtain the presence state of an average of 40 contacts, with an additional 40 dialogs to obtain presence for federated contacts.</span></span></p>
<p><span data-ttu-id="38376-194">展開的通訊群組成員的「目前狀態」是透過持久的目前狀態訂閱（不是輪詢）找到，且每個使用者每兩個小時都是以1個延伸的方式進行。</span><span class="sxs-lookup"><span data-stu-id="38376-194">Presence for members of an expanded distribution group is found through persistent presence subscriptions, not polling, and is modeled as 1 expansion per user for each 2 hours.</span></span></p>
<p><span data-ttu-id="38376-195"><em>較短的訂閱</em>會在使用者登入時發生，所有使用者的連絡人都有一個批次訂閱，然後使用者就會立即登入。</span><span class="sxs-lookup"><span data-stu-id="38376-195"><em>Short subscriptions</em> happen when a user logs in, there is a batch subscription for all the user’s contacts, and then the user soon logs off.</span></span> <span data-ttu-id="38376-196">我們假設每個使用者的每小時只有6個短訂閱，每個訂閱的持續時間為10分鐘。</span><span class="sxs-lookup"><span data-stu-id="38376-196">We assume 6 short subscriptions per user per hour, where each subscription lasts 10 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38376-197">目前狀態發佈</span><span class="sxs-lookup"><span data-stu-id="38376-197">Presence Publication</span></span></p></td>
<td><p><span data-ttu-id="38376-198">[目前狀態] 是以每個使用者每小時4個發佈的平均發佈，每個使用者最多每小時6份。</span><span class="sxs-lookup"><span data-stu-id="38376-198">Presence state is published at an average of 4 publications per user per hour, with a maximum 6 per user per hour.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38376-199">目前狀態檔案大小</span><span class="sxs-lookup"><span data-stu-id="38376-199">Presence Document Size</span></span></p></td>
<td><p><span data-ttu-id="38376-200">完整目前狀態檔的平均大小假設是4K，且最大25K。</span><span class="sxs-lookup"><span data-stu-id="38376-200">The average size of a complete presence document is assumed to be 4K, with a maximum of 25K.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="38376-201">下表說明通訊錄使用的使用者模型。</span><span class="sxs-lookup"><span data-stu-id="38376-201">The following table describes the user model for address book use.</span></span>

### <a name="address-book-usage-user-model"></a><span data-ttu-id="38376-202">[通訊錄使用方式] 使用者模型</span><span class="sxs-lookup"><span data-stu-id="38376-202">Address Book Usage User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38376-203">通訊錄搜尋模式</span><span class="sxs-lookup"><span data-stu-id="38376-203">Address Book search mode</span></span></th>
<th><span data-ttu-id="38376-204">用法</span><span class="sxs-lookup"><span data-stu-id="38376-204">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38376-205">[通訊錄網頁查詢] （由通訊錄網頁查詢服務所執行的所有查詢）</span><span class="sxs-lookup"><span data-stu-id="38376-205">Address Book Web Query only (all queries performed by Address Book Web Query service)</span></span></p></td>
<td><p><span data-ttu-id="38376-206">每位使用者一天四個首碼查詢。</span><span class="sxs-lookup"><span data-stu-id="38376-206">Four prefix queries per user per day.</span></span></p>
<p><span data-ttu-id="38376-207">60每位使用者每天精確搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="38376-207">60 exact search queries per user per day.</span></span> <span data-ttu-id="38376-208">其中的40% 是批次，平均每個查詢20個連絡人。</span><span class="sxs-lookup"><span data-stu-id="38376-208">40% of those are batched, with an average of 20 contacts per query.</span></span> <span data-ttu-id="38376-209">其他60% 的查詢是針對單一連絡人。</span><span class="sxs-lookup"><span data-stu-id="38376-209">The other 60% of the queries are for a single contact.</span></span></p>
<p><span data-ttu-id="38376-210">每個使用者每天有25個相片查詢。</span><span class="sxs-lookup"><span data-stu-id="38376-210">25 photo queries per user per day.</span></span> <span data-ttu-id="38376-211">24是針對單一相片，另一個是平均為20個連絡人的批次查詢。</span><span class="sxs-lookup"><span data-stu-id="38376-211">24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="38376-212">每個使用者每天一個組織搜尋查詢的總數。</span><span class="sxs-lookup"><span data-stu-id="38376-212">One total organization search query per user per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38376-213">混合模式，使用通訊錄檔案和網路查詢。</span><span class="sxs-lookup"><span data-stu-id="38376-213">Mixed mode, both address book file and web queries used.</span></span> <span data-ttu-id="38376-214">這是預設模式。</span><span class="sxs-lookup"><span data-stu-id="38376-214">This is the default mode.</span></span></p></td>
<td><p><span data-ttu-id="38376-215">只有兩種類型的查詢會移至網路、相片與整個組織的搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="38376-215">Only two types of queries go to the network, the photo and total organizational search queries.</span></span></p>
<p><span data-ttu-id="38376-216">每個使用者每天有25個相片查詢。</span><span class="sxs-lookup"><span data-stu-id="38376-216">25 photo queries per user per day.</span></span> <span data-ttu-id="38376-217">24是針對單一相片，另一個是平均為20個連絡人的批次查詢。</span><span class="sxs-lookup"><span data-stu-id="38376-217">24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="38376-218">每個使用者每天一個組織搜尋查詢的總數。</span><span class="sxs-lookup"><span data-stu-id="38376-218">One total organization search query per user per day.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="38376-219">下表說明會議模型。</span><span class="sxs-lookup"><span data-stu-id="38376-219">The following table describes the conferencing model.</span></span>

### <a name="conferencing-model"></a><span data-ttu-id="38376-220">會議模型</span><span class="sxs-lookup"><span data-stu-id="38376-220">Conferencing Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38376-221">類別</span><span class="sxs-lookup"><span data-stu-id="38376-221">Category</span></span></th>
<th><span data-ttu-id="38376-222">描述</span><span class="sxs-lookup"><span data-stu-id="38376-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38376-223">排定的會議&quot;與 [&quot;立即開會] 會議</span><span class="sxs-lookup"><span data-stu-id="38376-223">Scheduled meetings versus &quot;Meet now&quot; meetings</span></span></p></td>
<td><p><span data-ttu-id="38376-224">已排程60%，40% 未排程。</span><span class="sxs-lookup"><span data-stu-id="38376-224">60% scheduled, 40% unscheduled.</span></span></p>
<p><span data-ttu-id="38376-225">在已排定的會議中，我們假設80% 是指派的會議，這是週期性會議的出現次數;10% 是一次開啟的會議;8% 是一次性的匿名會議，2% 是一次性關閉的會議。</span><span class="sxs-lookup"><span data-stu-id="38376-225">Of the scheduled meetings, we assume that 80% are assigned conferences, which are occurences of recurring conferences; 10% are one-time open meetings; 8% are one-time anonymous meetings, and 2% are one-time closed meetings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38376-226">會議用戶端發佈</span><span class="sxs-lookup"><span data-stu-id="38376-226">Conferencing client distribution</span></span></p></td>
<td><p><span data-ttu-id="38376-227">針對排程的會議：</span><span class="sxs-lookup"><span data-stu-id="38376-227">For scheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="38376-228">65% 的會議使用者使用 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="38376-228">65% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="38376-229">5% 的會議使用者使用 Microsoft Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="38376-229">5% of conferencing users use Microsoft Lync Web App.</span></span></p></li>
<li><p><span data-ttu-id="38376-230">30% 的會議使用者使用較舊的用戶端，包括 Microsoft Lync 2010、Office Communicator 2007 R2、Office Communicator 2007，以及 Microsoft Office Communicator Web Access （2007發行版本）。</span><span class="sxs-lookup"><span data-stu-id="38376-230">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul>
<p><span data-ttu-id="38376-231">針對未排程的會議：</span><span class="sxs-lookup"><span data-stu-id="38376-231">For unscheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="38376-232">70% 的會議使用者使用 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="38376-232">70% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="38376-233">30% 的會議使用者使用較舊的用戶端，包括 Microsoft Lync 2010、Office Communicator 2007 R2、Office Communicator 2007，以及 Microsoft Office Communicator Web Access （2007發行版本）。</span><span class="sxs-lookup"><span data-stu-id="38376-233">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38376-234">會議併發性</span><span class="sxs-lookup"><span data-stu-id="38376-234">Meeting concurrency</span></span></p></td>
<td><p><span data-ttu-id="38376-235">在工作時間內，5% 的使用者就會參與會議。</span><span class="sxs-lookup"><span data-stu-id="38376-235">5% of users will be in conferences during working hours.</span></span> <span data-ttu-id="38376-236">因此，在 80000-使用者池中，4000許多使用者可能都會在會議中進行任何一次的會議。</span><span class="sxs-lookup"><span data-stu-id="38376-236">Thus, in an 80,000-user pool, as many as 4,000 users might be in conferences at any one time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38376-237">會議音訊發佈</span><span class="sxs-lookup"><span data-stu-id="38376-237">Meeting audio distribution</span></span></p></td>
<td><p><span data-ttu-id="38376-238">40% 混合式 VoIP 音訊和撥入式會議，且 VoIP 使用者的3:1 比率為撥入使用者。</span><span class="sxs-lookup"><span data-stu-id="38376-238">40% mixed VoIP audio and dial-in conferencing, with a 3:1 ratio of VoIP users to dial-in users.</span></span></p>
<p><span data-ttu-id="38376-239">僅35% 的 VoIP 音訊。</span><span class="sxs-lookup"><span data-stu-id="38376-239">35% VoIP audio only.</span></span></p>
<p><span data-ttu-id="38376-240">只有15% 的電話撥入式會議音訊。</span><span class="sxs-lookup"><span data-stu-id="38376-240">15% dial-in conferencing audio only.</span></span></p>
<p><span data-ttu-id="38376-241">10% 無音訊（僅限 IM 會議，平均每位使用者傳送五個郵件）。</span><span class="sxs-lookup"><span data-stu-id="38376-241">10% no audio (IM-only conferences, with an average of five messages sent per user).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38376-242">適用于會議的媒體組合</span><span class="sxs-lookup"><span data-stu-id="38376-242">Media mix for conferences</span></span></p></td>
<td><p><span data-ttu-id="38376-243">75% 的會議是網路會議，其中包含音訊加上其他一些共同作業形式。</span><span class="sxs-lookup"><span data-stu-id="38376-243">75% of conferences are web conferences, which include audio plus some other collaboration modalities.</span></span></p>
<p><span data-ttu-id="38376-244">針對這些會議，其他共同作業方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="38376-244">For these conferences, the other collaboration methods are as follows:</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="38376-245">因為一個會議可以有多個共同作業方法，所以這些數位會加總超過100%。</span><span class="sxs-lookup"><span data-stu-id="38376-245">These numbers add up to more than 100% because one conference can have multiple collaboration methods.</span></span>


</div>
<ul>
<li><p><span data-ttu-id="38376-246">50% 新增應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="38376-246">50% add application sharing.</span></span> <span data-ttu-id="38376-247">我們假設一位使用者以每秒 1.1 MB 的峰值傳送資料。</span><span class="sxs-lookup"><span data-stu-id="38376-247">We assume one users sends data at a peak of 1.1 MB per second.</span></span></p></li>
<li><p><span data-ttu-id="38376-248">50% 新增立即訊息（每位使用者平均為2封郵件）。</span><span class="sxs-lookup"><span data-stu-id="38376-248">50% add instant messaging (with an average of 2 messages per user).</span></span></p></li>
<li><p><span data-ttu-id="38376-249">20% 新增資料共同作業，包括 PowerPoint 或白板，這兩個是每個會議所提供的兩個 PowerPoint 檔案，一般的 PowerPoint 檔案大小為 10 MB （沒有內嵌影片）或 30 MB （內嵌的影片）。</span><span class="sxs-lookup"><span data-stu-id="38376-249">20% add data collaboration, including PowerPoint or whiteboard In these, an average of 2 PowerPoint files presented per conference, with an average PowerPoint file size of 10 MB (without embedded video) or 30 MB (with embedded video).</span></span> <span data-ttu-id="38376-250">每個白板的平均20個批註。</span><span class="sxs-lookup"><span data-stu-id="38376-250">Average of 20 annotations per whiteboard.</span></span></p></li>
<li><p><span data-ttu-id="38376-251">20% [新增影片]。</span><span class="sxs-lookup"><span data-stu-id="38376-251">20% add video.</span></span> <span data-ttu-id="38376-252">在這些使用者中，70% 是針對多畫面影片啟用的會議，每個使用者都會收到2-3 視頻串流。</span><span class="sxs-lookup"><span data-stu-id="38376-252">Of these users, 70% are in conferences enabled for multiview video, where each user receives 2-3 video streams.</span></span></p></li>
<li><p><span data-ttu-id="38376-253">15% 新增共用筆記。</span><span class="sxs-lookup"><span data-stu-id="38376-253">15% add shared notes.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38376-254">會議參與者發佈</span><span class="sxs-lookup"><span data-stu-id="38376-254">Meeting participant distribution</span></span></p></td>
<td><p><span data-ttu-id="38376-255">50% 內部、經過驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="38376-255">50% internal, authenticated users.</span></span></p>
<p><span data-ttu-id="38376-256">25% 的遠端存取，經過驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="38376-256">25% remote access, authenticated users.</span></span></p>
<p><span data-ttu-id="38376-257">15% 匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="38376-257">15% anonymous users.</span></span></p>
<p><span data-ttu-id="38376-258">10% 聯盟使用者。</span><span class="sxs-lookup"><span data-stu-id="38376-258">10% federated users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38376-259">會議加入發佈</span><span class="sxs-lookup"><span data-stu-id="38376-259">Meeting join distribution</span></span></p></td>
<td><p><span data-ttu-id="38376-260">使用者會在前5分鐘內模擬為加入會議。</span><span class="sxs-lookup"><span data-stu-id="38376-260">Users are simulated as joining the meeting within the first 5 minutes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="38376-261">在一般的前端池中，Lync Server 2013 的最大支援會議大小為250個使用者。</span><span class="sxs-lookup"><span data-stu-id="38376-261">In regular Front End pools, Lync Server 2013 has a maximum supported meeting size of 250 users.</span></span> <span data-ttu-id="38376-262">每個池都可以一次主持 1 250-使用者會議。</span><span class="sxs-lookup"><span data-stu-id="38376-262">Each pool can host one 250-user meeting at a time.</span></span> <span data-ttu-id="38376-263">在進行這個大型會議時，該池子也可以主持其他較小的會議。</span><span class="sxs-lookup"><span data-stu-id="38376-263">While this large meeting is occurring, the pool can also host other smaller conferences.</span></span> <span data-ttu-id="38376-264">此外，您可以設定專用的池子來主持這些會議，以支援最多1000個使用者的會議。</span><span class="sxs-lookup"><span data-stu-id="38376-264">Additionally, you can support meetings of up to 1000 users by setting up a dedicated pool to host these meetings.</span></span> <span data-ttu-id="38376-265">如需詳細資訊，請參閱[Lync Server 2013 中的大型會議支援](lync-server-2013-support-for-large-meetings.md)。</span><span class="sxs-lookup"><span data-stu-id="38376-265">For details, see [Support for large meetings in Lync Server 2013](lync-server-2013-support-for-large-meetings.md).</span></span>

<span data-ttu-id="38376-266">會議的類比方式如下：</span><span class="sxs-lookup"><span data-stu-id="38376-266">Conferences were simulated as follows:</span></span>

  - <span data-ttu-id="38376-267">85% 的會議有四個參與者。</span><span class="sxs-lookup"><span data-stu-id="38376-267">85% of conferences had four participants.</span></span>

  - <span data-ttu-id="38376-268">10% 的會議有六個參與者。</span><span class="sxs-lookup"><span data-stu-id="38376-268">10% of conferences had six participants.</span></span>

  - <span data-ttu-id="38376-269">5% 的會議有11個參與者。</span><span class="sxs-lookup"><span data-stu-id="38376-269">5% of conferences had 11 participants.</span></span>

  - <span data-ttu-id="38376-270">一個大型的250使用者會議。</span><span class="sxs-lookup"><span data-stu-id="38376-270">One large conference of 250 users.</span></span>

<span data-ttu-id="38376-271">下表提供涉及撥入使用者之會議之使用者模型的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="38376-271">The following table provides details about the user model for conferences involving dial-in users.</span></span>

### <a name="dial-in-conferencing-user-model"></a><span data-ttu-id="38376-272">電話撥入式會議使用者模型</span><span class="sxs-lookup"><span data-stu-id="38376-272">Dial-In Conferencing User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38376-273">類別</span><span class="sxs-lookup"><span data-stu-id="38376-273">Category</span></span></th>
<th><span data-ttu-id="38376-274">描述</span><span class="sxs-lookup"><span data-stu-id="38376-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38376-275">已驗證/匿名</span><span class="sxs-lookup"><span data-stu-id="38376-275">Authenticated/anonymous</span></span></p></td>
<td><p><span data-ttu-id="38376-276">70% 的呼叫者以匿名方式加入，且系統會提示您輸入錄製的名稱。</span><span class="sxs-lookup"><span data-stu-id="38376-276">70% of callers join as anonymous and are prompted for a recorded name.</span></span> <span data-ttu-id="38376-277">30% 以已驗證的使用者身分加入。</span><span class="sxs-lookup"><span data-stu-id="38376-277">30% join as authenticated users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38376-278">保留通話持續時間和音樂</span><span class="sxs-lookup"><span data-stu-id="38376-278">Call duration and music on hold</span></span></p></td>
<td><p><span data-ttu-id="38376-279">保留期間不含音樂的平均通話持續時間：50秒。</span><span class="sxs-lookup"><span data-stu-id="38376-279">Average call duration without music on hold: 50 seconds.</span></span></p>
<p><span data-ttu-id="38376-280">50% 的撥入使用者會聽到 [暫停音樂]，平均為5分鐘。</span><span class="sxs-lookup"><span data-stu-id="38376-280">50% of call-in users hear music on hold, for an average of 5 minutes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38376-281">雙音調 multifrequency （DTMF）</span><span class="sxs-lookup"><span data-stu-id="38376-281">Dual-tone multifrequency (DTMF)</span></span></p></td>
<td><p><span data-ttu-id="38376-282">在撥入的會議中，15% 只有手機領導人。</span><span class="sxs-lookup"><span data-stu-id="38376-282">15% of conferences that are dial-in only have phone leaders.</span></span> <span data-ttu-id="38376-283">包含撥入使用者的混合會議中有10% 的混合會議也有電話領導人。</span><span class="sxs-lookup"><span data-stu-id="38376-283">10% of mixed conferences that include dial-in users also have phone leaders.</span></span></p>
<p><span data-ttu-id="38376-284">20% 的手機領袖會針對每個會議使用2個 DTMF 命令。</span><span class="sxs-lookup"><span data-stu-id="38376-284">20% of phone leaders use 2 DTMF commands per conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38376-285">宣告語言</span><span class="sxs-lookup"><span data-stu-id="38376-285">Announcement languages</span></span></p></td>
<td><p><span data-ttu-id="38376-286">模擬使用英文做為宣告語言。</span><span class="sxs-lookup"><span data-stu-id="38376-286">Simulations use English as the announcement language.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="38376-287">下表提供有關 [會議大廳] 使用者模型的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="38376-287">The following table provides details about the user model for conference lobbies.</span></span>

### <a name="conference-lobby-user-model"></a><span data-ttu-id="38376-288">會議廳使用者模型</span><span class="sxs-lookup"><span data-stu-id="38376-288">Conference Lobby User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38376-289">類別</span><span class="sxs-lookup"><span data-stu-id="38376-289">Category</span></span></th>
<th><span data-ttu-id="38376-290">描述</span><span class="sxs-lookup"><span data-stu-id="38376-290">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38376-291">大廳中的使用者數目</span><span class="sxs-lookup"><span data-stu-id="38376-291">Number of users in lobby</span></span></p></td>
<td><p><span data-ttu-id="38376-292">5% 的撥入使用者會透過大廳進行，而25% 的其他使用者則會透過大廳進行</span><span class="sxs-lookup"><span data-stu-id="38376-292">5% of dial-in users go through the lobby, and 25% of other users go through the lobby</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38376-293">從大廳 Admitting</span><span class="sxs-lookup"><span data-stu-id="38376-293">Admitting from lobby</span></span></p></td>
<td><p><span data-ttu-id="38376-294">在模擬中，所有使用者都是在用戶端超時前由簡報者承認。</span><span class="sxs-lookup"><span data-stu-id="38376-294">In simulations, all users were admitted by the presenter before client timeout.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="38376-295">下表說明其他點對點工作階段的使用者模型。</span><span class="sxs-lookup"><span data-stu-id="38376-295">The following table describes the user model for other peer-to-peer sessions.</span></span>

### <a name="peer-to-peer-sessions-user-model"></a><span data-ttu-id="38376-296">點對點工作階段使用者模型</span><span class="sxs-lookup"><span data-stu-id="38376-296">Peer-to-Peer Sessions User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38376-297">類別</span><span class="sxs-lookup"><span data-stu-id="38376-297">Category</span></span></th>
<th><span data-ttu-id="38376-298">描述</span><span class="sxs-lookup"><span data-stu-id="38376-298">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38376-299">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="38376-299">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="38376-300">每個使用者每個月都參與5對等應用程式共用會話，平均每日0.25 個會話。</span><span class="sxs-lookup"><span data-stu-id="38376-300">Each user participates in 5 peer-to-peer application sharing sessions per month, for an average of 0.25 sessions per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38376-301">檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="38376-301">File transfer</span></span></p></td>
<td><p><span data-ttu-id="38376-302">每個使用者每個月都參與1對等檔案傳輸會話（作為 IM 會話的一部分），平均每日0.05 個會話。</span><span class="sxs-lookup"><span data-stu-id="38376-302">Each user participates in 1 peer-to-peer file transfer session per month (as part of an IM session), for an average of 0.05 sessions per day.</span></span> <span data-ttu-id="38376-303">傳輸的平均會話檔案大小為 1 MB。</span><span class="sxs-lookup"><span data-stu-id="38376-303">The average session file size transferred is 1 MB.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="38376-304">下表說明原則的使用者模型。</span><span class="sxs-lookup"><span data-stu-id="38376-304">The following table describes the user model for policies.</span></span>

### <a name="policies-user-model"></a><span data-ttu-id="38376-305">原則使用者模型</span><span class="sxs-lookup"><span data-stu-id="38376-305">Policies User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38376-306">類別</span><span class="sxs-lookup"><span data-stu-id="38376-306">Category</span></span></th>
<th><span data-ttu-id="38376-307">描述</span><span class="sxs-lookup"><span data-stu-id="38376-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38376-308">會議、目前狀態及歸檔原則</span><span class="sxs-lookup"><span data-stu-id="38376-308">Conferencing, Presence, and Archiving Policies</span></span></p></td>
<td><p><span data-ttu-id="38376-309">我們假設您有一個全域原則、10個標記會議原則、4個封存原則，以及10個標籤的目前狀態原則。</span><span class="sxs-lookup"><span data-stu-id="38376-309">We assume that there is one global policy, 10 tag conferencing policies, 4 Archiving policies, and 10 tag presence policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38376-310">語音原則</span><span class="sxs-lookup"><span data-stu-id="38376-310">Voice Policy</span></span></p></td>
<td><p><span data-ttu-id="38376-311">我們假設每個網站都有一個全域原則和2個標記原則。</span><span class="sxs-lookup"><span data-stu-id="38376-311">We assume that there is one global policy and 2 tag policies per site.</span></span> <span data-ttu-id="38376-312">100% 的網站有網站原則，30% 的使用者已指派每使用者原則。</span><span class="sxs-lookup"><span data-stu-id="38376-312">100% of sites have a site policy, and 30% of users have a per-user policy assigned.</span></span> <span data-ttu-id="38376-313">我們假設每個網站都有一個撥號方案，每個網站都有兩個路由。</span><span class="sxs-lookup"><span data-stu-id="38376-313">We assume one dial plan per site and two routes per site.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="busy-hour"></a><span data-ttu-id="38376-314">Busy 小時</span><span class="sxs-lookup"><span data-stu-id="38376-314">Busy Hour</span></span>

<span data-ttu-id="38376-315">對於點對點工作階段，峰值負載是使用繁忙時間的呼叫企圖（BHCA）來計算。</span><span class="sxs-lookup"><span data-stu-id="38376-315">For peer-to-peer sessions, peak load is calculated using busy hour call attempts (BHCA).</span></span> <span data-ttu-id="38376-316">這個語音產業字假設當天所有通話的50% 將在20% 的時間內完成。</span><span class="sxs-lookup"><span data-stu-id="38376-316">This voice industry term assumes that 50% of all calls for the day will be completed in 20% of the time.</span></span> <span data-ttu-id="38376-317">它是使用下列公式來計算：</span><span class="sxs-lookup"><span data-stu-id="38376-317">It is calculated using the following formula:</span></span>

`BHCA=(total calls * 0.5) / 1.6`

<span data-ttu-id="38376-318">在執行 VoIP 及其他點對點工作階段時，請在24小時內的每日至少1.6 小時負載中執行 VoIP 及其他點對點工作階段，以進行效能測試。</span><span class="sxs-lookup"><span data-stu-id="38376-318">Performance testing simulated busy hour by running VoIP and other peer-to-peer sessions at a busy hour load for at least 1.6 hours per day.</span></span>

<span data-ttu-id="38376-319">「會議峰值負載」假設所有會議的75% 是在4個小時的時間內完成。</span><span class="sxs-lookup"><span data-stu-id="38376-319">Conferencing peak load assumes that 75% of all conferences for an eight-hour day happen in 4 peak time hours.</span></span> <span data-ttu-id="38376-320">這些尖峰時間的平均會議負載是1.5。</span><span class="sxs-lookup"><span data-stu-id="38376-320">Those peak hours have 1.5 times the average conferencing load.</span></span>

</div>

<div>

## <a name="enterprise-voice-to-pstn-calls"></a><span data-ttu-id="38376-321">企業語音到 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="38376-321">Enterprise Voice to PSTN Calls</span></span>

<span data-ttu-id="38376-322">下列假設適用于企業語音通話：</span><span class="sxs-lookup"><span data-stu-id="38376-322">The following assumptions apply to Enterprise Voice calls:</span></span>

  - <span data-ttu-id="38376-323">50% 的使用者已啟用企業語音功能，而這些使用者的60% 已啟用 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="38376-323">50% of users are enabled for Enterprise Voice, and 60% of these users are enabled for PSTN calling.</span></span>

  - <span data-ttu-id="38376-324">每個啟用 PSTN 通話的使用者都會在繁忙時間內撥打4個 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="38376-324">Each of these users enabled for PSTN calling makes 4 PSTN calls during the busy hour.</span></span> <span data-ttu-id="38376-325">每個通話持續時間為3分鐘。</span><span class="sxs-lookup"><span data-stu-id="38376-325">Each call duration is 3 minutes.</span></span>

  - <span data-ttu-id="38376-326">這些 PSTN 語音通話的65% 使用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="38376-326">65% of these PSTN voice calls use media bypass.</span></span>

</div>

<div>

## <a name="mobility"></a><span data-ttu-id="38376-327">行動性</span><span class="sxs-lookup"><span data-stu-id="38376-327">Mobility</span></span>

<span data-ttu-id="38376-328">系統會假設已登錄使用者的40% 是啟用行動。</span><span class="sxs-lookup"><span data-stu-id="38376-328">40% of registered users are assumed to be enabled for Mobility.</span></span> <span data-ttu-id="38376-329">針對已啟用行動裝置的每位使用者，我們假設行動用戶端的活動會累加至該使用者的其他 MPOP 實例，除了會議互動以外，其行動用戶端只是另一個用戶端類型，可以用來參與會議。</span><span class="sxs-lookup"><span data-stu-id="38376-329">For each user that has mobility enabled, we assume that the activity of the mobile client is additive to that of the other MPOP instances for that user, with the exception of conferencing interactions, for which the mobility client is just another client type that can be used to participate in conferences.</span></span>

</div>

<div>

## <a name="persistent-chat"></a><span data-ttu-id="38376-330">常設聊天室</span><span class="sxs-lookup"><span data-stu-id="38376-330">Persistent Chat</span></span>

<span data-ttu-id="38376-331">我們假設有25% 的註冊使用者將參與持續聊天會話，且具有下列特性：</span><span class="sxs-lookup"><span data-stu-id="38376-331">We assume that 25% of registered users will be involved in Persistent chat sessions, with the following characteristics:</span></span>

  - <span data-ttu-id="38376-332">每位使用者1.5 聊天室的平均值</span><span class="sxs-lookup"><span data-stu-id="38376-332">An average of 1.5 chat rooms per user</span></span>

  - <span data-ttu-id="38376-333">每個聊天室會每小時產生12個輪詢要求，平均目標為10個使用者</span><span class="sxs-lookup"><span data-stu-id="38376-333">Each chat room results in 12 polling requests per hour, targeting an average of 10 users each</span></span>

</div>

<div>

## <a name="response-group-and-call-park"></a><span data-ttu-id="38376-334">回應群組和通話駐留</span><span class="sxs-lookup"><span data-stu-id="38376-334">Response Group and Call Park</span></span>

<span data-ttu-id="38376-335">我們假設已註冊的使用者0.15% 是屬於回應群組。</span><span class="sxs-lookup"><span data-stu-id="38376-335">We assume that 0.15% of registered users belong to response groups.</span></span> <span data-ttu-id="38376-336">我們假設0.02% 的已註冊使用者已在任何指定時間點停用通話。</span><span class="sxs-lookup"><span data-stu-id="38376-336">We assume that 0.02% of registered users have parked calls at any given point of time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


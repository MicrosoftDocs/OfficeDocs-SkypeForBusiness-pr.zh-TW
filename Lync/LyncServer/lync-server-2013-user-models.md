---
title: Lync Server 2013：使用者模型
description: Lync Server 2013：使用者模型。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 user models
ms:assetid: c551371c-d740-4372-bada-f0d713ec0d33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398811(v=OCS.15)
ms:contentKeyID: 49733811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15be3f4c002de6cfb9ade4f13d80aedb59d76a82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569759"
---
# <a name="user-models-in-lync-server-2013"></a><span data-ttu-id="cf7c1-103">Lync Server 2013 中的使用者模型</span><span class="sxs-lookup"><span data-stu-id="cf7c1-103">User models in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf7c1-104">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="cf7c1-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="cf7c1-105">本文所述的使用者模型為 [使用使用者模型的 Lync Server 2013 容量規劃](lync-server-2013-capacity-planning-using-the-user-models.md)中所述的容量規劃測量和建議提供基礎。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-105">The user models described here provide the basis for the capacity planning measurements and recommendations described in [Capacity planning for Lync Server 2013 using the user models](lync-server-2013-capacity-planning-using-the-user-models.md).</span></span>

<div>

## <a name="lync-server-2013-user-models"></a><span data-ttu-id="cf7c1-106">Lync Server 2013 使用者模型</span><span class="sxs-lookup"><span data-stu-id="cf7c1-106">Lync Server 2013 User Models</span></span>

<span data-ttu-id="cf7c1-107">下表說明 Lync Server 2013 的註冊、連絡人、立即訊息 (IM) 及顯示狀態的使用者模型。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-107">The following table describes the user model for registration, contacts, instant messaging (IM), and presence for Lync Server 2013.</span></span>

### <a name="environment-and-registration-user-model"></a><span data-ttu-id="cf7c1-108">環境和註冊使用者模型</span><span class="sxs-lookup"><span data-stu-id="cf7c1-108">Environment and Registration User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf7c1-109">類別</span><span class="sxs-lookup"><span data-stu-id="cf7c1-109">Category</span></span></th>
<th><span data-ttu-id="cf7c1-110">描述</span><span class="sxs-lookup"><span data-stu-id="cf7c1-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf7c1-111">部署規模及分配</span><span class="sxs-lookup"><span data-stu-id="cf7c1-111">Deployment size and distribution</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-112">我們會使用三個中央網站來建立大型部署模型，每個網站各有一個前端集區。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-112">We model a large deployment with three central sites, with one Front End pool per site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf7c1-113">Active Directory 使用者的百分比</span><span class="sxs-lookup"><span data-stu-id="cf7c1-113">Percentage of Active Directory users</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-114">我們假設組織中所有 Active Directory 使用者的70% 皆已啟用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-114">We assume that 70% of all Active Directory users in the organization are enabled for Lync Server.</span></span> <span data-ttu-id="cf7c1-115">80% 的已啟用使用者每天會登入 Lync Server (80% concurrency) 。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-115">80% of those enabled users are logged on to Lync Server each day (80% concurrency).</span></span> <span data-ttu-id="cf7c1-116">並行使用者是此區段其餘部分之數位的基礎。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-116">The concurrent users are the basis for the numbers in the rest of this section.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf7c1-117">Active Directory 變更</span><span class="sxs-lookup"><span data-stu-id="cf7c1-117">Active Directory changes</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-118">我們假設每週在 Active Directory 中為 Lync 建立和啟用使用者總數的0.5%，且每週會從 Active Directory 和 Lync 停用總使用者的0.5%。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-118">We assume that 0.5% of total users are created and enabled for Lync in Active Directory each week, and that 0.5% of total users are disabled from Active Directory and from Lync each week.</span></span> <span data-ttu-id="cf7c1-119">5% 的使用者每週至少有一個 Active Directory 屬性已變更。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-119">5% of users have at least one Active Directory attribute changed each week.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf7c1-120">Active Directory 通訊群組</span><span class="sxs-lookup"><span data-stu-id="cf7c1-120">Active Directory distribution groups</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-121">我們假設組織中的 Active Directory 通訊群組數目等於 Active Directory 中所有使用者數目的三倍。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-121">We assume that the number of Active Directory distribution groups in the organization is equal to three times the number of all users in Active Directory.</span></span> <span data-ttu-id="cf7c1-122">通訊群組具有下列大小：</span><span class="sxs-lookup"><span data-stu-id="cf7c1-122">The distribution groups have the following sizes:</span></span></p>
<ul>
<li><p><span data-ttu-id="cf7c1-123">64% 具有2-30 使用者</span><span class="sxs-lookup"><span data-stu-id="cf7c1-123">64% have 2-30 users</span></span></p></li>
<li><p><span data-ttu-id="cf7c1-124">13% 具有31-50 使用者</span><span class="sxs-lookup"><span data-stu-id="cf7c1-124">13% have 31-50 users</span></span></p></li>
<li><p><span data-ttu-id="cf7c1-125">10% 具有51-100 使用者</span><span class="sxs-lookup"><span data-stu-id="cf7c1-125">10% have 51-100 users</span></span></p></li>
<li><p><span data-ttu-id="cf7c1-126">13% 具有101-500 使用者</span><span class="sxs-lookup"><span data-stu-id="cf7c1-126">13% have 101-500 users</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf7c1-127">) 使用者 VoIP 的語音 over IP (</span><span class="sxs-lookup"><span data-stu-id="cf7c1-127">Voice over IP (VoIP) users</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-128">60% 的 Lync Server 使用者已啟用整合通訊 (UC)  (也就是說，其電話號碼會歸 Lync Server) 所有。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-128">60% of Lync Server users are enabled for unified communications (UC) (that is, their phone numbers are owned by Lync Server).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf7c1-129">已註冊的用戶端分配</span><span class="sxs-lookup"><span data-stu-id="cf7c1-129">Registered client distribution</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-130">65% 的用戶端執行 Lync 2013 軟體，包括 Lync 和 Lync Phone Edition。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-130">65% of clients run Lync 2013 software, including Lync and Lync Phone Edition.</span></span></p>
<p><span data-ttu-id="cf7c1-131">30% 的用戶端執行先前版本的 Lync 用戶端軟體。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-131">30% of clients running client software from a previous version of Lync.</span></span></p>
<p><span data-ttu-id="cf7c1-132">使用 Lync Web App 的用戶端人數為5%。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-132">5% of clients using Lync Web App.</span></span></p>
<p><span data-ttu-id="cf7c1-133">如果已啟用行動性，我們會假設40% 的使用者正在與其他先前提及的註冊用戶端選項一起同時使用行動。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-133">If mobility is enabled, we assume that 40% of users are using mobility concurrently with the other previously cited registered client options.</span></span> <span data-ttu-id="cf7c1-134">在此情況下，用戶端多重顯示點 (MPOP) 比率為1：1.9。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-134">In this case the client multiple point of presence (MPOP) ratio is 1:1.9.</span></span> <span data-ttu-id="cf7c1-135">如果行動已停用，MPOP 比值為1：1.5。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-135">If mobility is disabled, the MPOP ratio is 1:1.5.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf7c1-136">遠端使用者分配</span><span class="sxs-lookup"><span data-stu-id="cf7c1-136">Remote user distribution</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-137">70% 的使用者內部連線。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-137">70% of users connecting internally.</span></span></p>
<p><span data-ttu-id="cf7c1-138">30% 的使用者透過 Edge Server 和 Director 進行連線。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-138">30% of users connecting through an Edge Server and a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf7c1-139">連絡人散佈</span><span class="sxs-lookup"><span data-stu-id="cf7c1-139">Contact distribution</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-140">使用者人數上限為1000。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-140">The maximum number of contacts a user has is 1,000.</span></span> <span data-ttu-id="cf7c1-141">小於1% 的使用者有1000連絡人。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-141">Less than 1% of users have 1,000 contacts.</span></span> <span data-ttu-id="cf7c1-142">少於25% 的使用者有100或以上的連絡人。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-142">Less than 25% of users have 100 or more contacts.</span></span></p>
<p><span data-ttu-id="cf7c1-143">使用公用雲端連線的使用者的平均80連絡人。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-143">Average of 80 contacts for users with public cloud connectivity.</span></span> <span data-ttu-id="cf7c1-144">下列使用者：</span><span class="sxs-lookup"><span data-stu-id="cf7c1-144">Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="cf7c1-145">50% 的連絡人位於組織內。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-145">50% of the contacts are within the organization.</span></span> <span data-ttu-id="cf7c1-146">10% 的使用者為遠端使用者，從防火牆外部連線。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-146">10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="cf7c1-147">40% 的連絡人是公用雲端使用者 (例如 AOL、Yahoo！、MSN 或 Google 交談) 的使用者。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-147">40% of the contacts are public cloud users (such as users of AOL, Yahoo!, MSN, or Google Talk).</span></span></p></li>
<li><p><span data-ttu-id="cf7c1-148">10% 的連絡人來自同盟合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-148">10% of the contacts are from federated partners.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="cf7c1-149">從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 ( 「PIC USL」 ) 不再提供購買新的或更新的協定。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-149">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="cf7c1-150">具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="cf7c1-150">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="cf7c1-151">信使直到服務關閉日期。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-151">Messenger until the service shut down date.</span></span> <span data-ttu-id="cf7c1-152">AOL 和 Yahoo！的循環結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="cf7c1-152">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="cf7c1-153">已宣告。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-153">has been announced.</span></span> <span data-ttu-id="cf7c1-154">如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-154">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="cf7c1-155">PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="cf7c1-155">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="cf7c1-156">信使。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-156">Messenger.</span></span> <span data-ttu-id="cf7c1-157">Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-157">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="cf7c1-158">Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-158">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="cf7c1-159">與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-159">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="cf7c1-160">隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-160">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
</ul>
<p><span data-ttu-id="cf7c1-161">在沒有公用雲端連線的情況下，為使用者平均50連絡人。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-161">Average of 50 contacts for users without public cloud connectivity.</span></span> <span data-ttu-id="cf7c1-162">下列使用者：</span><span class="sxs-lookup"><span data-stu-id="cf7c1-162">Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="cf7c1-163">80% 的連絡人位於組織內。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-163">80% of the contacts are within the organization.</span></span> <span data-ttu-id="cf7c1-164">10% 的使用者為遠端使用者，從防火牆外部連線。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-164">10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="cf7c1-165">20% 的連絡人來自同盟合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-165">20% of the contacts are from federated partners.</span></span></p>
<p><span data-ttu-id="cf7c1-166">每個使用者的連絡人清單中有1個通訊群組。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-166">Each user has 1 distribution group in their contact list.</span></span> <span data-ttu-id="cf7c1-167">針對效能測試，我們假設通訊群組永遠展開。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-167">For performance testing, we assume that distribution groups are always expanded.</span></span></p></li>
</ul>
<p><span data-ttu-id="cf7c1-168">25% 的使用者的連絡人使用 XMPP。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-168">25% of a user’s contacts use XMPP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf7c1-169">會話時間</span><span class="sxs-lookup"><span data-stu-id="cf7c1-169">Session time</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-170">平均使用者登入會話會持續12小時。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-170">The average user logon session lasts 12 hours.</span></span> <span data-ttu-id="cf7c1-171">所有使用者在會話開始的120分鐘內登入。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-171">All users log on within 120 minutes of the start of the session.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="im-and-presence-user-model"></a><span data-ttu-id="cf7c1-172">IM 和目前狀態使用者模型</span><span class="sxs-lookup"><span data-stu-id="cf7c1-172">IM and Presence User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf7c1-173">類別</span><span class="sxs-lookup"><span data-stu-id="cf7c1-173">Category</span></span></th>
<th><span data-ttu-id="cf7c1-174">描述</span><span class="sxs-lookup"><span data-stu-id="cf7c1-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf7c1-175">對等 IM 會話</span><span class="sxs-lookup"><span data-stu-id="cf7c1-175">Peer-to-peer IM sessions</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-176">每位使用者每天平均六個對等 IM 會話。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-176">Each user averages six peer-to-peer IM sessions per day.</span></span></p>
<p><span data-ttu-id="cf7c1-177">每個會話10個立即訊息。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-177">10 instant messages per session.</span></span></p>
<p><span data-ttu-id="cf7c1-178">每封郵件會以兩個 SIP 資訊訊息和2個 SIP 200 確定郵件 (，以供狀態指標（如 " &lt; Name the Name &gt; "） ) </span><span class="sxs-lookup"><span data-stu-id="cf7c1-178">Each message is matched by two SIP INFO messages and 2 SIP 200 OK messages (for the status indicators such as “&lt;Name&gt; is Typing”)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf7c1-179">目前狀態輪詢</span><span class="sxs-lookup"><span data-stu-id="cf7c1-179">Presence polling</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-180">總而言之，我們每位使用者每小時平均60輪詢的平均狀態輪詢。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-180">Overall, we assume presence polling at an average of 60 polls per user per hour.</span></span> <span data-ttu-id="cf7c1-181">針對每個使用者，假設平均：</span><span class="sxs-lookup"><span data-stu-id="cf7c1-181">For each user, assume an average of:</span></span></p>
<ul>
<li><p><span data-ttu-id="cf7c1-182">在使用者的 [組織] 索引標籤中，每一天一個輪詢使用者的狀態 (但不是連絡人清單) 。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-182">One poll per day of the presence of users in the user’s organization tab (but not Contacts list).</span></span> <span data-ttu-id="cf7c1-183">在使用者的 [組織] 索引標籤中，平均非連絡人數目為15位使用者。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-183">Average number of non-contacts in the user’s organization tab is 15 users.</span></span> <span data-ttu-id="cf7c1-184">每天的兩個連絡人卡片查看作業。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-184">Two contact card viewing operations per day.</span></span></p></li>
<li><p><span data-ttu-id="cf7c1-185">一個目前狀態輪詢每當使用者按一下另一個使用者來開始交談時，預估每小時預估一次。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-185">One presence poll every time the user clicks another user to start a conversation, estimated at once per hour.</span></span></p></li>
<li><p><span data-ttu-id="cf7c1-186">每小時六個使用者搜尋。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-186">Six user searches per hour.</span></span> <span data-ttu-id="cf7c1-187">每次執行搜尋時，都會針對搜尋結果清單中的每個人傳送批次投票。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-187">Every time a search is performed, a batch poll is sent for everyone in the search result list.</span></span> <span data-ttu-id="cf7c1-188">我們假設搜尋結果的平均大小為20。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-188">We assume the average size of search results is 20.</span></span> <span data-ttu-id="cf7c1-189">如果搜尋結果停留在螢幕上，批次輪詢會每5分鐘刷新一次。我們假設每小時會有兩種重新整理。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-189">If the search results stay on screen, the batch poll is refreshed every 5 minutes; we assume that there will be two such refreshes per hour.</span></span></p></li>
<li><p><span data-ttu-id="cf7c1-190">當使用者開啟或預覽 Outlook 中的電子郵件時，會在電子郵件的 [收件者：] 和 [副本：] 欄位中輪詢使用者的狀態，每小時預估5封電子郵件，每封電子郵件四位使用者。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-190">When the user opens or previews an email in Outlook, a poll of the presence of users in the To: and CC: fields of the email, estimated at five emails per hour and four users per email.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf7c1-191">目前狀態訂閱</span><span class="sxs-lookup"><span data-stu-id="cf7c1-191">Presence subscriptions</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-192">當一個使用者將另一個使用者新增為連絡人時，第一個使用者會 <em>訂閱</em> 第二個使用者的五種資訊類別。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-192">When one user adds another as a contact, the first user is <em>subscribing</em> to five categories of information about the second user.</span></span> <span data-ttu-id="cf7c1-193">這些資訊類別的更新會自動傳送給第一個使用者。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-193">Updates of these categories of information are automatically sent to the first user.</span></span></p>
<p><span data-ttu-id="cf7c1-194">針對每個用戶端，會傳送單一批次訂閱要求，以取得平均40連絡人的目前狀態，另外還有其他40對話方塊，可取得同盟連絡人的狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-194">For each client, a single batch subscription request is sent to obtain the presence state of an average of 40 contacts, with an additional 40 dialogs to obtain presence for federated contacts.</span></span></p>
<p><span data-ttu-id="cf7c1-195">展開的通訊群組成員的目前狀態會透過持續存在性訂閱來找到，而非輪詢，而且會為每位使用者每2個小時以1個擴充模式進行類比。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-195">Presence for members of an expanded distribution group is found through persistent presence subscriptions, not polling, and is modeled as 1 expansion per user for each 2 hours.</span></span></p>
<p><span data-ttu-id="cf7c1-196"><em>短訂閱</em> 會在使用者登入時發生，所有使用者的連絡人都有一個批次訂閱，然後使用者便會立即登出。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-196"><em>Short subscriptions</em> happen when a user logs in, there is a batch subscription for all the user’s contacts, and then the user soon logs off.</span></span> <span data-ttu-id="cf7c1-197">我們為每位使用者每小時假設6個短訂閱，每個訂閱會持續10分鐘。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-197">We assume 6 short subscriptions per user per hour, where each subscription lasts 10 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf7c1-198">目前狀態出版物</span><span class="sxs-lookup"><span data-stu-id="cf7c1-198">Presence Publication</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-199">每位使用者每小時平均發佈一個顯示狀態的狀態，每位使用者每小時最多6個出版物。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-199">Presence state is published at an average of 4 publications per user per hour, with a maximum 6 per user per hour.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf7c1-200">目前狀態檔案大小</span><span class="sxs-lookup"><span data-stu-id="cf7c1-200">Presence Document Size</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-201">完整顯示狀態檔的平均大小假設為4K，最大值為25K。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-201">The average size of a complete presence document is assumed to be 4K, with a maximum of 25K.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cf7c1-202">下表說明通訊錄使用的使用者模型。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-202">The following table describes the user model for address book use.</span></span>

### <a name="address-book-usage-user-model"></a><span data-ttu-id="cf7c1-203">通訊錄使用狀況使用者模型</span><span class="sxs-lookup"><span data-stu-id="cf7c1-203">Address Book Usage User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf7c1-204">通訊錄搜尋模式</span><span class="sxs-lookup"><span data-stu-id="cf7c1-204">Address Book search mode</span></span></th>
<th><span data-ttu-id="cf7c1-205">Usage</span><span class="sxs-lookup"><span data-stu-id="cf7c1-205">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf7c1-206">通訊錄 Web 查詢僅 (通訊錄 Web 查詢服務執行的所有查詢) </span><span class="sxs-lookup"><span data-stu-id="cf7c1-206">Address Book Web Query only (all queries performed by Address Book Web Query service)</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-207">每位使用者每天四個首碼查詢。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-207">Four prefix queries per user per day.</span></span></p>
<p><span data-ttu-id="cf7c1-208">60每天每位使用者的確切搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-208">60 exact search queries per user per day.</span></span> <span data-ttu-id="cf7c1-209">40% 的批次，每個查詢平均有20個連絡人。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-209">40% of those are batched, with an average of 20 contacts per query.</span></span> <span data-ttu-id="cf7c1-210">其他60% 的查詢是針對單一連絡人。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-210">The other 60% of the queries are for a single contact.</span></span></p>
<p><span data-ttu-id="cf7c1-211">每位使用者每天25張照片查詢。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-211">25 photo queries per user per day.</span></span> <span data-ttu-id="cf7c1-212">24是針對單一相片，另一個是具有平均20個連絡人的批次查詢。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-212">24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="cf7c1-213">每位使用者每天一個組織搜尋查詢總數。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-213">One total organization search query per user per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf7c1-214">混合模式，使用通訊錄檔案和 web 查詢。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-214">Mixed mode, both address book file and web queries used.</span></span> <span data-ttu-id="cf7c1-215">這是預設模式。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-215">This is the default mode.</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-216">只有兩種類型的查詢會進入網路、相片和組織總搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-216">Only two types of queries go to the network, the photo and total organizational search queries.</span></span></p>
<p><span data-ttu-id="cf7c1-217">每位使用者每天25張照片查詢。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-217">25 photo queries per user per day.</span></span> <span data-ttu-id="cf7c1-218">24是針對單一相片，另一個是具有平均20個連絡人的批次查詢。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-218">24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="cf7c1-219">每位使用者每天一個組織搜尋查詢總數。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-219">One total organization search query per user per day.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cf7c1-220">下表說明會議模型。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-220">The following table describes the conferencing model.</span></span>

### <a name="conferencing-model"></a><span data-ttu-id="cf7c1-221">會議模型</span><span class="sxs-lookup"><span data-stu-id="cf7c1-221">Conferencing Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf7c1-222">類別</span><span class="sxs-lookup"><span data-stu-id="cf7c1-222">Category</span></span></th>
<th><span data-ttu-id="cf7c1-223">描述</span><span class="sxs-lookup"><span data-stu-id="cf7c1-223">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf7c1-224">排定的會議與「 &quot; 立即開會」的 &quot; 會議</span><span class="sxs-lookup"><span data-stu-id="cf7c1-224">Scheduled meetings versus &quot;Meet now&quot; meetings</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-225">已排程60%，40% 未計畫。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-225">60% scheduled, 40% unscheduled.</span></span></p>
<p><span data-ttu-id="cf7c1-226">在排程的會議中，我們假設80% 指派為會議，也就是週期性會議的出現;10% 是一次開啟的會議;8% 是一次性匿名會議，2% 是一次關閉會議。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-226">Of the scheduled meetings, we assume that 80% are assigned conferences, which are occurences of recurring conferences; 10% are one-time open meetings; 8% are one-time anonymous meetings, and 2% are one-time closed meetings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf7c1-227">會議用戶端分配</span><span class="sxs-lookup"><span data-stu-id="cf7c1-227">Conferencing client distribution</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-228">對於排程的會議：</span><span class="sxs-lookup"><span data-stu-id="cf7c1-228">For scheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="cf7c1-229">65% 的會議使用者使用 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-229">65% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="cf7c1-230">5% 的會議使用者使用 Microsoft Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-230">5% of conferencing users use Microsoft Lync Web App.</span></span></p></li>
<li><p><span data-ttu-id="cf7c1-231">30% 的會議使用者使用舊版用戶端，包括 Microsoft Lync 2010、Office Communicator 2007 R2、Office Communicator 2007 和 Microsoft Office Communicator Web Access (2007 版本) 。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-231">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul>
<p><span data-ttu-id="cf7c1-232">針對排程的會議：</span><span class="sxs-lookup"><span data-stu-id="cf7c1-232">For unscheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="cf7c1-233">70% 的會議使用者使用 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-233">70% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="cf7c1-234">30% 的會議使用者使用舊版用戶端，包括 Microsoft Lync 2010、Office Communicator 2007 R2、Office Communicator 2007 和 Microsoft Office Communicator Web Access (2007 版本) 。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-234">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf7c1-235">會議並行</span><span class="sxs-lookup"><span data-stu-id="cf7c1-235">Meeting concurrency</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-236">5% 的使用者將在工作時間內的會議。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-236">5% of users will be in conferences during working hours.</span></span> <span data-ttu-id="cf7c1-237">因此，在80000使用者集區中，最多可以有4000個使用者在會議中有一次。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-237">Thus, in an 80,000-user pool, as many as 4,000 users might be in conferences at any one time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf7c1-238">會議音訊分配</span><span class="sxs-lookup"><span data-stu-id="cf7c1-238">Meeting audio distribution</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-239">40% 混合 VoIP 音訊和電話撥入式會議，具有 VoIP 使用者的3:1 比率為撥入使用者。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-239">40% mixed VoIP audio and dial-in conferencing, with a 3:1 ratio of VoIP users to dial-in users.</span></span></p>
<p><span data-ttu-id="cf7c1-240">35% 僅 VoIP 音訊。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-240">35% VoIP audio only.</span></span></p>
<p><span data-ttu-id="cf7c1-241">15% 僅限電話撥入式會議音訊。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-241">15% dial-in conferencing audio only.</span></span></p>
<p><span data-ttu-id="cf7c1-242">10% 無音訊 (僅限 IM 會議，每位使用者平均傳送五封郵件) 。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-242">10% no audio (IM-only conferences, with an average of five messages sent per user).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf7c1-243">會議的媒體組合</span><span class="sxs-lookup"><span data-stu-id="cf7c1-243">Media mix for conferences</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-244">75% 的會議是網路會議，包含音訊及其他一些共同作業形式。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-244">75% of conferences are web conferences, which include audio plus some other collaboration modalities.</span></span></p>
<p><span data-ttu-id="cf7c1-245">對於這些會議，其他共同作業方法如下：</span><span class="sxs-lookup"><span data-stu-id="cf7c1-245">For these conferences, the other collaboration methods are as follows:</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="cf7c1-246">這些數目的增加超過100%，因為一部會議可以有多個共同作業方法。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-246">These numbers add up to more than 100% because one conference can have multiple collaboration methods.</span></span>


</div>
<ul>
<li><p><span data-ttu-id="cf7c1-247">50% 新增應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-247">50% add application sharing.</span></span> <span data-ttu-id="cf7c1-248">我們假設一位使用者以每秒峰值 1.1 MB 的速率傳送資料。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-248">We assume one users sends data at a peak of 1.1 MB per second.</span></span></p></li>
<li><p><span data-ttu-id="cf7c1-249">50% 新增立即訊息 (，每位使用者) 平均有2封郵件。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-249">50% add instant messaging (with an average of 2 messages per user).</span></span></p></li>
<li><p><span data-ttu-id="cf7c1-250">20% 新增資料共同作業（包括 PowerPoint 或白板），平均每次會議所呈現的2個 PowerPoint 檔案，平均 PowerPoint 的檔案大小為 10 MB (，但沒有內嵌影片) 或 30 MB (使用內嵌的影片) 。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-250">20% add data collaboration, including PowerPoint or whiteboard In these, an average of 2 PowerPoint files presented per conference, with an average PowerPoint file size of 10 MB (without embedded video) or 30 MB (with embedded video).</span></span> <span data-ttu-id="cf7c1-251">每個白板的平均20個批註。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-251">Average of 20 annotations per whiteboard.</span></span></p></li>
<li><p><span data-ttu-id="cf7c1-252">20% 新增影片。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-252">20% add video.</span></span> <span data-ttu-id="cf7c1-253">在這些使用者中，70% 位於啟用多種顯示顯示的會議中，每個使用者都會收到2-3 的視頻資料流程。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-253">Of these users, 70% are in conferences enabled for multiview video, where each user receives 2-3 video streams.</span></span></p></li>
<li><p><span data-ttu-id="cf7c1-254">15% 新增共用筆記。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-254">15% add shared notes.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf7c1-255">會議參與者分配</span><span class="sxs-lookup"><span data-stu-id="cf7c1-255">Meeting participant distribution</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-256">50% 已驗證的內部使用者。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-256">50% internal, authenticated users.</span></span></p>
<p><span data-ttu-id="cf7c1-257">25% 遠端存取，已驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-257">25% remote access, authenticated users.</span></span></p>
<p><span data-ttu-id="cf7c1-258">15% 匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-258">15% anonymous users.</span></span></p>
<p><span data-ttu-id="cf7c1-259">10% 同盟使用者。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-259">10% federated users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf7c1-260">會議加入分配</span><span class="sxs-lookup"><span data-stu-id="cf7c1-260">Meeting join distribution</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-261">使用者在前5分鐘內模擬為加入會議。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-261">Users are simulated as joining the meeting within the first 5 minutes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cf7c1-262">在一般前端集區中，Lync Server 2013 的支援會議大小上限為250使用者。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-262">In regular Front End pools, Lync Server 2013 has a maximum supported meeting size of 250 users.</span></span> <span data-ttu-id="cf7c1-263">每個集區一次可裝載 1 250 使用者會議。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-263">Each pool can host one 250-user meeting at a time.</span></span> <span data-ttu-id="cf7c1-264">在此大型會議發生時，集區也可以主控其他較小的會議。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-264">While this large meeting is occurring, the pool can also host other smaller conferences.</span></span> <span data-ttu-id="cf7c1-265">此外，您可以設定專用集區來主控這些會議，以支援最多1000使用者的會議。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-265">Additionally, you can support meetings of up to 1000 users by setting up a dedicated pool to host these meetings.</span></span> <span data-ttu-id="cf7c1-266">如需詳細資訊，請參閱 [在 Lync Server 2013 中支援大型會議](lync-server-2013-support-for-large-meetings.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-266">For details, see [Support for large meetings in Lync Server 2013](lync-server-2013-support-for-large-meetings.md).</span></span>

<span data-ttu-id="cf7c1-267">會議的模擬方式如下：</span><span class="sxs-lookup"><span data-stu-id="cf7c1-267">Conferences were simulated as follows:</span></span>

  - <span data-ttu-id="cf7c1-268">85% 的會議有四位參與者。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-268">85% of conferences had four participants.</span></span>

  - <span data-ttu-id="cf7c1-269">10% 的會議有6位參與者。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-269">10% of conferences had six participants.</span></span>

  - <span data-ttu-id="cf7c1-270">5% 的會議有11位參與者。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-270">5% of conferences had 11 participants.</span></span>

  - <span data-ttu-id="cf7c1-271">一個大型的250使用者會議。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-271">One large conference of 250 users.</span></span>

<span data-ttu-id="cf7c1-272">下表提供使用者模型的詳細資訊，包括撥入使用者的會議。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-272">The following table provides details about the user model for conferences involving dial-in users.</span></span>

### <a name="dial-in-conferencing-user-model"></a><span data-ttu-id="cf7c1-273">會議使用者模型 Dial-In</span><span class="sxs-lookup"><span data-stu-id="cf7c1-273">Dial-In Conferencing User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf7c1-274">類別</span><span class="sxs-lookup"><span data-stu-id="cf7c1-274">Category</span></span></th>
<th><span data-ttu-id="cf7c1-275">描述</span><span class="sxs-lookup"><span data-stu-id="cf7c1-275">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf7c1-276">已驗證/匿名</span><span class="sxs-lookup"><span data-stu-id="cf7c1-276">Authenticated/anonymous</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-277">70% 的呼叫者會以匿名方式加入，並提示您輸入錄製的名稱。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-277">70% of callers join as anonymous and are prompted for a recorded name.</span></span> <span data-ttu-id="cf7c1-278">30% 加入為已驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-278">30% join as authenticated users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf7c1-279">通話持續時間和等候音樂</span><span class="sxs-lookup"><span data-stu-id="cf7c1-279">Call duration and music on hold</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-280">平均通話持續時間，未等候音樂：50秒。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-280">Average call duration without music on hold: 50 seconds.</span></span></p>
<p><span data-ttu-id="cf7c1-281">50% 的來電使用者在平均5分鐘內聽到等候音樂。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-281">50% of call-in users hear music on hold, for an average of 5 minutes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf7c1-282">雙音訊式訊號 (DTMF) </span><span class="sxs-lookup"><span data-stu-id="cf7c1-282">Dual-tone multifrequency (DTMF)</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-283">15% 的電話會議只有電話領導者。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-283">15% of conferences that are dial-in only have phone leaders.</span></span> <span data-ttu-id="cf7c1-284">包含撥入式使用者的混合式會議中，有10% 的混合會議也有電話領導者。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-284">10% of mixed conferences that include dial-in users also have phone leaders.</span></span></p>
<p><span data-ttu-id="cf7c1-285">20% 的電話領導者使用每個會議的2個 DTMF 命令。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-285">20% of phone leaders use 2 DTMF commands per conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf7c1-286">宣告語言</span><span class="sxs-lookup"><span data-stu-id="cf7c1-286">Announcement languages</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-287">模擬使用英文做為宣告語言。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-287">Simulations use English as the announcement language.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cf7c1-288">下表提供有關會議大廳之使用者模型的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-288">The following table provides details about the user model for conference lobbies.</span></span>

### <a name="conference-lobby-user-model"></a><span data-ttu-id="cf7c1-289">會議會議廳使用者模型</span><span class="sxs-lookup"><span data-stu-id="cf7c1-289">Conference Lobby User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf7c1-290">類別</span><span class="sxs-lookup"><span data-stu-id="cf7c1-290">Category</span></span></th>
<th><span data-ttu-id="cf7c1-291">描述</span><span class="sxs-lookup"><span data-stu-id="cf7c1-291">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf7c1-292">會議廳中的使用者人數</span><span class="sxs-lookup"><span data-stu-id="cf7c1-292">Number of users in lobby</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-293">5% 的撥入使用者會流覽會議廳，25% 的其他使用者會進入會議廳。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-293">5% of dial-in users go through the lobby, and 25% of other users go through the lobby</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf7c1-294">從會議廳准許</span><span class="sxs-lookup"><span data-stu-id="cf7c1-294">Admitting from lobby</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-295">在模擬中，所有使用者在用戶端超時之前都已由簡報者所承認。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-295">In simulations, all users were admitted by the presenter before client timeout.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cf7c1-296">下表說明其他點對點工作階段的使用者模型。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-296">The following table describes the user model for other peer-to-peer sessions.</span></span>

### <a name="peer-to-peer-sessions-user-model"></a><span data-ttu-id="cf7c1-297">Peer-to-Peer 會話使用者模型</span><span class="sxs-lookup"><span data-stu-id="cf7c1-297">Peer-to-Peer Sessions User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf7c1-298">類別</span><span class="sxs-lookup"><span data-stu-id="cf7c1-298">Category</span></span></th>
<th><span data-ttu-id="cf7c1-299">描述</span><span class="sxs-lookup"><span data-stu-id="cf7c1-299">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf7c1-300">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="cf7c1-300">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-301">每一位使用者每月加入5對等應用程式共用會話，平均每天0.25 個會話。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-301">Each user participates in 5 peer-to-peer application sharing sessions per month, for an average of 0.25 sessions per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf7c1-302">檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="cf7c1-302">File transfer</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-303">每個使用者都會每月加入一部對等檔案傳輸會話 (成為 IM 會話) ，平均每天0.05 個會話。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-303">Each user participates in 1 peer-to-peer file transfer session per month (as part of an IM session), for an average of 0.05 sessions per day.</span></span> <span data-ttu-id="cf7c1-304">傳輸的平均會話檔案大小為 1 MB。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-304">The average session file size transferred is 1 MB.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cf7c1-305">下表說明原則的使用者模型。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-305">The following table describes the user model for policies.</span></span>

### <a name="policies-user-model"></a><span data-ttu-id="cf7c1-306">原則使用者模型</span><span class="sxs-lookup"><span data-stu-id="cf7c1-306">Policies User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf7c1-307">類別</span><span class="sxs-lookup"><span data-stu-id="cf7c1-307">Category</span></span></th>
<th><span data-ttu-id="cf7c1-308">描述</span><span class="sxs-lookup"><span data-stu-id="cf7c1-308">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf7c1-309">會議、目前狀態及封存原則</span><span class="sxs-lookup"><span data-stu-id="cf7c1-309">Conferencing, Presence, and Archiving Policies</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-310">我們假設有一個全域原則、10個標記會議原則、4個封存原則及10個標記顯示狀態原則。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-310">We assume that there is one global policy, 10 tag conferencing policies, 4 Archiving policies, and 10 tag presence policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf7c1-311">語音原則</span><span class="sxs-lookup"><span data-stu-id="cf7c1-311">Voice Policy</span></span></p></td>
<td><p><span data-ttu-id="cf7c1-312">我們假設每個網站都有一個全域原則和2個標記原則。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-312">We assume that there is one global policy and 2 tag policies per site.</span></span> <span data-ttu-id="cf7c1-313">100% 的網站有網站原則，30% 的使用者已指派個別使用者原則。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-313">100% of sites have a site policy, and 30% of users have a per-user policy assigned.</span></span> <span data-ttu-id="cf7c1-314">我們假設每個網站有一個撥號對應表，每個網站都有兩個路由。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-314">We assume one dial plan per site and two routes per site.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="busy-hour"></a><span data-ttu-id="cf7c1-315">忙碌小時</span><span class="sxs-lookup"><span data-stu-id="cf7c1-315">Busy Hour</span></span>

<span data-ttu-id="cf7c1-316">點對點工作階段，峰值負載是使用繁忙的小時嘗試 (BHCA) 進行計算。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-316">For peer-to-peer sessions, peak load is calculated using busy hour call attempts (BHCA).</span></span> <span data-ttu-id="cf7c1-317">這個語音行業條款假設一天的50% 會在20% 的時間內完成。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-317">This voice industry term assumes that 50% of all calls for the day will be completed in 20% of the time.</span></span> <span data-ttu-id="cf7c1-318">它會使用下列公式計算：</span><span class="sxs-lookup"><span data-stu-id="cf7c1-318">It is calculated using the following formula:</span></span>

`BHCA=(total calls * 0.5) / 1.6`

<span data-ttu-id="cf7c1-319">執行 VoIP 及其他點對點工作階段時，效能測試會以每小時至少每日至少1.6 小時的速度來執行。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-319">Performance testing simulated busy hour by running VoIP and other peer-to-peer sessions at a busy hour load for at least 1.6 hours per day.</span></span>

<span data-ttu-id="cf7c1-320">會議峰值負載假設一天的75% 的所有會議都會以4個峰時段的時間進行。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-320">Conferencing peak load assumes that 75% of all conferences for an eight-hour day happen in 4 peak time hours.</span></span> <span data-ttu-id="cf7c1-321">這兩個峰時段的平均會議負載是1.5 倍。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-321">Those peak hours have 1.5 times the average conferencing load.</span></span>

</div>

<div>

## <a name="enterprise-voice-to-pstn-calls"></a><span data-ttu-id="cf7c1-322">Enterprise Voice to PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="cf7c1-322">Enterprise Voice to PSTN Calls</span></span>

<span data-ttu-id="cf7c1-323">下列假設適用于 Enterprise Voice 呼叫：</span><span class="sxs-lookup"><span data-stu-id="cf7c1-323">The following assumptions apply to Enterprise Voice calls:</span></span>

  - <span data-ttu-id="cf7c1-324">50% 的使用者已啟用 Enterprise Voice，而這些使用者的60% 已啟用 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-324">50% of users are enabled for Enterprise Voice, and 60% of these users are enabled for PSTN calling.</span></span>

  - <span data-ttu-id="cf7c1-325">每個為 PSTN 通話啟用的使用者，在忙碌小時內撥打4個 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-325">Each of these users enabled for PSTN calling makes 4 PSTN calls during the busy hour.</span></span> <span data-ttu-id="cf7c1-326">每個通話持續時間為3分鐘。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-326">Each call duration is 3 minutes.</span></span>

  - <span data-ttu-id="cf7c1-327">65% 的這些 PSTN 語音通話使用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-327">65% of these PSTN voice calls use media bypass.</span></span>

</div>

<div>

## <a name="mobility"></a><span data-ttu-id="cf7c1-328">行動性</span><span class="sxs-lookup"><span data-stu-id="cf7c1-328">Mobility</span></span>

<span data-ttu-id="cf7c1-329">40% 的註冊使用者會被視為啟用行動性。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-329">40% of registered users are assumed to be enabled for Mobility.</span></span> <span data-ttu-id="cf7c1-330">針對每個已啟用行動裝置的使用者，我們假設行動用戶端的活動已附加到該使用者的其他 MPOP 實例，但會議互動例外，其行動用戶端只是另一種可用於參與會議的用戶端類型。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-330">For each user that has mobility enabled, we assume that the activity of the mobile client is additive to that of the other MPOP instances for that user, with the exception of conferencing interactions, for which the mobility client is just another client type that can be used to participate in conferences.</span></span>

</div>

<div>

## <a name="persistent-chat"></a><span data-ttu-id="cf7c1-331">常設聊天室</span><span class="sxs-lookup"><span data-stu-id="cf7c1-331">Persistent Chat</span></span>

<span data-ttu-id="cf7c1-332">我們假設25% 的註冊使用者會參與持續聊天會話，具有下列特性：</span><span class="sxs-lookup"><span data-stu-id="cf7c1-332">We assume that 25% of registered users will be involved in Persistent chat sessions, with the following characteristics:</span></span>

  - <span data-ttu-id="cf7c1-333">每位使用者的平均1.5 聊天室</span><span class="sxs-lookup"><span data-stu-id="cf7c1-333">An average of 1.5 chat rooms per user</span></span>

  - <span data-ttu-id="cf7c1-334">每個聊天室都會每小時產生12個輪詢要求，每個目標平均平均為10位使用者。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-334">Each chat room results in 12 polling requests per hour, targeting an average of 10 users each</span></span>

</div>

<div>

## <a name="response-group-and-call-park"></a><span data-ttu-id="cf7c1-335">回應群組和通話駐留</span><span class="sxs-lookup"><span data-stu-id="cf7c1-335">Response Group and Call Park</span></span>

<span data-ttu-id="cf7c1-336">我們假設已註冊使用者的0.15% 屬於回應群組。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-336">We assume that 0.15% of registered users belong to response groups.</span></span> <span data-ttu-id="cf7c1-337">我們假設已註冊使用者的0.02% 已在任何指定的時間點寄存通話。</span><span class="sxs-lookup"><span data-stu-id="cf7c1-337">We assume that 0.02% of registered users have parked calls at any given point of time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


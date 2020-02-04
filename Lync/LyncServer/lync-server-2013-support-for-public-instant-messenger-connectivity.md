---
title: Lync Server 2013 支援公用立即信使連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cd3c8cf89b9d5e1637db893b57e6b5955fbcee9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a><span data-ttu-id="c5950-102">支援 Lync Server 2013 中的公用立即信使連線</span><span class="sxs-lookup"><span data-stu-id="c5950-102">Support for public instant messenger connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5950-103">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="c5950-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a><span data-ttu-id="c5950-104">支援公用立即信使連線</span><span class="sxs-lookup"><span data-stu-id="c5950-104">Support for Public Instant Messenger Connectivity</span></span>

<span data-ttu-id="c5950-105">本文提供有關公用 IM 連線（PIC）支援的資訊。</span><span class="sxs-lookup"><span data-stu-id="c5950-105">This article provides information about support for Public IM Connectivity (PIC).</span></span> <span data-ttu-id="c5950-106">PIC 是 Microsoft Lync 的一項功能，可讓組織透過其 Lync 用戶端和身分識別，讓其 Lync 使用者能夠與特定公用立即訊息（IM）服務的使用者連線。</span><span class="sxs-lookup"><span data-stu-id="c5950-106">PIC is a feature of Microsoft Lync that allows organizations to enable their Lync users to connect with users of certain public instant messaging (IM) services through their Lync clients and identities.</span></span>

<span data-ttu-id="c5950-107">當使用者與客戶、合作夥伴及廠商的相關產品時，使用者就能獲益。</span><span class="sxs-lookup"><span data-stu-id="c5950-107">End-users benefit from being able to connect with customers, partners, and vendors on their terms.</span></span> <span data-ttu-id="c5950-108">它的優點在於支援單一即時通訊用戶端，同時維持 Lync 的控制、合規性和歸檔功能。</span><span class="sxs-lookup"><span data-stu-id="c5950-108">IT benefits from supporting a single real-time communications client while maintaining the control, compliance, and archiving features of Lync.</span></span> <span data-ttu-id="c5950-109">Lync-Skype 連線（[在2013年5月公開提供](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx)）依賴舊版的 Lync/Office 通訊伺服器（OCS）/Live 通訊伺服器（LCS），首先在連線至 MSN/Windows LIVE、AOL 和 Yahoo 時建立與 PIC 的連接。</span><span class="sxs-lookup"><span data-stu-id="c5950-109">Lync-Skype connectivity, [publicly available in May 2013](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), relies on the legacy that Lync/Office Communications Server (OCS)/Live Communications Server (LCS) first established with PIC in connecting to MSN/Windows Live, AOL, and Yahoo.</span></span><span data-ttu-id="c5950-110">如需 Lync Skype 連線的詳細資訊，請參閱[lync-skype 連線能力](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c5950-110">  For more information on Lync-Skype connectivity, see the [Lync-Skype connectivity](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx).</span></span> <span data-ttu-id="c5950-111">與 Windows Live、AOL 和 Yahoo 的同盟，都是以路徑結束的方式進行。</span><span class="sxs-lookup"><span data-stu-id="c5950-111">Federation with Windows Live, AOL, and Yahoo are each on a path towards end-of-life.</span></span><span data-ttu-id="c5950-112">此頁面會記錄每個服務的狀態。</span><span class="sxs-lookup"><span data-stu-id="c5950-112"> This page documents the status of each service.</span></span>

<span data-ttu-id="c5950-113">若要使用 PIC，必須有客戶為每個公用 IM 服務提供者啟用服務。</span><span class="sxs-lookup"><span data-stu-id="c5950-113">To use PIC, customers have been required to activate the service for each public IM service provider.</span></span> <span data-ttu-id="c5950-114">此做法的需求及詳細資料取決於 IM 服務提供者和客戶的基礎授權計畫。</span><span class="sxs-lookup"><span data-stu-id="c5950-114">The requirements and details for how to do this are dependent upon the IM service provider and the customer's underlying licensing program.</span></span>

<div>

## <a name="windows-live-messenger"></a><span data-ttu-id="c5950-115">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c5950-115">Windows Live Messenger</span></span>

<span data-ttu-id="c5950-116">Microsoft 會將 Windows 即時信使和 Skype 集中在一起。</span><span class="sxs-lookup"><span data-stu-id="c5950-116">Microsoft brought Windows Live Messenger and Skype together.</span></span> <span data-ttu-id="c5950-117">在2013年4月，Messenger 使用者已在登入時遷移至 Skype。</span><span class="sxs-lookup"><span data-stu-id="c5950-117">In April 2013, Messenger users were migrated to Skype upon sign-in.</span></span> <span data-ttu-id="c5950-118">依賴同盟與 Messenger 的 Lync 客戶將會繼續與其 Messenger 連絡人通訊，即使在這些連絡人更新到 Skype 之後也一樣。</span><span class="sxs-lookup"><span data-stu-id="c5950-118">Lync customers who rely on federation with Messenger will continue to be able to communicate with their Messenger contacts, even after those contacts update to Skype.</span></span> <span data-ttu-id="c5950-119">Lync 系統管理員或 Lync 使用者不需要執行此動作，就能維持服務的連續性，而且在 Lync 中管理這項功能的方式與 Messenger 的通訊是一樣的。</span><span class="sxs-lookup"><span data-stu-id="c5950-119">There is nothing that Lync administrators or Lync end-users need to do to maintain continuity of service, and management of this capability within Lync remains the same as it has been for communications with Messenger.</span></span> 

<span data-ttu-id="c5950-120">當 Messenger 使用者使用其 Microsoft 帳戶登入 Skype 時（亦即用於 Messenger 的相同認證）所有的 Messenger 連絡人（包括同盟 Lync 連絡人），請依照 Skype 進行。</span><span class="sxs-lookup"><span data-stu-id="c5950-120">When Messenger users sign into Skype using their Microsoft accounts (i.e., the same credentials used for Messenger) all of their Messenger contacts - including federated Lync contacts - follow them into Skype.</span></span> <span data-ttu-id="c5950-121">您可以使用 Skype 和 Lync 之間的目前狀態共用與立即訊息。</span><span class="sxs-lookup"><span data-stu-id="c5950-121">Presence sharing and instant messaging between Skype and Lync for these contacts is available.</span></span> 

<span data-ttu-id="c5950-122">Lync-Skype 連線-連絡人在 Lync 與 Skype 使用者之間的新增、目前狀態共用、立即訊息及語音通話，現在也可供所有 Lync 客戶使用。</span><span class="sxs-lookup"><span data-stu-id="c5950-122">Lync-Skype connectivity - contact adding, presence sharing, instant messaging, and audio calling between Lync and Skype users - is also now available to all Lync customers.</span></span>

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a><span data-ttu-id="c5950-123">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="c5950-123">Yahoo\!</span></span> <span data-ttu-id="c5950-124">以及 AOL 立即 Messenger</span><span class="sxs-lookup"><span data-stu-id="c5950-124">and AOL Instant Messenger</span></span>

<span data-ttu-id="c5950-125">使用 Yahoo 的同盟\!</span><span class="sxs-lookup"><span data-stu-id="c5950-125">Federation with Yahoo\!</span></span> <span data-ttu-id="c5950-126">而且 AOL 都是在 Lync （以及 Office 通訊伺服器）用戶端的路線中使用。</span><span class="sxs-lookup"><span data-stu-id="c5950-126">and AOL are both on a path toward end-of-life for customers of Lync (and Office Communications Server).</span></span> <span data-ttu-id="c5950-127">Microsoft 提供每一項服務的能力都是從 Yahoo 支援。\!</span><span class="sxs-lookup"><span data-stu-id="c5950-127">Microsoft’s ability to provide each of these services has been contingent upon support from Yahoo\!</span></span> <span data-ttu-id="c5950-128">而且 AOL 以及這些專案的基礎協定會向下纏繞。</span><span class="sxs-lookup"><span data-stu-id="c5950-128">and AOL, and the underlying agreements of these are winding down.</span></span> <span data-ttu-id="c5950-129">兩個 Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="c5950-129">For both Yahoo\!</span></span> <span data-ttu-id="c5950-130">而且 AOL、服務將在2014年6月後繼續進行。</span><span class="sxs-lookup"><span data-stu-id="c5950-130">and AOL, service will continue through June 2014.</span></span>

  - <span data-ttu-id="c5950-131">**Yahoo** -服務將在2014年6月後繼續，而且客戶繼續需要使用 Microsoft LYNC 公用 IM 連線使用者訂閱授權（"PIC USL"）。</span><span class="sxs-lookup"><span data-stu-id="c5950-131">**Yahoo** - Service will continue through June 2014, and customers continue to need to be licensed with the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”).</span></span><span data-ttu-id="c5950-132">從2012年9月1日起，PIC USL 已不再提供購買新的或續約協定的功能。</span><span class="sxs-lookup"><span data-stu-id="c5950-132">  As of September 1st, 2012, the PIC USL, is no longer available for purchase for new or renewing agreements.</span></span><span data-ttu-id="c5950-133">擁有此日期之前購買之授權的客戶，將能夠繼續與 Yahoo 進行聯盟\!</span><span class="sxs-lookup"><span data-stu-id="c5950-133">  Customers with licenses purchased prior to this date will be able to continue to federate with Yahoo\!</span></span> <span data-ttu-id="c5950-134">直到較舊的服務關閉日期或其授權到期日為止。</span><span class="sxs-lookup"><span data-stu-id="c5950-134">until the earlier of the service shut down date or their license expiration.</span></span><span data-ttu-id="c5950-135">閱讀 Lync 團隊博客上[的公告](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c5950-135"> Read [the announcement](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) on the Lync Team Blog.</span></span><span data-ttu-id="c5950-136">如果客戶在2014年6月30日延長的合約上擁有 PIC 授權，將會以比例支付與2014年6月30日之後的付款金額的點數。</span><span class="sxs-lookup"><span data-stu-id="c5950-136"> Customers who have PIC licenses on agreements that extend past June 30, 2014 will receive a credit in proportion to the amount of the payments covering the time period following June 30, 2014.</span></span>

  - <span data-ttu-id="c5950-137">**AOL** -在2014年6月30日，LYNC 的 IM 連線（"PIC"）服務將不再提供使用。</span><span class="sxs-lookup"><span data-stu-id="c5950-137">**AOL** - On June 30, 2014, Lync's IM connectivity ("PIC") service will no longer be available.</span></span><span data-ttu-id="c5950-138">為了在服務結束時限制客戶的中斷，我們已停止提供額外的客戶網域。</span><span class="sxs-lookup"><span data-stu-id="c5950-138"> In order to limit customer disruption when the service ends, we have discontinued the provisioning of additional customer domains.</span></span> <span data-ttu-id="c5950-139">除非2014年6月30日，否則客戶就不需要執行任何動作，就能繼續支援與 AIM 進行聯盟通訊。</span><span class="sxs-lookup"><span data-stu-id="c5950-139">Until June 30, 2014, customers do not need to do anything to continue to support federated communications with AIM.</span></span> <span data-ttu-id="c5950-140">在此日期之後（或針對想要同時提供其他網域的客戶），可以直接從 AOL 取得替代服務。</span><span class="sxs-lookup"><span data-stu-id="c5950-140">Beyond this date (or for customers that would like to provision additional domains in the meantime), a substitute service is available directly from AOL.</span></span> <span data-ttu-id="c5950-141">如需 AOL 新服務的詳細資訊，請參閱[建立直接同盟與 AIM](http://aimenterprise.aol.com/pic.php)  （在 AOL.com 上開啟新頁面）。</span><span class="sxs-lookup"><span data-stu-id="c5950-141">For more information on AOL's new service, see [Establishing Direct Federation with AIM](http://aimenterprise.aol.com/pic.php)  (opens new page on AOL.com).</span></span>  

</div>

<div>

## <a name="public-im-provider-summary"></a><span data-ttu-id="c5950-142">公用 IM 提供者摘要</span><span class="sxs-lookup"><span data-stu-id="c5950-142">Public IM Provider Summary</span></span>

<span data-ttu-id="c5950-143">下表提供公用 IM 服務提供者的摘要、與 Lync 的同盟功能以及授權需求。</span><span class="sxs-lookup"><span data-stu-id="c5950-143">The following table provides a summary of the Public IM service providers, federation capabilities with Lync, and licensing requirements.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5950-144">公用 IM 服務提供者</span><span class="sxs-lookup"><span data-stu-id="c5950-144">Public IM Service Provider</span></span></th>
<th><span data-ttu-id="c5950-145">同盟功能</span><span class="sxs-lookup"><span data-stu-id="c5950-145">Federated Capabilities</span></span></th>
<th><span data-ttu-id="c5950-146">授權需求</span><span class="sxs-lookup"><span data-stu-id="c5950-146">Licensing Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5950-147">Skype</span><span class="sxs-lookup"><span data-stu-id="c5950-147">Skype</span></span></p></td>
<td><p><span data-ttu-id="c5950-148">IM、目前狀態、音訊</span><span class="sxs-lookup"><span data-stu-id="c5950-148">IM, Presence, Audio</span></span></p></td>
<td><p><span data-ttu-id="c5950-149">Lync Server 用戶端存取授權，Lync Online 方案1/2/3</span><span class="sxs-lookup"><span data-stu-id="c5950-149">Lync Server Client Access Licenses, Lync Online Plan 1/2/3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5950-150">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c5950-150">Windows Live Messenger</span></span></p></td>
<td><p><span data-ttu-id="c5950-151">IM、目前狀態、音訊/視頻</span><span class="sxs-lookup"><span data-stu-id="c5950-151">IM, Presence, Audio/Video</span></span></p></td>
<td><p><span data-ttu-id="c5950-152">Lync Server 用戶端存取授權（只要 WLM 為市場，即支援此功能）</span><span class="sxs-lookup"><span data-stu-id="c5950-152">Lync Server Client Access Licenses (supported as long as WLM is in market)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5950-153">AOL</span><span class="sxs-lookup"><span data-stu-id="c5950-153">AOL</span></span></p></td>
<td><p><span data-ttu-id="c5950-154">IM、目前狀態</span><span class="sxs-lookup"><span data-stu-id="c5950-154">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="c5950-155">Lync Server 用戶端存取授權;支援于現有客戶的2014年6月。</span><span class="sxs-lookup"><span data-stu-id="c5950-155">Lync Server Client Access Licenses; supported through June 2014 for existing customers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5950-156">Yahoo</span><span class="sxs-lookup"><span data-stu-id="c5950-156">Yahoo!</span></span></p></td>
<td><p><span data-ttu-id="c5950-157">IM、目前狀態</span><span class="sxs-lookup"><span data-stu-id="c5950-157">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="c5950-158">除了 Lync Server 用戶端存取授權之外，還需要額外的 Microsoft Lync 公用 IM 連線使用者訂閱授權（"PIC USL"）。</span><span class="sxs-lookup"><span data-stu-id="c5950-158">Requires additional Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) in addition to Lync Server Client Access Licences.</span></span> <span data-ttu-id="c5950-159">從2012年9月的價目表，PIC USL 已不再提供購買。</span><span class="sxs-lookup"><span data-stu-id="c5950-159">As of the September 2012 Price List, the PIC USL is no longer available for purchase.</span></span> <span data-ttu-id="c5950-160">擁有有效授權的客戶可以繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="c5950-160">Customers with active licenses are able to continue to federate with Yahoo!</span></span> <span data-ttu-id="c5950-161">Messenger，直到服務在2014年6月30日為止關閉。</span><span class="sxs-lookup"><span data-stu-id="c5950-161">Messenger until the service shut down date on June 30, 2014.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


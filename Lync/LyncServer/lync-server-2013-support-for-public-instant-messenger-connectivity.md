---
title: Lync Server 2013 支援公用立即信使連線
description: Lync Server 2013 支援公用立即信使連接。
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
ms.openlocfilehash: d4a58d71eb23012da960cf4505f1a55fd08df32c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573249"
---
# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a><span data-ttu-id="89a93-103">Lync Server 2013 中的公用立即信使連線支援</span><span class="sxs-lookup"><span data-stu-id="89a93-103">Support for public instant messenger connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89a93-104">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="89a93-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a><span data-ttu-id="89a93-105">支援公用立即信使連線</span><span class="sxs-lookup"><span data-stu-id="89a93-105">Support for Public Instant Messenger Connectivity</span></span>

<span data-ttu-id="89a93-106">本文提供 (PIC) 之公用 IM 連線支援的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="89a93-106">This article provides information about support for Public IM Connectivity (PIC).</span></span> <span data-ttu-id="89a93-107">PIC 是 Microsoft Lync 的一項功能，可讓組織讓其 Lync 使用者能夠透過其 Lync 用戶端和身分識別，透過某些公用立即訊息 (IM) 服務的使用者進行連線。</span><span class="sxs-lookup"><span data-stu-id="89a93-107">PIC is a feature of Microsoft Lync that allows organizations to enable their Lync users to connect with users of certain public instant messaging (IM) services through their Lync clients and identities.</span></span>

<span data-ttu-id="89a93-108">使用者可在其條款中與客戶、合作夥伴及廠商聯繫，以享受相關條款。</span><span class="sxs-lookup"><span data-stu-id="89a93-108">End-users benefit from being able to connect with customers, partners, and vendors on their terms.</span></span> <span data-ttu-id="89a93-109">其好處是支援單一即時通訊用戶端，同時維持 Lync 的控制、法規遵從性及封存功能。</span><span class="sxs-lookup"><span data-stu-id="89a93-109">IT benefits from supporting a single real-time communications client while maintaining the control, compliance, and archiving features of Lync.</span></span> <span data-ttu-id="89a93-110">Lync-Skype 連線，可于 [2013 年5月公開](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx)取得，依賴舊版的 Lync/Office 通訊伺服器 (OCS) /Live 通訊伺服器 (LCS) ，可在連線至 MSN/Windows LIVE、AOL 和 Yahoo 時，先建立與 PIC 的連接。</span><span class="sxs-lookup"><span data-stu-id="89a93-110">Lync-Skype connectivity, [publicly available in May 2013](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), relies on the legacy that Lync/Office Communications Server (OCS)/Live Communications Server (LCS) first established with PIC in connecting to MSN/Windows Live, AOL, and Yahoo.</span></span><span data-ttu-id="89a93-111">如需 Lync-Skype 連線的詳細資訊，請參閱 [Lync-Skype 連通性](https://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx)。</span><span class="sxs-lookup"><span data-stu-id="89a93-111">  For more information on Lync-Skype connectivity, see the [Lync-Skype connectivity](https://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx).</span></span> <span data-ttu-id="89a93-112">與 Windows Live、AOL 和 Yahoo 的同盟都是在生命週期結束的路徑上。</span><span class="sxs-lookup"><span data-stu-id="89a93-112">Federation with Windows Live, AOL, and Yahoo are each on a path towards end-of-life.</span></span><span data-ttu-id="89a93-113">此頁面會記錄每個服務的狀態。</span><span class="sxs-lookup"><span data-stu-id="89a93-113"> This page documents the status of each service.</span></span>

<span data-ttu-id="89a93-114">若要使用 PIC，客戶必須啟用每個公用 IM 服務提供者的服務。</span><span class="sxs-lookup"><span data-stu-id="89a93-114">To use PIC, customers have been required to activate the service for each public IM service provider.</span></span> <span data-ttu-id="89a93-115">如何做到這一點的需求和詳細資料，取決於 IM 服務提供者和客戶的基礎授權計畫。</span><span class="sxs-lookup"><span data-stu-id="89a93-115">The requirements and details for how to do this are dependent upon the IM service provider and the customer's underlying licensing program.</span></span>

<div>

## <a name="windows-live-messenger"></a><span data-ttu-id="89a93-116">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="89a93-116">Windows Live Messenger</span></span>

<span data-ttu-id="89a93-117">Microsoft 會讓 Windows Live Messenger 和 Skype 一起運作。</span><span class="sxs-lookup"><span data-stu-id="89a93-117">Microsoft brought Windows Live Messenger and Skype together.</span></span> <span data-ttu-id="89a93-118">在4月2013，Messenger 使用者已遷移到登入的 Skype。</span><span class="sxs-lookup"><span data-stu-id="89a93-118">In April 2013, Messenger users were migrated to Skype upon sign-in.</span></span> <span data-ttu-id="89a93-119">依靠同盟與 Messenger 的 Lync 客戶將繼續與其 Messenger 連絡人進行通訊，即使這些連絡人更新至 Skype，也是如此。</span><span class="sxs-lookup"><span data-stu-id="89a93-119">Lync customers who rely on federation with Messenger will continue to be able to communicate with their Messenger contacts, even after those contacts update to Skype.</span></span> <span data-ttu-id="89a93-120">Lync 系統管理員或 Lync 使用者不需要執行任何動作來維護服務的連續性，而且 Lync 中此功能的管理仍保持與使用信使進行通訊的方式相同。</span><span class="sxs-lookup"><span data-stu-id="89a93-120">There is nothing that Lync administrators or Lync end-users need to do to maintain continuity of service, and management of this capability within Lync remains the same as it has been for communications with Messenger.</span></span> 

<span data-ttu-id="89a93-121">當 Messenger 使用者使用其 Microsoft 帳戶登入 Skype 時 (亦即，Messenger 所用的相同認證) 所有的信使連絡人-包括同盟 Lync 連絡人-遵循 Skype。</span><span class="sxs-lookup"><span data-stu-id="89a93-121">When Messenger users sign into Skype using their Microsoft accounts (i.e., the same credentials used for Messenger) all of their Messenger contacts - including federated Lync contacts - follow them into Skype.</span></span> <span data-ttu-id="89a93-122">您可以使用 Skype 和 Lync 之間的顯示狀態共用和立即訊息。</span><span class="sxs-lookup"><span data-stu-id="89a93-122">Presence sharing and instant messaging between Skype and Lync for these contacts is available.</span></span> 

<span data-ttu-id="89a93-123">Lync-Skype 連線-連絡人的新增、目前狀態共用、立即訊息，以及 Lync 與 Skype 使用者之間的語音通話-現在，所有的 Lync 客戶皆可使用此功能。</span><span class="sxs-lookup"><span data-stu-id="89a93-123">Lync-Skype connectivity - contact adding, presence sharing, instant messaging, and audio calling between Lync and Skype users - is also now available to all Lync customers.</span></span>

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a><span data-ttu-id="89a93-124">雅虎\!</span><span class="sxs-lookup"><span data-stu-id="89a93-124">Yahoo\!</span></span> <span data-ttu-id="89a93-125">和 AOL 立即信使</span><span class="sxs-lookup"><span data-stu-id="89a93-125">and AOL Instant Messenger</span></span>

<span data-ttu-id="89a93-126">使用 Yahoo 的同盟\!</span><span class="sxs-lookup"><span data-stu-id="89a93-126">Federation with Yahoo\!</span></span> <span data-ttu-id="89a93-127">和 AOL 都是在 Lync (和 Office 通訊伺服器) 客戶的使用週期中的路徑。</span><span class="sxs-lookup"><span data-stu-id="89a93-127">and AOL are both on a path toward end-of-life for customers of Lync (and Office Communications Server).</span></span> <span data-ttu-id="89a93-128">Microsoft 提供每項服務的能力都是由 Yahoo 的支援所決定\!</span><span class="sxs-lookup"><span data-stu-id="89a93-128">Microsoft’s ability to provide each of these services has been contingent upon support from Yahoo\!</span></span> <span data-ttu-id="89a93-129">和 AOL，以及這些條款的底層合約會向下纏繞。</span><span class="sxs-lookup"><span data-stu-id="89a93-129">and AOL, and the underlying agreements of these are winding down.</span></span> <span data-ttu-id="89a93-130">這兩個 Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="89a93-130">For both Yahoo\!</span></span> <span data-ttu-id="89a93-131">和 AOL，服務會在2014年6月繼續。</span><span class="sxs-lookup"><span data-stu-id="89a93-131">and AOL, service will continue through June 2014.</span></span>

  - <span data-ttu-id="89a93-132">**Yahoo** -服務會在2014年6月繼續進行，並且客戶會繼續使用 Microsoft LYNC Public IM 連線使用者訂閱授權 ( "PIC USL" ) 獲得授權。</span><span class="sxs-lookup"><span data-stu-id="89a93-132">**Yahoo** - Service will continue through June 2014, and customers continue to need to be licensed with the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”).</span></span><span data-ttu-id="89a93-133">從2012年9月1日起，USL 已無法再購買新的或更新的協定。</span><span class="sxs-lookup"><span data-stu-id="89a93-133">  As of September 1st, 2012, the PIC USL, is no longer available for purchase for new or renewing agreements.</span></span><span data-ttu-id="89a93-134">在此日期之前購買授權的客戶，將可以繼續與 Yahoo 進行同盟\!</span><span class="sxs-lookup"><span data-stu-id="89a93-134">  Customers with licenses purchased prior to this date will be able to continue to federate with Yahoo\!</span></span> <span data-ttu-id="89a93-135">直到之前的服務關閉日期或其授權到期為止。</span><span class="sxs-lookup"><span data-stu-id="89a93-135">until the earlier of the service shut down date or their license expiration.</span></span><span data-ttu-id="89a93-136">閱讀 Lync 小組博客上 [的宣告](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="89a93-136"> Read [the announcement](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) on the Lync Team Blog.</span></span><span data-ttu-id="89a93-137">若客戶在已超過6月30日的合約上使用 PIC 授權，將會以支付于2014年6月 30 2014 日的時段的付款金額為比例，取得學分。</span><span class="sxs-lookup"><span data-stu-id="89a93-137"> Customers who have PIC licenses on agreements that extend past June 30, 2014 will receive a credit in proportion to the amount of the payments covering the time period following June 30, 2014.</span></span>

  - <span data-ttu-id="89a93-138">**AOL** -在2014年6月30日，LYNC 的 IM 連線 ( "PIC" ) 服務將無法再使用。</span><span class="sxs-lookup"><span data-stu-id="89a93-138">**AOL** - On June 30, 2014, Lync's IM connectivity ("PIC") service will no longer be available.</span></span><span data-ttu-id="89a93-139">為了在服務結束時限制客戶的中斷，我們已停止提供額外的客戶網域。</span><span class="sxs-lookup"><span data-stu-id="89a93-139"> In order to limit customer disruption when the service ends, we have discontinued the provisioning of additional customer domains.</span></span> <span data-ttu-id="89a93-140">在2014年6月30日之前，客戶不需要執行任何動作，就能繼續支援與 AIM 的同盟通訊。</span><span class="sxs-lookup"><span data-stu-id="89a93-140">Until June 30, 2014, customers do not need to do anything to continue to support federated communications with AIM.</span></span> <span data-ttu-id="89a93-141">除了這一日期 (或客戶若要在此同時布建其他網域) ，可直接從 AOL 取得替代服務。</span><span class="sxs-lookup"><span data-stu-id="89a93-141">Beyond this date (or for customers that would like to provision additional domains in the meantime), a substitute service is available directly from AOL.</span></span> <span data-ttu-id="89a93-142">如需 AOL 新服務的詳細資訊，請參閱[建立與 AIM 的直接同盟](http://aimenterprise.aol.com/pic.php)    (開啟 AOL.com) 上的新頁面。</span><span class="sxs-lookup"><span data-stu-id="89a93-142">For more information on AOL's new service, see [Establishing Direct Federation with AIM](http://aimenterprise.aol.com/pic.php)  (opens new page on AOL.com).</span></span>  

</div>

<div>

## <a name="public-im-provider-summary"></a><span data-ttu-id="89a93-143">公用 IM 提供者摘要</span><span class="sxs-lookup"><span data-stu-id="89a93-143">Public IM Provider Summary</span></span>

<span data-ttu-id="89a93-144">下表提供公用 IM 服務提供者、具有 Lync 的同盟功能及授權需求的摘要。</span><span class="sxs-lookup"><span data-stu-id="89a93-144">The following table provides a summary of the Public IM service providers, federation capabilities with Lync, and licensing requirements.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89a93-145">公用 IM 服務提供者</span><span class="sxs-lookup"><span data-stu-id="89a93-145">Public IM Service Provider</span></span></th>
<th><span data-ttu-id="89a93-146">同盟功能</span><span class="sxs-lookup"><span data-stu-id="89a93-146">Federated Capabilities</span></span></th>
<th><span data-ttu-id="89a93-147">授權需求</span><span class="sxs-lookup"><span data-stu-id="89a93-147">Licensing Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89a93-148">Skype</span><span class="sxs-lookup"><span data-stu-id="89a93-148">Skype</span></span></p></td>
<td><p><span data-ttu-id="89a93-149">IM、顯示狀態、音訊</span><span class="sxs-lookup"><span data-stu-id="89a93-149">IM, Presence, Audio</span></span></p></td>
<td><p><span data-ttu-id="89a93-150">Lync Server 用戶端存取授權，Lync Online 方案1/2/3</span><span class="sxs-lookup"><span data-stu-id="89a93-150">Lync Server Client Access Licenses, Lync Online Plan 1/2/3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89a93-151">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="89a93-151">Windows Live Messenger</span></span></p></td>
<td><p><span data-ttu-id="89a93-152">IM、目前狀態、Audio/Video</span><span class="sxs-lookup"><span data-stu-id="89a93-152">IM, Presence, Audio/Video</span></span></p></td>
<td><p><span data-ttu-id="89a93-153"> (支援 Lync Server 用戶端存取授權，只要 WLM 位於市場) </span><span class="sxs-lookup"><span data-stu-id="89a93-153">Lync Server Client Access Licenses (supported as long as WLM is in market)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89a93-154">Aol</span><span class="sxs-lookup"><span data-stu-id="89a93-154">AOL</span></span></p></td>
<td><p><span data-ttu-id="89a93-155">IM、目前狀態</span><span class="sxs-lookup"><span data-stu-id="89a93-155">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="89a93-156">Lync Server 用戶端存取授權;支援現有客戶2014年6月。</span><span class="sxs-lookup"><span data-stu-id="89a93-156">Lync Server Client Access Licenses; supported through June 2014 for existing customers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89a93-157">雅虎！</span><span class="sxs-lookup"><span data-stu-id="89a93-157">Yahoo!</span></span></p></td>
<td><p><span data-ttu-id="89a93-158">IM、目前狀態</span><span class="sxs-lookup"><span data-stu-id="89a93-158">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="89a93-159">除了 Lync Server 用戶端存取授權之外，還需要額外的 Microsoft Lync Public IM 連線使用者訂閱授權 ( "PIC USL" ) 。</span><span class="sxs-lookup"><span data-stu-id="89a93-159">Requires additional Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) in addition to Lync Server Client Access Licences.</span></span> <span data-ttu-id="89a93-160">從2012年9月的標價，PIC USL 已無法再供購買。</span><span class="sxs-lookup"><span data-stu-id="89a93-160">As of the September 2012 Price List, the PIC USL is no longer available for purchase.</span></span> <span data-ttu-id="89a93-161">具有有效授權的客戶可以繼續與 Yahoo！進行同盟</span><span class="sxs-lookup"><span data-stu-id="89a93-161">Customers with active licenses are able to continue to federate with Yahoo!</span></span> <span data-ttu-id="89a93-162">在2014年6月30日，直到服務關閉日期為止。</span><span class="sxs-lookup"><span data-stu-id="89a93-162">Messenger until the service shut down date on June 30, 2014.</span></span></p></td>
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


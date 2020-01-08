---
title: Lync Server 2013：行動用戶端部署處理常式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobile client deployment process
ms:assetid: 6498235b-2fa9-421d-bfa0-0ccc09508dbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690982(v=OCS.15)
ms:contentKeyID: 51541484
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0d0bf17fe4906d49fefd8bd319d25d1268191e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="e084c-102">Lync Server 2013 中的行動用戶端部署程式</span><span class="sxs-lookup"><span data-stu-id="e084c-102">Mobile client deployment process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e084c-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="e084c-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="e084c-104">完成 Microsoft Lync Server 2013 的部署之後，使用者就可以從行動市場安裝 Lync 2013 應用程式，他們習慣用來供其特定裝置使用。</span><span class="sxs-lookup"><span data-stu-id="e084c-104">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="e084c-105">Lync 行動裝置部署程式</span><span class="sxs-lookup"><span data-stu-id="e084c-105">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e084c-106">分</span><span class="sxs-lookup"><span data-stu-id="e084c-106">Phase</span></span></th>
<th><span data-ttu-id="e084c-107">步驟</span><span class="sxs-lookup"><span data-stu-id="e084c-107">Steps</span></span></th>
<th><span data-ttu-id="e084c-108">許可權</span><span class="sxs-lookup"><span data-stu-id="e084c-108">Permissions</span></span></th>
<th><span data-ttu-id="e084c-109">文件</span><span class="sxs-lookup"><span data-stu-id="e084c-109">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e084c-110">執行預先設定的工作。</span><span class="sxs-lookup"><span data-stu-id="e084c-110">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="e084c-111">驗證 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="e084c-111">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="e084c-112">驗證憑證需求。</span><span class="sxs-lookup"><span data-stu-id="e084c-112">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e084c-113">許可權</span><span class="sxs-lookup"><span data-stu-id="e084c-113">Administrator</span></span></p></td>
<td><p><span data-ttu-id="e084c-114">在伺服器規劃檔的<a href="lync-server-2013-planning-for-mobility.md">Lync Server 2013 中規劃行動</a>。</span><span class="sxs-lookup"><span data-stu-id="e084c-114"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="e084c-115">在伺服器部署檔的<a href="lync-server-2013-deploying-mobility.md">Lync Server 2013 中部署行動</a>。</span><span class="sxs-lookup"><span data-stu-id="e084c-115"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="e084c-116">伺服器規劃檔中<a href="lync-server-2013-certificate-infrastructure-requirements.md">Lync Server 2013 的憑證基礎結構需求</a>。</span><span class="sxs-lookup"><span data-stu-id="e084c-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e084c-117">在測試裝置上安裝 Lync 應用程式。</span><span class="sxs-lookup"><span data-stu-id="e084c-117">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="e084c-118">安裝必備元件。</span><span class="sxs-lookup"><span data-stu-id="e084c-118">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="e084c-119">從適用于行動裝置的 marketplace 進行安裝。</span><span class="sxs-lookup"><span data-stu-id="e084c-119">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e084c-120">許可權</span><span class="sxs-lookup"><span data-stu-id="e084c-120">Administrator</span></span></p></td>
<td><p><span data-ttu-id="e084c-121">在<a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013 中部署行動用戶端</a>的行動裝置專用的安裝指示。</span><span class="sxs-lookup"><span data-stu-id="e084c-121">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e084c-122">設定用戶端。</span><span class="sxs-lookup"><span data-stu-id="e084c-122">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e084c-123">設定登入設定和伺服器資訊。</span><span class="sxs-lookup"><span data-stu-id="e084c-123">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e084c-124">許可權</span><span class="sxs-lookup"><span data-stu-id="e084c-124">Administrator</span></span></p></td>
<td><p><span data-ttu-id="e084c-125"><a href="lync-server-2013-deploying-mobile-clients.md">在 Lync Server 2013 中部署行動用戶端</a></span><span class="sxs-lookup"><span data-stu-id="e084c-125"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e084c-126">測試行動案例。</span><span class="sxs-lookup"><span data-stu-id="e084c-126">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="e084c-127">測試立即訊息（IM）與目前狀態。</span><span class="sxs-lookup"><span data-stu-id="e084c-127">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="e084c-128">測試撥出式會議。</span><span class="sxs-lookup"><span data-stu-id="e084c-128">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="e084c-129">在公司目錄中搜尋連絡人。</span><span class="sxs-lookup"><span data-stu-id="e084c-129">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="e084c-130">測試推播通知。</span><span class="sxs-lookup"><span data-stu-id="e084c-130">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e084c-131">許可權</span><span class="sxs-lookup"><span data-stu-id="e084c-131">Administrator</span></span></p></td>
<td><p><span data-ttu-id="e084c-132">在<a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013 中部署行動用戶端</a>之行動裝置專用的驗證指示。</span><span class="sxs-lookup"><span data-stu-id="e084c-132">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e084c-133">在行動電話上安裝 Lync 應用程式。</span><span class="sxs-lookup"><span data-stu-id="e084c-133">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="e084c-134">安裝必備元件。</span><span class="sxs-lookup"><span data-stu-id="e084c-134">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="e084c-135">從適用于行動裝置的 marketplace 進行安裝。</span><span class="sxs-lookup"><span data-stu-id="e084c-135">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e084c-136">使用者</span><span class="sxs-lookup"><span data-stu-id="e084c-136">User</span></span></p></td>
<td><p><span data-ttu-id="e084c-137">在<a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013 中部署行動用戶端</a>的行動裝置專用的安裝指示。</span><span class="sxs-lookup"><span data-stu-id="e084c-137">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：行動用戶端部署程式
description: Lync Server 2013：行動用戶端部署程式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobile client deployment process
ms:assetid: 6498235b-2fa9-421d-bfa0-0ccc09508dbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690982(v=OCS.15)
ms:contentKeyID: 51541484
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fa4e9e1d272915e06009df5c06480309ce104e0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563479"
---
# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="9b0b9-103">Lync Server 2013 中的行動用戶端部署程式</span><span class="sxs-lookup"><span data-stu-id="9b0b9-103">Mobile client deployment process in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b0b9-104">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="9b0b9-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="9b0b9-105">完成 Microsoft Lync Server 2013 的部署之後，使用者可以從行動市場安裝 Lync 2013 應用程式，而這些應用程式習慣于用於其特定裝置。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-105">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="9b0b9-106">Lync 行動部署程序</span><span class="sxs-lookup"><span data-stu-id="9b0b9-106">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b0b9-107">階段</span><span class="sxs-lookup"><span data-stu-id="9b0b9-107">Phase</span></span></th>
<th><span data-ttu-id="9b0b9-108">步驟</span><span class="sxs-lookup"><span data-stu-id="9b0b9-108">Steps</span></span></th>
<th><span data-ttu-id="9b0b9-109">權限</span><span class="sxs-lookup"><span data-stu-id="9b0b9-109">Permissions</span></span></th>
<th><span data-ttu-id="9b0b9-110">文件</span><span class="sxs-lookup"><span data-stu-id="9b0b9-110">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b0b9-111">執行預先設定工作。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-111">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="9b0b9-112">驗證 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-112">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="9b0b9-113">確認憑證需求。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-113">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="9b0b9-114">系統管理員</span><span class="sxs-lookup"><span data-stu-id="9b0b9-114">Administrator</span></span></p></td>
<td><p><span data-ttu-id="9b0b9-115">在 [伺服器規劃] 檔中<a href="lync-server-2013-planning-for-mobility.md">規劃 Lync Server 2013 中的行動性</a>。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-115"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="9b0b9-116">在伺服器部署檔中的<a href="lync-server-2013-deploying-mobility.md">Lync Server 2013 部署行動性</a>。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-116"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="9b0b9-117">伺服器規劃檔中的<a href="lync-server-2013-certificate-infrastructure-requirements.md">Lync Server 2013 的憑證基礎結構需求</a>。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-117"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b0b9-118">在測試裝置上安裝 Lync 應用程式。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-118">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="9b0b9-119">安裝先決條件。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-119">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="9b0b9-120">從行動裝置特定的市場來安裝。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-120">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="9b0b9-121">系統管理員</span><span class="sxs-lookup"><span data-stu-id="9b0b9-121">Administrator</span></span></p></td>
<td><p><span data-ttu-id="9b0b9-122">在 <a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013 中部署行動用戶端</a>時，特定于行動裝置的安裝指示。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-122">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b0b9-123">設定用戶端。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-123">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9b0b9-124">設定登入設定和伺服器資訊。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-124">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9b0b9-125">系統管理員</span><span class="sxs-lookup"><span data-stu-id="9b0b9-125">Administrator</span></span></p></td>
<td><p><span data-ttu-id="9b0b9-126"><a href="lync-server-2013-deploying-mobile-clients.md">在 Lync Server 2013 中部署行動用戶端</a></span><span class="sxs-lookup"><span data-stu-id="9b0b9-126"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b0b9-127">測試行動案例。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-127">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="9b0b9-128">測試立即訊息 (IM) 及顯示狀態。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-128">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="9b0b9-129">測試電話撥出式會議。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-129">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="9b0b9-130">在公司目錄中搜尋連絡人。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-130">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="9b0b9-131">測試推入通知。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-131">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="9b0b9-132">系統管理員</span><span class="sxs-lookup"><span data-stu-id="9b0b9-132">Administrator</span></span></p></td>
<td><p><span data-ttu-id="9b0b9-133">在 <a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013 中部署行動用戶端</a>時，特定于行動裝置的驗證指示。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-133">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b0b9-134">在行動電話上安裝 Lync 應用程式。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-134">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="9b0b9-135">安裝先決條件。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-135">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="9b0b9-136">從行動裝置特定的市場來安裝。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-136">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="9b0b9-137">使用者</span><span class="sxs-lookup"><span data-stu-id="9b0b9-137">User</span></span></p></td>
<td><p><span data-ttu-id="9b0b9-138">在 <a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013 中部署行動用戶端</a>時，特定于行動裝置的安裝指示。</span><span class="sxs-lookup"><span data-stu-id="9b0b9-138">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


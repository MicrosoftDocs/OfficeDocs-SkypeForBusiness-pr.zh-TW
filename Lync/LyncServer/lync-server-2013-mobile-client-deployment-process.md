---
title: Lync Server 2013： 行動用戶端部署程序
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
ms.openlocfilehash: 9b24ade528d40a80cac4870e02c656ba97f4143a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="a9cc3-102">Lync Server 2013 中的行動用戶端部署程序</span><span class="sxs-lookup"><span data-stu-id="a9cc3-102">Mobile client deployment process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9cc3-103">_**上次修改主題：** 2013年-02-20 個_</span><span class="sxs-lookup"><span data-stu-id="a9cc3-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="a9cc3-104">Microsoft Lync Server 2013 的部署完成後，使用者可以從他們以熟悉他們的特定裝置的行動市集安裝 Lync 2013 應用程式。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-104">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="a9cc3-105">Lync 行動部署程序</span><span class="sxs-lookup"><span data-stu-id="a9cc3-105">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9cc3-106">階段</span><span class="sxs-lookup"><span data-stu-id="a9cc3-106">Phase</span></span></th>
<th><span data-ttu-id="a9cc3-107">步驟</span><span class="sxs-lookup"><span data-stu-id="a9cc3-107">Steps</span></span></th>
<th><span data-ttu-id="a9cc3-108">權限</span><span class="sxs-lookup"><span data-stu-id="a9cc3-108">Permissions</span></span></th>
<th><span data-ttu-id="a9cc3-109">文件</span><span class="sxs-lookup"><span data-stu-id="a9cc3-109">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9cc3-110">執行預先設定工作。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-110">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="a9cc3-111">確認 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-111">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="a9cc3-112">確認憑證需求。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-112">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="a9cc3-113">系統管理員</span><span class="sxs-lookup"><span data-stu-id="a9cc3-113">Administrator</span></span></p></td>
<td><p><span data-ttu-id="a9cc3-114">伺服器規劃文件中的<a href="lync-server-2013-planning-for-mobility.md">Planning for Lync Server 2013 中的行動性</a>。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-114"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="a9cc3-115"><a href="lync-server-2013-deploying-mobility.md">部署 Lync Server 2013 中的行動性</a>中的伺服器部署文件。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-115"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="a9cc3-116">伺服器規劃文件中<a href="lync-server-2013-certificate-infrastructure-requirements.md">的 Lync Server 2013 的憑證基礎結構需求</a>。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9cc3-117">在測試裝置上安裝 Lync 應用程式。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-117">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="a9cc3-118">安裝先決條件。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-118">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="a9cc3-119">從行動裝置特定的市場來安裝。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-119">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="a9cc3-120">系統管理員</span><span class="sxs-lookup"><span data-stu-id="a9cc3-120">Administrator</span></span></p></td>
<td><p><span data-ttu-id="a9cc3-121"><a href="lync-server-2013-deploying-mobile-clients.md">部署 Lync Server 2013 中的行動用戶端</a>的行動裝置特定的安裝指示。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-121">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9cc3-122">設定用戶端。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-122">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a9cc3-123">設定登入設定和伺服器資訊。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-123">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a9cc3-124">系統管理員</span><span class="sxs-lookup"><span data-stu-id="a9cc3-124">Administrator</span></span></p></td>
<td><p><span data-ttu-id="a9cc3-125"><a href="lync-server-2013-deploying-mobile-clients.md">部署 Lync Server 2013 中的行動用戶端</a></span><span class="sxs-lookup"><span data-stu-id="a9cc3-125"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9cc3-126">測試行動案例。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-126">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="a9cc3-127">測試立即訊息 (IM) 和目前狀態。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-127">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="a9cc3-128">測試電話撥出式會議。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-128">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="a9cc3-129">在公司目錄中搜尋連絡人。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-129">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="a9cc3-130">測試推入通知。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-130">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="a9cc3-131">系統管理員</span><span class="sxs-lookup"><span data-stu-id="a9cc3-131">Administrator</span></span></p></td>
<td><p><span data-ttu-id="a9cc3-132"><a href="lync-server-2013-deploying-mobile-clients.md">部署 Lync Server 2013 中的行動用戶端</a>的行動裝置特定的驗證指示。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-132">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9cc3-133">在行動電話上安裝 Lync 應用程式。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-133">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="a9cc3-134">安裝先決條件。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-134">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="a9cc3-135">從行動裝置特定的市場來安裝。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-135">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="a9cc3-136">使用者</span><span class="sxs-lookup"><span data-stu-id="a9cc3-136">User</span></span></p></td>
<td><p><span data-ttu-id="a9cc3-137"><a href="lync-server-2013-deploying-mobile-clients.md">部署 Lync Server 2013 中的行動用戶端</a>的行動裝置特定的安裝指示。</span><span class="sxs-lookup"><span data-stu-id="a9cc3-137">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


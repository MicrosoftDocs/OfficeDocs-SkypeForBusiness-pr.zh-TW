---
title: Lync Server 2013：準備及部署 Lync Server 混合式環境的步驟
description: Lync Server 2013：準備及部署 Lync Server 混合式環境的步驟。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffb791a8a45b2220d8987c8d688f346447747c00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546329"
---
# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a><span data-ttu-id="78a47-103">準備及部署 Lync Server 2013 混合式環境的步驟</span><span class="sxs-lookup"><span data-stu-id="78a47-103">Steps to prepare and deploy Lync Server 2013 hybrid environment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78a47-104">_**主題上次修改日期：** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="78a47-104">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="78a47-105">下表列出使用商務用 Skype Online 和 Microsoft Office 365 為混合式部署準備環境所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="78a47-105">The following table lists the steps required to prepare your environment for a hybrid deployment with Skype for Business Online and Microsoft Office 365.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78a47-106">完成？</span><span class="sxs-lookup"><span data-stu-id="78a47-106">Completed?</span></span></th>
<th><span data-ttu-id="78a47-107">步驟</span><span class="sxs-lookup"><span data-stu-id="78a47-107">Step</span></span></th>
<th><span data-ttu-id="78a47-108">描述</span><span class="sxs-lookup"><span data-stu-id="78a47-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="78a47-109">建立 Office 365 的租使用者帳戶並啟用 Lync Online</span><span class="sxs-lookup"><span data-stu-id="78a47-109">Create a tenant account for Office 365 and enable Lync Online</span></span></p></td>
<td><p><span data-ttu-id="78a47-110">深入瞭解 Office 365 和 Lync Online （ <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">office 365</a>）。</span><span class="sxs-lookup"><span data-stu-id="78a47-110">Learn about Office 365 and Lync Online at <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">Office 365</a>.</span></span></p>
<p><span data-ttu-id="78a47-111">若要確定您的環境已準備好用於 Office 365，請參閱 <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">系統需求</a>。</span><span class="sxs-lookup"><span data-stu-id="78a47-111">To make sure that your environment is ready for Office 365, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">System Requirements</a>.</span></span></p>
<p><span data-ttu-id="78a47-112">如需設定 Office 365 的詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">office 365 快速入門</a> 和 <a href="https://go.microsoft.com/fwlink/p/?linkid=254979">設定 Office 365</a>。</span><span class="sxs-lookup"><span data-stu-id="78a47-112">For details about setting up Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Getting Started with Office 365</a> and <a href="https://go.microsoft.com/fwlink/p/?linkid=254979">Set Up Office 365</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="78a47-113">新增您的網域並驗證擁有權</span><span class="sxs-lookup"><span data-stu-id="78a47-113">Add your domain and verify ownership</span></span></p></td>
<td><p><span data-ttu-id="78a47-114">您的網域有時也稱為您的 <em>虛名網域</em>。</span><span class="sxs-lookup"><span data-stu-id="78a47-114">Your domain is sometimes also referred to as your <em>vanity domain</em>.</span></span> <span data-ttu-id="78a47-115">您必須將您的網域新增至 Office 365 組織，然後依照步驟驗證使用 Office 365 的網域。</span><span class="sxs-lookup"><span data-stu-id="78a47-115">You must add your domain to your Office 365 organization, and then follow the steps to validate the domain with Office 365.</span></span> <span data-ttu-id="78a47-116">這是確認您是網域的擁有者。</span><span class="sxs-lookup"><span data-stu-id="78a47-116">This is to confirm that you are the owner of the domain.</span></span></p>
<p><span data-ttu-id="78a47-117">若要將您的網域新增至 Office 365 組織，請遵循在 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">將您的網域新增至 office 365</a>] 中所述的步驟。</span><span class="sxs-lookup"><span data-stu-id="78a47-117">To add your domain to your Office 365 organization, follow the steps described at <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">Add your domain to Office 365</a>.</span></span></p>
<p><span data-ttu-id="78a47-118">完成主題中每一個區段中的所有步驟，包括 &quot; 為您的 Office 365 服務編輯 DNS 記錄。&quot;</span><span class="sxs-lookup"><span data-stu-id="78a47-118">Complete all of the steps in each section in the topic, including &quot;Edit DNS records for your Office 365 services.&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="78a47-119">驗證環境準備</span><span class="sxs-lookup"><span data-stu-id="78a47-119">Verify environment readiness</span></span></p></td>
<td><p><span data-ttu-id="78a47-120">您可以使用 Office 365 設定助理來協助您部署 Office 365。</span><span class="sxs-lookup"><span data-stu-id="78a47-120">You can use the Office 365 Setup Assistant to help you deploy Office 365.</span></span> <span data-ttu-id="78a47-121">如需詳細資訊，請參閱<a href="https://go.microsoft.com/fwlink/p/?linkid=254985">使用設定助理來決定 Office 365 的準備</a></span><span class="sxs-lookup"><span data-stu-id="78a47-121">For more information, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">Use Setup Assistant to determine Office 365 readiness</a>.</span></span></p>
<p><span data-ttu-id="78a47-122">如需使用工具及部署 Office 365 的詳細資訊，請參閱《 <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">office 365 部署指南》</a>。</span><span class="sxs-lookup"><span data-stu-id="78a47-122">For details about using the tool and deploying Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Office 365 deployment guide</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="78a47-123">準備 Active Directory 同步處理</span><span class="sxs-lookup"><span data-stu-id="78a47-123">Prepare for Active Directory synchronization</span></span></p></td>
<td><p><span data-ttu-id="78a47-124">Active Directory 同步處理會使您的內部部署 Active Directory 持續與 Office 365 保持同步。</span><span class="sxs-lookup"><span data-stu-id="78a47-124">Active Directory synchronization keeps your on-premises Active Directory continuously synchronized with Office 365.</span></span> <span data-ttu-id="78a47-125">這可讓您建立每個使用者帳戶和群組的同步處理版本，也可讓全域通訊清單 (GAL) 從您當地的 Microsoft Exchange Server 環境同步處理至 Microsoft Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="78a47-125">This lets you create synchronized versions of each user account and group, and also enables global address list (GAL) synchronization from your local Microsoft Exchange Server environment to Microsoft Exchange Online.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="78a47-126">您必須在內部部署和線上 Lync 部署之間同步處理組織內所有 Lync 使用者的 AD 帳戶，即使使用者未移至 Lync Online 也是一樣。</span><span class="sxs-lookup"><span data-stu-id="78a47-126">You need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="78a47-127">如果您未同步處理所有使用者，組織中內部部署與線上使用者之間的通訊可能無法如預期的方式運作。</span><span class="sxs-lookup"><span data-stu-id="78a47-127">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>


</div>
<p><span data-ttu-id="78a47-128">若要準備環境以進行 Active Directory 同步處理，請遵循 <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">目錄同步處理藍圖</a>中所述的步驟，包括設定單一登入。</span><span class="sxs-lookup"><span data-stu-id="78a47-128">To prepare your environment for Active Directory synchronization, follow the steps described in <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">Directory synchronization Roadmap</a>, including setting up single sign-on.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="78a47-129">建立 Active Directory Federation Services (AD FS 的憑證) </span><span class="sxs-lookup"><span data-stu-id="78a47-129">Create certificates for Active Directory Federation Services (AD FS)</span></span></p></td>
<td><p><span data-ttu-id="78a47-130">您將需要建立憑證，以用於與 Office 365 的身分識別同盟。</span><span class="sxs-lookup"><span data-stu-id="78a47-130">You will need to create the certificates that are used for identity federation with Office 365.</span></span> <span data-ttu-id="78a47-131">如需詳細資訊，請參閱規劃及部署 AD FS 的「同盟伺服器憑證」一節，以與單一登入主題搭配使用， <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">檢查清單：使用 AD fs 來執行和管理單一登入</a>。</span><span class="sxs-lookup"><span data-stu-id="78a47-131">For more information, see the “Federation server certificates” section of the Plan for and deploy AD FS for use with single sign-on topic at <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">Checklist: Use AD FS to implement and manage single sign-on</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="78a47-132">指派 AD FS 的憑證</span><span class="sxs-lookup"><span data-stu-id="78a47-132">Assign certificates for AD FS</span></span></p></td>
<td><p><span data-ttu-id="78a47-133">在您建立用於身分識別同盟與 Office 365 的憑證之後，您必須安裝並指派這些憑證。</span><span class="sxs-lookup"><span data-stu-id="78a47-133">After you create the certificates that are used for identity federation with Office 365, you must install and assign them.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="78a47-134">將試驗使用者移至商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="78a47-134">Move pilot users to Skype for Business Online</span></span></p></td>
<td><p><span data-ttu-id="78a47-135">在您完成準備及設定商務用 Skype Online 環境的步驟之後，您可以開始將試驗使用者移至 Lync Online。</span><span class="sxs-lookup"><span data-stu-id="78a47-135">After you have completed the steps to prepare and configure your environment for Skype for Business Online, you can start moving pilot users to Lync Online.</span></span></p>
<p><span data-ttu-id="78a47-136">請參閱 <a href="lync-server-2013-move-users-to-lync-online.md">在 Lync Server 2013 中將使用者移至 Lync Online</a>。</span><span class="sxs-lookup"><span data-stu-id="78a47-136">See <a href="lync-server-2013-move-users-to-lync-online.md">Move users to Lync Online in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="78a47-137">在混合式部署中管理使用者</span><span class="sxs-lookup"><span data-stu-id="78a47-137">Administering users in a hybrid deployment</span></span></p></td>
<td><p><span data-ttu-id="78a47-138">如需如何在混合式部署中管理使用者的詳細資訊，請參閱 <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">在混合 Lync Server 2013 部署中管理使用者</a>。</span><span class="sxs-lookup"><span data-stu-id="78a47-138">For details about how to administer users in a hybrid deployment, see <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：準備與部署 Lync Server 混合式環境的步驟
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
ms.openlocfilehash: 6ebcce8d0021789a409c8f41b5f635d82284b7bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a><span data-ttu-id="2a5fc-102">準備與部署 Lync Server 2013 混合式環境的步驟</span><span class="sxs-lookup"><span data-stu-id="2a5fc-102">Steps to prepare and deploy Lync Server 2013 hybrid environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a5fc-103">_**主題上次修改日期：** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="2a5fc-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="2a5fc-104">下表列出使用商務用 Skype Online 和 Microsoft Office 365 為混合式部署準備環境所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-104">The following table lists the steps required to prepare your environment for a hybrid deployment with Skype for Business Online and Microsoft Office 365.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a5fc-105">完畢?</span><span class="sxs-lookup"><span data-stu-id="2a5fc-105">Completed?</span></span></th>
<th><span data-ttu-id="2a5fc-106">循序漸進</span><span class="sxs-lookup"><span data-stu-id="2a5fc-106">Step</span></span></th>
<th><span data-ttu-id="2a5fc-107">說明</span><span class="sxs-lookup"><span data-stu-id="2a5fc-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="2a5fc-108">建立 Office 365 的租使用者帳戶並啟用 Lync Online</span><span class="sxs-lookup"><span data-stu-id="2a5fc-108">Create a tenant account for Office 365 and enable Lync Online</span></span></p></td>
<td><p><span data-ttu-id="2a5fc-109">在<a href="https://go.microsoft.com/fwlink/p/?linkid=254980">office 365</a>上瞭解 office 365 和 Lync Online。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-109">Learn about Office 365 and Lync Online at <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">Office 365</a>.</span></span></p>
<p><span data-ttu-id="2a5fc-110">若要確定您的環境已準備好進行 Office 365，請參閱<a href="https://go.microsoft.com/fwlink/p/?linkid=401408">系統需求</a>。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-110">To make sure that your environment is ready for Office 365, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">System Requirements</a>.</span></span></p>
<p><span data-ttu-id="2a5fc-111">如需設定 Office 365 的詳細資訊，請參閱<a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Office 365 快速入門</a>及<a href="http://go.microsoft.com/fwlink/p/?linkid=254979">設定 office 365</a>。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-111">For details about setting up Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Getting Started with Office 365</a> and <a href="http://go.microsoft.com/fwlink/p/?linkid=254979">Set Up Office 365</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="2a5fc-112">新增您的網域並驗證擁有權</span><span class="sxs-lookup"><span data-stu-id="2a5fc-112">Add your domain and verify ownership</span></span></p></td>
<td><p><span data-ttu-id="2a5fc-113">您的網域有時也稱為您的<em>vanity 網域</em>。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-113">Your domain is sometimes also referred to as your <em>vanity domain</em>.</span></span> <span data-ttu-id="2a5fc-114">您必須將您的網域新增至您的 Office 365 租使用者，然後依照步驟使用 Office 365 驗證網域。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-114">You must add your domain to your Office 365 tenant, and then follow the steps to validate the domain with Office 365.</span></span> <span data-ttu-id="2a5fc-115">這是為了確認您是網域的擁有者。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-115">This is to confirm that you are the owner of the domain.</span></span></p>
<p><span data-ttu-id="2a5fc-116">若要將您的網域新增至您的 Office 365 租使用者，請依照<a href="https://go.microsoft.com/fwlink/p/?linkid=254983">將您的網域新增至 office 365</a>中所述的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-116">To add your domain to your Office 365 tenant, follow the steps described at <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">Add your domain to Office 365</a>.</span></span></p>
<p><span data-ttu-id="2a5fc-117">完成主題中每一節中的所有步驟，包括&quot;編輯 Office 365 服務的 DNS 記錄。&quot;</span><span class="sxs-lookup"><span data-stu-id="2a5fc-117">Complete all of the steps in each section in the topic, including &quot;Edit DNS records for your Office 365 services.&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="2a5fc-118">驗證環境就緒性</span><span class="sxs-lookup"><span data-stu-id="2a5fc-118">Verify environment readiness</span></span></p></td>
<td><p><span data-ttu-id="2a5fc-119">您可以使用 Office 365 設定助理來協助您部署 Office 365。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-119">You can use the Office 365 Setup Assistant to help you deploy Office 365.</span></span> <span data-ttu-id="2a5fc-120">如需詳細資訊，請參閱<a href="https://go.microsoft.com/fwlink/p/?linkid=254985">使用設定助理來判斷 Office 365 準備就緒</a>。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-120">For more information, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">Use Setup Assistant to determine Office 365 readiness</a>.</span></span></p>
<p><span data-ttu-id="2a5fc-121">如需使用工具和部署 Office 365 的詳細資料，請參閱<a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Office 365 部署指南</a>。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-121">For details about using the tool and deploying Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Office 365 deployment guide</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="2a5fc-122">準備 Active Directory 同步處理</span><span class="sxs-lookup"><span data-stu-id="2a5fc-122">Prepare for Active Directory synchronization</span></span></p></td>
<td><p><span data-ttu-id="2a5fc-123">Active Directory 同步處理可讓您的內部部署 Active Directory 持續與 Office 365 保持同步。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-123">Active Directory synchronization keeps your on-premises Active Directory continuously synchronized with Office 365.</span></span> <span data-ttu-id="2a5fc-124">這可讓您建立每個使用者帳戶和群組的同步處理版本，也可從您的本機 Microsoft Exchange Server 環境將全域通訊清單（GAL）同步處理到 Microsoft Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-124">This lets you create synchronized versions of each user account and group, and also enables global address list (GAL) synchronization from your local Microsoft Exchange Server environment to Microsoft Exchange Online.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="2a5fc-125">您必須在內部部署和線上 Lync 部署之間，將組織中所有 Lync 使用者的廣告帳戶同步處理，即使使用者未移至 Lync Online 也一樣。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-125">You need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="2a5fc-126">如果您不同步處理所有使用者，貴組織中內部部署與線上使用者之間的通訊可能無法如期運作。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-126">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>


</div>
<p><span data-ttu-id="2a5fc-127">若要為您的環境準備作用中的 Active Directory 同步處理，請遵循<a href="https://go.microsoft.com/fwlink/p/?linkid=254988">目錄同步處理藍圖</a>中所述的步驟，包括設定單一登入。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-127">To prepare your environment for Active Directory synchronization, follow the steps described in <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">Directory synchronization Roadmap</a>, including setting up single sign-on.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="2a5fc-128">建立 Active Directory 同盟服務（AD FS）的憑證</span><span class="sxs-lookup"><span data-stu-id="2a5fc-128">Create certificates for Active Directory Federation Services (AD FS)</span></span></p></td>
<td><p><span data-ttu-id="2a5fc-129">您必須建立與 Office 365 搭配使用身分識別聯盟的憑證。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-129">You will need to create the certificates that are used for identity federation with Office 365.</span></span> <span data-ttu-id="2a5fc-130">如需詳細資訊，請參閱與部署 AD FS 之方案的 [同盟伺服器憑證] 一節，以在檢查清單中與單一登入主題搭配使用<a href="https://go.microsoft.com/fwlink/p/?linkid=285376">：使用 [AD FS] 來執行和管理單一登入</a>。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-130">For more information, see the “Federation server certificates” section of the Plan for and deploy AD FS for use with single sign-on topic at <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">Checklist: Use AD FS to implement and manage single sign-on</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="2a5fc-131">指派 AD FS 的憑證</span><span class="sxs-lookup"><span data-stu-id="2a5fc-131">Assign certificates for AD FS</span></span></p></td>
<td><p><span data-ttu-id="2a5fc-132">建立與 Office 365 搭配身分識別聯盟的憑證之後，您必須安裝並指派這些憑證。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-132">After you create the certificates that are used for identity federation with Office 365, you must install and assign them.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="2a5fc-133">將試驗使用者移至商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="2a5fc-133">Move pilot users to Skype for Business Online</span></span></p></td>
<td><p><span data-ttu-id="2a5fc-134">完成準備及設定商務用 Skype Online 的環境步驟之後，您就可以開始將試點使用者移至 Lync Online。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-134">After you have completed the steps to prepare and configure your environment for Skype for Business Online, you can start moving pilot users to Lync Online.</span></span></p>
<p><span data-ttu-id="2a5fc-135">請參閱<a href="lync-server-2013-move-users-to-lync-online.md">在 Lync Server 2013 中將使用者移至 Lync Online</a>。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-135">See <a href="lync-server-2013-move-users-to-lync-online.md">Move users to Lync Online in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="2a5fc-136">在混合式部署中管理使用者</span><span class="sxs-lookup"><span data-stu-id="2a5fc-136">Administering users in a hybrid deployment</span></span></p></td>
<td><p><span data-ttu-id="2a5fc-137">如需如何在混合式部署中管理使用者的詳細資料，請參閱<a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">在混合式 Lync Server 2013 部署中管理使用者</a>。</span><span class="sxs-lookup"><span data-stu-id="2a5fc-137">For details about how to administer users in a hybrid deployment, see <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


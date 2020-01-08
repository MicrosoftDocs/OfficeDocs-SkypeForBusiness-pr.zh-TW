---
title: Lync Server 2013：支援的 Active Directory 拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc15cea3d07dc4e00f1d2a5527c862d90a078c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-active-directory-topologies-in-lync-server-2013"></a><span data-ttu-id="7ef49-102">Lync Server 2013 中支援的 Active Directory 拓撲</span><span class="sxs-lookup"><span data-stu-id="7ef49-102">Supported Active Directory topologies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ef49-103">_**主題上次修改日期：** 2014-10-02_</span><span class="sxs-lookup"><span data-stu-id="7ef49-103">_**Topic Last Modified:** 2014-10-02_</span></span>

<span data-ttu-id="7ef49-104">Lync Server 2013 支援與 Microsoft Lync Server 2010 和 Microsoft Office 通訊伺服器 2007 R2 相同的 Active Directory 網域服務拓撲。</span><span class="sxs-lookup"><span data-stu-id="7ef49-104">Lync Server 2013 supports the same Active Directory Domain Services topologies as Microsoft Lync Server 2010 and Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="7ef49-105">支援下列拓撲：</span><span class="sxs-lookup"><span data-stu-id="7ef49-105">The following topologies are supported:</span></span>

  - <span data-ttu-id="7ef49-106">單一目錄林與單一網域</span><span class="sxs-lookup"><span data-stu-id="7ef49-106">Single forest with single domain</span></span>

  - <span data-ttu-id="7ef49-107">具有單一樹狀結構和多個網域的單一目錄林</span><span class="sxs-lookup"><span data-stu-id="7ef49-107">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="7ef49-108">具有多個樹和不連續命名空間的單一目錄林</span><span class="sxs-lookup"><span data-stu-id="7ef49-108">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="7ef49-109">中央目錄林拓撲中的多個林</span><span class="sxs-lookup"><span data-stu-id="7ef49-109">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="7ef49-110">資原始目錄林拓朴中的多個目錄林</span><span class="sxs-lookup"><span data-stu-id="7ef49-110">Multiple forests in a resource forest topology</span></span>

  - <span data-ttu-id="7ef49-111">使用 Exchange Online 的 Lync 資原始目錄林拓撲結構中有多個目錄林</span><span class="sxs-lookup"><span data-stu-id="7ef49-111">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="7ef49-112">下圖說明本節中的圖例所使用的圖示。</span><span class="sxs-lookup"><span data-stu-id="7ef49-112">The following figure identifies the icons used in the illustrations in this section.</span></span>

<span data-ttu-id="7ef49-113">**拓撲圖例索引**</span><span class="sxs-lookup"><span data-stu-id="7ef49-113">**Key to topology illustrations**</span></span>

<span data-ttu-id="7ef49-114">![拓撲]圖的(images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "索引鍵")</span><span class="sxs-lookup"><span data-stu-id="7ef49-114">![Key to topology illustrations](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Key to topology illustrations")</span></span>

<div>

## <a name="single-forest-single-domain"></a><span data-ttu-id="7ef49-115">單一目錄林、單一網域</span><span class="sxs-lookup"><span data-stu-id="7ef49-115">Single Forest, Single Domain</span></span>

<span data-ttu-id="7ef49-116">Lync Server （單一網域林）支援的最簡單的 Active Directory 拓撲是常見的拓撲。</span><span class="sxs-lookup"><span data-stu-id="7ef49-116">The simplest Active Directory topology supported by Lync Server, a single domain forest, is a common topology.</span></span>

<span data-ttu-id="7ef49-117">下圖說明單一網域 Active Directory 拓撲中的 Lync Server 部署。</span><span class="sxs-lookup"><span data-stu-id="7ef49-117">The following figure illustrates a Lync Server deployment in a single domain Active Directory topology.</span></span>

<span data-ttu-id="7ef49-118">**單一網域拓撲**</span><span class="sxs-lookup"><span data-stu-id="7ef49-118">**Single domain topology**</span></span>

<span data-ttu-id="7ef49-119">![單一網域拓朴](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "單一網域拓朴")</span><span class="sxs-lookup"><span data-stu-id="7ef49-119">![Single domain topology](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Single domain topology")</span></span>

</div>

<div>

## <a name="single-forest-multiple-domains"></a><span data-ttu-id="7ef49-120">單一目錄林、多個網域</span><span class="sxs-lookup"><span data-stu-id="7ef49-120">Single Forest, Multiple Domains</span></span>

<span data-ttu-id="7ef49-121">Lync Server 支援的另一個 Active Directory 拓撲是一個由根網域以及一個或多個子網域組成的單一目錄林。</span><span class="sxs-lookup"><span data-stu-id="7ef49-121">Another Active Directory topology supported by Lync Server is a single forest that consists of a root domain and one or more child domains.</span></span> <span data-ttu-id="7ef49-122">在這種類型的 Active Directory 拓撲中，您建立使用者的網域可能與您部署 Lync Server 的網域不同。</span><span class="sxs-lookup"><span data-stu-id="7ef49-122">In this type of Active Directory topology, the domain where you create users can be different from the domain where you deploy Lync Server.</span></span> <span data-ttu-id="7ef49-123">不過，如果您要部署前端池，您必須在單一網域中部署該池中的所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="7ef49-123">However, if you deploy a Front End pool, you must deploy all the Front End Servers in the pool within a single domain.</span></span> <span data-ttu-id="7ef49-124">Windows 通用管理員群組的 Lync Server 支援可啟用跨網域管理。</span><span class="sxs-lookup"><span data-stu-id="7ef49-124">Lync Server support for Windows universal administrator groups enables cross-domain administration.</span></span>

<span data-ttu-id="7ef49-125">下圖說明單一樹林中有多個網域的部署。</span><span class="sxs-lookup"><span data-stu-id="7ef49-125">The following figure illustrates a deployment in a single forest with multiple domains.</span></span> <span data-ttu-id="7ef49-126">在此圖中，使用者圖示會顯示使用者帳戶所在的網域，而箭頭則指向 Lync 伺服器池所在的網域。</span><span class="sxs-lookup"><span data-stu-id="7ef49-126">In this figure, a user icon shows the domain where the user account is homed, and the arrow points to the domain where the Lync Server pool resides.</span></span> <span data-ttu-id="7ef49-127">使用者帳戶包括下列專案：</span><span class="sxs-lookup"><span data-stu-id="7ef49-127">User accounts include the following:</span></span>

  - <span data-ttu-id="7ef49-128">與 Lync Server pool 在同一個網域中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="7ef49-128">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="7ef49-129">Lync Server pool 的不同網域中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="7ef49-129">User accounts in a different domain from the Lync Server pool</span></span>

  - <span data-ttu-id="7ef49-130">網域子域中擁有 Lync 伺服器池的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="7ef49-130">User accounts in a child domain of the domain with the Lync Server pool</span></span>

<span data-ttu-id="7ef49-131">**具多重網域的單一樹系**</span><span class="sxs-lookup"><span data-stu-id="7ef49-131">**Single forest with multiple domains**</span></span>

<span data-ttu-id="7ef49-132">具有多個網域的![單一目錄林](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "單一目錄林")</span><span class="sxs-lookup"><span data-stu-id="7ef49-132">![Single forest with multiple domains](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Single forest with multiple domains")</span></span>

</div>

<div>

## <a name="single-forest-multiple-trees"></a><span data-ttu-id="7ef49-133">單一目錄林、多個樹</span><span class="sxs-lookup"><span data-stu-id="7ef49-133">Single Forest, Multiple Trees</span></span>

<span data-ttu-id="7ef49-134">多重樹狀目錄林拓朴由兩個以上的網域組成，這些網域定義獨立的樹狀結構和獨立的 Active Directory 命名空間。</span><span class="sxs-lookup"><span data-stu-id="7ef49-134">A multiple-tree forest topology consists of two or more domains that define independent tree structures and separate Active Directory namespaces.</span></span>

<span data-ttu-id="7ef49-135">下圖說明單一擁有多個樹的目錄林。</span><span class="sxs-lookup"><span data-stu-id="7ef49-135">The following figure illustrates a single forest with multiple trees.</span></span> <span data-ttu-id="7ef49-136">在此圖中，使用者圖示會顯示使用者帳戶所在的網域、實線指向位於相同或不同網域的 Lync 伺服器池，而虛線則指向位於不同樹狀結構的 Lync Server pool。</span><span class="sxs-lookup"><span data-stu-id="7ef49-136">In this figure, a user icon shows the domain where the user account is homed, a solid line points to a Lync Server pool that resides in the same or a different domain, and a dashed line points to Lync Server pool that resides in a different tree.</span></span> <span data-ttu-id="7ef49-137">使用者帳戶包括下列專案：</span><span class="sxs-lookup"><span data-stu-id="7ef49-137">User accounts include the following:</span></span>

  - <span data-ttu-id="7ef49-138">與 Lync Server pool 在同一個網域中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="7ef49-138">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="7ef49-139">不同網域中的使用者帳戶（但與 Lync 伺服器池的同一個樹狀結構一樣）</span><span class="sxs-lookup"><span data-stu-id="7ef49-139">User accounts in a different domain from (but the same tree as) the Lync Server pool</span></span>

  - <span data-ttu-id="7ef49-140">Lync Server 文件庫不同樹狀結構中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="7ef49-140">User accounts in a different tree from the Lync Server pool</span></span>

<span data-ttu-id="7ef49-141">**具多重樹狀結構的單一樹系**</span><span class="sxs-lookup"><span data-stu-id="7ef49-141">**Single forest with multiple trees**</span></span>

<span data-ttu-id="7ef49-142">具有多個樹的![單一目錄林]的單一目錄(images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "林")</span><span class="sxs-lookup"><span data-stu-id="7ef49-142">![Single forest with multiple trees](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Single forest with multiple trees")</span></span>

</div>

<div>

## <a name="multiple-forests-central-forest"></a><span data-ttu-id="7ef49-143">多個目錄林，中央目錄林</span><span class="sxs-lookup"><span data-stu-id="7ef49-143">Multiple Forests, Central Forest</span></span>

<span data-ttu-id="7ef49-144">Lync Server 支援多個在中央目錄林拓撲結構中設定的目錄林。</span><span class="sxs-lookup"><span data-stu-id="7ef49-144">Lync Server supports multiple forests that are configured in a central forest topology.</span></span> <span data-ttu-id="7ef49-145">中央林拓撲在中央林中使用連絡人物件來代表其他林中的使用者。</span><span class="sxs-lookup"><span data-stu-id="7ef49-145">Central forest topologies use contact objects in the central forest to represent users in the other forests.</span></span> <span data-ttu-id="7ef49-146">中央目錄林也會為此林中的任何使用者託管使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7ef49-146">The central forest also hosts user accounts for any users in this forest.</span></span> <span data-ttu-id="7ef49-147">目錄同步處理產品，例如 Microsoft 身分識別整合伺服器（MIIS）、Microsoft Forefront 身分識別管理員（FIM）2010或 Microsoft 身分識別週期管理員（ILM）2007功能套件1（FP1），管理使用者帳戶在其中的生命週期組織：當您在其中一個目錄林中建立新的使用者帳戶，或從樹林中刪除使用者帳戶時，目錄同步處理產品會同步處理中央林中的對應連絡人。</span><span class="sxs-lookup"><span data-stu-id="7ef49-147">A directory synchronization product, such as Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts within the organization: When a new user account is created in one of the forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding contact in the central forest.</span></span>

<span data-ttu-id="7ef49-148">中央林具有下列優點：</span><span class="sxs-lookup"><span data-stu-id="7ef49-148">A central forest has the following advantages:</span></span>

  - <span data-ttu-id="7ef49-149">在單一目錄林中執行 Lync Server 的伺服器是集中式。</span><span class="sxs-lookup"><span data-stu-id="7ef49-149">Servers running Lync Server are centralized within a single forest.</span></span>

  - <span data-ttu-id="7ef49-150">使用者可以在任何林中搜尋並與其他使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="7ef49-150">Users can search for and communicate with other users in any forest.</span></span>

  - <span data-ttu-id="7ef49-151">使用者可以在任何林中查看其他使用者的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="7ef49-151">Users can view presence of other users in any forest.</span></span>

  - <span data-ttu-id="7ef49-152">目錄同步處理產品會在建立或移除使用者帳戶時，自動在中央林中新增和刪除連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="7ef49-152">The directory synchronization product automates the addition and deletion of contact objects in the central forest as user accounts are created or removed.</span></span>

<span data-ttu-id="7ef49-153">下圖說明中央林拓撲。</span><span class="sxs-lookup"><span data-stu-id="7ef49-153">The following figure illustrates a central forest topology.</span></span> <span data-ttu-id="7ef49-154">在此圖中，託管 Lync Server 的網域（位於中央林中）與每個使用者專用的網域（分別位於不同的林中）都有雙向信任關係。</span><span class="sxs-lookup"><span data-stu-id="7ef49-154">In this figure, there are two-way trust relationships between the domain that hosts Lync Server, which is in the central forest, and each user-only domain, which is in a separate forest.</span></span> <span data-ttu-id="7ef49-155">個別使用者林內的架構不需要進行延伸。</span><span class="sxs-lookup"><span data-stu-id="7ef49-155">The schema in the separate user forests does not need to be extended.</span></span>

<span data-ttu-id="7ef49-156">**中央樹系拓撲**</span><span class="sxs-lookup"><span data-stu-id="7ef49-156">**Central forest topology**</span></span>

<span data-ttu-id="7ef49-157">![中央林拓撲](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "中央林拓撲")</span><span class="sxs-lookup"><span data-stu-id="7ef49-157">![Central forest topology](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Central forest topology")</span></span>

</div>

<div>

## <a name="multiple-forests-resource-forest"></a><span data-ttu-id="7ef49-158">多個林、資原始目錄林</span><span class="sxs-lookup"><span data-stu-id="7ef49-158">Multiple Forests, Resource Forest</span></span>

<span data-ttu-id="7ef49-159">在資原始目錄林拓朴中，有一個目錄林專用於執行伺服器應用程式，例如 Microsoft Exchange Server 和 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="7ef49-159">In a resource forest topology, one forest is dedicated to running server applications, such as Microsoft Exchange Server and Lync Server.</span></span> <span data-ttu-id="7ef49-160">資原始目錄林主持伺服器應用程式及作用中使用者物件的同步表示，但不包含登入的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7ef49-160">The resource forest hosts the server applications and a synchronized representation of the active user object, but it does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="7ef49-161">資原始目錄林充當使用者物件所在之其他目錄林的共用服務環境。</span><span class="sxs-lookup"><span data-stu-id="7ef49-161">The resource forest acts as a shared services environment for the other forests where user objects reside.</span></span> <span data-ttu-id="7ef49-162">使用者目錄林與資原始目錄林有林層級的信任關係。</span><span class="sxs-lookup"><span data-stu-id="7ef49-162">The user forests have a forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="7ef49-163">當您在這種類型的拓朴中部署 Lync Server 時，您會在資原始目錄林中為使用者樹林中的每個使用者帳戶建立一個停用的使用者物件。</span><span class="sxs-lookup"><span data-stu-id="7ef49-163">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="7ef49-164">如果 Microsoft Exchange 已部署在資原始目錄林中，停用的使用者帳戶可能已經存在。</span><span class="sxs-lookup"><span data-stu-id="7ef49-164">If Microsoft Exchange is already deployed in the resource forest, the disabled user accounts might already exist.</span></span> <span data-ttu-id="7ef49-165">目錄同步處理產品，例如 MIIS、Microsoft Forefront 身分識別管理員（FIM）2010或 Microsoft 身分識別週期管理員（ILM）2007功能套件1（FP1），管理使用者帳戶的生命週期。</span><span class="sxs-lookup"><span data-stu-id="7ef49-165">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="7ef49-166">當您在其中一個使用者林中建立新的使用者帳戶，或是從樹林中刪除使用者帳戶時，目錄同步處理產品會同步處理資原始目錄林中對應的使用者表示。</span><span class="sxs-lookup"><span data-stu-id="7ef49-166">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span>

<span data-ttu-id="7ef49-167">這個拓撲可用來為組織中管理多個目錄林的服務提供共用基礎結構，或是將 Active Directory 物件的管理與其他管理區分開。</span><span class="sxs-lookup"><span data-stu-id="7ef49-167">This topology can be used to provide a shared infrastructure for services in organizations that manage multiple forests or to separate the administration of Active Directory objects from other administration.</span></span> <span data-ttu-id="7ef49-168">需要隔離 Active Directory 系統管理以安全原因的公司，通常會選擇此拓撲。</span><span class="sxs-lookup"><span data-stu-id="7ef49-168">Companies that need to isolate Active Directory administration for security reasons often choose this topology.</span></span>

<span data-ttu-id="7ef49-169">這個拓撲提供限制將 Active Directory 架構延伸到單一目錄林（也就是資原始目錄林）的好處。</span><span class="sxs-lookup"><span data-stu-id="7ef49-169">This topology provides the benefit of limiting the need to extend the Active Directory schema to a single forest (that is, the resource forest).</span></span>

<span data-ttu-id="7ef49-170">下列圖表說明資源林拓撲。</span><span class="sxs-lookup"><span data-stu-id="7ef49-170">The following diagram illustrates a resource forest topology.</span></span>

<span data-ttu-id="7ef49-171">**資源林拓撲**</span><span class="sxs-lookup"><span data-stu-id="7ef49-171">**Resource forest topology**</span></span>

<span data-ttu-id="7ef49-172">![Active Directory 資源林拓撲](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory 資源林拓撲")</span><span class="sxs-lookup"><span data-stu-id="7ef49-172">![Active Directory Resource Forest Topology](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory Resource Forest Topology")</span></span>

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a><span data-ttu-id="7ef49-173">使用 Exchange Online 的 Lync 資原始目錄林拓撲結構中有多個目錄林</span><span class="sxs-lookup"><span data-stu-id="7ef49-173">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="7ef49-174">在此拓撲中，一個或多個目錄林位於內部部署，且專用於託管 Active Directory 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7ef49-174">In this topology, one or more forests are located on-premises and are dedicated to hosting Active Directory user accounts.</span></span> <span data-ttu-id="7ef49-175">資原始目錄林位於內部部署，且由協力廠商主機服務提供者維護。</span><span class="sxs-lookup"><span data-stu-id="7ef49-175">The resource forest is located off-premises and is maintained by a third-party hosting provider.</span></span> <span data-ttu-id="7ef49-176">資原始目錄林只包含 Lync Server 部署與內部部署使用者帳戶林中的使用者帳戶同步複製。</span><span class="sxs-lookup"><span data-stu-id="7ef49-176">The resource forest contains only the Lync Server deployment and a synchronized replication of the user accounts from the on-premises user accounts forest(s).</span></span> <span data-ttu-id="7ef49-177">它不包含登入的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7ef49-177">It does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="7ef49-178">Exchange 是在結合 Exchange Online （混合式）的內部部署使用者帳戶目錄林中，或以 exchange Online 為內部部署使用者帳戶提供電子郵件服務。</span><span class="sxs-lookup"><span data-stu-id="7ef49-178">Exchange is deployed either in the on-premises user account forest(s) integrated along with Exchange Online (Hybrid), or email services for the on-premises user accounts are provided exclusively by Exchange Online.</span></span>

<span data-ttu-id="7ef49-179">資原始目錄林充當使用者物件所在之內部部署 Active Directory 林的共用服務環境。</span><span class="sxs-lookup"><span data-stu-id="7ef49-179">The resource forest acts as a shared services environment for the on-premises Active Directory forest(s) where user objects reside.</span></span> <span data-ttu-id="7ef49-180">使用者帳戶目錄林與資原始目錄林有單一的方式林層級信任關係。</span><span class="sxs-lookup"><span data-stu-id="7ef49-180">The user account forest(s) have a one way forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="7ef49-181">當您在這種類型的拓朴中部署 Lync Server 時，您會在資原始目錄林中為使用者樹林中的每個使用者帳戶建立一個停用的使用者物件。</span><span class="sxs-lookup"><span data-stu-id="7ef49-181">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="7ef49-182">目錄同步處理產品，例如 MIIS、Microsoft Forefront 身分識別管理員（FIM）2010或 Microsoft 身分識別週期管理員（ILM）2007功能套件1（FP1），管理使用者帳戶的生命週期。</span><span class="sxs-lookup"><span data-stu-id="7ef49-182">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="7ef49-183">當您在其中一個使用者林中建立新的使用者帳戶，或是從樹林中刪除使用者帳戶時，目錄同步處理產品會同步處理資原始目錄林中對應的使用者表示。</span><span class="sxs-lookup"><span data-stu-id="7ef49-183">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span> <span data-ttu-id="7ef49-184">如需有關設定多目錄林部署的詳細資訊，請參閱[在多林結構（含 Exchange 混合式的合作夥伴託管的 lync）中部署 lync](http://go.microsoft.com/fwlink/p/?linkid=513216)。</span><span class="sxs-lookup"><span data-stu-id="7ef49-184">For more information about configuring a multi-forest deployment, see [Deploying Lync in a Multi-Forest Architecture (Partner Hosted Lync with Exchange Hybrid)](http://go.microsoft.com/fwlink/p/?linkid=513216).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


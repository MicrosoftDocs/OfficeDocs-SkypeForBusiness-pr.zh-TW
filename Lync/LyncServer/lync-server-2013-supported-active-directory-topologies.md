---
title: Lync Server 2013：支援的 Active Directory 拓撲
description: Lync Server 2013：支援的 Active Directory 拓撲。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ce820a36cb033933b423e01deb5a3049ed3ea2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575309"
---
# <a name="supported-active-directory-topologies-in-lync-server-2013"></a><span data-ttu-id="bae31-103">Lync Server 2013 中支援的 Active Directory 拓撲</span><span class="sxs-lookup"><span data-stu-id="bae31-103">Supported Active Directory topologies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bae31-104">_**主題上次修改日期：** 2014-10-02_</span><span class="sxs-lookup"><span data-stu-id="bae31-104">_**Topic Last Modified:** 2014-10-02_</span></span>

<span data-ttu-id="bae31-105">Lync Server 2013 支援與 Microsoft Lync Server 2010 和 Microsoft Office 通訊伺服器 2007 R2 相同的 Active Directory 網域服務拓撲。</span><span class="sxs-lookup"><span data-stu-id="bae31-105">Lync Server 2013 supports the same Active Directory Domain Services topologies as Microsoft Lync Server 2010 and Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="bae31-106">支援下列拓撲：</span><span class="sxs-lookup"><span data-stu-id="bae31-106">The following topologies are supported:</span></span>

  - <span data-ttu-id="bae31-107">具單一網域的單一樹系</span><span class="sxs-lookup"><span data-stu-id="bae31-107">Single forest with single domain</span></span>

  - <span data-ttu-id="bae31-108">具單一樹狀結構和多個網域的單一樹系</span><span class="sxs-lookup"><span data-stu-id="bae31-108">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="bae31-109">具多重樹狀結構和斷續命名空間的單一樹系</span><span class="sxs-lookup"><span data-stu-id="bae31-109">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="bae31-110">中央樹系拓撲中的多重樹系</span><span class="sxs-lookup"><span data-stu-id="bae31-110">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="bae31-111">資源樹系拓撲中的多重樹系</span><span class="sxs-lookup"><span data-stu-id="bae31-111">Multiple forests in a resource forest topology</span></span>

  - <span data-ttu-id="bae31-112">具有 Exchange Online 之 Lync 資源樹系拓撲中的多個樹系</span><span class="sxs-lookup"><span data-stu-id="bae31-112">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="bae31-113">下圖識別本節圖例中使用的圖示。</span><span class="sxs-lookup"><span data-stu-id="bae31-113">The following figure identifies the icons used in the illustrations in this section.</span></span>

<span data-ttu-id="bae31-114">**拓撲圖例**</span><span class="sxs-lookup"><span data-stu-id="bae31-114">**Key to topology illustrations**</span></span>

<span data-ttu-id="bae31-115">![拓撲圖例](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "拓撲圖例")</span><span class="sxs-lookup"><span data-stu-id="bae31-115">![Key to topology illustrations](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Key to topology illustrations")</span></span>

<div>

## <a name="single-forest-single-domain"></a><span data-ttu-id="bae31-116">單一樹系、單一網域</span><span class="sxs-lookup"><span data-stu-id="bae31-116">Single Forest, Single Domain</span></span>

<span data-ttu-id="bae31-117">Lync Server、單一網域樹系支援的最簡單 Active Directory 拓撲是一般拓撲。</span><span class="sxs-lookup"><span data-stu-id="bae31-117">The simplest Active Directory topology supported by Lync Server, a single domain forest, is a common topology.</span></span>

<span data-ttu-id="bae31-118">下圖說明單一網域 Active Directory 拓撲中的 Lync Server 部署。</span><span class="sxs-lookup"><span data-stu-id="bae31-118">The following figure illustrates a Lync Server deployment in a single domain Active Directory topology.</span></span>

<span data-ttu-id="bae31-119">**單一網域拓撲**</span><span class="sxs-lookup"><span data-stu-id="bae31-119">**Single domain topology**</span></span>

<span data-ttu-id="bae31-120">![單一網域拓撲](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "單一網域拓撲")</span><span class="sxs-lookup"><span data-stu-id="bae31-120">![Single domain topology](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Single domain topology")</span></span>

</div>

<div>

## <a name="single-forest-multiple-domains"></a><span data-ttu-id="bae31-121">單一樹系、多個網域</span><span class="sxs-lookup"><span data-stu-id="bae31-121">Single Forest, Multiple Domains</span></span>

<span data-ttu-id="bae31-122">Lync Server 支援的另一個 Active Directory 拓撲是單一樹系，由一個根網域及一個或多個子域所組成。</span><span class="sxs-lookup"><span data-stu-id="bae31-122">Another Active Directory topology supported by Lync Server is a single forest that consists of a root domain and one or more child domains.</span></span> <span data-ttu-id="bae31-123">在這種類型的 Active Directory 拓撲中，您建立使用者的網域可能與您部署 Lync Server 的網域不同。</span><span class="sxs-lookup"><span data-stu-id="bae31-123">In this type of Active Directory topology, the domain where you create users can be different from the domain where you deploy Lync Server.</span></span> <span data-ttu-id="bae31-124">但是，如果您部署前端集區，您就必須在單一網域內部署集區中的所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="bae31-124">However, if you deploy a Front End pool, you must deploy all the Front End Servers in the pool within a single domain.</span></span> <span data-ttu-id="bae31-125">適用于 Windows 通用管理員群組的 Lync Server 支援可啟用跨網域管理。</span><span class="sxs-lookup"><span data-stu-id="bae31-125">Lync Server support for Windows universal administrator groups enables cross-domain administration.</span></span>

<span data-ttu-id="bae31-126">下圖說明具有多個網域之單一樹系的部署。</span><span class="sxs-lookup"><span data-stu-id="bae31-126">The following figure illustrates a deployment in a single forest with multiple domains.</span></span> <span data-ttu-id="bae31-127">在此圖中，使用者圖示會顯示使用者帳戶所在的網域，箭號會指向 Lync Server 集區所在的網域。</span><span class="sxs-lookup"><span data-stu-id="bae31-127">In this figure, a user icon shows the domain where the user account is homed, and the arrow points to the domain where the Lync Server pool resides.</span></span> <span data-ttu-id="bae31-128">使用者帳戶包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="bae31-128">User accounts include the following:</span></span>

  - <span data-ttu-id="bae31-129">與 Lync Server 集區在相同網域中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="bae31-129">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="bae31-130">Lync Server 集區的不同網域中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="bae31-130">User accounts in a different domain from the Lync Server pool</span></span>

  - <span data-ttu-id="bae31-131">具有 Lync Server 集區之網域之子域中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="bae31-131">User accounts in a child domain of the domain with the Lync Server pool</span></span>

<span data-ttu-id="bae31-132">**具多重網域的單一樹系**</span><span class="sxs-lookup"><span data-stu-id="bae31-132">**Single forest with multiple domains**</span></span>

<span data-ttu-id="bae31-133">![具多重網域的單一樹系](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "具多重網域的單一樹系")</span><span class="sxs-lookup"><span data-stu-id="bae31-133">![Single forest with multiple domains](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Single forest with multiple domains")</span></span>

</div>

<div>

## <a name="single-forest-multiple-trees"></a><span data-ttu-id="bae31-134">單一樹系、多重樹狀結構</span><span class="sxs-lookup"><span data-stu-id="bae31-134">Single Forest, Multiple Trees</span></span>

<span data-ttu-id="bae31-135">多重樹狀結構的樹系拓撲是由兩個以上的網域組成，這些網域定義獨立的樹狀結構和個別的 Active Directory 命名空間。</span><span class="sxs-lookup"><span data-stu-id="bae31-135">A multiple-tree forest topology consists of two or more domains that define independent tree structures and separate Active Directory namespaces.</span></span>

<span data-ttu-id="bae31-136">下圖說明具多重樹狀結構的單一樹系。</span><span class="sxs-lookup"><span data-stu-id="bae31-136">The following figure illustrates a single forest with multiple trees.</span></span> <span data-ttu-id="bae31-137">在此圖中，使用者圖示會顯示使用者帳戶所在的網域、實線指向位於相同或不同網域中的 Lync 伺服器集區，而虛線指向位於其他樹狀目錄中的 Lync Server 集區。</span><span class="sxs-lookup"><span data-stu-id="bae31-137">In this figure, a user icon shows the domain where the user account is homed, a solid line points to a Lync Server pool that resides in the same or a different domain, and a dashed line points to Lync Server pool that resides in a different tree.</span></span> <span data-ttu-id="bae31-138">使用者帳戶包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="bae31-138">User accounts include the following:</span></span>

  - <span data-ttu-id="bae31-139">與 Lync Server 集區在相同網域中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="bae31-139">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="bae31-140">不同網域中的使用者帳戶 (，但與 Lync Server 集區) 相同的樹狀目錄</span><span class="sxs-lookup"><span data-stu-id="bae31-140">User accounts in a different domain from (but the same tree as) the Lync Server pool</span></span>

  - <span data-ttu-id="bae31-141">Lync Server 集區的不同樹狀目錄中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="bae31-141">User accounts in a different tree from the Lync Server pool</span></span>

<span data-ttu-id="bae31-142">**具多重樹狀結構的單一樹系**</span><span class="sxs-lookup"><span data-stu-id="bae31-142">**Single forest with multiple trees**</span></span>

<span data-ttu-id="bae31-143">![具多重樹狀結構的單一樹系](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "具多重樹狀結構的單一樹系")</span><span class="sxs-lookup"><span data-stu-id="bae31-143">![Single forest with multiple trees](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Single forest with multiple trees")</span></span>

</div>

<div>

## <a name="multiple-forests-central-forest"></a><span data-ttu-id="bae31-144">多重樹系、中央樹系</span><span class="sxs-lookup"><span data-stu-id="bae31-144">Multiple Forests, Central Forest</span></span>

<span data-ttu-id="bae31-145">Lync Server 支援在中央樹系拓撲中設定多個樹系。</span><span class="sxs-lookup"><span data-stu-id="bae31-145">Lync Server supports multiple forests that are configured in a central forest topology.</span></span> <span data-ttu-id="bae31-146">中央樹系拓撲使用中央樹系中的連絡人物件來代表其他樹系的使用者。</span><span class="sxs-lookup"><span data-stu-id="bae31-146">Central forest topologies use contact objects in the central forest to represent users in the other forests.</span></span> <span data-ttu-id="bae31-147">中央樹系也會為此樹系中的任一使用者裝載其使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bae31-147">The central forest also hosts user accounts for any users in this forest.</span></span> <span data-ttu-id="bae31-148">目錄同步處理產品 (例如 Microsoft Identity Integration Server (MIIS)、Microsoft Forefront Identity Manager (FIM) 2010 或 Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1)) 會管理組織中的使用者帳戶生命週期：在其中一個樹系中建立新的使用者帳戶，或在樹系中刪除使用者帳戶時，目錄同步處理產品就會在中央樹系中同步處理對應的連絡人。</span><span class="sxs-lookup"><span data-stu-id="bae31-148">A directory synchronization product, such as Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts within the organization: When a new user account is created in one of the forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding contact in the central forest.</span></span>

<span data-ttu-id="bae31-149">中央樹系有下列優點：</span><span class="sxs-lookup"><span data-stu-id="bae31-149">A central forest has the following advantages:</span></span>

  - <span data-ttu-id="bae31-150">在單一樹系中集中執行 Lync Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="bae31-150">Servers running Lync Server are centralized within a single forest.</span></span>

  - <span data-ttu-id="bae31-151">使用者可以搜尋任何樹系中的其他使用者，並與之通訊。</span><span class="sxs-lookup"><span data-stu-id="bae31-151">Users can search for and communicate with other users in any forest.</span></span>

  - <span data-ttu-id="bae31-152">使用者可以檢視任何樹系中其他使用者的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="bae31-152">Users can view presence of other users in any forest.</span></span>

  - <span data-ttu-id="bae31-153">當建立或移除使用者帳戶時，目錄同步處理產品會自動新增及刪除中央樹系中的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="bae31-153">The directory synchronization product automates the addition and deletion of contact objects in the central forest as user accounts are created or removed.</span></span>

<span data-ttu-id="bae31-154">下圖說明中央樹系拓撲。</span><span class="sxs-lookup"><span data-stu-id="bae31-154">The following figure illustrates a central forest topology.</span></span> <span data-ttu-id="bae31-155">在此圖中，主控 Lync Server 的網域（位於中央樹系中）和每個僅使用者網域（位於不同樹系中）皆有雙向信任關係。</span><span class="sxs-lookup"><span data-stu-id="bae31-155">In this figure, there are two-way trust relationships between the domain that hosts Lync Server, which is in the central forest, and each user-only domain, which is in a separate forest.</span></span> <span data-ttu-id="bae31-156">個別使用者樹系中的架構不需要擴充。</span><span class="sxs-lookup"><span data-stu-id="bae31-156">The schema in the separate user forests does not need to be extended.</span></span>

<span data-ttu-id="bae31-157">**中央樹系拓撲**</span><span class="sxs-lookup"><span data-stu-id="bae31-157">**Central forest topology**</span></span>

<span data-ttu-id="bae31-158">![中央樹系拓撲](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "中央樹系拓撲")</span><span class="sxs-lookup"><span data-stu-id="bae31-158">![Central forest topology](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Central forest topology")</span></span>

</div>

<div>

## <a name="multiple-forests-resource-forest"></a><span data-ttu-id="bae31-159">多重樹系、資源樹系</span><span class="sxs-lookup"><span data-stu-id="bae31-159">Multiple Forests, Resource Forest</span></span>

<span data-ttu-id="bae31-160">在資源樹系拓撲中，有一個樹系專用於執行伺服器應用程式，例如 Microsoft Exchange Server 和 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="bae31-160">In a resource forest topology, one forest is dedicated to running server applications, such as Microsoft Exchange Server and Lync Server.</span></span> <span data-ttu-id="bae31-161">資源樹系會裝載伺服器應用程式以及作用中使用者物件的同步表示，但不包含已啟用登入的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bae31-161">The resource forest hosts the server applications and a synchronized representation of the active user object, but it does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="bae31-162">資源樹系是當做使用者物件所在的其他樹系的共用服務環境。</span><span class="sxs-lookup"><span data-stu-id="bae31-162">The resource forest acts as a shared services environment for the other forests where user objects reside.</span></span> <span data-ttu-id="bae31-163">使用者樹系與資源樹系之間有樹系層級的信任關係。</span><span class="sxs-lookup"><span data-stu-id="bae31-163">The user forests have a forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="bae31-164">當您在此類型的拓撲中部署 Lync Server 時，您會在資源樹系中為使用者樹系中的每個使用者帳戶建立一個已停用的使用者物件。</span><span class="sxs-lookup"><span data-stu-id="bae31-164">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="bae31-165">如果已在資源樹系中部署 Microsoft Exchange，則已停用的使用者帳戶可能已存在。</span><span class="sxs-lookup"><span data-stu-id="bae31-165">If Microsoft Exchange is already deployed in the resource forest, the disabled user accounts might already exist.</span></span> <span data-ttu-id="bae31-166">目錄同步處理產品 (例如 MIIS、Microsoft Forefront Identity Manager (FIM) 2010 或 Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1)) 會管理使用者帳戶的生命週期。</span><span class="sxs-lookup"><span data-stu-id="bae31-166">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="bae31-167">在其中一個使用者樹系中建立新的使用者帳戶，或在樹系中刪除使用者帳戶時，目錄同步處理產品就會在資源樹系中同步處理對應的使用者表示。</span><span class="sxs-lookup"><span data-stu-id="bae31-167">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span>

<span data-ttu-id="bae31-p108">此拓撲可以為管理多重樹系的組織提供共用的服務基礎結構，或用來將 Active Directory 物件的管理作業與其他管理作業區隔開來。公司基於安全考量，要將 Active Directory 管理作業隔離起來時，通常會選擇此拓撲。</span><span class="sxs-lookup"><span data-stu-id="bae31-p108">This topology can be used to provide a shared infrastructure for services in organizations that manage multiple forests or to separate the administration of Active Directory objects from other administration. Companies that need to isolate Active Directory administration for security reasons often choose this topology.</span></span>

<span data-ttu-id="bae31-170">此拓撲的優點是，您只需在單一樹系 (也就是資源樹系) 中擴充 Active Directory 架構。</span><span class="sxs-lookup"><span data-stu-id="bae31-170">This topology provides the benefit of limiting the need to extend the Active Directory schema to a single forest (that is, the resource forest).</span></span>

<span data-ttu-id="bae31-171">下圖說明資源樹系拓撲。</span><span class="sxs-lookup"><span data-stu-id="bae31-171">The following diagram illustrates a resource forest topology.</span></span>

<span data-ttu-id="bae31-172">**資源樹系拓撲**</span><span class="sxs-lookup"><span data-stu-id="bae31-172">**Resource forest topology**</span></span>

<span data-ttu-id="bae31-173">![Active Directory 資源樹系拓撲](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory 資源樹系拓撲")</span><span class="sxs-lookup"><span data-stu-id="bae31-173">![Active Directory Resource Forest Topology](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory Resource Forest Topology")</span></span>

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a><span data-ttu-id="bae31-174">具有 Exchange Online 之 Lync 資源樹系拓撲中的多個樹系</span><span class="sxs-lookup"><span data-stu-id="bae31-174">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="bae31-175">在此拓撲中，一或多個樹系位於內部部署，而且專用於主控 Active Directory 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bae31-175">In this topology, one or more forests are located on-premises and are dedicated to hosting Active Directory user accounts.</span></span> <span data-ttu-id="bae31-176">資源樹系位於內部部署，由協力廠商主機服務提供者維護。</span><span class="sxs-lookup"><span data-stu-id="bae31-176">The resource forest is located off-premises and is maintained by a third-party hosting provider.</span></span> <span data-ttu-id="bae31-177">資源樹系僅包含從內部部署使用者帳戶樹系 (s) 中的 Lync Server 部署和使用者帳戶的同步複寫。</span><span class="sxs-lookup"><span data-stu-id="bae31-177">The resource forest contains only the Lync Server deployment and a synchronized replication of the user accounts from the on-premises user accounts forest(s).</span></span> <span data-ttu-id="bae31-178">不包含啟用登入的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bae31-178">It does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="bae31-179">Exchange 是在內部部署使用者帳戶樹系中部署 (s) 與 Exchange Online (混合式) ，或內部部署使用者帳戶的電子郵件服務，由 Exchange Online 獨佔提供。</span><span class="sxs-lookup"><span data-stu-id="bae31-179">Exchange is deployed either in the on-premises user account forest(s) integrated along with Exchange Online (Hybrid), or email services for the on-premises user accounts are provided exclusively by Exchange Online.</span></span>

<span data-ttu-id="bae31-180">資源樹系充當內部部署 Active Directory 樹系的共用服務環境 (s) 使用者物件所在的位置。</span><span class="sxs-lookup"><span data-stu-id="bae31-180">The resource forest acts as a shared services environment for the on-premises Active Directory forest(s) where user objects reside.</span></span> <span data-ttu-id="bae31-181">使用者帳戶樹系 (s) 具有與資源樹系的單向樹系層級信任關係。</span><span class="sxs-lookup"><span data-stu-id="bae31-181">The user account forest(s) have a one way forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="bae31-182">當您在此類型的拓撲中部署 Lync Server 時，您會在資源樹系中為使用者樹系中的每個使用者帳戶建立一個已停用的使用者物件。</span><span class="sxs-lookup"><span data-stu-id="bae31-182">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="bae31-183">目錄同步處理產品 (例如 MIIS、Microsoft Forefront Identity Manager (FIM) 2010 或 Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1)) 會管理使用者帳戶的生命週期。</span><span class="sxs-lookup"><span data-stu-id="bae31-183">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="bae31-184">在其中一個使用者樹系中建立新的使用者帳戶，或在樹系中刪除使用者帳戶時，目錄同步處理產品就會在資源樹系中同步處理對應的使用者表示。</span><span class="sxs-lookup"><span data-stu-id="bae31-184">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span> <span data-ttu-id="bae31-185">如需設定多樹系部署的詳細資訊，請參閱 [在多樹系架構中部署 Lync， (第三個樹系的 lync 具有 Exchange 混合) ](https://go.microsoft.com/fwlink/p/?linkid=513216)。</span><span class="sxs-lookup"><span data-stu-id="bae31-185">For more information about configuring a multi-forest deployment, see [Deploying Lync in a Multi-Forest Architecture (Partner Hosted Lync with Exchange Hybrid)](https://go.microsoft.com/fwlink/p/?linkid=513216).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


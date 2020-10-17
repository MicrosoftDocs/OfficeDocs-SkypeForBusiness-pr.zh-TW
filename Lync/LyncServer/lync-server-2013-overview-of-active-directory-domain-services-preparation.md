---
title: Lync Server 2013： Active Directory 網域服務準備工作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0074b1739cd571db46fc704d4863ac4f0462c99b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500580"
---
# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a><span data-ttu-id="8736a-102">Lync Server 2013 中的 Active Directory 網域服務準備工作</span><span class="sxs-lookup"><span data-stu-id="8736a-102">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8736a-103">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="8736a-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="8736a-104">若要為您的 Lync Server 2013 部署準備 Active Directory 網域服務，您必須依特定循序執行三個步驟。</span><span class="sxs-lookup"><span data-stu-id="8736a-104">To prepare Active Directory Domain Services for your Lync Server 2013 deployment, you must perform three steps in a specific sequence.</span></span>

<span data-ttu-id="8736a-105">下表說明為 Lync Server 準備 AD DS 所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="8736a-105">The following table describes the steps required to prepare AD DS for Lync Server.</span></span>

### <a name="active-directory-preparation-steps"></a><span data-ttu-id="8736a-106">Active Directory 準備步驟</span><span class="sxs-lookup"><span data-stu-id="8736a-106">Active Directory Preparation Steps</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="8736a-107">步驟</span><span class="sxs-lookup"><span data-stu-id="8736a-107">Step</span></span></th>
<th><span data-ttu-id="8736a-108">描述</span><span class="sxs-lookup"><span data-stu-id="8736a-108">Description</span></span></th>
<th><span data-ttu-id="8736a-109">執行位置</span><span class="sxs-lookup"><span data-stu-id="8736a-109">Where run</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><span data-ttu-id="8736a-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">在 Lync Server 2013 中準備 Active Directory 架構</a></span><span class="sxs-lookup"><span data-stu-id="8736a-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparing the Active Directory schema in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="8736a-111">新增 Lync Server 所使用的新類別和屬性，以擴充 Active Directory 架構。</span><span class="sxs-lookup"><span data-stu-id="8736a-111">Extends the Active Directory schema by adding new classes and attributes that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="8736a-112">針對您要部署 Lync Server 的部署中的每個樹系執行一次。</span><span class="sxs-lookup"><span data-stu-id="8736a-112">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="8736a-113">針對要部署 Lync Server 之每個樹系的根域中的架構主機。</span><span class="sxs-lookup"><span data-stu-id="8736a-113">Against the schema master in the root domain of each forest where Lync Server will be deployed.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="8736a-114">如果您擁有架構主機的許可權，您就不需要在根網域中執行這個步驟，但必須是根域中 Schema Admins 群組的成員，以及架構主機上的 Enterprise Admins 群組成員。</span><span class="sxs-lookup"><span data-stu-id="8736a-114">You do not need to run this step in the root domain if you have permissions on the schema master, but you must be a member of the Schema Admins group in the root domain and a member of the Enterprise Admins group on the schema master.</span></span> <span data-ttu-id="8736a-115">在資源樹系拓撲中，僅在資源樹系中執行此步驟，而不是在任何使用者樹系中執行。</span><span class="sxs-lookup"><span data-stu-id="8736a-115">In a resource forest topology, run this step only in the resource forest, not in any user forests.</span></span> <span data-ttu-id="8736a-116">在中央樹系拓撲中，請只在中央樹系中執行此步驟，而不是在任何使用者樹系中執行。</span><span class="sxs-lookup"><span data-stu-id="8736a-116">In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><span data-ttu-id="8736a-117"><a href="lync-server-2013-preparing-the-forest.md">準備 Lync Server 2013 的樹系</a></span><span class="sxs-lookup"><span data-stu-id="8736a-117"><a href="lync-server-2013-preparing-the-forest.md">Preparing the forest for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="8736a-118">建立 Lync Server 所使用的全域設定與通用群組。</span><span class="sxs-lookup"><span data-stu-id="8736a-118">Creates global settings and universal groups that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="8736a-119">針對您要部署 Lync Server 的部署中的每個樹系執行一次。</span><span class="sxs-lookup"><span data-stu-id="8736a-119">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="8736a-120">在每個樹系將要部署 Lync Server 的根域中。</span><span class="sxs-lookup"><span data-stu-id="8736a-120">In the root domain of each forest where Lync Server will be deployed.</span></span> <span data-ttu-id="8736a-121">您必須是 Enterprise Admins 群組的成員，才可執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="8736a-121">To run this step, you must be a member of the Enterprise Admins group.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="8736a-122">在資源樹系拓撲中，僅在資源樹系中執行此步驟，而不是在任何使用者樹系中執行。</span><span class="sxs-lookup"><span data-stu-id="8736a-122">In a resource forest topology, run this step only in the resource forest, not in any user forests.</span></span> <span data-ttu-id="8736a-123">在中央樹系拓撲中，請只在中央樹系中執行此步驟，而不是在任何使用者樹系中執行。</span><span class="sxs-lookup"><span data-stu-id="8736a-123">In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><span data-ttu-id="8736a-124"><a href="lync-server-2013-preparing-domains.md">準備 Lync Server 2013 的網域</a></span><span class="sxs-lookup"><span data-stu-id="8736a-124"><a href="lync-server-2013-preparing-domains.md">Preparing domains for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="8736a-125">在通用群組的成員要使用的物件上新增許可權。</span><span class="sxs-lookup"><span data-stu-id="8736a-125">Adds permissions on objects to be used by members of universal groups.</span></span></p>
<p><span data-ttu-id="8736a-126">針對每個使用者網域或伺服器網域執行一次。</span><span class="sxs-lookup"><span data-stu-id="8736a-126">Run once per user domain or server domain.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="8736a-127">如果您要從 Lync Server 2010 遷移至 Lync Server 2013，部署嚮導可能會指出已完成網域準備工作。</span><span class="sxs-lookup"><span data-stu-id="8736a-127">If you are migrating from Lync Server 2010 to Lync Server 2013, the Deployment Wizard may indicate that domain preparation is already complete.</span></span> <span data-ttu-id="8736a-128">您不需要重新執行網域準備工作。</span><span class="sxs-lookup"><span data-stu-id="8736a-128">You do not need to run domain preparation again.</span></span> <span data-ttu-id="8736a-129">許可權未從 Lync Server 2010 變更為 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="8736a-129">Permissions were not changed from Lync Server 2010 to Lync Server 2013.</span></span>


</div></td>
<td><p><span data-ttu-id="8736a-130">在每個將部署 Lync Server 的網域中的成員伺服器上。</span><span class="sxs-lookup"><span data-stu-id="8736a-130">On a member server in each domain where Lync Server will be deployed.</span></span> <span data-ttu-id="8736a-131">您必須是 Domain Admins 群組的成員，才可執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="8736a-131">To run this step, you must be a member of the Domain Admins group.</span></span></p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

<span data-ttu-id="8736a-132">Lync Server 2013 （如 Lync Server 2010）會將許多設定資訊儲存在中央管理存放區中，而不是 Office DS 中，就像是 Office 通訊伺服器 2007 R2 中的案例。</span><span class="sxs-lookup"><span data-stu-id="8736a-132">Lync Server 2013, like Lync Server 2010, stores much of the configuration information in the Central Management store instead of in AD DS as was the case in Office Communications Server 2007 R2.</span></span> <span data-ttu-id="8736a-133">不過，下列資訊會儲存在 AD DS 中：</span><span class="sxs-lookup"><span data-stu-id="8736a-133">However, the following information is stored in AD DS:</span></span>

  - <span data-ttu-id="8736a-134">**架構擴充**：</span><span class="sxs-lookup"><span data-stu-id="8736a-134">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="8736a-135">使用者物件擴充</span><span class="sxs-lookup"><span data-stu-id="8736a-135">User object extensions</span></span>
    
      - <span data-ttu-id="8736a-136">維護回溯相容性的 Office 通訊伺服器 2007 R2 類別分機</span><span class="sxs-lookup"><span data-stu-id="8736a-136">Extensions for Office Communications Server 2007 R2 classes to maintain backward compatibility</span></span>

<!-- end list -->

  - <span data-ttu-id="8736a-137">儲存在 Lync Server 擴充架構和現有架構類別中的**資料** () ：</span><span class="sxs-lookup"><span data-stu-id="8736a-137">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="8736a-138">使用者 SIP 統一資源識別項 (URI) 和其他使用者設定</span><span class="sxs-lookup"><span data-stu-id="8736a-138">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="8736a-139">回應群組和會議助理等應用程式的連絡人物件</span><span class="sxs-lookup"><span data-stu-id="8736a-139">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="8736a-140">中央管理存放區的指標</span><span class="sxs-lookup"><span data-stu-id="8736a-140">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="8736a-141">Kerberos 驗證帳戶 (選用的電腦物件) </span><span class="sxs-lookup"><span data-stu-id="8736a-141">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="8736a-142">在 Lync Server 2013 中，您可以委派安裝和管理，方法是將設定許可權授與 RTCUniversalServerAdmins 通用群組，讓該群組的成員可以在本機伺服器 (上安裝和啟動 Lync Server 2013，然後再將伺服器新增至拓撲、發行及啟用) 。</span><span class="sxs-lookup"><span data-stu-id="8736a-142">In Lync Server 2013, you delegate setup and administration by granting setup permissions to the RTCUniversalServerAdmins universal group so that members of that group can install and activate Lync Server 2013 on a local server (after the server has been added to the topology, published, and enabled).</span></span> <span data-ttu-id="8736a-143">委派的使用者必須是安裝和啟動 Lync Server 2013 之電腦上的本機系統管理員，但不需要是 Domain Admins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="8736a-143">The delegated users must be local administrators on the computer where they are installing and activating Lync Server 2013, but they do not need to be members of the Domain Admins group.</span></span> <span data-ttu-id="8736a-144">您也可以在指定的組織單位 (Ou) 中授與物件的許可權，使樹系準備期間建立的通用群組成員可以存取這些物件，而不是 Domain Admins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="8736a-144">You can also grant permissions for objects in specified organizational units (OUs) so that members of the universal groups created during forest preparation can access those objects without being members of the Domain Admins group.</span></span>

<span data-ttu-id="8736a-145">針對 Lync Server 2013 的新部署，全域設定必須儲存在設定容器中。</span><span class="sxs-lookup"><span data-stu-id="8736a-145">For new deployments of Lync Server 2013, global settings must be stored in the Configuration container.</span></span> <span data-ttu-id="8736a-146">如果您的組織是從舊版升級，而且您在系統容器內仍有全域設定，系統容器仍然支援。</span><span class="sxs-lookup"><span data-stu-id="8736a-146">If your organization is upgrading from an earlier version and you still have global settings in the System container, the System container is still supported.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8736a-147">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8736a-147">See Also</span></span>


[<span data-ttu-id="8736a-148">在 Lync Server 2013 中準備 Active Directory 架構</span><span class="sxs-lookup"><span data-stu-id="8736a-148">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
[<span data-ttu-id="8736a-149">Lync Server 2013 使用的 Active Directory 架構擴充功能、類別及屬性</span><span class="sxs-lookup"><span data-stu-id="8736a-149">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[<span data-ttu-id="8736a-150">準備 Lync Server 2013 的樹系</span><span class="sxs-lookup"><span data-stu-id="8736a-150">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="8736a-151">準備 Lync Server 2013 的網域</span><span class="sxs-lookup"><span data-stu-id="8736a-151">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


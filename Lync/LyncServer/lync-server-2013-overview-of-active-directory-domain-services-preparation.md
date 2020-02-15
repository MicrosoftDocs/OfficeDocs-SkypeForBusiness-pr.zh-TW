---
title: Active Directory 網域服務準備的 Lync Server 2013： 概觀
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
ms.openlocfilehash: 3085caf0b118b20bf52a4ff82a14b399d1ee6594
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a><span data-ttu-id="5ce9f-102">Lync Server 2013 中的 Active Directory 網域服務準備的概觀</span><span class="sxs-lookup"><span data-stu-id="5ce9f-102">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ce9f-103">_**主題上次修改日期：** 2012年-10-29_</span><span class="sxs-lookup"><span data-stu-id="5ce9f-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="5ce9f-104">若要準備您的 Lync Server 2013 部署的 Active Directory 網域服務，您必須以特定順序執行三個步驟。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-104">To prepare Active Directory Domain Services for your Lync Server 2013 deployment, you must perform three steps in a specific sequence.</span></span>

<span data-ttu-id="5ce9f-105">下表說明準備 AD DS 的 Lync Server 時所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-105">The following table describes the steps required to prepare AD DS for Lync Server.</span></span>

### <a name="active-directory-preparation-steps"></a><span data-ttu-id="5ce9f-106">Active Directory 準備步驟</span><span class="sxs-lookup"><span data-stu-id="5ce9f-106">Active Directory Preparation Steps</span></span>

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
<th><span data-ttu-id="5ce9f-107">步驟</span><span class="sxs-lookup"><span data-stu-id="5ce9f-107">Step</span></span></th>
<th><span data-ttu-id="5ce9f-108">描述</span><span class="sxs-lookup"><span data-stu-id="5ce9f-108">Description</span></span></th>
<th><span data-ttu-id="5ce9f-109">執行位置</span><span class="sxs-lookup"><span data-stu-id="5ce9f-109">Where run</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><span data-ttu-id="5ce9f-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">準備 Lync Server 2013 中的 Active Directory 結構描述</a></span><span class="sxs-lookup"><span data-stu-id="5ce9f-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparing the Active Directory schema in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5ce9f-111">將 Active Directory 架構延伸藉由新增新的類別和屬性所使用的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-111">Extends the Active Directory schema by adding new classes and attributes that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="5ce9f-112">執行一次每個樹系中部署 Lync Server 部署的位置。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-112">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="5ce9f-113">針對要部署 Lync Server 每個樹系根網域中的結構描述主圖形。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-113">Against the schema master in the root domain of each forest where Lync Server will be deployed.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="5ce9f-114">您不需要執行此步驟的根網域中，如果您的架構主機上有權限，但是您必須是 Schema Admins 群組中的根網域的成員，以及架構主機上的 Enterprise Admins 群組成員。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-114">You do not need to run this step in the root domain if you have permissions on the schema master, but you must be a member of the Schema Admins group in the root domain and a member of the Enterprise Admins group on the schema master.</span></span> <span data-ttu-id="5ce9f-115">在資源樹系拓撲中，執行此步驟中，只能在資源樹系中，在任何使用者樹系中。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-115">In a resource forest topology, run this step only in the resource forest, not in any user forests.</span></span> <span data-ttu-id="5ce9f-116">在中央樹系拓撲中，執行此步驟中，只能在中央樹系中，在任何使用者樹系中。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-116">In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><span data-ttu-id="5ce9f-117"><a href="lync-server-2013-preparing-the-forest.md">準備樹系的 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5ce9f-117"><a href="lync-server-2013-preparing-the-forest.md">Preparing the forest for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5ce9f-118">會建立全域設定和萬用群組所使用的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-118">Creates global settings and universal groups that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="5ce9f-119">執行一次每個樹系中部署 Lync Server 部署的位置。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-119">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="5ce9f-120">在 [Lync Server 將會部署每個樹系根網域。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-120">In the root domain of each forest where Lync Server will be deployed.</span></span> <span data-ttu-id="5ce9f-121">若要執行此步驟，您必須是 Enterprise Admins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-121">To run this step, you must be a member of the Enterprise Admins group.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="5ce9f-122">在資源樹系拓撲中，執行此步驟中，只能在資源樹系中，在任何使用者樹系中。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-122">In a resource forest topology, run this step only in the resource forest, not in any user forests.</span></span> <span data-ttu-id="5ce9f-123">在中央樹系拓撲中，執行此步驟中，只能在中央樹系中，在任何使用者樹系中。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-123">In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><span data-ttu-id="5ce9f-124"><a href="lync-server-2013-preparing-domains.md">Lync Server 2013 的準備網域</a></span><span class="sxs-lookup"><span data-stu-id="5ce9f-124"><a href="lync-server-2013-preparing-domains.md">Preparing domains for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5ce9f-125">新增權限萬用群組成員所使用的物件。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-125">Adds permissions on objects to be used by members of universal groups.</span></span></p>
<p><span data-ttu-id="5ce9f-126">每個使用者網域或伺服器網域執行一次。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-126">Run once per user domain or server domain.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="5ce9f-127">如果您從 Lync Server 2010 移轉至 Lync Server 2013，[部署精靈可能表示網域準備已完成。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-127">If you are migrating from Lync Server 2010 to Lync Server 2013, the Deployment Wizard may indicate that domain preparation is already complete.</span></span> <span data-ttu-id="5ce9f-128">您不需要執行網域準備一次。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-128">You do not need to run domain preparation again.</span></span> <span data-ttu-id="5ce9f-129">從 Lync Server 2010 to Lync Server 2013 未變更權限。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-129">Permissions were not changed from Lync Server 2010 to Lync Server 2013.</span></span>


</div></td>
<td><p><span data-ttu-id="5ce9f-130">在 [Lync Server 部署的位置的每個網域中的成員伺服器。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-130">On a member server in each domain where Lync Server will be deployed.</span></span> <span data-ttu-id="5ce9f-131">若要執行此步驟，您必須是 Domain Admins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-131">To run this step, you must be a member of the Domain Admins group.</span></span></p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

<span data-ttu-id="5ce9f-132">Lync Server 2013 中，例如 [Lync Server 2010]，儲存量的組態資訊的中央管理存放區中而不是 AD DS 中為已在 Office Communications Server 2007 R2 的案例。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-132">Lync Server 2013, like Lync Server 2010, stores much of the configuration information in the Central Management store instead of in AD DS as was the case in Office Communications Server 2007 R2.</span></span> <span data-ttu-id="5ce9f-133">不過，下列資訊會儲存在 AD DS 中：</span><span class="sxs-lookup"><span data-stu-id="5ce9f-133">However, the following information is stored in AD DS:</span></span>

  - <span data-ttu-id="5ce9f-134">**架構延伸模組**：</span><span class="sxs-lookup"><span data-stu-id="5ce9f-134">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="5ce9f-135">使用者物件延伸</span><span class="sxs-lookup"><span data-stu-id="5ce9f-135">User object extensions</span></span>
    
      - <span data-ttu-id="5ce9f-136">Office Communications Server 2007 R2 類別，以維持回溯相容性的副檔名</span><span class="sxs-lookup"><span data-stu-id="5ce9f-136">Extensions for Office Communications Server 2007 R2 classes to maintain backward compatibility</span></span>

<!-- end list -->

  - <span data-ttu-id="5ce9f-137">**資料**（儲存在 Lync Server 延伸架構和現有的架構類別中）：</span><span class="sxs-lookup"><span data-stu-id="5ce9f-137">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="5ce9f-138">使用者的 SIP 統一資源識別元 (URI) 及其他使用者設定</span><span class="sxs-lookup"><span data-stu-id="5ce9f-138">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="5ce9f-139">回應群組與會議服務員等應用程式的連絡人物件</span><span class="sxs-lookup"><span data-stu-id="5ce9f-139">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="5ce9f-140">中央管理存放區的指標</span><span class="sxs-lookup"><span data-stu-id="5ce9f-140">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="5ce9f-141">Kerberos 驗證帳戶 （選擇性的電腦物件）</span><span class="sxs-lookup"><span data-stu-id="5ce9f-141">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="5ce9f-142">在 Lync Server 2013 中，您委派的安裝和管理 RTCUniversalServerAdmins 萬用群組設定權限授與使該群組的成員可以安裝並在本機伺服器上啟動 Lync Server 2013 (伺服器已新增至之後拓撲中，發佈，而且可啟用）。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-142">In Lync Server 2013, you delegate setup and administration by granting setup permissions to the RTCUniversalServerAdmins universal group so that members of that group can install and activate Lync Server 2013 on a local server (after the server has been added to the topology, published, and enabled).</span></span> <span data-ttu-id="5ce9f-143">委派的使用者必須是本機系統管理員，他們會安裝並啟動 Lync Server 2013，但它們不需要成為 Domain Admins 群組的成員的電腦上。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-143">The delegated users must be local administrators on the computer where they are installing and activating Lync Server 2013, but they do not need to be members of the Domain Admins group.</span></span> <span data-ttu-id="5ce9f-144">您也可以授與指定組織單位 (Ou) 中的物件的權限，讓樹系準備時建立萬用群組的成員可以存取這些物件不是 Domain Admins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-144">You can also grant permissions for objects in specified organizational units (OUs) so that members of the universal groups created during forest preparation can access those objects without being members of the Domain Admins group.</span></span>

<span data-ttu-id="5ce9f-145">針對新的 Lync Server 2013 的部署，全域設定必須儲存在 [Configuration] 容器。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-145">For new deployments of Lync Server 2013, global settings must be stored in the Configuration container.</span></span> <span data-ttu-id="5ce9f-146">如果您的組織從較早版本升級，仍必須在將系統容器中的全域設定，仍支援系統容器。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-146">If your organization is upgrading from an earlier version and you still have global settings in the System container, the System container is still supported.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5ce9f-147">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5ce9f-147">See Also</span></span>


[<span data-ttu-id="5ce9f-148">準備 Lync Server 2013 中的 Active Directory 結構描述</span><span class="sxs-lookup"><span data-stu-id="5ce9f-148">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
[<span data-ttu-id="5ce9f-149">Active Directory 架構延伸模組、 類別及 Lync Server 2013 所使用的屬性</span><span class="sxs-lookup"><span data-stu-id="5ce9f-149">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[<span data-ttu-id="5ce9f-150">準備樹系的 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ce9f-150">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="5ce9f-151">Lync Server 2013 的準備網域</span><span class="sxs-lookup"><span data-stu-id="5ce9f-151">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: A/V 會議的 Lync Server 2013 部署檢查清單
description: A/V 會議的 Lync Server 2013 部署檢查清單。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for A/V conferencing
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49733684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9a4584172ed4c01eb163ea51aa4f62c2ce75185
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557769"
---
# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="6fce1-103">Lync Server 2013 中 A/V 會議的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="6fce1-103">Deployment checklist for A/V conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fce1-104">_**主題上次修改日期：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="6fce1-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="6fce1-105">與其他 Lync Server 2013 元件的部署一樣，部署 A/V 會議需要您使用拓撲產生器來建立及發佈併入會議的拓撲。</span><span class="sxs-lookup"><span data-stu-id="6fce1-105">As with deployment of your other Lync Server 2013 components, deployment of A/V conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="6fce1-106">部署順序</span><span class="sxs-lookup"><span data-stu-id="6fce1-106">Deployment Sequence</span></span>

<span data-ttu-id="6fce1-107">您可以在部署初始拓撲時，或在部署至少一個前端集區或 Standard Edition server 之後，部署會議。</span><span class="sxs-lookup"><span data-stu-id="6fce1-107">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="6fce1-108">會議部署程序</span><span class="sxs-lookup"><span data-stu-id="6fce1-108">Conferencing Deployment Process</span></span>

<span data-ttu-id="6fce1-109">下表提供將會議部署至現有拓撲所需的步驟概觀。</span><span class="sxs-lookup"><span data-stu-id="6fce1-109">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6fce1-110">階段</span><span class="sxs-lookup"><span data-stu-id="6fce1-110">Phase</span></span></th>
<th><span data-ttu-id="6fce1-111">步驟</span><span class="sxs-lookup"><span data-stu-id="6fce1-111">Steps</span></span></th>
<th><span data-ttu-id="6fce1-112">角色和群組成員資格</span><span class="sxs-lookup"><span data-stu-id="6fce1-112">Roles and group memberships</span></span></th>
<th><span data-ttu-id="6fce1-113">文件</span><span class="sxs-lookup"><span data-stu-id="6fce1-113">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fce1-114"><strong>安裝必備硬體和軟體</strong></span><span class="sxs-lookup"><span data-stu-id="6fce1-114"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="6fce1-115">會議會在前端集區和 Standard Edition server 的前端伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="6fce1-115">Conferencing runs on Front End Servers of a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="6fce1-116">安裝這些伺服器除必條件外，沒有額外的硬體或軟體需求。</span><span class="sxs-lookup"><span data-stu-id="6fce1-116">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6fce1-117">Lync Server 2013 使用 Office Web Apps 與 Office Web apps Server 來處理 PowerPoint 簡報的共用及呈現。</span><span class="sxs-lookup"><span data-stu-id="6fce1-117">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="6fce1-118">如需安裝及設定 Office Web Apps Server 的詳細資訊，請參閱設定 <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Office Web Apps server 與 Lync server 2013 的整合</A>。</span><span class="sxs-lookup"><span data-stu-id="6fce1-118">For details about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="6fce1-119">為本機系統管理員成員之網域使用者</span><span class="sxs-lookup"><span data-stu-id="6fce1-119">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="6fce1-120">支援檔中的<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支援的硬體</a></span><span class="sxs-lookup"><span data-stu-id="6fce1-120"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="6fce1-121">支援檔中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的伺服器軟體和基礎結構支援</a></span><span class="sxs-lookup"><span data-stu-id="6fce1-121"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="6fce1-122">在規劃檔中<a href="lync-server-2013-determining-your-system-requirements.md">決定 Lync Server 2013 的系統需求</a>。</span><span class="sxs-lookup"><span data-stu-id="6fce1-122"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="6fce1-123">規劃檔中的<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013</a>中封存的技術需求。</span><span class="sxs-lookup"><span data-stu-id="6fce1-123"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fce1-124"><strong>建立適當的內部拓撲以支援會議</strong></span><span class="sxs-lookup"><span data-stu-id="6fce1-124"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="6fce1-125">執行拓撲產生器，將會議新增至拓撲，然後發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="6fce1-125">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="6fce1-126">定義拓撲，須以本機使用者群組成員帳戶進行</span><span class="sxs-lookup"><span data-stu-id="6fce1-126">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="6fce1-127">若要發行拓撲，則為 Domain Admins 群組和 RTCUniversalServerAdmins 群組成員的帳戶，且具有「完全控制」 (許可權的檔案共用上的「讀取/寫入/修改」) ，以用於 Lync Server 2013 file store (，拓撲產生器可以設定必要的 Dacl) </span><span class="sxs-lookup"><span data-stu-id="6fce1-127">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="6fce1-128">在部署檔中<a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">定義及設定 Lync Server 2013 拓撲</a>產生器中的拓撲。</span><span class="sxs-lookup"><span data-stu-id="6fce1-128"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fce1-129"><strong>設定會議原則及支援</strong></span><span class="sxs-lookup"><span data-stu-id="6fce1-129"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="6fce1-130">使用 Lync Server 2013 控制台或 Lync Server 管理命令介面來設定會議設定。</span><span class="sxs-lookup"><span data-stu-id="6fce1-130">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="6fce1-131">RTCUniversalServerAdmins 群組 (Windows PowerShell 只) 或指派使用者至 [] 或 [CSAdministrator] 角色</span><span class="sxs-lookup"><span data-stu-id="6fce1-131">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="6fce1-132">Operations 檔中的<a href="lync-server-2013-conferencing-policies.md">Lync Server 2013 中的會議原則</a>。</span><span class="sxs-lookup"><span data-stu-id="6fce1-132"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6fce1-133">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6fce1-133">See Also</span></span>


[<span data-ttu-id="6fce1-134">Lync Server 2013 中的會議綜述</span><span class="sxs-lookup"><span data-stu-id="6fce1-134">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)  
[<span data-ttu-id="6fce1-135">在 Lync Server 2013 中定義會議需求</span><span class="sxs-lookup"><span data-stu-id="6fce1-135">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


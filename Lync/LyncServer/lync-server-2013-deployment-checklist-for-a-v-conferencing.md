---
title: 適用于 A/V 會議的 Lync Server 2013 部署檢查清單
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
ms.openlocfilehash: 736719475d77f67932b350e1684b4af26ca2fbd6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="b0196-102">Lync Server 2013 中的 A/V 會議部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="b0196-102">Deployment checklist for A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0196-103">_**主題上次修改日期：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="b0196-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="b0196-104">隨著您其他 Lync Server 2013 元件的部署，部署 A/V 會議時，需要您使用拓撲建立器來建立併發布包含會議的拓撲。</span><span class="sxs-lookup"><span data-stu-id="b0196-104">As with deployment of your other Lync Server 2013 components, deployment of A/V conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="b0196-105">部署順序</span><span class="sxs-lookup"><span data-stu-id="b0196-105">Deployment Sequence</span></span>

<span data-ttu-id="b0196-106">您可以在部署初始拓朴時，或在部署了至少一個前端池或標準版伺服器之後，部署會議。</span><span class="sxs-lookup"><span data-stu-id="b0196-106">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="b0196-107">會議部署流程</span><span class="sxs-lookup"><span data-stu-id="b0196-107">Conferencing Deployment Process</span></span>

<span data-ttu-id="b0196-108">下表提供將會議部署至現有拓撲所需的步驟的概覽。</span><span class="sxs-lookup"><span data-stu-id="b0196-108">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0196-109">分</span><span class="sxs-lookup"><span data-stu-id="b0196-109">Phase</span></span></th>
<th><span data-ttu-id="b0196-110">步驟</span><span class="sxs-lookup"><span data-stu-id="b0196-110">Steps</span></span></th>
<th><span data-ttu-id="b0196-111">角色和群組成員資格</span><span class="sxs-lookup"><span data-stu-id="b0196-111">Roles and group memberships</span></span></th>
<th><span data-ttu-id="b0196-112">文件</span><span class="sxs-lookup"><span data-stu-id="b0196-112">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0196-113"><strong>安裝必備的硬體和軟體</strong></span><span class="sxs-lookup"><span data-stu-id="b0196-113"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="b0196-114">會議會在前端池和標準版伺服器的前端伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="b0196-114">Conferencing runs on Front End Servers of a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="b0196-115">除了安裝這些伺服器所需的其他硬體或軟體需求之外，它還沒有其他硬體或軟體需求。</span><span class="sxs-lookup"><span data-stu-id="b0196-115">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b0196-116">Lync Server 2013 使用 Office Web Apps 和 Office Web Apps 伺服器來處理 PowerPoint 簡報的共用和轉譯。</span><span class="sxs-lookup"><span data-stu-id="b0196-116">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="b0196-117">如需安裝及設定 Office Web Apps 伺服器的詳細資料，請參閱設定<A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">與 Office Web Apps server 和 Lync Server 2013 的整合</A>。</span><span class="sxs-lookup"><span data-stu-id="b0196-117">For details about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="b0196-118">屬於本機管理員群組成員的網域使用者</span><span class="sxs-lookup"><span data-stu-id="b0196-118">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="b0196-119">支援檔中的<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支援的硬體</a></span><span class="sxs-lookup"><span data-stu-id="b0196-119"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="b0196-120">支援檔中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的伺服器軟體和基礎結構支援</a></span><span class="sxs-lookup"><span data-stu-id="b0196-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="b0196-121">在規劃檔中<a href="lync-server-2013-determining-your-system-requirements.md">判斷 Lync Server 2013 的系統需求</a>。</span><span class="sxs-lookup"><span data-stu-id="b0196-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="b0196-122">規劃檔中的<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 中的存檔技術需求</a>。</span><span class="sxs-lookup"><span data-stu-id="b0196-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0196-123"><strong>建立適當的內部拓朴以支援會議</strong></span><span class="sxs-lookup"><span data-stu-id="b0196-123"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="b0196-124">執行拓撲建立器，將會議新增至拓撲結構，然後發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="b0196-124">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="b0196-125">若要定義拓撲，該帳戶是 [本機使用者] 群組的成員</span><span class="sxs-lookup"><span data-stu-id="b0196-125">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="b0196-126">若要發佈拓朴，該帳戶是網域系統管理員群組和 RTCUniversalServerAdmins 群組的成員，且在檔案共用上擁有 [完全控制] 許可權（讀取/寫入/修改），以用於 Lync Server 2013 檔案存放區（以便讓拓撲建立器能夠設定所需的 Dacl）</span><span class="sxs-lookup"><span data-stu-id="b0196-126">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="b0196-127">在 [部署] 檔中，在 [Lync Server 2013] 的 [拓撲建立器] 中<a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">定義及設定拓撲</a>。</span><span class="sxs-lookup"><span data-stu-id="b0196-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0196-128"><strong>設定會議原則及支援</strong></span><span class="sxs-lookup"><span data-stu-id="b0196-128"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="b0196-129">使用 Lync Server 2013 的 [控制台] 或 [Lync Server 管理命令介面] 來設定會議設定。</span><span class="sxs-lookup"><span data-stu-id="b0196-129">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="b0196-130">RTCUniversalServerAdmins 群組（僅限 Windows PowerShell）或將使用者指派至 [] 或 CSAdministrator 角色</span><span class="sxs-lookup"><span data-stu-id="b0196-130">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="b0196-131"><a href="lync-server-2013-conferencing-policies.md">Lync Server 2013 中的會議原則</a>在作業檔中。</span><span class="sxs-lookup"><span data-stu-id="b0196-131"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b0196-132">請參閱</span><span class="sxs-lookup"><span data-stu-id="b0196-132">See Also</span></span>


[<span data-ttu-id="b0196-133">Lync Server 2013 中的會議概觀</span><span class="sxs-lookup"><span data-stu-id="b0196-133">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)  
[<span data-ttu-id="b0196-134">在 Lync Server 2013 中定義會議需求</span><span class="sxs-lookup"><span data-stu-id="b0196-134">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


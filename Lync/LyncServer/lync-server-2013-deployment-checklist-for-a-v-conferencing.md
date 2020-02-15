---
title: Lync Server 2013 部署檢查清單，a / V 會議
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
ms.openlocfilehash: 5a0c48d78c33c652f7a28e277600fa957cb6fd1f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="81221-102">部署檢查清單 a / V 會議在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81221-102">Deployment checklist for A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81221-103">_**主題上次修改日期：** 2012年-09-30_</span><span class="sxs-lookup"><span data-stu-id="81221-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="81221-104">在部署其他 Lync Server 2013 元件，部署 A / V 會議會要求您使用拓撲產生器來建立及發行納入會議的拓撲。</span><span class="sxs-lookup"><span data-stu-id="81221-104">As with deployment of your other Lync Server 2013 components, deployment of A/V conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="81221-105">部署順序</span><span class="sxs-lookup"><span data-stu-id="81221-105">Deployment Sequence</span></span>

<span data-ttu-id="81221-106">您可以將會議部署在您部署初始拓撲的同時或之後您已部署至少一個前端集區或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="81221-106">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="81221-107">會議部署程序</span><span class="sxs-lookup"><span data-stu-id="81221-107">Conferencing Deployment Process</span></span>

<span data-ttu-id="81221-108">下表提供將會議部署至現有拓撲所需的步驟概觀。</span><span class="sxs-lookup"><span data-stu-id="81221-108">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81221-109">階段</span><span class="sxs-lookup"><span data-stu-id="81221-109">Phase</span></span></th>
<th><span data-ttu-id="81221-110">步驟</span><span class="sxs-lookup"><span data-stu-id="81221-110">Steps</span></span></th>
<th><span data-ttu-id="81221-111">角色和群組成員資格</span><span class="sxs-lookup"><span data-stu-id="81221-111">Roles and group memberships</span></span></th>
<th><span data-ttu-id="81221-112">文件</span><span class="sxs-lookup"><span data-stu-id="81221-112">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81221-113"><strong>安裝必備硬體和軟體</strong></span><span class="sxs-lookup"><span data-stu-id="81221-113"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="81221-114">前端伺服器的前端集區及 Standard Edition server 上執行會議。</span><span class="sxs-lookup"><span data-stu-id="81221-114">Conferencing runs on Front End Servers of a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="81221-115">安裝這些伺服器除必條件外，沒有額外的硬體或軟體需求。</span><span class="sxs-lookup"><span data-stu-id="81221-115">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="81221-116">Lync Server 2013 使用 Office Web Apps 與 Office Web Apps Server 來處理共用和 PowerPoint 簡報的轉譯。</span><span class="sxs-lookup"><span data-stu-id="81221-116">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="81221-117">如需安裝及設定 Office Web Apps Server 的詳細資訊，請參閱<A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">設定整合 Office Web Apps Server 與 Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="81221-117">For details about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="81221-118">為本機系統管理員成員之網域使用者</span><span class="sxs-lookup"><span data-stu-id="81221-118">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="81221-119">支援文件中<a href="lync-server-2013-supported-hardware.md">的 Lync Server 2013 支援硬體</a></span><span class="sxs-lookup"><span data-stu-id="81221-119"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="81221-120">支援文件中的 [ <a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync Server 2013 中的伺服器軟體和基礎結構支援</a></span><span class="sxs-lookup"><span data-stu-id="81221-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="81221-121"><a href="lync-server-2013-determining-your-system-requirements.md">決定您的系統需求，針對 Lync Server 2013</a>中規劃文件。</span><span class="sxs-lookup"><span data-stu-id="81221-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="81221-122">規劃文件中<a href="lync-server-2013-technical-requirements-for-archiving.md">的 technical requirements for Lync Server 2013 中的封存</a>。</span><span class="sxs-lookup"><span data-stu-id="81221-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81221-123"><strong>建立適當的內部拓撲以支援會議</strong></span><span class="sxs-lookup"><span data-stu-id="81221-123"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="81221-124">執行拓撲產生器來將會議新增至拓撲，並再發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="81221-124">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="81221-125">定義拓撲，須以本機使用者群組成員帳戶進行</span><span class="sxs-lookup"><span data-stu-id="81221-125">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="81221-126">若要發行拓撲，這是 Domain Admins 群組和 RTCUniversalServerAdmins 群組的成員，且用於 Lync Server 2013 檔案存放區 （以便拓撲產生器可以設定必要的 Dacl） 的檔案共用具有完整控制權限 （讀取/寫入/修改） 的帳戶</span><span class="sxs-lookup"><span data-stu-id="81221-126">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="81221-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">定義和設定拓撲在拓撲產生器中的 Lync Server 2013</a>部署文件中。</span><span class="sxs-lookup"><span data-stu-id="81221-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81221-128"><strong>設定會議原則及支援</strong></span><span class="sxs-lookup"><span data-stu-id="81221-128"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="81221-129">使用 Lync Server 2013 控制台] 或 [Lync Server 管理命令介面來設定會議設定。</span><span class="sxs-lookup"><span data-stu-id="81221-129">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="81221-130">以 RTCUniversalServerAdmins 群組 (僅限 Windows PowerShell)，或將使用者指派給] 或 CSAdministrator 角色</span><span class="sxs-lookup"><span data-stu-id="81221-130">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="81221-131">作業文件中的<a href="lync-server-2013-conferencing-policies.md">Lync Server 2013 中的 conferencing policies</a> 。</span><span class="sxs-lookup"><span data-stu-id="81221-131"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="81221-132">另請參閱</span><span class="sxs-lookup"><span data-stu-id="81221-132">See Also</span></span>


[<span data-ttu-id="81221-133">Lync Server 2013 中的會議概觀</span><span class="sxs-lookup"><span data-stu-id="81221-133">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)  
[<span data-ttu-id="81221-134">Lync Server 2013 中定義會議需求</span><span class="sxs-lookup"><span data-stu-id="81221-134">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


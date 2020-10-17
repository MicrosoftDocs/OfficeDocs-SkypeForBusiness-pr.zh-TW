---
title: Web 會議的 Lync Server 2013 部署檢查清單
description: Web 會議的 Lync Server 2013 部署檢查清單。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6194cb71af268a45dc5c142c1814d8c1ef15c09e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562179"
---
# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a><span data-ttu-id="6e9a8-103">Lync Server 2013 中的 web 會議部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="6e9a8-103">Deployment checklist for web conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e9a8-104">_**主題上次修改日期：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="6e9a8-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="6e9a8-105">與其他 Lync Server 2013 元件的部署一樣，部署 web 會議時，需要您使用拓撲產生器來建立及發佈併入會議的拓撲。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-105">As with deployment of your other Lync Server 2013 components, deployment of web conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="6e9a8-106">部署順序</span><span class="sxs-lookup"><span data-stu-id="6e9a8-106">Deployment Sequence</span></span>

<span data-ttu-id="6e9a8-107">您可以在部署初始拓撲時，或在部署至少一個前端集區或 Standard Edition server 之後，部署會議。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-107">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="6e9a8-108">會議部署程序</span><span class="sxs-lookup"><span data-stu-id="6e9a8-108">Conferencing Deployment Process</span></span>

<span data-ttu-id="6e9a8-109">下表提供將會議部署至現有拓撲所需的步驟概觀。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-109">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e9a8-110">階段</span><span class="sxs-lookup"><span data-stu-id="6e9a8-110">Phase</span></span></th>
<th><span data-ttu-id="6e9a8-111">步驟</span><span class="sxs-lookup"><span data-stu-id="6e9a8-111">Steps</span></span></th>
<th><span data-ttu-id="6e9a8-112">角色和群組成員資格</span><span class="sxs-lookup"><span data-stu-id="6e9a8-112">Roles and group memberships</span></span></th>
<th><span data-ttu-id="6e9a8-113">文件</span><span class="sxs-lookup"><span data-stu-id="6e9a8-113">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e9a8-114"><strong>安裝必備硬體和軟體</strong></span><span class="sxs-lookup"><span data-stu-id="6e9a8-114"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="6e9a8-115">會議會在前端集區和 Standard Edition server 的前端伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-115">Conferencing runs on Front End Servers in a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="6e9a8-116">安裝這些伺服器除必條件外，沒有額外的硬體或軟體需求。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-116">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6e9a8-117">Lync Server 2013 使用 Office Web Apps 與 Office Web apps Server 來處理 PowerPoint 簡報的共用及呈現。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-117">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="6e9a8-118">如需安裝及設定 Office Web Apps Server 的詳細資訊，請參閱設定 <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Office Web Apps server 與 Lync server 2013 的整合</A>。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-118">For information about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="6e9a8-119">為本機系統管理員成員之網域使用者</span><span class="sxs-lookup"><span data-stu-id="6e9a8-119">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="6e9a8-120">支援檔中的<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支援的硬體</a></span><span class="sxs-lookup"><span data-stu-id="6e9a8-120"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="6e9a8-121">支援檔中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的伺服器軟體和基礎結構支援</a></span><span class="sxs-lookup"><span data-stu-id="6e9a8-121"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="6e9a8-122">在規劃檔中<a href="lync-server-2013-determining-your-system-requirements.md">決定 Lync Server 2013 的系統需求</a>。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-122"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="6e9a8-123">規劃檔中的<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013</a>中封存的技術需求。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-123"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e9a8-124"><strong>建立適當的內部拓撲以支援會議</strong></span><span class="sxs-lookup"><span data-stu-id="6e9a8-124"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="6e9a8-125">執行拓撲產生器，將會議新增至拓撲，然後發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-125">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="6e9a8-126">定義拓撲，須以本機使用者群組成員帳戶進行</span><span class="sxs-lookup"><span data-stu-id="6e9a8-126">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="6e9a8-127">若要發行拓撲，則為 Domain Admins 群組和 RTCUniversalServerAdmins 群組成員的帳戶，且具有「完全控制」 (許可權的檔案共用上的「讀取/寫入/修改」) ，以用於 Lync Server 2013 file store (，拓撲產生器可以設定必要的 Dacl) </span><span class="sxs-lookup"><span data-stu-id="6e9a8-127">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="6e9a8-128">在部署檔中<a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">定義及設定 Lync Server 2013 拓撲</a>產生器中的拓撲。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-128"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e9a8-129"><strong>設定會議原則及支援</strong></span><span class="sxs-lookup"><span data-stu-id="6e9a8-129"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="6e9a8-130">使用 Lync Server 2013 控制台或 Lync Server 管理命令介面來設定會議設定。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-130">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="6e9a8-131">RTCUniversalServerAdmins 群組 ( Windows PowerShell 只) 或指派使用者至 [] 或 [CSAdministrator] 角色</span><span class="sxs-lookup"><span data-stu-id="6e9a8-131">RTCUniversalServerAdmins group ( Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="6e9a8-132">Operations 檔中的<a href="lync-server-2013-conferencing-policies.md">Lync Server 2013 中的會議原則</a>。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-132"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6e9a8-133">Lync Server 2013 現在包括 **MaxUploadFileSizeMb** 設定，它會限制在會議期間可上傳的檔案大小。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-133">Lync Server 2013 now includes the **MaxUploadFileSizeMb** setting, which limits the size of files that can be uploaded during a meeting.</span></span> <span data-ttu-id="6e9a8-134">此設定的預設值為 500 MB。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-134">The default value for this setting is 500 MB.</span></span> <span data-ttu-id="6e9a8-135">您可以使用**Set-CsConferencingConfiguration** Cmdlet 來調整**MaxUploadFileSizeMb** 。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-135">You can adjust **MaxUploadFileSizeMb** using the **Set-CsConferencingConfiguration** cmdlet.</span></span>

<span data-ttu-id="6e9a8-136">**MaxUploadFileSizeMb** 不會限制 Lync Web App 的檔案上傳設定。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-136">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="6e9a8-137">Lync Web App 的檔案大小上傳限制設定為大約30MB，且由 IIS web.config 檔案：/DataCollabWeb/Int \[ Ext \] /Handler/web.config 所控制。若要設定 Lync Web App 的檔案大小上傳限制，請更新， `maxRequestLength` 並 `maxAllowedContentLength` 在 web.config 檔中，如下所示。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-137">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by LWA client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for LWA upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

<span data-ttu-id="6e9a8-138">您必須更新每一部前端伺服器的 web.config 檔案。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-138">You must update the web.config file for each Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


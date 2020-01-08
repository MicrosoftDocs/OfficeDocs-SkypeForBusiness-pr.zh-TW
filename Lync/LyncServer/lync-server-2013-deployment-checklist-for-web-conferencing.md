---
title: 適用于 web 會議的 Lync Server 2013 部署檢查清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5f845fd57846d7f9b58351d1cb77f3f1c0142ed
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a><span data-ttu-id="019a3-102">Lync Server 2013 的網路會議部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="019a3-102">Deployment checklist for web conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="019a3-103">_**主題上次修改日期：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="019a3-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="019a3-104">隨著您其他 Lync Server 2013 元件的部署，部署 web 會議時，需要您使用拓撲建立器來建立併發布包含會議的拓撲。</span><span class="sxs-lookup"><span data-stu-id="019a3-104">As with deployment of your other Lync Server 2013 components, deployment of web conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="019a3-105">部署順序</span><span class="sxs-lookup"><span data-stu-id="019a3-105">Deployment Sequence</span></span>

<span data-ttu-id="019a3-106">您可以在部署初始拓朴時，或在部署了至少一個前端池或標準版伺服器之後，部署會議。</span><span class="sxs-lookup"><span data-stu-id="019a3-106">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="019a3-107">會議部署流程</span><span class="sxs-lookup"><span data-stu-id="019a3-107">Conferencing Deployment Process</span></span>

<span data-ttu-id="019a3-108">下表提供將會議部署至現有拓撲所需的步驟的概覽。</span><span class="sxs-lookup"><span data-stu-id="019a3-108">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="019a3-109">分</span><span class="sxs-lookup"><span data-stu-id="019a3-109">Phase</span></span></th>
<th><span data-ttu-id="019a3-110">步驟</span><span class="sxs-lookup"><span data-stu-id="019a3-110">Steps</span></span></th>
<th><span data-ttu-id="019a3-111">角色和群組成員資格</span><span class="sxs-lookup"><span data-stu-id="019a3-111">Roles and group memberships</span></span></th>
<th><span data-ttu-id="019a3-112">文件</span><span class="sxs-lookup"><span data-stu-id="019a3-112">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="019a3-113"><strong>安裝必備的硬體和軟體</strong></span><span class="sxs-lookup"><span data-stu-id="019a3-113"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="019a3-114">在前端伺服器和標準版伺服器中，在前端伺服器上執行會議。</span><span class="sxs-lookup"><span data-stu-id="019a3-114">Conferencing runs on Front End Servers in a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="019a3-115">除了安裝這些伺服器所需的其他硬體或軟體需求之外，它還沒有其他硬體或軟體需求。</span><span class="sxs-lookup"><span data-stu-id="019a3-115">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="019a3-116">Lync Server 2013 使用 Office Web Apps 和 Office Web Apps 伺服器來處理 PowerPoint 簡報的共用和轉譯。</span><span class="sxs-lookup"><span data-stu-id="019a3-116">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="019a3-117">如需安裝及設定 Office Web Apps 伺服器的相關資訊，請參閱設定<A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">與 Office Web Apps server 和 Lync Server 2013 的整合</A>。</span><span class="sxs-lookup"><span data-stu-id="019a3-117">For information about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="019a3-118">屬於本機管理員群組成員的網域使用者</span><span class="sxs-lookup"><span data-stu-id="019a3-118">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="019a3-119">支援檔中的<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支援的硬體</a></span><span class="sxs-lookup"><span data-stu-id="019a3-119"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="019a3-120">支援檔中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的伺服器軟體和基礎結構支援</a></span><span class="sxs-lookup"><span data-stu-id="019a3-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="019a3-121">在規劃檔中<a href="lync-server-2013-determining-your-system-requirements.md">判斷 Lync Server 2013 的系統需求</a>。</span><span class="sxs-lookup"><span data-stu-id="019a3-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="019a3-122">規劃檔中的<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 中的存檔技術需求</a>。</span><span class="sxs-lookup"><span data-stu-id="019a3-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="019a3-123"><strong>建立適當的內部拓朴以支援會議</strong></span><span class="sxs-lookup"><span data-stu-id="019a3-123"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="019a3-124">執行拓撲建立器，將會議新增至拓撲結構，然後發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="019a3-124">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="019a3-125">若要定義拓撲，該帳戶是 [本機使用者] 群組的成員</span><span class="sxs-lookup"><span data-stu-id="019a3-125">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="019a3-126">若要發佈拓朴，該帳戶是網域系統管理員群組和 RTCUniversalServerAdmins 群組的成員，且在檔案共用上擁有 [完全控制] 許可權（讀取/寫入/修改），以用於 Lync Server 2013 檔案存放區（以便讓拓撲建立器能夠設定所需的 Dacl）</span><span class="sxs-lookup"><span data-stu-id="019a3-126">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="019a3-127">在 [部署] 檔中，在 [Lync Server 2013] 的 [拓撲建立器] 中<a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">定義及設定拓撲</a>。</span><span class="sxs-lookup"><span data-stu-id="019a3-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="019a3-128"><strong>設定會議原則及支援</strong></span><span class="sxs-lookup"><span data-stu-id="019a3-128"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="019a3-129">使用 Lync Server 2013 的 [控制台] 或 [Lync Server 管理命令介面] 來設定會議設定。</span><span class="sxs-lookup"><span data-stu-id="019a3-129">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="019a3-130">RTCUniversalServerAdmins 群組（僅限 Windows PowerShell）或將使用者指派至 [] 或 CSAdministrator 角色</span><span class="sxs-lookup"><span data-stu-id="019a3-130">RTCUniversalServerAdmins group ( Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="019a3-131"><a href="lync-server-2013-conferencing-policies.md">Lync Server 2013 中的會議原則</a>在作業檔中。</span><span class="sxs-lookup"><span data-stu-id="019a3-131"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="019a3-132">Lync Server 2013 現在包含 [ **MaxUploadFileSizeMb** ] 設定，可限制在會議期間可以上傳的檔案大小。</span><span class="sxs-lookup"><span data-stu-id="019a3-132">Lync Server 2013 now includes the **MaxUploadFileSizeMb** setting, which limits the size of files that can be uploaded during a meeting.</span></span> <span data-ttu-id="019a3-133">此設定的預設值為 500 MB。</span><span class="sxs-lookup"><span data-stu-id="019a3-133">The default value for this setting is 500 MB.</span></span> <span data-ttu-id="019a3-134">您可以使用**CsConferencingConfiguration** Cmdlet 來調整**MaxUploadFileSizeMb** 。</span><span class="sxs-lookup"><span data-stu-id="019a3-134">You can adjust **MaxUploadFileSizeMb** using the **Set-CsConferencingConfiguration** cmdlet.</span></span>

<span data-ttu-id="019a3-135">**MaxUploadFileSizeMb**不會限制 Lync Web App 的 [檔案上傳] 設定。</span><span class="sxs-lookup"><span data-stu-id="019a3-135">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="019a3-136">Lync Web App 的檔案大小上傳限制是設定為 [大約 30MB]，且由 IIS web.config 檔案所控制：/DataCollabWeb/Int\[Ext\]/Handler/web.config。若要設定 Lync Web App 的檔案大小上傳限制， `maxRequestLength`請`maxAllowedContentLength`更新並放在 web.config 檔案中，如下所示。</span><span class="sxs-lookup"><span data-stu-id="019a3-136">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

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

<span data-ttu-id="019a3-137">您必須為每個前端伺服器更新 web.config 檔案。</span><span class="sxs-lookup"><span data-stu-id="019a3-137">You must update the web.config file for each Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


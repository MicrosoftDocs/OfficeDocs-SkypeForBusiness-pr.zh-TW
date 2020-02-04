---
title: Lync Server 2013 會議的技術需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for conferencing
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48183923
ms.date: 06/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a275836b940cfe2c56b184d238bc12c432132e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="5ec73-102">Lync Server 2013 中會議的技術需求</span><span class="sxs-lookup"><span data-stu-id="5ec73-102">Technical requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ec73-103">_**主題上次修改日期：** 2014-06-25_</span><span class="sxs-lookup"><span data-stu-id="5ec73-103">_**Topic Last Modified:** 2014-06-25_</span></span>

<span data-ttu-id="5ec73-104">針對 Lync Server 2013、電話撥入式會議、A/V 會議、立即訊息（IM）會議和網路會議功能，都必須在前端伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="5ec73-104">For Lync Server 2013, dial-in conferencing, A/V conferencing, instant messaging (IM) conferencing and web conferencing capabilities always run on Front End Servers.</span></span>

<span data-ttu-id="5ec73-105">本節詳細說明這些伺服器的硬體和軟體需求，以及支援的 collocation。</span><span class="sxs-lookup"><span data-stu-id="5ec73-105">This section details the hardware and software requirements for these servers, along with the supported collocation.</span></span>

<span data-ttu-id="5ec73-106">電話撥入式會議是包含各種元件的功能。</span><span class="sxs-lookup"><span data-stu-id="5ec73-106">Dial-in conferencing is a feature that includes a variety of components.</span></span> <span data-ttu-id="5ec73-107">某些元件是與電話撥入式會議相關的，而有些則是企業語音元件。</span><span class="sxs-lookup"><span data-stu-id="5ec73-107">Some of the components are specific to dial-in conferencing and some are Enterprise Voice components.</span></span> <span data-ttu-id="5ec73-108">本節說明特定于電話撥入式會議的元件需求。</span><span class="sxs-lookup"><span data-stu-id="5ec73-108">This section describes the requirements for the components that are specific to dial-in conferencing.</span></span> <span data-ttu-id="5ec73-109">如需有關中繼伺服器與公用交換電話網絡（PSTN）閘道需求的詳細資料，請參閱規劃檔中的 lync server 2013 中的[中繼伺服器元件](lync-server-2013-mediation-server-component.md)和 lync server 2013 中的發佈伺服器的[元件與拓撲](lync-server-2013-components-and-topologies-for-mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="5ec73-109">For details about Mediation Server and public switched telephone network (PSTN) gateway requirements, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) and [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="5ec73-110">硬體需求</span><span class="sxs-lookup"><span data-stu-id="5ec73-110">Hardware Requirements</span></span>

<span data-ttu-id="5ec73-111">因為 web 會議和 A/V 會議是與前端伺服器 collocated，所以伺服器的硬體需求與前端伺服器的需求相同。</span><span class="sxs-lookup"><span data-stu-id="5ec73-111">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server hardware requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="5ec73-112">如需硬體需求的詳細資訊，請參閱支援檔中的[Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)。</span><span class="sxs-lookup"><span data-stu-id="5ec73-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="5ec73-113">下列是電話撥入式會議所需的元件，也會有與前端伺服器相同的硬體需求：</span><span class="sxs-lookup"><span data-stu-id="5ec73-113">The following components required for dial-in conferencing also have the same hardware requirements as Front End Servers:</span></span>

  - <span data-ttu-id="5ec73-114">應用程式服務</span><span class="sxs-lookup"><span data-stu-id="5ec73-114">Application service</span></span>

  - <span data-ttu-id="5ec73-115">會議助理應用程式</span><span class="sxs-lookup"><span data-stu-id="5ec73-115">Conferencing Attendant application</span></span>

  - <span data-ttu-id="5ec73-116">會議公告應用程式</span><span class="sxs-lookup"><span data-stu-id="5ec73-116">Conferencing Announcement application</span></span>

<span data-ttu-id="5ec73-117">前端伺服器的硬體需求與 Lync Server 2013 中的許多其他伺服器角色相同，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="5ec73-117">The hardware requirements for Front End Server are the same as for many other server roles in Lync Server 2013 are outlined in the following table.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="5ec73-118">軟體需求</span><span class="sxs-lookup"><span data-stu-id="5ec73-118">Software Requirements</span></span>

<span data-ttu-id="5ec73-119">因為 web 會議和 A/V 會議是與前端伺服器 collocated，所以伺服器軟體需求與前端伺服器的需求相同。</span><span class="sxs-lookup"><span data-stu-id="5ec73-119">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server software requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="5ec73-120">如需軟體需求的詳細資訊，請參閱支援檔中的[Lync server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)。</span><span class="sxs-lookup"><span data-stu-id="5ec73-120">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="5ec73-121">針對網路會議，Lync Server 2013 也需要 Office Web Apps 和 Office Web Apps 伺服器（先前稱為 WAC 伺服器）來處理 PowerPoint 簡報。</span><span class="sxs-lookup"><span data-stu-id="5ec73-121">For web conferencing, Lync Server 2013 also requires Office Web Apps and the Office Web Apps Server (formerly known as WAC Server) to handle PowerPoint presentations.</span></span> <span data-ttu-id="5ec73-122">如需詳細資訊，請參閱設定[與 Office Web Apps server 和 Lync server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="5ec73-122">For details, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="5ec73-123">如果是電話撥入式會議、應用程式服務、會議助理應用程式及會議公告應用程式，與前端伺服器的作業系統需求相同。</span><span class="sxs-lookup"><span data-stu-id="5ec73-123">For dial-in conferencing, Application service, Conferencing Attendant application, and Conferencing Announcement application have the same operating system requirements as Front End Servers.</span></span> <span data-ttu-id="5ec73-124">如需軟體需求的詳細資訊，請參閱支援檔中的[Lync server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)。</span><span class="sxs-lookup"><span data-stu-id="5ec73-124">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="5ec73-125">會議助理應用程式與會議公告應用程式要求 Windows Media 格式執行時間已安裝在前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="5ec73-125">Conferencing Attendant application and Conferencing Announcement application require that Windows Media Format Runtime is installed on Front End Servers.</span></span> <span data-ttu-id="5ec73-126">Windows Media 格式執行時間需要播放 Windows Media 音訊（WMA）檔案，這些檔案是用來等候音樂、錄製的名稱和提示。</span><span class="sxs-lookup"><span data-stu-id="5ec73-126">The Windows Media Format Runtime is required to play Windows Media audio (WMA) files that are used for music on hold, recorded names, and prompts.</span></span> <span data-ttu-id="5ec73-127">除了 Windows Server 2012 和 Windows Server 2012 R2 之外，當您執行安裝程式時，Windows Media 格式執行時間會自動安裝為 Windows 桌面體驗的一部分，但您可能需要重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="5ec73-127">Except for Windows Server 2012 and Windows Server 2012 R2, the Windows Media Format Runtime is installed automatically as part of the Windows Desktop Experience when you run Setup, but you might need to restart the computer.</span></span> <span data-ttu-id="5ec73-128">因此，建議您在 Windows 桌面體驗中安裝，包括 Windows 媒體格式執行時間，然後再執行安裝程式。</span><span class="sxs-lookup"><span data-stu-id="5ec73-128">Therefore, we recommend that you install as part of the Windows Desktop Experience, which includes Windows Media Format Runtime before you run Setup.</span></span> <span data-ttu-id="5ec73-129">Windows Server 2012 和 Windows Server 2012 R2 需要 Microsoft 媒體基礎。</span><span class="sxs-lookup"><span data-stu-id="5ec73-129">Windows Server 2012 and Windows Server 2012 R2 requires Microsoft Media Foundation.</span></span>

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a><span data-ttu-id="5ec73-130">電話撥入式會議的埠需求</span><span class="sxs-lookup"><span data-stu-id="5ec73-130">Port Requirements for dial-in conferencing</span></span>

<span data-ttu-id="5ec73-131">下表說明電話撥入式會議所使用的埠。</span><span class="sxs-lookup"><span data-stu-id="5ec73-131">The following table describes the ports that are used by dial-in conferencing.</span></span> <span data-ttu-id="5ec73-132">如果您使用負載平衡器，請確定已針對將在池中執行的任何應用程式所使用的埠設定負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="5ec73-132">If you use a load balancer, ensure that the load balancer is configured for the ports used by any applications that will run in the pool.</span></span>

<span data-ttu-id="5ec73-133">這些埠是預設的設定，您可以使用**CsApplicationServer** Cmdlet 變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="5ec73-133">These ports are default settings that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="5ec73-134">如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="5ec73-134">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5ec73-135">池中相同應用程式的所有實例都使用相同的 SIP 偵聽埠。</span><span class="sxs-lookup"><span data-stu-id="5ec73-135">All instances of the same application in a pool use the same SIP listening port.</span></span>



</div>

### <a name="ports-used-by-dial-in-conferencing"></a><span data-ttu-id="5ec73-136">電話撥入式會議所用的埠</span><span class="sxs-lookup"><span data-stu-id="5ec73-136">Ports used by dial-in conferencing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ec73-137">埠號碼</span><span class="sxs-lookup"><span data-stu-id="5ec73-137">Port number</span></span></th>
<th><span data-ttu-id="5ec73-138">說明</span><span class="sxs-lookup"><span data-stu-id="5ec73-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ec73-139">5072</span><span class="sxs-lookup"><span data-stu-id="5ec73-139">5072</span></span></p></td>
<td><p><span data-ttu-id="5ec73-140">由會議助理應用程式用於 SIP 偵聽要求</span><span class="sxs-lookup"><span data-stu-id="5ec73-140">Used by Conferencing Attendant application for SIP listening requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ec73-141">5073</span><span class="sxs-lookup"><span data-stu-id="5ec73-141">5073</span></span></p></td>
<td><p><span data-ttu-id="5ec73-142">由會議公告應用程式用於 SIP 偵聽要求</span><span class="sxs-lookup"><span data-stu-id="5ec73-142">Used by Conferencing Announcement application for SIP listening requests</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a><span data-ttu-id="5ec73-143">電話撥入式會議支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="5ec73-143">Supported Clients for Dial-In Conferencing</span></span>

<span data-ttu-id="5ec73-144">您可以使用下列用戶端來排程支援撥入存取的內部部署會議：</span><span class="sxs-lookup"><span data-stu-id="5ec73-144">You can use the following client to schedule on-premises conferences that support dial-in access:</span></span>

  - <span data-ttu-id="5ec73-145">Lync 2013 的線上會議增益集（安裝 Lync 2013 或出席者時會自動安裝）</span><span class="sxs-lookup"><span data-stu-id="5ec73-145">Online Meeting Add-in for Lync 2013 (installed automatically when you install Lync 2013 or Attendee)</span></span>

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a><span data-ttu-id="5ec73-146">電話撥入式會議設定頁面需求</span><span class="sxs-lookup"><span data-stu-id="5ec73-146">Dial-in Conferencing Settings page Requirements</span></span>

<span data-ttu-id="5ec73-147">[電話撥入式會議設定] 頁面支援下表所述的作業系統與網頁瀏覽器混合。</span><span class="sxs-lookup"><span data-stu-id="5ec73-147">The Dial-in Conferencing Settings page supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5ec73-148">支援32位及64位版本的作業系統。</span><span class="sxs-lookup"><span data-stu-id="5ec73-148">32-bit and 64-bit versions of the operating systems are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="5ec73-149">支援的作業系統與網頁瀏覽器</span><span class="sxs-lookup"><span data-stu-id="5ec73-149">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ec73-150">作業系統</span><span class="sxs-lookup"><span data-stu-id="5ec73-150">Operating system</span></span></th>
<th><span data-ttu-id="5ec73-151">網頁瀏覽器</span><span class="sxs-lookup"><span data-stu-id="5ec73-151">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ec73-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="5ec73-152">Windows 7</span></span></p></td>
<td><p><span data-ttu-id="5ec73-153">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="5ec73-153">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="5ec73-154">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="5ec73-154">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="5ec73-155">Firefox</span><span class="sxs-lookup"><span data-stu-id="5ec73-155">Firefox</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ec73-156">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="5ec73-156">Windows Server 2008 R2</span></span></p></td>
<td><p><span data-ttu-id="5ec73-157">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="5ec73-157">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="5ec73-158">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="5ec73-158">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="5ec73-159">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="5ec73-159">Internet Explorer 7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ec73-160">Mac OS</span><span class="sxs-lookup"><span data-stu-id="5ec73-160">Mac OS</span></span></p></td>
<td><p><span data-ttu-id="5ec73-161">Firefox</span><span class="sxs-lookup"><span data-stu-id="5ec73-161">Firefox</span></span></p>
<p><span data-ttu-id="5ec73-162">Safari</span><span class="sxs-lookup"><span data-stu-id="5ec73-162">Safari</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a><span data-ttu-id="5ec73-163">電話撥入式會議的音訊檔需求</span><span class="sxs-lookup"><span data-stu-id="5ec73-163">Audio File Requirements for dial-in conferencing</span></span>

<span data-ttu-id="5ec73-164">Lync Server 2013 不支援自訂語音提示和電話撥入式會議的音樂。</span><span class="sxs-lookup"><span data-stu-id="5ec73-164">Lync Server 2013 does not support customization of voice prompts and music for dial-in conferencing.</span></span> <span data-ttu-id="5ec73-165">不過，如果您需要變更預設音訊檔案，請參閱 Microsoft 知識庫文章961177，[說明如何在 Microsoft Office 通訊伺服器 2007 R2 中自訂語音提示或音樂檔案，以進行電話撥入式音訊會議](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177)。</span><span class="sxs-lookup"><span data-stu-id="5ec73-165">However, if you have a strong business need that requires you to change the default audio files, see Microsoft Knowledge Base article 961177, [How to customize voice prompts or music files for dial-in audio conferencing in Microsoft Office Communications Server 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span></span>

<span data-ttu-id="5ec73-166">您也可以使用[Microsoft Lync Server 會議助理自訂語音提示](http://go.microsoft.com/fwlink/p/?linkid=396880)管理實用程式，當電話來電者加入 Lync 會議時，系統會使用自訂提示來取代預設語音提示，以提供不同的會議進入體驗。</span><span class="sxs-lookup"><span data-stu-id="5ec73-166">You can also use the [Microsoft Lync Server Conferencing Attendant Custom Voice Prompts](http://go.microsoft.com/fwlink/p/?linkid=396880) management utility, which enables administrators to replace the default voice prompts used when a phone caller joins a Lync meeting with custom prompts to provide a different meeting entry experience.</span></span> <span data-ttu-id="5ec73-167">您可以在執行 Lync Server 2010 或 Lync Server 2013 （企業版或標準版）的伺服器上安裝自訂語音提示。</span><span class="sxs-lookup"><span data-stu-id="5ec73-167">The custom voice prompts can be installed on a server that is running Lync Server 2010 or Lync Server 2013, either Enterprise or Standard Edition.</span></span>

<span data-ttu-id="5ec73-168">會議助理應用程式與會議公告應用程式對於保留的音樂、錄製的名稱及音訊提示檔案有下列需求：</span><span class="sxs-lookup"><span data-stu-id="5ec73-168">Conferencing Attendant application and Conferencing Announcement application have the following requirements for music on hold, recorded name, and audio prompt files:</span></span>

  - <span data-ttu-id="5ec73-169">Windows Media 音訊（WMA）檔案格式</span><span class="sxs-lookup"><span data-stu-id="5ec73-169">Windows Media Audio (WMA) file format</span></span>

  - <span data-ttu-id="5ec73-170">16位 mono</span><span class="sxs-lookup"><span data-stu-id="5ec73-170">16-bit mono</span></span>

  - <span data-ttu-id="5ec73-171">48 kbps 2-pass CBR （恒定傳輸率）</span><span class="sxs-lookup"><span data-stu-id="5ec73-171">48 kbps 2-pass CBR (constant bit rate)</span></span>

  - <span data-ttu-id="5ec73-172">24DB 的語音層級</span><span class="sxs-lookup"><span data-stu-id="5ec73-172">Speech level at -24DB</span></span>

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a><span data-ttu-id="5ec73-173">電話撥入式會議的使用者需求</span><span class="sxs-lookup"><span data-stu-id="5ec73-173">User Requirements for Dial-In Conferencing</span></span>

<span data-ttu-id="5ec73-174">電話撥入式會議使用者必須有指派給其帳戶的唯一電話號碼或副檔名。</span><span class="sxs-lookup"><span data-stu-id="5ec73-174">Dial-in conferencing users must have a unique phone number or extension assigned to their account.</span></span> <span data-ttu-id="5ec73-175">此需求支援在電話撥入式會議期間進行驗證。</span><span class="sxs-lookup"><span data-stu-id="5ec73-175">This requirement supports authentication during dial-in conferencing.</span></span> <span data-ttu-id="5ec73-176">企業使用者（也就是在貴組織內擁有 Active Directory 網域服務認證和 Lync Server 帳戶的使用者）輸入他們的電話號碼（或分機），以及使用個人識別碼（PIN）撥入會議作為已驗證使用者。</span><span class="sxs-lookup"><span data-stu-id="5ec73-176">Enterprise users (that is, users who have Active Directory Domain Services credentials and Lync Server accounts within your organization) enter their phone number (or extension) and a personal identification number (PIN) to dial in to conferences as an authenticated user.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


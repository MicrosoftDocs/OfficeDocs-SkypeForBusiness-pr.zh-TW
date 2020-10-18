---
title: Lync Server 2013 會議的技術需求
description: Lync Server 2013 會議的技術需求。
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
ms.openlocfilehash: 0b3b787d84288d789cd0d824081439004f19327e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577119"
---
# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="ddc8c-103">Lync Server 2013 中的會議技術需求</span><span class="sxs-lookup"><span data-stu-id="ddc8c-103">Technical requirements for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ddc8c-104">_**主題上次修改日期：** 2014-06-25_</span><span class="sxs-lookup"><span data-stu-id="ddc8c-104">_**Topic Last Modified:** 2014-06-25_</span></span>

<span data-ttu-id="ddc8c-105">針對 Lync Server 2013，電話撥入式會議、A/V 會議、立即訊息 (IM) 會議和 web 會議功能一定會在前端伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-105">For Lync Server 2013, dial-in conferencing, A/V conferencing, instant messaging (IM) conferencing and web conferencing capabilities always run on Front End Servers.</span></span>

<span data-ttu-id="ddc8c-106">本節將詳細說明這些伺服器的硬體和軟體需求，以及支援的組合。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-106">This section details the hardware and software requirements for these servers, along with the supported collocation.</span></span>

<span data-ttu-id="ddc8c-107">電話撥入式會議是一項包含許多不同元件的功能。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-107">Dial-in conferencing is a feature that includes a variety of components.</span></span> <span data-ttu-id="ddc8c-108">有些元件是電話撥入式會議所特有的，有些則是企業語音元件。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-108">Some of the components are specific to dial-in conferencing and some are Enterprise Voice components.</span></span> <span data-ttu-id="ddc8c-109">本節說明電話撥入式會議專用元件的需求。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-109">This section describes the requirements for the components that are specific to dial-in conferencing.</span></span> <span data-ttu-id="ddc8c-110">如需有關轉送伺服器和公用交換電話網路 (PSTN) 閘道需求的詳細資訊，請參閱規劃檔中的 [lync server 2013](lync-server-2013-mediation-server-component.md) 和中繼 [2013 伺服器的元件和拓撲](lync-server-2013-components-and-topologies-for-mediation-server.md) 中的轉送伺服器元件。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-110">For details about Mediation Server and public switched telephone network (PSTN) gateway requirements, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) and [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="ddc8c-111">硬體需求</span><span class="sxs-lookup"><span data-stu-id="ddc8c-111">Hardware Requirements</span></span>

<span data-ttu-id="ddc8c-112">因為 web 會議和 A/V 會議會與前端伺服器組合，所以伺服器的硬體需求與前端伺服器的需求相同。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-112">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server hardware requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="ddc8c-113">如需硬體需求的詳細資訊，請參閱支援檔中的 [Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md) 。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-113">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="ddc8c-114">電話撥入式會議所需的下列元件也具有與前端伺服器相同的硬體需求：</span><span class="sxs-lookup"><span data-stu-id="ddc8c-114">The following components required for dial-in conferencing also have the same hardware requirements as Front End Servers:</span></span>

  - <span data-ttu-id="ddc8c-115">應用程式服務</span><span class="sxs-lookup"><span data-stu-id="ddc8c-115">Application service</span></span>

  - <span data-ttu-id="ddc8c-116">Conferencing Attendant application</span><span class="sxs-lookup"><span data-stu-id="ddc8c-116">Conferencing Attendant application</span></span>

  - <span data-ttu-id="ddc8c-117">Conferencing Announcement application</span><span class="sxs-lookup"><span data-stu-id="ddc8c-117">Conferencing Announcement application</span></span>

<span data-ttu-id="ddc8c-118">前端伺服器的硬體需求與 Lync Server 2013 中的許多其他伺服器角色相同，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-118">The hardware requirements for Front End Server are the same as for many other server roles in Lync Server 2013 are outlined in the following table.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="ddc8c-119">軟體需求</span><span class="sxs-lookup"><span data-stu-id="ddc8c-119">Software Requirements</span></span>

<span data-ttu-id="ddc8c-120">因為 web 會議和 A/V 會議會與前端伺服器組合，所以伺服器軟體需求與前端伺服器的需求相同。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-120">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server software requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="ddc8c-121">如需軟體需求的詳細資訊，請參閱支援檔中的 [伺服器和工具作業系統支援（Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) ）。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-121">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="ddc8c-122">若為 web 會議，Lync Server 2013 也需要 Office Web Apps 和 Office Web Apps Server (（以前稱為 WAC Server) ）來處理 PowerPoint 簡報。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-122">For web conferencing, Lync Server 2013 also requires Office Web Apps and the Office Web Apps Server (formerly known as WAC Server) to handle PowerPoint presentations.</span></span> <span data-ttu-id="ddc8c-123">如需詳細資訊，請參閱設定 [Office Web Apps Server 和 Lync Server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-123">For details, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="ddc8c-124">在電話撥入式會議中，應用程式服務、會議應答應用程式和會議宣告應用程式與前端伺服器具有相同的作業系統需求。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-124">For dial-in conferencing, Application service, Conferencing Attendant application, and Conferencing Announcement application have the same operating system requirements as Front End Servers.</span></span> <span data-ttu-id="ddc8c-125">如需軟體需求的詳細資訊，請參閱支援檔中的 [伺服器和工具作業系統支援（Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) ）。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-125">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="ddc8c-126">會議應答應用程式和會議宣告應用程式需要 Windows Media Format Runtime 安裝在前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-126">Conferencing Attendant application and Conferencing Announcement application require that Windows Media Format Runtime is installed on Front End Servers.</span></span> <span data-ttu-id="ddc8c-127">您必須有 Windows Media Format Runtime 才能播放等候音樂、錄音名稱和提示所使用的 Windows Media Audio (WMA) 檔。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-127">The Windows Media Format Runtime is required to play Windows Media audio (WMA) files that are used for music on hold, recorded names, and prompts.</span></span> <span data-ttu-id="ddc8c-128">除了 Windows Server 2012 和 Windows Server 2012 R2 之外，Windows Media Format Runtime 會在您執行安裝程式時自動安裝為 Windows 桌面體驗的一部分，但您可能需要重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-128">Except for Windows Server 2012 and Windows Server 2012 R2, the Windows Media Format Runtime is installed automatically as part of the Windows Desktop Experience when you run Setup, but you might need to restart the computer.</span></span> <span data-ttu-id="ddc8c-129">因此建議您以 Windows Desktop Experience 的一部分安裝，其中包括 Windows Media Format Runtime。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-129">Therefore, we recommend that you install as part of the Windows Desktop Experience, which includes Windows Media Format Runtime before you run Setup.</span></span> <span data-ttu-id="ddc8c-130">Windows Server 2012 和 Windows Server 2012 R2 需要 Microsoft Media Foundation。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-130">Windows Server 2012 and Windows Server 2012 R2 requires Microsoft Media Foundation.</span></span>

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a><span data-ttu-id="ddc8c-131">電話撥入式會議的連接埠需求</span><span class="sxs-lookup"><span data-stu-id="ddc8c-131">Port Requirements for dial-in conferencing</span></span>

<span data-ttu-id="ddc8c-p107">下表描述電話撥入式會議所使用的連接埠。如果您使用負載平衡器，務必針對將在集區中執行的任何應用程式所使用的連接埠設定負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-p107">The following table describes the ports that are used by dial-in conferencing. If you use a load balancer, ensure that the load balancer is configured for the ports used by any applications that will run in the pool.</span></span>

<span data-ttu-id="ddc8c-134">這些連接埠為預設設定，可使用 **Set-CsApplicationServer** Cmdlet 予以變更。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-134">These ports are default settings that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="ddc8c-135">如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-135">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ddc8c-136">集區中同一個應用程式的所有執行個體都使用相同的 SIP 聆聽連接埠。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-136">All instances of the same application in a pool use the same SIP listening port.</span></span>



</div>

### <a name="ports-used-by-dial-in-conferencing"></a><span data-ttu-id="ddc8c-137">電話撥入式會議使用的連接埠</span><span class="sxs-lookup"><span data-stu-id="ddc8c-137">Ports used by dial-in conferencing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ddc8c-138">連接埠編號</span><span class="sxs-lookup"><span data-stu-id="ddc8c-138">Port number</span></span></th>
<th><span data-ttu-id="ddc8c-139">描述</span><span class="sxs-lookup"><span data-stu-id="ddc8c-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ddc8c-140">5072</span><span class="sxs-lookup"><span data-stu-id="ddc8c-140">5072</span></span></p></td>
<td><p><span data-ttu-id="ddc8c-141">用於 SIP 聆聽要求的會議值守應用程式</span><span class="sxs-lookup"><span data-stu-id="ddc8c-141">Used by Conferencing Attendant application for SIP listening requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddc8c-142">5073</span><span class="sxs-lookup"><span data-stu-id="ddc8c-142">5073</span></span></p></td>
<td><p><span data-ttu-id="ddc8c-143">供會議宣告應用程式用於 SIP 聆聽要求</span><span class="sxs-lookup"><span data-stu-id="ddc8c-143">Used by Conferencing Announcement application for SIP listening requests</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a><span data-ttu-id="ddc8c-144">支援的電話撥入式會議用戶端</span><span class="sxs-lookup"><span data-stu-id="ddc8c-144">Supported Clients for Dial-In Conferencing</span></span>

<span data-ttu-id="ddc8c-145">您可以使用下列用戶端，排程支援電話撥入式存取的內部部署會議：</span><span class="sxs-lookup"><span data-stu-id="ddc8c-145">You can use the following client to schedule on-premises conferences that support dial-in access:</span></span>

  - <span data-ttu-id="ddc8c-146">當您安裝 Lync 2013 或出席者時，會自動安裝 Lync 2013 (的線上會議增益集) </span><span class="sxs-lookup"><span data-stu-id="ddc8c-146">Online Meeting Add-in for Lync 2013 (installed automatically when you install Lync 2013 or Attendee)</span></span>

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a><span data-ttu-id="ddc8c-147">電話撥入式會議設定頁面需求</span><span class="sxs-lookup"><span data-stu-id="ddc8c-147">Dial-in Conferencing Settings page Requirements</span></span>

<span data-ttu-id="ddc8c-148">[電話撥入式會議設定] 頁面支援下表所述之作業系統和網頁瀏覽器的組合。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-148">The Dial-in Conferencing Settings page supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ddc8c-149">支援 32 位元和 64 位元版本的作業系統。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-149">32-bit and 64-bit versions of the operating systems are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="ddc8c-150">支援的作業系統和網頁瀏覽器</span><span class="sxs-lookup"><span data-stu-id="ddc8c-150">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ddc8c-151">作業系統</span><span class="sxs-lookup"><span data-stu-id="ddc8c-151">Operating system</span></span></th>
<th><span data-ttu-id="ddc8c-152">網頁瀏覽器</span><span class="sxs-lookup"><span data-stu-id="ddc8c-152">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ddc8c-153">Windows 7</span><span class="sxs-lookup"><span data-stu-id="ddc8c-153">Windows 7</span></span></p></td>
<td><p><span data-ttu-id="ddc8c-154">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="ddc8c-154">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="ddc8c-155">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="ddc8c-155">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="ddc8c-156">Firefox</span><span class="sxs-lookup"><span data-stu-id="ddc8c-156">Firefox</span></span></p></td>
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
<td><p><span data-ttu-id="ddc8c-157">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="ddc8c-157">Windows Server 2008 R2</span></span></p></td>
<td><p><span data-ttu-id="ddc8c-158">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="ddc8c-158">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="ddc8c-159">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="ddc8c-159">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="ddc8c-160">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="ddc8c-160">Internet Explorer 7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ddc8c-161">Mac 作業系統</span><span class="sxs-lookup"><span data-stu-id="ddc8c-161">Mac OS</span></span></p></td>
<td><p><span data-ttu-id="ddc8c-162">Firefox</span><span class="sxs-lookup"><span data-stu-id="ddc8c-162">Firefox</span></span></p>
<p><span data-ttu-id="ddc8c-163">Safari</span><span class="sxs-lookup"><span data-stu-id="ddc8c-163">Safari</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a><span data-ttu-id="ddc8c-164">電話撥入式會議的音訊檔需求</span><span class="sxs-lookup"><span data-stu-id="ddc8c-164">Audio File Requirements for dial-in conferencing</span></span>

<span data-ttu-id="ddc8c-165">Lync Server 2013 不支援自訂語音提示和音樂的電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-165">Lync Server 2013 does not support customization of voice prompts and music for dial-in conferencing.</span></span> <span data-ttu-id="ddc8c-166">不過，如果您有需要變更預設音訊檔的強有力的商務需求，請參閱 Microsoft 知識庫文章961177： [如何在 Microsoft Office 通訊伺服器 2007 R2 中自訂語音提示或音樂檔，以進行電話撥入音訊會議](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177)。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-166">However, if you have a strong business need that requires you to change the default audio files, see Microsoft Knowledge Base article 961177, [How to customize voice prompts or music files for dial-in audio conferencing in Microsoft Office Communications Server 2007 R2](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span></span>

<span data-ttu-id="ddc8c-167">您也可以使用 [Microsoft Lync Server 會議助理自訂語音提示](https://go.microsoft.com/fwlink/p/?linkid=396880) 管理公用程式，讓系統管理員可以取代當電話來電者加入具有自訂提示的 Lync 會議以提供不同會議輸入經驗時所使用的預設語音提示。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-167">You can also use the [Microsoft Lync Server Conferencing Attendant Custom Voice Prompts](https://go.microsoft.com/fwlink/p/?linkid=396880) management utility, which enables administrators to replace the default voice prompts used when a phone caller joins a Lync meeting with custom prompts to provide a different meeting entry experience.</span></span> <span data-ttu-id="ddc8c-168">自訂語音提示可以安裝在執行 Lync Server 2010 或 Lync Server 2013 （Enterprise 或 Standard Edition）的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-168">The custom voice prompts can be installed on a server that is running Lync Server 2010 or Lync Server 2013, either Enterprise or Standard Edition.</span></span>

<span data-ttu-id="ddc8c-169">會議應答應用程式和會議宣告應用程式對於等候音樂、錄製名稱和音訊提示檔有下列需求：</span><span class="sxs-lookup"><span data-stu-id="ddc8c-169">Conferencing Attendant application and Conferencing Announcement application have the following requirements for music on hold, recorded name, and audio prompt files:</span></span>

  - <span data-ttu-id="ddc8c-170">Windows Media Audio (WMA) 檔案格式</span><span class="sxs-lookup"><span data-stu-id="ddc8c-170">Windows Media Audio (WMA) file format</span></span>

  - <span data-ttu-id="ddc8c-171">16 位元單聲道</span><span class="sxs-lookup"><span data-stu-id="ddc8c-171">16-bit mono</span></span>

  - <span data-ttu-id="ddc8c-172">48 kbps 2-pass CBR (常數位元速率)</span><span class="sxs-lookup"><span data-stu-id="ddc8c-172">48 kbps 2-pass CBR (constant bit rate)</span></span>

  - <span data-ttu-id="ddc8c-173">語音層級為 -24DB</span><span class="sxs-lookup"><span data-stu-id="ddc8c-173">Speech level at -24DB</span></span>

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a><span data-ttu-id="ddc8c-174">電話撥入式會議的使用者需求</span><span class="sxs-lookup"><span data-stu-id="ddc8c-174">User Requirements for Dial-In Conferencing</span></span>

<span data-ttu-id="ddc8c-175">必須指派唯一的電話號碼或分機至電話撥入式會議使用者的帳戶。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-175">Dial-in conferencing users must have a unique phone number or extension assigned to their account.</span></span> <span data-ttu-id="ddc8c-176">此需求可支援電話撥入式會議期間的驗證。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-176">This requirement supports authentication during dial-in conferencing.</span></span> <span data-ttu-id="ddc8c-177">企業使用者 (，也就是在組織內具有 Active Directory 網域服務認證和 Lync Server 帳戶的使用者) 輸入他們的電話號碼 (或分機) ，以及個人識別碼 (PIN) ，以驗證的使用者的身分撥打會議。</span><span class="sxs-lookup"><span data-stu-id="ddc8c-177">Enterprise users (that is, users who have Active Directory Domain Services credentials and Lync Server accounts within your organization) enter their phone number (or extension) and a personal identification number (PIN) to dial in to conferences as an authenticated user.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


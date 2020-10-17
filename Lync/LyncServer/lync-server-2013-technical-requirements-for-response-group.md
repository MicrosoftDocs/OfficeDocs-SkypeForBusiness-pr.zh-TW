---
title: Lync Server 2013：回應群組的技術需求
description: Lync Server 2013：回應群組的技術需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3125ed8c732960e23970229e99bf5a8487eb96a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550319"
---
# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a><span data-ttu-id="8d053-103">Lync Server 2013 中回應群組的技術需求</span><span class="sxs-lookup"><span data-stu-id="8d053-103">Technical requirements for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d053-104">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="8d053-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="8d053-105">本節說明回應群組應用程式的下列技術需求：</span><span class="sxs-lookup"><span data-stu-id="8d053-105">This section describes the following technical requirements for the Response Group application:</span></span>

  - <span data-ttu-id="8d053-106">硬體需求</span><span class="sxs-lookup"><span data-stu-id="8d053-106">Hardware requirements</span></span>

  - <span data-ttu-id="8d053-107">軟體需求</span><span class="sxs-lookup"><span data-stu-id="8d053-107">Software requirements</span></span>

  - <span data-ttu-id="8d053-108">連接埠需求</span><span class="sxs-lookup"><span data-stu-id="8d053-108">Port requirements</span></span>

  - <span data-ttu-id="8d053-109">音訊檔案需求</span><span class="sxs-lookup"><span data-stu-id="8d053-109">Audio file requirements</span></span>

  - <span data-ttu-id="8d053-110">回應群組設定工具需求</span><span class="sxs-lookup"><span data-stu-id="8d053-110">Response Group configuration tool requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="8d053-111">硬體需求</span><span class="sxs-lookup"><span data-stu-id="8d053-111">Hardware Requirements</span></span>

<span data-ttu-id="8d053-112">回應群組應用程式的硬體需求與前端伺服器相同。</span><span class="sxs-lookup"><span data-stu-id="8d053-112">The Response Group application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="8d053-113">如需硬體需求的詳細資訊，請參閱支援檔中的 [Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md) 。</span><span class="sxs-lookup"><span data-stu-id="8d053-113">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="8d053-114">軟體需求</span><span class="sxs-lookup"><span data-stu-id="8d053-114">Software Requirements</span></span>

<span data-ttu-id="8d053-115">回應群組應用程式與前端伺服器具有相同的作業系統需求和軟體必要條件。</span><span class="sxs-lookup"><span data-stu-id="8d053-115">The Response Group application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="8d053-116">如需軟體需求的詳細資訊，請參閱支援檔中的 [伺服器和工具作業系統支援（Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) ）。</span><span class="sxs-lookup"><span data-stu-id="8d053-116">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="8d053-117">如果您使用 Windows Media Audio () 的回應群組音樂和宣告的檔案，所有執行回應群組應用程式的前端伺服器或 Standard Edition 伺服器，都必須針對執行 windows server 2008 R2 的伺服器及 Microsoft Media Foundation （執行 Windows Server 2012 或 Windows Server 2012 R2 的伺服器）安裝 Windows Media Format Runtime。</span><span class="sxs-lookup"><span data-stu-id="8d053-117">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="8d053-118">若為 Windows Server 2008 R2，Windows Media Format Runtime 會安裝為 Windows 桌面體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="8d053-118">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="8d053-119">如需有關音訊需求的詳細資訊，請參閱本節稍後的＜音訊檔案需求＞。</span><span class="sxs-lookup"><span data-stu-id="8d053-119">For more details about audio requirements, see "Audio File Requirements" later in this section.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="8d053-120">連接埠需求</span><span class="sxs-lookup"><span data-stu-id="8d053-120">Port Requirements</span></span>

<span data-ttu-id="8d053-121">回應群組應用程式使用下列埠：</span><span class="sxs-lookup"><span data-stu-id="8d053-121">The Response Group application uses the following ports:</span></span>

  - <span data-ttu-id="8d053-122">**埠 5071**    用於 SIP 聆聽要求</span><span class="sxs-lookup"><span data-stu-id="8d053-122">**Port 5071**   Used for SIP listening requests</span></span>

  - <span data-ttu-id="8d053-123">**埠 8404**    用於伺服器間通訊</span><span class="sxs-lookup"><span data-stu-id="8d053-123">**Port 8404**   Used for interserver communications</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8d053-124">此埠用於配對服務，且在具有多部前端伺服器的集區中部署回應群組應用程式時是必要的。</span><span class="sxs-lookup"><span data-stu-id="8d053-124">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="8d053-125">這些連接埠為預設設定，可使用 <STRONG>Set-CsApplicationServer</STRONG> Cmdlet 予以變更。</span><span class="sxs-lookup"><span data-stu-id="8d053-125">These ports are default settings that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="8d053-126">如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="8d053-126">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="8d053-127">音訊檔案需求</span><span class="sxs-lookup"><span data-stu-id="8d053-127">Audio File Requirements</span></span>

<span data-ttu-id="8d053-128">回應群組應用程式支援波形 ( wav) 檔案格式和 Windows Media 音訊 ( 回應群組訊息、等候音樂或互動語音回應的檔案格式) 。 (IVR) 問題。</span><span class="sxs-lookup"><span data-stu-id="8d053-128">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="8d053-129">Windows Media 音訊檔案格式要求 Windows Media Format Runtime 已安裝在執行 Windows Server 2008 R2 和 Windows Server 2008 的前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="8d053-129">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="8d053-130">如需詳細資訊，請參閱本節稍早的＜軟體需求＞。</span><span class="sxs-lookup"><span data-stu-id="8d053-130">For more details, see "Software Requirements" earlier in this section.</span></span>

<div>

## <a name="supported-wave-file-formats"></a><span data-ttu-id="8d053-131">支援的 Wave 檔案格式</span><span class="sxs-lookup"><span data-stu-id="8d053-131">Supported Wave File Formats</span></span>

<span data-ttu-id="8d053-132">所有 Wave 檔案必須符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="8d053-132">All wave files must meet the following requirements:</span></span>

  - <span data-ttu-id="8d053-133">8 位元或 16 位元檔案</span><span class="sxs-lookup"><span data-stu-id="8d053-133">8-bit or 16-bit file</span></span>

  - <span data-ttu-id="8d053-134">線性脈衝代碼調變 (LPCM)，A-Law 或 mu-Law 格式</span><span class="sxs-lookup"><span data-stu-id="8d053-134">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

  - <span data-ttu-id="8d053-135">單音或立體聲</span><span class="sxs-lookup"><span data-stu-id="8d053-135">Mono or stereo</span></span>

  - <span data-ttu-id="8d053-136">4MB 以下</span><span class="sxs-lookup"><span data-stu-id="8d053-136">4MB or less</span></span>

<span data-ttu-id="8d053-137">為使 Wave 檔案有最佳表現，建議使用 16 kHz 單音的 16 位元 Wave 檔案。</span><span class="sxs-lookup"><span data-stu-id="8d053-137">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="8d053-138">支援的 Windows Media 音訊檔案格式</span><span class="sxs-lookup"><span data-stu-id="8d053-138">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="8d053-139">如果您使用 Windows Media 音訊檔案，請考慮使用低位元速率，並驗證系統承受負載時的效能。</span><span class="sxs-lookup"><span data-stu-id="8d053-139">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="8d053-140">您可以使用 Microsoft Expression Encoder 4 將檔案轉換成 Windows Media Audio 格式。</span><span class="sxs-lookup"><span data-stu-id="8d053-140">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="8d053-141">若要下載運算式編碼器4，請參閱 [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843) 。</span><span class="sxs-lookup"><span data-stu-id="8d053-141">To download Expression Encoder 4, see [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span></span>

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="8d053-142">回應群組設定工具需求</span><span class="sxs-lookup"><span data-stu-id="8d053-142">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="8d053-143">回應群組設定工具支援下表所述之作業系統和網頁瀏覽器的組合。</span><span class="sxs-lookup"><span data-stu-id="8d053-143">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8d053-p107">支援 32 位元或 64 位元版本的作業系統。只支援 32 位元版本的 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="8d053-p107">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="8d053-146">支援的作業系統和網頁瀏覽器</span><span class="sxs-lookup"><span data-stu-id="8d053-146">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d053-147">作業系統</span><span class="sxs-lookup"><span data-stu-id="8d053-147">Operating system</span></span></th>
<th><span data-ttu-id="8d053-148">網頁瀏覽器</span><span class="sxs-lookup"><span data-stu-id="8d053-148">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d053-149">Windows Vista Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="8d053-149">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="8d053-150">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="8d053-150">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="8d053-151">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="8d053-151">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="8d053-152">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="8d053-152">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d053-153">Windows 7</span><span class="sxs-lookup"><span data-stu-id="8d053-153">Windows 7</span></span></p>
<p><span data-ttu-id="8d053-154">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="8d053-154">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="8d053-155">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="8d053-155">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="8d053-156">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="8d053-156">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d053-157">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="8d053-157">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="8d053-158">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="8d053-158">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="8d053-159">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="8d053-159">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="8d053-160">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="8d053-160">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d053-161">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="8d053-161">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="8d053-162">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="8d053-162">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="8d053-163">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="8d053-163">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="8d053-164">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="8d053-164">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a><span data-ttu-id="8d053-165">回應群組代理程式主控台</span><span class="sxs-lookup"><span data-stu-id="8d053-165">Response Group Agent Console</span></span>

<span data-ttu-id="8d053-166">代理程式主控台支援下表中所述之作業系統和網頁瀏覽器的組合。</span><span class="sxs-lookup"><span data-stu-id="8d053-166">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8d053-p108">支援 32 位元或 64 位元版本的作業系統。只支援 32 位元版本的 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="8d053-p108">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="8d053-169">支援的作業系統和網頁瀏覽器</span><span class="sxs-lookup"><span data-stu-id="8d053-169">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d053-170">作業系統</span><span class="sxs-lookup"><span data-stu-id="8d053-170">Operating system</span></span></th>
<th><span data-ttu-id="8d053-171">網頁瀏覽器</span><span class="sxs-lookup"><span data-stu-id="8d053-171">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d053-172">Windows Vista Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="8d053-172">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="8d053-173">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="8d053-173">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="8d053-174">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="8d053-174">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="8d053-175">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="8d053-175">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d053-176">Windows 7</span><span class="sxs-lookup"><span data-stu-id="8d053-176">Windows 7</span></span></p>
<p><span data-ttu-id="8d053-177">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="8d053-177">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="8d053-178">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="8d053-178">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="8d053-179">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="8d053-179">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="8d053-180">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="8d053-180">Firefox 10.0</span></span></p>
<p><span data-ttu-id="8d053-181">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="8d053-181">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d053-182">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="8d053-182">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="8d053-183">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="8d053-183">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="8d053-184">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="8d053-184">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="8d053-185">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="8d053-185">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d053-186">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="8d053-186">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="8d053-187">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="8d053-187">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="8d053-188">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="8d053-188">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="8d053-189">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="8d053-189">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="8d053-190">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="8d053-190">Firefox 10.0</span></span></p>
<p><span data-ttu-id="8d053-191">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="8d053-191">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


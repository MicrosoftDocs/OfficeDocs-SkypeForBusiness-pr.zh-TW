---
title: Lync Server 2013：回應群組的技術需求
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
ms.openlocfilehash: b7ab381a70a8a6d69170959fbaf488982887d765
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a><span data-ttu-id="6c8bc-102">Lync Server 2013 中回應群組的技術需求</span><span class="sxs-lookup"><span data-stu-id="6c8bc-102">Technical requirements for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c8bc-103">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="6c8bc-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="6c8bc-104">本節說明回應群組應用程式的下列技術需求：</span><span class="sxs-lookup"><span data-stu-id="6c8bc-104">This section describes the following technical requirements for the Response Group application:</span></span>

  - <span data-ttu-id="6c8bc-105">硬體需求</span><span class="sxs-lookup"><span data-stu-id="6c8bc-105">Hardware requirements</span></span>

  - <span data-ttu-id="6c8bc-106">軟體需求</span><span class="sxs-lookup"><span data-stu-id="6c8bc-106">Software requirements</span></span>

  - <span data-ttu-id="6c8bc-107">埠需求</span><span class="sxs-lookup"><span data-stu-id="6c8bc-107">Port requirements</span></span>

  - <span data-ttu-id="6c8bc-108">音訊檔需求</span><span class="sxs-lookup"><span data-stu-id="6c8bc-108">Audio file requirements</span></span>

  - <span data-ttu-id="6c8bc-109">回應群組設定工具需求</span><span class="sxs-lookup"><span data-stu-id="6c8bc-109">Response Group configuration tool requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="6c8bc-110">硬體需求</span><span class="sxs-lookup"><span data-stu-id="6c8bc-110">Hardware Requirements</span></span>

<span data-ttu-id="6c8bc-111">回應群組應用程式具有與前端伺服器相同的硬體需求。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-111">The Response Group application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="6c8bc-112">如需硬體需求的詳細資訊，請參閱支援檔中的[Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="6c8bc-113">軟體需求</span><span class="sxs-lookup"><span data-stu-id="6c8bc-113">Software Requirements</span></span>

<span data-ttu-id="6c8bc-114">回應群組應用程式具有與前端伺服器相同的作業系統需求和軟體先決條件。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-114">The Response Group application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="6c8bc-115">如需軟體需求的詳細資訊，請參閱支援檔中的[Lync server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="6c8bc-116">如果您使用 Windows Media Audio （.wma）檔案來取得回應群組的音樂與宣告，所有前端伺服器或執行回應群組應用程式的標準版伺服器，都必須針對執行 Windows 的伺服器安裝 Windows Media 格式執行時間伺服器 2008 R2 或適用于執行 Windows Server 2012 或 Windows Server 2012 R2 之伺服器的 Microsoft 媒體基礎。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-116">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="6c8bc-117">針對 Windows Server 2008 R2，Windows Media 格式執行時間已安裝為 Windows 桌面體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-117">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="6c8bc-118">如需音訊需求的詳細資訊，請參閱本節稍後的「音訊檔案需求」。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-118">For more details about audio requirements, see "Audio File Requirements" later in this section.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="6c8bc-119">埠需求</span><span class="sxs-lookup"><span data-stu-id="6c8bc-119">Port Requirements</span></span>

<span data-ttu-id="6c8bc-120">回應群組應用程式使用下列埠：</span><span class="sxs-lookup"><span data-stu-id="6c8bc-120">The Response Group application uses the following ports:</span></span>

  - <span data-ttu-id="6c8bc-121">\*\*\*\*    用於 SIP 偵聽要求的埠5071</span><span class="sxs-lookup"><span data-stu-id="6c8bc-121">**Port 5071**   Used for SIP listening requests</span></span>

  - <span data-ttu-id="6c8bc-122">\*\*\*\*    用於 interserver 通訊的埠8404</span><span class="sxs-lookup"><span data-stu-id="6c8bc-122">**Port 8404**   Used for interserver communications</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6c8bc-123">這個埠是用於相符的服務，而且當回應群組應用程式部署在擁有多個前端伺服器的池中時，就是必要的。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-123">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="6c8bc-124">這些埠是預設的設定，您可以使用<STRONG>CsApplicationServer</STRONG> Cmdlet 變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-124">These ports are default settings that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="6c8bc-125">如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-125">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="6c8bc-126">音訊檔需求</span><span class="sxs-lookup"><span data-stu-id="6c8bc-126">Audio File Requirements</span></span>

<span data-ttu-id="6c8bc-127">回應群組應用程式支援波形（.wav）檔案格式和 Windows Media 音訊（.wma）檔案格式，以取得回應群組訊息、等候音樂或互動式語音回應（IVR）問題。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-127">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="6c8bc-128">Windows Media 音訊檔案格式要求 Windows Media 格式執行時間已安裝在執行 Windows Server 2008 R2 和 Windows Server 2008 的前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-128">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="6c8bc-129">如需詳細資訊，請參閱本節前面的「軟體需求」。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-129">For more details, see "Software Requirements" earlier in this section.</span></span>

<div>

## <a name="supported-wave-file-formats"></a><span data-ttu-id="6c8bc-130">支援的 Wave 檔案格式</span><span class="sxs-lookup"><span data-stu-id="6c8bc-130">Supported Wave File Formats</span></span>

<span data-ttu-id="6c8bc-131">所有的 wave 檔案必須符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="6c8bc-131">All wave files must meet the following requirements:</span></span>

  - <span data-ttu-id="6c8bc-132">8位或16位檔案</span><span class="sxs-lookup"><span data-stu-id="6c8bc-132">8-bit or 16-bit file</span></span>

  - <span data-ttu-id="6c8bc-133">線性脈衝程式碼調製（LPCM）、法律或 mu-定律格式</span><span class="sxs-lookup"><span data-stu-id="6c8bc-133">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

  - <span data-ttu-id="6c8bc-134">單聲道或身歷聲</span><span class="sxs-lookup"><span data-stu-id="6c8bc-134">Mono or stereo</span></span>

  - <span data-ttu-id="6c8bc-135">4MB 或更低</span><span class="sxs-lookup"><span data-stu-id="6c8bc-135">4MB or less</span></span>

<span data-ttu-id="6c8bc-136">為了獲得波形檔案的最佳效能，建議使用 16 kHz、單聲道、16位波檔案。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-136">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="6c8bc-137">支援的 Windows Media 音訊檔案格式</span><span class="sxs-lookup"><span data-stu-id="6c8bc-137">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="6c8bc-138">如果您使用的是 Windows Media 音訊檔，請考慮使用低傳輸率，並在 [載入] 底下驗證系統的效能。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-138">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="6c8bc-139">您可以使用 Microsoft Expression 編碼器4將檔案轉換成 Windows Media 音訊格式。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-139">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="6c8bc-140">若要下載運算式編碼器4， [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)請參閱。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-140">To download Expression Encoder 4, see [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span></span>

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="6c8bc-141">回應群組設定工具需求</span><span class="sxs-lookup"><span data-stu-id="6c8bc-141">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="6c8bc-142">[回應群組設定] 工具支援下表所述的作業系統與網頁瀏覽器混合。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-142">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6c8bc-143">支援32位或64位版本的作業系統。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-143">32-bit or 64-bit versions of the operating systems are supported.</span></span> <span data-ttu-id="6c8bc-144">僅支援32位版本的 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-144">Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="6c8bc-145">支援的作業系統與網頁瀏覽器</span><span class="sxs-lookup"><span data-stu-id="6c8bc-145">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c8bc-146">作業系統</span><span class="sxs-lookup"><span data-stu-id="6c8bc-146">Operating system</span></span></th>
<th><span data-ttu-id="6c8bc-147">網頁瀏覽器</span><span class="sxs-lookup"><span data-stu-id="6c8bc-147">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c8bc-148">Windows Vista （含 Service Pack （SP）2）</span><span class="sxs-lookup"><span data-stu-id="6c8bc-148">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="6c8bc-149">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="6c8bc-149">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="6c8bc-150">Internet Explorer 8 （原生模式）</span><span class="sxs-lookup"><span data-stu-id="6c8bc-150">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="6c8bc-151">Internet Explorer 9 （原生模式）</span><span class="sxs-lookup"><span data-stu-id="6c8bc-151">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8bc-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="6c8bc-152">Windows 7</span></span></p>
<p><span data-ttu-id="6c8bc-153">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="6c8bc-153">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="6c8bc-154">Internet Explorer 8 （原生模式）</span><span class="sxs-lookup"><span data-stu-id="6c8bc-154">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="6c8bc-155">Internet Explorer 9 （原生模式）</span><span class="sxs-lookup"><span data-stu-id="6c8bc-155">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8bc-156">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="6c8bc-156">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="6c8bc-157">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="6c8bc-157">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="6c8bc-158">Internet Explorer 8 （原生模式）</span><span class="sxs-lookup"><span data-stu-id="6c8bc-158">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="6c8bc-159">Internet Explorer 9 （原生模式）</span><span class="sxs-lookup"><span data-stu-id="6c8bc-159">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8bc-160">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="6c8bc-160">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="6c8bc-161">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="6c8bc-161">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="6c8bc-162">Internet Explorer 8 （原生模式）</span><span class="sxs-lookup"><span data-stu-id="6c8bc-162">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="6c8bc-163">Internet Explorer 9 （原生模式）</span><span class="sxs-lookup"><span data-stu-id="6c8bc-163">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a><span data-ttu-id="6c8bc-164">回應群組代理程式主控台</span><span class="sxs-lookup"><span data-stu-id="6c8bc-164">Response Group Agent Console</span></span>

<span data-ttu-id="6c8bc-165">[代理程式主控台] 支援下表所述的作業系統與網頁瀏覽器混合。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-165">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6c8bc-166">支援32位或64位版本的作業系統。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-166">32-bit or 64-bit versions of the operating systems are supported.</span></span> <span data-ttu-id="6c8bc-167">僅支援32位版本的 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="6c8bc-167">Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="6c8bc-168">支援的作業系統與網頁瀏覽器</span><span class="sxs-lookup"><span data-stu-id="6c8bc-168">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c8bc-169">作業系統</span><span class="sxs-lookup"><span data-stu-id="6c8bc-169">Operating system</span></span></th>
<th><span data-ttu-id="6c8bc-170">網頁瀏覽器</span><span class="sxs-lookup"><span data-stu-id="6c8bc-170">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c8bc-171">Windows Vista （含 Service Pack （SP）2）</span><span class="sxs-lookup"><span data-stu-id="6c8bc-171">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="6c8bc-172">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="6c8bc-172">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="6c8bc-173">Internet Explorer 8 （原生模式）</span><span class="sxs-lookup"><span data-stu-id="6c8bc-173">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="6c8bc-174">Internet Explorer 9 （原生模式）</span><span class="sxs-lookup"><span data-stu-id="6c8bc-174">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8bc-175">Windows 7</span><span class="sxs-lookup"><span data-stu-id="6c8bc-175">Windows 7</span></span></p>
<p><span data-ttu-id="6c8bc-176">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="6c8bc-176">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="6c8bc-177">Internet Explorer 8 （原生模式）</span><span class="sxs-lookup"><span data-stu-id="6c8bc-177">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="6c8bc-178">Internet Explorer 9 （原生模式）</span><span class="sxs-lookup"><span data-stu-id="6c8bc-178">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="6c8bc-179">Firefox 10。0</span><span class="sxs-lookup"><span data-stu-id="6c8bc-179">Firefox 10.0</span></span></p>
<p><span data-ttu-id="6c8bc-180">Chrome 18。0</span><span class="sxs-lookup"><span data-stu-id="6c8bc-180">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8bc-181">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="6c8bc-181">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="6c8bc-182">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="6c8bc-182">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="6c8bc-183">Internet Explorer 8 （原生模式）</span><span class="sxs-lookup"><span data-stu-id="6c8bc-183">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="6c8bc-184">Internet Explorer 9 （原生模式）</span><span class="sxs-lookup"><span data-stu-id="6c8bc-184">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8bc-185">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="6c8bc-185">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="6c8bc-186">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="6c8bc-186">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="6c8bc-187">Internet Explorer 8 （原生模式）</span><span class="sxs-lookup"><span data-stu-id="6c8bc-187">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="6c8bc-188">Internet Explorer 9 （原生模式）</span><span class="sxs-lookup"><span data-stu-id="6c8bc-188">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="6c8bc-189">Firefox 10。0</span><span class="sxs-lookup"><span data-stu-id="6c8bc-189">Firefox 10.0</span></span></p>
<p><span data-ttu-id="6c8bc-190">Chrome 18。0</span><span class="sxs-lookup"><span data-stu-id="6c8bc-190">Chrome 18.0</span></span></p></td>
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


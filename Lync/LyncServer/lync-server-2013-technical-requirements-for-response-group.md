---
title: Lync Server 2013： 的回應群組的技術需求
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
ms.openlocfilehash: 041f4c6ada99d6991c18b20f77701c78eec8cd95
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42022564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a><span data-ttu-id="71a7a-102">Lync Server 2013 中的回應群組的技術需求</span><span class="sxs-lookup"><span data-stu-id="71a7a-102">Technical requirements for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71a7a-103">_**上次修改主題：** 2013年-11-07_</span><span class="sxs-lookup"><span data-stu-id="71a7a-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="71a7a-104">本節說明回應群組應用程式的下列技術需求：</span><span class="sxs-lookup"><span data-stu-id="71a7a-104">This section describes the following technical requirements for the Response Group application:</span></span>

  - <span data-ttu-id="71a7a-105">硬體需求</span><span class="sxs-lookup"><span data-stu-id="71a7a-105">Hardware requirements</span></span>

  - <span data-ttu-id="71a7a-106">軟體需求</span><span class="sxs-lookup"><span data-stu-id="71a7a-106">Software requirements</span></span>

  - <span data-ttu-id="71a7a-107">連接埠需求</span><span class="sxs-lookup"><span data-stu-id="71a7a-107">Port requirements</span></span>

  - <span data-ttu-id="71a7a-108">音訊檔案需求</span><span class="sxs-lookup"><span data-stu-id="71a7a-108">Audio file requirements</span></span>

  - <span data-ttu-id="71a7a-109">回應群組組態工具需求</span><span class="sxs-lookup"><span data-stu-id="71a7a-109">Response Group configuration tool requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="71a7a-110">硬體需求</span><span class="sxs-lookup"><span data-stu-id="71a7a-110">Hardware Requirements</span></span>

<span data-ttu-id="71a7a-111">回應群組應用程式都有相同的硬體需求，作為前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="71a7a-111">The Response Group application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="71a7a-112">如需硬體需求的詳細資訊，請參閱支援文件中的[Lync Server 2013 的伺服器硬體平台](lync-server-2013-server-hardware-platforms.md)。</span><span class="sxs-lookup"><span data-stu-id="71a7a-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="71a7a-113">軟體需求</span><span class="sxs-lookup"><span data-stu-id="71a7a-113">Software Requirements</span></span>

<span data-ttu-id="71a7a-114">回應群組應用程式具有與前端伺服器相同的作業系統需求及軟體先決條件。</span><span class="sxs-lookup"><span data-stu-id="71a7a-114">The Response Group application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="71a7a-115">如需軟體需求的詳細資訊，請參閱支援文件中的[Lync Server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)。</span><span class="sxs-lookup"><span data-stu-id="71a7a-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="71a7a-116">如果您的回應群組音樂] 和 [宣告使用 Windows Media Audio (.wma) 檔案，請執行回應群組應用程式的所有前端伺服器或 Standard Edition 伺服器必須執行 Windows 的伺服器已安裝 Windows Media Format RuntimeServer 2008 R2 或 Microsoft 媒體 Foundation 執行 Windows Server 2012 或 Windows Server 2012 R2 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="71a7a-116">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="71a7a-117">Windows Server 2008 R2、 Windows Media Format Runtime 被安裝 Windows 桌面體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="71a7a-117">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="71a7a-118">如需有關音訊需求的詳細資訊，請參閱本節稍後的＜音訊檔案需求＞。</span><span class="sxs-lookup"><span data-stu-id="71a7a-118">For more details about audio requirements, see "Audio File Requirements" later in this section.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="71a7a-119">連接埠需求</span><span class="sxs-lookup"><span data-stu-id="71a7a-119">Port Requirements</span></span>

<span data-ttu-id="71a7a-120">回應群組應用程式使用下列連接埠：</span><span class="sxs-lookup"><span data-stu-id="71a7a-120">The Response Group application uses the following ports:</span></span>

  - <span data-ttu-id="71a7a-121">**連接埠 5071**   用於 SIP 聆聽要求</span><span class="sxs-lookup"><span data-stu-id="71a7a-121">**Port 5071**   Used for SIP listening requests</span></span>

  - <span data-ttu-id="71a7a-122">**連接埠 8404**   用於伺服器間的通訊</span><span class="sxs-lookup"><span data-stu-id="71a7a-122">**Port 8404**   Used for interserver communications</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="71a7a-123">此連接埠用於配對服務，並具有多個前端伺服器集區中部署的回應群組應用程式時，為必要。</span><span class="sxs-lookup"><span data-stu-id="71a7a-123">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="71a7a-124">這些連接埠為預設設定，可使用 <STRONG>Set-CsApplicationServer</STRONG> Cmdlet 予以變更。</span><span class="sxs-lookup"><span data-stu-id="71a7a-124">These ports are default settings that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="71a7a-125">如需此 cmdlet 的詳細資訊，請參閱 < Lync Server 管理命令介面文件。</span><span class="sxs-lookup"><span data-stu-id="71a7a-125">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="71a7a-126">音訊檔案需求</span><span class="sxs-lookup"><span data-stu-id="71a7a-126">Audio File Requirements</span></span>

<span data-ttu-id="71a7a-127">回應群組應用程式支援 wave (.wav) 檔案格式和 Windows Media 音訊 (.wma) 檔案格式的回應群組訊息、 在保留音樂或互動語音回應 (IVR) 問題。</span><span class="sxs-lookup"><span data-stu-id="71a7a-127">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="71a7a-128">Windows Media 音訊檔案格式需要的 Windows Media Format Runtime 一起安裝在前端伺服器執行 Windows Server 2008 R2 和 Windows Server 2008 上。</span><span class="sxs-lookup"><span data-stu-id="71a7a-128">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="71a7a-129">如需詳細資訊，請參閱本節稍早的＜軟體需求＞。</span><span class="sxs-lookup"><span data-stu-id="71a7a-129">For more details, see "Software Requirements" earlier in this section.</span></span>

<div>

## <a name="supported-wave-file-formats"></a><span data-ttu-id="71a7a-130">支援的 Wave 檔案格式</span><span class="sxs-lookup"><span data-stu-id="71a7a-130">Supported Wave File Formats</span></span>

<span data-ttu-id="71a7a-131">所有 Wave 檔案必須符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="71a7a-131">All wave files must meet the following requirements:</span></span>

  - <span data-ttu-id="71a7a-132">8 位元或 16 位元檔案</span><span class="sxs-lookup"><span data-stu-id="71a7a-132">8-bit or 16-bit file</span></span>

  - <span data-ttu-id="71a7a-133">線性脈衝代碼調變 (LPCM)，A-Law 或 mu-Law 格式</span><span class="sxs-lookup"><span data-stu-id="71a7a-133">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

  - <span data-ttu-id="71a7a-134">單音或立體聲</span><span class="sxs-lookup"><span data-stu-id="71a7a-134">Mono or stereo</span></span>

  - <span data-ttu-id="71a7a-135">4MB 以下</span><span class="sxs-lookup"><span data-stu-id="71a7a-135">4MB or less</span></span>

<span data-ttu-id="71a7a-136">為使 Wave 檔案有最佳表現，建議使用 16 kHz 單音的 16 位元 Wave 檔案。</span><span class="sxs-lookup"><span data-stu-id="71a7a-136">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="71a7a-137">支援的 Windows Media 音訊檔案格式</span><span class="sxs-lookup"><span data-stu-id="71a7a-137">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="71a7a-138">如果您使用 Windows Media 音訊檔案，請考慮使用低位元速率，並驗證系統承受負載時的效能。</span><span class="sxs-lookup"><span data-stu-id="71a7a-138">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="71a7a-139">您可以使用 Microsoft Expression Encoder 4 將檔案轉換成 Windows Media Audio 格式。</span><span class="sxs-lookup"><span data-stu-id="71a7a-139">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="71a7a-140">若要下載運算式編碼器 4，請參閱[http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)。</span><span class="sxs-lookup"><span data-stu-id="71a7a-140">To download Expression Encoder 4, see [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span></span>

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="71a7a-141">回應群組設定工具需求</span><span class="sxs-lookup"><span data-stu-id="71a7a-141">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="71a7a-142">回應群組組態工具支援的作業系統和網頁瀏覽器中，如下表所述的組合。</span><span class="sxs-lookup"><span data-stu-id="71a7a-142">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="71a7a-p107">支援 32 位元或 64 位元版本的作業系統。只支援 32 位元版本的 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="71a7a-p107">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="71a7a-145">支援的作業系統和網頁瀏覽器</span><span class="sxs-lookup"><span data-stu-id="71a7a-145">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71a7a-146">作業系統</span><span class="sxs-lookup"><span data-stu-id="71a7a-146">Operating system</span></span></th>
<th><span data-ttu-id="71a7a-147">網頁瀏覽器</span><span class="sxs-lookup"><span data-stu-id="71a7a-147">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71a7a-148">Windows Vista Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="71a7a-148">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="71a7a-149">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="71a7a-149">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="71a7a-150">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="71a7a-150">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="71a7a-151">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="71a7a-151">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71a7a-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="71a7a-152">Windows 7</span></span></p>
<p><span data-ttu-id="71a7a-153">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="71a7a-153">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="71a7a-154">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="71a7a-154">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="71a7a-155">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="71a7a-155">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71a7a-156">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="71a7a-156">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="71a7a-157">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="71a7a-157">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="71a7a-158">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="71a7a-158">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="71a7a-159">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="71a7a-159">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71a7a-160">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="71a7a-160">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="71a7a-161">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="71a7a-161">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="71a7a-162">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="71a7a-162">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="71a7a-163">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="71a7a-163">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a><span data-ttu-id="71a7a-164">回應群組代理程式主控台</span><span class="sxs-lookup"><span data-stu-id="71a7a-164">Response Group Agent Console</span></span>

<span data-ttu-id="71a7a-165">代理程式主控台支援下表中所述之作業系統和網頁瀏覽器的組合。</span><span class="sxs-lookup"><span data-stu-id="71a7a-165">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="71a7a-p108">支援 32 位元或 64 位元版本的作業系統。只支援 32 位元版本的 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="71a7a-p108">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="71a7a-168">支援的作業系統和網頁瀏覽器</span><span class="sxs-lookup"><span data-stu-id="71a7a-168">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71a7a-169">作業系統</span><span class="sxs-lookup"><span data-stu-id="71a7a-169">Operating system</span></span></th>
<th><span data-ttu-id="71a7a-170">網頁瀏覽器</span><span class="sxs-lookup"><span data-stu-id="71a7a-170">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71a7a-171">Windows Vista Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="71a7a-171">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="71a7a-172">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="71a7a-172">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="71a7a-173">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="71a7a-173">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="71a7a-174">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="71a7a-174">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71a7a-175">Windows 7</span><span class="sxs-lookup"><span data-stu-id="71a7a-175">Windows 7</span></span></p>
<p><span data-ttu-id="71a7a-176">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="71a7a-176">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="71a7a-177">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="71a7a-177">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="71a7a-178">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="71a7a-178">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="71a7a-179">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="71a7a-179">Firefox 10.0</span></span></p>
<p><span data-ttu-id="71a7a-180">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="71a7a-180">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71a7a-181">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="71a7a-181">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="71a7a-182">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="71a7a-182">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="71a7a-183">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="71a7a-183">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="71a7a-184">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="71a7a-184">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71a7a-185">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="71a7a-185">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="71a7a-186">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="71a7a-186">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="71a7a-187">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="71a7a-187">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="71a7a-188">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="71a7a-188">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="71a7a-189">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="71a7a-189">Firefox 10.0</span></span></p>
<p><span data-ttu-id="71a7a-190">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="71a7a-190">Chrome 18.0</span></span></p></td>
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


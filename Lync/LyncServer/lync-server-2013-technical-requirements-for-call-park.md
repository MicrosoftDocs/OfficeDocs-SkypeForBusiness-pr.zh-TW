---
title: Lync Server 2013：通話駐留的技術需求
description: Lync Server 2013：通話駐留的技術需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ddc17b40f78c42c090d1a87b4580ebdad0a07f6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577129"
---
# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a><span data-ttu-id="51090-103">Lync Server 2013 中通話駐留的技術需求</span><span class="sxs-lookup"><span data-stu-id="51090-103">Technical requirements for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51090-104">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="51090-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="51090-105">本節說明通話駐留的下列技術需求：</span><span class="sxs-lookup"><span data-stu-id="51090-105">This section describes the following technical requirements for Call Park:</span></span>

  - <span data-ttu-id="51090-106">硬體需求</span><span class="sxs-lookup"><span data-stu-id="51090-106">Hardware requirements</span></span>

  - <span data-ttu-id="51090-107">軟體需求</span><span class="sxs-lookup"><span data-stu-id="51090-107">Software requirements</span></span>

  - <span data-ttu-id="51090-108">連接埠需求</span><span class="sxs-lookup"><span data-stu-id="51090-108">Port requirements</span></span>

  - <span data-ttu-id="51090-109">音訊檔需求</span><span class="sxs-lookup"><span data-stu-id="51090-109">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="51090-110">硬體需求</span><span class="sxs-lookup"><span data-stu-id="51090-110">Hardware Requirements</span></span>

<span data-ttu-id="51090-111">通話駐留應用程式的硬體需求與前端伺服器相同。</span><span class="sxs-lookup"><span data-stu-id="51090-111">The Call Park application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="51090-112">如需硬體需求的詳細資訊，請參閱支援檔中的 [Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md) 。</span><span class="sxs-lookup"><span data-stu-id="51090-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="51090-113">軟體需求</span><span class="sxs-lookup"><span data-stu-id="51090-113">Software Requirements</span></span>

<span data-ttu-id="51090-114">通話駐留應用程式與前端伺服器具有相同的作業系統需求和軟體必要條件。</span><span class="sxs-lookup"><span data-stu-id="51090-114">The Call Park application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="51090-115">如需軟體需求的詳細資訊，請參閱支援檔中的 [伺服器和工具作業系統支援（Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) ）。</span><span class="sxs-lookup"><span data-stu-id="51090-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="51090-116">部署通話駐留應用程式的所有前端伺服器和 Standard Edition 伺服器，都必須為執行 windows Server 2008 R2 的伺服器安裝 Windows Media Format Runtime，或為執行 Windows Server 2012 或 Windows Server 2012 R2 的伺服器安裝 Microsoft Media Foundation。</span><span class="sxs-lookup"><span data-stu-id="51090-116">All Front End Servers and Standard Edition servers where the Call Park application is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="51090-117">若為 Windows Server 2008 R2，Windows Media Format Runtime 會安裝為 Windows 桌面體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="51090-117">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="51090-118">Windows media Audio ( 的 windows Media Format Runtime 或 Microsoft Media Foundation 是必要的功能。) 通話駐留的檔案會對等候音樂播放。</span><span class="sxs-lookup"><span data-stu-id="51090-118">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="51090-119">連接埠需求</span><span class="sxs-lookup"><span data-stu-id="51090-119">Port Requirements</span></span>

<span data-ttu-id="51090-120">通話駐留應用程式使用下列埠：</span><span class="sxs-lookup"><span data-stu-id="51090-120">The Call Park application uses the following port:</span></span>

  - <span data-ttu-id="51090-121">**埠 5075**    用於 SIP 聆聽要求。</span><span class="sxs-lookup"><span data-stu-id="51090-121">**Port 5075**   Used for SIP listening requests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="51090-122">此連接埠為預設設定，可使用 <STRONG>Set-CsApplicationServer</STRONG> Cmdlet 予以變更。</span><span class="sxs-lookup"><span data-stu-id="51090-122">This port is a default setting that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="51090-123">如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="51090-123">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="51090-124">音訊檔案需求</span><span class="sxs-lookup"><span data-stu-id="51090-124">Audio File Requirements</span></span>

<span data-ttu-id="51090-125">通話駐留應用程式僅支援 Windows Media Audio ( 的 wma) 檔案用於等候音樂。</span><span class="sxs-lookup"><span data-stu-id="51090-125">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="51090-126">您可以使用 Microsoft Expression Encoder 4 自訂等候音樂的檔案。</span><span class="sxs-lookup"><span data-stu-id="51090-126">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="51090-127">若要下載運算式編碼器4，請參閱的「運算式編碼器4」 [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843) 。</span><span class="sxs-lookup"><span data-stu-id="51090-127">To download Expression Encoder 4, see "Expression Encoder 4" at [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span></span> <span data-ttu-id="51090-128">使用此工具可將檔案轉換成 .wma 格式。</span><span class="sxs-lookup"><span data-stu-id="51090-128">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="51090-129">通話駐留等候音樂檔案的建議格式為 Media Audio 9、44 kHz、16 位元、Mono、CBR、32 kbps。</span><span class="sxs-lookup"><span data-stu-id="51090-129">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="51090-130">轉換後的檔案只能以 16 kHz 音頻在電話中播放，即使檔案是以 44 kHz 音頻錄製也一樣。</span><span class="sxs-lookup"><span data-stu-id="51090-130">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


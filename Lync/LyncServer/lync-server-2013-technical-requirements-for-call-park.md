---
title: Lync Server 2013： 通話駐留的技術需求
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
ms.openlocfilehash: 6467f4047754697322780373521cdd47fe1e1ba3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a><span data-ttu-id="dac8e-102">Lync Server 2013 中的通話駐留的技術需求</span><span class="sxs-lookup"><span data-stu-id="dac8e-102">Technical requirements for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dac8e-103">_**上次修改主題：** 2013年-11-07_</span><span class="sxs-lookup"><span data-stu-id="dac8e-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="dac8e-104">本節說明通話駐留的技術需求如下：</span><span class="sxs-lookup"><span data-stu-id="dac8e-104">This section describes the following technical requirements for Call Park:</span></span>

  - <span data-ttu-id="dac8e-105">硬體需求</span><span class="sxs-lookup"><span data-stu-id="dac8e-105">Hardware requirements</span></span>

  - <span data-ttu-id="dac8e-106">軟體需求</span><span class="sxs-lookup"><span data-stu-id="dac8e-106">Software requirements</span></span>

  - <span data-ttu-id="dac8e-107">連接埠需求</span><span class="sxs-lookup"><span data-stu-id="dac8e-107">Port requirements</span></span>

  - <span data-ttu-id="dac8e-108">音訊檔需求</span><span class="sxs-lookup"><span data-stu-id="dac8e-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="dac8e-109">硬體需求</span><span class="sxs-lookup"><span data-stu-id="dac8e-109">Hardware Requirements</span></span>

<span data-ttu-id="dac8e-110">通話駐留應用程式都有相同的硬體需求，作為前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="dac8e-110">The Call Park application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="dac8e-111">如需硬體需求的詳細資訊，請參閱支援文件中的[Lync Server 2013 的伺服器硬體平台](lync-server-2013-server-hardware-platforms.md)。</span><span class="sxs-lookup"><span data-stu-id="dac8e-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="dac8e-112">軟體需求</span><span class="sxs-lookup"><span data-stu-id="dac8e-112">Software Requirements</span></span>

<span data-ttu-id="dac8e-113">通話駐留應用程式具有與前端伺服器相同的作業系統需求及軟體先決條件。</span><span class="sxs-lookup"><span data-stu-id="dac8e-113">The Call Park application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="dac8e-114">如需軟體需求的詳細資訊，請參閱支援文件中的[Lync Server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)。</span><span class="sxs-lookup"><span data-stu-id="dac8e-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="dac8e-115">部署通話駐留應用程式，其中的所有前端伺服器和 Standard Edition 伺服器必須執行 Windows Server 2008 R2 或 Microsoft 媒體 Foundation 執行 Windows Server 2012 的伺服器的伺服器已安裝 Windows Media Format Runtime 或Windows Server 2012 R2。</span><span class="sxs-lookup"><span data-stu-id="dac8e-115">All Front End Servers and Standard Edition servers where the Call Park application is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="dac8e-116">Windows Server 2008 R2、 Windows Media Format Runtime 被安裝 Windows 桌面體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="dac8e-116">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="dac8e-117">Windows Media Format Runtime] 或 [Microsoft 媒體 Foundation 才所需的 Windows Media Audio (.wma) 檔案的通話駐留播放音樂保留。</span><span class="sxs-lookup"><span data-stu-id="dac8e-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="dac8e-118">連接埠需求</span><span class="sxs-lookup"><span data-stu-id="dac8e-118">Port Requirements</span></span>

<span data-ttu-id="dac8e-119">通話駐留應用程式使用下列連接埠：</span><span class="sxs-lookup"><span data-stu-id="dac8e-119">The Call Park application uses the following port:</span></span>

  - <span data-ttu-id="dac8e-120">**連接埠 5075**   用於 SIP 聆聽要求。</span><span class="sxs-lookup"><span data-stu-id="dac8e-120">**Port 5075**   Used for SIP listening requests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dac8e-121">此連接埠為預設設定，可使用 <STRONG>Set-CsApplicationServer</STRONG> Cmdlet 予以變更。</span><span class="sxs-lookup"><span data-stu-id="dac8e-121">This port is a default setting that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="dac8e-122">如需此 cmdlet 的詳細資訊，請參閱 < Lync Server 管理命令介面文件。</span><span class="sxs-lookup"><span data-stu-id="dac8e-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="dac8e-123">音訊檔案需求</span><span class="sxs-lookup"><span data-stu-id="dac8e-123">Audio File Requirements</span></span>

<span data-ttu-id="dac8e-124">通話駐留應用程式只支援 Windows Media Audio (.wma) 檔案的等候音樂保留。</span><span class="sxs-lookup"><span data-stu-id="dac8e-124">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="dac8e-125">您可以使用 Microsoft Expression Encoder 4 自訂等候音樂的檔案。</span><span class="sxs-lookup"><span data-stu-id="dac8e-125">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="dac8e-126">若要下載運算式編碼器 4，請參閱 「 運算式編碼器 4" [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843)。</span><span class="sxs-lookup"><span data-stu-id="dac8e-126">To download Expression Encoder 4, see "Expression Encoder 4" at [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span></span> <span data-ttu-id="dac8e-127">使用此工具可將檔案轉換成 .wma 格式。</span><span class="sxs-lookup"><span data-stu-id="dac8e-127">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="dac8e-128">通話駐留等候音樂檔案的建議格式為 Media Audio 9、44 kHz、16 位元、Mono、CBR、32 kbps。</span><span class="sxs-lookup"><span data-stu-id="dac8e-128">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dac8e-129">轉換後的檔案只能以 16 kHz 音頻在電話中播放，即使檔案是以 44 kHz 音頻錄製也一樣。</span><span class="sxs-lookup"><span data-stu-id="dac8e-129">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


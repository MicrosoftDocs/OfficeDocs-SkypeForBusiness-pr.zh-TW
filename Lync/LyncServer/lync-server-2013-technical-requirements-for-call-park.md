---
title: Lync Server 2013：通話駐留的技術需求
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
ms.openlocfilehash: 742d6ef62068e3e6e3bbd953e078b186e86bb497
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a><span data-ttu-id="91ef3-102">Lync Server 2013 中通話駐留的技術需求</span><span class="sxs-lookup"><span data-stu-id="91ef3-102">Technical requirements for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91ef3-103">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="91ef3-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="91ef3-104">本節說明通話駐留的下列技術需求：</span><span class="sxs-lookup"><span data-stu-id="91ef3-104">This section describes the following technical requirements for Call Park:</span></span>

  - <span data-ttu-id="91ef3-105">硬體需求</span><span class="sxs-lookup"><span data-stu-id="91ef3-105">Hardware requirements</span></span>

  - <span data-ttu-id="91ef3-106">軟體需求</span><span class="sxs-lookup"><span data-stu-id="91ef3-106">Software requirements</span></span>

  - <span data-ttu-id="91ef3-107">埠需求</span><span class="sxs-lookup"><span data-stu-id="91ef3-107">Port requirements</span></span>

  - <span data-ttu-id="91ef3-108">音訊檔需求</span><span class="sxs-lookup"><span data-stu-id="91ef3-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="91ef3-109">硬體需求</span><span class="sxs-lookup"><span data-stu-id="91ef3-109">Hardware Requirements</span></span>

<span data-ttu-id="91ef3-110">通話駐留應用程式具有與前端伺服器相同的硬體需求。</span><span class="sxs-lookup"><span data-stu-id="91ef3-110">The Call Park application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="91ef3-111">如需硬體需求的詳細資訊，請參閱支援檔中的[Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)。</span><span class="sxs-lookup"><span data-stu-id="91ef3-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="91ef3-112">軟體需求</span><span class="sxs-lookup"><span data-stu-id="91ef3-112">Software Requirements</span></span>

<span data-ttu-id="91ef3-113">通話駐留應用程式具有與前端伺服器相同的作業系統需求和軟體先決條件。</span><span class="sxs-lookup"><span data-stu-id="91ef3-113">The Call Park application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="91ef3-114">如需軟體需求的詳細資訊，請參閱支援檔中的[Lync server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)。</span><span class="sxs-lookup"><span data-stu-id="91ef3-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="91ef3-115">已部署通話駐留應用程式的所有前端伺服器和標準版伺服器，都必須針對執行 Windows Server 2008 R2 的伺服器安裝 Windows Media 格式執行時間，或是執行 Windows Server 2012 的伺服器的 Microsoft Media Foundation，或Windows Server 2012 R2。</span><span class="sxs-lookup"><span data-stu-id="91ef3-115">All Front End Servers and Standard Edition servers where the Call Park application is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="91ef3-116">針對 Windows Server 2008 R2，Windows Media 格式執行時間已安裝為 Windows 桌面體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="91ef3-116">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="91ef3-117">Windows media 音訊（.wma）檔案需要 windows Media Format 執行時間或 Microsoft 媒體基礎，這些檔案會通話駐留的暫停播放。</span><span class="sxs-lookup"><span data-stu-id="91ef3-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="91ef3-118">埠需求</span><span class="sxs-lookup"><span data-stu-id="91ef3-118">Port Requirements</span></span>

<span data-ttu-id="91ef3-119">通話駐留應用程式使用下列埠：</span><span class="sxs-lookup"><span data-stu-id="91ef3-119">The Call Park application uses the following port:</span></span>

  - <span data-ttu-id="91ef3-120">\*\*\*\*    用於 SIP 偵聽要求的埠5075。</span><span class="sxs-lookup"><span data-stu-id="91ef3-120">**Port 5075**   Used for SIP listening requests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="91ef3-121">此埠是預設設定，您可以使用<STRONG>CsApplicationServer</STRONG> Cmdlet 進行變更。</span><span class="sxs-lookup"><span data-stu-id="91ef3-121">This port is a default setting that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="91ef3-122">如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="91ef3-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="91ef3-123">音訊檔需求</span><span class="sxs-lookup"><span data-stu-id="91ef3-123">Audio File Requirements</span></span>

<span data-ttu-id="91ef3-124">通話駐留應用程式只支援 Windows Media 音訊（.wma）檔案，以供等候音樂。</span><span class="sxs-lookup"><span data-stu-id="91ef3-124">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="91ef3-125">您可以使用 Microsoft Expression 編碼器4來自訂等候音樂的檔案。</span><span class="sxs-lookup"><span data-stu-id="91ef3-125">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="91ef3-126">若要下載 Expression 編碼器4，請參閱「運算式編碼器 4 [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)」。</span><span class="sxs-lookup"><span data-stu-id="91ef3-126">To download Expression Encoder 4, see "Expression Encoder 4" at [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span></span> <span data-ttu-id="91ef3-127">使用工具將檔案轉換為 .wma 格式。</span><span class="sxs-lookup"><span data-stu-id="91ef3-127">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="91ef3-128">通話駐留音樂保留盤案的建議格式是媒體音訊9、44 kHz、16位、單聲道、CBR、32 kbps。</span><span class="sxs-lookup"><span data-stu-id="91ef3-128">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="91ef3-129">已轉換的檔案只能在 16 kHz 的電話上播放，即使該檔案是在 44 kHz 錄製。</span><span class="sxs-lookup"><span data-stu-id="91ef3-129">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


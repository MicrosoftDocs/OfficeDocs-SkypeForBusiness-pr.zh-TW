---
title: Lync Server 2013：宣告應用程式的技術需求
description: Lync Server 2013：宣告應用程式的技術需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adc5019408b79301bbcda3993ceb7d96ee4d9b7d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550309"
---
# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="b5db8-103">Lync Server 2013 中宣告應用程式的技術需求</span><span class="sxs-lookup"><span data-stu-id="b5db8-103">Technical requirements for the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5db8-104">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="b5db8-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="b5db8-105">本節說明宣告應用程式的下列技術需求：</span><span class="sxs-lookup"><span data-stu-id="b5db8-105">This section describes the following technical requirements for the Announcement application:</span></span>

  - <span data-ttu-id="b5db8-106">硬體需求</span><span class="sxs-lookup"><span data-stu-id="b5db8-106">Hardware requirements</span></span>

  - <span data-ttu-id="b5db8-107">軟體需求</span><span class="sxs-lookup"><span data-stu-id="b5db8-107">Software requirements</span></span>

  - <span data-ttu-id="b5db8-108">連接埠需求</span><span class="sxs-lookup"><span data-stu-id="b5db8-108">Port requirements</span></span>

  - <span data-ttu-id="b5db8-109">音訊檔需求</span><span class="sxs-lookup"><span data-stu-id="b5db8-109">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="b5db8-110">硬體需求</span><span class="sxs-lookup"><span data-stu-id="b5db8-110">Hardware Requirements</span></span>

<span data-ttu-id="b5db8-111">宣告應用程式的硬體需求與前端伺服器相同。</span><span class="sxs-lookup"><span data-stu-id="b5db8-111">The Announcement application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="b5db8-112">如需硬體需求的詳細資訊，請參閱支援檔中的 [Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md) 。</span><span class="sxs-lookup"><span data-stu-id="b5db8-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="b5db8-113">軟體需求</span><span class="sxs-lookup"><span data-stu-id="b5db8-113">Software Requirements</span></span>

<span data-ttu-id="b5db8-114">宣告應用程式與前端伺服器具有相同的作業系統需求和軟體必要條件。</span><span class="sxs-lookup"><span data-stu-id="b5db8-114">The Announcement application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="b5db8-115">如需軟體需求的詳細資訊，請參閱支援檔中的 [伺服器和工具作業系統支援（Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) ）。</span><span class="sxs-lookup"><span data-stu-id="b5db8-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="b5db8-116">執行宣告應用程式的所有前端伺服器或 Standard Edition 伺服器，都必須為執行 windows Server 2008 R2 的伺服器安裝 Windows Media Format Runtime，或為執行 Windows Server 2012 或 Windows Server 2012 R2 的伺服器安裝 Microsoft Media Foundation。</span><span class="sxs-lookup"><span data-stu-id="b5db8-116">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="b5db8-117">若為 Windows Server 2008 R2，Windows Media Format Runtime 會安裝為 Windows 桌面體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="b5db8-117">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="b5db8-118">Windows media Audio ( 的 windows media Format Runtime 或 Microsoft Media Foundation 是 Windows Media Audio 的必要功能。宣告應用程式針對宣告和音樂所播放的 wma) 檔案。</span><span class="sxs-lookup"><span data-stu-id="b5db8-118">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="b5db8-119">連接埠需求</span><span class="sxs-lookup"><span data-stu-id="b5db8-119">Port Requirements</span></span>

<span data-ttu-id="b5db8-120">宣告應用程式使用下列埠：</span><span class="sxs-lookup"><span data-stu-id="b5db8-120">The Announcement application uses the following port:</span></span>

  - <span data-ttu-id="b5db8-121">**埠 5071**    用於 SIP 聆聽要求</span><span class="sxs-lookup"><span data-stu-id="b5db8-121">**Port 5071**   Used for SIP listening requests</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b5db8-122">此埠是預設設定，您可以使用 <STRONG>Set-CsApplicationServer</STRONG> Cmdlet 進行變更。</span><span class="sxs-lookup"><span data-stu-id="b5db8-122">This port is the default setting, which you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="b5db8-123">如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="b5db8-123">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="b5db8-124">音訊檔案需求</span><span class="sxs-lookup"><span data-stu-id="b5db8-124">Audio File Requirements</span></span>

<span data-ttu-id="b5db8-125">宣告應用程式支援波形 ( .wav) 檔案格式和 Windows Media 音訊)  ( 的音樂和宣告的檔案格式。</span><span class="sxs-lookup"><span data-stu-id="b5db8-125">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="b5db8-126">宣告應用程式的音訊檔需求與回應群組應用程式相同。</span><span class="sxs-lookup"><span data-stu-id="b5db8-126">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="b5db8-127">如需詳細資訊，請參閱 [Lync Server 2013 中的回應群組技術需求](lync-server-2013-technical-requirements-for-response-group.md)。</span><span class="sxs-lookup"><span data-stu-id="b5db8-127">For details, see [Technical requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


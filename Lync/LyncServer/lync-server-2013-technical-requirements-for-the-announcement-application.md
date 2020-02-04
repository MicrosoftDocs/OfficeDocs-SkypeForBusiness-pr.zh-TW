---
title: Lync Server 2013：宣告應用程式的技術需求
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
ms.openlocfilehash: 8812dca81d656e68fc506c4a87c3c80481040bf6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="592ea-102">Lync Server 2013 中的宣告應用程式的技術需求</span><span class="sxs-lookup"><span data-stu-id="592ea-102">Technical requirements for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="592ea-103">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="592ea-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="592ea-104">本節說明宣告應用程式的下列技術需求：</span><span class="sxs-lookup"><span data-stu-id="592ea-104">This section describes the following technical requirements for the Announcement application:</span></span>

  - <span data-ttu-id="592ea-105">硬體需求</span><span class="sxs-lookup"><span data-stu-id="592ea-105">Hardware requirements</span></span>

  - <span data-ttu-id="592ea-106">軟體需求</span><span class="sxs-lookup"><span data-stu-id="592ea-106">Software requirements</span></span>

  - <span data-ttu-id="592ea-107">埠需求</span><span class="sxs-lookup"><span data-stu-id="592ea-107">Port requirements</span></span>

  - <span data-ttu-id="592ea-108">音訊檔需求</span><span class="sxs-lookup"><span data-stu-id="592ea-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="592ea-109">硬體需求</span><span class="sxs-lookup"><span data-stu-id="592ea-109">Hardware Requirements</span></span>

<span data-ttu-id="592ea-110">宣告應用程式的硬體需求與前端伺服器相同。</span><span class="sxs-lookup"><span data-stu-id="592ea-110">The Announcement application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="592ea-111">如需硬體需求的詳細資訊，請參閱支援檔中的[Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)。</span><span class="sxs-lookup"><span data-stu-id="592ea-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="592ea-112">軟體需求</span><span class="sxs-lookup"><span data-stu-id="592ea-112">Software Requirements</span></span>

<span data-ttu-id="592ea-113">宣告應用程式的作業系統需求和軟體先決條件與前端伺服器相同。</span><span class="sxs-lookup"><span data-stu-id="592ea-113">The Announcement application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="592ea-114">如需軟體需求的詳細資訊，請參閱支援檔中的[Lync server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)。</span><span class="sxs-lookup"><span data-stu-id="592ea-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="592ea-115">執行宣告應用程式的所有前端伺服器或標準版伺服器，都必須針對執行 Windows Server 2008 R2 的伺服器安裝 windows Media 格式執行時間，或是執行 Windows Server 2012 的伺服器的 Microsoft Media Foundation，或Windows Server 2012 R2。</span><span class="sxs-lookup"><span data-stu-id="592ea-115">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="592ea-116">針對 Windows Server 2008 R2，Windows Media 格式執行時間會安裝為 Windows 桌面體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="592ea-116">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="592ea-117">Windows Media 格式執行時間或 Microsoft 媒體基礎是 Windows Media 音訊（.wma）檔案所必需的，這些檔案是宣告應用程式在公告和音樂中播放的檔。</span><span class="sxs-lookup"><span data-stu-id="592ea-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="592ea-118">埠需求</span><span class="sxs-lookup"><span data-stu-id="592ea-118">Port Requirements</span></span>

<span data-ttu-id="592ea-119">宣告應用程式會使用下列埠：</span><span class="sxs-lookup"><span data-stu-id="592ea-119">The Announcement application uses the following port:</span></span>

  - <span data-ttu-id="592ea-120">\*\*\*\*    用於 SIP 偵聽要求的埠5071</span><span class="sxs-lookup"><span data-stu-id="592ea-120">**Port 5071**   Used for SIP listening requests</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="592ea-121">這個埠是預設設定，您可以使用<STRONG>CsApplicationServer</STRONG> Cmdlet 進行變更。</span><span class="sxs-lookup"><span data-stu-id="592ea-121">This port is the default setting, which you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="592ea-122">如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="592ea-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="592ea-123">音訊檔需求</span><span class="sxs-lookup"><span data-stu-id="592ea-123">Audio File Requirements</span></span>

<span data-ttu-id="592ea-124">宣告應用程式支援 Wave （.wav）檔案格式和 Windows Media 音訊（.wma）檔案格式，以供音樂和公告用。</span><span class="sxs-lookup"><span data-stu-id="592ea-124">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="592ea-125">宣告應用程式的音訊檔需求與回應群組應用程式相同。</span><span class="sxs-lookup"><span data-stu-id="592ea-125">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="592ea-126">如需詳細資訊，請參閱[Lync Server 2013 中的 [回應] 群組技術需求](lync-server-2013-technical-requirements-for-response-group.md)。</span><span class="sxs-lookup"><span data-stu-id="592ea-126">For details, see [Technical requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


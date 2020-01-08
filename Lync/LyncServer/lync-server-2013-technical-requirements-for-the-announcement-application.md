---
title: Lync Server 2013：宣告應用程式的技術需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec0da862ce2032f5a659c9e9b7bd3b437349a3cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="ffef4-102">Lync Server 2013 中的宣告應用程式的技術需求</span><span class="sxs-lookup"><span data-stu-id="ffef4-102">Technical requirements for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffef4-103">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="ffef4-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="ffef4-104">本節說明宣告應用程式的下列技術需求：</span><span class="sxs-lookup"><span data-stu-id="ffef4-104">This section describes the following technical requirements for the Announcement application:</span></span>

  - <span data-ttu-id="ffef4-105">硬體需求</span><span class="sxs-lookup"><span data-stu-id="ffef4-105">Hardware requirements</span></span>

  - <span data-ttu-id="ffef4-106">軟體需求</span><span class="sxs-lookup"><span data-stu-id="ffef4-106">Software requirements</span></span>

  - <span data-ttu-id="ffef4-107">埠需求</span><span class="sxs-lookup"><span data-stu-id="ffef4-107">Port requirements</span></span>

  - <span data-ttu-id="ffef4-108">音訊檔需求</span><span class="sxs-lookup"><span data-stu-id="ffef4-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="ffef4-109">硬體需求</span><span class="sxs-lookup"><span data-stu-id="ffef4-109">Hardware Requirements</span></span>

<span data-ttu-id="ffef4-110">宣告應用程式的硬體需求與前端伺服器相同。</span><span class="sxs-lookup"><span data-stu-id="ffef4-110">The Announcement application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="ffef4-111">如需硬體需求的詳細資訊，請參閱支援檔中的[Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)。</span><span class="sxs-lookup"><span data-stu-id="ffef4-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="ffef4-112">軟體需求</span><span class="sxs-lookup"><span data-stu-id="ffef4-112">Software Requirements</span></span>

<span data-ttu-id="ffef4-113">宣告應用程式的作業系統需求和軟體先決條件與前端伺服器相同。</span><span class="sxs-lookup"><span data-stu-id="ffef4-113">The Announcement application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="ffef4-114">如需軟體需求的詳細資訊，請參閱支援檔中的[Lync server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)。</span><span class="sxs-lookup"><span data-stu-id="ffef4-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="ffef4-115">執行宣告應用程式的所有前端伺服器或標準版伺服器，都必須針對執行 Windows Server 2008 R2 的伺服器安裝 windows Media 格式執行時間，或是執行 Windows Server 2012 的伺服器的 Microsoft Media Foundation，或Windows Server 2012 R2。</span><span class="sxs-lookup"><span data-stu-id="ffef4-115">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="ffef4-116">針對 Windows Server 2008 R2，Windows Media 格式執行時間會安裝為 Windows 桌面體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="ffef4-116">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="ffef4-117">Windows Media 格式執行時間或 Microsoft 媒體基礎是 Windows Media 音訊（.wma）檔案所必需的，這些檔案是宣告應用程式在公告和音樂中播放的檔。</span><span class="sxs-lookup"><span data-stu-id="ffef4-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="ffef4-118">埠需求</span><span class="sxs-lookup"><span data-stu-id="ffef4-118">Port Requirements</span></span>

<span data-ttu-id="ffef4-119">宣告應用程式會使用下列埠：</span><span class="sxs-lookup"><span data-stu-id="ffef4-119">The Announcement application uses the following port:</span></span>

  - <span data-ttu-id="ffef4-120">\*\*\*\*    用於 SIP 偵聽要求的埠5071</span><span class="sxs-lookup"><span data-stu-id="ffef4-120">**Port 5071**   Used for SIP listening requests</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ffef4-121">這個埠是預設設定，您可以使用<STRONG>CsApplicationServer</STRONG> Cmdlet 進行變更。</span><span class="sxs-lookup"><span data-stu-id="ffef4-121">This port is the default setting, which you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="ffef4-122">如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="ffef4-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="ffef4-123">音訊檔需求</span><span class="sxs-lookup"><span data-stu-id="ffef4-123">Audio File Requirements</span></span>

<span data-ttu-id="ffef4-124">宣告應用程式支援 Wave （.wav）檔案格式和 Windows Media 音訊（.wma）檔案格式，以供音樂和公告用。</span><span class="sxs-lookup"><span data-stu-id="ffef4-124">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="ffef4-125">宣告應用程式的音訊檔需求與回應群組應用程式相同。</span><span class="sxs-lookup"><span data-stu-id="ffef4-125">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="ffef4-126">如需詳細資訊，請參閱[Lync Server 2013 中的 [回應] 群組技術需求](lync-server-2013-technical-requirements-for-response-group.md)。</span><span class="sxs-lookup"><span data-stu-id="ffef4-126">For details, see [Technical requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


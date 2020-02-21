---
title: Lync Server 2013： 新的虛擬化功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New virtualization features
ms:assetid: edeb2c41-765e-47b8-8a2b-7a7ce09de2ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721926(v=OCS.15)
ms:contentKeyID: 49733861
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e0b7b6d0d4af8d5aa922262004cf14d33757f42
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-virtualization-features-in-lync-server-2013"></a><span data-ttu-id="e8f41-102">Lync Server 2013 中的新虛擬化功能</span><span class="sxs-lookup"><span data-stu-id="e8f41-102">New virtualization features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8f41-103">_**上次修改主題：** 2013年-11-07_</span><span class="sxs-lookup"><span data-stu-id="e8f41-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="e8f41-104">Lync Server 2013 支援 Windows Server 2012、 Windows Server 2012 R2 和 Windows Server 2008 R2 上的虛擬化。</span><span class="sxs-lookup"><span data-stu-id="e8f41-104">Lync Server 2013 supports virtualization on both Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span> <span data-ttu-id="e8f41-105">支援在 Windows Server 2012 和 Windows Server 2012 R2 包含單一根 I/O 虛擬化 (SR IOV) 功能的支援。</span><span class="sxs-lookup"><span data-stu-id="e8f41-105">Support on Windows Server 2012 and Windows Server 2012 R2 includes support for the Single Root I/O Virtualization (SR-IOV) capabilities.</span></span> <span data-ttu-id="e8f41-106">SR IOV，與實體網路介面卡的虛擬函式會直接指派給虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="e8f41-106">With SR-IOV, the virtual function of a physical network adapter is assigned directly to a virtual machine.</span></span> <span data-ttu-id="e8f41-107">這會增加網路輸送量，並減少網路延遲，同時也減少主機 CPU 額外負荷，才處理網路流量。</span><span class="sxs-lookup"><span data-stu-id="e8f41-107">This increases network throughput and reduces network latency while also reducing the host CPU overhead that is required for processing network traffic.</span></span> <span data-ttu-id="e8f41-108">若要利用 SR IOV，您必須使用的主機伺服器具有 BIOS 支援 SR IOV，以及使用支援 SR IOV 網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="e8f41-108">To take advantage of SR-IOV, you must use a host server which has BIOS which supports SR-IOV, as well as use network adapters that support SR-IOV.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


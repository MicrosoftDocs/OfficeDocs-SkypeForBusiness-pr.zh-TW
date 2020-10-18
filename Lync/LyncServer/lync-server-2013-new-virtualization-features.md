---
title: Lync Server 2013：新的虛擬化功能
description: Lync Server 2013：新的虛擬化功能。
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
ms.openlocfilehash: ac15b8592d158d84807ff9e665dd6da50b699059
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579219"
---
# <a name="new-virtualization-features-in-lync-server-2013"></a><span data-ttu-id="30ee5-103">Lync Server 2013 中的新虛擬化功能</span><span class="sxs-lookup"><span data-stu-id="30ee5-103">New virtualization features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30ee5-104">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="30ee5-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="30ee5-105">Lync Server 2013 支援在 Windows Server 2012、Windows Server 2012 R2 和 Windows Server 2008 R2 上進行虛擬化。</span><span class="sxs-lookup"><span data-stu-id="30ee5-105">Lync Server 2013 supports virtualization on both Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span> <span data-ttu-id="30ee5-106">在 Windows Server 2012 和 Windows Server 2012 R2 上的支援包括對單一根 I/O 虛擬化 (SR-IOV) 功能的支援。</span><span class="sxs-lookup"><span data-stu-id="30ee5-106">Support on Windows Server 2012 and Windows Server 2012 R2 includes support for the Single Root I/O Virtualization (SR-IOV) capabilities.</span></span> <span data-ttu-id="30ee5-107">使用 SR-IOV 時，實體網路介面卡的虛擬功能會直接指派給虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="30ee5-107">With SR-IOV, the virtual function of a physical network adapter is assigned directly to a virtual machine.</span></span> <span data-ttu-id="30ee5-108">這會增加網路輸送量並減少網路延遲，同時減少處理網路流量所需的主機 CPU 負荷。</span><span class="sxs-lookup"><span data-stu-id="30ee5-108">This increases network throughput and reduces network latency while also reducing the host CPU overhead that is required for processing network traffic.</span></span> <span data-ttu-id="30ee5-109">若要利用 SR-IOV，您必須使用具有支援 SR-IOV 之 BIOS 的主機伺服器，以及使用支援 SR-IOV 的網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="30ee5-109">To take advantage of SR-IOV, you must use a host server which has BIOS which supports SR-IOV, as well as use network adapters that support SR-IOV.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


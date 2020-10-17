---
title: Lync Server 2013：掃描病毒及檢查病毒定義
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scanning for viruses and checking virus definitions
ms:assetid: 287c0f43-82d1-4c1d-b08f-77112fcb5bfa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720909(v=OCS.15)
ms:contentKeyID: 63969589
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1432480cbe62aedfc5c05362cc322d971c3cb321
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510860"
---
# <a name="scanning-for-viruses-and-checking-virus-definitions-in-lync-server-2013"></a><span data-ttu-id="0b190-102">在 Lync Server 2013 中掃描病毒及檢查病毒定義</span><span class="sxs-lookup"><span data-stu-id="0b190-102">Scanning for viruses and checking virus definitions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b190-103">_**主題上次修改日期：** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="0b190-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<span data-ttu-id="0b190-104">強烈建議安裝 IM 層級的防病毒產品。</span><span class="sxs-lookup"><span data-stu-id="0b190-104">We highly recommend installing an IM-level antivirus product.</span></span> <span data-ttu-id="0b190-105">IM 是眾所周知的來源，可快速散佈整個組織中的病毒和惡意軟體。</span><span class="sxs-lookup"><span data-stu-id="0b190-105">IM is a well-known source for quickly spreading both virus and malicious software throughout an organization.</span></span> <span data-ttu-id="0b190-106">Microsoft Forefront®的 Lync Server 安全性，可提供多引擎掃描，包含病毒、惡意軟體、檔案及關鍵字篩選保護，以及與 Office 通訊伺服器的無縫整合。</span><span class="sxs-lookup"><span data-stu-id="0b190-106">Microsoft Forefront® Security for Lync Server provides multi-engine scanning with virus, malicious software, file and keyword filter protection and seamless integration with Office Communications Server.</span></span>

<span data-ttu-id="0b190-107">除了 Forefront Security for Lync Server 之外，我們也強烈建議安裝檔級的防病毒解決方案，以保護伺服器的檔案系統。</span><span class="sxs-lookup"><span data-stu-id="0b190-107">In addition to Forefront Security for Lync Server, we also highly recommend installing a file-level, antivirus solution to protect the server’s file system.</span></span>

<span data-ttu-id="0b190-108">保持掃描程式引擎和病毒定義的更新十分重要。</span><span class="sxs-lookup"><span data-stu-id="0b190-108">Keeping scanner engines and virus definitions updated is very important.</span></span> <span data-ttu-id="0b190-109">設定和監控更新的健康情況，可確保使用最新的掃描資訊來保護 Office 通訊伺服器及檔案系統。</span><span class="sxs-lookup"><span data-stu-id="0b190-109">Configuring and monitoring the health of the updates makes sure that the most current scanning information is being used to protect both Office Communications Server and file-system.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0b190-110">在執行 lync server 2013 及 Forefront Security for Lync Server 的伺服器上使用協力廠商的檔案層級防毒軟體時，請確定未掃描 Lync Server 和 Lync Server 的 Forefront Security 所安裝的資料夾，以避免其損毀。</span><span class="sxs-lookup"><span data-stu-id="0b190-110">When using a third-party, file-level antivirus software on a server that runs Lync Server 2013 and Forefront Security for Lync Server, make sure that the folders in which Forefront Security for Lync Server and the Lync Server are installed are not scanned, to prevent their corruption.</span></span> <span data-ttu-id="0b190-111">如需排除的完整清單，請參閱 <A class=uri href="https://support.microsoft.com/kb/943620">https://support.microsoft.com/kb/943620</A> 。</span><span class="sxs-lookup"><span data-stu-id="0b190-111">For the full list of exclusions, see <A class=uri href="https://support.microsoft.com/kb/943620">https://support.microsoft.com/kb/943620</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


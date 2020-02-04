---
title: Lync Server 2013：掃描病毒並檢查病毒定義
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
ms.openlocfilehash: fb36ec86c5e9d30e6a215a89748a02e5ef355b73
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scanning-for-viruses-and-checking-virus-definitions-in-lync-server-2013"></a><span data-ttu-id="7829e-102">在 Lync Server 2013 中掃描病毒及檢查病毒定義</span><span class="sxs-lookup"><span data-stu-id="7829e-102">Scanning for viruses and checking virus definitions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7829e-103">_**主題上次修改日期：** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="7829e-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<span data-ttu-id="7829e-104">我們強烈建議您安裝 IM 層級的防病毒產品。</span><span class="sxs-lookup"><span data-stu-id="7829e-104">We highly recommend installing an IM-level antivirus product.</span></span> <span data-ttu-id="7829e-105">IM 是一個知名來源，能讓整個組織快速散佈病毒和惡意軟體。</span><span class="sxs-lookup"><span data-stu-id="7829e-105">IM is a well-known source for quickly spreading both virus and malicious software throughout an organization.</span></span> <span data-ttu-id="7829e-106">Microsoft Forefront® Lync Server 的安全性可提供多引擎掃描，包括病毒、惡意軟體、檔案及關鍵字篩選保護，以及與 Office 通訊伺服器的流暢整合。</span><span class="sxs-lookup"><span data-stu-id="7829e-106">Microsoft Forefront® Security for Lync Server provides multi-engine scanning with virus, malicious software, file and keyword filter protection and seamless integration with Office Communications Server.</span></span>

<span data-ttu-id="7829e-107">除了 Lync Server 的 Forefront Security 之外，我們也強烈建議您安裝可保護伺服器檔案系統的檔案層級防病毒方案。</span><span class="sxs-lookup"><span data-stu-id="7829e-107">In addition to Forefront Security for Lync Server, we also highly recommend installing a file-level, antivirus solution to protect the server’s file system.</span></span>

<span data-ttu-id="7829e-108">保持掃描器引擎與病毒定義的更新非常重要。</span><span class="sxs-lookup"><span data-stu-id="7829e-108">Keeping scanner engines and virus definitions updated is very important.</span></span> <span data-ttu-id="7829e-109">設定及監視更新的健康情況，可以確保使用最新的掃描資訊來保護 Office 通訊伺服器與檔案系統。</span><span class="sxs-lookup"><span data-stu-id="7829e-109">Configuring and monitoring the health of the updates makes sure that the most current scanning information is being used to protect both Office Communications Server and file-system.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7829e-110">在運行 lync server 2013 和 lync server 的 Forefront Security 的伺服器上使用協力廠商的檔案層式防毒軟體時，請確認未掃描在其中安裝 Lync Server 和 Lync Server Forefront Security 的資料夾，以免發生其損毀。</span><span class="sxs-lookup"><span data-stu-id="7829e-110">When using a third-party, file-level antivirus software on a server that runs Lync Server 2013 and Forefront Security for Lync Server, make sure that the folders in which Forefront Security for Lync Server and the Lync Server are installed are not scanned, to prevent their corruption.</span></span> <span data-ttu-id="7829e-111">如需排除的完整清單，請<A class=uri href="http://support.microsoft.com/kb/943620">http://support.microsoft.com/kb/943620</A>參閱。</span><span class="sxs-lookup"><span data-stu-id="7829e-111">For the full list of exclusions, see <A class=uri href="http://support.microsoft.com/kb/943620">http://support.microsoft.com/kb/943620</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


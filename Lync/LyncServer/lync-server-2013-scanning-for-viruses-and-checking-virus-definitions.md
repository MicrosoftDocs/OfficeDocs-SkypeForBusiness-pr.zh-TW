---
title: Lync Server 2013： 有病毒掃描，並檢查病毒定義
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
ms.openlocfilehash: 1bc6704329dbc124bb61f779bf773a1f55bd72d2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scanning-for-viruses-and-checking-virus-definitions-in-lync-server-2013"></a><span data-ttu-id="13b76-102">有病毒掃描，並檢查 Lync Server 2013 中的病毒定義</span><span class="sxs-lookup"><span data-stu-id="13b76-102">Scanning for viruses and checking virus definitions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13b76-103">_**上次修改主題：** 2014年-05-01_</span><span class="sxs-lookup"><span data-stu-id="13b76-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<span data-ttu-id="13b76-104">我們強烈建議您安裝 IM 層級防毒軟體產品。</span><span class="sxs-lookup"><span data-stu-id="13b76-104">We highly recommend installing an IM-level antivirus product.</span></span> <span data-ttu-id="13b76-105">IM 是快速分配病毒和整個組織的惡意軟體的已知來源。</span><span class="sxs-lookup"><span data-stu-id="13b76-105">IM is a well-known source for quickly spreading both virus and malicious software throughout an organization.</span></span> <span data-ttu-id="13b76-106">Microsoft Forefront® Security for Lync Server 提供多引擎掃描病毒、 惡意軟體、 檔案和與關鍵字篩選保護與 Office Communications Server 緊密整合。</span><span class="sxs-lookup"><span data-stu-id="13b76-106">Microsoft Forefront® Security for Lync Server provides multi-engine scanning with virus, malicious software, file and keyword filter protection and seamless integration with Office Communications Server.</span></span>

<span data-ttu-id="13b76-107">除了 Forefront Security for Lync Server，我們也強烈建議安裝的檔案層級防毒解決方案來保護伺服器的檔案系統。</span><span class="sxs-lookup"><span data-stu-id="13b76-107">In addition to Forefront Security for Lync Server, we also highly recommend installing a file-level, antivirus solution to protect the server’s file system.</span></span>

<span data-ttu-id="13b76-108">保持掃描器引擎和防毒更新的定義是非常重要。</span><span class="sxs-lookup"><span data-stu-id="13b76-108">Keeping scanner engines and virus definitions updated is very important.</span></span> <span data-ttu-id="13b76-109">設定和監控的健康狀況來更新可確保最新的掃描資訊要用來保護 Office Communications Server 和檔案系統。</span><span class="sxs-lookup"><span data-stu-id="13b76-109">Configuring and monitoring the health of the updates makes sure that the most current scanning information is being used to protect both Office Communications Server and file-system.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="13b76-110">當執行 Lync Server 2013 和 Forefront Security for Lync Server 的伺服器上使用協力廠商進行檔案層級的防毒軟體，請確定已安裝哪個 Forefront Security for Lync Server 和 Lync Server 中的資料夾，則不會掃描，以避免其損毀。</span><span class="sxs-lookup"><span data-stu-id="13b76-110">When using a third-party, file-level antivirus software on a server that runs Lync Server 2013 and Forefront Security for Lync Server, make sure that the folders in which Forefront Security for Lync Server and the Lync Server are installed are not scanned, to prevent their corruption.</span></span> <span data-ttu-id="13b76-111">排除的完整清單，請參閱<A class=uri href="https://support.microsoft.com/kb/943620">https://support.microsoft.com/kb/943620</A>。</span><span class="sxs-lookup"><span data-stu-id="13b76-111">For the full list of exclusions, see <A class=uri href="https://support.microsoft.com/kb/943620">https://support.microsoft.com/kb/943620</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


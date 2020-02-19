---
title: Lync Server 2013： 詳細通話記錄 (CDR)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call detail recording (CDR)
ms:assetid: 67726075-c77c-4191-a64f-a1cf5c7bcbb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688079(v=OCS.15)
ms:contentKeyID: 49733675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c10c1ef0b48157c69789ed26221d9f6367f5d5e0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-detail-recording-cdr-in-lync-server-2013"></a><span data-ttu-id="d9d9d-102">通話詳細記錄 (CDR) 在 [Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9d9d-102">Call detail recording (CDR) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9d9d-103">_**主題上次修改日期：** 2012年-10-22_</span><span class="sxs-lookup"><span data-stu-id="d9d9d-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="d9d9d-104">詳細通話記錄 (CDR) 會記錄對等活動的使用和診斷資訊，包括立即訊息、Voice over Internet Protocol (VoIP) 通話、應用程式共用、檔案傳輸和會議。</span><span class="sxs-lookup"><span data-stu-id="d9d9d-104">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities, including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings.</span></span> <span data-ttu-id="d9d9d-105">使用資料可用來計算投資報酬率 (ROI)，而診斷資料可用來疑難排解對等活動和會議。</span><span class="sxs-lookup"><span data-stu-id="d9d9d-105">The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span> <span data-ttu-id="d9d9d-106">當您安裝 Lync Server 2013 時，您也會安裝預先定義的 CDR 的通用組態設定集合。</span><span class="sxs-lookup"><span data-stu-id="d9d9d-106">When you install Lync Server 2013, you will also install a predefined collection of global configuration settings for CDR.</span></span> <span data-ttu-id="d9d9d-107">請使用本節中的主題來設定 CDR。</span><span class="sxs-lookup"><span data-stu-id="d9d9d-107">Use the topics in this section to configure CDR.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d9d9d-108">本章節內容</span><span class="sxs-lookup"><span data-stu-id="d9d9d-108">In This Section</span></span>

  - [<span data-ttu-id="d9d9d-109">Lync Server 2013 中檢視 CDR 組態資訊</span><span class="sxs-lookup"><span data-stu-id="d9d9d-109">View CDR configuration information in Lync Server 2013</span></span>](lync-server-2013-view-cdr-configuration-information.md)

  - [<span data-ttu-id="d9d9d-110">啟用 Lync Server 2013 中的通話詳細記錄</span><span class="sxs-lookup"><span data-stu-id="d9d9d-110">Enable call detail recording in Lync Server 2013</span></span>](lync-server-2013-enable-call-detail-recording.md)

  - [<span data-ttu-id="d9d9d-111">建立或修改的 Lync Server 2013 中的 CDR 組態設定集合</span><span class="sxs-lookup"><span data-stu-id="d9d9d-111">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-cdr-configuration-settings.md)

  - [<span data-ttu-id="d9d9d-112">刪除現有的 Lync Server 2013 中的 CDR 組態設定集合</span><span class="sxs-lookup"><span data-stu-id="d9d9d-112">Delete an existing collection of CDR configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-cdr-configuration-settings.md)

  - [<span data-ttu-id="d9d9d-113">手動清除詳細通話記錄及 Lync Server 2013 中的經驗品質資料庫</span><span class="sxs-lookup"><span data-stu-id="d9d9d-113">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>](lync-server-2013-manually-purging-the-call-detail-recording-and-quality-of-experience-databases.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d9d9d-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d9d9d-114">See Also</span></span>


[<span data-ttu-id="d9d9d-115">在 Lync Server 2013 中設定詳細通話記錄與經驗品質設定</span><span class="sxs-lookup"><span data-stu-id="d9d9d-115">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</span></span>](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


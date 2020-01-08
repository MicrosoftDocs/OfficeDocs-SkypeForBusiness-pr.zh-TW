---
title: Lync Server 2013：檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Documentation
ms:assetid: 5a69c0a2-0986-49c3-809c-89bc175a34ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720335(v=OCS.15)
ms:contentKeyID: 63969609
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0b54d4bc007ecdf58cfb3a472a990ffc7a51158
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="documentation-in-lync-server-2013"></a><span data-ttu-id="efc5c-102">Lync Server 2013 中的檔</span><span class="sxs-lookup"><span data-stu-id="efc5c-102">Documentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efc5c-103">_**主題上次修改日期：** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="efc5c-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="efc5c-104">MOF 模型是由許多服務管理功能所組成。</span><span class="sxs-lookup"><span data-stu-id="efc5c-104">The MOF model is composed of many service management functions.</span></span> <span data-ttu-id="efc5c-105">有關如何以及何時執行工作的檔，可以與相同團隊或其他團隊的成員共用。</span><span class="sxs-lookup"><span data-stu-id="efc5c-105">Documentation about how and when tasks are performed can be shared with members of the same team or with other teams.</span></span> <span data-ttu-id="efc5c-106">儲存及共用檔的方法可能會根據函數類型而有所不同。</span><span class="sxs-lookup"><span data-stu-id="efc5c-106">The method of storing and sharing documentation can vary according to the type of function.</span></span> <span data-ttu-id="efc5c-107">例如，系統管理的程式可能會儲存為 Word 檔，因為它們可能會經常列印並加以參照。</span><span class="sxs-lookup"><span data-stu-id="efc5c-107">For example, the procedures for system administration may be stored as Word documents because they are likely to be printed and referenced frequently.</span></span> <span data-ttu-id="efc5c-108">建構管理資訊可能會自動產生並儲存在資料庫中，以方便搜尋和編制索引。</span><span class="sxs-lookup"><span data-stu-id="efc5c-108">Configuration management information may be automatically generated and stored in a database for easy searching and indexing.</span></span> <span data-ttu-id="efc5c-109">有些檔可能是敏感的，應該受到限制。</span><span class="sxs-lookup"><span data-stu-id="efc5c-109">Some documentation may be sensitive and should be restricted.</span></span>

<div>

## <a name="document-management-systems"></a><span data-ttu-id="efc5c-110">檔管理系統</span><span class="sxs-lookup"><span data-stu-id="efc5c-110">Document management systems</span></span>

<span data-ttu-id="efc5c-111">檔管理系統是檔的中央文件庫，可協助確保只有最新版本的檔可供使用。</span><span class="sxs-lookup"><span data-stu-id="efc5c-111">A documentation management system acts as a central repository for documents and helps ensure that only the latest revision of a document is available.</span></span> <span data-ttu-id="efc5c-112">您也可以考慮封存較舊版本的檔以供參考。</span><span class="sxs-lookup"><span data-stu-id="efc5c-112">You can also consider archiving the older version of the document for reference.</span></span> <span data-ttu-id="efc5c-113">Lync Server 提供適合此任務的功能。</span><span class="sxs-lookup"><span data-stu-id="efc5c-113">Lync Server provides functionality suitable to this task.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="efc5c-114">資料庫</span><span class="sxs-lookup"><span data-stu-id="efc5c-114">Databases</span></span>

<span data-ttu-id="efc5c-115">我們討論了幾個適用于使用資料庫的工具和管理功能。</span><span class="sxs-lookup"><span data-stu-id="efc5c-115">Several tools and management functions were discussed that are suited to using databases.</span></span> <span data-ttu-id="efc5c-116">建構管理程式可能會使用自動程式儲存大量需要編制索引及搜尋的資料。</span><span class="sxs-lookup"><span data-stu-id="efc5c-116">The configuration management process is likely to use automated processes that store large amounts of data that require indexing and searching.</span></span> <span data-ttu-id="efc5c-117">支援人員可能會在針對新問題進行疑難排解時搜尋過去問題和解決方式的資料庫。</span><span class="sxs-lookup"><span data-stu-id="efc5c-117">Support staff may search a database of past issues and resolutions when troubleshooting new issues.</span></span>

<span data-ttu-id="efc5c-118">可能會有不同的資料庫被用於不同的用途。</span><span class="sxs-lookup"><span data-stu-id="efc5c-118">It is likely that there will be different databases being used for different purposes.</span></span> <span data-ttu-id="efc5c-119">決定這些資料庫是否應該連結或合併。</span><span class="sxs-lookup"><span data-stu-id="efc5c-119">Decide if these databases should be linked or combined.</span></span> <span data-ttu-id="efc5c-120">例如，如果服務台發現常見主題有幾個問題（例如新的軟體造成特定網路介面卡的問題），支援人員可以查詢設定資料庫，以預測可能會受到影響的電腦數。</span><span class="sxs-lookup"><span data-stu-id="efc5c-120">For example, if the service desk identifies several issues with a common theme (such as new software causing an issue with a particular network adapter), the support staff can query the configuration database to predict how many computers might be affected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


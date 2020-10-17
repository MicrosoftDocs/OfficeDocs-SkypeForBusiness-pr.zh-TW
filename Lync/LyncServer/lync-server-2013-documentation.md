---
title: Lync Server 2013：檔
description: Lync Server 2013：檔。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Documentation
ms:assetid: 5a69c0a2-0986-49c3-809c-89bc175a34ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720335(v=OCS.15)
ms:contentKeyID: 63969609
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f128daa7941db8ae461b4bb12bcc9b97bbb5876e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553209"
---
# <a name="documentation-in-lync-server-2013"></a><span data-ttu-id="90277-103">Lync Server 2013 中的檔</span><span class="sxs-lookup"><span data-stu-id="90277-103">Documentation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90277-104">_**主題上次修改日期：** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="90277-104">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="90277-105">MOF 模型是由許多服務管理功能所組成。</span><span class="sxs-lookup"><span data-stu-id="90277-105">The MOF model is composed of many service management functions.</span></span> <span data-ttu-id="90277-106">有關如何以及何時執行工作的檔，可以與相同小組的成員或其他小組共用。</span><span class="sxs-lookup"><span data-stu-id="90277-106">Documentation about how and when tasks are performed can be shared with members of the same team or with other teams.</span></span> <span data-ttu-id="90277-107">儲存和共用檔的方法可能會因函數類型而異。</span><span class="sxs-lookup"><span data-stu-id="90277-107">The method of storing and sharing documentation can vary according to the type of function.</span></span> <span data-ttu-id="90277-108">例如，系統管理的程式可能會儲存為 Word 檔，因為它們可能會經常列印和參照。</span><span class="sxs-lookup"><span data-stu-id="90277-108">For example, the procedures for system administration may be stored as Word documents because they are likely to be printed and referenced frequently.</span></span> <span data-ttu-id="90277-109">設定管理資訊可能會自動產生，並儲存在資料庫中，以方便搜尋和編制索引。</span><span class="sxs-lookup"><span data-stu-id="90277-109">Configuration management information may be automatically generated and stored in a database for easy searching and indexing.</span></span> <span data-ttu-id="90277-110">有些檔可能是保密的，應加以限制。</span><span class="sxs-lookup"><span data-stu-id="90277-110">Some documentation may be sensitive and should be restricted.</span></span>

<div>

## <a name="document-management-systems"></a><span data-ttu-id="90277-111">檔管理系統</span><span class="sxs-lookup"><span data-stu-id="90277-111">Document management systems</span></span>

<span data-ttu-id="90277-112">檔管理系統充當檔的中央存放庫，並協助確保只有最新的檔版本可供使用。</span><span class="sxs-lookup"><span data-stu-id="90277-112">A documentation management system acts as a central repository for documents and helps ensure that only the latest revision of a document is available.</span></span> <span data-ttu-id="90277-113">您也可以考慮封存檔的舊版本以供參考。</span><span class="sxs-lookup"><span data-stu-id="90277-113">You can also consider archiving the older version of the document for reference.</span></span> <span data-ttu-id="90277-114">Lync Server 提供此工作適用的功能。</span><span class="sxs-lookup"><span data-stu-id="90277-114">Lync Server provides functionality suitable to this task.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="90277-115">資料庫</span><span class="sxs-lookup"><span data-stu-id="90277-115">Databases</span></span>

<span data-ttu-id="90277-116">討論的一些工具和管理功能與使用資料庫非常相關。</span><span class="sxs-lookup"><span data-stu-id="90277-116">Several tools and management functions were discussed that are suited to using databases.</span></span> <span data-ttu-id="90277-117">設定管理程式可能會使用儲存大量資料的自動化程式，而這些資料需要編制索引及搜尋。</span><span class="sxs-lookup"><span data-stu-id="90277-117">The configuration management process is likely to use automated processes that store large amounts of data that require indexing and searching.</span></span> <span data-ttu-id="90277-118">支援人員在疑難排解新問題時，可能會搜尋過去問題和解決方法的資料庫。</span><span class="sxs-lookup"><span data-stu-id="90277-118">Support staff may search a database of past issues and resolutions when troubleshooting new issues.</span></span>

<span data-ttu-id="90277-119">在不同的情況中，可能會使用不同的資料庫。</span><span class="sxs-lookup"><span data-stu-id="90277-119">It is likely that there will be different databases being used for different purposes.</span></span> <span data-ttu-id="90277-120">決定是否應該連結或合併這些資料庫。</span><span class="sxs-lookup"><span data-stu-id="90277-120">Decide if these databases should be linked or combined.</span></span> <span data-ttu-id="90277-121">例如，如果服務台發現一般主題 (的幾個問題，例如新的軟體導致特定網路介面卡發生問題) ，支援人員就可以查詢設定資料庫，以預測可能影響的電腦數目。</span><span class="sxs-lookup"><span data-stu-id="90277-121">For example, if the service desk identifies several issues with a common theme (such as new software causing an issue with a particular network adapter), the support staff can query the configuration database to predict how many computers might be affected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


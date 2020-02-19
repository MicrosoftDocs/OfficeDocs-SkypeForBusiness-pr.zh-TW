---
title: Lync Server 2013： 文件
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
ms.openlocfilehash: c834194244c7c3d483d299958468437c22eeda61
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137512"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="documentation-in-lync-server-2013"></a><span data-ttu-id="80fb1-102">Lync Server 2013 中的文件</span><span class="sxs-lookup"><span data-stu-id="80fb1-102">Documentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80fb1-103">_**主題上次修改日期：** 2015年-05-15_</span><span class="sxs-lookup"><span data-stu-id="80fb1-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="80fb1-104">MOF 模型是由許多服務管理功能所組成。</span><span class="sxs-lookup"><span data-stu-id="80fb1-104">The MOF model is composed of many service management functions.</span></span> <span data-ttu-id="80fb1-105">使用相同的小組的成員，或與其他小組可以共用文件中的有關如何及何時執行工作。</span><span class="sxs-lookup"><span data-stu-id="80fb1-105">Documentation about how and when tasks are performed can be shared with members of the same team or with other teams.</span></span> <span data-ttu-id="80fb1-106">儲存與共用文件的方法可以因函數的類型。</span><span class="sxs-lookup"><span data-stu-id="80fb1-106">The method of storing and sharing documentation can vary according to the type of function.</span></span> <span data-ttu-id="80fb1-107">例如，進行系統管理工作的程序可能會儲存為 Word 文件因為它們可能會列印及經常參照。</span><span class="sxs-lookup"><span data-stu-id="80fb1-107">For example, the procedures for system administration may be stored as Word documents because they are likely to be printed and referenced frequently.</span></span> <span data-ttu-id="80fb1-108">組態管理資訊可能會自動產生並儲存在資料庫中的簡單搜尋與編製索引。</span><span class="sxs-lookup"><span data-stu-id="80fb1-108">Configuration management information may be automatically generated and stored in a database for easy searching and indexing.</span></span> <span data-ttu-id="80fb1-109">某個文件中可能敏感，而且應該限制。</span><span class="sxs-lookup"><span data-stu-id="80fb1-109">Some documentation may be sensitive and should be restricted.</span></span>

<div>

## <a name="document-management-systems"></a><span data-ttu-id="80fb1-110">文件管理系統</span><span class="sxs-lookup"><span data-stu-id="80fb1-110">Document management systems</span></span>

<span data-ttu-id="80fb1-111">文件管理系統作為文件的集中存放庫，以協助確保只有最新的修訂的文件，均提供。</span><span class="sxs-lookup"><span data-stu-id="80fb1-111">A documentation management system acts as a central repository for documents and helps ensure that only the latest revision of a document is available.</span></span> <span data-ttu-id="80fb1-112">您也可以考慮封存參考文件的舊版本。</span><span class="sxs-lookup"><span data-stu-id="80fb1-112">You can also consider archiving the older version of the document for reference.</span></span> <span data-ttu-id="80fb1-113">Lync Server 提供更適合這項工作的功能。</span><span class="sxs-lookup"><span data-stu-id="80fb1-113">Lync Server provides functionality suitable to this task.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="80fb1-114">資料庫</span><span class="sxs-lookup"><span data-stu-id="80fb1-114">Databases</span></span>

<span data-ttu-id="80fb1-115">數個工具和管理功能所討論，適用於使用的資料庫。</span><span class="sxs-lookup"><span data-stu-id="80fb1-115">Several tools and management functions were discussed that are suited to using databases.</span></span> <span data-ttu-id="80fb1-116">設定管理程序是可能會使用儲存大量的資料需要編製索引和搜尋功能的自動化處理程序。</span><span class="sxs-lookup"><span data-stu-id="80fb1-116">The configuration management process is likely to use automated processes that store large amounts of data that require indexing and searching.</span></span> <span data-ttu-id="80fb1-117">支援人員可能會搜尋過去的問題與解決方案的資料庫，當新的問題的疑難排解。</span><span class="sxs-lookup"><span data-stu-id="80fb1-117">Support staff may search a database of past issues and resolutions when troubleshooting new issues.</span></span>

<span data-ttu-id="80fb1-118">很可能會有不同的資料庫正在用於不同用途。</span><span class="sxs-lookup"><span data-stu-id="80fb1-118">It is likely that there will be different databases being used for different purposes.</span></span> <span data-ttu-id="80fb1-119">決定是否應連結或結合這些資料庫。</span><span class="sxs-lookup"><span data-stu-id="80fb1-119">Decide if these databases should be linked or combined.</span></span> <span data-ttu-id="80fb1-120">例如，如果服務台具有共通主題 （例如特定網路介面卡造成此問題： 新的軟體） 識別幾個問題，支援人員可以查詢要預測多少電腦可能會受到影響的設定資料庫。</span><span class="sxs-lookup"><span data-stu-id="80fb1-120">For example, if the service desk identifies several issues with a common theme (such as new software causing an issue with a particular network adapter), the support staff can query the configuration database to predict how many computers might be affected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


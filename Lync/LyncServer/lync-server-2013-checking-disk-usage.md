---
title: Lync Server 2013： 檢查磁碟使用狀況
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0cb167d2a7aed3f5c107d4beba568c00ac501e0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a><span data-ttu-id="052b0-102">Lync Server 2013 中的檢查磁碟使用狀況</span><span class="sxs-lookup"><span data-stu-id="052b0-102">Checking disk usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="052b0-103">_**上次修改主題：** 2014年-04-30_</span><span class="sxs-lookup"><span data-stu-id="052b0-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="052b0-104">硬碟機是 Lync Server 2013 部署的重要元件。</span><span class="sxs-lookup"><span data-stu-id="052b0-104">Hard disks drives are an important component of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="052b0-105">沒有足夠的可用磁碟區，作業系統和 Lync Server 2013 資料庫都可以正常運作。</span><span class="sxs-lookup"><span data-stu-id="052b0-105">Without sufficient free disk volume, neither the operating system nor the Lync Server 2013 databases can function correctly.</span></span> <span data-ttu-id="052b0-106">您必須監視的 Lync Server 2013 後端資料庫統計資料每日可協助確定伺服器不要執行磁碟空間不足，並準備視需要新增存放裝置資源。</span><span class="sxs-lookup"><span data-stu-id="052b0-106">You must monitor the Lync Server 2013 back-end database statistics daily to help to make sure that servers do not run out of disk space, and to prepare to add storage resources as required.</span></span>

<span data-ttu-id="052b0-107">不同於檢查上主控的作業系統，程式檔案、 資料庫和交易記錄檔 （Lync Server 2013 後端） 的磁碟空間，您也應該監視包含磁碟空間可供包含下列重要的檔案共用的檔案系統的使用方式資料：</span><span class="sxs-lookup"><span data-stu-id="052b0-107">Apart from checking space on disks hosting the operating system, program files, database, and transaction logs (Lync Server 2013 Back End), you should also monitor usage of the file system that includes disk space for file shares that contain the following important data:</span></span>

  - <span data-ttu-id="052b0-108">會議內容</span><span class="sxs-lookup"><span data-stu-id="052b0-108">Meeting content</span></span>

  - <span data-ttu-id="052b0-109">會議內容中繼資料</span><span class="sxs-lookup"><span data-stu-id="052b0-109">Meeting content metadata</span></span>

  - <span data-ttu-id="052b0-110">會議規範記錄</span><span class="sxs-lookup"><span data-stu-id="052b0-110">Meeting compliance logs</span></span>

  - <span data-ttu-id="052b0-111">應用程式資料檔案 （用於內部應用程式伺服器元件）</span><span class="sxs-lookup"><span data-stu-id="052b0-111">Application data files (used internally by the application server component)</span></span>

  - <span data-ttu-id="052b0-112">群組聊天伺服器 web 服務及符合性資料夾 （若要儲存檔案上傳到 [Group Chat web 服務）</span><span class="sxs-lookup"><span data-stu-id="052b0-112">Group Chat Server web service and compliance folders (to store files uploaded to the Group Chat web service)</span></span>

  - <span data-ttu-id="052b0-113">群組聊天規範的 XML 檔案 （包含 Group Chat 規範記錄）</span><span class="sxs-lookup"><span data-stu-id="052b0-113">Group Chat compliance XML files (that contain Group Chat compliance records)</span></span>

  - <span data-ttu-id="052b0-114">更新檔案 （適用於裝置更新服務）</span><span class="sxs-lookup"><span data-stu-id="052b0-114">Update files (for Device Update Service)</span></span>

  - <span data-ttu-id="052b0-115">通訊錄檔案</span><span class="sxs-lookup"><span data-stu-id="052b0-115">Address Book files</span></span>

<span data-ttu-id="052b0-116">Lync Server 2013 所需的硬碟空間來儲存其資料庫與交易記錄檔，除了先前所列的檔案共用上的檔案。</span><span class="sxs-lookup"><span data-stu-id="052b0-116">Lync Server 2013 needs hard disk space to store its databases and transaction logs in addition to files on file shares previously listed.</span></span>

<span data-ttu-id="052b0-117">您應監視的磁碟空間，定期可協助確定 Lync Server 2013 部署不產生負面影響因為沒有足夠的儲存資源。</span><span class="sxs-lookup"><span data-stu-id="052b0-117">You should monitor the disk space regularly to help to make sure that the Lync Server 2013 deployment is not adversely affected because of insufficient storage resources.</span></span>

<span data-ttu-id="052b0-118">比較和維護每個 Lync Server 2013 的磁碟區與資料庫和交易記錄檔的預期的成長上可用的磁碟空間的統計資訊。</span><span class="sxs-lookup"><span data-stu-id="052b0-118">Compare and maintain statistical information about available disk space on each Lync Server 2013 volume and expected growth of the databases and transaction log files.</span></span> <span data-ttu-id="052b0-119">這可協助容量規劃及必要的存放裝置資源時新增存放裝置。</span><span class="sxs-lookup"><span data-stu-id="052b0-119">This helps with capacity planning and adding storage when the storage resources are required.</span></span>

<span data-ttu-id="052b0-120">若要容納疑難排解和嚴重損壞修復情況下，我們建議您提供的可用磁碟區空間為等於或大於資料庫大小的 110%。</span><span class="sxs-lookup"><span data-stu-id="052b0-120">To accommodate troubleshooting and disaster recovery situations, we recommend that available free volume space be equal or greater than 110 percent of the size of database.</span></span>

<span data-ttu-id="052b0-121">您可以使用下列方法來檢查可用磁碟空間：</span><span class="sxs-lookup"><span data-stu-id="052b0-121">You can check free disk space by using the following methods:</span></span>

1.  <span data-ttu-id="052b0-122">**System Center Operations Manager**   System Center Operations Manager 可用來警告系統管理員，當磁碟區空間會受到限制。</span><span class="sxs-lookup"><span data-stu-id="052b0-122">**System Center Operations Manager**   System Center Operations Manager can be used to warn administrators when volume space is constrained.</span></span>

2.  <span data-ttu-id="052b0-123">**執行指令碼**   執行傳送郵件給您，如果的可用硬碟空間低於 20%的指令碼，以監視磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="052b0-123">**Running a script**   Monitor disk space by running a script that sends you a message if the available hard disk space falls below 20 percent.</span></span> <span data-ttu-id="052b0-124">您可以找到 Microsoft TechNet 上的指令碼中心上的範例指令碼，請檢查：[https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span><span class="sxs-lookup"><span data-stu-id="052b0-124">You can find a sample script on Microsoft Script Center on TechNet, examine: [https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span></span>

3.  <span data-ttu-id="052b0-125">**Windows 檔案總管**   使用 Windows 檔案總管中要檢查的磁碟區上的磁碟空間，Lync Server 2013 記錄該儲存區與資料庫。</span><span class="sxs-lookup"><span data-stu-id="052b0-125">**Windows Explorer**   Use Windows Explorer to check for disk space on volumes that store Lync Server 2013 logs and databases.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


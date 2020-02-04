---
title: Lync Server 2013：檢查磁片使用量
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
ms.openlocfilehash: 554b493ba7ca837a8ea5c80f6751ddb91061c374
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a><span data-ttu-id="17bde-102">在 Lync Server 2013 中檢查磁片使用量</span><span class="sxs-lookup"><span data-stu-id="17bde-102">Checking disk usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17bde-103">_**主題上次修改日期：** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="17bde-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="17bde-104">硬碟磁片磁碟機是 Lync Server 2013 部署的一個重要元件。</span><span class="sxs-lookup"><span data-stu-id="17bde-104">Hard disks drives are an important component of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="17bde-105">若沒有足夠的可用磁碟空間，作業系統和 Lync Server 2013 資料庫都無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="17bde-105">Without sufficient free disk volume, neither the operating system nor the Lync Server 2013 databases can function correctly.</span></span> <span data-ttu-id="17bde-106">您必須每天監視 Lync Server 2013 後端資料庫統計資料，以協助確保伺服器不會用盡磁碟空間，並準備根據需要新增儲存資源。</span><span class="sxs-lookup"><span data-stu-id="17bde-106">You must monitor the Lync Server 2013 back-end database statistics daily to help to make sure that servers do not run out of disk space, and to prepare to add storage resources as required.</span></span>

<span data-ttu-id="17bde-107">除了檢查託管作業系統、程式檔案、資料庫及交易處理記錄（Lync Server 2013 後端）的磁碟空間，您也應該監視檔案系統的使用方式，這些檔案系統包含下列重要檔案共用的磁碟空間資料</span><span class="sxs-lookup"><span data-stu-id="17bde-107">Apart from checking space on disks hosting the operating system, program files, database, and transaction logs (Lync Server 2013 Back End), you should also monitor usage of the file system that includes disk space for file shares that contain the following important data:</span></span>

  - <span data-ttu-id="17bde-108">會議內容</span><span class="sxs-lookup"><span data-stu-id="17bde-108">Meeting content</span></span>

  - <span data-ttu-id="17bde-109">會議內容中繼資料</span><span class="sxs-lookup"><span data-stu-id="17bde-109">Meeting content metadata</span></span>

  - <span data-ttu-id="17bde-110">會議合規性記錄</span><span class="sxs-lookup"><span data-stu-id="17bde-110">Meeting compliance logs</span></span>

  - <span data-ttu-id="17bde-111">應用程式資料檔案（由應用程式伺服器元件在內部使用）</span><span class="sxs-lookup"><span data-stu-id="17bde-111">Application data files (used internally by the application server component)</span></span>

  - <span data-ttu-id="17bde-112">群組聊天伺服器 web 服務與合規性資料夾（儲存已上傳到群組聊天網頁服務的檔案）</span><span class="sxs-lookup"><span data-stu-id="17bde-112">Group Chat Server web service and compliance folders (to store files uploaded to the Group Chat web service)</span></span>

  - <span data-ttu-id="17bde-113">群組聊天合規性 XML 檔案（包含群組聊天合規性記錄）</span><span class="sxs-lookup"><span data-stu-id="17bde-113">Group Chat compliance XML files (that contain Group Chat compliance records)</span></span>

  - <span data-ttu-id="17bde-114">更新檔案（適用于裝置更新服務）</span><span class="sxs-lookup"><span data-stu-id="17bde-114">Update files (for Device Update Service)</span></span>

  - <span data-ttu-id="17bde-115">通訊錄檔案</span><span class="sxs-lookup"><span data-stu-id="17bde-115">Address Book files</span></span>

<span data-ttu-id="17bde-116">Lync Server 2013 需要硬碟空間來儲存其資料庫及事務記錄記錄，以及先前所列的檔案共用中的檔案。</span><span class="sxs-lookup"><span data-stu-id="17bde-116">Lync Server 2013 needs hard disk space to store its databases and transaction logs in addition to files on file shares previously listed.</span></span>

<span data-ttu-id="17bde-117">您應該定期監視磁碟空間，以協助確保 Lync Server 2013 部署由於儲存資源不足而不會受到負面影響。</span><span class="sxs-lookup"><span data-stu-id="17bde-117">You should monitor the disk space regularly to help to make sure that the Lync Server 2013 deployment is not adversely affected because of insufficient storage resources.</span></span>

<span data-ttu-id="17bde-118">針對每個 Lync Server 2013 容量與預期的資料庫及事務記錄檔增長，比較並維持有關可用磁碟空間的統計資訊。</span><span class="sxs-lookup"><span data-stu-id="17bde-118">Compare and maintain statistical information about available disk space on each Lync Server 2013 volume and expected growth of the databases and transaction log files.</span></span> <span data-ttu-id="17bde-119">這有助於在儲存資源需要時，進行容量規劃並新增儲存空間。</span><span class="sxs-lookup"><span data-stu-id="17bde-119">This helps with capacity planning and adding storage when the storage resources are required.</span></span>

<span data-ttu-id="17bde-120">為了適應疑難排解及災害復原的情況，建議可用的可用磁碟空間大小等於或大於資料庫大小的110%。</span><span class="sxs-lookup"><span data-stu-id="17bde-120">To accommodate troubleshooting and disaster recovery situations, we recommend that available free volume space be equal or greater than 110 percent of the size of database.</span></span>

<span data-ttu-id="17bde-121">您可以使用下列方法來查看可用磁碟空間：</span><span class="sxs-lookup"><span data-stu-id="17bde-121">You can check free disk space by using the following methods:</span></span>

1.  <span data-ttu-id="17bde-122">**系統中心作業管理員**   系統中心作業管理員可以用來在卷空間受到限制時向管理員發出警告。</span><span class="sxs-lookup"><span data-stu-id="17bde-122">**System Center Operations Manager**   System Center Operations Manager can be used to warn administrators when volume space is constrained.</span></span>

2.  <span data-ttu-id="17bde-123">\*\*\*\*    如果可用的硬碟空間低於20%，您可以執行腳本來傳送一則腳本來監視磁碟空間，以傳送訊息給您。</span><span class="sxs-lookup"><span data-stu-id="17bde-123">**Running a script**   Monitor disk space by running a script that sends you a message if the available hard disk space falls below 20 percent.</span></span> <span data-ttu-id="17bde-124">您可以在 TechNet 上的 Microsoft 腳本中心找到範例腳本，請檢查：[http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span><span class="sxs-lookup"><span data-stu-id="17bde-124">You can find a sample script on Microsoft Script Center on TechNet, examine: [http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span></span>

3.  <span data-ttu-id="17bde-125">**Windows 資源管理器**   使用 windows 資源管理器來檢查儲存 Lync Server 2013 記錄和資料庫之磁片卷的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="17bde-125">**Windows Explorer**   Use Windows Explorer to check for disk space on volumes that store Lync Server 2013 logs and databases.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


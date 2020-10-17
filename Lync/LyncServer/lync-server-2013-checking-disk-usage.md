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
ms.openlocfilehash: 6379d110fc25ba31062d211d3893567ad92fda1f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526200"
---
# <a name="checking-disk-usage-in-lync-server-2013"></a><span data-ttu-id="b5466-102">在 Lync Server 2013 中檢查磁片使用量</span><span class="sxs-lookup"><span data-stu-id="b5466-102">Checking disk usage in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5466-103">_**主題上次修改日期：** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="b5466-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="b5466-104">硬碟磁片磁碟機是 Lync Server 2013 部署的重要元件。</span><span class="sxs-lookup"><span data-stu-id="b5466-104">Hard disks drives are an important component of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="b5466-105">若沒有足夠的可用磁碟空間，作業系統和 Lync Server 2013 資料庫皆無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="b5466-105">Without sufficient free disk volume, neither the operating system nor the Lync Server 2013 databases can function correctly.</span></span> <span data-ttu-id="b5466-106">您必須每天監視 Lync Server 2013 後端資料庫統計資料，以確保伺服器不會耗盡磁碟空間，並準備好視需要新增儲存體資源。</span><span class="sxs-lookup"><span data-stu-id="b5466-106">You must monitor the Lync Server 2013 back-end database statistics daily to help to make sure that servers do not run out of disk space, and to prepare to add storage resources as required.</span></span>

<span data-ttu-id="b5466-107">除了檢查主控作業系統、程式檔、資料庫和交易記錄的磁碟空間之外 (Lync Server 2013 後端) 之外，您還應該監視包含下列重要資料的檔案共用磁碟空間的檔案系統使用狀況：</span><span class="sxs-lookup"><span data-stu-id="b5466-107">Apart from checking space on disks hosting the operating system, program files, database, and transaction logs (Lync Server 2013 Back End), you should also monitor usage of the file system that includes disk space for file shares that contain the following important data:</span></span>

  - <span data-ttu-id="b5466-108">會議內容</span><span class="sxs-lookup"><span data-stu-id="b5466-108">Meeting content</span></span>

  - <span data-ttu-id="b5466-109">會議內容中繼資料</span><span class="sxs-lookup"><span data-stu-id="b5466-109">Meeting content metadata</span></span>

  - <span data-ttu-id="b5466-110">會議規範記錄</span><span class="sxs-lookup"><span data-stu-id="b5466-110">Meeting compliance logs</span></span>

  - <span data-ttu-id="b5466-111">應用程式伺服器元件 (內部使用的應用程式資料檔案) </span><span class="sxs-lookup"><span data-stu-id="b5466-111">Application data files (used internally by the application server component)</span></span>

  - <span data-ttu-id="b5466-112">Group Chat Server web service 和合規性資料夾 (儲存上傳至群組聊天 web 服務的檔案) </span><span class="sxs-lookup"><span data-stu-id="b5466-112">Group Chat Server web service and compliance folders (to store files uploaded to the Group Chat web service)</span></span>

  - <span data-ttu-id="b5466-113">包含群組聊天規範記錄的群組聊天規範 XML 檔案 () </span><span class="sxs-lookup"><span data-stu-id="b5466-113">Group Chat compliance XML files (that contain Group Chat compliance records)</span></span>

  - <span data-ttu-id="b5466-114">更新裝置更新服務的 (檔案) </span><span class="sxs-lookup"><span data-stu-id="b5466-114">Update files (for Device Update Service)</span></span>

  - <span data-ttu-id="b5466-115">通訊錄檔案</span><span class="sxs-lookup"><span data-stu-id="b5466-115">Address Book files</span></span>

<span data-ttu-id="b5466-116">Lync Server 2013 除先前所列檔案共用上的檔案之外，還需要硬碟空間來儲存其資料庫和交易記錄。</span><span class="sxs-lookup"><span data-stu-id="b5466-116">Lync Server 2013 needs hard disk space to store its databases and transaction logs in addition to files on file shares previously listed.</span></span>

<span data-ttu-id="b5466-117">您應該定期監控磁碟空間，以協助確保 Lync Server 2013 部署不會因為儲存資源不足而受到不良影響。</span><span class="sxs-lookup"><span data-stu-id="b5466-117">You should monitor the disk space regularly to help to make sure that the Lync Server 2013 deployment is not adversely affected because of insufficient storage resources.</span></span>

<span data-ttu-id="b5466-118">比較及維護每個 Lync Server 2013 磁片區上可用磁碟空間的統計資訊，以及資料庫及交易記錄檔的預期成長。</span><span class="sxs-lookup"><span data-stu-id="b5466-118">Compare and maintain statistical information about available disk space on each Lync Server 2013 volume and expected growth of the databases and transaction log files.</span></span> <span data-ttu-id="b5466-119">這可協助您進行容量規劃，並在需要儲存資源時新增儲存體。</span><span class="sxs-lookup"><span data-stu-id="b5466-119">This helps with capacity planning and adding storage when the storage resources are required.</span></span>

<span data-ttu-id="b5466-120">為了容納疑難排解與嚴重損壞修復的情況，建議可用的磁片區空間大小等於或大於資料庫大小的110%。</span><span class="sxs-lookup"><span data-stu-id="b5466-120">To accommodate troubleshooting and disaster recovery situations, we recommend that available free volume space be equal or greater than 110 percent of the size of database.</span></span>

<span data-ttu-id="b5466-121">您可以使用下列方法來檢查可用的磁碟空間：</span><span class="sxs-lookup"><span data-stu-id="b5466-121">You can check free disk space by using the following methods:</span></span>

1.  <span data-ttu-id="b5466-122">**System Center Operations Manager**    在限制磁片區空間時，可以使用 System Center Operations Manager 來警告管理員。</span><span class="sxs-lookup"><span data-stu-id="b5466-122">**System Center Operations Manager**   System Center Operations Manager can be used to warn administrators when volume space is constrained.</span></span>

2.  <span data-ttu-id="b5466-123">執行**腳本**    執行腳本以監視磁碟空間（如果可用的硬碟空間低於20%）。</span><span class="sxs-lookup"><span data-stu-id="b5466-123">**Running a script**   Monitor disk space by running a script that sends you a message if the available hard disk space falls below 20 percent.</span></span> <span data-ttu-id="b5466-124">您可以在 TechNet 上的 [Microsoft Script Center] 中找到範例腳本，請檢查： [https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span><span class="sxs-lookup"><span data-stu-id="b5466-124">You can find a sample script on Microsoft Script Center on TechNet, examine: [https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span></span>

3.  <span data-ttu-id="b5466-125">**Windows Explorer**    使用 Windows Explorer 檢查儲存 Lync Server 2013 記錄和資料庫之磁片區上的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="b5466-125">**Windows Explorer**   Use Windows Explorer to check for disk space on volumes that store Lync Server 2013 logs and databases.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

